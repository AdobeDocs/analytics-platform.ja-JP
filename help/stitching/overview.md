---
title: ステッチの概要
description: ステッチの概要。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 195659d6665e5a3c0e4bf5a4f02ce2af5b95749c
workflow-type: tm+mt
source-wordcount: '3793'
ht-degree: 12%

---

# ステッチ

>[!NOTE]
>
>以下が必要です。 **を選択** パッケージ以上（フィールドベースのステッチの場合）または **Prime** この節で説明している機能を使用するには、パッケージ以降（グラフベースのステッチの場合）。 使用している Customer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。


ID のステッチ（または単にステッチ）は、クロスチャネル分析に対するイベントデータセットの適合性を高める強力な機能です。 クロスチャネル分析は、Customer Journey Analyticsで処理できる主なユースケースで、共通の ID （ユーザー ID）に基づいて、異なるチャネルの複数のデータセットに対してレポートをシームレスに組み合わせて実行できます。

データセットを同様のユーザー ID と組み合わせると、アトリビューションはデバイスやチャネルにも伝わります。例えば、ユーザーがデスクトップコンピューターの広告を通じて最初にサイトを訪問したとします。また、注文で問題が発生し、その解決方法を求めてカスタマーサービスチームに電話をしたとします。クロスチャネル分析を使用すると、コールセンターイベントを、訪問者が最初にクリックした広告に関連付けることができます。

残念ながら、Customer Journey Analyticsの連携に含まれるすべてのイベントベースのデータセットが、標準ではこのアトリビューションをサポートするデータが十分に入力されているわけではありません。 特に、web ベースまたはモバイルベースのエクスペリエンスデータセットには、多くの場合、すべてのイベントで使用できる実際のユーザー ID 情報がありません。

ステッチを使用すると、1 つのデータセットの行内の ID を再入力できるので、各イベントでユーザー ID （ステッチされた ID）が使用可能になります。 ステッチでは、認証済みセッションと未認証セッションの両方からのユーザーデータを調べて、ステッチされた ID として使用できる共通の一時的な ID （ユーザー ID）値を決定します。 このキー更新により、異なるレコードを単一のステッチ ID に解決し、デバイスや cookie レベルではなく、ユーザーレベルで分析できます。

Customer Journey Analyticsでは、フィールドベースのステッチとグラフベースのステッチの 2 種類のステッチをサポートしています。

## 前提条件

>[!IMPORTANT]
>
>すべての前提条件を満たしていないと、クロスチャネル分析を適切に行うことができない可能性があります。

ステッチを使用する前に、組織で次のものが準備されていることを確認してください。

- ステッチには、認証済みユーザーデータと未認証ユーザーデータの結合が含まれます。 イベントデータセットに対してステッチを有効にする前に、必要なエンドユーザー権限の取得など、適用される法律および規制を遵守していることを確認してください。 詳しくは、[UI で ID フィールドを定義](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity)を参照してください。

