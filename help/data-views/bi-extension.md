---
title: Customer Journey Analytics BI 拡張機能
description: Power BIまたは Tableau Desktop を使用して、Customer Journey Analytics BI 拡張機能を使用してデータビューにアクセスする方法について説明します。
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 30e3df15aecec0bab180cd06e0ae7c79f58cdf44
workflow-type: tm+mt
source-wordcount: '3620'
ht-degree: 53%

---

# Customer Journey Analytics BI 拡張機能

{{select-package}}

[!DNL Customer Journey Analytics BI extension] を使用すると、Customer Journey Analytics で定義した[データビュー](./data-views.md)への SQL アクセスが可能になります。データエンジニアやアナリストは、Power BI、Tableau Desktop、その他のビジネスインテリジェンスおよびビジュアライゼーションツール（BI ツールとも呼ばれます）に精通している可能性があります。 Customer Journey Analytics ユーザーが Analysis Workspace プロジェクトを作成する際に使用しているものと同じデータビューに基づいて、レポートおよびダッシュボードを作成できるようになりました。

Adobe Experience Platform [クエリサービス](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home)は、Experience Platform のデータレイクで使用可能なデータへの SQL インターフェイスです。[!DNL Customer Journey Analytics BI extension] を有効にすると、[!DNL Query Service] の機能が拡張され、Customer Journey Analytics データビューを [!DNL Query Service] セッションのテーブルまたはビューとして表示できるようになります。その結果、[!DNL Query Service] を PostgresSQL インターフェイスとして使用するビジネスインテリジェンスツールは、この拡張機能のメリットをシームレスに受けられます。

主なメリットは次のとおりです。

* BI ツール自体内で Customer Journey Analytics データビューの同等の表示域を再作成する必要はありません。<br/> データビューの機能について詳しくは、[ データビュー ](data-views.md) を参照して、再作成する必要があるものを理解します。
* BI ツールと Customer Journey Analytics 間のレポートと分析の一貫性が向上します。
* Customer Journey Analytics データを、BI ツールで既に使用可能な他のデータソースと組み合わせます。

## 前提条件

この機能を使用するには、有効期限のある資格情報または有効期限のない資格情報を使用して、BI ツールを [!DNL Customer Journey Analytics BI extension] に接続します。 [ 資格情報ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) には、有効期限のある資格情報または有効期限のない資格情報の設定に関する詳細が記載されています。
CJA 権限を設定するための追加手順を以下に示します
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### 資格情報の期限切れ

有効期限が切れる資格情報を使用するには、次の操作を実行します。

* Experience PlatformとCustomer Journey Analyticsへのアクセス権を付与します。
* Customer Journey Analyticsへの製品管理者アクセス権を付与して、接続およびデータビューを表示、編集、更新または削除できるようにします。

または、次のことができます。

* アクセスするデータビューへのアクセス権を付与します。
* Customer Journey Analytics BI 拡張機能へのアクセス権を付与します。

### 有効期限が切れていない資格情報

有効期限のない認証情報を使用するには：

