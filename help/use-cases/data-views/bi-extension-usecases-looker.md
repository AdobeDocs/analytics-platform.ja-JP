---
title: Customer Journey Analyticsの BI 拡張機能の使用例
description: Customer Journey Analyticsの様々な BI ツールで BI 拡張機能を使用する方法を示す複数の使用例
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
exl-id: 3d1e3b79-402d-44ff-86b3-be9fd5494e19
source-git-commit: 739d92a3e9b623e3f04bf28de8213f1c76d5036b
workflow-type: tm+mt
source-wordcount: '13066'
ht-degree: 2%

---

# BI 拡張機能のユースケース

この記事では、Customer Journey Analytics BI 拡張機能を使用して様々なユースケースを達成する方法について説明します。 各ユースケースでは、Customer Journey Analytics機能を説明し、その後でサポートされている各 BI ツールの詳細を説明します。

* **Power BI デスクトップ**。 使用されるバージョンは 2.137.1102.0 64 ビット（2024 年 10 月）です。
* **Tableau Desktop**。 使用されるバージョンは 2024.1.5 （20241.24.0705.0334） 64 ビットです。
* **Looker**。 オンラインバージョン 25.0.23、[looker.com](https://looker.com){target="_blank"} から入手可能

次のユースケースについて説明します。

* **接続**
   * [データビューの接続とリスト表示](#connect-and-validate)

* **報告及び分析**
   * [毎日のトレンド](#daily-trend)
   * [毎時トレンド](#hourly-trend)
   * [月間トレンド](#monthly-trend)
   * [ランク付けされた単一ディメンション](#single-dimension-ranked)
   * [複数のディメンションのランク](#multiple-dimension-ranked)
   * [個別ディメンション値のカウント](#count-distinct-dimension-values)
   * [日付範囲名を使用してフィルター](#use-date-range-names-to-filter)
   * [フィルター名を使用したフィルタリング](#use-filter-names-to-filter)
   * [ディメンション値を使用したフィルタリング](#use-dimension-values-to-filter)
   * [並べ替え](#sort)
   * [制限](#limits)

* **理解**

   * [Transformations](#transformations)
   * [ビジュアライゼーション](#visualizations)
   * [注意事項](#caveats)

**connect** のユースケースでは、Customer Journey Analytics BI 拡張機能を使用して BI ツールを接続する方法に重点を置いています。

**レポートと分析** のユースケースでは、現在サポートされている BI ツールで同様のCustomer Journey Analytics ビジュアライゼーションを実行する方法を示しています。

**理解** ユースケースでは、次の項目について詳しく説明します。

* BI ツールを使用してレポートおよび分析を行う場合に発生する変換。
* ビジュアライゼーションのCustomer Journey Analytics ツールと BI ツールの類似点と相違点。
* 注意が必要な各 BI ツールの注意事項。


## 接続と検証

このユースケースでは、BI ツールからCustomer Journey Analyticsへの接続を設定し、使用可能なデータビューを一覧表示して、使用するデータビューを選択します。

+++ Customer Journey Analytics

この手順では、次のオブジェクトを持つ環境例を参照しています。

* データビュー：**[!UICONTROL C&amp;C - データビュー]** ??。
* ディメンション：**[!UICONTROL 製品名]** ?？および **[!UICONTROL 製品カテゴリ]** ??。
* 指標：**[!UICONTROL 購入売上高]**?？および **[!UICONTROL 購入]**??。
* フィルター：**[!UICONTROL 釣り製品]** ??。

![Customer Journey Analytics ベースのセットアップ ](assets/cja-base.png){zoomable="yes"}

ユースケースを確認したら、これらのサンプルオブジェクトを特定の環境に適したオブジェクトに置き換えます。

+++

+++ BI ツール

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. **[!UICONTROL データベース]** ドロップダウンメニューから「`prod:cja`」を選択します。

      ![ クエリサービス資格情報 ](assets/queryservice-credentials.png){zoomable="yes"}

1. Power BI Desktop を起動します。
   1. メインインターフェイスから、「**[!UICONTROL 他のソースからデータを取得]**」を選択します。
   1. **[!UICONTROL データを取得]** ダイアログで、次の手順を実行します。
      ![PowerBI PostgreSQL データベース ](assets/powerbi-postgresql.png){zoomable="yes"}
      1. **[!UICONTROL PostgreSQL データベース]** を検索して選択します。
      1. **[!UICONTROL 接続]** を選択します。
   1. **[!UICONTROL PostgreSQL データベース]** ダイアログで、次の手順を実行します。
      ![PowerBI デスクトップサーバーとデータベースの設定 ](assets/powerbi-serverdatabase.png){zoomable="yes"}
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルの **[!UICONTROL Host]** と **[!UICONTROL Port]** の値をコピーして貼り付け、**[!UICONTROL Server]** の値として `:` で区切ります。 例：`examplecompany.platform-query.adobe.io:80`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルから ]**Database]** 値をコピー&amp;ペーストします。 貼り付ける値に `?FLATTEN` を追加します。 例：`prod:cja?FLATTEN`。
      1. **[!UICONTROL Data connectivity mode]** として **[!UICONTROL DirectQuery]** を選択します。
      1. **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL PostgreSQL データベース]** - **[!UICONTROL データベース]** ダイアログで、
      ![PowerBI デスクトップユーザーとパスワード ](assets/powerbi-userpassword.png){zoomable="yes"}
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、**[!UICONTROL ユーザー名]** および **[!UICONTROL パスワード]** フィールドのExperience Platform **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL ユーザー名]** および **[!UICONTROL パスワード]** の値をコピーします。 [ 有効期限のない認証情報 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) を使用している場合は、有効期限のない認証情報のパスワードを使用します。
      1. **[!UICONTROL これらの設定を適用するレベルを選択]** のドロップダウンメニューが、前に定義した **[!UICONTROL サーバー]** に設定されていることを確認します。
      1. **[!UICONTROL 接続]** を選択します。
   1. **[!UICONTROL ナビゲーター]** ダイアログで、データビューが取得されます。 この取得には時間がかかる場合があります。 取得すると、Power BI Desktop に以下が表示されます。
      ![Power BI Destkop 読み込みデータ ](assets/powerbi-navigator-load.png){zoomable="yes"}
      1. 左パネルのリストから **[!UICONTROL public.cc_data_view]** を選択します。
      1. 次の 2 つのオプションがあります。
         1. **[!UICONTROL 読み込み]** を選択して続行し、設定を完了します。
         1. **[!UICONTROL データを変換]** を選択します。 オプションで設定の一部として変換を適用できるダイアログが表示されます。
            ![Power BI デスクトップ変換データ ](assets/powerbi-transform-data.png){zoomable="yes"}
            * **[!UICONTROL 閉じて適用]** を選択します。
   1. しばらくすると、**[!UICONTROL public.cc_data_view]** が **[!UICONTROL Data]** ペインに表示されます。 ![ChevronRight](/help/assets/icons/ChevronRight.svg) を選択して、ディメンションと指標を表示します。
      ![Power BI Destkop サーバーのデータが読み込まれました ](assets/powerbi-navigator-loaded.png){zoomable="yes"}


### FLATTEN か NOT か

Power BI Desktop では、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプションは次のとおりです。** |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CloseCircle](/help/assets/icons/CloseCircle.svg) | Power BI デスクトップに「**[!UICONTROL 指定された資格情報では認証できませんでした。 もう一度やり直してください。]** |

### 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials)
* [Power BIをクエリサービスに接続 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi)。




>[!TAB Tableau Desktop]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. **[!UICONTROL データベース]** ドロップダウンメニューから「`prod:cja`」を選択します。

      ![ クエリサービス資格情報 ](assets/queryservice-credentials.png){zoomable="yes"}

1. Tableau の起動
   1. **[!UICONTROL To a Server]** の下の左パネルから「**[!UICONTROL PostgreSQL]**」を選択します。 使用できない場合は、「**[!UICONTROL その他…]**」を選択し、「**[!UICONTROL インストールされているコネクタ**[!UICONTROL 」から「]**PostgreSQL]**」を選択します。
      ![Tableau コネクタ ](assets/tableau-connectors.png){zoomable="yes"}
   1. **[!UICONTROL PostgreSQL]** ダイアログの **[!UICONTROL 一般]** タブで、次の操作を行います。
      ![Tableau へのログインダイアログ ](assets/tableau-signin.png){zoomable="yes"}
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、**[!UICONTROL ホスト]** をExperience Platform **[!UICONTROL クエリ]** **[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL サーバー]** にコピー&amp;ペーストします。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルから ]**Port]** に **[!UICONTROL Port]** をコピー&amp;ペーストします。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルから ]**データベース]** に **[!UICONTROL データベース]** をコピー&amp;ペーストします。 貼り付ける値に `%3FFLATTEN` を追加します。 例：`prod:cja%3FFLATTEN`。
      1. **[!UICONTROL 認証]** ドロップダウンメニューから **[!UICONTROL ユーザー名とパスワード]** を選択します。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、**[!UICONTROL ユーザー名]** をExperience Platform **[!UICONTROL クエリ]** **[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL ユーザー名]** にコピー&amp;ペーストします。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、**[!UICONTROL パスワード]** をExperience Platform **[!UICONTROL クエリ]** **[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL パスワード]** にコピー&amp;ペーストします。 [ 有効期限のない認証情報 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) を使用している場合は、有効期限のない認証情報のパスワードを使用します。
      1. 「**[!UICONTROL SSL が必要]**」が選択されていることを確認します。
      1. 「**[!UICONTROL ログイン]**」を選択します。

      Tableau Desktop が接続を検証している間、**[!UICONTROL 要求の進行状況]** ダイアログが表示されます。
   1. メインウィンドウの左側のペインには、「**[!UICONTROL データSource]**」ページが表示されます。
      * **[!UICONTROL 接続]** の下の接続名。
      * **[!UICONTROL Database]** の下のデータベースの名前。
      * **[!UICONTROL Table]** の下のテーブルのリスト。
        ![Tableau Connected](assets/tableau-connected.png){zoomable="yes"}
      1. **[!UICONTROL cc_data_view]** エントリをドラッグし、「**[!UICONTROL テーブルをドラッグ]**」と表示されるメインビューにここにエントリをドロップします。
   1. メインウィンドウに、**[!UICONTROL cc_data_view]** データビューの詳細が表示されます。
      ![Tableau Connected](assets/tableau-validation.png){zoomable="yes"}

### FLATTEN か NOT か

Tableau Desktop は、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプション**。 `%3FFLATTEN` は URL エンコードされたバージョンの `?FLATTEN` であることに注意してください。 |

### 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials)
* [Tableau Desktop をクエリサービスに接続します ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau)。


>[!TAB Looker]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. **[!UICONTROL データベース]** ドロップダウンメニューから「`prod:cja`」を選択します。

      ![ クエリサービス資格情報 ](assets/queryservice-credentials.png){zoomable="yes"}

1. Looker へのログイン

   1. 左パネルから **[!UICONTROL 管理者]** を選択します。
   1. **[!UICONTROL 接続]** を選択します。
   1. **[!UICONTROL 接続を追加]** を選択します。
   1. **[!UICONTROL データベースを Looker に接続画面]** で確認します。

      ![Looker データベースへの接続 ](assets/looker-connect.png){zoomable="yes"}

      1. 接続の **[!UICONTROL 名前]** を入力（例：`Example Looker Connection`）
      1. **[!UICONTROL 接続範囲]** として「すべてのプロジェクト **[!UICONTROL が選択されていることを確認]** ます。
      1. ダイアレクトとして **[!UICONTROL PostgreSQL 9.5 以上]** を選択します。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルの ]**ホスト]** 値をコピーし、**[!UICONTROL ホスト]** の値として貼り付けます。 例：`examplecompany.platform-query.adobe.io`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルの ]**Port]** 値をコピーして **[!UICONTROL Port]** に貼り付けます。 例：`80`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルの ]**データベース]** 値をコピーして **[!UICONTROL データベース]** に貼り付けます。 貼り付ける値に `?FLATTEN` を追加します。 例：`prod:cja?FLATTEN`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platform **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルの ]**ユーザー名]** 値をコピーして **[!UICONTROL ユーザー名]** に貼り付けます。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platform **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報**[!UICONTROL  パネルの ]**パスワード]** 値をコピーして **[!UICONTROL パスワード]** に貼り付けます。
      1. **[!UICONTROL オプション設定]** で **[!UICONTROL すべて展開]** を選択します。
      1. ノードごとの **[!UICONTROL 最大接続数]** を `5` に設定します。
      1. **[!UICONTROL SSL]** が有効になっていることを確認します。
      1. 「**[!UICONTROL テスト]**」を選択して、接続をテストします。 画面上部にバナーと「**[!UICONTROL Success, can connect JDBC string: jdbc:postgresql://examplecompany.platform-query-stage.adobe.io:80/prod:cja?FLATTEN?tcpKeepAlive=true&amp;ssl=true&amp;sslfactory=org.postgresql.ssl.NonValidatingFactory&amp;sslmode=prefer]**」のようなメッセージが表示されます。
      1. 「**[!UICONTROL 接続]**」を選択し、接続を確立して保存します。
   1. **[!UICONTROL Connections]** インターフェイスに新しい接続が表示されます。
   1. **[!UICONTROL 管理者]** から **←** を選択して、左側のパネルのメインナビゲーションに移動します。
   1. **[!UICONTROL 開発]** を選択します。
   1. **[!UICONTROL プロジェクト]** を選択します。
   1. LookML プロジェクトで **[!UICONTROL 新規モデル]** を選択します。
   1. を設定して、他のユーザーに影響を与えないようにします。 プロンプトが表示されたら、「開発モードに入る」を選択します。
   1. **[!UICONTROL モデルを作成]** エクスペリエンスで、次の操作を行います。
      1. **[!UICONTROL ➊データベース接続を選択し]** す。
         1. **[!UICONTROL データベース接続を選択]** でデータベース接続を選択します。 例：**[!UICONTROL example_looker_connection]**。
         1. **[!UICONTROL このモデルの新しい LookML プロジェクトを作成]** でプロジェクトに名前を付けます。 （`example: example_looker_project` 用）。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. **[!UICONTROL ➋テーブルを選択します]**。
         1. **[!UICONTROL 公開]** を選択し、Customer Journey Analytics データビューが選択されていることを確認します。 例：![SelectBox](/help/assets/icons/SelectBox.svg)**[!UICONTROL cc_data_view]**。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. **[!UICONTROL で➌プライマリキーを選択し]** す。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. **[!UICONTROL ➍作成する探索を選択します]**
         1. 必ずビューを選択してください。 例：**[!UICONTROL cc_data_view.view]**。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. **[!UICONTROL ➎モデル名を入力し]** す。
         1. モデルに名前を付けます。 例：`example_looker_model`。
      1. 「**[!UICONTROL データを入力して調査]**」を選択します。

   Looker の **[!UICONTROL 参照]** インターフェイスにリダイレクトされ、データを参照する準備が整います。



### FLATTEN か NOT か

Looker では、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプション**。 `%3FFLATTEN` は URL エンコードされたバージョンの `?FLATTEN` であることに注意してください。 |

### 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials)

>[!ENDTABS]

+++


## 毎日のトレンド

このユースケースでは、2023 年 1 月 1 日から 2023 年 1 月 31 日までの発生件数（イベント）の毎日のトレンドを表示するテーブルとシンプルな線のビジュアライゼーションを表示します。

+++ Customer Journey Analytics

ユースケースの例 **[!UICONTROL 毎日のトレンド]** パネルを次に示します。

![Customer Journey Analytics毎日のトレンドパネル ](assets/cja_daily_trend.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールの [ 接続に成功した ](#connect-and-validate) 検証され、データビューのリスト作成と使用ができることを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterangeday]** を選択します。
   1. 「**[!UICONTROL ∑回数]**」を選択します。

   当月の発生件数を示すテーブルが表示されます。 視認性を高めるには、ビジュアライゼーションを拡大します。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterangeday is （All）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. フィルターを定義して **[!UICONTROL 値が]** 次の値の場合に項目を表示 **** `1/1/2023` **[!UICONTROL および]** **[!UICONTROL 次の値の前]** `2/1/2023.` を設定します。カレンダーアイコンを使用して、日付を選択して選択できます。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

   適用した **[!UICONTROL daterangeday]** フィルターで更新されたテーブルが表示されます。

1. **[!UICONTROL ビジュアライゼーション]** パネルで、**[!UICONTROL 折れ線グラフ]** ビジュアライゼーションを選択します。

   折れ線グラフビジュアライゼーションは、テーブルと同じデータを使用しながら、テーブルを置き換えます。 Power BI デスクトップは次のようになります。

   ![Power BI Desktop ユースケース 2 日付範囲フィルター ](assets/uc2-pbi-daterange.png){zoomable="yes"}

1. 折れ線グラフのビジュアライゼーションで：

   1. ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
   1. コンテキストメニューから「**[!UICONTROL テーブルとして表示]**」を選択します。

   メインビューが更新され、折れ線グラフのビジュアライゼーションとテーブルの両方が表示されます。 Power BI デスクトップは次のようになります。

   ![Power BI デスクトップのユースケース 2 最終的な毎日のトレンドビジュアライゼーション ](assets/uc2-pbi-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」ビューから切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付範囲]** を選択し、`01/01/2023` ～ `01/02/2023` の期間を指定します。

      ![Tableau Desktop フィルター ](assets/uc2-tableau-filter.png){zoomable="yes"}

   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterangeday]** をドラッグ&amp;ドロップし、**[!UICONTROL 列]** の横のフィールドにエントリをドロップします。
      * **[!UICONTROL Daterangeday]** ドロップダウンメニューから **[!UICONTROL Day]** を選択し、値が **[!UICONTROL DAY （Daterangeday）]** に更新されます。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル（*メジャー名*）]** リストから **[!UICONTROL 発生件数]** をドラッグ&amp;ドロップし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。 値は自動的に **[!UICONTROL SUM （発生件数）]** に変換されます。
   1. **[!UICONTROL 標準]** を、ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop グラフ ](assets/uc2-tableau-graph.png){zoomable="yes"}

