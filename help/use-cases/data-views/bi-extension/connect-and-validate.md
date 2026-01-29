---
title: 接続と検証
description: Customer Journey Analyticsの様々な BI ツールで BI 拡張機能のユースケースを接続して検証します
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '1864'
ht-degree: 5%

---

# 接続と検証


このユースケースでは、BI ツールからCustomer Journey Analyticsへの接続を設定し、使用可能なデータビューを一覧表示して、使用するデータビューを選択します。

+++ Customer Journey Analytics

この手順では、次のオブジェクトを持つ環境例を参照しています。

* データビュー：**[!UICONTROL C&amp;C - データビュー]** 🅐。
* ディメンション：**[!UICONTROL 製品名]** 🅑 および **[!UICONTROL 製品カテゴリ]** 🅒。
* 指標：**[!UICONTROL 購入売上高]**🅓 および **[!UICONTROL 購入]** 🅔。
* フィルター：**[!UICONTROL 釣り製品]** 🅕。

![Customer Journey Analytics ベースのセットアップ ](../assets/cja-base.png)

ユースケースを確認したら、これらのサンプルオブジェクトを特定の環境に適したオブジェクトに置き換えます。

+++

+++ BI ツール

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. `prod:cja` データベース **[!UICONTROL ドロップダウンメニューから「]**」を選択します。

      ![ クエリサービス資格情報 ](../assets/queryservice-credentials.png)

1. Power BI Desktop を起動します。
   1. メインインターフェイスから、「**[!UICONTROL 他のソースからデータを取得]**」を選択します。
   1. **[!UICONTROL データを取得]** ダイアログで、次の手順を実行します。
      ![PowerBI PostgreSQL データベース ](../assets/powerbi-postgresql.png)
      1. **[!UICONTROL PostgreSQL データベース]** を検索して選択します。
      1. **[!UICONTROL 接続]** を選択します。
   1. **[!UICONTROL PostgreSQL データベース]** ダイアログで、次の手順を実行します。
      ![PowerBI デスクトップサーバーとデータベースの設定 ](../assets/powerbi-serverdatabase.png)
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルの **[!UICONTROL Host]** と **[!UICONTROL Port]** の値をコピーして貼り付け、`:`Server **[!UICONTROL の値として]** で区切ります。 例：`examplecompany.platform-query.adobe.io:80`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL Database]** 値をコピー&amp;ペーストします。 貼り付ける値に `?FLATTEN` を追加します。 例：`prod:cja?FLATTEN`。
      1. **[!UICONTROL Data connectivity mode]** として **[!UICONTROL DirectQuery]** を選択します。
      1. **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL PostgreSQL データベース]** - **[!UICONTROL データベース]** ダイアログで、
      ![PowerBI デスクトップユーザーとパスワード ](../assets/powerbi-userpassword.png)
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、**[!UICONTROL ユーザー名]** および **[!UICONTROL パスワード]** フィールドのExperience Platform **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL ユーザー名]** および **[!UICONTROL パスワード]** の値をコピーします。 [ 有効期限のない認証情報 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect) を使用している場合は、有効期限のない認証情報のパスワードを使用します。
      1. **[!UICONTROL これらの設定を適用するレベルを選択]** のドロップダウンメニューが、前に定義した **[!UICONTROL サーバー]** に設定されていることを確認します。
      1. **[!UICONTROL 接続]** を選択します。
   1. **[!UICONTROL ナビゲーター]** ダイアログで、データビューが取得されます。 この取得には時間がかかる場合があります。 取得すると、Power BI Desktop に以下が表示されます。
      ![Power BI Destkop 読み込みデータ ](../assets/powerbi-navigator-load.png)
      1. 左パネルのリストから **[!UICONTROL public.cc_data_view]** を選択します。
      1. 次の 2 つのオプションがあります。
         1. **[!UICONTROL 読み込み]** を選択して続行し、設定を完了します。
         1. **[!UICONTROL データを変換]** を選択します。 オプションで設定の一部として変換を適用できるダイアログが表示されます。
            ![Power BI デスクトップ変換データ ](../assets/powerbi-transform-data.png)
            * **[!UICONTROL 閉じて適用]** を選択します。
   1. しばらくすると、**[!UICONTROL public.cc_data_view]** が **[!UICONTROL Data]** ペインに表示されます。 ![ChevronRight](/help/assets/icons/ChevronRight.svg) を選択して、ディメンションと指標を表示します。
      ![Power BI Destkop サーバーのデータが読み込まれました ](../assets/powerbi-navigator-loaded.png)


