---
title: タグを使用したCustomer Journey Analytics用 Web SDK の実装
description: タグを使用してCustomer Journey Analytics用 Web SDK を実装する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 76%

---

# タグを使用したCustomer Journey Analytics用 Web SDK の実装

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Adobe Experience Platformのタグ機能を使用して、データを収集するコードをサイトに実装できます。 このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。タグは、Adobe Experience Platform Web SDK 拡張機能を使用して、Adobe Experience Platform とのシームレスな統合を提供します。

## タグを作成する

1. Adobe Experience Platform UI の左パネルの「[!UICONTROL データ収集]」で、「**[!UICONTROL タグ]**」を選択します。

2. 「**[!UICONTROL 新しいプロパティ]**」を選択します。

   タグに名前を付け、「**[!UICONTROL Web]**」を選択し、ドメイン名を入力します。「**[!UICONTROL 保存]**」を選択して続行します。

   ![ プロパティの作成](assets/create-property.png)

## タグの設定

タグを作成したら、適切な拡張機能を使用してタグを設定し、サイトをトラッキングしてAdobe Experience Platformにデータを送信する方法に応じて、データ要素とルールを設定する必要があります。

[!UICONTROL タグのプロパティ]をクリックして新しく作成したタグを開きます。


### **拡張機能**

（データストリーム経由で）Adobe Experience Platformにデータを確実に送信できるようにするには、タグに Platform Web SDKAdobe拡張機能を追加します。

Adobe Experience Platform Web SDK 拡張機能を作成して設定するには：

1. 左パネルで「**[!UICONTROL 拡張機能]**」を選択します。

1. 上部のバーで「**[!UICONTROL カタログ]**」をクリックします。

1. Adobe Experience Platform Web SDK 拡張機能を検索またはスクロールし、「**[!UICONTROL インストール]**」をクリックしてインストールします。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. サンドボックスと、以前に作成した[!UICONTROL 実稼動環境]、（オプション）[!UICONTROL ステージング環境]および[!UICONTROL 開発環境]用のデータストリームを選択します。

   ![AEP Web SDK 拡張機能の設定](assets/aepwebsk-extension-datastreams.png)

   「**[!UICONTROL 保存]**」を選択します。

詳しくは、[Adobe Experience Platform Web SDK 拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html)を参照してください。

Web SDK には、[!UICONTROL Adobe Experience Cloud ID サービス ] がネイティブに含まれているので、タグに ID サービス拡張機能を追加する必要はありません。

### **データ要素**

データ要素は、データディクショナリ（またはデータマップ）の構築ブロックです。データ要素を使用して、マーケティングおよび広告テクノロジー全体でデータを収集、整理、配信します。タグでデータレイヤーから読み取り、Adobe Experience Platform にデータを配信するために使用できるデータ要素を設定します。

データ要素には様々なタイプがあります。最初にデータ要素を設定して、サイトでユーザーが表示しているページ名を取り込みます。

ページ名データ要素を定義するには：

1. 左パネルで「**[!UICONTROL データ要素]**」を選択します。

2. 「**[!UICONTROL データ要素を追加]**」を選択します。

3. [!UICONTROL データ要素を作成]ダイアログで、次の手順を実行します。

   - データ要素に名前を付けます（例：`Page Name`）。

   - [!UICONTROL 拡張機能]リストから、「**[!UICONTROL Core]**」を選択します。

   - [!UICONTROL データ要素タイプ]リストから、**[!UICONTROL ページ情報]**&#x200B;を選択します。

   - [!UICONTROL 属性]リストから、「**[!UICONTROL タイトル]**」を選択します。

     ![ページ情報を使用した日付要素の作成](assets/create-dataelement-1.png)

     または、データレイヤーの変数の値（`pageName` や [!UICONTROL JavaScript 変数] データ要素タイプなど）を使用して、データ要素を定義できました。

     ![JavaScript 変数を使用したデータ要素の作成](assets/create-dataelement-2.png)

   - 「**[!UICONTROL 保存]**」を選択します。

次に、Experience Cloud ID（Adobe Experience Platform Web SDK によって自動的に提供され、Experience Cloud ID サービス拡張機能を通じて使用できる）を参照するデータ要素を設定します。

ECID データ要素を定義するには：

1. 左パネルで「**[!UICONTROL データ要素]**」を選択します。

2. 「**[!UICONTROL データ要素を追加]**」を選択します。

3. [!UICONTROL データ要素を作成]ダイアログで、次の手順を実行します。

   - データ要素に名前を付けます（例：`ECID`）。

   - [!UICONTROL 拡張機能]リストから、**[!UICONTROL Experience Cloud ID サービス]**&#x200B;を選択します。

   - [!UICONTROL データ要素タイプ]リストから、**[!UICONTROL ECID]** を選択します。

     ![ECID データ要素](assets/ecid-dataelement.png)

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

     ![ECID データ要素を選択](assets/pick-ecid-dataelement.png)

     ![ECID データ要素をマッピング](assets/map-ecid.png)


   - スキーマ内で定義した `web > webPageDetails > name` 属性を、ページ名データ要素にマッピングします。

     ![ページ名データ要素をマップ](assets/map-pagename.png)

   - 「**[!UICONTROL 保存]**」を選択します。