1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 複製]** を選択し、2 番目のシートを作成します。
1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Graph` に変更します。
1. **[!UICONTROL シート 1 （2）]** タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Data` に変更します。
1. **[!UICONTROL データ]** シートが選択されていることを確認します。 **[!UICONTROL データ]** 表示で、次の操作を行います。
   1. 右上の **[!UICONTROL 表示]** を選択し、**[!UICONTROL テキストテーブル]** （左上のビジュアライゼーション）を選択して、データビューのコンテンツをテーブルに変更します。
   1. ツールバーの **[!UICONTROL 行と列を入れ替える]** を選択します。
   1. **[!UICONTROL 標準]** を、ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop データ ](assets/uc2-tableau-data.png){zoomable="yes"}

1. 「**[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL Sheets]** シェルフから **[!UICONTROL Graph]** シートを **[!UICONTROL Dashboard 1]** ビュー（「シートをここにドロップ *」と表示されているビュー* にドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL グラフ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビューで **[!UICONTROL データ]** シートを選択し、**[!UICONTROL ビュー全体]** を **[!UICONTROL 固定幅]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop ダッシュボード 1](assets/uc2-tableau-dashboard.png){zoomable="yes"}


>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/02/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL Cc データビュー]**」セクションから、
   1. 「**[!UICONTROL ‣Daterange Date]**」を選択し、「**[!UICONTROL DIMENSIONS]**」のリストから「**[!UICONTROL Date]**」を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択して、折れ線グラフのビジュアライゼーションを表示します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker 結果日別トレンド ](assets/uc2-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++


## 毎時トレンド

このユースケースでは、2023 年 1 月 1 日の発生件数（イベント）の 1 時間ごとのトレンドを表示するテーブルと単純な線のビジュアライゼーションを表示します。

+++ Customer Journey Analytics

ユースケースの例 **[!UICONTROL 時間別トレンド]** パネル：

![Customer Journey Analyticsの時間別トレンドビジュアライゼーション ](assets/cja_hourly_trend.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BIは日時フィールドの処理方法を **認識** ていないので、**[!UICONTROL daterangehour]** や **[!UICONTROL daterangeminute]** などのディメンションはサポートされていません。

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付範囲]** を選択し、`01/01/2023` ～ `02/01/2023` の期間を指定します。

      ![Tableau Desktop フィルター ](assets/uc3-tableau-filter.png){zoomable="yes"}

   1. **[!UICONTROL データ]** ペインの「**[!UICONTROL テーブル]**」リストから **[!UICONTROL Daterangehour]** をドラッグ&amp;ドロップし、「**[!UICONTROL 列]**」の横のフィールドにエントリをドロップします。
      * **[!UICONTROL Daterangeday]** ドロップダウンメニューから **[!UICONTROL More]** > **[!UICONTROL Hours]** を選択し、値が **[!UICONTROL HOUR （Daterangeday）]** に更新されるようにします。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル（*メジャー名*）]** リストから **[!UICONTROL 発生件数]** をドラッグ&amp;ドロップし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。 値は自動的に **[!UICONTROL SUM （発生件数）]** に変換されます。
   1. **[!UICONTROL 標準]** を、ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop グラフ ](assets/uc3-tableau-graph.png){zoomable="yes"}

1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 複製]** を選択し、2 番目のシートを作成します。
1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Graph` に変更します。
1. **[!UICONTROL シート 1 （2）]** タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Data` に変更します。
1. **[!UICONTROL データ]** シートが選択されていることを確認します。 **[!UICONTROL データ]** 表示で、次の操作を行います。
   1. 右上の **[!UICONTROL 表示]** を選択し、**[!UICONTROL テキストテーブル]** （左上のビジュアライゼーション）を選択して、データビューのコンテンツをテーブルに変更します。
   1. **[!UICONTROL HOUR （Daterangeday）]** を **[!UICONTROL Columns]** から **[!UICONTROL Rows]** にドラッグします。
   1. **[!UICONTROL 標準]** を、ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop データ ](assets/uc3-tableau-data.png){zoomable="yes"}

1. **[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL Sheets]** シェルフから **[!UICONTROL Graph]** シートを **[!UICONTROL Dashboard 1]** ビュー（「シートをここにドロップ *」と表示されているビュー* にドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL グラフ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビューで **[!UICONTROL データ]** シートを選択し、**[!UICONTROL ビュー全体]** を **[!UICONTROL 固定幅]** に変更します。

      **[!UICONTROL ダッシュボード 1]** ビューは次のようになります。

      ![Tableau Desktop ダッシュボード 1](assets/uc3-tableau-dashboard.png){zoomable="yes"}


>[!TAB Looker]


1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/01/02]** として指定します。
1. 左側のパネルの「**[!UICONTROL Cc データビュー]**」セクションから、
   1. 「**[!UICONTROL ‣ Daterangehour Date]**」を選択し、「**[!UICONTROL DIMENSIONS]**」のリストから「**[!UICONTROL Time]**」を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択して、折れ線グラフのビジュアライゼーションを表示します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker 結果日別トレンド ](assets/uc3-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++


## 月間トレンド

このユースケースでは、2023 年の発生（イベント）の月ごとのトレンドを表示するテーブルとシンプルな線のビジュアライゼーションを表示します。

+++ Customer Journey Analytics

ユースケースの例 **[!UICONTROL 月間トレンド]** パネルを次に示します。

![Customer Journey Analyticsの月間トレンドビジュアライゼーション ](assets/cja_monthly_trend.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterangemonth]** を選択します。
   1. 「**[!UICONTROL ∑回数]**」を選択します。

   当月の発生件数を示すテーブルが表示されます。 視認性を高めるには、ビジュアライゼーションを拡大します。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterangemonth is （All）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. フィルターを定義して **[!UICONTROL 値が]** 次の値の場合に項目を表示 **** `1/1/2023` **[!UICONTROL および]** **[!UICONTROL 次の値の前]** `1/1/2024.` を設定します。カレンダーアイコンを使用して、日付を選択して選択できます。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

   適用した **[!UICONTROL daterangemonth]** フィルターで更新されたテーブルが表示されます。

1. **[!UICONTROL ビジュアライゼーション]** パネルで、

   1. **[!UICONTROL 折れ線グラフ]** ビジュアライゼーションを選択します。

   折れ線グラフビジュアライゼーションは、テーブルと同じデータを使用しながら、テーブルを置き換えます。 Power BI デスクトップは次のようになります。

   ![Power BI Desktop ユースケース 2 日付範囲フィルター ](assets/uc4-pbi-filter-daterange.png){zoomable="yes"}

1. 折れ線グラフのビジュアライゼーションで：

   1. ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
   1. コンテキストメニューから「**[!UICONTROL テーブルとして表示]**」を選択します。

   メインビューが更新され、折れ線グラフのビジュアライゼーションとテーブルの両方が表示されます。 Power BI デスクトップは次のようになります。

   ![Power BI デスクトップのユースケース 2 最終的な毎日のトレンドビジュアライゼーション ](assets/uc4-pbi-filter-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付範囲]** を選択し、`01/01/2023` ～ `01/01/2024` の期間を指定します。

      ![Tableau Desktop フィルター ](assets/uc4-tableau-filter.png){zoomable="yes"}

   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterangeday]** をドラッグ&amp;ドロップし、**[!UICONTROL 列]** の横のフィールドにエントリをドロップします。
      * **[!UICONTROL Daterangeday]** ドロップダウンメニューから **[!UICONTROL MONTH]** を選択し、値が **[!UICONTROL MONTH （Daterangeday）]** に更新されるようにします。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル（*メジャー名*）]** リストから **[!UICONTROL 発生件数]** をドラッグ&amp;ドロップし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。 値は自動的に **[!UICONTROL SUM （発生件数）]** に変換されます。
   1. **[!UICONTROL 標準]** を、ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop グラフ ](assets/uc4-tableau-graph.png){zoomable="yes"}

1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 複製]** を選択し、2 番目のシートを作成します。
1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Graph` に変更します。
1. **[!UICONTROL シート 1 （2）]** タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Data` に変更します。
1. **[!UICONTROL データ]** シートが選択されていることを確認します。 データビューで、
   1. 右上の **[!UICONTROL 表示]** を選択し、**[!UICONTROL テキストテーブル]** （左上のビジュアライゼーション）を選択して、データビューのコンテンツをテーブルに変更します。
   1. **[!UICONTROL MONTH （Daterangeday）]** を **[!UICONTROL Columns]** から **[!UICONTROL Rows]** にドラッグします。
   1. **[!UICONTROL 標準]** を、ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop データ ](assets/uc4-tableau-data.png){zoomable="yes"}

1. **[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL Sheets]** シェルフから **[!UICONTROL Graph]** シートを **[!UICONTROL Dashboard 1]** ビュー（「シートをここにドロップ *」と表示されているビュー* にドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL グラフ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビューで **[!UICONTROL データ]** シートを選択し、**[!UICONTROL ビュー全体]** を **[!UICONTROL 固定幅]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop ダッシュボード 1](assets/uc4-tableau-dashboard.png){zoomable="yes"}


