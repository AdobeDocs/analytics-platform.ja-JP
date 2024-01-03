---
title: SQL コネクター
description: クエリサービス、Power BI、Tableau を使用して、SQL コネクタを介してデータビューにアクセスする方法について説明します。
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 1827a637-6c0f-43f2-862a-928089340d30
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '2789'
ht-degree: 100%

---

# SQL コネクター

{{release-limited-testing}}

{{select-package}}

[!DNL Customer Journey Analytics SQL Connector] を使用すると、Customer Journey Analytics で定義した[データビュー](./data-views.md)への SQL アクセスが可能になります。データエンジニアやアナリストは、Power BI、Tableau またはその他のビジネスインテリジェンスツールやビジュアライゼーションツール（以降、BI ツールと呼びます）に精通している可能性があります。Customer Journey Analytics ユーザーが Analysis Workspace プロジェクトを作成する際に使用しているものと同じデータビューに基づいて、レポートおよびダッシュボードを作成できるようになりました。

Adobe Experience Platform [クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)は、Experience Platform のデータレイクで使用可能なデータへの SQL インターフェイスです。[!DNL Customer Journey Analytics SQL Connector] を有効にすると、[!DNL Query Service] の機能が拡張され、Customer Journey Analytics データビューを [!DNL Query Service] セッションのテーブルまたはビューとして表示できるようになります。その結果、[!DNL Query Service] を PostgresSQL インターフェイスとして使用するビジネスインテリジェンスツールは、この拡張機能のメリットをシームレスに受けられます。

主なメリットは次のとおりです。

- BI ツール自体内で Customer Journey Analytics データビューの同等の表示域を再作成する必要はありません。<br/>再作成する必要がある項目を理解するためのデータビューの機能について詳しくは、[データビュー](data-views.md)を参照してください。<br/>

- BI ツールと Customer Journey Analytics 間のレポートと分析の一貫性が向上します。

- Customer Journey Analytics データを、BI ツールで既に使用可能な他のデータソースと組み合わせます。

## 前提条件

この機能を使用するには、次の操作を行う必要があります。

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- 関連する製品プロファイル、ユーザーグループ、個々のユーザーの機能を設定します。<br/>
ユーザーには、以下へのアクセス権がある必要があります。
   - Experience Platform クエリサービス。
   - Customer Journey Analytics Workspace プロジェクト。
   - Customer Journey Analytics データビュー。

- 有効期限のない資格情報での期限切れを使用して、BI ツールを Customer Journey Analytics SQL コネクタに接続します。[資格情報ガイド](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=ja)では、有効期限のある資格情報または無期限の資格情報の設定について詳しく説明します。

詳しくは、Customer Journey Analytics 管理の節にある[アクセス制御](../admin/cja-access-control.md)を参照してください。


## 用途

[!DNL Customer Journey Analytics SQL Connector] 機能を使用するには、SQL を直接使用することも、特定の BI ツールで使用可能なドラッグ＆ドロップエクスペリエンスを使用することもできます。

### SQL

この機能は、クエリエディターまたは標準の PostgreSQL コマンドラインインターフェイス（CLI）クライアントを使用して SQL 文で直接使用できます。

+++ クエリエディター

Experience Platform UI の場合：

1. 左側のパネルの&#x200B;**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

