---
title: Content Analyticsの設定（スタンドアロン）
description: Content Analytics（スタンドアロン）の設定に必要な手順について説明します
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 81e7488a91a99456cd950d367d9ff16ec7c1cb5a
workflow-type: tm+mt
source-wordcount: '1810'
ht-degree: 8%

---


# スタンドアロン設定

>[!IMPORTANT]
>
>この設定ガイドは、スタンドアロンのAdobe Content Analytics パッケージのライセンスを取得したお客様向けです。 このガイドは、Customer Journey AnalyticsまたはContent Analyticsの機能を超えるその他のExperience Platform アプリケーションを使用していないか、使用する予定がないことを前提としています。 既存のContent Analytics実装の一部としてContent Analyticsを設定および使用する場合は、[Customer Journey Analyticsの設定 ](configuration.md) を参照してください。
>

この設定ガイドを使用すると、動作する **スタンドアロン** Content Analytics実装を必要とするすべてのアプリケーションの管理、設定およびセットアップを行うことができます。 これらの手順は、次の要素で構成されます。

1. **アクセス制御および権限を設定** して、Content Analyticsの設定と実装をサポートします。
1. **スキーマとデータセットの設定**：コンテンツ分析インサイトの収集元となるデータのモデル（スキーマ）と、そのデータ（データセット）を収集する場所を定義します。
1. **データストリームの設定**：収集したデータをデータセットにルーティングする方法を設定します。
1. Web サイト上のデータレイヤーのデータに対してルールやデータ要素を設定し、設定されたデータストリームにデータが確実に送信されるようにするには **Web サイトタグを使用** します。
1. 実稼動環境に公開する前に、データ収集をテスト環境に **** デプロイ **および検証** します。
1. データセットへの **接続の設定**。
1. **データビューの設定** をクリックして、指標とディメンションを定義します。
1. **Content Analyticsの設定と実装** を行います。
1. **プロジェクトを設定** して、Content Analyticsのレポートとビジュアライゼーションを作成します。

## アクセス制御と権限の設定

この節では、製品に対して必要なアクセス権、製品プロファイルおよびスタンドアロン Content Analyticsの設定とセットアップに必要な権限について説明します。 Content Analyticsの機能にのみ関心がありますが、その機能を正しく動作させるには、他のExperience Platform製品に対するアクセス権と権限が必要です。

### アクセス制御

アクセス制御は、Experience Platform製品へのアクセスを許可するかどうかを決定します。

製品または製品プロファイルの管理者としてユーザーを追加するには、システム管理者または製品管理者が必要です。 製品管理者は、管理対象の製品（プロファイル）の管理者としてのみユーザーを追加できます。システム管理者は、任意の製品（プロファイル）に製品管理者を追加できます。

>[!BEGINSHADEBOX]