>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2024/01/01]** として指定します。
1. 左側の **[!UICONTROL Cc データビュー]** パネルから、
   1. **[!UICONTROL DIMENSIONS]** のリストから「**[!UICONTROL ‣Daterangemonth 日付]**」を選択してから「**[!UICONTROL 月]**」を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択して、折れ線グラフのビジュアライゼーションを表示します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker 結果日別トレンド ](assets/uc4-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++


## ランク付けされた単一ディメンション

このユースケースでは、2023 年を超える製品名の購入および購入売上高を示すテーブルとシンプルな棒ビジュアライゼーションを表示します。

+++ Customer Journey Analytics

ユースケースの例 **[!UICONTROL 単一のDimensionのランク付け]** パネルは次のとおりです。

![Customer Journey Analyticsの単一ディメンションランクのビジュアライゼーション ](assets/cja-single-dimension-ranked.png){zoomable="yes"}
+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterange]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. 「**[!UICONTROL ∑ purchase_revenue]**」を選択します。
   1. 「**[!UICONTROL ∑購入]**」を選択します。

   選択した要素の列ヘッダーのみを表示する空のテーブルが表示されます。 視認性を高めるには、ビジュアライゼーションを拡大します。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL このビジュアルのフィルター**[!UICONTROL  から ]**daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 相対日付]** を選択します。
   1. フィルターを定義して **[!UICONTROL 値が過去]** **[!UICONTROL 暦年**[!UICONTROL  に含まれる場合に項目を表示 ]**`1` します]**。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

   適用した **[!UICONTROL daterange]** フィルターを使用して更新されたテーブルが表示されます。

1. **[!UICONTROL ビジュアライゼーション]** パネルで、

   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用して **[!UICONTROL Daterange]** を **[!UICONTROL Columns]** から削除します。
   1. **[!UICONTROL 購入の合計]** を **[!UICONTROL 列]** の **[!UICONTROL 購入の合計]** の下にドラッグ&amp;ドロップします。

1. テーブル ビジュアライゼーションで、次の操作を行います。

   1. **[!UICONTROL purchase_revenue の合計]** を選択すると、商品名を降順で並べ替えることができます。 Power BI デスクトップは次のようになります。

   ![Power BI デスクトップユースケース 5 テーブルステータス ](assets/uc5-pbi-table.png){zoomable="yes"}

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL product_name is （All）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** を **[!UICONTROL 上位 N]** に設定します。
   1. フィルターを定義して **[!UICONTROL 項目を表示]****[!UICONTROL 上位]**`10`**[!UICONTROL 値]** にします。
   1. **[!UICONTROL purchase_revenue]** を **[!UICONTROL By value]** **[!UICONTROL ここにデータフィールドを追加]** にドラッグ&amp;ドロップします。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

   Analysis Workspaceのフリーフォームテーブルビジュアライゼーションと同期して、購入売上高の値で更新されたテーブルが表示されます。

1. **[!UICONTROL ビジュアライゼーション]** パネルで、

   1. **[!UICONTROL 折れ線グラフおよび積み重ね柱状グラフ]** ビジュアライゼーションを選択します。

   折れ線グラフおよび積み重ね柱状グラフビジュアライゼーションは、テーブルを置き換え、テーブルと同じデータを使用します。

1. **[!UICONTROL 購入]** を **[!UICONTROL ビジュアライゼーション]** ペインの **[!UICONTROL 線の Y 軸]** にドラッグ&amp;ドロップします。

   折れ線グラフと積み重ね柱状グラフが更新されます。 Power BI デスクトップは次のようになります。

   ![Power BI デスクトップのユースケース 5 グラフ ](assets/uc5-pbi-chart.png){zoomable="yes"}

1. 折れ線グラフおよび積み重ね柱状グラフのビジュアライゼーションで：

   1. ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
   1. コンテキストメニューから「**[!UICONTROL テーブルとして表示]**」を選択します。

   メインビューが更新され、折れ線グラフのビジュアライゼーションとテーブルの両方が表示されます。

   ![Power BI デスクトップのユースケース 2 最終的な毎日のトレンドビジュアライゼーション ](assets/uc5-pbi-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付範囲]** を選択し、`01/01/2023` ～ `31/12/2023` の期間を指定します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。

      ![Tableau Desktop フィルター ](assets/uc5-tableau-filter.png){zoomable="yes"}

   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** をドラッグ&amp;ドロップし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル（*メジャー名*）]** リストから **[!UICONTROL 購入]** をドラッグ&amp;ドロップし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。 値は自動的に **[!UICONTROL SUM （Purchases）]** に変換されます。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル（*メジャー名*）]** リストから **[!UICONTROL 購入収益]** をドラッグ&amp;ドロップし、**[!UICONTROL 列]** の横のフィールドにエントリをドロップして、**[!UICONTROL SUM （購入）]** から左にドロップします。 値は **[!UICONTROL SUM （Purchase Revenue）]** に自動変換されます。
   1. 両方のグラフを降順で並べ替えるには、**[!UICONTROL 購買収益]** タイトルにポインタを合わせて、並べ替えアイコンを選択します。
   1. グラフのエントリ数を制限するには、「**[!UICONTROL 行**[!UICONTROL 」で「SUM （購入売上高） ]**を選択し、ドロップダウンメニューから]** フィルター **[!UICONTROL を選択し]** す。
   1. **[!UICONTROL フィルター\[Purchase Revenue\]]** ダイアログで **[!UICONTROL 値の範囲]** を選択し、適切な値を入力します。 例：`1,000,000`～`2,000,000` **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. 2 つの棒グラフを 2 つの組み合わせのグラフに変換するには、「**[!UICONTROL 行**[!UICONTROL 」で「合計 ]**購入）]** を選択し、ドロップダウンメニューから「**[!UICONTROL 二重軸]**」を選択します。 棒グラフは散布図に変換されます。
   1. 散布図を棒グラフに変更するには、次の手順に従います。
      1. **[!UICONTROL マーク]** エリアで **[!UICONTROL SUM （Purchases）]** を選択し、ドロップダウンメニューから **[!UICONTROL ライン]** を選択します。
      1. **[!UICONTROL マーク]** エリアで「**[!UICONTROL SUM （Purchase Revenue）]**」を選択し、ドロップダウンメニューから「**[!UICONTROL バー]**」を選択します。

   Tableau Desktop は次のようになります。

   ![Tableau Desktop グラフ ](assets/uc5-tableau-graph.png){zoomable="yes"}

1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 複製]** を選択し、2 番目のシートを作成します。
1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Data` に変更します。
1. **[!UICONTROL シート 1 （2）]** タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Graph` に変更します。
1. **[!UICONTROL データ]** シートが選択されていることを確認します。
   1. 右上の **[!UICONTROL 表示]** を選択し、**[!UICONTROL テキストテーブル]** （左上のビジュアライゼーション）を選択して、2 つのグラフのコンテンツをテーブルに変更します。
   1. 購買収益を降順で並べ替えるには、テーブルの **[!UICONTROL 購買収益]** にポインタを合わせて ![SortOrderDown](/help/assets/icons/SortOrderDown.svg) を選択します。
   1. **[!UICONTROL 全体表示]** ドロップダウンメニューから **[!UICONTROL 全体表示]** を選択します。

   Tableau Desktop は次のようになります。

   ![Tableau Desktop データ ](assets/uc5-tableau-data.png){zoomable="yes"}

1. **[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL Sheets]** シェルフから **[!UICONTROL Graph]** シートを **[!UICONTROL Dashboard 1]** ビュー（「シートをここにドロップ *」と表示されているビュー* にドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL グラフ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビューで **[!UICONTROL データ]** シートを選択し、**[!UICONTROL ビュー全体]** を **[!UICONTROL 固定幅]** に変更します。

   **[!UICONTROL ダッシュボード 1]** ビューは次のようになります。

   ![Tableau Desktop ダッシュボード 1](assets/uc5-tableau-dashboard.png){zoomable="yes"}



>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2024/01/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションで、「**[!UICONTROL 製品名]**」を選択します。
1. 左パネルの「**[!UICONTROL ‣カスタムフィールド]**」セクションから：
   1. 「**[!UICONTROL +追加]**」ドロップダウンメニューから「**[!UICONTROL カスタム測定]**」を選択します。
   1. **[!UICONTROL カスタム測定を作成]** ダイアログで、次の手順を実行します。
      1. **[!UICONTROL 測定するフィールド]** ドロップダウンメニューから **[!UICONTROL 購入売上高]** を選択します。
      1. **[!UICONTROL 測定タイプ]** ドロップダウンメニューから **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 名前]** のカスタムフィールド名を入力します。 例：`Purchase Revenue`。
      1. **[!UICONTROL フィールドの詳細]** タブを選択します。
      1. **[!UICONTROL 形式]** ドロップダウンメニューから「**[!UICONTROL 小数]**」を選択し、「**[!UICONTROL 小数]**」 `0` 入力されていることを確認します。
         ![Looker カスタム指標フィールド ](assets/uc5-looker-customfield.png){zoomable="yes"}
      1. 「**[!UICONTROL 保存]**」を選択します。
   1. 「**[!UICONTROL +追加**[!UICONTROL 」ドロップダウンメニューから ]**カスタム測定]** をもう一度選択します。 **[!UICONTROL カスタムを作成]** メジャーダイアログで、
      1. **[!UICONTROL 測定するフィールド]** ドロップダウンメニューから **[!UICONTROL 購入]** を選択します。
      1. **[!UICONTROL 測定タイプ]** ドロップダウンメニューから **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 名前]** のカスタムフィールド名を入力します。 例：`Sum of Purchases`。
      1. **[!UICONTROL フィールドの詳細]** タブを選択します。
      1. **[!UICONTROL 形式]** ドロップダウンメニューから「**[!UICONTROL 小数]**」を選択し、「**[!UICONTROL 小数]**」 `0` 入力されていることを確認します。
      1. 「**[!UICONTROL 保存]**」を選択します。
   1. 両方のフィールドがデータビューに自動的に追加されます。
1. 別の **[!UICONTROL フィルター]** を追加する場合は「**[!UICONTROL + フィルター]** を選択し、データを制限する場合は「制限」を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、「**[!UICONTROL ‣カスタムフィールド]**」を選択し、「**[!UICONTROL 購入収益]**」を選択します。
1. 適切な選択を行い、提案された値を入力します。これにより、フィルターの `2000000` が **[!UICONTROL 次を含む]** `1000000` **[!UICONTROL AND]** になります。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択して、折れ線グラフのビジュアライゼーションを表示します。
1. **[!UICONTROL ビジュアライゼーション]** の「**[!UICONTROL 編集]**」を選択して、ビジュアライゼーションを更新します。 ポップアップダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL シリーズ]** タブを選択します。
   1. 下にスクロールして **[!UICONTROL 購入]** を表示し、**[!UICONTROL タイプ]** を **[!UICONTROL 行]** に変更します。
   1. 「**[!UICONTROL Y]**」タブを選択します。
   1. **[!UICONTROL 左側の 1]** コンテナから **[!UICONTROL 購入]** を **[!UICONTROL *ここにシリーズをドラッグして新しい左軸を作成&#x200B;*]**にドラッグします。 このアクションにより、**[!UICONTROL  左 2 ]**コンテナが作成されます。
      ![Looker ビジュアライゼーション設定 ](assets/uc5-looker-visualization.png){zoomable="yes"}
   1. **[!UICONTROL 編集 ](/help/assets/icons/CrossSize75.svg) の横にある ![CrossSize75]** を選択して、ポップアップダイアログを非表示にします

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker 結果日別トレンド ](assets/uc5-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++


## 複数のディメンションのランク

このユースケースでは、2023 年を超える製品カテゴリ内の製品名について、購入収益と購入を分類したテーブルを表示する必要があります。 その上に、いくつかのビジュアライゼーションを使用して、各製品カテゴリ内での製品カテゴリ分布と製品名の貢献度の両方を示します。

+++ Customer Journey Analytics

ユースケースの例 **[!UICONTROL 複数のDimensionのランク付け]** パネルを次に示します。

![Customer Journey Analyticsの複数のDimensionのランクパネル ](assets/cja-multiple-dimension-ranked.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. 日付範囲をすべてのビジュアライゼーションに確実に適用するには、**[!UICONTROL データ]** パネルから **[!UICONTROL このページのフィルター**[!UICONTROL  に ]**daterangeday]** をドラッグ&amp;ドロップします。
   1. **[!UICONTROL このページのフィルター]** から **[!UICONTROL daterangeday is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 相対日付]** を選択します。
   1. フィルターを定義して **[!UICONTROL 値が過去]** **[!UICONTROL 暦年**[!UICONTROL  に含まれる場合に項目を表示 ]**`1` します]**。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL datarangeday]** を選択します。
   1. **[!UICONTROL product_category]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. 「**[!UICONTROL ∑ purchase_revenue]**」を選択します。
   1. **[!UICONTROL ∑の購入を選択]**

1. 縦棒グラフをテーブルに変更するには、テーブルが選択されていることを確認し、**[!UICONTROL ビジュアライゼーション]** ペインから **[!UICONTROL マトリックス]** を選択します。
   * **[!UICONTROL product_name]** を **[!UICONTROL 列]** からドラッグし、**[!UICONTROL 行]** の**[!UICONTROL product_categor]**y の下にあるフィールドを **[!UICONTROL ビジュアライゼーション]** ペインにドロップします。

1. テーブル内に表示される製品の数を制限するには、**[!UICONTROL フィルター]** ペインで **[!UICONTROL product_name is （All）]** を選択します。

   1. **[!UICONTROL 詳細フィルター]** を選択します。
   1. **[!UICONTROL フィルタータイプ]****[!UICONTROL 上位 N]****[!UICONTROL 項目を表示]****[!UICONTROL 上位]**`15`**[!UICONTROL 値別]** を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 購入]** を **[!UICONTROL ここにデータフィールドを追加]** にドラッグします。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

