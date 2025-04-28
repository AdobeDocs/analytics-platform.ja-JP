---
title: フィールドベースのステッチ
description: フィールドベースのステッチの説明
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 9237549aabe73ec98fc42d593e899c98e12eb194
workflow-type: tm+mt
source-wordcount: '1779'
ht-degree: 15%

---

# フィールドベースのステッチ

フィールドベースのステッチでは、イベントデータセットと、そのデータセットの永続 ID （cookie）および一時的な ID （ユーザー ID）を指定します。 フィールドベースのステッチでは、新しいステッチされたデータセットに新しいステッチ ID 列が作成され、その特定の永続 ID の一時的な ID を持つ行に基づいて、このステッチ ID 列が更新されます。 <br/>Customer Journey Analyticsをスタンドアロンソリューションとして使用する場合（Experience Platform ID サービスおよび関連する ID グラフへのアクセス権を持たない場合）、フィールドベースのステッチを使用できます。 または、使用可能な ID グラフを使用しない場合にも使用できます。

![フィールドベースのステッチ](/help/stitching/assets/fbs.png)


## identityMap

フィールドベースのステッチでは、次のシナリオで ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)[`identifyMap` フィールドグループの使用をサポートしています。

- 名前空間でのプライマリ ID`identityMap` 使用して persistentID を定義します。
   - 異なる名前空間に複数のプライマリ ID が見つかった場合、名前空間の ID は辞書的に並べ替えられ、最初の ID が選択されます。
   - 単一の名前空間に複数のプライマリ ID が見つかった場合は、辞書学的に利用できる最初のプライマリ ID が選択されます。

  次の例では、名前空間と ID によりプライマリ ID リストが並べ替えられ、最終的に選択された ID が表示されます。

  <table>
     <tr>
       <th>名前空間</th>
       <th>ID リスト</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table>
    <tr>
      <th>並べ替えられた ID リスト</th>
      <th>選択した ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>


- 名前空間 `identityMap` 使用して、persistentID、transientID、またはその両方を定義します。
   - persistentID または transientID の複数の値が `identityMap` 名前空間で見つかった場合は、最初の辞書編集可能な値が使用されます。
   - persistentID と transientID の名前空間は、相互に排他的にする必要があります。

  以下の例では、名前空間と ID により、選択された名前空間（ECID）で並べ替えられた ID リストが作成され、最後に選択された ID が作成されます。

  <table>
     <tr>
       <th>名前空間</th>
       <th>ID リスト</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table>
    <tr>
      <th>並べ替えられた ID リスト</th>
      <th>選択した ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>

## フィールドベースのステッチの仕組み

ステッチでは、特定のデータセット内のデータに対して少なくとも 2 つのパスが作成されます。

- **ライブステッチ**：各ヒット（イベント）が発生するとそのヒットをステッチしようとします。 データセットに「新規」である（認証されたことのない）デバイスからのヒットは、通常、このレベルでは結び付けられません。 既に認識済みのデバイスからのヒットは、直ちに結合されます。

- **ステッチを再生**：学習した一意の識別子（一時的な ID）に基づいてデータを「再生」します。 このステージでは、以前は不明だったデバイス（永続 ID）からのヒットが（一時的な ID に）結合されます。 再生は、**頻度** および **ルックバックウィンドウ** の 2 つのパラメーターによって決定されます。 Adobeでは、次のパラメーターの組み合わせを使用できます。
   - **毎日の頻度での毎日のルックバック**：データは毎日、24 時間のルックバックウィンドウで再生されます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、認証されていない訪問者は、サイトを訪問した日に認証を行う必要があります。
   - **毎週の頻度での毎週のルックバック**：データは、毎週のルックバックウィンドウで週に 1 回再生されます（[ オプション ](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 週間未満の未ステッチデータは、次の週次再生まで再処理されません。
   - **毎週の頻度での隔週ルックバック**：データは、毎週 1 回、隔週ルックバックウィンドウで再生されます（[ オプション ](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、2 週間未満の未ステッチデータは、次の週別の再生まで再処理されません。
   - **毎週の頻度での毎月のルックバック**：データは、毎週、毎月のルックバックウィンドウで再生されます（[ オプション ](#options) を参照）。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 か月未満の未ステッチデータは、次の週次再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合、リクエストされた ID を削除する以外に、認証されていないイベントに対するその ID の関連付けを取り消す必要があります。

  >[!IMPORTANT]
  >
  >ステッチ解除プロセスは、プライバシーリクエストの一環として、2025 年の初めに変更されます。 現在のステッチ解除プロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 イベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を修正するために、2025 年以降、新しいステッチプロセスにより、プライバシーリクエストの対象となるイベントが永続 ID で更新されます。
  > 


ルックバックウィンドウを超えたデータは再生されません。未認証の訪問と認証された訪問を一緒に識別するには、訪問者は、所定のルックバックウィンドウ内で認証する必要があります。 デバイスが認識されると、その時点からライブステッチされます。

### 手順 1：ライブステッチ

ライブステッチは、コレクション時に既知のデバイスとチャネルに各イベントをステッチしようとします。

+++ 詳細

次の例について考えてみます。Bob がイベントデータセットの一部として様々なイベントを記録する場合を考えてみましょう。

*データが収集された日の状態：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID （ログイン ID） | ステッチ ID （ライブステッチ後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 デバイス** | | **4 人**:<br/>`246`、`Bob`、`3579`、`81911` |

新しいデバイスでの未認証イベントと認証イベントは、両方とも別のユーザーとして（一時的に）カウントされます。認識されたデバイス上の未認証のイベントは、ライブステッチされます。

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1、8、9、10 を除くすべてのイベントがライブステッチされます（すべてのイベントが `Bob` 識別子を使用します）。 ライブステッチは、イベント 4、6、12 のステッチ ID を「解決」します。

遅延データ（タイムスタンプが 24 時間以上経過したデータ）は、「ベストエフォート」ベースで処理され、最高の品質を得るために現在のデータのステッチが優先されます。

+++

### 手順 2：再生のステッチ

一定の間隔（選択されたルックバックウィンドウに応じて週に 1 回または 1 日に 1 回）で、再生のステッチは、認識されたデバイスに基づいて履歴データを再計算します。 デバイスが未認証の状態で最初にデータを送信してからログインした場合、再生のステッチにより、未認証のイベントが適切なユーザーに結び付けられます。

+++ 詳細

次の表は、上記と同じデータを示していますが、データの再生に基づいて異なる数字が表示されています。

*再生後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID （ログイン ID） | ステッチ ID （ライブステッチ後） | ステッチ ID （再生後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![ 上矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![ 上矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 デバイス** | | **4 人**:<br/>`246`、`Bob`、`3579`、`81911` | **2 人**:<br/>`Bob`、`3579` |

{style="table-layout:auto"}

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1 と 10 が再生の結果としてステッチされ、イベント 8 と 9 のみがステッチされていない状態になります。 人物指標（累積）を 2 に減らします。

+++

### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、ステッチされた ID は、プライバシーリクエストのユーザー主体に対するすべてのレコードで削除されます。

+++ 詳細

次の表は上記と同じデータですが、Bob に対するプライバシーリクエストが処理後のデータに与える影響を示しています。 Bob が認証されたローは、他のローの一時的な ID として Bob を削除すると同時に、削除されます（2、3、5、7、11）。

*Bob に対するプライバシーリクエスト後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID （ログイン ID） | ステッチ ID （ライブステッチ後） | ステッチ ID （再生後） | 一時 ID （ログイン ID） | ステッチ ID （プライバシーリクエスト後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | ボブ ![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![ 上矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | ボブ ![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | ボブ ![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob`![ 右矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![ 下矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![ 上矢印 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 デバイス** | | **4 人**:<br/>246、`Bob`、`3579`、`81911` | **2 人**:<br/>Bob, `3579` |  | **3 人**:<br/>`246`、`3579`、`81911` |

+++

## 前提条件

次の前提条件は、特にフィールドベースのステッチに適用されます。

- ステッチを適用するAdobe Experience Platformのイベントデータセットには、訪問者の識別に役立つ次の 2 つの列が必要です。

   - **永続 ID**：各行で使用できる識別子。 例えば、Adobe Analytics AppMeasurement ライブラリで生成された訪問者 ID や、Adobe Experience Platform ID サービスで生成された ECID などです。
   - **一時的な ID**：一部の行でのみ使用できる識別子。 例えば、訪問者の認証後にハッシュ化されたユーザー名やメールアドレスなどがあります。実質的に任意の識別子を使用できます。 ステッチでは、このフィールドを実際のユーザー ID 情報を保持すると見なされます。 最適なステッチ結果を得るには、データセットのイベント内で、永続 ID ごとに少なくとも 1 回、一時的な ID を送信する必要があります。 Customer Journey Analytics接続内にこのデータセットを含める予定がある場合は、他のデータセットも同様の共通の ID を持っていることが推奨されます。

<!--
- Both columns (persistent ID and transient ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 制限事項

次の制限は、特にフィールドベースのステッチに適用されます。

- 現在のキー変更機能は、1 つの手順（永続 ID から一時的な ID への変更）に制限されます。複数手順でのキーの変更（例えば、永続 ID を一時的な ID に、その後別の一時的な IDに変更）はサポートされません。
- デバイスが複数のユーザーによって共有されており、ユーザー間のトランジションの合計が 50,000 を超えている場合、Customer Journey Analyticsはそのデバイスに対するデータのステッチを停止します。
- 組織で使用されているカスタム ID マップはサポートされていません。
- ステッチでは大文字と小文字が区別されます。 Analytics ソースコネクタを通じて生成されたデータセットの場合、Adobeでは、一時的な ID フィールドに適用される VISTA ルールまたは処理ルールのレビューを行うことをお勧めします。 これにより、これらのルールによって同じ ID の新しいフォームが導入されることがなくなります。 例えば、VISTA ルールまたは処理ルールにより、イベントの一部のみで一時的な ID フィールドが小文字になっていないか確認する必要があります。
- ステッチでフィールドの結合や連結は行われません。
- 一時的な ID フィールドには、1 種類の ID （1 つの名前空間からの ID）を含める必要があります。 例えば、一時的な ID フィールドにログイン ID と電子メール ID の組み合わせを含めることはできません。
- 同じ永続 ID の同じタイムスタンプで複数のイベントが発生しても、一時 ID フィールドに異なる値がある場合、ステッチはアルファベット順に基づいて ID を選択します。 したがって、永続 ID A に同じタイムスタンプの 2 つのイベントがあり、1 つのイベントが Bob を指定し、もう 1 つが Ann を指定している場合、ステッチは Ann を選択します。
- 一時的な ID にプレースホルダー値（例：`Undefined`）が含まれるシナリオでは注意が必要です。 詳しくは、[FAQ](faq.md) を参照してください。
- persistentID と transientID の両方に同じ名前空間を使用することはできません。名前空間は相互に排他的である必要があります。
