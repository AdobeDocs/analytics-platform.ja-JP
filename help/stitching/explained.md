---
title: ステッチの仕組み
description: ステッチの概念を理解する
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
source-git-commit: 8ca11b37ebda952d95ae38473a9c0d62be007e79
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 21%

---

# ステッチの仕組み

ステッチでは、特定のデータセットでデータの受け渡しが最低でも 2 回おこなわれます。

* **ライブステッチ**：各ヒット（イベント）が含まれるたびにステッチを試みます。 「新規」のデバイスからデータセットへのヒット（認証されたことがない）は、通常、このレベルでは結び付けられません。 既に認識されているデバイスからのヒットは、即座に結び付けられます。

* **ステッチを再生**：学習した一意の識別子（一時的な ID）に基づいてデータを「再生」します。 この段階では、以前に不明だったデバイス（永続 ID）からのヒットが（一時的な ID に）結び付けられます。 アドビでは、次の 2 つの再生間隔を用意しています。
   * **毎日**：データは毎日、24 時間のルックバックウィンドウで再生されます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、認証されていない訪問者は、サイトを訪問した日に認証を行う必要があります。
   * **毎週**：データは週に 1 回、7 日間のルックバックウィンドウで再生されます。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 週間未満の未関連付けデータは、次の週次再生まで再処理されません。

* **プライバシー（オプション）**：プライバシー関連のリクエストを受け取った場合、リクエストされた ID を削除する以外に、未認証のイベントでのその ID の結合を元に戻す必要があります。

ルックバックウィンドウを超えたデータは再生されません。未認証の訪問と認証された訪問を一緒に識別するためには、訪問者は、所定のルックバックウィンドウ内で認証する必要があります。デバイスが認識されると、その時点からライブステッチされます。

## 手順 1：ライブステッチ

ライブステッチでは、既知のデバイスやチャネルに対して、収集時に各イベントをステッチしようとします。 次の例では、Bob がイベントデータセットの一部として異なるイベントを記録しています。

*収集された日に表示されるデータ：*

| イベント | タイムスタンプ | 永続 ID (Cookie ID) | 一時的な ID（ログイン ID） | ステッチされた ID（ライブステッチ後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **3 台のデバイス** | | **4 人**:<br/>246, Bob, 3579, 81911 |

新しいデバイスでの未認証イベントと認証イベントは、両方とも別のユーザーとして（一時的に）カウントされます。認識されたデバイスの未認証イベントは、ライブステッチされます。

アトリビューションは、識別するカスタム変数がデバイスに結び付けられる場合に機能します。 上の例では、イベント 1、8、9、10 を除くすべてのイベントがライブステッチされます ( すべて `Bob` 識別子 ) です。 ライブステッチで、イベント 4、6、12 のステッチ済み ID が「解決」されます。


<!--

### Delayed data

When incoming data for 'Live' stitching is delayed and over 24 hours old, and when no identities in that delayed data can be matched against identities already considered for 'Live' stitching, that delayed data is not added to the data considered for 'Live' stitching.

In the example below, the data in event 2 is delayed but will be part of 'Live' stitching.

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **246** |
| 2 | 2023-05-14 12:02 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |

In the example below, the data in event 2 is delayed and will NOT become part of 'Live' stitching.

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **246** |
| ~~2~~ | ~~2023-05-14 12:02~~ | ~~891~~ |  | (not considered for 'Live' stitching) |

-->


## 手順 2：再生のステッチ

再生ステッチでは、一定の間隔（選択したルックバックウィンドウに応じて週に 1 回、または日に 1 回）で、認識されたデバイスに基づいて履歴データが再計算されます。 認証されていない状態でデバイスが最初にデータを送信し、その後ログインした場合は、再生を実行して、未認証のイベントを正しいユーザーに結び付けます。 次の表は、上記と同じデータを示していますが、データの再生に基づいて異なる数字が表示されています。

*再生後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID (Cookie ID) | 一時的な ID（ログイン ID） | ステッチされた ID（ライブステッチ後） | ステッチ済み ID（再生後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![上向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![上向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob |
| | | **3 台のデバイス** | | **4 人**:<br/>246, Bob, 3579, 81911 | **2 人**:<br/>ボブ、3579 年 |

{style="table-layout:auto"}

アトリビューションは、識別するカスタム変数がデバイスに結び付けられる場合に機能します。 上の例では、再生の結果としてイベント 1 と 10 が関連付けられ、イベント 8 と 9 のみが未関連付けのまま残ります。 人物指標（累積）を 2 に減らします。

## 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、元のユーザー情報を含む行と、この同じ人物情報を含む関連付け ID が削除されます。 次の表に、上記と同じデータを示しますが、Bob のプライバシーリクエストがデータの処理後にデータに与える影響を示します。 Bob が認証された行 (2、3、5、7、11) が削除され、他の行の一時的な ID として Bob が削除されます。

*Bob のプライバシーリクエスト後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID (Cookie ID) | 一時的な ID（ログイン ID） | ステッチされた ID（ライブステッチ後） | ステッチ済み ID（再生後） | 一時的な ID（ログイン ID） | ステッチされた ID（プライバシーリクエストの後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![上向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![右向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![下向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![上向き矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3 台のデバイス** | | **4 人**:<br/>246, Bob, 3579, 81911 | **2 人**:<br/>ボブ、3579 年 |  | **3 人**:<br/>246, 3579, 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## 概要

* ステッチでは、既知のデバイスからのイベントを即座にステッチしますが、新しいデバイスや認識されていないデバイスからのイベントは即座にステッチされません。
* データは一定の間隔で再生され、過去に識別されたデバイスに基づいて、接続内の履歴データが変更されます。
* ライブステッチと再生のステッチは、1 つのデータセットで実行されます。 その結果、新しい高度なデータセットが作成され、他のデータセット（コールセンターデータなど）と組み合わせてクロスチャネル分析を実行する場合に適しています。
* プライバシーリクエストは、未認証の行に広がった ID を削除します。