2. ![クエリを作成](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;クエリを作成&#x200B;**]** を選択します。

3. クエリを実行するには、SQL 文を入力し、![再生](assets/Smock_Play_18_N.svg)ボタンを選択します（または Shift+Enter キーを押します）。

+++


+++ PostgreSQL CLI

1. Experience Platform UI で、PostgreSQL 資格情報を検索してコピーします。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   2. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   3. 接続文字列をコピーするには、「**[!UICONTROL ** PSQL コマンド&#x200B;**]**」セクションの![コピー](assets/Smock_Copy_18_N.svg)を使用します。

2. PostgreSQL CLI を開きます。

3. ログインしてクエリの実行を開始するには、PostgreSQL CLI に接続文字列をペーストします。

+++

詳しくは、[クエリエディター UI ガイド](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=ja)を参照してください。


### BI ツール

現在、Customer Journey Analytics SQL コネクターは、Power BI と Tableau に対してのみサポートおよびテストされています。PSQL インターフェイスを使用する他の BI ツールも同様に機能する可能性がありますが、まだ正式にはサポートされていません。

+++ Power BI

1. Adobe Experience Platform UI で、PostgreSQL 資格情報の詳細を検索します。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   2. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   3. Power BI で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

2. Power BI の場合：

   1. メインウィンドウで、上部のツールバーから「**[!UICONTROL **&#x200B;データを取得&#x200B;**]**」を選択します。

   2. 左側のパネルで「**[!UICONTROL **&#x200B;その他...**]**」を選択します。

   3. **データを取得**&#x200B;画面で `PostgresSQL` を検索し、リストから 「**[!UICONTROL ** PostgreSQL データベース&#x200B;**]**」を選択します。

   4. **[!UICONTROL ** PostgreSQL データベース&#x200B;**]**&#x200B;ダイアログの場合：

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ホスト&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;サーバー&#x200B;**]**」テキストフィールドにペーストします。

      2. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;データベース&#x200B;**]**」テキストフィールドにペーストします。

         `?FLATTEN` を&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターに追加すると、例えば、`prod:cja?FLATTEN` のように読み込まれます。詳しくは、[サードパーティの BI ツールで使用するネストされたデータ構造のフラット化](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=ja)を参照してください。

      3. **[!UICONTROL **&#x200B;データ接続&#x200B;**]**&#x200B;モードを求められたら、「**[!UICONTROL **&#x200B;直接クエリ&#x200B;**]**」を選択して、データ構造が適切にフラット化されていることを確認します。

      4. **[!UICONTROL **&#x200B;ユーザー名&#x200B;**]**&#x200B;と&#x200B;**[!UICONTROL **&#x200B;パスワード&#x200B;**]**&#x200B;の入力を求められます。Experience Platform クエリ[!UICONTROL 資格情報]の同等のパラメーターを使用します。


   5. ログインに成功すると、Power BI の&#x200B;**[!UICONTROL **&#x200B;ナビゲーター&#x200B;**]**&#x200B;に Customer Journey Analytics データビューテーブルが表示されます。データビューテーブルは、名前に `dv_` を使用することで特定されます。


   6. 使用するデータビューテーブルを選択し、「**[!UICONTROL **&#x200B;読み込み&#x200B;**]**」を選択します。

   選択した 1 つ以上のテーブルに関連付けられたすべてのディメンションと指標が右側のパネルに表示され、ビジュアライゼーションで使用できるようになります。

   詳しくは、[クエリサービスへの Power BI の接続](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=ja)を参照してください。

+++

+++Tableau

1. Experience Platform UI で、PostgreSQL 資格情報の詳細を検索します。

   1. 左側のパネル（**[!UICONTROL **&#x200B;データ管理&#x200B;**]**&#x200B;の下）から「**[!UICONTROL **&#x200B;クエリ&#x200B;**]**」を選択します。

   2. 上部のバーから「**[!UICONTROL **&#x200B;資格情報&#x200B;**]**」を選択します。

   3. Tableau で必要に応じて![コピー](assets/Smock_Copy_18_N.svg)を使用して、PostgreSQL 資格情報の各パラメーター（[!UICONTROL ホスト]、[!UICONTROL ポート]、[!UICONTROL データベース]、[!UICONTROL ユーザー名]など）をコピーします。

2. Tableau の場合：

   1. 左側のパネルの&#x200B;**[!UICONTROL **&#x200B;サーバーへ&#x200B;**]**&#x200B;から「**[!UICONTROL **&#x200B;その他&#x200B;**]**」を選択します。

   2. リストから「**[!UICONTROL ** PostgreSQL **]**」を選択します。

   3. [!UICONTROL PostgreSQL] ダイアログの場合：

      1. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ホスト&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;サーバー&#x200B;**]**」テキストフィールドにペーストします。

      2. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ポート&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;ポート&#x200B;**]**」テキストフィールドにペーストします。

      3. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;データベース&#x200B;**]**」テキストフィールドにペーストします。

         `%3FFLATTEN` を&#x200B;**[!UICONTROL **&#x200B;データベース&#x200B;**]**&#x200B;パラメーターに追加すると、例えば、`prod:cja%3FFLATTEN` のように読み込まれます。詳しくは、[サードパーティの BI ツールで使用するネストされたデータ構造のフラット化](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=ja)を参照してください。

      4. **[!UICONTROL **&#x200B;認証&#x200B;**]**&#x200B;リストから&#x200B;**[!UICONTROL **&#x200B;ユーザー名とパスワード&#x200B;**]**&#x200B;を選択します。

      5. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;ユーザー名&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;ユーザー名&#x200B;**]**」テキストフィールドにペーストします。

      6. Experience Platform クエリ[!UICONTROL 資格情報]の&#x200B;**[!UICONTROL **&#x200B;パスワード&#x200B;**]**&#x200B;パラメーターを「**[!UICONTROL **&#x200B;パスワード&#x200B;**]**」テキストフィールドにペーストします。

      7. 「**[!UICONTROL **&#x200B;ログイン&#x200B;**]**」を選択します。

   4. Customer Journey Analytics データビューは、**[!UICONTROL **&#x200B;テーブル&#x200B;**]**&#x200B;リストにテーブルとして表示されます。データビューテーブルには、`dv_` が接頭辞として付きます。

   5. 使用するテーブルをキャンバス上でドラッグします。

   これで、データビューテーブルのデータを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、[クエリサービスへの Tableau の接続](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=ja)を参照してください。

+++

使用可能な様々なツールの概要と詳細情報については、[クエリサービスへのクライアントの接続](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=ja)を参照してください。

## 機能

デフォルトでは、データビューには、わかりやすい名前から生成されたテーブルセーフ名が付けられます。例えば、[!UICONTROL マイ web データ]という名前のデータビューのビュー名は `dv_my_web_data` です。

データビュー ID をテーブル名として使用する場合は、接続時にデータベース名にオプションの `CJA_USE_IDS` 設定を追加できます。例えば、`prod:all?CJA_USE_IDS` は、`dv_ABC123` のような名前でデータビューを表示します。

### データガバナンス

Customer Journey Analytics のデータガバナンス関連の設定は、Adobe Experience Platform から継承されます。Customer Journey Analytics と Adobe Experience Platform のデータガバナンスの統合により、機密性の高い Customer Journey Analytics データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platform で使用されるデータセットに関して作成されたプライバシーラベルとポリシーは、 Customer Journey Analytics データビューワークフローで表示できます。したがって、Customer Journey Analytics SQL コネクタを使用してクエリされたデータは、定義されたプライバシーラベルとポリシーに準拠していない場合、適切な警告またはエラーを表示します。

### データビューのリスト

標準の PostgreSQL CLI では、`\dv` を使用してビューをリストできます

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### ネスト化とフラット化

デフォルトでは、データビューのスキーマは、元の XDM スキーマと同様に、ネストされた構造を使用します。また、この統合では、`FLATTEN` オプションもサポートされています。このオプションを使用すると、データビュー（およびセッション内の他のテーブル）のスキーマを強制的にフラット化できます。フラット化により、構造化スキーマをサポートしていない BI ツールでも簡単に使用できるようになります。詳しくは、[クエリサービスでのネストされたデータ構造の操作](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=ja)を参照してください。

### サポートされる SQL

サポートされている SQL のタイプの完全なリファレンスについては、[クエリサービス SQL リファレンス](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=ja)を参照してください。

使用可能な SQL の例については、次の表を参照してください。

+++ 例

| パターン | 例 |
|---|---|
| スキーマの検出 | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| ランク付け／分類 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| HAVING 句 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| 個別、上位の<br/>ディメンション値 | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| 指標の合計値 | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| マルチディメンションの<br/>分類<br/>と上位の個別 | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| サブ選択：<br/>追加の結果<br/>フィルタリング | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| サブ選択：<br/>Customer Journey Analytics にないデータセット<br/>との結合<br/> | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| サブ選択：データビュー<br/>全体のクエリ<br/> | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| サブ選択：<br/>レイヤー化されたソース、<br/>フィルタリング、<br/>集計 | サブ選択を使用したレイヤー化：<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>CTE WITH を使用するレイヤー：<br/><pre>WITH rows AS (<br/>  WITH \_ AS (<br/>    SELECT * FROM data_ares<br/>    WHERE \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| <br/>指標をディメンションの前<br/>に配置するか、ディメンションと<br/>混合する場所を選択します | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### ディメンション

デフォルトで使用可能なディメンションや、データビューで定義されたディメンションを選択できます。ID でディメンションを選択します。

### 指標

選択できる指標は次のとおりです。

- デフォルトで使用可能な指標。

- データビューで定義する指標。

- ユーザーにアクセス権があるデータビューと互換性のある計算指標。

他の SQL ソースの場合と同様に、`SUM(metric)` 式に含まれる ID で指標を選択します。

以下が可能です：

- `SELECT COUNT(*)` または `COUNT(1)` を使用して、発生件数指標を取得する。

- `SELECT COUNT(DISTINCT dimension)` または `SELECT APPROX_COUNT_DISTINCT(dimension)` を使用して、ディメンションの個別概算値をカウントする。詳しくは、[個別のカウント](#counting-distincts)を参照してください。

- [インライン計算](#inline-calculations)を使用して、即座に指標を組み合わせたり、計算を行ったりする。

#### 個別のカウント

Customer Journey Analytics の仕組みの基本的な性質により、正確な個別のカウントを取得できる唯一のディメンションは、`adobe_personid` ディメンションです。次の SQL 文である `SELECT COUNT(DISTINCT adobe_personid)` または `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` は、個別の人物の数であるデフォルトのユーザー指標の値を返します。その他のディメンションの場合は、おおよその個別のカウントが返されます。

#### 条件付き指標

`IF` 句または `CASE` 句を `SUM` 関数または `COUNT` 関数に埋め込んで、選択した指標に固有のフィルタリングを追加できます。これらの句を追加することは、Workspace レポートテーブルの指標列にフィルターを適用することと似ています。

例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### インライン計算

計算指標で数値を定義する代わりに、`SELECT` で指標式に追加を適用できます。次の表に、サポートされる式のタイプを示します。

| 演算子または関数 | 詳細 |
|---|---|
| `+`、`-`、`*`、`/` および `%` | 加算、減算、乗算、除算、剰余演算 |
| `-X` または`+X` | 符号または指標の変更（X は指標式） |
| `PI()` | π 定数 |
| `POSITIVE`、`NEGATIVE`、`ABS`、`FLOOR`、`CEIL`、`CEILING`、`EXP`、`LN`、`LOG10`、`LOG1P`、`SQRT`、`CBRT`、`DEGREES`、`RADIANS`、`SIN`、`COS`、`TAN`、`ACOS`、`ASIN`、`ATAN`、 `COSH`、`SINH` および `TANH` | 単項数学関数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二項数学関数 |

{style="table-layout:auto"}

### 特殊列

**タイムスタンプ**

`timestamp` 特殊列は、クエリの日付範囲を指定するために使用されます。日付範囲は、`BETWEEN` 式または `timestamp` `>`、`>=`、`<`、`<=` チェックの `AND` を組み合わせて定義できます。
`timestamp` はオプションで、全範囲を指定しない場合は、デフォルトが使用されます。

- 最小値のみを指定している場合（`timestamp > X` または ` timestamp >= X`）、範囲は X から現在までです。

- 最大値のみを指定している場合（`timestamp < X` または `timestamp <= X`）、範囲は X-30 日から X です。

- 何も指定しない場合、範囲は現在-30 日から現在までです。

タイムスタンプの範囲は、RankedRequest の日付範囲グローバルフィルターに変換されます。
また、タイムスタンプフィールドを日時関数で使用して、イベントのタイムスタンプを解析したり切り捨てたりすることもできます。

**日付範囲**

`daterange` 特殊列は `timestamp` と同様に機能しますが、フィルタリングは全日に制限されます。`daterange` もオプションで、`timestamp` と同じ範囲のデフォルトが設定されます。
また、`daterange` フィールドを日時関数で使用して、イベントの日付を解析したり切り捨てたりすることもできます。

**filterId**

`filterId` 特殊列はオプションで、外部で定義されたフィルターをクエリに適用するために使用されます。外部で定義されたフィルターをクエリに適用することは、Workspace のパネルにフィルターをドラッグすることと似ています。複数のフィルター ID は、`AND` 演算することで指定できます。

### WHERE 句

WHERE 句は、次の 3 つの手順で処理されます。

1. `timestamp` の特殊フィールドから日付範囲を見つけます。

2. フィルタリングに含める外部で定義された `filterId` を見つけます。

3. 残りの式をアドホックフィルターに変換します。

この処理は、`WHERE` 句の最初のレベルの `AND` を解析することによって行われます。最上位の各 `AND` 式は、上記のいずれかと一致する必要があります。最初のレベルの `AND` より深い部分や、`WHERE` 句が最上位レベルで `OR` を使用している場合は、アドホックフィルターとして処理されます。

### ORDER BY

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
| [CAST(列 AS 型)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` または <br/> `` `timestamp`::string `` | 型キャストは現在サポートされていませんが、エラーはスローされません。`CAST` 関数は無視されます。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | `WHERE` 句内で使用するタイムスタンプとして時刻文字列を解析します。 |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 時刻文字列を `WHERE` 句内で使用するタイムスタンプとして解析し、オプションでその時刻文字列の形式を指定します。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | `WHERE` 句内で使用するために、日付文字列をタイムスタンプとして解析します。 |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 日付文字列を `WHERE` 句内で使用するタイムスタンプとして解析し、オプションでその日付文字列の形式を指定します。 |

{style="table-layout:auto"}

### ディメンション機能のサポート

以下の関数は、`SELECT`、`WHERE` 句または条件付き指標のディメンションで使用できます。

**文字列関数**

| 関数 | 例 | 詳細 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 渡されたフィールドで動的ディメンション ID を生成します。 |

{style="table-layout:auto"}

**日時関数**

| 関数 | 例 | 詳細 |
|---|---|---|
| [YEAR(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [MONTH(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [DAY(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [DAYOFWEEK(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。 |
| [DAYOFYEAR(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [WEEK(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [QUARTER(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [HOUR(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。 |
| [MINUTE(date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [EXTRACT(part FROM date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。この関数の一部では、わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。<br/>サポートされる一部は次のとおりです。<br>- キーワード：`YEAR`、`MONTH`、`DAYOFMONTH`、`DAYOFWEEK`、`DAYOFYEAR`、`WEEK`、`QUARTER`、`HOUR`、`MINUTE`。<br/>- 文字列：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |
| [DATE_PART(part, date, または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。この関数の一部では、わかりやすい名前ではなく数値が必要なので、値の代わりに項目 ID を使用します。<br/>サポートされる文字列部分は次のとおりです。`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |
| [DATE_TRUNC(精度, date または date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。<br/>サポートされる文字列の精度は次のとおりです。`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` または `'MINUTE'`。 |

{style="table-layout:auto"}