### **ルール**

Adobe Experience Platform のタグは、ルールベースのシステムに従います。ユーザーの操作と関する各種データを参照します。ルールで設定された条件が満たされると、ルールは、特定した拡張機能、スクリプトまたはクライアント側コードをトリガーします。ルールを使用し、Adobe Experience Platform Web SDK 拡張機能を使用して、XDM オブジェクトなどのデータを Adobe Experience Platform に送信できます。

ルールを定義するには：

1. 左パネルで「**[!UICONTROL ルール]**」を選択します。

1. 「**[!UICONTROL 新規ルールを作成]**」を選択します。

1. [!UICONTROL ルールを作成]ダイアログで、次の手順を実行します。

   - ルールに名前を付けます（例：`Page View`）。

   - 「[!UICONTROL イベント]」の下の「**[!UICONTROL + 追加]**」を選択します。

   - [!UICONTROL イベント設定]ダイアログで、次の手順を実行します。

      - [!UICONTROL 拡張機能]リストから、「**[!UICONTROL Core]**」を選択します。

      - [!UICONTROL イベントタイプ]リストから「**[!UICONTROL 読み込んだウィンドウ]**」を選択します。

        ![ルール - イベント設定](assets/event-windowloaded-pageview.png)

      - 「**[!UICONTROL 変更を保持]**」を選択します。



   - 「[!UICONTROL アクション]」の下の「**[!UICONTROL + 追加]**」を選択します。

   - [!UICONTROL アクション設定]ダイアログで、次の手順を実行します。

      - [!UICONTROL 拡張機能]リストから&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]** を選択します。

      - [!UICONTROL アクションタイプ]リストから「**[!UICONTROL イベントを送信]**」を選択します。

      - [!UICONTROL タイプ]リストから、**[!UICONTROL web.webpagedetails.pageViews]** を選択します。

      - [!UICONTROL XDM データ]の横にある円柱アイコンを選択し、データ要素のリストから「**[!UICONTROL XDM - ページビュー]**」を選択します。

     ![ルール - アクションの設定](assets/action-pageview-xdm.png)

      - 「**[!UICONTROL 変更を保持]**」を選択します。

   - ルールは次のようになります。

     ![ルールを作成](assets/rule-pageview.png)

1. 「**[!UICONTROL 保存]**」を選択します。

上記は、他のデータ要素の値を含む XDM データをAdobe Experience Platformに送信するルールを定義する例に過ぎません。

タグ内で様々な方法でルールを使用して、（データ要素を使用して）変数を操作できます。

詳しくは、[ルール](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=ja)を参照してください。

## タグを作成して公開する

データ要素とルールを定義したら、タグを作成して公開する必要があります。 ライブラリビルドを作成する場合は、そのビルドを環境に割り当てる必要があります。ビルドの拡張機能、ルール、およびデータ要素がコンパイルされ、割り当てられた環境に配置されます。各環境は、割り当てられたビルドをサイトに統合できる、一意の埋め込みコードを提供します。

タグを構築して公開するには、次の手順に従います。

1. 左パネルから「**[!UICONTROL 公開フロー]**」をクリックします。

2. **[!UICONTROL 作業ライブラリを選択]**／**[!UICONTROL ライブラリを追加…]**&#x200B;を選択します。

3. [!UICONTROL ライブラリを作成]ダイアログで、次の手順を実行します。

   - ライブラリに名前を付けます。

   - [!UICONTROL 環境]リストから「**[!UICONTROL 開発（開発）]**」を選択します。

   - 「**[!UICONTROL + 変更されたリソースをすべて追加]**」を選択します。

     ![公開 - ライブラリを作成](assets/create-library-aep.png)

   - 「**[!UICONTROL 開発用に保存およびビルド]**」を選択します。

   タグが保存され、開発環境用に作成されます。 緑のドットは、開発環境でタグが正常に作成されたことを示します。

4. **[!UICONTROL ...]** を選択してライブラリを再構築するか、ライブラリをステージング環境または実稼動環境に移動することができます。

   ![公開 - ライブラリを作成](assets/build-library.png)

Adobe Experience Platform タグは、Adobe Experience Platform Web SDK のデプロイに対応する必要がある、シンプルな公開ワークフローから複雑な公開ワークフローをサポートします。

詳しくは、[公開の概要](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja)を参照してください。


## タグコードの取得

最後に、追跡する web サイトにタグをインストールする必要があります。これは、web サイトのテンプレートのヘッダータグにコードを配置することを意味します。

タグを参照するコードを取得するには：

1. 左パネルで「**[!UICONTROL 環境]**」を選択します。

1. 環境のリストから、正しいインストール（ボックス）ボタンを選択します。

   [!UICONTROL Web インストール手順]ダイアログで、次のように読み込むスクリプトコードの横にある「コピー」ボタンを選択します。

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![環境](assets/environment.png)

1. 「**[!UICONTROL 閉じる]**」を選択します。

   開発環境用のコードの代わりに、Adobe Experience Platform Web SDK をデプロイするプロセスの場所に基づいて、別の環境（ステージング、実稼動）を選択することもできます。

   詳しくは、[環境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ja)を参照してください。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