## FLATTEN か NOT か

Power BI Desktop では、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプションは次のとおりです。** |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CloseCircle](/help/assets/icons/CloseCircle.svg) | Power BI デスクトップに「**[!UICONTROL 指定された資格情報では認証できませんでした。 もう一度やり直してください。]** |

### 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/ui/credentials)
* [Power BIをクエリサービスに接続 ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/power-bi)。




>[!TAB Tableau Desktop]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. `prod:cja` データベース **[!UICONTROL ドロップダウンメニューから「]**」を選択します。

      ![ クエリサービス資格情報 ](../assets/queryservice-credentials.png)

1. Tableau の起動
   1. **[!UICONTROL To a Server]** の下の左パネルから「**[!UICONTROL PostgreSQL]**」を選択します。 使用できない場合は、「**[!UICONTROL その他…]**」を選択し、「**[!UICONTROL インストールされているコネクタ]**」から「**[!UICONTROL PostgreSQL]**」を選択します。
      ![Tableau コネクタ ](../assets/tableau-connectors.png)
   1. **[!UICONTROL PostgreSQL]** ダイアログの **[!UICONTROL 一般]** タブで、次の操作を行います。
      ![Tableau へのログインダイアログ ](../assets/tableau-signin.png)
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、**[!UICONTROL ホスト]** をExperience Platform **[!UICONTROL クエリ]** **[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL サーバー]** にコピー&amp;ペーストします。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL Port]** に **[!UICONTROL Port]** をコピー&amp;ペーストします。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルから **[!UICONTROL データベース]** に **[!UICONTROL データベース]** をコピー&amp;ペーストします。 貼り付ける値に `%3FFLATTEN` を追加します。 例：`prod:cja%3FFLATTEN`。
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
        ![Tableau Connected](../assets/tableau-connected.png)
      1. **[!UICONTROL cc_data_view]** エントリをドラッグし、「**[!UICONTROL テーブルをドラッグ]**」と表示されるメインビューにここにエントリをドロップします。
   1. メインウィンドウに、**[!UICONTROL cc_data_view]** データビューの詳細が表示されます。
      ![Tableau Connected](../assets/tableau-validation.png)

## FLATTEN か NOT か

Tableau Desktop は、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプション**。 `%3FFLATTEN` は URL エンコードされたバージョンの `?FLATTEN` であることに注意してください。 |

## 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/ui/credentials)
* [Tableau Desktop をクエリサービスに接続します ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/tableau)。


>[!TAB Looker]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. `prod:cja` データベース **[!UICONTROL ドロップダウンメニューから「]**」を選択します。

      ![ クエリサービス資格情報 ](../assets/queryservice-credentials.png)

