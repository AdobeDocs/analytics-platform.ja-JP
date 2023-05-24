---
title: Adobe Experience Platform Web SDK と Edge Network を介したデータの取り込み
description: Adobe Experience Platform Web SDK と Edge Network を使用して Customer Journey Analytics にデータを取り込む方法について説明する
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 0b595e9e-0dcf-4c70-ac6d-5a2322824328
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '3587'
ht-degree: 98%

---

# Adobe Experience Platform Web SDK と Edge Network を介したデータの取り込み

このクイックスタートガイドでは、Adobe Experience Platform Web SDK と Edge Network を使用して web サイトトラッキングデータを Adobe Experience Platform に直接取り込み、Customer Journey Analytics で使用する方法について説明します。

これには、次の手順を実行する必要があります。

- Adobe Experience Platform で&#x200B;**スキーマとデータセットを設定**&#x200B;し、収集するデータのモデル（スキーマ）と、実際にデータ（データセット）を収集する場所を定義します。

- **データストリームの設定**：収集したデータを Adobe Experience Platform で設定したデータセットにルーティングするように Adobe Experience Platform Edge Network を設定します。

- **タグを使用**：web サイト上のデータレイヤーのデータに対して、ルールやデータ要素を容易に設定できます。次に、データが Adobe Experience Platform Edge Network 上に設定されたデータストリームに送信されることを確認します。

- **デプロイと検証**&#x200B;を行います。タグの開発を繰り返し実行し、すべての検証が完了したら、実稼動環境で公開できる環境を構築します。

- Customer Journey Analytics で、**接続を設定**&#x200B;します。この接続には、（少なくとも）Adobe Experience Platform データセットを含める必要があります。

- Customer Journey Analytics で&#x200B;**データ表示を設定**&#x200B;し、Analysis Workspace で使用する指標とディメンションを定義します。

- Customer Journey Analytics で&#x200B;**プロジェクトを設定**&#x200B;して、レポートとビジュアライゼーションを作成します。

>[!NOTE]
>
>これは、サイトから収集されたデータを Adobe Experience Platform に取り込み、Customer Journey Analytics で使用する方法を簡単に説明するガイドです。参照する際には、追加情報を調べることを強くお勧めします。


## スキーマとデータセットの設定

データを Adobe Experience Platform に取り込むには、まず収集するデータを定義する必要があります。ダウンストリームの機能で認識し、処理するには、Adobe Experience Platform に取り込まれるすべてのデータが、標準的な非正規化された構造に準拠する必要があります。エクスペリエンスデータモデル（XDM）は、この構造をスキーマの形式で提供する標準フレームワークです。

スキーマを定義したら、1 つ以上のデータセットを使用して、データの収集を保存および管理します。データセットは、スキーマ（列）とフィールド（行）を含んだデータコレクション（通常はテーブル）のストレージおよび管理用の構成体です。

Adobe Experience Platform に取り込まれるすべてのデータは、データセットとして保持する前に、事前定義済みのスキーマに準拠している必要があります。

### スキーマの設定

Web サイトを訪問するプロファイルからの最小限のデータ（ページ名、ID など）を追跡することがあります。
この場合、まず、このデータをモデル化するスキーマを定義する必要があります。

スキーマを設定するには：

1. Adobe Experience Platform UI の左パネルの「[!UICONTROL データ管理]」で、「**[!UICONTROL スキーマ]**」を選択します。

2. 「**[!UICONTROL スキーマを作成]**」を選択します。オプションのリストから、「**[!UICONTROL XDM ExperienceEvent]**」を選択します。

   ![スキーマ](./assets/create-ee-schema.png)

   >[!INFO]
   >
   >    エクスペリエンスイベントスキーマは、プロファイルの&#x200B;_動作_（ページ表示や買い物かごに追加など）をモデル化するために使用できます。個々のプロファイルスキーマは、プロファイル&#x200B;_属性_（名前、メール、性別など）のモデル化に使用されます。