1. 読みやすくするには、トップメニューから **[!UICONTROL 表示]** を選択し、**[!UICONTROL ページビュー]**/**[!UICONTROL 実際のサイズ]** を選択して、テーブルビジュアライゼーションのサイズを変更します。

1. テーブルの各カテゴリを分類するには、製品カテゴリレベルで **[!UICONTROL +]** を選択します。 Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数ディメンションのランク付けマトリックス テーブル ](assets/uc6-powerbi-data.png){zoomable="yes"}

1. 上部のメニューから **[!UICONTROL ホーム]** を選択し、「**[!UICONTROL 新しいビジュアル]** を選択します。 新しいビジュアルがレポートに追加されます。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL product_category]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. **[!UICONTROL purchase_revenue]** を選択します。

1. ビジュアルを変更するには、棒グラフを選択し、「**[!UICONTROL ビジュアライゼーション]** パネルから **[!UICONTROL ツリーマップ]** を選択します。
1. **[!UICONTROL product_category]** が **[!UICONTROL Category]** の下にリストされ、**[!UICONTROL product_name]** が **[!UICONTROL ビジュアライゼーション]** ペインの **[!UICONTROL 詳細]** の下にリストされていることを確認します。

   Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数ディメンションのランクツリーマップ ](assets/uc6-powerbi-treemap.png){zoomable="yes"}

1. 上部のメニューから **[!UICONTROL ホーム]** を選択し、「**[!UICONTROL 新しいビジュアル]** を選択します。 新しいビジュアルがレポートに追加されます。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL product_category]** を選択します。
   1. **[!UICONTROL purchase_revenue]** を選択します。
   1. **[!UICONTROL 購入]** を選択します。

1. **[!UICONTROL ビジュアライゼーション]** パネルで、
   1. ビジュアライゼーションを変更するには、**[!UICONTROL 折れ線グラフと積み重ね柱状グラフ]** を選択します。
   1. **[!UICONTROL 列の y 軸]** から **[!UICONTROL 行の y 軸]** に **[!UICONTROL sum_of_purchases]** をドラッグします。

1. レポートで、個々のビジュアライゼーションを再シャッフルします。

   Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数ディメンションが最終ランクに ](assets/uc6-powerbi-final.png){zoomable="yes"} りました


>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 前年]** を指定します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](assets/uc6-tableau-filter.png){zoomable="yes"}

   1. **[!UICONTROL 製品カテゴリ]** をドラッグして、「列 **[!UICONTROL の横にドロップ]** ます。
   1. **[!UICONTROL 購入売上高]** をドラッグし、「行 **[!UICONTROL の横にドロップ]** ます。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. 「購入」をドラッグし、「**[!UICONTROL 行]**」の横にドロップします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL SUM （Purchases）]** を選択し、ドロップダウンメニューから **[!UICONTROL Dual Axis]** を選択します。
   1. **[!UICONTROL マーク]** で **[!UICONTROL SUM （Purchases）]** を選択し、ドロップダウンメニューから **[!UICONTROL Line]** を選択します。
   1. **[!UICONTROL マーク]** の **[!UICONTROL SUM （Purchase Revenue）]** を選択し、ドロップダウンメニューから **[!UICONTROL 棒グラフ]** を選択します。
   1. **[!UICONTROL フィット]** メニューから **[!UICONTROL ビュー全体]** を選択します。
   1. グラフの **[!UICONTROL 購買収益]** タイトルを選択し、購買収益が昇順であることを確認します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop 複数ディメンションのランク付けカテゴリ ](assets/uc6-tableau-category.png){zoomable="yes"}

1. 現在の **[!UICONTROL シート 1]** シートの名前を `Category` に変更します。
1. **[!UICONTROL 新規ワークシート]** を選択して新規シートを作成し、名前を `Data` に変更します。

   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 前年]** を指定します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** に **[!UICONTROL 購入売上高]** をドラッグします。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. **[!UICONTROL 購入]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** にドラッグし、**[!UICONTROL 購入収益]** の横にドラッグします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL 製品カテゴリ]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 行]** にドラッグします。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 製品名]** を **[!UICONTROL 行]** にドラッグし、**[!UICONTROL 製品カテゴリ]** の横にドラッグします。
   1. 2 つの横棒をテーブルに変更するには、「**[!UICONTROL 表示]**」から「**[!UICONTROL テキスト表]**」を選択します。
   1. 製品数を制限するには、「**[!UICONTROL 測定値]**」で「**[!UICONTROL 購入]**」を選択します。 ドロップダウンメニューから「**[!UICONTROL フィルター]**」を選択します。
   1. **[!UICONTROL フィルター\[ 購入\]]** ダイアログで **[!UICONTROL 少なくとも]** を選択し、`7000` と入力します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop の複数Dimensionのランクデータ ](assets/uc6-tableau-data.png){zoomable="yes"}

1. **[!UICONTROL 新規ワークシート]** を選択して新しいシートを作成し、名前を **[!UICONTROL ツリーマップ]** に変更します。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 前年]** を指定します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 行]** に **[!UICONTROL 購入売上高]** をドラッグします。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 購入]** を **[!UICONTROL 行]** にドラッグし、**[!UICONTROL 購入収益]** の横にドラッグします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL 製品カテゴリ]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** にドラッグします。
   1. **[!UICONTROL 製品名]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** にドラッグします。
   1. 2 つの縦棒グラフをツリーマップに変更するには、「**[!UICONTROL 表示]**」から「**[!UICONTROL ツリーマップ]**」を選択します。
   1. 製品数を制限するには、「**[!UICONTROL 測定値]**」で「**[!UICONTROL 購入]**」を選択します。 ドロップダウンメニューから「**[!UICONTROL フィルター]**」を選択します。
   1. **[!UICONTROL フィルター\[ 購入\]]** ダイアログで **[!UICONTROL 少なくとも]** を選択し、`7000` と入力します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop の複数Dimensionのランクデータ ](assets/uc6-tableau-treemap.png){zoomable="yes"}

1. **[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL カテゴリ]** シートを **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビュー（「シートをここにドロップ *」と表示される* にドラッグ&amp;ドロップします。
   1. **[!UICONTROL ツリーマップ]** シートを、**[!UICONTROL カテゴリ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL ツリーマップ**[!UICONTROL  シートの下にある ]**シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビュー内の各シートのサイズを変更します。

   **[!UICONTROL ダッシュボード 1]** ビューは次のようになります。

   ![Tableau Desktop ダッシュボード 1](assets/uc6-tableau-final.png){zoomable="yes"}


>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2024/01/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL 製品カテゴリ]** を選択します。
   1. **[!UICONTROL 製品名]** を選択します。
1. 左パネルの「**[!UICONTROL ‣カスタムフィールド]**」セクションから：
   1. 「**[!UICONTROL +追加]**」ドロップダウンメニューから「**[!UICONTROL カスタム測定]**」を選択します。
   1. **[!UICONTROL カスタム測定を作成]** ダイアログで、次の手順を実行します。
      1. **[!UICONTROL 測定するフィールド]** ドロップダウンメニューから **[!UICONTROL 購入売上高]** を選択します。
      1. **[!UICONTROL 測定タイプ]** ドロップダウンメニューから **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 名前]** のカスタムフィールド名を入力します。 例：`Sum of Purchase Revenue`。
      1. **[!UICONTROL フィールドの詳細]** タブを選択します。
      1. **[!UICONTROL 形式]** ドロップダウンメニューから「**[!UICONTROL 小数]**」を選択し、「**[!UICONTROL 小数]**」 `0` 入力されていることを確認します。
         ![Looker カスタム指標フィールド ](assets/uc5-looker-customfield.png){zoomable="yes"}
      1. 「**[!UICONTROL 保存]**」を選択します。
   1. 「**[!UICONTROL +追加**[!UICONTROL 」ドロップダウンメニューから ]**カスタム測定]** をもう一度選択します。 **[!UICONTROL カスタムを作成]** メジャーダイアログで、
      1. **[!UICONTROL 測定するフィールド]** ドロップダウンメニューから **[!UICONTROL 購入]** を選択します。
      1. **[!UICONTROL 測定タイプ]** ドロップダウンメニューから **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 名前]** のカスタムフィールド名を入力します。 例：`Sum of Purchases`。
      1. **[!UICONTROL フィールドの詳細]** タブを選択します。
      1. **[!UICONTROL 形式]** ドロップダウンメニューから「**[!UICONTROL 小数]**」を選択し、「**[!UICONTROL 小数]**」 `0` 入力されていることを確認します。
      1. 「**[!UICONTROL 保存]**」を選択します。
   1. 両方のフィールドがデータビューに自動的に追加されます。
1. 「**[!UICONTROL フィルター]**」セクションで、「**[!UICONTROL + フィルター]**」を選択します。 **[!UICONTROL フィルターを追加]** ダイアログで以下を行います。 「**[!UICONTROL ‣カスタムフィールド]**」を選択し、「**[!UICONTROL 購入収益]**」を選択します。
1. **[!UICONTROL is >]** を選択し、`800000` と入力して結果を制限します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択して、折れ線グラフのビジュアライゼーションを表示します。
1. **[!UICONTROL ビジュアライゼーション]** の「**[!UICONTROL 編集]**」を選択して、ビジュアライゼーションを更新します。 ポップアップダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL プロット]**」タブを選択します。
   1. 下にスクロールして、「**[!UICONTROL グラフ設定を編集]**」を選択します。
   1. 以下のスクリーンショットに示すように ]****[!UICONTROL  グラフ設定（上書き）で JSON を変更し、「**[!UICONTROL プレビュー]**」を選択します。

      ![Looker 検証設定 ](assets/uc6-looker-visualization.png){zoomable="yes"}

   1. 「**[!UICONTROL 適用]**」を選択します。
   1. **[!UICONTROL 編集 ](/help/assets/icons/CrossSize75.svg) の横にある ![CrossSize75]** を選択して、ポップアップダイアログを非表示にします

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker 結果日別トレンド ](assets/uc6-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++


## 個別ディメンション値のカウント

このユースケースでは、2023 年 1 月中にレポートされた製品名のユニーク数を取得します。

+++ Customer Journey Analytics

商品名の個別カウントについてレポートするには、Customer Journey Analyticsで、**[!UICONTROL タイトル]**`Product Name (Count Distinct)` と **[!UICONTROL 外部 ID]**`product_name_count_distinct` を使用する計算指標を設定します。

![Customer Journey Analytics製品名（Distincr カウント）の計算指標 ](assets/cja-calc-metric-distinct-count-product-names.png){zoomable="yes"}

次に、その指標をユースケースの例の **[!UICONTROL 個別のDimension値をカウント]** パネルで使用できます。

![Customer Journey Analytics個別カウント値 ](assets/cja-count-distinct-dimension-values.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. 日付範囲をすべてのビジュアライゼーションに確実に適用するには、**[!UICONTROL データ]** パネルからこのページの **[!UICONTROL フィルター]** に **[!UICONTROL daterangeday]** をドラッグ&amp;ドロップします。
   1. **[!UICONTROL このページのフィルター]** から **[!UICONTROL daterangeday is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. **[!UICONTROL 値が次の値の場合に項目を表示]****[!UICONTROL が次の値以上の場合に項目を表示]**`1/1/2023`**[!UICONTROL および]****[!UICONTROL が次の値の前]**`2/1/2023` のフィルターを定義してください。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL datarangeday]** を選択します。
   1. Customer Journey Analyticsで定義された計算指標である **[!UICONTROL ∑ cm_product_name_count_distinct]** を選択します。

1. 縦棒グラフをテーブルに変更するには、グラフが選択されていることを確認し、**[!UICONTROL ビジュアライゼーション]** ペインから **[!UICONTROL テーブル]** を選択します。

   Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数カウントの個別テーブル ](assets/uc7-powerbi-table.png){zoomable="yes"}

1. テーブルビジュアライゼーションを選択します。 コンテキストメニューから **[!UICONTROL コピー]**/**[!UICONTROL ビジュアルをコピー]** を選択します。
1. **[!UICONTROL ctrl+v]** を使用してビジュアライゼーションを貼り付けます。 ビジュアライゼーションの正確なコピーが元のコピーと重なります。 レポート領域で右に移動します。
1. コピーしたビジュアライゼーションをテーブルからカードに変更するには、**[!UICONTROL ビジュアライゼーション]** から **[!UICONTROL カード]** を選択します。

   Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数カウントの個別テーブル ](assets/uc7-powerbi-final.png){zoomable="yes"}

または、Power BIの個別カウント機能を使用できます。

1. **[!UICONTROL product_name]** ディメンションを選択します。
1. **[!UICONTROL Count （Distinct）]** 関数を **[!UICONTROL Columns]** の **[!UICONTROL product_name]** ディメンションに適用します。

   ![ 個別Power BI数 ](assets/uc7-powerbi-alternative.png){zoomable="yes"}



