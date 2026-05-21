---
title: Adobe Experience Platform Mobile SDKを介したデータの取り込み
description: Adobe Experience Platform Mobile SDKとEdge Networkを使用してCustomer Journey Analyticsにデータを取り込む方法について説明します
solution: Customer Journey Analytics
feature: Basics
exl-id: fb48b031-e093-4490-b457-69dbb5debe8d
role: Admin
TQID: https://experienceleague.adobe.com/rbgqDkQLPbw-EfhMyUL-eVXZZ1cxMXiQmvU7Si2WCZ8
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: c38ed341-fab2-46df-9d72-88d8166edebbid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: df28738e-9c71-4aa8-929e-edde22340cc6id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 3536
ht-degree: 63%

---

# モバイル SDK経由でのデータ取り込み

このクイックスタートガイドでは、Adobe Experience Platform Mobile SDKとEdge Networkを使用して、モバイルアプリのトラッキングデータをAdobe Experience Platformに直接取り込む方法について説明します。 そのデータをCustomer Journey Analyticsで使用し。

これには、次の手順を実行する必要があります。

- Adobe Experience Platform で&#x200B;**スキーマとデータセットを設定**&#x200B;し、収集するデータのモデル（スキーマ）と、実際にデータ（データセット）を収集する場所を定義します。

- **データストリームの設定**：収集したデータを Adobe Experience Platform で設定したデータセットにルーティングするように Adobe Experience Platform Edge Network を設定します。

- **タグ**&#x200B;を使用すると、モバイルアプリケーションのデータに対してルールとデータ要素を簡単に設定できます。 次に、データが Adobe Experience Platform Edge Network 上に設定されたデータストリームに送信されることを確認します。

- **デプロイと検証**&#x200B;を行います。 タグの開発を繰り返し実行し、すべての検証が完了したら、本番環境で公開できる環境を構築します。

- Customer Journey Analytics で、**接続を設定**&#x200B;します。 この接続には、（少なくとも）Adobe Experience Platform データセットを含める必要があります。

- Customer Journey Analytics で&#x200B;**データ表示を設定**&#x200B;し、Analysis Workspace で使用する指標とディメンションを定義します。

- Customer Journey Analytics で&#x200B;**プロジェクトを設定**&#x200B;して、レポートとビジュアライゼーションを作成します。

>[!NOTE]
>
>このクイックスタートガイドは、アプリケーションから収集したデータをAdobe Experience Platformに取り込み、Customer Journey Analyticsで使用する方法に関する簡略化されたガイドです。 参照する際には、追加情報を調べることを強くお勧めします。


## スキーマとデータセットの設定

データを Adobe Experience Platform に取り込むには、まず収集するデータを定義する必要があります。 ダウンストリームの機能で認識し、処理するには、Adobe Experience Platform に取り込まれるすべてのデータが、標準的な非正規化された構造に準拠する必要があります。 Experience Data Model （XDM）は、スキーマの形式で構造を提供する標準フレームワークです。

スキーマを定義したら、1 つ以上のデータセットを使用して、データの収集を保存および管理します。 データセットは、スキーマ（列）とフィールド（行）を含むデータのコレクション（通常はテーブル）のストレージおよび管理構造です。

Adobe Experience Platform に取り込まれるすべてのデータは、データセットとして保持する前に、事前定義済みのスキーマに準拠している必要があります。

### スキーマの設定

モバイルアプリを使用してプロファイルから最小限のデータ（シーン名、識別など）を追跡する必要があります。
まず、このデータをモデル化するスキーマを定義する必要があります。

スキーマを設定するには：

1. Adobe Experience Platform UI の左パネルの「[!UICONTROL データ管理]」で、「**[!UICONTROL スキーマ]**」を選択します。

