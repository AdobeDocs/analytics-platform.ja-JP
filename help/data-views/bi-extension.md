---
title: Customer Journey Analytics BI 拡張機能
description: Power BI または Tableau Desktop を使用して、Customer Journey Analytics BI 拡張機能を使用してデータビューにアクセスする方法について説明します。
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '3247'
ht-degree: 90%

---

# Customer Journey Analytics BI 拡張機能

{{select-package}}

[!DNL Customer Journey Analytics BI extension] を使用すると、Customer Journey Analytics で定義した[データビュー](./data-views.md)への SQL アクセスが可能になります。データエンジニアやアナリストは、Power BI、Tableau Desktop またはその他のビジネスインテリジェンスツールやビジュアライゼーションツール（以降、BI ツールと呼びます）に精通している可能性があります。Customer Journey Analytics ユーザーが Analysis Workspace プロジェクトを作成する際に使用しているものと同じデータビューに基づいて、レポートおよびダッシュボードを作成できるようになりました。

Adobe Experience Platform [クエリサービス](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home)は、Experience Platform のデータレイクで使用可能なデータへの SQL インターフェイスです。[!DNL Customer Journey Analytics BI extension] を有効にすると、[!DNL Query Service] の機能が拡張され、Customer Journey Analytics データビューを [!DNL Query Service] セッションのテーブルまたはビューとして表示できるようになります。その結果、[!DNL Query Service] を PostgresSQL インターフェイスとして使用するビジネスインテリジェンスツールは、この拡張機能のメリットをシームレスに受けられます。

主なメリットは次のとおりです。

* BI ツール自体内で Customer Journey Analytics データビューの同等の表示域を再作成する必要はありません。<br/>再作成する必要がある項目を理解するためのデータビューの機能について詳しくは、[データビュー](data-views.md)を参照してください。
* BI ツールと Customer Journey Analytics 間のレポートと分析の一貫性が向上します。
* Customer Journey Analytics データを、BI ツールで既に使用可能な他のデータソースと組み合わせます。

## 前提条件