>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付の範囲]** を選択し、`01/01/2023` - `31/1/2023` を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL Cm 製品名の個別カウント]** を **[!UICONTROL 行]** にドラッグします。 値が「**[!UICONTROL SUM （Cm Product Name Count Distinct）]**」に変わります。 このフィールドは、Customer Journey Analyticsで定義した計算指標です。
   1. **[!UICONTROL Daterangeday]** をドラッグして、「**[!UICONTROL 列]** の横にドロップします。 **[!UICONTROL Daterangeday]** を選択し、ドロップダウンメニューから **[!UICONTROL Day]** を選択します。
   1. 折れ線グラフのビジュアライゼーションをテーブルに変更するには、「**[!UICONTROL 表示]**」から「**[!UICONTROL テキストテーブル]**」を選択します。
   1. ツールバーの **[!UICONTROL 行と列を入れ替える]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](assets/uc7-tableau-data.png){zoomable="yes"}

1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 複製]** を選択し、2 番目のシートを作成します。
1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Data` に変更します。
1. **[!UICONTROL シート 1 （2）]** タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Card` に変更します。

1. **[!UICONTROL カード]** ビューが選択されていることを確認します。
1. 「**[!UICONTROL DAY （Daterangeday）]**」を選択し、ドロップダウンメニューから「**[!UICONTROL 月]**」を選択します。 値が「**[!UICONTROL MONTH （Daterangeday）]**」に変わります。
1. **[!UICONTROL マーク]** の **[!UICONTROL SUM （CM 製品名カウント個別）]** を選択し、ドロップダウンメニューから **[!UICONTROL 形式]** を選択します。
1. フォントサイズを変更するには、**[!UICONTROL Format SUM （CM Product Name Count Distinct）]** ペインで、「**[!UICONTROL デフォルト**[!UICONTROL 」内の「]**フォント]**」を選択し、フォントサイズとして「**[!UICONTROL 72]**」を選択します。
1. 数値を整列するには、「**[!UICONTROL 整列]**」の横にある「**[!UICONTROL 自動]** を選択し、「**[!UICONTROL 水平]** を中央揃えに設定します。
1. 整数を使用するには、「**[!UICONTROL 数値]**」の横の「**[!UICONTROL 123.456]**」を選択し、「**[!UICONTROL 数値（カスタム）]**」を選択します。 **[!UICONTROL 小数点以下の桁数]** を `0` に設定します。

   Tableau Desktop は次のようになります。

   ![Tableau Desktop Multiple Dimension Rank Filter](assets/uc7-tableau-card.png){zoomable="yes"}

1. **[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL Sheets]** シェルフから **[!UICONTROL Card]** シートを *ここにシートをドロップ* と表示される **[!UICONTROL Dashboard 1]** ビューにドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL カード**[!UICONTROL  シートの下にある ]**シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。

   **[!UICONTROL ダッシュボード 1]** ビューは次のようになります。

   ![Tableau Desktop ダッシュボード 1](assets/uc7-tableau-final.png){zoomable="yes"}


または、Tableau Desktop の個別カウント機能を使用することもできます。

1. **[!UICONTROL Cm の製品名の個別カウント]** ではなく **[!UICONTROL 製品名]** を使用します。
1. **[!UICONTROL Marks]** の **[!UICONTROL 製品名]** に **[!UICONTROL Measure]** > **[!UICONTROL Count （Distinct）]** を適用します。

   ![Tableau の個別カウント ](assets/uc7-tableau-alternative.png){zoomable="yes"}


>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/02/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL Daterange Date]** を選択してから、**[!UICONTROL Date]** を選択します。
   1. **[!UICONTROL 製品名]** の「**⋮詳細**」コンテキストメニューから「**[!UICONTROL 個別‣カウントを集計]**」を選択します。
      ![Looker 製品名コンテキストメニュー ](assets/uc7-looker-count-distinct.png){zoomable="yes"}
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ ビジュアライゼーション]**」を選択し、ツールバーの「6︎⃣」を選択して 1 つの値のビジュアライゼーションを表示します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](assets/uc7-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++


## 日付範囲名を使用してフィルター

このユースケースでは、Customer Journey Analyticsで定義した日付範囲を使用して、昨年の発生件数（イベント数）をフィルタリングしてレポートします。

+++ Customer Journey Analytics

日付範囲を使用してレポートを作成するには、Customer Journey Analyticsで **[!UICONTROL タイトル]** `Last Year 2023` を使用して日付範囲を設定します。

![Customer Journey Analytics フィルターに日付範囲名を使用 ](assets/cja-daterange.png){zoomable="yes"}

次に、使用例の **[!UICONTROL 日付範囲名をフィルターに使用]** パネルでその日付範囲を使用できます。

![Customer Journey Analytics個別カウント値 ](assets/cja-using-date-range-filter-names-to-filter.png){zoomable="yes"}

フリーフォームテーブルのビジュアライゼーションで定義された日付範囲が、パネルに適用される日付範囲をどのように上書きするかに注意してください。

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterangemonth]** を選択します。
   1. **[!UICONTROL daterangeName]** を選択します。
   1. 「**[!UICONTROL ∑回数]**」を選択します。

   **[!UICONTROL このビジュアルのデータ取得エラー]** と表示されるビジュアライゼーションが表示されます。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterangeName は（すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 基本フィルタリング]** を選択します。
   1. **[!UICONTROL 検索]** フィールドの下で、Customer Journey Analyticsで定義された日付範囲の名前である **[!UICONTROL Last Year 2023]** を選択します。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、**[!UICONTROL daterangeName]** を **[!UICONTROL Columns]** から削除します。

   適用した **[!UICONTROL daterangeName]** フィルターで更新されたテーブルが表示されます。 Power BI デスクトップは次のようになります。

   ![ 日付範囲名を使用してフィルターを適用するPower BI デスクトップ ](assets/uc8-powerbi-final.png){zoomable="yes"}

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange Name]** エントリをドラッグします。
   1. **[!UICONTROL フィルター\[Daterange Name\]]** ダイアログで **[!UICONTROL リストから選択]** が選択されていることを確認し、リストから **[!UICONTROL Last Year 2023]** を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterangemonth]** エントリをドラッグし、**[!UICONTROL 行]** の横のフィールドにドロップします。 「**[!UICONTROL Daterangemonth]**」を選択し、「**[!UICONTROL 月]**」を選択します。 値が「**[!UICONTROL MONTH （Daterangemonth）]**」に変わります。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 発生件数]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が「**[!UICONTROL SUM （発生件数）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. ツールバーの **[!UICONTROL 行と列を入れ替える]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](assets/uc8-tableau-final.png){zoomable="yes"}

>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Name]**」を選択します。
1. **[!UICONTROL CC データビューのデータレンジ名]** フィルターを **[!UICONTROL のままに指定し]** 値リストから **[!UICONTROL 昨年 2023]** を選択します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL Daterange Month]** を選択してから、**[!UICONTROL Month]** を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](assets/uc8-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++



## フィルター名を使用したフィルタリング

このユースケースでは、Customer Journey Analyticsで定義した釣り商品カテゴリの既存のフィルターを使用します。 2023 年 1 月中に製品名と発生件数（イベント）をフィルタリングしてレポートするには、次の手順を実行します。

+++ Customer Journey Analytics

Customer Journey Analyticsで使用するフィルターを調べます。

![Customer Journey Analytics フィルター名を使用してフィルター ](assets/cja-fishing-products.png){zoomable="yes"}

次に、使用例の **[!UICONTROL 日付範囲名をフィルターに使用]** パネルでそのフィルターを使用できます。

![Customer Journey Analytics個別カウント値 ](assets/cja-using-filter-names-to-filter.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterange]** を選択します。
   1. **[!UICONTROL filterName]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. 「**[!UICONTROL ∑回数]**」を選択します。

**[!UICONTROL このビジュアルのデータ取得エラー]** と表示されるビジュアライゼーションが表示されます。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL filterName is （All）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 基本フィルタリング]** を選択します。
   1. **[!UICONTROL 検索]** フィールドの下で、**[!UICONTROL 釣り商品]** を選択します。これは、Customer Journey Analyticsで定義されている既存のフィルターの名前です。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. **[!UICONTROL 値が次の値の場合に項目を表示]****[!UICONTROL が次の値以上の場合に項目を表示]**`1/1/2023`**[!UICONTROL および]****[!UICONTROL が次の値の前]**`2/1/2023` のフィルターを定義してください。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、**[!UICONTROL filterName]** を **[!UICONTROL Columns]** から削除します。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して **[!UICONTROL Daterange]** を **[!UICONTROL Columns]** から削除します。

   適用した **[!UICONTROL filterName]** フィルターで更新されたテーブルが表示されます。 Power BI デスクトップは次のようになります。

   ![ 日付範囲名を使用してフィルターを適用するPower BI デスクトップ ](assets/uc9-powerbi-final.png){zoomable="yes"}


>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL フィルター名]** エントリをドラッグします。
   1. **[!UICONTROL フィルター\[ フィルター名\]]** ダイアログで **[!UICONTROL リストから選択]** が選択されていることを確認し、リストから **[!UICONTROL 釣り製品]** を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付の範囲]** を選択し、`01/01/2023` - `01/02/2023` を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** を **[!UICONTROL 行]** にドラッグします。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 発生件数]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が「**[!UICONTROL SUM （発生件数）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](assets/uc9-tableau-final.png){zoomable="yes"}

>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/02/01]** として指定します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択して、別のフィルターを追加します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣フィルター名]**」を選択します。
1. フィルターの選択範囲が **[!UICONTROL is]** であることを確認します。
1. 可能な値のリストから **[!UICONTROL 釣り製品]** を選択します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL 製品名]** を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](assets/uc9-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++


## ディメンション値を使用したフィルタリング

Customer Journey Analyticsで、ハンティング商品カテゴリの商品をフィルタリングする新しいフィルターを作成します。 次に、新しいフィルターを使用して、2023 年 1 月のハンティングカテゴリの商品の製品名と発生件数（イベント）についてレポートします。

+++ Customer Journey Analytics

Customer Journey Analyticsで **[!UICONTROL タイトル]** の新しいフィルターを作成し `Hunting Products` す。

![Customer Journey Analytics Dimension値を使用してフィルターする ](assets/cja-hunting-products.png){zoomable="yes"}

次に、使用例の **[!UICONTROL Dimension値をフィルターに使用]** パネルでそのフィルターを使用できます。

![Customer Journey Analytics個別カウント値 ](assets/cja-using-dimension-values-to-filter.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. メニューから **[!UICONTROL ホーム]** を選択し、ツールバーから **[!UICONTROL 更新]** を選択します。 Customer Journey Analyticsで定義した新しいフィルターを取得するには、連携を更新する必要があります。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterange]** を選択します。
   1. **[!UICONTROL filterName]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. 「**[!UICONTROL ∑回数]**」を選択します。

**[!UICONTROL このビジュアルのデータ取得エラー]** と表示されるビジュアライゼーションが表示されます。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL filterName is （All）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 基本フィルタリング]** を選択します。
   1. **[!UICONTROL 検索]** フィールドの下の **[!UICONTROL ハンティング商品]** を選択します。これは、Customer Journey Analyticsで定義されている既存のフィルターの名前です。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. **[!UICONTROL 値が次の値の場合に項目を表示]****[!UICONTROL が次の値以上の場合に項目を表示]**`1/1/2023`**[!UICONTROL および]****[!UICONTROL が次の値の前]**`2/1/2023` のフィルターを定義してください。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、**[!UICONTROL filterName]** を **[!UICONTROL Columns]** から削除します。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して **[!UICONTROL Daterange]** を **[!UICONTROL Columns]** から削除します。

   適用した **[!UICONTROL filterName]** フィルターで更新されたテーブルが表示されます。 Power BI デスクトップは次のようになります。

   ![ 日付範囲名を使用してフィルターを適用するPower BI デスクトップ ](assets/uc10-powerbi-final.png){zoomable="yes"}



>[!TAB Tableau Desktop]

1. **[!UICONTROL Data Source]** ビューの **[!UICONTROL Data]** の下で、**[!UICONTROL cc_data_view （prod:cja%3FFLATTEN）]** のコンテキストメニューから **[!UICONTROL 更新]** を選択します。 Customer Journey Analyticsで定義した新しいフィルターを取得するには、連携を更新する必要があります。
1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL フィルター名]** エントリをドラッグします。
   1. **[!UICONTROL フィルター\[ フィルター名\]]** ダイアログで **[!UICONTROL リストから選択]** が選択されていることを確認し、リストから **[!UICONTROL ハンティング製品]** を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付の範囲]** を選択し、`01/01/2023` - `1/2/2023` を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** を **[!UICONTROL 行]** にドラッグします。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 発生件数]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が「**[!UICONTROL SUM （発生件数）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](assets/uc10-tableau-final.png){zoomable="yes"}

>[!TAB Looker]

1. 1 で。 Looker の **[!UICONTROL 探索]** インターフェイスで、接続を更新します。 「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL キャッシュのクリアと更新]**」を選択します。
1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/02/01]** として指定します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択して、別のフィルターを追加します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣製品カテゴリ]**」を選択します。
1. フィルターの選択として **[!UICONTROL is]** を使用していることを確認します。
1. 可能な値のリストから **[!UICONTROL ハンティング製品]** を選択します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL 製品名]** を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。

次のようなテーブルが表示されます。

![Looker count distinct](assets/uc10-looker-result.png){zoomable="yes"}

>[!ENDTABS]

+++



## 並べ替え

このユースケースでは、2023 年 1 月の製品名の購入収益と購入を、購入収益の降順に並べ替えてレポートします。

+++ Customer Journey Analytics

このユースケースでは、例えば **[!UICONTROL 並べ替え]** パネルを使用します。