デモビデオについては、![ 製品プロファイルの VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ ユーザーの管理 ](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"} を参照してください。


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


### 権限

権限では、製品へのアクセス権を持った後に製品内で実行できる操作を定義します。

Experience Platformの権限を [!UICONTROL  権限 ] インターフェイスで定義し、属性ベースのアクセス制御を使用します。 Customer Journey Analyticsの場合は、[!UICONTROL Admin Console] を通じて権限を定義します。

#### Experience Platform

Experience Platformの [!UICONTROL  権限 ] インターフェイスは、ロールの定義に基づいています。 役割は、リソースベースの権限のコレクションです。 新しいプロビジョニング済み環境では、2 つのデフォルトの役割（**[!UICONTROL デフォルトの実稼動環境へのすべてのアクセス]** と **[!UICONTROL サンドボックス管理者]** を使用できます。

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
1. ![ 権限 ](/help/assets/icons/PinOn.svg) のピン留め **[!UICONTROL PinOn]** を有効にすると、後で使用できるように **[!UICONTROL 権限]** が **[!UICONTROL クイックアクセス]** 内で使用できるようになります。
1. **[!UICONTROL 権限]** を選択します。
1. ![ ユーザー ](/help/assets/icons/User.svg) **[!UICONTROL 役割]** を選択します。
1. 検証する特定の役割を選択します（例：**[!UICONTROL デフォルトの実稼働のすべてのアクセス]**）。 **[!UICONTROL すべて表示]** を選択すると、すべての権限が表示されます。
1. **[!UICONTROL 詳細]** 画面で、次の操作を行います。
   1. **[!UICONTROL 権限]** に一覧表示されている **[!UICONTROL リソース]** を確認します。
   1. 「**[!UICONTROL サンドボックス]**」でサンドボックス名を確認します。

   更新を行うには、「![ 編集 ](/help/assets/icons/Edit.svg)**[!UICONTROL 編集]**」を選択します。
   1. 不足しているリソースを追加するには、左側のパネルの **[!UICONTROL リソース]**/![Adobe Experience Platform](/help/assets/icons/Add.svg) から **[!UICONTROL リソース名]****[!UICONTROL 追加]** を選択します。
   1. 不足している権限を追加するには、メインパネルで権限が欠落しているリソース内で ![ChevronDown](/help/assets/icons/ChevronDown.svg) を選択し、不足している権限を選択します。

      ![ 権限インターフェイス ](/help/content-analytics/assets/aep-permissions-ui.png)

   「**[!UICONTROL 保存]**」を選択して、更新を保存します。

1. ユーザーまたはユーザーグループ画面で、次の操作を行います。
   1. 個々のユーザーまたはユーザーのグループが、この役割に適切に含まれていることを確認します。
      1. Admin Consoleで定義した個々のユーザーを追加するには、「![ ユーザー追加 ](/help/assets/icons/UserAdd.svg) ユーザーにユーザーを追加」を選択します。
      1. Admin Consoleで定義したユーザーグループを追加するには、「ユーザーグループにグループを追加 ![ 追加 ](/help/assets/icons/Add.svg)」を選択します。


#### Customer Journey Analytics

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
   * Data Insights エージェント
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
1. 任意の ![ 編集 ](/help/assets/icons/Edit.svg) ボタンを選択して、権限を編集します。 **[!UICONTROL Customer Journey Analyticsの権限を編集]** ダイアログで、次の手順を実行します。

   ![CJA権限 UI](../assets/cja-permissions-ui.png)

   1. **[!UICONTROL データビュー]** を選択し、「**[!UICONTROL 自動インクルード：オン]**」を有効にします。 この切り替えにより、すべてのデータビューが自動的に **[!UICONTROL 含まれる権限項目]** の一部になります。
   1. **[!UICONTROL レポートツール]** を選択し、上記のすべての権限が **[!UICONTROL 含まれる権限項目]** の一部であることを確認します。
   1. **[!UICONTROL データ表示ツール]** を選択し、上記のすべての権限が **[!UICONTROL 含まれる権限項目]** の一部であることを確認します。

   「**[!UICONTROL 保存]**」を選択します。


## スキーマとデータセットの設定

Content Analytics Insights に従って web サイトからデータを収集するには、まず収集するデータの種類を定義する必要があります。 また、そのデータの保存方法も説明します。 両方の概念については、[Adobe Experience Platform Web SDKを使用したデータの取り込み ](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) クイックスタートガイドの [ スキーマとデータセットの設定 ](/help/data-ingestion/aepwebsdk.md) を参照してください。


## データストリームの設定

収集するデータとそのデータの保存方法を定義しました。 次の手順では、web サイトから収集されたデータが確実にデータセットにルーティングされるようにします。 データストリームの設定と設定が必要です。詳しくは、『 [Adobe Experience Platform Web SDKを使用したデータの取り込み ](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) クイックスタートガイド [ のデータストリームの設定 ](/help/data-ingestion/aepwebsdk.md) を参照してください。


## タグの使用

収集するデータ（スキーマ）、そのデータ（データセット）の保存方法、web サイトから収集したデータをデータセット（データストリーム）にルーティングする方法を定義しました。 次の手順として、web サイトにタグ付けし、web サイト上のデータレイヤーのデータに対してルールとデータ要素を設定する必要があります。 Web サイトにタグを付けると、設定済みのデータストリームにデータが確実に送信されます。 タグを使用して web サイトにタグを付ける方法については、[Adobe Experience Platform Web SDKを使用したデータの取り込み ](/help/data-ingestion/aepwebsdk.md#use-tags) クイックスタートガイドの [ タグの使用 ](/help/data-ingestion/aepwebsdk.md) を参照してください。


## デプロイと検証

次に、web サイトの開発バージョンで、`<head>` タグをデプロイできます。デプロイすると、web サイトはAdobe Experience Platformへのデータの収集を開始します。 そのデータは、Content Analyticsの対象となります。

実装を検証し、必要に応じて修正したら、タグの公開ワークフロー機能を使用して、ステージング環境と実稼動環境にデプロイします


## データセットへの接続を設定します。

収集したデータに関するレポートを作成し、そのデータをContent Analyticsに設定するには、Customer Journey Analyticsで接続を設定する必要があります。 接続は、収集されたデータを含むデータセットに接続します。 接続の設定方法については、[Adobe Experience Platform Web SDKを使用したデータの取り込み ](../../data-ingestion/aepwebsdk.md#set-up-a-connection) クイックスタートガイドの [ 接続の設定 ](/help/data-ingestion/aepwebsdk.md) を参照してください。


## データ表示の設定

Content Analyticsを設定する前の最後の手順は、データビューを定義することです。 データ表示は、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。データビューを使用すると、Customer Journey Analyticsが接続されている 1 つ以上のデータセットのデータから指標とディメンションを定義できます。 データビューの設定方法については、『 [Adobe Experience Platform Web SDKを使用したデータの取り込み ](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) クイックスタートガイドの [ データビューの設定 ](/help/data-ingestion/aepwebsdk.md) を参照してください。


## Content Analytics の設定

これで、Content Analyticsを設定するためのすべての機能が用意できました。

### ガイド付き設定

[ ガイド付き設定ウィザード ](guided.md) を使用し、[ データビューのセットアップ ](#set-up-a-data-view) 手順の一部として作成したデータビューを選択します。 これにより、web サイトから収集したデータに基づいて、Content Analyticsが設定および実装されます。

ガイド付き設定ウィザードでは、次のようなContent Analytics固有のオブジェクトも設定されます。

* Content Analytics イベント用に自動的に設定される **データセット**。 このデータセットでは、既に作成されて使用可能な特定のContent Analytics スキーマを使用します。
* **データストリーム**:Content Analytics イベントをContent Analytics データセットにストリーミングするために自動的に設定されます。
* **タグプロパティ**：自動的に設定され、Content Analytics拡張機能で設定されます。 このタグプロパティにより、web サイトからContent Analytics データがContent Analytics データストリームとContent Analytics データセットに送信されるようにします。

  >[!IMPORTANT]
  >
  >ウィザードの [ データ収集 ](guided.md#new-configuration-1) 手順の一部として、新しいタグプロパティを作成するオプションを選択していることを確認してください。
  >



### 手動設定

Web サイトにContent Analyticsを実装するには、Content Analytics タグプロパティを [ 手動で ](manual.md) 公開する必要があります。


## プロジェクトの設定

Customer Journey Analyticsでプロジェクトを設定して、[Content Analyticsのレポートとビジュアライゼーション ](/help/content-analytics/report/report.md) を作成します。 または、[Content Analytics テンプレート ](/help/content-analytics/report/report.md#template) を使用して開始することもできます。






