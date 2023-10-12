---
title: Adobe Experience Platform Edge Network Server API を使用したデータの取得
description: Adobe Experience Platform Edge Network Server API と Edge Network を使用してCustomer Journey Analyticsにデータを取り込む方法について説明する
solution: Customer Journey Analytics
feature: Basics
exl-id: 6bfb7254-5bb7-45c6-86a2-0651a0d222fa
source-git-commit: 7ed28afa9d98a581e2d648dcfb438f960900f602
workflow-type: tm+mt
source-wordcount: '2353'
ht-degree: 60%

---

# Adobe Experience Platform Edge Network Server API を使用したデータの取得

このクイックスタートガイドでは、IoT デバイス、セットトップボックス、ゲームコンソール、デスクトップアプリケーションなどのデバイスから、Adobe Experience Platform Edge Network Server API と Edge Network を使用して、Adobe Experience Platformに直接トラッキングデータを取り込む方法について説明します。 そのデータをCustomer Journey Analyticsで使う。

これを実現するには、次の操作を行う必要があります。

- Adobe Experience Platform で&#x200B;**スキーマとデータセットを設定**&#x200B;し、収集するデータのモデル（スキーマ）と、実際にデータ（データセット）を収集する場所を定義します。

- **データストリームの設定**：収集したデータを Adobe Experience Platform で設定したデータセットにルーティングするように Adobe Experience Platform Edge Network を設定します。

- **Server API を使用** デスクトップ、ゲームコンソール、IoT デバイス、セットトップボックスで実行しているアプリケーションまたはゲームから直接データをデータストリームに送信する。

- **デプロイと検証**&#x200B;を行います。開発を繰り返し処理し、すべての検証が完了したら、実稼動環境で公開できる環境を構築します。

- Customer Journey Analytics で、**接続を設定**&#x200B;します。この接続には、（少なくとも）Adobe Experience Platform データセットを含める必要があります。

- Customer Journey Analytics で&#x200B;**データ表示を設定**&#x200B;し、Analysis Workspace で使用する指標とディメンションを定義します。

- Customer Journey Analytics で&#x200B;**プロジェクトを設定**&#x200B;して、レポートとビジュアライゼーションを作成します。

>[!NOTE]
>
>このクイックスタートガイドは、IoT デバイス、セットトップボックス、ゲームコンソール、デスクトップで実行されているアプリケーションまたはゲームから収集したデータをAdobe Experience Platformに取り込み、Customer Journey Analyticsで使用する方法を簡単に説明するガイドです。 参照する際には、追加情報を調べることを強くお勧めします。


## スキーマとデータセットの設定

データをAdobe Experience Platformに取り込むには、まず収集するデータを定義する必要があります。 ダウンストリームの機能で認識し、処理するには、Adobe Experience Platform に取り込まれるすべてのデータが、標準的な非正規化された構造に準拠する必要があります。エクスペリエンスデータモデル (XDM) は、スキーマの形式で構造を提供する標準フレームワークです。

スキーマを定義したら、1 つ以上のデータセットを使用して、データの収集を保存および管理します。データセットは、スキーマ（列）とフィールド（行）を含むデータ（通常はテーブル）の集まりのストレージと管理の構成体です。

Adobe Experience Platform に取り込まれるすべてのデータは、データセットとして保持する前に、事前定義済みのスキーマに準拠している必要があります。

### スキーマの設定

識別、スコア、進捗状況、その他の情報など、コンソールでゲームをプレイするプロファイルの最小限のデータを追跡する場合。
最初に、このデータをモデル化するスキーマを定義する必要があります。

スキーマを設定するには：

1. Adobe Experience Platform UI の左パネルの「[!UICONTROL データ管理]」で、「**[!UICONTROL スキーマ]**」を選択します。

1. 選択 **[!UICONTROL スキーマを作成]**..
1. スキーマ作成ウィザードのクラスの選択手順で、「 」を選択します。 **[!UICONTROL エクスペリエンスイベント]**.

   ![スキーマ](./assets/create-ee-schema-wizard-step-1.png)

   >[!INFO]
   >
   >    エクスペリエンスイベントスキーマは、 _動作_ プロファイルの名前（シーン名、押しボタンなど、買い物かごに追加するボタン）。 個々のプロファイルスキーマは、プロファイル&#x200B;_属性_（名前、メール、性別など）のモデル化に使用されます。

   「**[!UICONTROL 次へ]**」を選択します。