![Customer Journey Analytics並べ替えパネル ](assets/cja-sort.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterange]** を選択します。
   1. **[!UICONTROL product_namr]** を選択します。
   1. 「**[!UICONTROL ∑ purchase_revenue]**」を選択します。
   1. 「**[!UICONTROL ∑購入]**」を選択します。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. **[!UICONTROL 値が次の値の場合に項目を表示]****[!UICONTROL が次の値以上の場合に項目を表示]**`1/1/2023`**[!UICONTROL および]****[!UICONTROL が次の値の前]**`2/1/2023` のフィルターを定義してください。

1. ビジュアライゼーション パネルで、次の操作を行います。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、Columns から daterange を削除します。
   1. **[!UICONTROL purchase_revenue の合計]** を **[!UICONTROL 列]** 項目の下部にドラッグします。

1. レポートで、「**[!UICONTROL purchase_revenue の合計]** を選択して、購買収益の降順でテーブルをソートします。

   Power BI デスクトップは次のようになります。

   ![ 日付範囲名を使用してフィルターを適用するPower BI デスクトップ ](assets/uc11-powerbi-final.png){zoomable="yes"}

BI 拡張機能を使用してPower BI Desktop が実行するクエリには、`sort` ステートメントが含まれていません。 `sort` ステートメントがないということは、並べ替えがクライアントサイドで実行されることを意味します。

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 日付の範囲]** を選択し、`01/01/2023` - `1/2/2023` を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** をドラッグし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 購入]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 購入売上高]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールド、**[!UICONTROL SUM （購入）]** の横のエントリをドロップします。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。
   1. **[!UICONTROL 購入収益]** 列ヘッダーを選択し、この列のテーブルを降順で並べ替えます。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop 並べ替え ](assets/uc11-tableau-final.png){zoomable="yes"}

BI 拡張機能を使用して Tableau Desktop で実行されるクエリには、`sort` ステートメントが含まれていません。 この `sort` ステートメントがないということは、並べ替えがクライアント側で実行されることを意味します。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、接続を更新します。 「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL キャッシュのクリアと更新]**」を選択します。
1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/02/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションで、「**[!UICONTROL 製品名]**」を選択します。
1. 左パネルの「**[!UICONTROL ‣カスタムフィールド]**」セクションから：
   1. 「**[!UICONTROL +追加]**」ドロップダウンメニューから「**[!UICONTROL カスタム測定]**」を選択します。
   1. **[!UICONTROL カスタム測定を作成]** ダイアログで、次の手順を実行します。
      1. **[!UICONTROL 測定するフィールド]** ドロップダウンメニューから **[!UICONTROL 購入売上高]** を選択します。
      1. **[!UICONTROL 測定タイプ]** ドロップダウンメニューから **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 名前]** のカスタムフィールド名を入力します。 例：`Sum of Purchase Revenue`。
      1. **[!UICONTROL フィールドの詳細]** タブを選択します。
      1. **[!UICONTROL 形式]** ドロップダウンメニューから「**[!UICONTROL 小数]**」を選択し、「**[!UICONTROL 小数]**」 `0` 入力されていることを確認します。
         ![Looker カスタム指標フィールド ](assets/uc5-looker-customfield.png){zoomable="yes"}
      1. 「**[!UICONTROL 保存]**」を選択します。
1. **[!UICONTROL 購入収益]** 列で **[!UICONTROL ↓]** （**[!UICONTROL 降順、並べ替え順：1]**）を選択していることを確認します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](assets/uc11-looker-result.png){zoomable="yes"}


BI 拡張機能を使用して Looker によって生成されるクエリには `ORDER BY` が含まれています。これは、Looker および BI 拡張機能を使用して並べ替えが実行されることを意味します。

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"fc83573987b999306eaf6e1a3f2cde70","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "purchase_revenue"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2023-02-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!ENDTABS]

+++

## 制限

このユースケースでは、2023 年中に発生した上位 5 回の製品名についてレポートします。

+++ Customer Journey Analytics

このユースケースの例では **[!UICONTROL 制限]** パネルは次のようになります。

![Customer Journey Analytics制限パネル ](assets/cja-limit.png){zoomable="yes"}

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterange]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. 「**[!UICONTROL ∑回数]**」を選択します。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 相対日付]** を選択します。
   1. フィルターを定義して **[!UICONTROL 値が過去]** **[!UICONTROL 暦年**[!UICONTROL  に含まれる場合に項目を表示 ]**`1` します]**。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。
   1. **[!UICONTROL このビジュアルのフィルター**[!UICONTROL  から ]**product_name は（すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 上位 N]** を選択します。
   1. 「**[!UICONTROL 項目を表示]****[!UICONTROL 上位]**」 `5` 「**[!UICONTROL 値別]**」を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL ∑回数]** をドラッグ&amp;ドロップし、「**[!UICONTROL データフィールドをここに追加]**」にドロップします。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

1. ビジュアライゼーションパネルで、
   * ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、Columns から daterange を削除します。

   Power BI デスクトップは次のようになります。

   ![ 日付範囲名を使用してフィルターを適用するPower BI デスクトップ ](assets/uc12-powerbi-final.png){zoomable="yes"}

BI 拡張機能を使用してPower BI Desktop が実行するクエリには、`limit` ステートメントが含まれていますが、想定されたステートメントは含まれていません。 Power BI デスクトップでは、明示的な製品名の結果を使用して、上位 5 件の発生件数の制限が適用されます。

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 以前の年]** を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** を **[!UICONTROL 行]** にドラッグします。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 発生件数]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が「**[!UICONTROL SUM （発生件数）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。
   1. **[!UICONTROL 行]** の **[!UICONTROL 製品名]** を選択します。 ドロップダウンメニューから **[!UICONTROL フィルター]** を選択します。
      1. **[!UICONTROL フィルター\[ 製品名\]]** ダイアログで **[!UICONTROL トップ]** タブを選択します。
      1. **[!UICONTROL フィールド別：]** **[!UICONTROL 上位]** `5` **[!UICONTROL 発生件数別]** **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。

         ![AlertRed](/help/assets/icons/AlertRed.svg) テーブルが消えていることがわかります。 発生件数別に上位 5 つの製品名を選択しても、このフィルターを使用して正しく機能しない **** 場合。
      1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL 製品名]** を選択し、ドロップダウンメニューから **[!UICONTROL 削除]** を選択します。 テーブルが再び表示されます。
   1. **[!UICONTROL マーク]** シェルフで **[!UICONTROL SUM （発生件数）]** を選択します。 ドロップダウンメニューから **[!UICONTROL フィルター]** を選択します。
      1. **[!UICONTROL フィルタ \[ オカレンス\]]** ダイアログで **[!UICONTROL 最低]** を選択します。
      1. 値として `47.799` と入力します。 この値を使用すると、テーブルに上位 5 項目のみが表示されます。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。

         Tableau Desktop は次のようになります。

         ![Tableau Desktop の制限 ](assets/uc12-tableau-final.png){zoomable="yes"}

上に示すように、Tableau Desktop が実行するこのクエリは、製品名に対して上位 5 件の発生フィルターを定義すると失敗します。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

Tableau Desktop で実行されるクエリは、発生件数に対して上位 5 件のフィルターを定義する際に、以下のように表示されます。 制限は、クエリおよび適用されたクライアントサイドには表示されません。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、接続を更新します。 「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL キャッシュのクリアと更新]**」を選択します。
1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](assets/uc2-looker-filter.png){zoomable="yes"}
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2024/01/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL 製品名]** を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. **[!UICONTROL 購入収益]** 列で **[!UICONTROL ↓]** （**[!UICONTROL 降順、並べ替え順：1]**）を選択していることを確認します。
1. **[!UICONTROL 購入収益]** 列で **[!UICONTROL ↓]** （**[!UICONTROL 降順、並べ替え順：1]**）を選択していることを確認します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](assets/uc12-looker-result.png){zoomable="yes"}