3. [!UICONTROL 名称未設定スキーマ]画面で、次の手順を実行します。

   1. スキーマの表示名と説明（オプション）を入力します。

      ![スキーマに名前を付ける](./assets/name-schema.png)

   2. 「[!UICONTROL フィールドグループ]」で「**[!UICONTROL + 追加]**」を選択します。

      ![フィールドグループを追加](./assets/add-field-group-button.png)

      フィールドグループは、スキーマを簡単に拡張できる、再利用可能なオブジェクトと属性のコレクションです。

   3. [!UICONTROL フィールドグループを追加]ダイアログで、リストから「**[!UICONTROL AEP Web SDK ExperienceEvent]**」フィールドグループを選択します。

      ![AEP Web SDK ExperienceEvent フィールドグループ](./assets/select-aepwebsdk-experienceevent.png)

      「プレビュー」ボタンを選択すると、このフィールドグループに属するフィールド（`web > webPageDetails > name` など）のプレビューを表示できます。

      ![AEP Web SDK ExperienceEvent フィールドグループのプレビュー](./assets/aepwebsdk-experiencevent-preview.png)

      「**[!UICONTROL 戻る]**」を選択してプレビューを閉じます。

   4. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

4. [!UICONTROL 構造]パネルで、スキーマ名の隣にある「**[!UICONTROL +]**」をクリックします。

   ![スキーマ追加フィールドボタンの例](./assets/example-schema-plus.png)

5. 「[!UICONTROL フィールドプロパティ]」パネルで、名前に `Identification`、[!UICONTROL 表示名]に&#x200B;**[!UICONTROL ID]** と入力し、[!UICONTROL タイプ]で&#x200B;**[!UICONTROL オブジェクト]**、[!UICONTROL フィールドグループ]で **[!UICONTROL ExperienceEvent Core v2.1]** を選択します。

   ![ID オブジェクト](./assets/identification-field.png)

   スキーマに ID 機能を追加します。この場合、Experience Cloud ID とメールアドレスを使用して、サイトを訪問しているプロファイルを識別します。個人の ID を追跡するために使用できるその他の多くの属性（例えば、顧客 ID、ロイヤリティ ID）があります。

   「**[!UICONTROL 適用]**」を選択して、このオブジェクトをスキーマに追加します。

6. 先ほど追加した ID オブジェクトで「**[!UICONTROL ecid]**」フィールドをクリックし、右パネルの [!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]**、**[!UICONTROL プライマリ ID]** および **[!UICONTROL ECID]** を選択します。

   ![ECID を ID として指定](./assets/specify-identity.png)

   Experience Cloud ID を、Adobe Experience Platform Identity Service が同じ ECID を持つプロファイルの動作を組み合わせる（ステッチする）ために使用するプライマリ ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。ecid 属性にフィンガープリントアイコンが表示されます。

7. 先ほど追加した ID オブジェクトで「**[!UICONTROL メール]**」フィールドをクリックし、[!UICONTROL フィールドプロパティ]パネルの[!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]** と&#x200B;**[!UICONTROL メール]**&#x200B;を選択します。

   ![メールを ID として指定](./assets/specify-email-identity.png)

   メールアドレスを、Adobe Experience Platform Identity Service がプロファイルの動作を組み合わせる（ステッチする）ために使用するもう一つの ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。メール属性にフィンガープリントアイコンが表示されます。

   「**[!UICONTROL 保存]**」を選択します。