- 目的のデータをAdobe Experience Platformに読み込みます。

   - Adobe Analyticsのデータについては、を参照してください。 [Customer Journey AnalyticsでのAdobe Analytics レポートスイートデータの利用](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - 他のタイプのデータについては、Adobe Experience Platform ドキュメントの[スキーマの作成](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)と[データの取り込み](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)を参照してください。

Customer Journey Analytics接続の定義の一環として、1 つ以上のステッチされたデータセットを、コールセンターデータなどの他のデータセットと組み合わせると、クロスチャネル分析のメリットが得られます。 この接続設定では、ステッチされた ID と同様に、他のデータセットに既にすべての行に人物 ID が含まれていることを前提としています。


## 制限事項

>[!IMPORTANT]
>
>- の使用はサポートされていません `identityMap` 永続 ID として設定します。 データセットに特定の識別子を定義する必要があります（例： `ECID`）を使用して設定します。
>
>- ソースイベントデータセットスキーマに加えた変更を、新しい関連付けられたデータセットスキーマにも適用します。適用しないと、関連付けられたデータセットが破損します。
>
>- ソースデータセットを削除すると、ステッチされたデータセットは、処理を停止し、システムによって削除されます。
>
>- データ使用ラベルは、ステッチされたデータセットスキーマに自動的には生成されません。 ソースデータセットスキーマにデータ使用ラベルが適用されている場合は、ステッチされたデータセットスキーマにこれらのデータ使用ラベルを手動で適用する必要があります。 参照： [Experience Platformでのデータ使用ラベルの管理](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) を参照してください。

ステッチは画期的で堅牢な機能ですが、使用方法に制限があります。

- イベントデータセットのみがサポートされます。参照データセットなどの他のデータセットはサポートされていません。
- ステッチによって、ステッチに使用されるフィールドが変換されることはありません。 ステッチでは、指定したフィールドの値が使用されます。これは、その値がデータレイク内の関連付けられていないデータセットに存在するためです。
- ステッチ処理では、大文字と小文字が区別されます。例えば、フィールドに「Bob」という単語が表示される場合や、「BOB」という単語が表示される場合は、これらの ID は 2 つの異なる人物として扱われます。

ステッチを次と混同しないでください。

- 2 つ以上のデータセットの結合。 ステッチは、1 つのデータセットにのみ適用されます。 データセットの結合は、Customer Journey Analytics接続を設定し、接続内の選択したデータセットで同じ人物 ID を選択した結果として発生します。

- 2 つのデータセットの結合。 Customer Journey Analyticsでは、結合は、Analysis Workspaceでの検索や分類によく使用されます。 ステッチには結合機能が使用されますが、プロセス自体には複数の結合が含まれます。


## フィールドベースのステッチ

イベントデータセットと、そのデータセットの永続 ID （cookie）および一時的な ID （ユーザー ID）を指定します。 フィールドベースのステッチでは、新しいステッチされたデータセットに新しいステッチ ID 列が作成され、その特定の永続 ID の一時的な ID を持つ行に基づいて、このステッチ ID 列が更新されます。 <br/>Customer Journey Analyticsをスタンドアロンソリューションとして使用する場合（Experience Platform ID サービスおよび関連する ID グラフへのアクセス権を持たない場合）、フィールドベースのステッチを使用できます。 または、使用可能な ID グラフを使用しない場合にも使用できます。

![フィールドベースのステッチ](/help/stitching/assets/fbs.png)

### フィールドベースのステッチの仕組み

ステッチでは、特定のデータセット内のデータに対して少なくとも 2 つのパスが作成されます。

- **ライブステッチ**：各ヒット（イベント）が発生すると、そのヒットをステッチしようとします。 データセットに「新規」である（認証されたことのない）デバイスからのヒットは、通常、このレベルでは結び付けられません。 既に認識済みのデバイスからのヒットは、直ちに結合されます。

- **ステッチを再生**：学習した一意の識別子（一時的な ID）に基づいてデータを「再生」します。 このステージでは、以前は不明だったデバイス（永続 ID）からのヒットが（一時的な ID に）結合されます。 アドビでは、次の 2 つの再生間隔を用意しています。
   - **日次**：データ再生は毎日、24 時間のルックバックウィンドウで行われます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、認証されていない訪問者は、サイトを訪問した日に認証を行う必要があります。
   - **毎週**：選択したルックバックウィンドウで週に 1 回データが再生されます（を参照） [オプション](#options)）に設定します。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 週間未満の未ステッチデータは、次の週次再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合、リクエストされた ID を削除する以外に、未認証のイベントに対するその ID の関連付けを取り消す必要があります。

ルックバックウィンドウを超えたデータは再生されません。未認証の訪問と認証された訪問を一緒に識別するには、訪問者は、所定のルックバックウィンドウ内で認証する必要があります。 デバイスが認識されると、その時点からライブステッチされます。

#### 手順 1：ライブステッチ

ライブステッチは、コレクション時に既知のデバイスとチャネルに各イベントをステッチしようとします。

+++ 詳細

次の例について考えてみます。Bob がイベントデータセットの一部として様々なイベントを記録する場合を考えてみましょう。

*収集日に表示されたデータ：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID （ログイン ID） | ステッチ ID （ライブステッチ後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 台のデバイス** | | **4 人**:<br/>`246`, `Bob`, `3579`, `81911` |

新しいデバイスでの未認証イベントと認証イベントは、両方とも別のユーザーとして（一時的に）カウントされます。認識されたデバイス上の未認証のイベントは、ライブステッチされます。

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1、8、9、10 を除くすべてのイベントがライブステッチされます（すべてのイベントで `Bob` 識別子）。 ライブステッチは、イベント 4、6、12 のステッチ ID を「解決」します。

遅延データ（タイムスタンプが 24 時間以上経過したデータ）は、「ベストエフォート」ベースで処理され、最高の品質を得るために現在のデータのステッチが優先されます。

+++

#### 手順 2：再生のステッチ

一定の間隔（選択されたルックバックウィンドウに応じて週に 1 回または 1 日に 1 回）で、再生のステッチは、認識されたデバイスに基づいて履歴データを再計算します。 デバイスが未認証の状態で最初にデータを送信してからログインした場合、再生のステッチにより、未認証のイベントが適切なユーザーに結び付けられます。

+++ 詳細

次の表は、上記と同じデータを示していますが、データの再生に基づいて異なる数字が表示されています。

*再生後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID （ログイン ID） | ステッチ ID （ライブステッチ後） | ステッチ ID （再生後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![上矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![上矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 台のデバイス** | | **4 人**:<br/>`246`, `Bob`, `3579`, `81911` | **2 人**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

アトリビューションが機能するのは、識別するカスタム変数がデバイスに関連付けられている場合です。 上記の例では、イベント 1 と 10 が再生の結果としてステッチされ、イベント 8 と 9 のみがステッチされていない状態になります。 人物指標（累積）を 2 に減らします。

+++

#### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、ステッチされた ID は、プライバシーリクエストのユーザー主体に対するすべてのレコードで削除されます。

+++ 詳細

次の表は上記と同じデータですが、Bob に対するプライバシーリクエストが処理後のデータに与える影響を示しています。 Bob が認証されたローは、他のローの一時的な ID として Bob を削除すると同時に、削除されます（2、3、5、7、11）。

*Bob に対するプライバシーリクエスト後の同じデータ：*

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID （ログイン ID） | ステッチ ID （ライブステッチ後） | ステッチ ID （再生後） | 一時 ID （ログイン ID） | ステッチ ID （プライバシーリクエスト後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | ボブ ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![上矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | ボブ ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | ボブ ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![右矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![下矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![上矢印](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 台のデバイス** | | **4 人**:<br/>246, `Bob`, `3579`, `81911` | **2 人**:<br/>ボブ `3579` |  | **3 人**:<br/>`246`, `3579`, `81911` |

+++

### 前提条件

次の前提条件は、特にフィールドベースのステッチに適用されます。

- ステッチを適用するAdobe Experience Platformのイベントデータセットには、訪問者の識別に役立つ次の 2 つの列が必要です。

   - A **永続 ID**：各行で使用できる識別子。 例えば、Adobe Analytics AppMeasurementライブラリで生成された訪問者 ID や、Adobe Experience Platform ID サービスで生成された ECID などです。
   - A **一時 ID**：一部の行でのみ使用できる識別子。 例えば、訪問者の認証後にハッシュ化されたユーザー名やメールアドレスなどがあります。実質的に任意の識別子を使用できます。 ステッチでは、このフィールドを実際のユーザー ID 情報を保持すると見なされます。 最適なステッチ結果を得るには、データセットのイベント内で、永続 ID ごとに少なくとも 1 回、一時的な ID を送信する必要があります。 このデータセットをCustomer Journey Analytics接続内に含める予定がある場合は、他のデータセットも同様の共通の ID を持っていることが推奨されます。

- 両方の列（永続 ID と一時 ID）は、ステッチするデータセットのスキーマで、ID 名前空間を持つ ID フィールドとして定義する必要があります。 Real-time Customer Data Platformで ID ステッチを使用する場合は、 [`identityMap` フィールドグループ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)を選択した場合でも、id 名前空間を持つ id フィールドを追加する必要があります。 Customer Journey Analyticsのステッチではをサポートしていないので、この ID フィールドの ID は必須です `identityMap` フィールドグループ。 スキーマに ID フィールドを追加すると、同時にを使用する場合 `identityMap` フィールドグループで、「追加 id」フィールドをプライマリ id として設定しないでください。 追加 ID フィールドをプライマリ ID として設定すると、に干渉します。 `identityMap` Real-time Customer Data Platformに使用されるフィールドグループ。

### 制限事項

次の制限は、特にフィールドベースのステッチに適用されます。

- 現在のキー変更機能は、1 つの手順（永続 ID から一時的な ID への変更）に制限されます。複数手順でのキーの変更（例えば、永続 ID を一時的な ID に、その後別の一時的な IDに変更）はサポートされません。
- デバイスが複数のユーザーによって共有されていて、ユーザー間のトランジションの合計が 50,000 を超えている場合、Customer Journey Analyticsはそのデバイスに対するデータのステッチを停止します。
- 組織で使用されているカスタム ID マップはサポートされていません。
- ステッチでは大文字と小文字が区別されます。 Analytics ソースコネクタを通じて生成されたデータセットの場合、Adobeでは、一時的な ID フィールドに適用される VISTA ルールまたは処理ルールを確認することをお勧めします。 これにより、これらのルールによって同じ ID の新しいフォームが導入されることがなくなります。 例えば、VISTA ルールまたは処理ルールにより、イベントの一部のみで一時的な ID フィールドが小文字になっていないか確認する必要があります。
- ステッチでフィールドの結合や連結は行われません。
- 一時的な ID フィールドには、1 種類の ID （1 つの名前空間からの ID）を含める必要があります。 例えば、一時的な ID フィールドにログイン ID と電子メール ID の組み合わせを含めることはできません。
- 同じ永続 ID の同じタイムスタンプで複数のイベントが発生しても、一時 ID フィールドに異なる値がある場合、ステッチはアルファベット順に基づいて ID を選択します。 したがって、永続 ID A に同じタイムスタンプの 2 つのイベントがあり、1 つのイベントが Bob を指定し、もう 1 つが Ann を指定している場合、ステッチは Ann を選択します。
- 一時的な ID にプレースホルダー値が含まれるシナリオには注意が必要です（例：） `Undefined`. を参照してください。 [FAQ](faq.md) を参照してください。


## グラフベースのステッチ

イベントデータセット、およびそのデータセットの一時的な ID （ユーザー ID）の永続 ID （cookie）と名前空間を指定します。 グラフベースのステッチでは、新しいステッチされたデータセットのステッチ ID に新しい列が作成されます。 次に、永続 ID を使用して、指定された名前空間を使用してExperience PlatformID サービスから ID グラフをクエリし、ステッチされた ID を更新します。

![グラフベースのステッチ](/help/stitching/assets/gbs.png)

### グラフベースのステッチの仕組み

ステッチでは、特定のデータセット内のデータに対して少なくとも 2 つのパスが作成されます。

- **ライブステッチ**：は、永続 ID を使用して、ID グラフにクエリを実行し、選択した名前空間の一時的な ID を検索し、ヒット（イベント）ごとにステッチを試みます。 ルックアップから一時的な ID を使用できる場合、この一時的な ID は直ちにステッチされます。

- **ステッチを再生**:ID グラフ内の更新された ID に基づいてデータを「再生」します。 このステージでは、ID グラフが名前空間の ID を解決したので、以前は不明だったデバイス（永続的な ID）からのヒットがステッチされます。 アドビでは、次の 2 つの再生間隔を用意しています。
   - **日次**：データ再生は毎日、24 時間のルックバックウィンドウで行われます。 このオプションには、再生がより頻繁に行われるという利点があります。ただし、認証されていない訪問者は、サイトを訪問した日に認証を行う必要があります。
   - **毎週**：ルックバックウィンドウで週に 1 回データを再生（を参照） [オプション](#options)）に設定します。 このオプションには、認証されていないセッションを後から認証できるという利点があります。ただし、1 週間未満の未ステッチデータは、次の週次再生まで再処理されません。

- **プライバシー**：プライバシー関連のリクエストを受信した場合、ソースデータセットからリクエストされた ID を削除する以外に、認証されていないイベントに対するその ID のステッチを取り消す必要があります。 また、その特定の ID に対してグラフベースのステッチが今後行われないようにするために、ID を ID グラフから削除する必要があります。

ルックバックウィンドウを超えたデータは再生されません。未認証の訪問と認証された訪問を一緒に識別するには、訪問者は、所定のルックバックウィンドウ内で認証する必要があります。 デバイスが認識されると、その時点からライブステッチされます。

永続 ID について、次の 2 つの ID グラフについて考えてみます `246` および `3579`、これらの ID グラフが時間の経過とともにどのように更新されるか、およびこれらの更新がグラフベースのステッチのステップにどのように影響するか。

![ID グラフ 246](assets/identity-graph-246.svg)
![ID グラフ 3579](assets/identity-graph-3579.svg)

次を使用して、特定のプロファイルの ID グラフを経時的に表示できます [ID グラフビューア](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). 関連トピック [ID サービスリンクロジック](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) id のリンク時に使用されるロジックをより深く理解するために。

#### 手順 1：ライブステッチ

ライブステッチは、コレクション時に、各イベントを ID グラフからその時点での既知の情報にステッチしようと試みます。

+++ 詳細

| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![グラフ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID （ライブステッチ後） |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定義* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定義* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

ステッチされた ID がイベントごとにどのように解決されるかを確認できます。 時刻、永続 ID、指定された名前空間の ID グラフのルックアップに基づきます（同時）。
参照が複数のステッチ ID に解決される場合（イベント 7 の場合など）、ID グラフによって返される辞書的な最初の ID が選択されます（`a.b@yahoo.co.uk` この例では）。

+++

#### 手順 2：再生のステッチ

一定の間隔（選択したルックバックウィンドウに応じて）で、再生のステッチを行うと、その間隔の時点での ID グラフの最新バージョンに基づいて、履歴データが再計算されます。

+++ 詳細

2023-05-13 16:30 に再生のステッチが行われ、24 時間のルックバックウィンドウ設定では、サンプルの一部のイベントが再ステッチされます（次の記号が表示されます） ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)）に設定します。

| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![グラフ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID<br/>（ライブステッチの後） | ステッチ ID<br/>（再生後 24 時間） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


2023-05-13 16:30 に再生のステッチが行われ、7 日間のルックバックウィンドウ設定がある場合、サンプルからのすべてのイベントが再ステッチされます。


| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![グラフ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID<br/>（ライブステッチの後） | ステッチ ID<br/>（再生 7 日後） |
|---|---|---|---|---|---|
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定義* | `246` | `a.b@yahoo.co.uk` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![再生](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

#### 手順 3：プライバシーリクエスト

プライバシーリクエストを受け取ると、ステッチされた ID は、プライバシーリクエストのユーザー主体に対するすべてのレコードで削除されます。

+++ 詳細

次の表は上記と同じデータですが、サンプルイベントに対するプライバシーリクエスト（例：2023-05-13 18:00）の効果を示しています。

| | 時間 | 永続 ID<br/>`ECID` | 名前空間<br/>`Email` ![グラフ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ステッチ ID （プライバシーリクエスト後） |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246`  ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246`  ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246`  ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![リンク](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### 前提条件

次の前提条件は、特にグラフベースのステッチに適用されます。

- ステッチを適用するAdobe Experience Platformのイベントデータセットには、すべての行で訪問者を特定する 1 つの列がある必要があります。 **永続 ID**. 例えば、Adobe Analytics AppMeasurementライブラリで生成された訪問者 ID や、Adobe Experience Platform ID サービスで生成された ECID などです。
- Experience PlatformID サービスの ID グラフには、名前空間が必要です（例： `Email`、または `Phone`）を使用します **一時 ID**. 参照： [Experience PlatformID サービス](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) を参照してください。

>[!NOTE]
>
>あなたは、 **ではない** グラフベースのステッチにはReal-time Customer Data Platform ライセンスが必要です。 この **Prime** パッケージ以降のCustomer Journey Analyticsには、必要なExperience Platform ID サービス使用権限が含まれています。


### 制限事項

次の制限は、特にグラフベースのステッチに適用されます。

- 指定された名前空間を使用して一時的な ID をクエリする場合、タイムスタンプは考慮されません。 そのため、永続的 ID が、以前のタイムスタンプを持つレコードからの一時的な ID でステッチされる可能性があります。
- 共有デバイスはサポートされていません。 複数の ID が返される場合、名前空間を使用して ID グラフにクエリを実行すると、最初の辞書作成 ID が使用されます。
- ID グラフへの ID のバックフィルには、3 か月というハードリミットがあります。 Real-time Customer Data PlatformのようなExperience Platformアプリケーションを使用していない場合は、ID グラフへの入力にバックフィル ID を使用します。
- この [ID サービスガードレール](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) 適用。 例えば、次を参照してください [静的制限](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - グラフ内の ID の最大数：50。
   - 単一のバッチ取得での ID へのリンクの最大数：50。
   - グラフ取り込み用の XDM レコードの ID の最大数：20。
   - グラフ取り込み用の XDM レコードの最小 ID 数：2.


## ステッチを使用

組織がすべてを満たしたら [前提条件](#prerequisites) 共通のことを理解している [制限事項](#limitations) とステッチ方法固有（[フィールドベース](#limitations-1) および [グラフベース](#limitations-2)）の制限により、次の手順に従ってCustomer Journey Analyticsでステッチを使用し始めることができます。

### オプション

ステッチのオプションを選択します。 Customer Journey Analyticsパッケージは、初期バックフィル期間、ルックバックウィンドウ、再生頻度、ステッチ可能なデータセットの最大数に関して使用可能なオプションを決定します。 を参照してください。 [Customer Journey Analytics商品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html) を参照してください。

| | Customer Journey Analytics<br/>を選択 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>究極の |
|---|---|---|---|
| 1 回限りのステッチバックフィル期間 | 13 ヶ月 | 13 ヶ月 | 25 ヶ月 |
| ルックバックウィンドウと再生頻度 | <li>1 日、毎日</li><li>最大 7 日間、毎週</li> | <li>1 日、毎日</li><li>最大 14 日間、毎週</li> | <li>1 日、毎日</li><li>最大 30 日間、毎週</li> |
| ステッチできるデータセットの最大数 | 5 | 10 | 50 |

### サポートをリクエスト

1. 次の情報をアドビカスタマーサポートに連絡してください。

   - ステッチを有効にするリクエスト。
   - キーを変更するデータセットのデータセット ID。
   - 目的のデータセットの永続 ID の列名（ID パスと名前空間） （すべての行に表示される識別子）。
   - フィールドベースのステッチの場合、目的のデータセットの一時的な ID の列名（ユーザー識別子。接続のコンテキストでデータセット間のリンクとしても機能します）。 グラフベースのステッチの場合、ID グラフのクエリに使用する ID 名前空間。
   - ルックバックウィンドウと再生頻度の環境設定。 については、Customer Journey Analyticsパッケージを参照してください [オプション](#options) 使用可能。
   - サンドボックス名


2. AdobeカスタマーサポートはAdobeエンジニアリングと連携し、お客様のリクエストを受け取ったらステッチを有効にします。 有効にすると、新しいステッチ ID 列を含んだ新しいキー再設定済みデータセットがAdobe Experience Platformに表示されます。 Adobeカスタマーサポートは、新しいデータセットの ID を提供できます。

3. 最初にオンにした場合、Adobeはステッチされたデータのバックフィルを行います。 については、Customer Journey Analyticsパッケージを参照してください [オプション](#options) 使用可能。

4. クロスチャネル分析で新しいステッチされたデータセットを使用する場合は、新しいステッチされたデータセットをに追加する必要があります [接続](../connections/overview.md) Customer Journey Analyticsで。 次に、クロスチャネル分析に必要な他のデータセットを追加し、各データセットに対して正しいユーザー ID を選択します。

5. 接続に基づいて、[データ表示を作成](/help/data-views/create-dataview.md)します。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

データビューを設定したら、チャネルとデバイスをまたいでCustomer Journey Analyticsレポート分析を実行できます。

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->