1. Looker へのログイン

   1. 左側のパネルから「**[!UICONTROL 管理]**」を選択します。
   1. 「**[!UICONTROL 接続]**」を選択します。
   1. 「**[!UICONTROL 接続を追加]**」を選択します。
   1. **[!UICONTROL データベースを Looker に接続画面]** で確認します。

      ![Looker データベースへの接続 ](../assets/looker-connect.png)

      1. 接続の **[!UICONTROL 名前]** を入力（例：`Example Looker Connection`）
      1. **[!UICONTROL 接続範囲]** として「すべてのプロジェクト **[!UICONTROL が選択されていることを確認]** ます。
      1. ダイアレクトとして **[!UICONTROL PostgreSQL 9.5 以上]** を選択します。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルの **[!UICONTROL ホスト]** 値をコピーし、**[!UICONTROL ホスト]** の値として貼り付けます。 例：`examplecompany.platform-query.adobe.io`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルの **[!UICONTROL Port]** 値をコピーして **[!UICONTROL Port]** に貼り付けます。 例：`80`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルの **[!UICONTROL データベース]** 値をコピーして **[!UICONTROL データベース]** に貼り付けます。 貼り付ける値に `%3FFLATTEN` を追加します。 例：`prod:cja%3FFLATTEN`。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platform **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルの **[!UICONTROL ユーザー名]** 値をコピーして **[!UICONTROL ユーザー名]** に貼り付けます。
      1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platform **[!UICONTROL クエリ]****[!UICONTROL 有効期限が切れる資格情報]** パネルの **[!UICONTROL パスワード]** 値をコピーして **[!UICONTROL パスワード]** に貼り付けます。
      1. **[!UICONTROL オプション設定]** で **[!UICONTROL すべて展開]** を選択します。
      1. ノードごとの **[!UICONTROL 最大接続数]** を `5` に設定します。
      1. **[!UICONTROL SSL]** が有効になっていることを確認します。
      1. 「**[!UICONTROL テスト]**」を選択して、接続をテストします。 画面の上部にバナーが表示され、「Success, can connect JDBC ...**[!UICONTROL のようなメッセージが表示されます]**。
      1. 「**[!UICONTROL 接続]**」を選択し、接続を確立して保存します。
   1. **[!UICONTROL Connections]** インターフェイスに新しい接続が表示されます。
   1. **管理者** から **[!UICONTROL ←]** を選択して、左側のパネルのメインナビゲーションに移動します。
   1. **[!UICONTROL 開発]** を選択します。
   1. **[!UICONTROL プロジェクト]** を選択します。
   1. LookML プロジェクトで **[!UICONTROL 新規モデル]** を選択します。
   1. を設定して、他のユーザーに影響を与えないようにします。 プロンプトが表示されたら、「開発モードに入る」を選択します。
   1. **[!UICONTROL モデルを作成]** エクスペリエンスで、次の操作を行います。
      1. データベース接続 **[!UICONTROL ➊選択します]**。
         1. **[!UICONTROL データベース接続を選択]** でデータベース接続を選択します。 例：**[!UICONTROL example_looker_connection]**。
         1. **[!UICONTROL このモデルの新しい LookML プロジェクトを作成]** でプロジェクトに名前を付けます。 （`example: example_looker_project` 用）。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. テーブル **[!UICONTROL ➋選択]**:
         1. **[!UICONTROL 公開]** を選択し、Customer Journey Analytics データビューが選択されていることを確認します。 例：![SelectBox](/help/assets/icons/SelectBox.svg)**[!UICONTROL cc_data_view]**。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. **[!UICONTROL ➌でプライマリキーを選択し]** す。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. で、作成 **[!UICONTROL ➍る探索を選択します]**
         1. 必ずビューを選択してください。 例：**[!UICONTROL cc_data_view.view]**。
         1. 「**[!UICONTROL 次へ]**」を選択します。
      1. モデル名 **[!UICONTROL ➎入力し]** す。
         1. モデルに名前を付けます。 例：`example_looker_model`。
      1. 「**[!UICONTROL データを入力して調査]**」を選択します。

   Looker の **[!UICONTROL 参照]** インターフェイスにリダイレクトされ、データを参照する準備が整います。



## FLATTEN か NOT か

Looker では、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプション**。 `%3FFLATTEN` は URL エンコードされたバージョンの `?FLATTEN` であることに注意してください。 |

## 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/ui/credentials)


>[!TAB Jupyter Notebook]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. `prod:cja` データベース **[!UICONTROL ドロップダウンメニューから「]**」を選択します。

      ![ クエリサービス資格情報 ](../assets/queryservice-credentials.png)

1. Jupyter Notebook 環境を実行するための専用の Python 仮想環境をセットアップしていることを確認します。
1. 仮想環境に必要なライブラリがインストールされていることを確認します。
   * ipython-sql: `pip install ipython-sql`。
   * psycopg2-binary: `pip install psycopg-binary`。
   * sqlalchemy: pip `install sqlalchemy`。