1. 「**[!UICONTROL スキーマを作成]**」を選択します。
.
1. スキーマを作成ウィザードの「クラスを選択」ステップで、次の操作を行います。

   1. 「**[!UICONTROL エクスペリエンスイベント]**」を選択します。

      ![スキーマ](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    エクスペリエンスイベントスキーマを使用すると、プロファイルの&#x200B;_動作_（シーン名、買い物かごに追加するプッシュボタンなど）をモデル化できます。 個々のプロファイルスキーマは、プロファイル&#x200B;_属性_（名前、メール、性別など）のモデル化に使用されます。

   1. 「**[!UICONTROL 次へ]**」を選択します。


1. [!UICONTROL スキーマを作成]ウィザードの[!UICONTROL 名前とレビューの手順]で、次の操作を行います。

   1. スキーマの&#x200B;**[!UICONTROL スキーマ表示名]**&#x200B;と&#x200B;**[!UICONTROL 説明]**（オプション）を入力します。

      ![スキーマに名前を付ける](./assets/create-ee-schema-wizard-step-2.png)

   1. 「**[!UICONTROL 完了]**」を選択します。

1. 「スキーマの例」の「構造」タブで、次の操作を行います。

   1. 「[!UICONTROL フィールドグループ]」で「**[!UICONTROL + 追加]**」を選択します。

      ![フィールドグループを追加](./assets/add-field-group-button.png)

      フィールドグループは、スキーマを簡単に拡張できる、再利用可能なオブジェクトと属性のコレクションです。

   1. [!UICONTROL  フィールドグループを追加] ダイアログで、リストから&#x200B;**[!UICONTROL AEP Mobile SDK ExperienceEvent]** フィールドグループを選択します。

      ![AEP Mobile Lifecycle Details フィールドグループ ](./assets/select-aepmobilesdk-experienceevent.png)

      「プレビュー」ボタンを選択すると、このフィールドグループに属するフィールド（`application > name` など）のプレビューを表示できます。

      ![AEP Mobile Lifecycle Details フィールドグループ preview](./assets/aepmobilesdk-experienceevent-preview.png)

      「**[!UICONTROL 戻る]**」を選択してプレビューを閉じます。

   1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. [!UICONTROL 構造]パネルで、スキーマ名の隣にある「**[!UICONTROL +]**」をクリックします。

   ![スキーマ追加フィールドボタンの例](./assets/example-mobileschema-plus.png)

1. [!UICONTROL  フィールドプロパティ ] パネルで、`identification`を[!UICONTROL  フィールド名]として、**[!UICONTROL 識別]**&#x200B;を[!UICONTROL 表示名]として入力し、**[!UICONTROL オブジェクト]**&#x200B;を[!UICONTROL  タイプ ]として選択し、**[!UICONTROL ExperienceEvent Core v2.1]**&#x200B;を[!UICONTROL  フィールドグループ ]として選択します。

   >[!NOTE]
   >
   >このフィールドグループが使用できない場合は、ID フィールドを含む別のフィールドグループを検索します。 または、フィールドグループに[新しいフィールドグループを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=ja)し、（`ecid`、`crmId` など）[新しい ID フィールドを追加](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=ja#define-a-identity-field)して、この新しいフィールドグループを選択します。

   ![ID オブジェクト](./assets/identification-field-mobile.png)

   ID オブジェクトは、スキーマに ID 機能を追加します。 この場合、Experience Cloud IDとメールアドレスを使用して、モバイルアプリを使用してプロファイルを識別する必要があります。 ユーザーの ID を追跡するために使用できる属性は他にも多数あります（例：顧客 ID、ロイヤルティ ID）。

   「**[!UICONTROL 適用]**」を選択して、このオブジェクトをスキーマに追加します。

1. 先ほど追加した ID オブジェクトで「**[!UICONTROL ecid]**」フィールドをクリックし、右パネルの [!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]**、**[!UICONTROL プライマリ ID]** および **[!UICONTROL ECID]** を選択します。

   ![ECID を ID として指定](./assets/specify-identity-mobile.png)

   Experience Cloud ID を、Adobe Experience Platform Identity Service が同じ ECID を持つプロファイルの動作を組み合わせる（ステッチする）ために使用するプライマリ ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。 ecid 属性にフィンガープリントアイコンが表示されます。

1. 先ほど追加した ID オブジェクトで「**[!UICONTROL メール]**」フィールドをクリックし、[!UICONTROL フィールドプロパティ]パネルの[!UICONTROL ID 名前空間]リストから **[!UICONTROL ID]** と&#x200B;**[!UICONTROL メール]**&#x200B;を選択します。

   ![メールを ID として指定](./assets/specify-email-identity-mobile.png)

   メールアドレスを、Adobe Experience Platform Identity Service がプロファイルの動作を組み合わせる（ステッチする）ために使用するもう一つの ID として指定します。

   「**[!UICONTROL 適用]**」を選択します。 メール属性にフィンガープリントアイコンが表示されます。

   「**[!UICONTROL 保存]**」を選択します。

1. スキーマの名前を表示しているスキーマのルート要素を選択してから、**[!UICONTROL プロファイル]**&#x200B;スイッチをクリックします。

   プロファイルのスキーマを有効にするよう求められます。 有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータをリアルタイム顧客プロファイルと結合します。

   詳しくは、[リアルタイム顧客プロファイルで使用するスキーマを有効にする](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#profile)を参照してください。

   >[!IMPORTANT]
   >
   >    プロファイルで有効にしたスキーマを保存すると、そのスキーマはプロファイルで無効にできなくなります。

   ![プロファイルでスキーマを有効にする](./assets/enable-for-profile.png)

1. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

モバイルアプリケーションから取得できるデータをモデル化する、最小限のスキーマを作成しました。 このスキーマを使用することで、Experience Cloud ID とメールアドレスを使用してプロファイルを識別できます。 プロファイルのスキーマを有効にすると、モバイルアプリケーションから取得したデータがリアルタイム顧客プロファイルに追加されます。

行動データの横に、モバイルアプリケーションからプロファイル属性データを取り込むこともできます（ニュースレターを購読しているプロファイルの詳細など）。

プロファイルデータをキャプチャするには、次のことをおこないます。

- XDM Individual Profile クラスに基づいてスキーマを作成します。

- Profile Core v2 フィールドグループをスキーマに追加します。

- Profile Core v2 フィールドグループに基づいて ID オブジェクトを追加します。

- Experience Cloud ID をプライマリ識別子として定義し、メールを識別子として定義します。

- プロファイルでスキーマを有効にする

フィールドグループと個々のフィールドをスキーマに追加、またはスキーマから削除する方法について詳しくは、[UI でのスキーマの作成と編集](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=ja)を参照してください。

### データセットの設定

スキーマを使用して、データモデルを定義しました。 データセットを使用して、そのデータを保存および管理するための構造を定義する必要があります。

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

   プロファイルのデータセットを有効にするよう求められます。 有効にすると、データセットは、取り込んだデータを使用してリアルタイム顧客プロファイルを強化します。

   >[!IMPORTANT]
   >
   >    プロファイルのデータセットを有効にできるのは、データセットが準拠するスキーマがプロファイルに対しても有効になっている場合のみです。

   ![プロファイルでスキーマを有効にする](./assets/aepwebsdk-dataset-profile.png)

データセットの表示、プレビュー、作成、削除の方法について詳しくは、[データセット UI ガイド](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja)を参照してください。 リアルタイム顧客プロファイルのデータセットを有効にする方法について説明します。

## データストリームの設定

データストリームは、Adobe Experience Platform Web および Mobile SDK を実装する際のサーバーサイド設定を表します。 Adobe Experience Platform SDK を使用してデータを収集する際、データはAdobe Experience Platform Edge Network に送信されます。 これは、データの転送先となるサービスを決定するデータストリームです。

設定では、モバイルアプリから収集したデータをAdobe Experience Platformのデータセットに送信する必要があります。

データストリームを設定するには：

1. Adobe Experience Platform UI の左パネルで、「[!UICONTROL データ収集]」から「**[!UICONTROL データストリーム]**」を選択します。

2. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。

3. データストリームに名前を付けて説明します。 [!UICONTROL イベントスキーマ]リストからスキーマを選択します。

   ![新規データストリーム](./assets/new-datastream.png)

4. 「**[!UICONTROL 保存]**」を選択します。

5. 「**[!UICONTROL サービスを追加]**」を選択します。

6. [!UICONTROL サービスを追加画面]で、次の操作を行います。

   1. [!UICONTROL サービス]リストから&#x200B;**[!UICONTROL Adobe Experience Platform]** を選択します。

   2. 「**[!UICONTROL 有効]**」が選択されていることを確認します。

   3. [!UICONTROL イベントデータセット]リストからお使いのデータセットを選択します。

      ![Datastream AEP サービス](./assets/datastream-aep-service.png)

   4. その他の設定はそのままにし、「**[!UICONTROL 保存]**」を選択してデータストリームを保存します。

これで、データストリームは、モバイルアプリから収集したデータをAdobe Experience Platformのデータセットに転送するように設定されました。

データストリームの設定方法と機密データの処理方法について詳しくは、[データストリームの概要](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja)を参照してください。



## タグの使用

サイトにコードを実装して実際にデータを収集するには、Adobe Experience Platformのタグ機能を使用します。 このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。 タグは、Adobe Experience Platform Mobile SDK拡張機能を使用して、Adobe Experience Platformとシームレスに連携します。

### タグを作成する

1. Adobe Experience Platform UI の左パネルの「[!UICONTROL データ収集]」で、「**[!UICONTROL タグ]**」を選択します。

2. 「**[!UICONTROL 新しいプロパティ]**」を選択します。

   タグに名前を付け、**[!UICONTROL モバイル]**&#x200B;を選択します。 「**[!UICONTROL 保存]**」を選択して続行します。

   ![ プロパティの作成](./assets/create-mobile-property.png)

### タグの設定

タグを作成したら、適切な拡張機能を使用してタグを設定し、サイトを追跡して Adobe Experience Platform にデータを送信する方法に応じて、データ要素とルールを設定する必要があります。

設定するには、[!UICONTROL  タグプロパティ ]のリストから新しく作成したタグを選択します。


#### **拡張機能**

Adobe Platform Edge Network拡張機能をタグに追加して、（データストリームを介して）Adobe Experience Platformにデータを送信できるようにします。

Adobe Experience Platform Mobile SDK拡張機能を作成して設定するには：

1. 左パネルで「**[!UICONTROL 拡張機能]**」を選択します。 Mobile CoreとProfileの拡張機能は既に利用可能です。

1. 上部のバーで「**[!UICONTROL カタログ]**」をクリックします。

1. **[!UICONTROL Adobe Experience Platform Edge Network]**&#x200B;拡張機能を検索またはスクロールし、右側のウィンドウで&#x200B;**[!UICONTROL Install]**&#x200B;を選択してインストールします。

1. サンドボックスと、以前に作成した[!UICONTROL 本番環境]、（オプション）[!UICONTROL ステージング環境]および[!UICONTROL 開発環境]用のデータストリームを選択します。

   ![AEP Mobile SDK拡張機能の設定](./assets/aepmobilesdk-extension-datastream.png)

1. [!UICONTROL Domain configuration]の下に&#x200B;**[!UICONTROL Edge Network domain]**&#x200B;を入力します。 通常は`<organizationName>.data.adobedc.net`を使用します。

1. 「**[!UICONTROL 保存]**」を選択します。

詳しくは、[Adobe Experience Platform Edge Network拡張機能の設定](https://developer.adobe.com/client-sdks/documentation/edge-network)を参照してください。

また、カタログから次の追加の拡張機能を設定することもできます。

- 単一の顧客像：
- AEP Assurance:
- 同意：

拡張機能とその設定について詳しくは、Experience Platform モバイルアプリチュートリアルの[ タグプロパティの設定](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html?lang=ja)を参照してください。

#### **データ要素**

データ要素は、データ辞書（またはデータマップ）の構築要素です。 データ要素を使用して、マーケティングおよび広告テクノロジー全体でデータを収集、整理、配信します。 モバイルアプリのデータやイベントから読み取り、データをAdobe Experience Platformに配信するために使用できるデータ要素をタグに設定します。

例えば、モバイルアプリからキャリア名を収集する場合などです。

キャリア名データ要素を定義するには、次の手順に従います。

1. 左パネルで「**[!UICONTROL データ要素]**」を選択します。

2. 「**[!UICONTROL データ要素を追加]**」を選択します。

3. [!UICONTROL データ要素を作成]ダイアログで、次の手順を実行します。

   - データ要素に名前を付けます（例：`Carrier Name`）。

   - [!UICONTROL 拡張機能] リストから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。

   - 「[!UICONTROL  データ要素タイプ ]」リストから「**[!UICONTROL キャリア名]**」を選択します。


     ![ページ情報を使用した日付要素の作成](./assets/create-dataelement-mobile.png)

   - 「**[!UICONTROL 保存]**」を選択します。

必要な数のデータ要素を作成し、ルールで使用できます。


#### **ルール**

Adobe Experience Platform のタグは、ルールベースのシステムに従います。 ユーザーの操作と関する各種データを参照します。 ルールで設定された条件が満たされると、ルールは、特定した拡張機能、スクリプトまたはクライアント側コードをトリガーします。 ルールを使用すると、Adobe Experience Platform Edge Network拡張機能を使用してAdobe Experience Platformにデータ（XDM オブジェクトなど）を送信できます。

例えば、モバイルアプリが使用されている場合（前景）と、モバイルアプリが使用されていない場合（背景にプッシュバックされている場合）に、イベントデータを送信する必要があります。

ルールを定義するには：

1. 左パネルで「**[!UICONTROL ルール]**」を選択します。

2. 「**[!UICONTROL 新規ルールを作成]**」を選択します。

3. [!UICONTROL ルールを作成]ダイアログで、次の手順を実行します。

   - ルールに名前を付けます（例：`Application Status`）。

   - 「[!UICONTROL イベント]」の下の「**[!UICONTROL + 追加]**」を選択します。

   - [!UICONTROL イベント設定]ダイアログで、次の手順を実行します。

      - [!UICONTROL 拡張機能] リストから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。

      - [!UICONTROL  イベントタイプ ] リストから&#x200B;**[!UICONTROL 描画領域]**&#x200B;を選択します。

      - 「**[!UICONTROL 変更を保持]**」を選択します。

   - [!UICONTROL Mobile Core - Foreground]の横にある![Plus](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg)をクリックします。

      - [!UICONTROL 拡張機能] リストから&#x200B;**[!UICONTROL Mobile Core]**&#x200B;を選択します。

      - 「[!UICONTROL  イベントタイプ ]」リストから「**[!UICONTROL 背景]**」を選択します。

      - 「**[!UICONTROL 変更を保持]**」を選択します。

   - [!UICONTROL  アクション ]の下にある![ プラス ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg)追加をクリックします。 [!UICONTROL アクション設定]ダイアログで、次の手順を実行します。

      - [!UICONTROL 拡張機能] リストから&#x200B;**[!UICONTROL Adobe Experience Platform Edge Network]**&#x200B;を選択します。

      - 「[!UICONTROL  アクションタイプ ]」リストから「**[!UICONTROL Edge Networkにイベントを転送」を選択します。]**

      - 「**[!UICONTROL 変更を保持]**」を選択します。

   - ルールは次のようになります。

     ![ルールを作成](assets/rule-appstatus.png)

   - 「**[!UICONTROL 保存]**」を選択します。

上記は、アプリケーションステータスを含むXDM データをAdobe Edge NetworkおよびAdobe Experience Platformに送信するルールの一例です。

タグ内で様々な方法でルールを使用して、（データ要素を使用して）変数を操作できます。

詳しくは、[ルール](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/#configure-a-rule-to-forward-lifecycle-metrics-to-platform)を参照してください。

### タグを作成して公開する

データ要素とルールを定義したら、タグを作成して公開する必要があります。 ライブラリビルドを作成する場合は、そのビルドを環境に割り当てる必要があります。 ビルドの拡張機能、ルール、およびデータ要素がコンパイルされ、割り当てられた環境に配置されます。 各環境は、割り当てられたビルドをサイトに統合できる、一意の埋め込みコードを提供します。

タグを構築して公開するには、次の手順に従います。

1. 左パネルから「**[!UICONTROL 公開フロー]**」をクリックします。

2. **[!UICONTROL 作業ライブラリを選択]**／**[!UICONTROL ライブラリを追加…]**&#x200B;を選択します。

3. [!UICONTROL ライブラリを作成]ダイアログで、次の手順を実行します。

   - ライブラリに名前を付けます。

   - [!UICONTROL 環境]リストから「**[!UICONTROL 開発（開発）]**」を選択します。

   - 「**[!UICONTROL + 変更されたリソースをすべて追加]**」を選択します。

     ![公開 - ライブラリを作成](./assets/build-library-mobile.png)

   - 「**[!UICONTROL 開発用に保存およびビルド]**」を選択します。

   タグが保存され、開発環境用に作成されます。 緑のドットは、開発環境でタグが正常に作成されたことを示します。

4. **[!UICONTROL ...]** を選択してライブラリを再構築するか、ライブラリをステージング環境または本番環境に移動することができます。

Adobe Experience Platform タグは、Adobe Experience Platform Edge Networkのデプロイメントに対応するシンプルから複雑な公開ワークフローをサポートします。

詳しくは、[公開の概要](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)を参照してください。


### タグコードの取得

最後に、追跡するモバイルアプリ内でタグを使用する必要があります。

モバイルアプリの設定方法とアプリ内でのタグの使用方法を説明するコード手順を取得するには、次の手順を実行します。

1. 左パネルで「**[!UICONTROL 環境]**」を選択します。

2. 環境のリストから、正しいインストール ![Box](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Box_18_N.svg) ボタンを選択します。

   [!UICONTROL  モバイルインストール手順] ダイアログで、適切なプラットフォーム（[!UICONTROL iOS]、[!UICONTROL Android]）を選択します。 次に、モバイルアプリの設定と初期化に使用する関連するコードスニペットの横にある「![ コピー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)」ボタンを使用します。

   ![環境](./assets/environment-mobile.png)

3. 「**[!UICONTROL 閉じる]**」を選択します。

開発環境のコードの代わりに、Adobe Experience Platform Mobile SDKのデプロイ中の場所に基づいて、別の環境（ステージング、実稼動環境）を選択できます。

詳しくは、[環境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ja)を参照してください。

## デプロイと検証

これで、モバイルアプリ内にコードをデプロイできるようになりました。 デプロイすると、モバイルアプリはAdobe Experience Platformにデータの収集を開始します。

実装を検証し、必要に応じて修正したら、タグの公開ワークフロー機能を使用して、ステージング環境と本番環境にデプロイします。

詳しくは、[ モバイルアプリでのAdobe Experience Cloudの実装チュートリアル ](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=ja)を参照してください。

## 接続の設定

Adobe Experience Platform データを Customer Journey Analytics で使用するには、接続（スキーマ、データセット、ワークフローの設定によって生成されたデータを含む）を作成します。

接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。 これらのデータセットについてレポートを作成するには、まずAdobe Experience PlatformとWorkspaceのデータセット間の接続を確立する必要があります。

接続を作成するには：

1. Customer Journey Analytics UIの上部メニューで、**[!UICONTROL Data management]**&#x200B;から&#x200B;**[!UICONTROL Connections]**&#x200B;を選択します（オプション）。

2. 「**[!UICONTROL 新しい接続を作成]**」を選択します。

3. [!UICONTROL 名称未設定の接続]画面で、次の手順を実行します。

   「[!UICONTROL 接続設定]」で接続に名前を付けて説明します。

   [!UICONTROL データ設定]の[!UICONTROL サンドボックス]リストから適切なサンドボックスを選択し、[!UICONTROL 毎日のイベントの平均数]リストから日次イベントの数を選択します。

   ![接続設定](./assets/cja-connections-1.png)

   「**[!UICONTROL データセットを追加]**」を選択します。

   「[!UICONTROL データセットを追加]」の「[!UICONTROL データセットを選択]」手順で、次の操作を行います。

   - 以前に作成したデータセットや、接続に含める関連データセット（例：Adobe Journey OptimizerのPush Tracking Experience Events データやPush Profile データ）を選択します

     ![データセットを追加](./assets/cja-connections-ajopush.png)

   - 「**[!UICONTROL 次へ]**」を選択します。

   「[!UICONTROL データセットを追加]」の「[!UICONTROL データセット設定]」手順で、次の操作を行います。

   - 各データセットに対して、次の手順を行います。

      - Adobe Experience Platform のデータセットスキーマで定義されている使用可能な ID から[!UICONTROL ユーザー ID] を選択します。

      - [!UICONTROL データソースタイプ]リストから正しいデータソースを選択します。 「**[!UICONTROL その他]**」を指定している場合は、データソースの説明を追加します。

      - 必要に応じて&#x200B;**[!UICONTROL すべての新しいデータを読み込み]**&#x200B;および&#x200B;**[!UICONTROL データセットの既存データのバックフィル]**&#x200B;を選択します。

     ![データセットの設定](./assets/cja-connections-ajopushid.png)

   - 「**[!UICONTROL データセットを追加]**」を選択します。

   「**[!UICONTROL 保存]**」を選択します。

接続を作成および管理する方法、およびデータセットを選択して組み合わせる方法について詳しくは、[接続の概要](../connections/overview.md)を参照してください。

## データ表示の設定

データ表示は、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。 Analysis Workspace で使用可能なすべてのディメンションと指標、およびこれらのディメンションと指標からデータを取得する列を指定します。 データ表示は、Analysis Workspace でレポートの準備を行う際に定義します。

データ表示を作成するには：

1. Customer Journey Analytics UIの上部メニューで、**[!UICONTROL データビュー]** （オプションで&#x200B;**[!UICONTROL データ管理]**&#x200B;から）を選択します。

2. 「**[!UICONTROL 新しいデータ表示を作成]**」を選択します。

3. [!UICONTROL 設定]手順で、次の操作を行います。

   [!UICONTROL 接続]リストで接続を選択します。

   接続に名前を付け、（オプションで）説明します。

   ![データ表示の設定](./assets/cja-dataview-1.png)

   「**[!UICONTROL 保存して続行]**」を選択します。

4. [!UICONTROL コンポーネント]手順で、次の操作を行います。

   [!UICONTROL 指標]または[!UICONTROL ディメンション]コンポーネントボックスに含めるスキーマフィールドや標準コンポーネントを追加します。

   ![データ表示コンポーネント](./assets/cja-dataview-2-mobile.png)

   「**[!UICONTROL 保存して続行]**」を選択します。

5. [!UICONTROL 設定]手順で、次の操作を行います。

   ![データ表示設定](./assets/cja-dataview-3.png)

   設定をそのままにし、「**[!UICONTROL 保存して終了]**」を選択します。

データビューの作成と編集方法、データビューで使用できるコンポーネント、セグメントとセッションの設定の使用方法について詳しくは、[ データビューの概要](../data-views/data-views.md)を参照してください。


## プロジェクトの設定

Analysis Workspace は、データに基づき、分析をすばやく構築してインサイトを共有できる、柔軟なブラウザーツールです。 ワークスペースプロジェクトでは、データコンポーネント、テーブル、およびビジュアライゼーションを組み合わせて、分析を作成し、組織内の任意のユーザーと共有できます。

プロジェクトを作成するには：

1. Customer Journey Analytics UIで、上部メニューの「**[!UICONTROL プロジェクト]**」を選択します。

2. 左側のナビゲーションの「**[!UICONTROL プロジェクト]**」を選択します。

3. 「**[!UICONTROL プロジェクトを作成]**」を選択します。

   ![ワークスペースプロジェクト](./assets/cja-projects-1.png)

   「**[!UICONTROL 空のプロジェクト]**」を選択します。

   ![ワークスペース - 空のプロジェクト](./assets/cja-projects-2.png)

4. リストからデータ表示を選択します。

   ![ワークスペースでデータ表示を選択](./assets/cja-projects-3.png)します。

5. 最初のレポートを作成するには、[!UICONTROL  パネル ]の[!UICONTROL 自由形式テーブル ]にディメンションと指標をドラッグ&amp;ドロップします。 例えば、`Events`を指標として、`Push Title`をディメンションとしてドラッグし、`Event Type`で分類して、モバイルアプリのプッシュ通知の概要とプッシュ通知に関する内容を確認します。

   ![ワークスペース - 最初のレポート](./assets/cja-projects-5-mobile.png)

コンポーネント、ビジュアライゼーション、パネルを使用してプロジェクトを作成し、分析を構築する方法について詳しくは、[Analysis Workspace の概要](../analysis-workspace/home.md)を参照してください。

>[!SUCCESS]
>
>すべての手順が完了しました。 Adobe Experience Platform でどのデータ（スキーマ）を収集するか、どこにそのデータセットを保存するかを定義することから開始して、データセットにデータを転送できるよう、Edge ネットワークでデータストリームを設定しました。 続いて、拡張機能（Adobe Experience Platform Edge Networkなど）、データ要素、ルールを含むタグを定義してデプロイし、モバイルアプリからデータを取得してデータストリームに送信します。 モバイルアプリのプッシュ通知トラッキングデータおよびその他のデータを使用するように、Customer Journey Analyticsで接続を定義しました。 データビュー定義で、使用するディメンションと指標を指定し、最初のプロジェクトとしてモバイルアプリデータの可視化と分析を作成しました。