この機能を使用するには、有効期限のある資格情報または無期限の資格情報を使用して、BI ツールを [!DNL Customer Journey Analytics BI extension] に接続できます。[資格情報ガイド](https://experienceleague.adobe.com/ja/docs/experience-platform/query/ui/credentials)では、有効期限のある資格情報または無期限の資格情報の設定について詳しく説明します。
CJA 権限を設定するための追加手順を以下に示します
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### 資格情報の期限切れ

有効期限のある資格情報を使用するには、次の操作を実行します。

* Experience Platform と Customer Journey Analytics へのアクセス権を付与します。
* 製品管理者に Customer Journey Analytics へのアクセス権を付与して、接続とデータビューを表示、編集、更新または削除できるようにします。

または、次の操作を実行します。

* アクセスするデータビューへのアクセス権を付与します。
* Customer Journey Analytics BI 拡張機能へのアクセス権を付与します。

### 無期限の資格情報

無期限の資格情報を使用するには：

* 無期限の資格情報を Experience Platform に作成します。
* [有効期限のある資格情報](#Expiring-credentials)に記載されている手順に従って、無期限の資格情報へのアクセス権を付与します。

詳しくは、[カスタマージャーニーのアクセス制御](../technotes/access-control.md)を参照してください。特に、[製品管理者の追加の権限](../technotes/access-control.md#product-admin-additional-permissions)と [Adobe Admin Console の Customer Journey Analytics 権限](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console)を参照してください。


## 使用状況

[!DNL Customer Journey Analytics BI extension] 機能を使用するには、SQL を直接使用することも、特定の BI ツールで使用可能なドラッグ＆ドロップエクスペリエンスを使用することもできます。

### SQL

この機能は、クエリエディターまたは標準の PostgreSQL コマンドラインインターフェイス（CLI）クライアントを使用して SQL 文で直接使用できます。

+++ クエリ編集者

Adobe Experience Platform の場合：

1. 左側のパネルの&#x200B;**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

1. ![クエリを作成](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;クエリを作成&#x200B;**]** を選択します。

1. `cja` データベース **[!UICONTROL ドロップダウンメニューのデータベースのリストから、サンドボックスの]** データベースを選択します。 例：`prod:cja`。

1. クエリを実行するには、SQL 文を入力し、![再生](assets/Smock_Play_18_N.svg)ボタンを選択します（または `[SHIFT]` + `[ENTER]` キーを押します）。

+++


+++ PostgreSQL CLI

1. Adobe Experience Platform で PostgresQL 資格情報を検索してコピーします。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. `cja` データベース **[!UICONTROL ドロップダウンメニューのデータベースのリストから、サンドボックスの]** データベースを選択します。 例：`prod:cja`。

   1. コマンド文字列をコピーするには、「**[!UICONTROL ** PSQL コマンド&#x200B;**]**」セクションの![コピー](assets/Smock_Copy_18_N.svg)を使用します。

1. コマンドウィンドウまたはターミナルウィンドウを開きます。

1. ログインしてクエリの実行を開始するには、ターミナルにコマンド文字列をペーストします。

+++

詳しくは、[クエリエディター UI ガイド](https://experienceleague.adobe.com/ja/docs/experience-platform/query/ui/user-guide)を参照してください。


### BI ツール

現在、[!DNL Customer Journey Analytics BI extension] は、以下に示すツールでサポートおよびテストされています。PSQL インターフェイスを使用する他の BI ツールも同様に機能する可能性がありますが、まだ正式にはサポートされていません。

+++ Power BI

1. Adobe Experience Platform で PostgresSQL 資格情報の詳細を参照します。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. `cja` データベース **[!UICONTROL ドロップダウンメニューのデータベースのリストから、サンドボックスの]** データベースを選択します。 例：`prod:cja`。

   1. Power BI で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

1. Power BI の場合：

   1. メインウィンドウで、上部のツールバーから「**[!UICONTROL **&#x200B;データを取得&#x200B;**]**」を選択します。

   1. 左側のパネルで「**[!UICONTROL その他...]**」を選択します。

   1. **データを取得**&#x200B;画面で `PostgresSQL` を検索し、リストから 「**[!UICONTROL ** PostgreSQL データベース&#x200B;**]**」を選択します。

   1. **[!UICONTROL ** PostgreSQL データベース&#x200B;**]**&#x200B;ダイアログの場合：

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ホスト&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;サーバー&#x200B;**]**」テキストフィールドにペーストします。

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;データベース&#x200B;**]**」テキストフィールドにペーストします。

         `?FLATTEN` を&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターに追加すると、例えば、`prod:cja?FLATTEN` のように読み込まれます。詳しくは、[サードパーティの BI ツールで使用するネストされたデータ構造のフラット化](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data)を参照してください。

      1. **[!UICONTROL データ接続]**&#x200B;モードを求められたら、「**[!UICONTROL 直接クエリ]**」を選択します。

      1. **[!UICONTROL ユーザー名]**&#x200B;と&#x200B;**[!UICONTROL パスワード]**&#x200B;の入力を求められます。Experience Platform クエリ[!UICONTROL 資格情報]の同等のパラメーターを使用します。


   1. ログインに成功すると、Power BI の&#x200B;**[!UICONTROL **&#x200B;ナビゲーター&#x200B;**]**&#x200B;に Customer Journey Analytics データビューテーブルが表示されます。

   1. 使用するデータビューテーブルを選択し、「**[!UICONTROL **&#x200B;読み込み&#x200B;**]**」を選択します。

   選択した 1 つ以上のテーブルに関連付けられたすべてのディメンションと指標が右側のパネルに表示され、ビジュアライゼーションで使用できるようになります。

   詳しくは、[クエリサービスへの Power BI の接続](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/power-bi)を参照してください。例について詳しくは、[BI 拡張機能のユースケース](/help/use-cases/data-views/bi-extension-usecases.md)も参照してください。

+++

+++Tableau Desktop

1. Adobe Experience Platform で PostgresSQL 資格情報の詳細を参照します。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. `cja` データベース **[!UICONTROL ドロップダウンメニューのデータベースのリストから、サンドボックスの]** データベースを選択します。 例：`prod:cja`。

   1. Tableau Desktop で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

1. Tableau Desktop の場合：

   1. 左側のパネルの&#x200B;**[!UICONTROL **&#x200B;サーバーへ&#x200B;**]**&#x200B;から「**[!UICONTROL **&#x200B;その他&#x200B;**]**」を選択します。

   1. リストから「**[!UICONTROL ** PostgreSQL **]**」を選択します。

   1. [!UICONTROL PostgreSQL] ダイアログの場合：

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ホスト&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;サーバー&#x200B;**]**」テキストフィールドにペーストします。

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ポート&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;ポート&#x200B;**]**」テキストフィールドにペーストします。

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;データベース&#x200B;**]**」テキストフィールドにペーストします。

         `%3FFLATTEN` を&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターに追加すると、例えば、`prod:cja%3FFLATTEN` のように読み込まれます。詳しくは、[サードパーティの BI ツールで使用するネストされたデータ構造のフラット化](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data)を参照してください。

      1. **[!UICONTROL **&#x200B;認証&#x200B;**]**&#x200B;リストから&#x200B;**[!UICONTROL **&#x200B;ユーザー名とパスワード&#x200B;**]**&#x200B;を選択します。

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ユーザー名&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;ユーザー名&#x200B;**]**」テキストフィールドにペーストします。

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;パスワード&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;パスワード&#x200B;**]**」テキストフィールドにペーストします。

      1. 「**[!UICONTROL **&#x200B;ログイン&#x200B;**]**」を選択します。

   1. Customer Journey Analytics データビューは、**[!UICONTROL **&#x200B;テーブル&#x200B;**]**&#x200B;リストにテーブルとして表示されます。

   1. 使用するテーブルをキャンバス上でドラッグします。

   これで、データビューテーブルのデータを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[クエリサービスへの Tableau の接続](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/tableau)を参照してください。例について詳しくは、[BI 拡張機能のユースケース](/help/use-cases/data-views/bi-extension-usecases.md)も参照してください。

+++

+++ Looker

1. Adobe Experience Platform で PostgresSQL 資格情報の詳細を参照します。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. `cja` データベース **[!UICONTROL ドロップダウンメニューのデータベースのリストから、サンドボックスの]** データベースを選択します。 例：`prod:cja`。

   1. Looker で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

1. Looker の場合：

   1. 左側のパネルから「**[!UICONTROL 管理]**」を選択します。
   1. 「**[!UICONTROL 接続]**」を選択します。
   1. 「**[!UICONTROL 接続を追加]**」を選択します。
   1. **[!UICONTROL データベースを Looker に接続]**&#x200B;画面で、新しい接続を設定する際に適切な値をペーストします。ダイアレクトとして **[!UICONTROL PostgreSQL 9.5 以降]**&#x200B;を選択します。
   1. 「**[!UICONTROL テスト]**」を選択して、接続をテストします。
   1. 成功したら、「**[!UICONTROL 更新]**」を選択して、接続を保存します。

   これで、データビューテーブルのデータを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[クエリサービスへの Looker の接続](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/looker)を参照してください。例について詳しくは、[BI 拡張機能のユースケース](/help/use-cases/data-views/bi-extension-usecases.md)も参照してください。

+++

+++ Jupyter Notebook

1. Adobe Experience Platform で PostgresSQL 資格情報の詳細を参照します。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. `cja` データベース **[!UICONTROL ドロップダウンメニューのデータベースのリストから、サンドボックスの]** データベースを選択します。 例：`prod:cja`。

   1. Jupyter Notebook で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

1. Jupyter Notebook の場合：

   1. 必要なライブラリを使用していることを確認します。
   1. 接続を設定して実行する際は、適切な値を使用します。
   1. 関連するクエリを実行して、接続をテストします。

   成功したら、データを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[クエリサービスへの Jupyter Notebook の接続](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/jupyter-notebook)を参照してください。例について詳しくは、[BI 拡張機能のユースケース](/help/use-cases/data-views/bi-extension-usecases.md)も参照してください。

+++

+++ RStudio

1. Adobe Experience Platform で PostgresSQL 資格情報の詳細を参照します。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   1. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   1. `cja` データベース **[!UICONTROL ドロップダウンメニューのデータベースのリストから、サンドボックスの]** データベースを選択します。 例：`prod:cja`。

   1. Jupyter Notebook で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

1. RStudio の場合：

   1. 必要なライブラリを使用していることを確認します。
   1. 接続を設定して実行する際は、適切な値を使用します。
   1. 関連するクエリを実行して、接続をテストします。

   成功したら、データを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[クエリサービスへの RStudio の接続](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/rstudio)を参照してください。例（代わりに RPostgres パッケージを使用）について詳しくは、[BI 拡張機能のユースケース](/help/use-cases/data-views/bi-extension-usecases.md)も参照してください。

+++

使用可能な様々なツールの概要と詳細情報については、[クエリサービスへのクライアントの接続](https://experienceleague.adobe.com/ja/docs/experience-platform/query/clients/overview)を参照してください。

Customer Journey Analytics BI 拡張機能を使用して様々なユースケースを達成する方法について詳しくは、[ユースケース](/help/use-cases/data-views/bi-extension-usecases.md)を参照してください。

## 機能

デフォルトでは、データビューには、わかりやすい名前から生成されたテーブルセーフ名が付けられます。例えば、[!UICONTROL マイ web データビュー]という名前のデータビューのビュー名は `my_web_data_view` です。データビューの BI ツールで使用する優先名を定義できます。詳しくは、[データビュー設定](create-dataview.md#settings)を参照してください。

データビュー ID をテーブル名として使用する場合は、接続時にデータベース名にオプションの `CJA_USE_IDS` 設定を追加できます。例えば、`prod:cja?CJA_USE_IDS` は、`dv_ABC123` のような名前でデータビューを表示します。

### データガバナンス

Customer Journey Analytics のデータガバナンス関連の設定は、Adobe Experience Platform から継承されます。Customer Journey Analytics と Adobe Experience Platform のデータガバナンスの統合により、機密性の高い Customer Journey Analytics データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platform で使用されるデータセットに関して作成されたプライバシーラベルおよびポリシーは、Adobe Customer Journey Analytics データビューワークフローで表示できます。したがって、[!DNL Customer Journey Analytics BI extension] を使用してクエリされたデータは、定義されたプライバシーラベルとポリシーに準拠していない場合、適切な警告またはエラーを表示します。

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

デフォルトでは、データビューのスキーマは、元の XDM スキーマと同様に、ネストされた構造を使用します。また、この統合では、`FLATTEN` オプションもサポートされています。このオプションを使用すると、データビュー（およびセッション内の他のテーブル）のスキーマを強制的にフラット化できます。フラット化により、構造化スキーマをサポートしていない BI ツールでも簡単に使用できるようになります。詳しくは、[クエリサービスでのネストされたデータ構造の操作](https://experienceleague.adobe.com/ja/docs/experience-platform/query/key-concepts/flatten-nested-data)を参照してください。


### デフォルトと制限

BI 拡張機能を使用する場合、次の追加のデフォルトと制限が適用されます。

* BI 拡張機能には、クエリ結果の行制限が必要です。デフォルトは 50 ですが、SQL で `LIMIT n` を使用して上書きできます。`n` は 1～50000 です。
* BI 拡張機能には、計算に使用する行を制限するために日付範囲が必要です。デフォルトは過去 30 日間ですが、特別な [`timestamp`](#timestamp) 列または [`daterange`](#date-range) 列を使用して、SQL `WHERE` 句で上書きできます。
* BI 拡張機能には、集約クエリが必要です。 `SELECT * FROM ...` のような SQL を使用して、生の基になる行を取得できません。大まかに言うと、集計クエリでは以下を使用する必要があります。
   * `SUM` や `COUNT` を使用して合計を選択します。<br/>例：`SELECT SUM(metric1), COUNT(*) FROM ...`
   * ディメンション別に分類された指標を選択します。<br/>例：`SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * 個別の指標値を選択します。<br/>例：`SELECT DISTINCT dimension1 FROM ...`

     詳しくは、[サポートされる SQL](#supported-sql) を参照してください。


### サポートされる SQL

サポートされている SQL のタイプの完全なリファレンスについては、[クエリサービス SQL リファレンス](https://experienceleague.adobe.com/ja/docs/experience-platform/query/sql/overview)を参照してください。

使用可能な SQL の例については、次の表を参照してください。

+++ 例

<table style="table-layout:auto">
    <thead>
        <tr>
            <th>パターン</th>
            <th>例</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>スキーマの検出 </td>
            <td>
                <pre><code>SELECT * FROM dv1 WHERE 1=0</code></pre>
            </td>
        </tr>
        <tr>
            <td>ランク付けまたは分類 </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  filterId = '12345'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))
GROUP BY dim1</code></pre>
            </td>
        </tr>
        <tr>
            <td><code>HAVING</code> 句 </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1
HAVING m1 > 100</code></pre>
            </td>
        </tr>
        <tr>
            <td>個別、上位の
ディメンション値 </td>
            <td>
                <pre><code>SELECT DISTINCT dim1 FROM dv1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` >= '2022-01-01' AND `timestamp` < '2022-01-02'
GROUP BY dim1
ORDER BY SUM(metric1)
LIMIT 15</code></pre>
            </td>
        </tr>
        <tr>
            <td>指標の合計値 </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</code></pre>
            </td>
        </tr>
        <tr>
            <td>マルチディメンションの
分類
と上位の個別 </td>
            <td>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1, dim2</code></pre>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 1, 2
ORDER BY 1, 2</code></pre>
                <pre><code>SELECT DISTINCT dim1, dim2
FROM dv1</code></pre>
            </td>
        </tr>
        <tr>
            <td>サブ選択：
追加の結果
フィルタリング </td>
            <td>
                <pre><code>SELECT dim1, m1
FROM (
  SELECT dim1, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</br>  GROUP BY dim1
)
WHERE dim1 in ('A', 'B')</code></pre>
            </td>
        </tr>
        <tr>
            <td>サブ選択：
データビュー
全体のクエリ </td>
            <td>
                <pre><code>SELECT key, SUM(m1) AS total
FROM (
  SELECT dim1 AS key, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim1
<br>
  UNION
<br>
  SELECT dim2 AS key, SUM(m1) AS m1
  FROM dv2
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim2
)
GROUP BY key
ORDER BY total</code></pre>
            </td>
        </tr>
        <tr>
            <td>サブ選択：
レイヤー化されたソース、
フィルタリング、
集計 </td>
            <td>サブ選択を使用したレイヤー化：
<pre><code>SELECT rows.dim1, SUM(rows.m1) AS total
FROM (
  SELECT _.dim1,_.m1
  FROM (
    SELECT * FROM dv1
    WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  ) _
  WHERE _.dim1 in ('A', 'B', 'C')
) rows
GROUP BY 1
ORDER BY total</code></pre>
CTE WITH を使用するレイヤー：
<pre><code>WITH rows AS (
  WITH _ AS (
    SELECT * FROM data_ares
    WHERE `timestamp` BETWEEN '2021-01-01' AND '2021-02-01'
  )
  SELECT _.item, _.units FROM _
  WHERE _.item IS NOT NULL
)
SELECT rows.item, SUM(rows.units) AS units
FROM rows WHERE rows.item in ('A', 'B', 'C')
GROUP BY rows.item</code></pre>
        </td>
        </tr>
        <tr>
            <td>指標をディメンション
の前に配置するか、
ディメンションと混合する
場所を選択します </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1, dim1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 2</code></pre>
            </td>
        </tr>
    </tbody>
</table>

+++

### ディメンション

デフォルトで使用可能なディメンションや、データビューで定義されたディメンションを選択できます。ID でディメンションを選択します。

### 指標

選択できる指標は次のとおりです。

* デフォルトで使用可能な指標。
* データビューで定義する指標。
* ユーザーにアクセス権があるデータビューと互換性のある計算指標。

他の SQL ソースの場合と同様に、`SUM(metric)` 式に含まれる ID で指標を選択します。

以下が可能です：

* `SELECT COUNT(*)` または `COUNT(1)` を使用して、発生件数指標を取得する。
* `SELECT COUNT(DISTINCT dimension)` または `SELECT APPROX_COUNT_DISTINCT(dimension)` を使用して、ディメンションの個別概算値をカウントする。詳しくは、[個別値のカウント](#counting-distinct-values)を参照してください。
* [インライン計算](#inline-calculations)を使用して、即座に指標を組み合わせたり、計算を行ったりする。

#### 個別値のカウント

Customer Journey Analytics の仕組みの基本的な性質により、正確な個別のカウントを取得できる唯一のディメンションは、`adobe_personid` ディメンションです。次の SQL 文である `SELECT COUNT(DISTINCT adobe_personid)` または `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` は、個別の人物の数であるデフォルトのユーザー指標の値を返します。その他のディメンションの場合は、おおよその個別のカウントが返されます。

#### 条件付き指標

`IF` 関数または `CASE` 関数に `SUM` 句または `COUNT` 句を埋め込むと、選択した指標に固有のセグメント化を追加できます。 これらの句を追加する方法は、Workspaceのレポートテーブルで指標列にセグメントを適用する場合と似ています。

例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### インライン計算

`SELECT` で指標式に追加の計算を適用できます。この計算は、計算指標で計算を定義する代わりに使用できます。次の表に、サポートされる式のタイプを示します。

| 演算子または関数 | 詳細 |
|---|---|
| `+`、`-`、`*`、`/` および `%` | 加算、減算、乗算、除算、剰余演算 |
| `-X` または`+X` | 符号または指標の変更（X は指標式） |
| `PI()` | π 定数 |
| `POSITIVE`、`NEGATIVE`、`ABS`、`FLOOR`、`CEIL`、`CEILING`、`EXP`、`LN`、`LOG10`、`LOG1P`、`SQRT`、`CBRT`、`DEGREES`、`RADIANS`、`SIN`、`COS`、`TAN`、`ACOS`、`ASIN`、`ATAN`、 `COSH`、`SINH` および `TANH` | 単項数学関数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二項数学関数 |

{style="table-layout:auto"}

### 特殊列

#### タイムスタンプ

`timestamp` 特殊列は、クエリの日付範囲を指定するために使用されます。日付範囲は、`BETWEEN` 式または `timestamp` `>`、`>=`、`<`、`<=` チェックの `AND` を組み合わせて定義できます。
`timestamp` はオプションで、全範囲を指定しない場合は、デフォルトが使用されます。

* 最小値のみを指定している場合（`timestamp > X` または ` timestamp >= X`）、範囲は X から現在までです。
* 最大値のみを指定している場合（`timestamp < X` または `timestamp <= X`）、範囲は X-30 日から X です。
* 何も指定しない場合、範囲は現在-30 日から現在までです。

タイムスタンプ範囲は、RankRequest の日付範囲グローバルセグメントに変換されます。
また、タイムスタンプフィールドを日時関数で使用して、イベントのタイムスタンプを解析したり切り捨てたりすることもできます。

#### 日付範囲

`daterange` の特別な列は `timestamp` と同様に機能しますが、セグメント化は 1 日に制限されます。 `daterange` もオプションで、`timestamp` と同じ範囲のデフォルトが設定されます。
また、`daterange` フィールドを日時関数で使用して、イベントの日付を解析したり切り捨てたりすることもできます。

`daterangeName` 特別列は、`Last Quarter` のような名前付き日付範囲を使用してクエリをセグメント化するために使用できます。

>[!NOTE]
>
>Power BI は、1 日未満の `daterange` 指標（時間、30 分、5 分など）をサポートしていません。
>

#### Segment ID

`filterId` の特別な列はオプションで、外部で定義されたセグメントをクエリに適用するために使用されます。 外部で定義されたセグメントをクエリに適用することは、Workspaceのパネル上でセグメントをドラッグすることに似ています。 複数のセグメント ID を使用する場合は、`AND` を付けます。

`filterId` と共に `filterName` を使用して、ID の代わりにセグメントの名前を使用できます。

### Where 句

`WHERE` 句は、次の 3 つの手順で処理されます。

1. `timestamp`、`daterange` または `daterangeName` の特殊フィールドから日付範囲を見つけます。

1. セグメントに含める、外部で定義された `filterId` または `filterName` を見つけます。

1. 残りの式をアドホックセグメントに変換します。

この処理は、`WHERE` 句の最初のレベルの `AND` を解析することによって行われます。最上位の各 `AND` 式は、上記のいずれかと一致する必要があります。`AND` の最初のレベルより深いもの、または `WHERE` 句で `OR` を最上位レベルで使用する場合は、アドホックセグメントとして処理されます。

### 並べ替え順序

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
| [キャスト](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` または <br/> `` `timestamp`::string `` | 型キャストは現在サポートされていませんが、エラーはスローされません。`CAST` 関数は無視されます。 |
| [タイムスタンプ](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | `WHERE` 句内で使用するタイムスタンプとして時刻文字列を解析します。 |
| [終了タイムスタンプ](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 時刻文字列を `WHERE` 句内で使用するタイムスタンプとして解析し、オプションでその時刻文字列の形式を指定します。 |
| [日付](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | `WHERE` 句内で使用するために、日付文字列をタイムスタンプとして解析します。 |
| [終了日](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 日付文字列を `WHERE` 句内で使用するタイムスタンプとして解析し、オプションでその日付文字列の形式を指定します。 |

{style="table-layout:auto"}

### ディメンション関数のサポート

以下の関数は、`SELECT`、`WHERE` 句または条件付き指標のディメンションで使用できます。

**文字列関数**

| 関数 | 例 | 詳細 |
|---|---|---|
| [下位](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 渡されたフィールドで動的ディメンション ID を生成します。 |

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
| [エクストラクト](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。この関数の一部では、わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。<br/>サポートされる一部は次のとおりです。<br>- キーワード：`YEAR`、`MONTH`、`DAYOFMONTH`、`DAYOFWEEK`、`DAYOFYEAR`、`WEEK`、`QUARTER`、`HOUR`、`MINUTE`。<br/>- 文字列：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |
| [日付（一部）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。この関数の一部では、わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。<br/>サポートされる文字列部分は次のとおりです。`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |
| [日付（切り捨て）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。<br/>サポートされる文字列の精度は次のとおりです。`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |

{style="table-layout:auto"}

### 部分的なサポート

一部の SQL 機能は、BI 拡張機能では部分的にのみサポートされており、他のデータベースで表示されるのと同じ結果を返しません。この特定の機能は、BI 拡張機能に完全に一致するものがない様々な BI ツールで生成した SQL で使用されます。その結果、BI 拡張機能は、エラーをスローすることなく最小限の BI ツールの使用を対象とする限定的な実装に焦点を当てています。詳しくは、以下の表を参照してください。

| 関数 | 例 | 詳細 |
|---|---|---|
| 最小値() と最大値() | ``MIN(daterange)`` または<br/> ``MAX(daterange)`` | `timestamp`、`daterange`、`daterangeday` などの `daterangeX` のいずれかに `MIN()` を実行すると、2 年前が返されます。<br/><br/> `timestamp`、`daterange`、`daterangeday` などの `daterangeX` のいずれかに `MAX()` を実行すると、現在の日付／時刻が返されます。他のディメンション、指標、式に対する <br/><br/>`MIN()` または `MAX()` は 0 を返します。 |

{style="table-layout:auto"}