1. 仮想環境 `jupyter notebook` から Jupyter Notebook を起動します。
1. 新しいノートブックを作成するか、[ このサンプルノートブック ](../assets/BI-Extension.ipynb.zip) をダウンロードします。
1. 最初のセルに、次のように入力して実行します。

   ```
   %config SqlMagic.style = '_DEPRECATED_DEFAULT'
   ```

1. 新しいセルに、接続の設定パラメーターを入力します。 ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platform **[!UICONTROL クエリ]** **[!UICONTROL 有効期限が切れる資格情報]** パネルの値をコピーして、設定パラメーターに必要な値に貼り付けます。 次に例を示します。

   ```
   import ipywidgets as widgets
   from IPython.display import display
   
   config_host = widgets.Text(description='Host:', value='example.platform-query-stage.adobe.io',
                           layout=widgets.Layout(width="600px"))
   display(config_host)
   config_port = widgets.IntText(description='Port:', value=80,
                              layout=widgets.Layout(width="200px"))
   display(config_port)
   config_db = widgets.Text(description='Database:', value='prod:cja',
                         layout=widgets.Layout(width="300px"))
   display(config_db)
   config_username = widgets.Text(description='Username:', value='EC582F955C8A79F70A49420E@AdobeOrg',
                               layout=widgets.Layout(width="600px"))
   display(config_username)
   config_password = widgets.Password(description='Password:', value='***',
                                   layout=widgets.Layout(width="600px"))
   display(config_password)
   ```

1. セルを実行します。
1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platformの **[!UICONTROL クエリ]** **[!UICONTROL 有効期限が切れる資格情報]** パネルから Jupyter Notebook の **[!UICONTROL パスワード]** フィールドにパスワードをコピー&amp;ペーストします。

   ![Jupter Notebook 設定の手順 1](../assets/jupyter-config-step1.png)

1. 新しいセルに、SQL 拡張機能を読み込むためのステートメント、必要なライブラリを入力し、Customer Journey Analyticsに接続します。

   ```python
   %load_ext sql
   from sqlalchemy import create_engine
   %sql postgresql://{config_username.value}:{config_password.value}@{config_host.value}:{config_port.value}/{config_db.value}?sslmode=require
   ```

   シェルを実行します。 出力は表示されませんが、セルは警告なしで実行する必要があります。

   ![Jupyer Notebook 設定手順 4](../assets/jupyter-config-step2.png)

1. 新しい呼び出しで、ステートメントを入力して、接続に基づいて使用可能なデータビューのリストを取得します。

   ```python
   %%sql
   SELECT n.nspname as "Schema",
      c.relname as "Name",
      CASE c.relkind WHEN 'r' THEN 'table' WHEN 'v' THEN 'view' WHEN 'm' THEN 'materialized view' WHEN 'i' THEN 'index' WHEN 'S' THEN 'sequence' WHEN 's' THEN 'special' WHEN 't' THEN 'TOAST table' WHEN 'f' THEN 'foreign table' WHEN 'p' THEN 'partitioned table' WHEN 'I' THEN 'partitioned index' END as "Type",
      pg_catalog.pg_get_userbyid(c.relowner) as "Owner"
   FROM pg_catalog.pg_class c
   LEFT JOIN pg_catalog.pg_namespace n ON n.oid = c.relnamespace
   WHERE c.relkind IN ('v','')
      AND n.nspname <> 'pg_catalog'
      AND n.nspname !~ '^pg_toast'
      AND n.nspname <> 'information_schema'
      AND pg_catalog.pg_table_is_visible(c.oid)
      AND c.relname NOT LIKE '%test%'
      AND c.relname NOT LIKE '%ajo%'
   ORDER BY 1,2;
   ```

   シェルを実行します。 以下のスクリーンショットに同様に出力が表示されます。

   ![Jupyter Notebook 設定の手順 5](../assets/jupyter-config-step3.png)

   データビューのリストに **[!UICONTROL cc_data_view]** が表示されます。

## FLATTEN か NOT か

