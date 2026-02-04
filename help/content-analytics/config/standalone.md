---
title: Content Analyticsの設定（スタンドアロン）
description: Content Analytics（スタンドアロン）の設定に必要な手順について説明します
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 44fa4385faf2e41f90c6bce3648a4890d4a70442
workflow-type: tm+mt
source-wordcount: '2517'
ht-degree: 6%

---


# スタンドアロン設定

>[!IMPORTANT]
>
>この設定ガイドは、スタンドアロンのAdobe Content Analytics パッケージのライセンスを取得したお客様向けです。 このガイドは、Customer Journey AnalyticsまたはContent Analyticsの機能を超えるその他のExperience Platform アプリケーションを使用していないか、使用する予定がないことを前提としています。 既存のContent Analytics実装の一部としてContent Analyticsを設定および使用する場合は、[Customer Journey Analyticsの設定 &#x200B;](configuration.md) を参照してください。
>

Content Analyticsはスタンドアロン製品としてライセンスされていますが、設定はExperience PlatformとCustomer Journey Analyticsの内部で行われます。 これらのプラットフォームは、Content Analyticsが必要とし、使用するデータ収集および分析インフラストラクチャを提供します。 このガイドでは、Experience PlatformとCustomer Journey Analyticsを初めて使用する場合でも、必要なすべての具体的な手順を説明します。

スタンドアロンのContent Analyticsの設定を開始する前に、次の操作をおこなう必要があります。

* Web 分析の概念の基本的な理解、タグ管理システムの知識、JavaScriptの基本的な知識。
* 初期セットアップには 4～6 時間と、セットアップのテストと検証にさらに時間がかかります。

## 用語

このガイドでは、Experience PlatformやCustomer Journey Analyticsなど、なじみのない技術用語をいくつか使用しています。 Content Analyticsのコンテキストでの各用語の説明（参照リンクを含む）を以下に示します。

| 用語 | 説明 |
|---|---|
| **スキーマ** | [&#x200B; スキーマ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition) は、データの構造と形式を表現および検証する一連のルールです。 スキーマは、大まかに言えば、実際のオブジェクト（クリックなど、web サイト上で発生するイベントなど）の抽象的な定義を提供します。 そのオブジェクトの各インスタンスに含める必要があるデータの概要を説明します。 |
| **データセット** | [&#x200B; データセット &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview) は、スキーマ（列）とフィールド（行）を含んだデータコレクション（通常はテーブル）のストレージおよび管理用の構成体です。 データセットは、データベーステーブルに似ており、各行は Web サイトのイベントです。 |
| **データストリーム** | [&#x200B; データストリーム &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/overview) は、web サイトからAdobe Experience Platform内の正しいデータセットにデータをルーティングするサーバーサイド設定を表します。 データストリームは、サイトとストレージを接続するデータハイウェイとして機能します。 |
| **タグ** | Experience Platformの [&#x200B; タグ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/home) は、Adobeの次世代タグ管理機能です。 タグは、適切な顧客体験の実現に必要な分析、マーケティングおよび広告タグをデプロイおよび管理するためのシンプルな手段を提供します。 Content Analyticsでは、Adobeの tag management system を使用すると、すべてのページを同じように編集しなくても、web サイトにトラッキングコードをデプロイできます。 タグ機能は、Google Tag Manager で認識される機能と似ています。 |
| **サンドボックス** | Experience Platformには、1 つのExperience Platform インスタンスを別々の仮想環境に分割し、デジタルエクスペリエンスアプリケーションの開発と発展に役立つ [&#x200B; サンドボックス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home) が用意されています。 Content Analyticsは通常、*実稼動* サンドボックスを使用します。 |
| **接続** | [&#x200B; 接続 &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/overview) 取り込むExperience Platform データセットを定義します。 接続は、データセット（データがAEPに保存される場所）とCustomer Journey Analytics（データを分析する場所）間のリンクを定義します。 接続を使用すると、収集したデータをレポートに使用できます。 |
| **データビュー** | [&#x200B; データビュー &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/data-views) は、接続からデータを解釈する方法を決定できるコンテナです。 データビューは、レポートに使用できるすべてのディメンションと指標を指定します。 データビューは、分析で使用できる行と列を決定する設定のようなものです。 |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/home) は、Content Analyticsのレポートおよび分析の作成に使用する、ドラッグ&amp;ドロップのブラウザーインターフェイスです。 |
| **エクスペリエンス** | Content Analyticsでは、[&#x200B; エクスペリエンス &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/content-analytics/content-analytics#terminology) とは、ページ URL に基づいて取得および分析できる web ページ上のすべてのテキストコンテンツを指します。 |
| **アセット** | Content Analyticsでは、[&#x200B; アセット &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/content-analytics/content-analytics#terminology) は、画像のような個別の一意のコンテンツです。 |


## 設定の概要

この設定ガイドを使用すると、動作する **スタンドアロン** Content Analytics実装を必要とするすべてのアプリケーションをセットアップできます。 設定は 3 つのフェーズに分けることができます。各フェーズは、前のフェーズに基づいて構築されます。

**フェーズ 1** - [&#x200B; 環境の準備 &#x200B;](#prepare-your-environment)。 このフェーズでは、ユーザー権限を設定し、データインフラストラクチャを検証します。 これらの適切な権限とデータ構造がないと、残りの手順を完了することはできません。 使用される手順は次のとおりです。

1. **アクセス制御および権限を設定** して、Content Analyticsの設定と実装をサポートします。
1. **スキーマとデータセットの設定**：コンテンツ分析インサイトの収集元となるデータのモデル（スキーマ）と、そのデータ（データセット）を収集する場所を定義します。

**フェーズ 2** - [&#x200B; データ収集の設定 &#x200B;](#configure-data-collection)。 このフェーズでは、web サイトからコンテンツデータを取り込むパイプラインを作成します。 そのため、Content Analyticsは、訪問者がどのようなコンテンツにエンゲージするかを把握しています。

1. **データストリームの設定**：収集したデータをデータセットにルーティングする方法を設定します。
1. Web サイト上のデータレイヤーのデータに対してルールやデータ要素を設定し、設定されたデータストリームにデータが確実に送信されるようにするには **Web サイトタグを使用** します。
1. 実稼動環境に公開する前に、データ収集をテスト環境に **&#x200B;**&#x200B;デプロイ **および検証** します。

**フェーズ 3** - [&#x200B; レポートの設定 &#x200B;](#set-up-reporting)。 このフェーズでは、収集したデータをレポートで分析できるようにします。 そのため、Content Analyticsから取得したいコンテンツパフォーマンスに関するインサイトを、実際に取得できます。

1. データセットへの **接続の設定**。
1. **データビューの設定** をクリックして、指標とディメンションを定義します。
1. **Content Analyticsの設定と実装** を行います。
1. **プロジェクトを設定** して、Content Analyticsのレポートとビジュアライゼーションを作成します。


## 環境の準備

このフェーズでは、ユーザー権限を設定し、データインフラストラクチャを検証します。

### アクセス制御と権限の設定

この節では、製品に対して必要なアクセス権、製品プロファイルおよびスタンドアロン Content Analyticsの設定とセットアップに必要な権限について説明します。 Content Analyticsの機能にのみ関心がありますが、その機能を正しく動作させるには、他のExperience Platform製品に対するアクセス権と権限が必要です。

#### アクセス制御

アクセス制御は、Experience Platform製品へのアクセスを許可するかどうかを決定します。

製品または製品プロファイルの管理者としてユーザーを追加するには、システム管理者または製品管理者が必要です。 製品管理者は、管理対象の製品（プロファイル）の管理者としてのみユーザーを追加できます。システム管理者は、任意の製品（プロファイル）に製品管理者を追加できます。

>[!BEGINSHADEBOX]

デモビデオについては、![&#x200B; 製品プロファイルの VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [&#x200B; ユーザーの管理 &#x200B;](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"} を参照してください。


>[!ENDSHADEBOX]

スタンドアロンのContent Analyticsを使用するには、次の製品および製品プロファイルの製品管理者である必要があります。

* Adobe Experience Platform
   * AEP-Default-All-Users （実稼動サンドボックスにアクセスするためのデフォルトプロファイル）

* Adobe Experience Platform のデータ収集
   * 既定のデータ収集のすべてのアクセス

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics（カスタム）
   * Customer Journey Analytics（または他のデフォルトでプロビジョニングされた製品プロファイル）

製品管理者アクセスを定義するには、Admin Consoleを使用します。

1. [Admin Console](https://adminconsole.adobe.com) にアクセスします。
1. **[!UICONTROL 製品]** を選択します。
1. 特定の製品を選択します。
1. 「**[!UICONTROL 管理者]**」タブを選択します。
1. **[!UICONTROL 管理者を追加]** を選択して、製品に管理者を追加します。
1. **[!UICONTROL 製品管理者を追加]** ダイアログで、1 つ以上のメール名またはユーザー名を入力します。 「**[!UICONTROL 保存]**」を選択して保存します。


製品プロファイル管理者アクセスを定義するには、Admin Consoleを使用します。

1. [Admin Console](https://adminconsole.adobe.com) にアクセスします。
1. **[!UICONTROL 製品]** を選択します。
1. 特定の製品を選択します。 製品管理者アクセス権が既に付与されていることを確認します。
1. **[!UICONTROL 製品プロファイル]** を選択します。
1. 特定の製品プロファイルを選択します。
1. 「**[!UICONTROL 管理者]**」タブを選択します。
1. **[!UICONTROL 管理者を追加]** を選択して、製品プロファイルに管理者を追加します。
1. **[!UICONTROL 製品プロファイル管理者を追加]** ダイアログに、1 つ以上のメール名またはユーザー名を入力します。 「**[!UICONTROL 保存]**」を選択して保存します。


#### 権限

権限では、製品へのアクセス権を持った後に製品内で実行できる操作を定義します。

Experience Platformの権限を [!UICONTROL &#x200B; 権限 &#x200B;] インターフェイスで定義し、属性ベースのアクセス制御を使用します。 Customer Journey Analyticsの場合は、[!UICONTROL Admin Console] を通じて権限を定義します。

##### Experience Platform

Experience Platformの [!UICONTROL &#x200B; 権限 &#x200B;] インターフェイスは、ロールの定義に基づいています。 役割は、リソースベースの権限のコレクションです。 新しいプロビジョニング済み環境では、2 つのデフォルトの役割（**[!UICONTROL デフォルトの実稼動環境へのすべてのアクセス]** と **[!UICONTROL サンドボックス管理者]** を使用できます。

Content Analyticsの場合、次のリソースおよび関連する権限がこれらのロールに追加されているかどうかを確認する必要があります。

* デフォルトの実稼働 – すべてのアクセスの役割

   * データ収集
      * データストリームを表示
      * データストリームの管理

   * データ管理
      * データセットの表示
      * データセットの管理

   * データモデリング
      * スキーマの表示
      * スキーマの管理
      * ID メタデータの管理


* サンドボックス管理者の役割

   * サンドボックス
      * Prod
      * （Content Analyticsに使用するその他のサンドボックス）

   * サンドボックス管理
      * パッケージの管理
      * サンドボックスの管理
      * サンドボックスをリセット
      * サンドボックスの表示


権限インターフェイス内では、役割と関連する権限の両方を確認できます。 および役割に属するユーザー

1. 組織のExperience Platformにアクセスします。
1. ようこそ画面の **[!UICONTROL クイックアクセス]** で「**[!UICONTROL すべて表示]**」を選択します。
1. ![&#x200B; 権限 &#x200B;](/help/assets/icons/PinOn.svg) のピン留め **[!UICONTROL PinOn]** を有効にすると、後で使用できるように **[!UICONTROL 権限]** が **[!UICONTROL クイックアクセス]** 内で使用できるようになります。
1. **[!UICONTROL 権限]** を選択します。
1. ![&#x200B; ユーザー &#x200B;](/help/assets/icons/User.svg) **[!UICONTROL 役割]** を選択します。
1. 検証する特定の役割を選択します（例：**[!UICONTROL デフォルトの実稼働のすべてのアクセス]**）。 **[!UICONTROL すべて表示]** を選択すると、すべての権限が表示されます。
1. **[!UICONTROL 詳細]** 画面で、次の操作を行います。
   1. **[!UICONTROL 権限]** に一覧表示されている **[!UICONTROL リソース]** を確認します。
   1. 「**[!UICONTROL サンドボックス]**」でサンドボックス名を確認します。

   更新を行うには、「![&#x200B; 編集 &#x200B;](/help/assets/icons/Edit.svg)**[!UICONTROL 編集]**」を選択します。
   1. 不足しているリソースを追加するには、左側のパネルの **[!UICONTROL リソース]**/![Adobe Experience Platform](/help/assets/icons/Add.svg) から **[!UICONTROL リソース名]**&#x200B;**[!UICONTROL 追加]** を選択します。
   1. 不足している権限を追加するには、メインパネルで権限が欠落しているリソース内で ![ChevronDown](/help/assets/icons/ChevronDown.svg) を選択し、不足している権限を選択します。

      ![&#x200B; 権限インターフェイス &#x200B;](/help/content-analytics/assets/aep-permissions-ui.png)

   「**[!UICONTROL 保存]**」を選択して、更新を保存します。

1. ユーザーまたはユーザーグループ画面で、次の操作を行います。
   1. 個々のユーザーまたはユーザーのグループが、この役割に適切に含まれていることを確認します。
      1. Admin Consoleで定義した個々のユーザーを追加するには、「![&#x200B; ユーザー追加 &#x200B;](/help/assets/icons/UserAdd.svg) ユーザーにユーザーを追加」を選択します。
      1. Admin Consoleで定義したユーザーグループを追加するには、「ユーザーグループにグループを追加 ![&#x200B; 追加 &#x200B;](/help/assets/icons/Add.svg)」を選択します。


##### Customer Journey Analytics

Customer Journey Analyticsは、属性ベースのアクセス制御をサポートしていません。 権限を指定するには、Admin Consoleを使用します。

Content Analyticsの場合、次のCustomer Journey Analytics製品プロファイル権限が含まれているかどうかを確認する必要があります。

* データビュー
   * 使用可能なすべてのデータビュー。

* レポートツール
   * ガイド付き分析へのアクセス
   * 計算指標の作成
   * セグメントの作成
   * ラボのアクセス？
   * 注釈の作成
   * オーディエンスの作成
   * オーディエンスの表示
   * 監査ログへのアクセス
   * 他のユーザーとプロジェクトリンクを共有
   * 予測
   * AI アシスタント : 製品知識
   * Data Insights Agent
   * インテリジェントキャプション
   * データStorytelling?

* データビューツール
   * テーブル全体をエクスポートしますか？
   * CJA BI 拡張機能？

Customer Journey Analyticsに対するこれらの権限を確認し更新するには：

1. [Admin Console](https://adminconsole.adobe.com) にアクセスします。
1. **[!UICONTROL 製品]** を選択します。
1. **[!UICONTROL Customer Journey Analytics]** 商品を選択します。
1. **[!UICONTROL 製品プロファイル]** を選択します。
1. Customer Journey Analyticsで使用可能なデフォルトのプロビジョニングされた製品プロファイルを選択します。 例：**[!UICONTROL Customer Journey Analytics]**。
1. 製品プロファイル画面で、「**[!UICONTROL 権限]**」を選択します。
1. 任意の ![&#x200B; 編集 &#x200B;](/help/assets/icons/Edit.svg) ボタンを選択して、権限を編集します。 **[!UICONTROL Customer Journey Analyticsの権限を編集]** ダイアログで、次の手順を実行します。

   ![CJA権限 UI](../assets/cja-permissions-ui.png)

   1. **[!UICONTROL データビュー]** を選択し、「**[!UICONTROL 自動インクルード：オン]**」を有効にします。 この切り替えにより、すべてのデータビューが自動的に **[!UICONTROL 含まれる権限項目]** の一部になります。
   1. **[!UICONTROL レポートツール]** を選択し、上記のすべての権限が **[!UICONTROL 含まれる権限項目]** の一部であることを確認します。
   1. **[!UICONTROL データ表示ツール]** を選択し、上記のすべての権限が **[!UICONTROL 含まれる権限項目]** の一部であることを確認します。

   「**[!UICONTROL 保存]**」を選択します。


### スキーマとデータセットの設定

Content Analytics Insights に従って web サイトからデータを収集するには、まず収集するデータの種類を定義する必要があります。 また、そのデータの保存方法も説明します。 両方の概念については、[Adobe Experience Platform Web SDKを使用したデータの取り込み &#x200B;](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) クイックスタートガイドの [&#x200B; スキーマとデータセットの設定 &#x200B;](/help/data-ingestion/aepwebsdk.md) を参照してください。


## データ収集の設定

このフェーズでは、web サイトからコンテンツデータを取り込むパイプラインを作成します。

### データストリームの設定

収集するデータとそのデータの保存方法を定義しました。 次の手順では、web サイトから収集されたデータが確実にデータセットにルーティングされるようにします。 データストリームの設定と設定が必要です。詳しくは、『 [Adobe Experience Platform Web SDKを使用したデータの取り込み &#x200B;](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) クイックスタートガイド [&#x200B; のデータストリームの設定 &#x200B;](/help/data-ingestion/aepwebsdk.md) を参照してください。


### タグの使用

収集するデータ（スキーマ）、そのデータ（データセット）の保存方法、web サイトから収集したデータをデータセット（データストリーム）にルーティングする方法を定義しました。 次の手順として、web サイトにタグ付けし、web サイト上のデータレイヤーのデータに対してルールとデータ要素を設定する必要があります。 Web サイトにタグを付けると、設定済みのデータストリームにデータが確実に送信されます。 タグを使用して web サイトにタグを付ける方法については、[Adobe Experience Platform Web SDKを使用したデータの取り込み &#x200B;](/help/data-ingestion/aepwebsdk.md#use-tags) クイックスタートガイドの [&#x200B; タグの使用 &#x200B;](/help/data-ingestion/aepwebsdk.md) を参照してください。


### デプロイと検証

次に、web サイトの開発バージョンで、`<head>` タグをデプロイできます。デプロイすると、web サイトはAdobe Experience Platformへのデータの収集を開始します。 そのデータは、Content Analyticsの対象となります。

実装を検証し、必要に応じて修正したら、タグの公開ワークフロー機能を使用して、ステージング環境と実稼動環境にデプロイします


## レポートの設定

このフェーズでは、収集したデータをレポートで分析できるようにします。

### データセットへの接続の設定

収集したデータに関するレポートを作成し、そのデータをContent Analyticsに設定するには、Customer Journey Analyticsで接続を設定する必要があります。 接続は、収集されたデータを含むデータセットに接続します。 接続の設定方法については、[Adobe Experience Platform Web SDKを使用したデータの取り込み &#x200B;](../../data-ingestion/aepwebsdk.md#set-up-a-connection) クイックスタートガイドの [&#x200B; 接続の設定 &#x200B;](/help/data-ingestion/aepwebsdk.md) を参照してください。


### データ表示の設定

Content Analyticsを設定する前の最後の手順は、データビューを定義することです。 データ表示は、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。データビューを使用すると、Customer Journey Analyticsが接続されている 1 つ以上のデータセットのデータから指標とディメンションを定義できます。 データビューの設定方法については、『 [Adobe Experience Platform Web SDKを使用したデータの取り込み &#x200B;](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) クイックスタートガイドの [&#x200B; データビューの設定 &#x200B;](/help/data-ingestion/aepwebsdk.md) を参照してください。


### Content Analytics の設定

これで、Content Analyticsを設定するためのすべての機能が用意できました。

#### ガイド付き設定

[&#x200B; ガイド付き設定ウィザード &#x200B;](guided.md) を使用し、[&#x200B; データビューのセットアップ &#x200B;](#set-up-a-data-view) 手順の一部として作成したデータビューを選択します。 これにより、web サイトから収集したデータに基づいて、Content Analyticsが設定および実装されます。

ガイド付き設定ウィザードでは、次のようなContent Analytics固有のオブジェクトも設定されます。

* Content Analytics イベント用に自動的に設定される **データセット**。 このデータセットでは、既に作成されて使用可能な特定のContent Analytics スキーマを使用します。
* **データストリーム**:Content Analytics イベントをContent Analytics データセットにストリーミングするために自動的に設定されます。
* **タグプロパティ**：自動的に設定され、Content Analytics拡張機能で設定されます。 このタグプロパティにより、web サイトからContent Analytics データがContent Analytics データストリームとContent Analytics データセットに送信されるようにします。

  >[!IMPORTANT]
  >
  >ウィザードの [&#x200B; データ収集 &#x200B;](guided.md#new-configuration-1) 手順の一部として、新しいタグプロパティを作成するオプションを選択していることを確認してください。
  >


#### 手動設定

Web サイトにContent Analyticsを実装するには、Content Analytics タグプロパティを [&#x200B; 手動で &#x200B;](manual.md) 公開する必要があります。


### プロジェクトの設定

Customer Journey Analyticsでプロジェクトを設定して、[Content Analyticsのレポートとビジュアライゼーション &#x200B;](/help/content-analytics/report/report.md) を作成します。 または、[Content Analytics テンプレート &#x200B;](/help/content-analytics/report/report.md#template) を使用して開始することもできます。