1. Adobe Analytics の [!UICONTROL 名前とレビュー手順] の [!UICONTROL スキーマを作成] ウィザード：

   1. を入力します。 **[!UICONTROL スキーマの表示名]** （スキーマ用）および（オプション）a **[!UICONTROL 説明]**.

      ![スキーマに名前を付ける](./assets/create-ee-schema-wizard-step-2.png)

   1. 「**[!UICONTROL 完了]**」を選択します。

1. サンプルスキーマの「構造」タブで、次の操作を実行します。

   1. 「[!UICONTROL フィールドグループ]」で「**[!UICONTROL + 追加]**」を選択します。

      ![フィールドグループを追加](./assets/add-field-group-button.png)

      フィールドグループは、スキーマを簡単に拡張できる、再利用可能なオブジェクトと属性のコレクションです。

   1. Adobe Analytics の [!UICONTROL フィールドグループを追加] ダイアログで、 **[!UICONTROL 目隠し光]** フィールドグループを選択します。 このフィールドグループは、コンソールで Blinding Light という架空のゲームをプレイするユーザーの進行状況を追跡するために作成されます。

      ![[ ブラインドライト ] フィールドグループ](assets/schema-fieldgroup-blindinglight.png)

      「プレビュー」ボタンを選択すると、このフィールドグループに属するフィールド（`scores > afterMatch` など）のプレビューを表示できます。

      ![ブラインドライトフィールドグループのプレビュー](assets/schema-fieldgroup-blindinglight-preview.png)

      「**[!UICONTROL 戻る]**」を選択してプレビューを閉じます。

   1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. 選択 **[!UICONTROL +]** スキーマ名の横に表示されます。

   ![スキーマ追加フィールドボタンの例](./assets/example-gamingschema-plus.png)

1. Adobe Analytics の [!UICONTROL フィールドのプロパティ] パネル、入力 `identification` として [!UICONTROL フィールド名], **[!UICONTROL 識別]** として [!UICONTROL 表示名]を選択します。 **[!UICONTROL オブジェクト]** として [!UICONTROL タイプ] を選択し、 **[!UICONTROL ExperienceEvent Core v2.1]** として [!UICONTROL フィールドグループ].

   ![ID オブジェクト](./assets/identification-field-gaming.png)

   識別オブジェクトは、スキーマに識別機能を追加します。 ゲームコンソールにログインする際に使用するExperience CloudID と電子メールアドレスを使用して、ゲーム中のプロファイルを識別したい場合。 個人の ID を追跡するために使用できるその他の属性は多数あります。

   「**[!UICONTROL 適用]**」を選択して、このオブジェクトをスキーマに追加します。

1. 先ほど追加した ID オブジェクトで「**[!UICONTROL ecid]**」フィールドをクリックし、右パネルの [!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]**、**[!UICONTROL プライマリ ID]** および **[!UICONTROL ECID]** を選択します。

   ![ECID を ID として指定](./assets/specify-identity-gaming.png)

   Experience Cloud ID を、Adobe Experience Platform Identity Service が同じ ECID を持つプロファイルの動作を組み合わせる（ステッチする）ために使用するプライマリ ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。ecid 属性にフィンガープリントアイコンが表示されます。

1. 先ほど追加した ID オブジェクトで「**[!UICONTROL メール]**」フィールドをクリックし、[!UICONTROL フィールドプロパティ]パネルの[!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]** と&#x200B;**[!UICONTROL メール]**&#x200B;を選択します。

   ![メールを ID として指定](./assets/specify-email-identity-gaming.png)

   メールアドレスを、Adobe Experience Platform Identity Service がプロファイルの動作を組み合わせる（ステッチする）ために使用するもう一つの ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。メール属性にフィンガープリントアイコンが表示されます。

   「**[!UICONTROL 保存]**」を選択します。