Jupyter Notebook では、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CloseCircle](/help/assets/icons/CloseCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプション**。 `%3FFLATTEN` は URL エンコードされたバージョンの `?FLATTEN` であることに注意してください。 |

## 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/ui/credentials)

>[!TAB RStudio]

1. Experience Platform クエリサービス UI から必要な資格情報とパラメーターにアクセスします。

   1. Experience Platform サンドボックスに移動します。
   1. 左パネルから ![ クエリ ](/help/assets/icons/DataSearch.svg)**[!UICONTROL クエリ]** を選択します。
   1. **[!UICONTROL クエリ]** インターフェイスの「**[!UICONTROL 資格情報]**」タブを選択します。
   1. `prod:cja` データベース **[!UICONTROL ドロップダウンメニューから「]**」を選択します。

      ![ クエリサービス資格情報 ](../assets/queryservice-credentials.png)

1. RStudio を起動します。
1. 新しい R Markdown ファイルを作成するか、[ このサンプル R Markdown ファイル ](../assets/BI-Extension.Rmd.zip) をダウンロードします。
1. 最初のチャンクでは、` ```{r} ` ～ ` ``` ` の間に次のステートメントを入力します。 ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platform **[!UICONTROL クエリ]** **[!UICONTROL 資格情報の有効期限]** パネルから `host`、`dbname`、`user` などの様々なパラメーターに必要な値にコピー&amp;ペーストします。 次に例を示します。

   ```R
   library(rstudioapi)
   library(DBI)
   library(dplyr)
   library(tidyr)
   library(RPostgres)
   library(ggplot2)
   
   host <- rstudioapi::showPrompt(title = "Host", message = "Host", default = "orangestagingco.platform-query-stage.adobe.io")
   dbname <- rstudioapi::showPrompt(title = "Database", message = "Database", default = "prod:cja?FLATTEN")
   user <- rstudioapi::showPrompt(title = "Username", message = "Username", default = "EC582F955C8A79F70A49420E@AdobeOrg")
   password <- rstudioapi::askForPassword(prompt = "Password")
   ```

1. チャンクを実行します。 「**[!UICONTROL Host]**」、「**[!UICONTROL Database]**」、「**[!UICONTROL User]**」の入力を求められます。 前の手順の一部として指定した値をそのまま使用します。
1. ![ コピー ](/help/assets/icons/Copy.svg) を使用して、Experience Platform **[!UICONTROL クエリ]** **[!UICONTROL 資格情報の有効期限]** パネルから RStudio の **[!UICONTROL パスワード]** ダイアログプロンプトにパスワードをコピー&amp;ペーストします。

   ![RStudio 設定手順 1](../assets/rstudio-config-step1.png)

1. 新しいチャンクを作成し、` ``` {r} ` ～ ` ``` ` の間に次のステートメントを入力してください。

   ```R
   con <- dbConnect(
      RPostgres::Postgres(),
      host = host,
      port = 80,
      dbname = dbname,
      user = user,
      password = password,
      sslmode = 'require'
   )
   ```

1. チャンクを実行します。 接続に成功した場合は、出力は表示されません。


1. 新しいチャンクを作成し、` ``` {r} ` ～ ` ``` ` の間に次のステートメントを入力してください。

   ```R
   views <- dbListTables(con)
   print(views)
   ```

1. チャンクを実行します。 `character(0)` が唯一の出力として表示されます。


1. 新しいチャンクを作成し、` ``` {r} ` ～ ` ``` ` の間に次のステートメントを入力してください。

   ```R
   glimpse(dv)
   ```

1. チャンクを実行します。 以下のスクリーンショットに同様に出力が表示されます。

   ![RStudio 構成の手順 2](../assets/rstudio-config-step2.png)

## FLATTEN か NOT か

RStudio は、`FLATTEN` パラメーターに対して次のシナリオをサポートしています。 詳しくは、[ ネストされたデータの統合 ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data) を参照してください。

| FLATTEN パラメータ | 例 | サポート | 備考 |
|---|---|:---:|---|
| なし | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **推奨されるオプション**。 |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CloseCircle](/help/assets/icons/CloseCircle.svg) | |

## 詳細情報

* [前提条件](/help/data-views/bi-extension.md#prerequisites)
* [ 資格情報ガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/ui/credentials)

>[!ENDTABS]

+++