8. スキーマの名前を表示しているスキーマのルート要素を選択してから、**[!UICONTROL プロファイル]**&#x200B;スイッチをクリックします。

   プロファイルのスキーマを有効にするよう求められます。有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータをリアルタイム顧客プロファイルと結合します。

   詳しくは、[リアルタイム顧客プロファイルで使用するスキーマを有効にする](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#profile)を参照してください。

   >[!IMPORTANT]
   >
   >    プロファイルで有効にしたスキーマを保存すると、そのスキーマはプロファイルで無効にできなくなります。

   ![プロファイルでスキーマを有効にする](./assets/enable-for-profile.png)

9. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

Web サイトから取得できるデータをモデル化する、最小限のスキーマを作成しました。このスキーマを使用することで、Experience Cloud ID とメールアドレスを使用してプロファイルを識別できます。プロファイルのスキーマを有効にすることで、web サイトから取り込んだデータをリアルタイム顧客プロファイルへと確実に追加できます。

行動データの横にある、サイトからプロファイル属性データ（ニュースレターを購読したプロファイルの詳細など）を取り込むこともできます。

このプロファイルデータを取得するには、次を実行します。

- XDM Individual Profile クラスに基づいてスキーマを作成します。

- Profile Core v2 フィールドグループをスキーマに追加します。

- Profile Core v2 フィールドグループに基づいて ID オブジェクトを追加します。

- ecid をプライマリ識別子、メールを識別子として定義します。

- プロファイルでスキーマを有効にする

フィールドグループと個々のフィールドをスキーマに追加、またはスキーマから削除する方法について詳しくは、[UI でのスキーマの作成と編集](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=ja)を参照してください。

### データセットの設定

スキーマを使用して、データモデルを定義しました。次に、そのデータを保存および管理するための構成を定義する必要があります。この処理は、データセットを通じて行います。

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

データストリームは、Adobe Experience Platform Web および Mobile SDK を実装する際のサーバーサイド設定を表します。Adobe Experience Platform SDK を使用してデータを収集する際、データはAdobe Experience Platform Edge Network に送信されます。データの転送先となるサービスを決定するデータストリームです。

設定では、web サイトから収集したデータを Adobe Experience Platform のデータセットに送信する必要があります。

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

これで、web サイトから収集したデータを Adobe Experience Platform でデータセットに転送するように、データストリームが設定されました。

データストリームの設定方法と機密データの処理方法について詳しくは、[データストリームの概要](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja)を参照してください。



## タグの使用

Adobe Experience Platform のタグ機能を使用して、実際にデータを収集するためのコードをサイトに実装します。このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。タグは、Adobe Experience Platform Web SDK 拡張機能を使用して、Adobe Experience Platform とのシームレスな統合を提供します。

### タグを作成する

1. Adobe Experience Platform UI の左パネルの「[!UICONTROL データ収集]」で、「**[!UICONTROL タグ]**」を選択します。

2. 「**[!UICONTROL 新しいプロパティ]**」を選択します。

   タグに名前を付け、「**[!UICONTROL Web]**」を選択し、ドメイン名を入力します。「**[!UICONTROL 保存]**」を選択して続行します。

   ![ プロパティの作成](./assets/create-property.png)

### タグの設定

タグを作成したら、適切な拡張機能を使用してタグを設定し、サイトを追跡して Adobe Experience Platform にデータを送信する方法に応じて、データ要素とルールを設定する必要があります。

[!UICONTROL タグのプロパティ]をクリックして新しく作成したタグを開きます。


#### **拡張機能**

タグに Adobe Platform Web SDK 拡張機能を追加し、（データストリームを介して）Adobe Experience Platform にデータを送信できるようにします。

Adobe Experience Platform Web SDK 拡張機能を作成して設定するには：

1. 左パネルで「**[!UICONTROL 拡張機能]**」を選択します。

2. 上部のバーで「**[!UICONTROL カタログ]**」をクリックします。

3. Adobe Experience Platform Web SDK 拡張機能を検索またはスクロールし、「**[!UICONTROL インストール]**」をクリックしてインストールします。

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. サンドボックスと、以前に作成した[!UICONTROL 実稼動環境]、（オプション）[!UICONTROL ステージング環境]および[!UICONTROL 開発環境]用のデータストリームを選択します。

   ![AEP Web SDK 拡張機能の設定](./assets/aepwebsk-extension-datastreams.png)

   「**[!UICONTROL 保存]**」を選択します。

詳しくは、[Adobe Experience Platform Web SDK 拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja)を参照してください。

また、Experience Cloud ID を簡単に使用できるように、Experience Cloud ID サービス拡張機能を設定する必要もあります。Experience CloudID サービスは、すべてのAdobe Experience Cloudソリューションをまたいで人を識別します。

Experience Cloud ID サービス拡張機能を作成および設定するには：

1. 左パネルで「**[!UICONTROL 拡張機能]**」を選択します。

2. 上部のバーで「**[!UICONTROL カタログ]**」をクリックします。

3. Experience Cloud ID サービス拡張機能を検索またはスクロールし、「**[!UICONTROL インストール]**」をクリックしてインストールします。

   <img src="./assets/ecid-extension.png" width="35%"/>

4. すべての設定はデフォルトのままにします。

5. 「**[!UICONTROL 保存]**」を選択します。

#### **データ要素**

データ要素は、データディクショナリ（またはデータマップ）の構築ブロックです。データ要素を使用して、マーケティングおよび広告テクノロジー全体でデータを収集、整理、配信します。タグでデータレイヤーから読み取り、Adobe Experience Platform にデータを配信するために使用できるデータ要素を設定します。

データ要素には様々なタイプがあります。最初に、サイトで閲覧しているページ名の人を取り込むデータ要素を設定します。

ページ名データ要素を定義するには：

1. 左パネルで「**[!UICONTROL データ要素]**」を選択します。

2. 「**[!UICONTROL データ要素を追加]**」を選択します。

3. [!UICONTROL データ要素を作成]ダイアログで、次の手順を実行します。

   - データ要素に名前を付けます（例：`Page Name`）。

   - [!UICONTROL 拡張機能]リストから、「**[!UICONTROL Core]**」を選択します。

   - [!UICONTROL データ要素タイプ]リストから、**[!UICONTROL ページ情報]**&#x200B;を選択します。

   - [!UICONTROL 属性]リストから、「**[!UICONTROL タイトル]**」を選択します。

      ![ページ情報を使用した日付要素の作成](./assets/create-dataelement-1.png)

      または、データレイヤーの変数の値（`pageName` や [!UICONTROL JavaScript 変数] データ要素タイプなど）を使用して、データ要素を定義できました。

      ![JavaScript 変数を使用したデータ要素の作成](./assets/create-dataelement-2.png)

   - 「**[!UICONTROL 保存]**」を選択します。

次に、Experience Cloud ID（Adobe Experience Platform Web SDK によって自動的に提供され、Experience Cloud ID サービス拡張機能を通じて使用できる）を参照するデータ要素を設定します。

ECID データ要素を定義するには：

1. 左パネルで「**[!UICONTROL データ要素]**」を選択します。

2. 「**[!UICONTROL データ要素を追加]**」を選択します。

3. [!UICONTROL データ要素を作成]ダイアログで、次の手順を実行します。

   - データ要素に名前を付けます（例：`ECID`）。

   - [!UICONTROL 拡張機能]リストから、**[!UICONTROL Experience Cloud ID サービス]**&#x200B;を選択します。

   - [!UICONTROL データ要素タイプ]リストから、**[!UICONTROL ECID]** を選択します。

      ![ECID データ要素](./assets/ecid-dataelement.png)

   - 「**[!UICONTROL 保存]**」を選択します。

最後に、特定のデータ要素を、前に定義したスキーマにマッピングします。XDM スキーマを表す別のデータ要素を定義します。

XDM オブジェクトデータ要素を定義するには：

1. 左パネルで「**[!UICONTROL データ要素]**」を選択します。

2. 「**[!UICONTROL データ要素を追加]**」を選択します。

3. [!UICONTROL データ要素を作成]ダイアログで、次の手順を実行します。

   - データ要素に名前を付けます（例：`XDM - Page View`）。

   - [!UICONTROL 拡張機能]リストから&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]** を選択します。

   - [!UICONTROL データ要素タイプ]リストから、**[!UICONTROL XDM オブジェクト]**&#x200B;を選択します。

   - [!UICONTROL サンドボックス]リストでお使いのサンドボックスを選択します。

   - [!UICONTROL スキーマ]リストからお使いのスキーマを選択します。

   - スキーマ内で定義した `identification > core > ecid` 属性を、ECID データ要素にマッピングします。円柱アイコンを選択すると、データ要素のリストから ECID データ要素を簡単に選択できます。

      ![ECID データ要素を選択](./assets/pick-ecid-dataelement.png)

      ![ECID データ要素をマッピング](./assets/map-ecid.png)


   - スキーマ内で定義した `web > webPageDetails > name` 属性を、ページ名データ要素にマッピングします。

      ![ページ名データ要素をマップ](./assets/map-pagename.png)

   - 「**[!UICONTROL 保存]**」を選択します。