1. スキーマの名前を表示しているスキーマのルート要素を選択してから、**[!UICONTROL プロファイル]**&#x200B;スイッチをクリックします。

   プロファイルのスキーマを有効にするよう求められます。有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータをリアルタイム顧客プロファイルと結合します。

   詳しくは、[リアルタイム顧客プロファイルで使用するスキーマを有効にする](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#profile)を参照してください。

   >[!IMPORTANT]
   >
   >    プロファイルで有効にしたスキーマを保存すると、そのスキーマはプロファイルで無効にできなくなります。

   ![プロファイルでスキーマを有効にする](./assets/enable-for-profile.png)

1. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

ゲームから取り込むデータをモデル化する最小限のスキーマを作成しました。 このスキーマを使用することで、Experience Cloud ID とメールアドレスを使用してプロファイルを識別できます。プロファイルのスキーマを有効にすると、コンソールゲームでキャプチャされたデータがリアルタイム顧客プロファイルに追加されます。

行動データの横にある、コンソールからプロファイル属性データ（例えば、コンソールにサインインしたプロファイルの詳細）を取り込むこともできます。

プロファイルデータを取り込むには、次の操作を実行します。

- XDM Individual Profile クラスに基づいてスキーマを作成します。

- Profile Core v2 フィールドグループをスキーマに追加します。

- Profile Core v2 フィールドグループに基づいて ID オブジェクトを追加します。

- Experience CloudID をプライマリ識別子として定義し、電子メールを識別子として定義します。

- プロファイルでスキーマを有効にする

フィールドグループと個々のフィールドをスキーマに追加、またはスキーマから削除する方法について詳しくは、[UI でのスキーマの作成と編集](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=ja)を参照してください。

### データセットの設定

スキーマを使用して、データモデルを定義しました。次に、データセットを使用してデータを保存および管理するための構成を定義する必要があります。

データセットを設定するには：

1. Adobe Experience Platform UI の左パネルの「[!UICONTROL データ管理]」で、「**[!UICONTROL データセット]**」を選択します。

2. 「**[!UICONTROL データセットを作成]**」を選択します。

   ![データセットの作成](./assets/create-dataset.png)

3. 「**[!UICONTROL スキーマからデータセットを作成]**」をクリックします。

   ![スキーマからのデータセットの作成](./assets/create-dataset-from-schema.png)

4. 作成したスキーマを選択し、「**[!UICONTROL 次へ]**」を選択します。

5. データセットに名前を付け、（オプション）説明を入力します。

   ![名前データセット](./assets/name-your-datatest.png)

6. 「**[!UICONTROL 完了]**」を選択します。

7. 「**[!UICONTROL プロファイル]**」スイッチを選択します。

   プロファイルのデータセットを有効にするよう求められます。有効にすると、データセットは、取り込んだデータを使用してリアルタイム顧客プロファイルを強化します。

   >[!IMPORTANT]
   >
   >    プロファイルのデータセットを有効にできるのは、データセットが準拠するスキーマがプロファイルに対しても有効になっている場合のみです。

   ![プロファイルでスキーマを有効にする](./assets/aepwebsdk-dataset-profile.png)

データセットの表示、プレビュー、作成、削除の方法について詳しくは、[データセット UI ガイド](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja)を参照してください。リアルタイム顧客プロファイルのデータセットを有効にする方法について説明します。

## データストリームの設定

datastream は、Adobe Experience Platform Web および Mobile SDK とAdobe Experience Platform Edge Network Server API を実装する際のサーバー側の設定を表します。 Adobe Experience Platform SDK および Edge Network Server API を使用してデータを収集する場合、データはAdobe Experience Platform Edge ネットワークに送信されます。 データを転送するサービスを決定するデータストリームです。

設定で、ゲームから収集したデータをAdobe Experience Platformのデータセットに送信する必要があります。

データストリームを設定するには：

1. Adobe Experience Platform UI の左パネルで、「[!UICONTROL データ収集]」から「**[!UICONTROL データストリーム]**」を選択します。

2. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。

3. データストリームに名前を付けて説明します。[!UICONTROL イベントスキーマ]リストからスキーマを選択します。

   ![新規データストリーム](./assets/new-datastream.png)

4. 「**[!UICONTROL 保存]**」を選択します。

5. 「**[!UICONTROL サービスを追加]**」を選択します。

6. [!UICONTROL サービスを追加画面]で、次の操作を行います。

   1. [!UICONTROL サービス]リストから&#x200B;**[!UICONTROL Adobe Experience Platform]** を選択します。

   2. 「**[!UICONTROL 有効]**」が選択されていることを確認します。

   3. [!UICONTROL イベントデータセット]リストからお使いのデータセットを選択します。

      ![Datastream AEP サービス](./assets/datastream-aep-service.png)

   4. その他の設定はそのままにし、「**[!UICONTROL 保存]**」を選択してデータストリームを保存します。

これで、データストリームは、ゲームから収集したデータをAdobe Experience Platformのデータセットに転送するように設定されました。

データストリームの設定方法と機密データの処理方法について詳しくは、[データストリームの概要](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=ja)を参照してください。

## Edge Network Server API の使用

ゲームの開発時に、必要に応じて、Adobe Experience Platform Edge Network Server API に関連する呼び出しを追加できます。

例えば、プレーヤーのスコアを更新するには、次のように使用します。

```
curl -X POST "https://server.adobedc.net/ee/v2/interact?dataStreamId={DATASTREAM_ID}"
-H "Authorization: Bearer {TOKEN}"
-H "x-gw-ims-org-id: {ORG_ID}"
-H "x-api-key: {API_KEY}"
-H "Content-Type: application/json"
-d '{
   "event": {
      "xdm": {
         "identityMap": {
            "Email_LC_SHA256": [
               {
                  "id": "0c7e6a405862e402eb76a70f8a26fc732d07c32931e9fae9ab1582911d2e8a3b",
                  "primary": true
               }
            ]
         },
         "eventType": "game.scoreUpdate",
         "{sandbox}": {
            "scores": {
               "afterMatch": 132391",
            }
         },
         "timestamp": "2021-08-09T14:09:20.859Z"
      }
   }
}'
```

この例では、POSTリクエストは、 `{DATASTREAM_ID}` は、前に設定した例のデータストリームの識別子を指します。 `{sandbox}` は、カスタムの [ ブラインドライト ] フィールドグループへのパスを識別する、サンドボックスの一意の名前です。

詳しくは、 [インタラクティブデータ収集](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en) および [非インタラクティブデータ収集](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=en) Edge Network Server API の使用方法に関する詳細

## 接続の設定

Adobe Experience Platform データを Customer Journey Analytics で使用するには、接続（スキーマ、データセット、ワークフローの設定によって生成されたデータを含む）を作成します。

接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。これらのデータセットに関するレポートを作成するには、まずAdobe Experience Platformと Workspace のデータセット間で接続を確立する必要があります。

接続を作成するには：

1. Customer Journey Analytics UI で、「**[!UICONTROL 接続]**」をクリックします。

2. 「**[!UICONTROL 新しい接続を作成]**」を選択します。

3. [!UICONTROL 名称未設定の接続]画面で、次の手順を実行します。

   「[!UICONTROL 接続設定]」で接続に名前を付けて説明します。

   [!UICONTROL データ設定]の[!UICONTROL サンドボックス]リストから適切なサンドボックスを選択し、[!UICONTROL 毎日のイベントの平均数]リストから日次イベントの数を選択します。

   ![接続設定](./assets/cja-connections-1.png)

   「**[!UICONTROL データセットを追加]**」を選択します。

   「[!UICONTROL データセットを追加]」の「[!UICONTROL データセットを選択]」手順で、次の操作を行います。

   - 以前に作成したデータセットや、接続に含める他の関連するデータセットを選択します。

   - 「**[!UICONTROL 次へ]**」を選択します。

   「[!UICONTROL データセットを追加]」の「[!UICONTROL データセット設定]」手順で、次の操作を行います。

   - 各データセットに対して、次の手順を行います。

      - Adobe Experience Platform のデータセットスキーマで定義されている使用可能な ID から[!UICONTROL ユーザー ID] を選択します。

      - [!UICONTROL データソースタイプ]リストから正しいデータソースを選択します。「**[!UICONTROL その他]**」を指定している場合は、データソースの説明を追加します。

      - 必要に応じて&#x200B;**[!UICONTROL すべての新しいデータを読み込み]**&#x200B;および&#x200B;**[!UICONTROL データセットの既存データのバックフィル]**&#x200B;を選択します。

   - 「**[!UICONTROL データセットを追加]**」を選択します。

   「**[!UICONTROL 保存]**」を選択します。

接続を作成および管理する方法、およびデータセットを選択して組み合わせる方法について詳しくは、[接続の概要](../connections/overview.md)を参照してください。

## データ表示の設定

データ表示は、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。Analysis Workspace で使用可能なすべてのディメンションと指標、およびこれらのディメンションと指標からデータを取得する列を指定します。データ表示は、Analysis Workspace でレポートの準備を行う際に定義します。

データ表示を作成するには：

1. Customer Journey Analytics UI の上部ナビゲーションで、「**[!UICONTROL データ表示]**」をクリックします。

2. 「**[!UICONTROL 新しいデータ表示を作成]**」を選択します。

3. [!UICONTROL 設定]手順で、次の操作を行います。

   [!UICONTROL 接続]リストで接続を選択します。

   接続に名前を付け、（オプションで）説明します。

   ![データ表示の設定](./assets/cja-dataview-1.png)

   「**[!UICONTROL 保存して続行]**」を選択します。

4. [!UICONTROL コンポーネント]手順で、次の操作を行います。

   [!UICONTROL 指標]または[!UICONTROL ディメンション]コンポーネントボックスに含めるスキーマフィールドや標準コンポーネントを追加します。

   「**[!UICONTROL 保存して続行]**」を選択します。

5. [!UICONTROL 設定]手順で、次の操作を行います。

   ![データ表示設定](./assets/cja-dataview-3.png)

   設定をそのままにし、「**[!UICONTROL 保存して終了]**」を選択します。

データ表示の作成および編集方法、データ表示で使用できるコンポーネント、フィルターおよびセッションの設定の使用方法について詳しくは、[データ表示の概要](../data-views/data-views.md)を参照してください。


## プロジェクトの設定

Analysis Workspace は、データに基づき、分析をすばやく構築してインサイトを共有できる、柔軟なブラウザーツールです。ワークスペースプロジェクトでは、データコンポーネント、テーブル、およびビジュアライゼーションを組み合わせて、分析を作成し、組織内の任意のユーザーと共有できます。

プロジェクトを作成するには：

1. Customer Journey Analytics UI で、「**[!UICONTROL プロジェクト]**」をクリックします。

2. 左側のナビゲーションの「**[!UICONTROL プロジェクト]**」を選択します。

3. 「**[!UICONTROL プロジェクトを作成]**」を選択します。

   ![ワークスペースプロジェクト](./assets/cja-projects-1.png)

   「**[!UICONTROL 空のプロジェクト]**」を選択します。

   ![ワークスペース - 空のプロジェクト](./assets/cja-projects-2.png)

4. リストからデータ表示を選択します。

   ![ワークスペースでデータ表示を選択](./assets/cja-projects-3.png)します。

5. 最初のレポートを作成するには、ディメンションと指標のドラッグ&amp;ドロップを [!UICONTROL フリーフォームテーブル] （内） [!UICONTROL パネル].

コンポーネント、ビジュアライゼーション、パネルを使用してプロジェクトを作成し、分析を構築する方法について詳しくは、[Analysis Workspace の概要](../analysis-workspace/home.md)を参照してください。

>[!SUCCESS]
>
>すべての手順が完了しました。まず、収集するデータ（スキーマ）と、そのデータ（データセット）をAdobe Experience Platform内のどこに保存するかを定義します。Edge ネットワーク上にデータストリームを設定し、データをそのデータセットに転送できるようにしました。 次に、Edge Network Server API を使用して、そのデータをデータストリームに送信しました。 ゲームデータや他のデータを使用するCustomer Journey Analyticsで接続を定義しました。 データビュー定義を使用すると、使用するディメンションと指標を指定でき、最後に、ゲームデータを視覚化および分析する最初のプロジェクトを作成しました。