* 有効期限のない認証情報をExperience Platformに作成します。
* [ 資格情報の有効期限 ](#Expiring-credentials) に記載されている手順に従って、有効期限のない資格情報へのアクセス権を付与します。

特に [ 製品管理者の追加の権限 ](../technotes/access-control.md) および [4}Admin ConsoleのCustomer Journey Analyticsの権限 ](../technotes/access-control.md#product-admin-additional-permissions) について詳しくは、{ 顧客ジャーニーのアクセス制御 ](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console) を参照してください。[


## 用途

[!DNL Customer Journey Analytics BI extension] 機能を使用するには、SQL を直接使用することも、特定の BI ツールで使用可能なドラッグ＆ドロップエクスペリエンスを使用することもできます。

### SQL

この機能は、クエリエディターまたは標準の PostgreSQL コマンドラインインターフェイス（CLI）クライアントを使用して SQL 文で直接使用できます。

+++ クエリ編集者

Adobe Experience Platformで：

1. 左側のパネルの&#x200B;**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

1. ![クエリを作成](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;クエリを作成&#x200B;**]** を選択します。

1. **[!UICONTROL データベース]** ドロップダウンメニューのデータベースのリストから、サンドボックスの `cja` データベースを選択します。 例：`prod:cja`。

1. クエリを実行するには、SQL ステートメントを入力して「![ 再生 ](assets/Smock_Play_18_N.svg)」ボタンを選択します（または、`[SHIFT]` + `[ENTER]` キーを押します）。

+++


+++ PostgreSQL CLI

1. Adobe Experience Platformで PostgresSQL 資格情報を検索してコピーします。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. **[!UICONTROL データベース]** ドロップダウンメニューのデータベースのリストから、サンドボックスの `cja` データベースを選択します。 例：`prod:cja`。

   1. コマンド文字列をコピーするには、「**[!UICONTROL ** PSQL コマンド ](assets/Smock_Copy_18_N.svg)」セクションの ![ コピー **]** を使用します。

1. コマンドウィンドウまたはターミナルウィンドウを開きます。

1. ログインしてクエリの実行を開始するには、ターミナルにコマンド文字列を貼り付けます。

+++

詳しくは、[ クエリエディター UI ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) を参照してください。


### BI ツール

現在、[!DNL Customer Journey Analytics BI extension] はPower BIおよび Tableau Desktop でのみサポートおよびテストされています。 PSQL インターフェイスを使用するその他の BI ツールも同様に機能する場合がありますが、まだ正式にはサポートされていません。

+++ Power BI

1. Adobe Experience Platformで PostgresSQL 資格情報の詳細を調べます。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. **[!UICONTROL データベース]** ドロップダウンメニューのデータベースのリストから、サンドボックスの `cja` データベースを選択します。 例：`prod:cja`。

   1. Power BI で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

1. Power BI の場合：

   1. メインウィンドウで、上部のツールバーから「**[!UICONTROL **&#x200B;データを取得&#x200B;**]**」を選択します。

   1. 左側のパネルで「**[!UICONTROL その他...]**」を選択します。

   1. **データを取得**&#x200B;画面で `PostgresSQL` を検索し、リストから 「**[!UICONTROL ** PostgreSQL データベース&#x200B;**]**」を選択します。

   1. **[!UICONTROL ** PostgreSQL データベース&#x200B;**]**&#x200B;ダイアログの場合：

      1. Experience Platform クエリ **[!UICONTROL ** 資格情報 **]** の [!UICONTROL Host] パラメーターを **[!UICONTROL ** Server **]** テキストフィールドに貼り付けます。

      1. Experience Platform クエリ **[!UICONTROL ** 資格情報 **]** の [!UICONTROL Database] パラメーターを **[!UICONTROL ** Database **]** テキストフィールドに貼り付けます。

         `?FLATTEN` を&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターに追加すると、例えば、`prod:cja?FLATTEN` のように読み込まれます。詳しくは、[サードパーティの BI ツールで使用するネストされたデータ構造のフラット化](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data)を参照してください。

      1. **[!UICONTROL Data Connectivity]** モードのプロンプトが表示されたら、「**[!UICONTROL DirectQuery]**」を選択します。

      1. **[!UICONTROL ユーザー名]**&#x200B;と&#x200B;**[!UICONTROL パスワード]**&#x200B;の入力を求められます。Experience Platform クエリ[!UICONTROL 資格情報]の同等のパラメーターを使用します。


   1. ログインに成功すると、Customer Journey Analytics データビューテーブルが Power BI **[!UICONTROL ** Navigator **]** に表示されます。

   1. 使用するデータビューテーブルを選択し、「**[!UICONTROL **&#x200B;読み込み&#x200B;**]**」を選択します。

   選択した 1 つ以上のテーブルに関連付けられたすべてのディメンションと指標が右側のパネルに表示され、ビジュアライゼーションで使用できるようになります。

   詳しくは [ クエリサービスへのPower BIの接続 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) を参照してください。 詳細な例については、[BI 拡張機能の使用例 ](/help/use-cases/data-views/bi-extension-usecases.md) も参照してください。

+++

+++Tableau Desktop

1. Adobe Experience Platformで PostgresSQL 資格情報の詳細を調べます。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. **[!UICONTROL データベース]** ドロップダウンメニューのデータベースのリストから、サンドボックスの `cja` データベースを選択します。 例：`prod:cja`。

   1. ![ コピー ](assets/Smock_Copy_18_N.svg) を使用して、Tableau Desktop で必要に応じて各 Postgres 資格情報パラメーター（[!UICONTROL  ホスト ]、[!UICONTROL  ポート ]、[!UICONTROL  データベース ]、[!UICONTROL  ユーザー名 ] など）をコピーします。

1. Tableau Desktop の場合：

   1. 左側のパネルの&#x200B;**[!UICONTROL **&#x200B;サーバーへ&#x200B;**]**&#x200B;から「**[!UICONTROL **&#x200B;その他&#x200B;**]**」を選択します。

   1. リストから「**[!UICONTROL ** PostgreSQL **]**」を選択します。

   1. [!UICONTROL PostgreSQL] ダイアログの場合：

      1. Experience Platform クエリ **[!UICONTROL ** 資格情報 **]** から [!UICONTROL Host] パラメーターを **[!UICONTROL ** Server **]** テキストフィールドに貼り付けます。

      1. Experience Platform クエリ **[!UICONTROL ** 資格情報 **]** の [!UICONTROL Port] パラメーターを **[!UICONTROL ** Port **]** テキストフィールドに貼り付けます。

      1. Experience Platform クエリ **[!UICONTROL ** 資格情報 **]** の [!UICONTROL Database] パラメーターを **[!UICONTROL ** Database **]** テキストフィールドに貼り付けます。

         `%3FFLATTEN` を&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターに追加すると、例えば、`prod:cja%3FFLATTEN` のように読み込まれます。詳しくは、[サードパーティの BI ツールで使用するネストされたデータ構造のフラット化](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data)を参照してください。

      1. **[!UICONTROL **&#x200B;認証&#x200B;**]**&#x200B;リストから&#x200B;**[!UICONTROL **&#x200B;ユーザー名とパスワード&#x200B;**]**&#x200B;を選択します。

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ユーザー名&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;ユーザー名&#x200B;**]**」テキストフィールドにペーストします。

      1. Experience Platform クエリ **[!UICONTROL ** 資格情報 **]** の [!UICONTROL  パスワード ] パラメーターを **[!UICONTROL ** パスワード **]** テキストフィールドに貼り付けます。

      1. 「**[!UICONTROL ** ログイン **]**」を選択します。

   1. Customer Journey Analyticsのデータビューは、「テーブル **[!UICONTROL ** リストにテーブルとして表示さ **]** ます。

   1. 使用するテーブルをキャンバス上でドラッグします。

   これで、データビューテーブルのデータを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[Tableau のクエリサービスへの接続 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) を参照してください。 詳細な例については、[BI 拡張機能の使用例 ](/help/use-cases/data-views/bi-extension-usecases.md) も参照してください。

+++

+++ Looker

1. Adobe Experience Platformで PostgresSQL 資格情報の詳細を調べます。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. **[!UICONTROL データベース]** ドロップダウンメニューのデータベースのリストから、サンドボックスの `cja` データベースを選択します。 例：`prod:cja`。

   1. ![ コピー ](assets/Smock_Copy_18_N.svg) を使用して、Looker で必要に応じて各 Postgres 認証情報パラメーター（[!UICONTROL  ホスト ]、[!UICONTROL  ポート ]、[!UICONTROL  データベース ]、[!UICONTROL  ユーザー名 ] などを）をコピーします。

1. Looker で：

   1. 左パネルから **[!UICONTROL 管理者]** を選択します。
   1. **[!UICONTROL 接続]** を選択します。
   1. **[!UICONTROL 接続を追加]** を選択します。
   1. **[!UICONTROL データベースを Looker に接続]** 画面で、新しい接続を設定する際に適切な値を貼り付けます。 ダイアレクトとして **[!UICONTROL PostgreSQL 9.5 以降]** を選択していることを確認してください。
   1. **[!UICONTROL テスト]** を選択して、接続をテストします。
   1. 正常に終了したら、「**[!UICONTROL 更新]**」を選択して接続を保存します。

   これで、データビューテーブルのデータを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[ クエリサービスへの Looker の接続 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/looker) を参照してください。 詳細な例については、[BI 拡張機能の使用例 ](/help/use-cases/data-views/bi-extension-usecases.md) も参照してください。

+++

+++ Jupyter Noteboook

1. Adobe Experience Platformで PostgresSQL 資格情報の詳細を調べます。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. **[!UICONTROL データベース]** ドロップダウンメニューのデータベースのリストから、サンドボックスの `cja` データベースを選択します。 例：`prod:cja`。

   1. Jupyter Notebook で必要に応じて、![ コピー ](assets/Smock_Copy_18_N.svg) を使用して、各 Postgres 資格情報パラメーター（[!UICONTROL  ホスト ]、[!UICONTROL  ポート ]、[!UICONTROL  データベース ]、[!UICONTROL  ユーザー名 ] など）をコピーします。

1. Jupyter Notebook で以下を行います。

   1. 必要なライブラリを使用していることを確認します。
   1. 接続を設定して実行する際は、適切な値を使用します。
   1. 関連するクエリを実行して、接続をテストします。

   成功したら、データを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[ クエリサービスへの Jupyter Notebook の接続 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/jupyter-notebook) を参照してください。 詳細な例については、[BI 拡張機能の使用例 ](/help/use-cases/data-views/bi-extension-usecases.md) も参照してください。

+++

+++ RStudio

1. Adobe Experience Platformで PostgresSQL 資格情報の詳細を調べます。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. **[!UICONTROL データベース]** ドロップダウンメニューのデータベースのリストから、サンドボックスの `cja` データベースを選択します。 例：`prod:cja`。

   1. Jupyter Notebook で必要に応じて、![ コピー ](assets/Smock_Copy_18_N.svg) を使用して、各 Postgres 資格情報パラメーター（[!UICONTROL  ホスト ]、[!UICONTROL  ポート ]、[!UICONTROL  データベース ]、[!UICONTROL  ユーザー名 ] など）をコピーします。

1. RStudio の場合：

   1. 必要なライブラリを使用していることを確認します。
   1. 接続を設定して実行する際は、適切な値を使用します。
   1. 関連するクエリを実行して、接続をテストします。

   成功したら、データを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[ クエリサービスへの RStudio の接続 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/rstudio) を参照してください。 詳細な例（代わりに RPostgres パッケージを使用）については、[BI 拡張機能の使用例 ](/help/use-cases/data-views/bi-extension-usecases.md) も参照してください。

+++

使用可能な様々なツールの概要と詳細情報については、[クエリサービスへのクライアントの接続](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview)を参照してください。

Customer Journey Analytics BI 拡張機能を使用して様々なユースケースを達成する方法については、[ ユースケース ](/help/use-cases/data-views/bi-extension-usecases.md) を参照してください。

## 機能

デフォルトでは、データビューには、わかりやすい名前から生成されたテーブルセーフ名が付けられます。例えば、[!UICONTROL My Web Data View] という名前のデータビューは、ビュー名が `my_web_data_view` です。 データビューの BI ツールで使用する優先名を定義できます。 詳しくは、[ データ表示設定 ](create-dataview.md#settings) を参照してください。

データビュー ID をテーブル名として使用する場合は、接続時にデータベース名にオプションの `CJA_USE_IDS` 設定を追加できます。例えば、`prod:cja?CJA_USE_IDS` は、`dv_ABC123` のような名前でデータビューを表示します。

### データガバナンス

Customer Journey Analytics のデータガバナンス関連の設定は、Adobe Experience Platform から継承されます。Customer Journey Analytics と Adobe Experience Platform のデータガバナンスの統合により、機密性の高い Customer Journey Analytics データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platform で使用されるデータセットに関して作成されたプライバシーラベルとポリシーは、 Customer Journey Analytics データビューワークフローで表示できます。したがって、[!DNL Customer Journey Analytics BI extension] を使用してクエリされたデータが、定義されたプライバシーラベルやポリシーに準拠していない場合、適切な警告やエラーが表示されます。

### データビューのリスト

標準の PostgreSQL CLI では、`\dv` を使用してビューをリストできます

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### ネスト化とフラット化

デフォルトでは、データビューのスキーマは、元の XDM スキーマと同様に、ネストされた構造を使用します。また、この統合では、`FLATTEN` オプションもサポートされています。このオプションを使用すると、データビュー（およびセッション内の他のテーブル）のスキーマを強制的にフラット化できます。フラット化により、構造化スキーマをサポートしていない BI ツールでも簡単に使用できるようになります。詳しくは、[クエリサービスでのネストされたデータ構造の操作](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data)を参照してください。


### デフォルトと制限事項

BI 拡張機能を使用する場合、次の追加のデフォルトと制限が適用されます。

* BI 拡張機能では、クエリ結果の行制限が必要です。 デフォルトは 50 ですが、`LIMIT n` を使用して SQL でこれを上書きできます（`n` は 1～50000）。
* BI 拡張機能では、計算に使用する行を制限する日付範囲が必要です。 デフォルトは過去 30 日間ですが、特殊 [`timestamp`](#timestamp) または [`daterange`](#date-range) 列を使用して、SQL `WHERE` 句でこれを上書きできます。
* BI 拡張機能には、集計クエリが必要です。 `SELECT * FROM ...` のような SQL を使用して、生の基になる行を取得することはできません。 集計クエリには、大まかに言えば、次を使用します。
   * `SUM` や `COUNT` を使用して合計を選択します。<br/> 例：`SELECT SUM(metric1), COUNT(*) FROM ...`
   * ディメンション別に分類された指標を選択します。 <br/> 例：`SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * 個別の指標値を選択します。<br/> 例：`SELECT DISTINCT dimension1 FROM ...`

     詳しくは、を参照してください [ サポートされている SQL](#supported-sql)。


### サポートされる SQL

サポートされている SQL のタイプの完全なリファレンスについては、[クエリサービス SQL リファレンス](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview)を参照してください。

使用可能な SQL の例については、次の表を参照してください。

+++ 例

| パターン | 例 |
|---|---|
| スキーマの検出 | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| ランクまたは分類 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| `HAVING` 句 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| 個別、上位の<br/>ディメンション値 | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| 指標の合計値 | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| マルチディメンションの<br/>分類<br/>と上位の個別 | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Subselect:<br/>Filter additional<br/>results | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Subselect:<br/> クエリの実行 <br/> データビュー | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Subselect:<br/> レイヤー化されたソース、<br/> フィルタリング、<br/> および集約 | サブ選択を使用したレイヤー化：<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>CTE WITH を使用するレイヤー：<br/><pre>行を（<br/> を\_に（<br/>    SELECT * FROM data_ares<br/>    ここで、\&#39;timestamp\&#39; BETWEEN &#39;2021-01&#39; AND &#39;2021-02-01&#39;<br/>） <br/>\_.item, \_.units FROM \_<br/> WHERE \_.item IS NOT NULL<br/>） <br/>SELECT rows.item, SUM （rows.units） AS UNITS<br/>WHERE rows.item IN （&#39;A&#39;, &#39;B&#39;, &#39;C&#39;） <br/>GROUP BY ROWS.ITEM</pre> |
| <br/>指標をディメンションの前<br/>に配置するか、ディメンションと<br/>混合する場所を選択します | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### ディメンション

デフォルトで使用可能なディメンションや、データビューで定義されたディメンションを選択できます。ID でディメンションを選択します。

### 指標

選択できる指標は次のとおりです。

* デフォルトで使用可能な指標。
* データビューで定義されます。
* ユーザーがアクセスできるデータビューと互換性のある計算指標。

他の SQL ソースの場合と同様に、`SUM(metric)` 式に含まれる ID で指標を選択します。

以下が可能です：

* `SELECT COUNT(*)` または `COUNT(1)` を使用して、発生件数指標を取得する。
* `SELECT COUNT(DISTINCT dimension)` または `SELECT APPROX_COUNT_DISTINCT(dimension)` を使用して、ディメンションの個別概算値をカウントする。詳しくは、[ 個別の値のカウント ](#counting-distinct-values) を参照してください。
* [ インライン計算 ](#inline-calculations)：指標をその場で組み合わせたり、計算を行ったりする。

#### ユニーク値のカウント

Customer Journey Analytics の仕組みの基本的な性質により、正確な個別のカウントを取得できる唯一のディメンションは、`adobe_personid` ディメンションです。次の SQL ステートメントは、`SELECT COUNT(DISTINCT adobe_personid)` または `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` は、個別のユーザーの数であるデフォルトの人物指標の値を返します。 その他のディメンションの場合は、おおよその個別のカウントが返されます。

#### 条件付き指標

`IF` 句または `CASE` 句を `SUM` 関数または `COUNT` 関数に埋め込んで、選択した指標に固有のフィルタリングを追加できます。これらの句を追加することは、Workspace レポートテーブルの指標列にフィルターを適用することと似ています。

例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### インライン計算

`SELECT` ール内の指標式に追加の数式を適用できます。 計算指標で数学を定義する代わりに、この数学を使用できます。 次の表に、サポートされている式の種類を示します。

| 演算子または関数 | 詳細 |
|---|---|
| `+`、`-`、`*`、`/` および `%` | 加算、減算、乗算、除算、剰余演算 |
| `-X` または`+X` | 符号または指標の変更（X は指標式） |
| `PI()` | π 定数 |
| `POSITIVE`、`NEGATIVE`、`ABS`、`FLOOR`、`CEIL`、`CEILING`、`EXP`、`LN`、`LOG10`、`LOG1P`、`SQRT`、`CBRT`、`DEGREES`、`RADIANS`、`SIN`、`COS`、`TAN`、`ACOS`、`ASIN`、`ATAN`、 `COSH`、`SINH` および `TANH` | 単項数学関数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二項数学関数 |

{style="table-layout:auto"}

### 特殊な列

#### タイムスタンプ

`timestamp` 特殊列は、クエリの日付範囲を指定するために使用されます。日付範囲は、`BETWEEN` 式または `timestamp` `>`、`>=`、`<`、`<=` チェックの `AND` を組み合わせて定義できます。
`timestamp` はオプションで、全範囲を指定しない場合は、デフォルトが使用されます。

* 最小値のみを指定している場合（`timestamp > X` または ` timestamp >= X`）、範囲は X から現在までです。
* 最大値（`timestamp < X` または `timestamp <= X`）のみを指定した場合、範囲は X から 30 日を引いた X です。
* 何も指定されない場合、範囲は現在から今まで–30 日です。

タイムスタンプ範囲は、RankRequest の日付範囲グローバルフィルターに変換されます。
タイムスタンプフィールドを日付/時間関数で使用して、イベントのタイムスタンプを解析または切り捨てることもできます。

#### 日付範囲

`daterange` 特別列は `timestamp` と同様に機能しますが、フィルタリングは 1 日に制限されます。 `daterange` もオプションで、`timestamp` と同じ範囲のデフォルトが設定されます。
`daterange` フィールドは、イベントの日付を解析または切り捨てるために日付/時間関数でも使用できます。

`daterangeName` 特別列は、`Last Quarter` のような名前付き日付範囲を使用してクエリをフィルタリングするために使用できます。

>[!NOTE]
>
>Power BIは、1 日未満（時、30 分、5 分など）の `daterange` 指標をサポートしていません。
>

#### フィルター ID

`filterId` 特殊列はオプションで、外部で定義されたフィルターをクエリに適用するために使用されます。外部で定義されたフィルターをクエリに適用することは、Workspace のパネルにフィルターをドラッグすることと似ています。複数のフィルター ID を使用する場合は、それらを `AND` イライトします。

`filterId` と共に、`filterName` を使用して、ID の代わりにフィルターの名前を使用できます。

### Where 句

`WHERE` 句は次の 3 つの手順で処理されます。

1. `timestamp`、`daterange` または `daterangeName` の特別なフィールドから日付範囲を検索します。

1. フィルターに含める、外部で定義された `filterId` または `filterName` を見つけます。

1. 残りの式をアドホックフィルターに変換します。

この処理は、`WHERE` 句の最初のレベルの `AND` を解析することによって行われます。トップレベルの `AND` 式は、上記のいずれかに一致する必要があります。 最初のレベルの `AND` より深い部分や、`WHERE` 句が最上位レベルで `OR` を使用している場合は、アドホックフィルターとして処理されます。

### ソート順序

デフォルトでは、クエリは最初に選択された指標によって結果を降順に並べ替えます。`ORDER BY ... ASC` または `ORDER BY ... DESC` を指定すると、デフォルトの並べ替え順序を上書きできます。`ORDER BY` を使用する場合は、最初に選択した指標に対して `ORDER BY` を指定する必要があります。

指標の前に `-`（マイナス）を使用して順序を入れ替えることもできます。次の 2 つの文の順序は同じになります。

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般的な関数のサポート

| 関数 | 例 | 詳細 |
|---|---|---|
| [ キャスト ](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` または <br/> `` `timestamp`::string `` | 型キャストは現在サポートされていませんが、エラーはスローされません。`CAST` 関数は無視されます。 |
| [タイムスタンプ](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | `WHERE` 句内で使用するタイムスタンプとして時刻文字列を解析します。 |
| [ 終了タイムスタンプ ](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 時刻文字列を `WHERE` 句内で使用するタイムスタンプとして解析し、オプションでその時刻文字列の形式を指定します。 |
| [日付](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | `WHERE` 句内で使用するために、日付文字列をタイムスタンプとして解析します。 |
| [ 終了日 ](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 日付文字列を `WHERE` 句内で使用するタイムスタンプとして解析し、オプションでその日付文字列の形式を指定します。 |

{style="table-layout:auto"}

### Dimension関数のサポート

以下の関数は、`SELECT`、`WHERE` 句または条件付き指標のディメンションで使用できます。

**文字列関数**

| 関数 | 例 | 詳細 |
|---|---|---|
| [Lower](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 渡されたフィールドで動的ディメンション ID を生成します。 |

{style="table-layout:auto"}

**日時関数**

| 関数 | 例 | 詳細 |
|---|---|---|
| [年](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [月](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [日](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [曜日](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。 |
| [年間通算日](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [週](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [四半期](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [時間](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。 |
| [分](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [ 抽出 ](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。この関数の一部では、わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。<br/>サポートされる一部は次のとおりです。<br>- キーワード：`YEAR`、`MONTH`、`DAYOFMONTH`、`DAYOFWEEK`、`DAYOFYEAR`、`WEEK`、`QUARTER`、`HOUR`、`MINUTE`。<br/>- 文字列：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |
| [ 日付（部分） ](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。この関数の一部では、わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。<br/>サポートされる文字列部分は次のとおりです。`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |
| [ 日付（切り捨て） ](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。<br/>サポートされる文字列の精度は次のとおりです。`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |

{style="table-layout:auto"}

### 部分的なサポート

一部の SQL 機能は、BI 拡張機能で部分的にのみサポートされており、他のデータベースで見られるような結果を返しません。  この特定の機能は、様々な BI ツールで生成される SQL で使用されます。これらのツールでは、BI 拡張機能に完全一致はありません。 その結果、BI 拡張機能は、エラーをスローせずに BI ツールの最小使用量をカバーする限定的な実装に焦点を当てています。 詳しくは、次の表を参照してください。

| 関数 | 例 | 詳細 |
|---|---|---|
| MIN （）およびMAX（） | ``MIN(daterange)`` または<br/> ``MAX(daterange)`` | `timestamp`、`daterange` または `daterangeday` のような `daterangeX` の `MIN()` は 2 年前に戻ります。<br/><br/> `timestamp`、`daterange`、または `daterangeday` のような `daterangeX` のいずれかに `MAX()` すると、現在の日付/時刻が返されます。他のディメンション、指標、式の <br/><br/>`MIN()` または `MAX()` は 0 を返します。 |

{style="table-layout:auto"}