#### **ルール**

Adobe Experience Platform のタグは、ルールベースのシステムに従います。ユーザーの操作と関する各種データを参照します。ルールで設定された条件が満たされると、ルールは、特定した拡張機能、スクリプトまたはクライアント側コードをトリガーします。ルールを使用し、Adobe Experience Platform Web SDK 拡張機能を使用して、XDM オブジェクトなどのデータを Adobe Experience Platform に送信できます。

ルールを定義するには：

1. 左パネルで「**[!UICONTROL ルール]**」を選択します。

2. 「**[!UICONTROL 新規ルールを作成]**」を選択します。

3. [!UICONTROL ルールを作成]ダイアログで、次の手順を実行します。

   - ルールに名前を付けます（例：`Page View`）。

   - 「[!UICONTROL イベント]」の下の「**[!UICONTROL + 追加]**」を選択します。

   - [!UICONTROL イベント設定]ダイアログで、次の手順を実行します。

      - [!UICONTROL 拡張機能]リストから、「**[!UICONTROL Core]**」を選択します。

      - [!UICONTROL イベントタイプ]リストから「**[!UICONTROL 読み込んだウィンドウ]**」を選択します。

         ![ルール - イベント設定](./assets/event-windowloaded-pageview.png)

      - 「**[!UICONTROL 変更を保持]**」を選択します。
   - 「[!UICONTROL アクション]」の下の「**[!UICONTROL + 追加]**」を選択します。

   - [!UICONTROL アクション設定]ダイアログで、次の手順を実行します。

      - [!UICONTROL 拡張機能]リストから&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]** を選択します。

      - [!UICONTROL アクションタイプ]リストから「**[!UICONTROL イベントを送信]**」を選択します。

      - [!UICONTROL タイプ]リストから、**[!UICONTROL web.webpagedetails.pageViews]** を選択します。

      - [!UICONTROL XDM データ]の横にある円柱アイコンを選択し、データ要素のリストから「**[!UICONTROL XDM - ページビュー]**」を選択します。

         ![ルール - アクションの設定](./assets/action-pageview-xdm.png)

      - 「**[!UICONTROL 変更を保持]**」を選択します。
   - ルールは次のようになります。

      ![ルールを作成](assets/rule-pageview.png)

   - 「**[!UICONTROL 保存]**」を選択します。