BI 拡張機能を使用して Looker によって生成されるクエリには `FETCH NEXT 5 ROWS ONLY` が含まれています。これは、制限が Looker と BI 拡張機能を通じて実行されることを意味します。

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"a8f3b1ebd5712413ca1ae695090f70db","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COUNT(*) AS "cc_data_view.count"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 5 ROWS ONLY
```

>[!ENDTABS]

+++

## Transformations

様々な BI ツールによる、ディメンション、指標、フィルター、計算指標、日付範囲などのCustomer Journey Analytics オブジェクトの変換を理解します。

+++ Customer Journey Analytics

Customer Journey Analyticsでは、データセットのコンポーネントを [ ディメンション ](/help/data-views/data-views.md) および [ 指標 ](/help/components/apply-create-metrics.md) として公開する方法を [ データビュー ](/help/components/dimensions/overview.md) で定義します。 このディメンションと指標の定義は、BI 拡張機能を使用して BI ツールに公開されます。
[ フィルター ](/help/components/filters/filters-overview.md)、[ 計算指標 ](/help/components/calc-metrics/calc-metr-overview.md)、[ 日付範囲 ](/help/components/date-ranges/overview.md) などのコンポーネントをWorkspace プロジェクトの一部として使用します。 これらのコンポーネントは、BI 拡張機能を使用して BI ツールにも公開されます。

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](#connect-and-validate) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

Customer Journey Analytics オブジェクトは「**[!UICONTROL データ]**」ペインで使用でき、Power BI Desktop で選択したテーブルから取得されます。 例えば、**[!UICONTROL public.cc_data_view]** と指定します。 テーブルの名前は、Customer Journey Analyticsのデータビューに対して定義した外部 ID と同じです。 例えば、**[!UICONTROL タイトル]**`C&C - Data View` と **[!UICONTROL 外部 ID]**`cc_data_view` のデータビューなどです。

**寸法**
Customer Journey Analytics内のディメンションは、[!UICONTROL  コンポーネント ID] で識別されます。 [!UICONTROL  コンポーネント ID] は、Customer Journey Analytics データビューで定義されます。 例えば、Customer Journey Analyticsのディメンション **[!UICONTROL 製品名]** には、Power BI Desktop のディメンションの名前である [!UICONTROL  コンポーネント ID]**[!UICONTROL product_name]** が含まれています。
**[!UICONTROL 日]**、**[!UICONTROL 週]**、**[!UICONTROL 月]** など、Customer Journey Analyticsの日付範囲ディメンションは、**[!UICONTROL daterangeday]**、**[!UICONTROL daterangeweek]**、**[!UICONTROL daterangemonth]** などの形式で使用できます。

**指標**
Customer Journey Analyticsの指標は、[!UICONTROL  コンポーネント ID] で識別されます。 [!UICONTROL  コンポーネント ID] は、Customer Journey Analytics データビューで定義されます。 例えば、Customer Journey Analyticsの **[!UICONTROL 購入売上高]** 指標には、Power BI Desktop の指標の名前である [!UICONTROL  コンポーネント ID]**[!UICONTROL purchase_revenue]** があります。 **[!UICONTROL ∑]** は指標を示します。 任意のビジュアライゼーションで指標を使用すると、指標の名前が **[!UICONTROL 合計 *指標&#x200B;*]**に変更されます。

**フィルター**
Customer Journey Analyticsで定義したフィルターは、「**[!UICONTROL filterName]**」フィールドの一部として使用できます。 Power BI Desktop で **[!UICONTROL filterName]** フィールドを使用すると、使用するフィルターを指定できます。

**計算指標**
Customer Journey Analyticsで定義した計算指標は、計算指標に対して定義した [!UICONTROL  外部 ID] によって識別されます。 例えば、計算指標 **[!UICONTROL Product Name （Count Distinct）]** は [!UICONTROL External ID] **[!UICONTROL product_name_count_distinct]** を持ち、Power BI Desktop では**[!UICONTROL cm_product_name_count_distinct]**t と表示されます。

**日付範囲**
Customer Journey Analyticsで定義する日付範囲は、「**[!UICONTROL daterangeName]**」フィールドの一部として使用できます。 **[!UICONTROL daterangeName]** フィールドを使用する場合は、使用する日付範囲を指定できます。

**カスタム変換**
Power BI Desktop は、[Data Analysis Expressions （DAX） ](https://learn.microsoft.com/en-us/dax/dax-overview) を使用したカスタム変換機能を提供します。 例えば、商品名が小文字の [ 単一のディメンションのランク付け ](#single-dimension-ranked) ユースケースを実行するとします。

1. レポート表示で、棒グラフ ビジュアライゼーションを選択します。
1. データ・ペインで **[!UICONTROL product_name]** を選択します。
1. ツールバーの **[!UICONTROL 新しい列]** を選択します。
1. 式エディターで、`product_name_lower = LOWER('public.cc_data_view[product_name])` のように `product_name_lower` という名前の新しい列を定義します。
   ![Power BI デスクトップの下位への変換 ](assets/uc14-powerbi-transformation.png){zoomable="yes"}
1. **[!UICONTROL product_name]** 列ではなく、必ず **[!UICONTROL Data]** ペインの新しい **[!UICONTROL product_name_lower]** 列を選択してください。
1. テーブルビジュアライゼーションの ![ 詳細 ](/help/assets/icons/More.svg) から **[!UICONTROL テーブルとしてレポート]** を選択します。

   Power BI デスクトップは次のようになります。
   ![Power BI デスクトップ変換の最終版 ](assets/uc14-powerbi-final.png){zoomable="yes"}

カスタム変換の結果、SQL クエリが更新されます。 以下の SQL の例で、`lower` 関数の使用を参照してください。

```sql
select "_"."product_name_lower",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name_lower" as "product_name_lower",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterange" as "daterange",
            "_"."product_name" as "product_name",
            "_"."purchase_revenue" as "purchase_revenue",
            "_"."purchases" as "purchases",
            lower("_"."product_name") as "product_name_lower"
        from 
        (
            select "_"."daterange",
                "_"."product_name",
                "_"."purchase_revenue",
                "_"."purchases"
            from 
            (
                select "daterange",
                    "product_name",
                    "purchase_revenue",
                    "purchases"
                from "public"."cc_data_view" "$Table"
            ) "_"
            where ("_"."daterange" < date '2024-01-01' and "_"."daterange" >= date '2023-01-01') and ("_"."product_name" in ('4G Cellular Trail Camera', '4K Wildlife Trail Camera', 'Wireless Trail Camera', '8-Person Cabin Tent', '20MP No-Glow Trail Camera', 'HD Wildlife Camera', '4-Season Mountaineering Tent', 'Trail Camera', '16MP Trail Camera with Solar Panel', '10-Person Family Tent'))
        ) "_"
    ) "rows"
    group by "product_name_lower"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```

>[!TAB Tableau Desktop]

Customer Journey Analytics オブジェクトは、シートで作業する際に **[!UICONTROL データ]** 側のバーで使用できます。 およびは、Tableau の **[!UICONTROL データソース]** ページの一部として選択したテーブルから取得されます。 例えば、**[!UICONTROL cc_data_view]** と指定します。 テーブルの名前は、Customer Journey Analyticsのデータビューに対して定義した外部 ID と同じです。 例えば、**[!UICONTROL タイトル]**`C&C - Data View` と **[!UICONTROL 外部 ID]**`cc_data_view` のデータビューなどです。

**寸法**
Customer Journey Analytics内のディメンションは、[!UICONTROL  コンポーネント名 ] で識別されます。 [!UICONTROL  コンポーネント名 ] は、Customer Journey Analytics データビューで定義されます。 例えば、Customer Journey Analyticsのディメンション **[!UICONTROL 製品名]** には、Tableau のディメンションの名前である [!UICONTROL  コンポーネント名 ]**[!UICONTROL 製品名]** が含まれています。 すべてのディメンションは、**[!UICONTROL Abc]** で識別されます。
**[!UICONTROL 日]**、**[!UICONTROL 週]**、**[!UICONTROL 月]** など、Customer Journey Analyticsの日付範囲ディメンションは、**[!UICONTROL Daterangeday]**、**[!UICONTROL Daterangeweek]**、**[!UICONTROL Daterangemonth]** などの形式で使用できます。 日付範囲ディメンションを使用する場合、ドロップダウンメニューから日付または時間の適切な定義を選択して、その日付範囲ディメンションに適用する必要があります。 例えば、**[!UICONTROL Year]**、**[!UICONTROL Quarter]**、**[!UICONTROL Month]**、**[!UICONTROL Day]** などです。

**指標**
Customer Journey Analyticsの指標は、[!UICONTROL  コンポーネント名 ] で識別されます。 [!UICONTROL  コンポーネント名 ] は、Customer Journey Analytics データビューで定義されます。 例えば、Customer Journey Analyticsの **[!UICONTROL 購入売上高]** 指標には、Tableau の指標の名前である [!UICONTROL  コンポーネント名 ] **[!UICONTROL 購入売上高]** があります。 すべての指標は、**[!UICONTROL #]** によって識別されます。 任意のビジュアライゼーションで指標を使用すると、指標の名前が **[!UICONTROL Sum （*metric*）]** に変更されます。

**フィルター**
Customer Journey Analyticsで定義したフィルターは、「**[!UICONTROL フィルター名]** フィールドの一部として使用できます。 Tableau で「**[!UICONTROL フィルター名]**」フィールドを使用する場合、使用するフィルターを指定できます。

**計算指標**
Customer Journey Analyticsで定義した計算指標は、計算指標に対して定義した [!UICONTROL  タイトル ] によって識別されます。 例えば、計算指標 **[!UICONTROL 製品名（Count Distinct）]** は [!UICONTROL  タイトル ]**[!UICONTROL 製品名（Count Distinct）]** を持ち、Tableau では **[!UICONTROL Cm 製品名の Count Distinct]** と表示されます。

**日付範囲**
Customer Journey Analyticsで定義した日付範囲は、「**[!UICONTROL Daterange Name]**」フィールドの一部として使用できます。 **[!UICONTROL Daterange Name]** フィールドを使用する場合は、使用する日付範囲を指定できます。

**カスタム変換**
Tableau Desktop は、[ 計算フィールド ](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm) を使用したカスタム変換機能を提供します。 例えば、商品名が小文字の [ 単一のディメンションのランク付け ](#single-dimension-ranked) ユースケースを実行するとします。

1. メインメニューから **[!UICONTROL 分析]**/**[!UICONTROL 計算フィールドを作成]** を選択します。
   1. 関数 `LOWER([Product Name])` を使用して **[!UICONTROL 小文字の製品名]** を定義します。
      ![Tableau 計算フィールド ](assets/uc14-tableau-calculated-field.png){zoomable="yes"}
   1. **[!UICONTROL OK]** を選択します。
1. **[!UICONTROL データ]** シートを選択します。
   1. **[!UICONTROL テーブル]** から **[!UICONTROL 小文字の製品名]** をドラッグし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。
   1. **[!UICONTROL 製品名]** を **[!UICONTROL 行]** から削除します。
1. **[!UICONTROL ダッシュボード 1]** ビューを選択します。

Tableau Desktop は次のようになります。

![ 変換後の Tableau Desktop](assets/uc14-tableau-final.png){zoomable="yes"}

カスタム変換の結果、SQL クエリが更新されます。 以下の SQL の例で、`LOWER` 関数の使用を参照してください。

```sql
SELECT LOWER(CAST(CAST("cc_data_view"."product_name" AS TEXT) AS TEXT)) AS "Calculation_1562467608097775616",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-12-31')))
GROUP BY 1
HAVING ((SUM("cc_data_view"."purchase_revenue") >= 999999.99999998999) AND (SUM("cc_data_view"."purchase_revenue") <= 2000000.00000002))
```

>[!TAB Looker]

Customer Journey Analytics オブジェクトは、**[!UICONTROL 探索]** インターフェイスの c で使用できます。 およびは、Looker での接続、プロジェクト、モデルの設定の一環として取得されます。 例えば、**[!UICONTROL cc_data_view]** と指定します。 ビューの名前は、Customer Journey Analyticsのデータビューに対して定義した外部 ID と同じです。 例えば、**[!UICONTROL タイトル]**`C&C - Data View` と **[!UICONTROL 外部 ID]**`cc_data_view` のデータビューなどです。

**寸法**
Customer Journey Analyticsのディメンションは、{Cc データビュー ]**の左パネルに**[!UICONTROL  2}DIMENSION ]**として表示されます。**[!UICONTROL &#x200B;ディメンションは、Customer Journey Analytics データビューで定義されます。 例えば、Customer Journey Analyticsのディメンション **[!UICONTROL Product Name]** には、Looker のディメンションの名前である **[!UICONTROL DIMENSION]****[!UICONTROL Product Name]** が含まれています。
**[!UICONTROL 日]**、**[!UICONTROL 週]**、**[!UICONTROL 月]** など、Customer Journey Analyticsの日付範囲ディメンションは、**[!UICONTROL Daterangeday 日]**、**[!UICONTROL Daterangeweek 日]**、**[!UICONTROL Daterangemonth 日]** などの形式で使用できます。  日付範囲ディメンションを使用する場合は、日付または時間の適切な定義を選択する必要があります。 例えば、**[!UICONTROL Year]**、**[!UICONTROL Quarter]**、**[!UICONTROL Month]**、**[!UICONTROL Date]** などです。

**指標**
Customer Journey Analyticsの指標は、{Cc データビュー ]**の左レールに**[!UICONTROL  2}DIMENSION ]**として表示されます。**[!UICONTROL &#x200B;例えば、Customer Journey Analyticsの **[!UICONTROL 購入売上高]** 指標には **[!UICONTROL DIMENSION]****[!UICONTROL 購入売上高]** があります。 実際にを指標として使用するには、上記の例に示すようにカスタム測定フィールドを作成するか、ディメンションにショートカットを使用します。 例えば、「**[!UICONTROL ⋮]**」を選択し、「**[!UICONTROL 集計]**」を選択したあと、「**[!UICONTROL 合計]**」を選択します。

**フィルター**
Customer Journey Analyticsで定義したフィルターは、「**[!UICONTROL フィルター名]** フィールドの一部として使用できます。 Looker で **[!UICONTROL フィルター名]** フィールドを使用する場合、使用するフィルターを指定できます。

**計算指標**
Customer Journey Analyticsで定義した計算指標は、計算指標に対して定義した [!UICONTROL  タイトル ] によって識別されます。 例えば、計算指標 **[!UICONTROL 製品名（個別カウント）]** は [!UICONTROL  タイトル ]**[!UICONTROL 製品名（個別カウント）を持ち]** Looker では **[!UICONTROL Cm 製品名カウント個別カウント]** として表示されます。

**日付範囲**
Customer Journey Analyticsで定義した日付範囲は、「**[!UICONTROL Daterange Name]**」フィールドの一部として使用できます。 **[!UICONTROL Daterange Name]** フィールドを使用する場合は、使用する日付範囲を指定できます。

**カスタム変換**
前述のように、Looker では、カスタムフィールドビルダーを使用してカスタム変換機能を提供しています。 例えば、商品名が小文字の [ 単一のディメンションのランク付け ](#single-dimension-ranked) ユースケースを実行するとします。

1. 左パネルの「**[!UICONTROL ‣カスタムフィールド]**」セクションから：
   1. 「**[!UICONTROL +追加**[!UICONTROL 」ドロップダウンメニューから「]**カスタムDimension]**」を選択します。
   1. **[!UICONTROL 式]** テキスト領域に `lower(${cc_data_view.product_name})` を入力します。 `Product Name` を入力し始めると、正しい構文で支援されます。
      ![Looker 変換の例 ](assets/uc14-looker-transformation.png){zoomable="yes"}
   1. **[!UICONTROL 名前]** として `product name` と入力します。
   1. 「**[!UICONTROL 保存]**」を選択します。

次のようなテーブルが表示されます。

![Looker 変換結果 ](assets/uc14-looker-result.png){zoomable="yes"}


カスタム変換の結果、SQL クエリが更新されます。 以下の SQL の例で、`LOWER` 関数の使用を参照してください。

```sql
SELECT
    LOWER((cc_data_view."product_name")) AS "product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchase_revenue",
    COALESCE(SUM(CAST(( cc_data_view."purchases"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchases"
FROM public.cc_data_view  AS cc_data_view
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-01')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!ENDTABS]

+++



## ビジュアライゼーション

Customer Journey Analyticsで使用可能なビジュアライゼーションが、BI ツールで使用可能なビジュアライゼーションを使用して同様に作成される方法を理解します。

+++ Customer Journey Analytics

Customer Journey Analyticsには多数のビジュアライゼーションがあります。 使用可能なすべてのビジュアライゼーションの概要と概要については、[ ビジュアライゼーション ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) を参照してください。

+++

+++ BI ツール

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

### 比較

ほとんどのCustomer Journey Analyticsのビジュアライゼーションでは、Power BI Desktop は同等のエクスペリエンスを提供します。 以下の表を参照してください。

| アイコン | Customer Journey Analyticsのビジュアライゼーション | Power BI デスクトップビジュアライゼーション |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [面グラフ](/help/analysis-workspace/visualizations/area.md) | [ 面グラフ、積み重ね面グラフ、100% 面グラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [棒グラフ](/help/analysis-workspace/visualizations/bar.md) | [ 集合縦棒グラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [ 積み重ね棒グラフ ](/help/analysis-workspace/visualizations/bar.md) | [ 積み重ね柱状グラフおよび 100% 積み重ね柱状グラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [ブレット](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [コホートテーブル](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![コンボ](/help/assets/icons/ComboChart.svg) | [コンボ](/help/analysis-workspace/visualizations/combo-charts.md) | [ 折れ線グラフおよび積み重ね柱状グラフおよび折れ線グラフおよび集合柱状グラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [ドーナツ](/help/analysis-workspace/visualizations/donut.md) | [ ドーナツグラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [フォールアウト](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [ ファネル ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts)。 |
| ![ グラフパス ](/help/assets/icons/GraphPathing.svg) | [フロー](/help/analysis-workspace/visualizations/c-flow/flow.md) | 分解ツリー？ |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Table](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables) および [Matrix](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [ヒストグラム](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md) | [ 集合棒グラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [ 積み重ね横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) | [ 積み重ね棒グラフおよび 100% 積み重ね棒グラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![ ブランチ 3](/help/assets/icons/Branch3.svg) | [ジャーニー キャンバス ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [ 分解ツリー ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![ 主要指標 ](/help/assets/icons/KeyMetrics.svg) | [ 主要指標の概要 ](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [折れ線グラフ](/help/analysis-workspace/visualizations/line.md) | [ 折れ線グラフ ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散布図](/help/analysis-workspace/visualizations/scatterplot.md) | [ 散布図 ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [ セクションヘッダー ](/help/analysis-workspace/visualizations/section-header.md) | [ テキストボックス ](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [変更の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | [ カード ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [数値の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | [ カード ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![テキスト](/help/assets/icons/Text.svg) | [テキスト](/help/analysis-workspace/visualizations/text.md) | [ テキストボックス ](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [ツリーマップ](/help/analysis-workspace/visualizations/treemap.md)<p> | [ツリーマップ](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![タイプ](/help/assets/icons/TwoDots.svg) | [ベン図](/help/analysis-workspace/visualizations/venn.md) | |


### ドリルダウン

Power BIでは、特定のビジュアライゼーションの詳細を調べる [ ドリルモード ](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) をサポートしています。 次の例では、製品カテゴリの購入売上高を分析します。 製品カテゴリを表すバーのコンテキストメニューから、「**[!UICONTROL ドリルダウン]**」を選択できます。

![Power BIのドリルダウン ](assets/uc15-powerbi-drilldown.png){zoomable="yes"}

ドリルダウンすると、選択した製品カテゴリ内の製品の購入売上高でビジュアライゼーションが更新されます。

![Power BIのドリルアップ ](assets/uc15-powerbi-drillup.png){zoomable="yes"}

ドリルダウンすると、`WHERE` 句を使用する次の SQL クエリが生成されます。

```sql
select "_"."product_category" as "c25",
    "_"."product_name" as "c26",
    "_"."a0" as "a0"
from 
(
    select "_"."product_category",
        "_"."product_name",
        "_"."a0"
    from 
    (
        select "_"."product_category",
            "_"."product_name",
            "_"."a0"
        from 
        (
            select "rows"."product_category" as "product_category",
                "rows"."product_name" as "product_name",
                sum("rows"."purchase_revenue") as "a0"
            from 
            (
                select "_"."product_category",
                    "_"."product_name",
                    "_"."purchase_revenue"
                from "public"."cc_data_view" "_"
                where ("_"."daterange" >= date '2023-01-01' and "_"."product_category" = 'Fishing') and "_"."daterange" < date '2024-01-01'
            ) "rows"
            group by "product_category",
                "product_name"
        ) "_"
        where not "_"."a0" is null
    ) "_"
) "_"
order by "_"."product_category",
        "_"."product_name"
limit 1001
```

>[!TAB Tableau Desktop]

### 比較

ほとんどのCustomer Journey Analyticsのビジュアライゼーションでは、Tableau Desktop は同等のエクスペリエンスを提供します。 以下の表を参照してください。

| アイコン | Customer Journey Analyticsのビジュアライゼーション | Power BI デスクトップビジュアライゼーション |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [面グラフ](/help/analysis-workspace/visualizations/area.md) | [ 面グラフ ](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [棒グラフ](/help/analysis-workspace/visualizations/bar.md) | [ 棒グラフ ](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [ 積み重ね棒グラフ ](/help/analysis-workspace/visualizations/bar.md) |  |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [ブレット](/help/analysis-workspace/visualizations/bullet-graph.md) | [ブレットグラフ](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [コホートテーブル](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![コンボ](/help/assets/icons/ComboChart.svg) | [コンボ](/help/analysis-workspace/visualizations/combo-charts.md) | [ 複合グラフ ](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [ドーナツ](/help/analysis-workspace/visualizations/donut.md) | |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [フォールアウト](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![ グラフパス ](/help/assets/icons/GraphPathing.svg) | [フロー](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [ テキスト テーブル ](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [ヒストグラム](/help/analysis-workspace/visualizations/histogram.md) | [ヒストグラム](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md) | [ 棒グラフ ](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [ 積み重ね横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) | [ 棒グラフ ](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![ ブランチ 3](/help/assets/icons/Branch3.svg) | [ジャーニー キャンバス ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![ 主要指標 ](/help/assets/icons/KeyMetrics.svg) | [ 主要指標の概要 ](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [折れ線グラフ](/help/analysis-workspace/visualizations/line.md) | [ 折れ線グラフ ](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散布図](/help/analysis-workspace/visualizations/scatterplot.md) | [散布図](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [ セクションヘッダー ](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [変更の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [数値の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![テキスト](/help/assets/icons/Text.svg) | [テキスト](/help/analysis-workspace/visualizations/text.md) | |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [ツリーマップ](/help/analysis-workspace/visualizations/treemap.md)<p> | [ツリーマップ](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![タイプ](/help/assets/icons/TwoDots.svg) | [ベン図](/help/analysis-workspace/visualizations/venn.md) | |


### ドリルダウン

Tableau は [ ドリルモード ](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) から [ 階層 ](https://help.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm) までサポートしています。 次の例では、**[!UICONTROL テーブル]** 内の **[!UICONTROL 製品名]** フィールドを選択して階層を作成し、**[!UICONTROL 製品カテゴリ]** の上にドラッグします。 次に、製品カテゴリを表すバーのコンテキストメニューから、「**[!UICONTROL + ドリルダウン]**」を選択します。

![Tableau のドリルダウン ](assets/uc15-tableau-drilldown.png){zoomable="yes"}

ドリルダウンすると、選択した製品カテゴリ内の製品の購入売上高でビジュアライゼーションが更新されます。

![Tableau のドリルアップ ](assets/uc15-tableau-drillup.png){zoomable="yes"}

ドリルダウンの結果、GROUP BY 句を使用する次の SQL 問合せが生成されます。

```sql
SELECT CAST("cc_data_view"."product_category" AS TEXT) AS "product_category",
  CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1,
  2
```

クエリでは、選択した製品カテゴリに結果が制限 **されません**。選択した製品カテゴリが表示されるのはビジュアライゼーションのみです。

![Tableau のドリルアップ ](assets/uc15-tableau-drillup2.png){zoomable="yes"}

または、あるビジュアルが別のビジュアルでの選択の結果であるドリルダウン・ダッシュボードを作成することもできます。 次の例では、**[!UICONTROL 製品カテゴリ]** ビジュアライゼーションをフィルターとして使用して、**[!UICONTROL 製品名]** テーブルを更新しています。 このビジュアライゼーションフィルターはクライアント専用であり、追加の SQL クエリは生成されません。

![Tableau ビジュアライゼーションフィルター ](assets/uc15-tableau-visualizationfilter.png){zoomable="yes"}


>[!TAB Looker]

### 比較

ほとんどのCustomer Journey Analyticsのビジュアライゼーションでは、Looker は同等のエクスペリエンスを提供します。 以下の表を参照してください。

| アイコン | Customer Journey Analyticsのビジュアライゼーション | Power BI デスクトップビジュアライゼーション |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [面グラフ](/help/analysis-workspace/visualizations/area.md) | [ 面グラフ ](https://cloud.google.com/looker/docs/area-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [棒グラフ](/help/analysis-workspace/visualizations/bar.md) | [ 棒グラフ ](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [ 積み重ね棒グラフ ](/help/analysis-workspace/visualizations/bar.md) | [ 棒グラフ ](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [ブレット](/help/analysis-workspace/visualizations/bullet-graph.md) | [ブレットグラフ](https://cloud.google.com/looker/docs/bullet-chart) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [コホートテーブル](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![コンボ](/help/assets/icons/ComboChart.svg) | [コンボ](/help/analysis-workspace/visualizations/combo-charts.md) | [ ビジュアライゼーションのカスタマイズ ](https://cloud.google.com/looker/docs/creating-visualizations#customizing_visualizations_with_chart_settings) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [ドーナツ](/help/analysis-workspace/visualizations/donut.md) | [ドーナツ](https://cloud.google.com/looker/docs/donut-multiples-options) |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [フォールアウト](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [ファネル](https://cloud.google.com/looker/docs/funnel-options) |
| ![ グラフパス ](/help/assets/icons/GraphPathing.svg) | [フロー](/help/analysis-workspace/visualizations/c-flow/flow.md) | [ サンキー ](https://cloud.google.com/looker/docs/sankey) |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [テーブル](https://cloud.google.com/looker/docs/table-options) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [ヒストグラム](/help/analysis-workspace/visualizations/histogram.md) | |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md) | [ 棒グラフ ](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [ 積み重ね横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) | [ 棒グラフ ](https://cloud.google.com/looker/docs/bar-options) |
| ![ ブランチ 3](/help/assets/icons/Branch3.svg) | [ジャーニー キャンバス ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) |  |
| ![ 主要指標 ](/help/assets/icons/KeyMetrics.svg) | [ 主要指標の概要 ](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [折れ線グラフ](/help/analysis-workspace/visualizations/line.md) | [ 折れ線グラフ ](https://cloud.google.com/looker/docs/line-options) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散布図](/help/analysis-workspace/visualizations/scatterplot.md) | [散布図](https://cloud.google.com/looker/docs/scatter-options) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [ セクションヘッダー ](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [変更の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | [ 単一値 ](https://cloud.google.com/looker/docs/single-value-options) |
| ![123](/help/assets/icons/123.svg)</p> | [数値の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | [ 単一値 ](https://cloud.google.com/looker/docs/single-value-options) |
| ![テキスト](/help/assets/icons/Text.svg) | [テキスト](/help/analysis-workspace/visualizations/text.md) | [ 単一値 ](https://cloud.google.com/looker/docs/single-value-options) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [ツリーマップ](/help/analysis-workspace/visualizations/treemap.md) | [ツリーマップ](https://cloud.google.com/looker/docs/treemap) |
| ![タイプ](/help/assets/icons/TwoDots.svg) | [ ベン図 ](/help/analysis-workspace/visualizations/venn.md) | [ ベン図 ](https://cloud.google.com/looker/docs/venn) |

>[!ENDTABS]

+++


## 注意事項

サポートされている各 BI ツールには、Customer Journey Analytics BI 拡張機能の操作に関する注意事項があります。

+++ BI ツール

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

* Power BI Desktop の高度な日付範囲フィルタリングは排他的です。  終了日には、レポートする日付の後の日付を選択する必要があります。 例えば、「**[!UICONTROL が次の日付以降である]**`1/1/2023`**[!UICONTROL および次の日付以前である]**`1/2/2023` などです。
* Power BI Desktop では、接続作成時にデフォルトで **[!UICONTROL 読み込み]** が設定されます。 必ず **[!UICONTROL 直接クエリ]** を使用してください。
* Power BI Desktop は、Power Query を使用してデータ変換を公開します。  Power Query は主にインポート型接続で動作するので、日付や文字列関数などの多くの変換を適用すると、インポート型接続に切り替える必要があるというエラーがスローされます。  クエリ時にデータを変換する必要がある場合は、Power BIが変換自体を行う必要がないように、派生ディメンションと指標を使用する必要があります。
* Power BI Desktop は、日時型の列の処理方法を理解していません。そのため、**[!UICONTROL daterange *hour]**や&#x200B;**[!UICONTROL daterangeminute]**などの&#x200B;**[!UICONTROL daterange *]**X ディメンションはサポートされていません。
* Power BI デスクトップは、デフォルトで、より多くのクエリサービスセッションを使用して複数の接続を確立しようとします。  プロジェクトのPower BI設定に移動し、並列クエリを無効にします。
* Power BI デスクトップは、クライアントサイドのすべての並べ替えと制限を行います。 Power BI Desktop には、結び付けられた値を含む上位 *X* フィルタリング用の異なるセマンティクスもあります。 そのため、Analysis Workspaceで行うのと同じ並べ替えと制限を作成することはできません。
* 2024 年 10 月リリースの以前のバージョンのPower BI デスクトップでは、PostgreSQL データソースが破損しています。 この記事で説明されているバージョンを使用してください。

>[!TAB Tableau Desktop]

* Tableau Desktop の日付範囲フィルタリングは排他的です。 終了日には、レポートする日付の後の日付を選択する必要があります。
* 既定では、シートの行に **[!UICONTROL Daterangemonth]** のような日付または日時次元を追加すると、Tableau Desktop はフィールドを **[!UICONTROL YEAR （）]** 関数でラップします。  目的のデータを取得するには、そのディメンションを選択し、ドロップダウンメニューから、使用する日付関数を選択する必要があります。  例えば、**[!UICONTROL Daterangemonth]** を使用しようとする場合は、**[!UICONTROL 年]** を **[!UICONTROL 月]** に変更します。
* Tableau Desktop では、結果を上位 *X* に制限することは明確ではありません。 結果を明示的に制限するか、計算フィールドと **[!UICONTROL INDEX （）]** 関数を使用することができます。  上位 *X* フィルターをディメンションに追加すると、サポートされていない内部結合を使用して複雑な SQL が生成されます。

>[!TAB Looker]

* Looker には、ノード設定ごとの最大接続数があり、5～100 にする必要があります。  この値を 1 に設定することはできません。  この設定は、Looker 接続が、常に使用可能なクエリサービスセッションを 5 つ以上使用することを意味します。
* Looker は、Customer Journey Analytics データビューに基づくビューを持つプロジェクトを作成できます。 次に、Looker は、LookerML を使用して、データビューで使用できるディメンションと指標に基づいてモデルを作成します。  このプロジェクト ビューは、ソースと一致するように自動的に更新されません。  CJA データビューのディメンション、指標、計算指標またはフィルターに変更や追加を加えた場合、それらの変更は Looker に自動的には表示されません。  プロジェクトビューを手動で更新するか、新しいプロジェクトを作成する必要があります。
* **[!UICONTROL Daterange Date]** や **[!UICONTROL Daterangeday Date]** などの日付または日時フィールドにおける Looker のユーザーエクスペリエンスは、混乱を招きます。
* Looker の日付範囲は、包括的ではなく排他的です。  （前の **[!UICONTROL まで]** はグレーで表示されるので、その側面を見逃すことがあります。  終了日には、レポートする日付の後の日付を選択する必要があります。
* Looker では、指標を指標として自動的に処理しません。  指標を選択すると、デフォルトでは、Looker は指標をクエリ内のディメンションとして扱おうとします。  指標を指標として扱うには、上記のようにカスタムフィールドを作成する必要があります。 ショートカットとして、「**[!UICONTROL ⋮]**」を選択し、「**[!UICONTROL 集計]**」を選択してから「**[!UICONTROL 合計]**」を選択できます。

>[!ENDTABS]

+++