これは、他のデータ要素の値を含む XDM データを Adobe Experience Platform に送信するルールを定義する例に過ぎません。

タグ内で様々な方法でルールを使用して、（データ要素を使用して）変数を操作できます。

詳しくは、[ルール](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=ja)を参照してください。

### タグを作成して公開する

データ要素とルールを定義したら、タグを作成して公開する必要があります。ライブラリビルドを作成する場合は、そのビルドを環境に割り当てる必要があります。ビルドの拡張機能、ルール、およびデータ要素がコンパイルされ、割り当てられた環境に配置されます。各環境は、割り当てられたビルドをサイトに統合できる、一意の埋め込みコードを提供します。

タグを構築して公開するには、次の手順に従います。

1. 左パネルから「**[!UICONTROL 公開フロー]**」をクリックします。

2. **[!UICONTROL 作業ライブラリを選択]**／**[!UICONTROL ライブラリを追加…]**&#x200B;を選択します。

3. [!UICONTROL ライブラリを作成]ダイアログで、次の手順を実行します。

   - ライブラリに名前を付けます。

   - [!UICONTROL 環境]リストから「**[!UICONTROL 開発（開発）]**」を選択します。

   - 「**[!UICONTROL + 変更されたリソースをすべて追加]**」を選択します。

      ![公開 - ライブラリを作成](./assets/create-library-aep.png)

   - 「**[!UICONTROL 開発用に保存およびビルド]**」を選択します。

   これにより、開発環境用のタグを保存して構築します。緑のドットは、開発環境でタグが正常に作成されたことを示します。

4. **[!UICONTROL ...]** を選択してライブラリを再構築するか、ライブラリをステージング環境または実稼動環境に移動することができます。

   ![公開 - ライブラリを作成](./assets/build-library.png)

Adobe Experience Platform タグは、Adobe Experience Platform Web SDK のデプロイに対応する必要がある、シンプルな公開ワークフローから複雑な公開ワークフローをサポートします。

詳しくは、[公開の概要](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja)を参照してください。


### タグコードの取得

最後に、追跡する web サイトにタグをインストールする必要があります。これは、web サイトのテンプレートのヘッダータグにコードを配置することを意味します。

タグを参照するコードを取得するには：

1. 左パネルで「**[!UICONTROL 環境]**」を選択します。

2. 環境のリストから、正しいインストール（ボックス）ボタンを選択します。

   [!UICONTROL Web インストール手順]ダイアログで、次のように読み込むスクリプトコードの横にある「コピー」ボタンを選択します。

   ```javascript
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>
   ```

   ![環境](./assets/environment.png)

3. 「**[!UICONTROL 閉じる]**」を選択します。

開発環境用のコードの代わりに、Adobe Experience Platform Web SDK をデプロイするプロセスの場所に基づいて、別の環境（ステージング、実稼動）を選択することもできます。

詳しくは、[環境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ja)を参照してください。

## デプロイと検証

次に、web サイトの開発バージョンで、`<head>` タグをデプロイできます。デプロイすると、web サイトは Adobe Experience Platform へのデータの収集を開始します。

実装を検証し、必要に応じて修正したら、タグの公開ワークフロー機能を使用して、ステージング環境と実稼動環境にデプロイします。

## 接続の設定

Adobe Experience Platform データを Customer Journey Analytics で使用するには、接続（スキーマ、データセット、ワークフローの設定によって生成されたデータを含む）を作成します。

接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。これらのデータセットに関するレポートを作成するには、まず Experience Platform とワークスペースのデータセット間で接続を確立する必要があります。

接続を作成するには：

1. Customer Journey Analytics UI で、「**[!UICONTROL 接続]**」をクリックします。

2. 「**[!UICONTROL 新しい接続を作成]**」を選択します。

3. [!UICONTROL 名称未設定の接続]画面で、次の手順を実行します。

   「[!UICONTROL 接続設定]」で接続に名前を付けて説明します。

   [!UICONTROL データ設定]の[!UICONTROL サンドボックス]リストから適切なサンドボックスを選択し、[!UICONTROL 毎日のイベントの平均数]リストから日次イベントの数を選択します。

   ![接続設定](./assets/cja-connections-1.png)

   「**[!UICONTROL データセットを追加]**」を選択します。

   「[!UICONTROL データセットを追加]」の「[!UICONTROL データセットを選択]」手順で、次の操作を行います。

   - 先ほど作成したデータセット（`Example dataset`）や、接続に含める他のデータセットに関連付けます。

      ![データセットを追加](./assets/cja-connections-2b.png)

   - 「**[!UICONTROL 次へ]**」を選択します。
   「[!UICONTROL データセットを追加]」の「[!UICONTROL データセット設定]」手順で、次の操作を行います。

   - 各データセットに対して、次の手順を行います。

      - Adobe Experience Platform のデータセットスキーマで定義されている使用可能な ID から[!UICONTROL ユーザー ID] を選択します。

      - [!UICONTROL データソースタイプ]リストから正しいデータソースを選択します。「**[!UICONTROL その他]**」を指定している場合は、データソースの説明を追加します。

      - 必要に応じて&#x200B;**[!UICONTROL すべての新しいデータを読み込み]**&#x200B;および&#x200B;**[!UICONTROL データセットの既存データのバックフィル]**&#x200B;を選択します。

      ![データセットの設定](./assets/cja-connections-3b.png)

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

   ![データ表示コンポーネント](./assets/cja-dataview-2.png)

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

5. [!UICONTROL パネル]の[!UICONTROL フリーフォームテーブル]でディメンションと指標のドラッグ＆ドロップを開始し、最初のレポートを作成します。例えば、`Program Points Balance` および `Page View` 指標、`email` をディメンションにドラッグすると、web サイトを訪問し、ロイヤルティポイントを収集するロイヤルティプログラムに参加しているプロファイルの概要をすばやく把握できます。

   ![ワークスペース - 最初のレポート](./assets/cja-projects-5.png)

コンポーネント、ビジュアライゼーション、パネルを使用してプロジェクトを作成し、分析を構築する方法について詳しくは、[Analysis Workspace の概要](../analysis-workspace/home.md)を参照してください。

>[!SUCCESS]
>
>すべての手順が完了しました。Adobe Experience Platform でどのデータ（スキーマ）を収集するか、どこにそのデータセットを保存するかを定義することから開始して、データセットにデータを転送できるよう、Edge ネットワークでデータストリームを設定しました。次に、拡張機能（Adobe Experience Platform Web SDK、Experience Cloud ID サービス）、データ要素、ルールを含むタグを定義してデプロイし、web サイトからデータを取得してデータストリームに送信します。Web サイトトラッキングデータやその他の Customer Journey Analytics を使用するために、接続を定義しました。データ表示の定義では、使用するディメンションと指標を指定でき、最後に、最初のプロジェクトを作成し、データを視覚化および分析します。
