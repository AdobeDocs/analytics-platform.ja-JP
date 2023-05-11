---
title: SQL コネクタ
description: クエリサービス、Power BI、Tableau を使用して、SQL コネクタを使用してデータビューにアクセスする方法を説明します。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
source-git-commit: 7d072538c42210f5de7c9c38df05423350e694b0
workflow-type: tm+mt
source-wordcount: '2879'
ht-degree: 6%

---

# SQL コネクタ

{{release-limited-testing}}

この [!DNL Customer Journey Analytics (CJA) SQL Connector] に対する SQL アクセスを有効にします。 [データビュー](./data-views.md) CJA で定義した。 Power BIエンジニアやアナリストは、データ、Tableau、またはその他のビジネスインテリジェンスやビジュアライゼーションツール（BI ツールとも呼ばれます）に詳しい場合があります。 CJA ユーザーがAnalysis Workspaceプロジェクトを作成する際に使用したのと同じデータビューに基づいて、レポートとダッシュボードを作成できるようになりました。

Adobe Experience Platform [クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja) は、Experience Platformのデータレイクで使用できるデータへの SQL インターフェイスです。 を使用 [!DNL CJA SQL Connector] 有効、 [!DNL Query Service] が拡張され、CJA データビューをテーブルまたはビューとして [!DNL Query Service] セッション。 その結果、 [!DNL Query Service] PostgresSQL インターフェイスは、この拡張機能をシームレスに利用できるので、

主な利点は次のとおりです。

- BI ツール自体内で CJA データビューと同等の表現を再作成する必要はありません。 <br/>詳しくは、 [データビュー](data-views.md) を参照してください。<br/>

- BI ツールと CJA 間のレポートおよび分析の一貫性が向上しました。

- CJA データを、BI ツールで既に使用可能な他のデータソースと組み合わせます。

## 前提条件

この機能を使用するには、次の手順を実行する必要があります。

- を有効にします。 [!UICONTROL CJA SQL コネクタ] をExperience Platform組織に追加します。

- 関連する製品プロファイル、ユーザーグループ、個々のユーザーの機能を設定します。<br/>
ユーザーは次にアクセスできる必要があります。
   - Experience Platformクエリサービス
   - CJA Workspace プロジェクトおよび
   - CJA データビュー。

- BI ツールを CJA SQL Connector に接続するには、有効期限のない資格情報で期限切れになる情報を使用します。 詳しくは、 [資格情報ガイド](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 有効期限が切れる資格情報または期限が切れない資格情報の設定について詳しくは、を参照してください。


## 用途

次の手順で [!DNL CJA SQL Connector] 機能を使用する場合は、SQL を直接使用するか、特定の BI ツールで使用できるドラッグ&amp;ドロップエクスペリエンスを使用できます。

### SQL

この機能は、クエリエディターまたは標準の PostgresSQL コマンドラインインターフェイス (CLI) クライアントを使用して、SQL 文内で直接使用できます。

+++ クエリエディター

Experience PlatformUI:

1. 選択 **[!UICONTROL **&#x200B;クエリ&#x200B;**]** から **[!UICONTROL **&#x200B;データ管理&#x200B;**]** をクリックします。

2. 選択 ![クエリを作成](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;クエリを作成&#x200B;**]**.

3. クエリを実行するには、SQL 文を入力し、 ![再生](assets/Smock_Play_18_N.svg) ボタン（または Shift + Enter キーを押します）。

+++


+++ PostgresSQL CLI

1. Experience PlatformUI で、PostgresSQL の資格情報を検索してコピーします。

   1. 選択 **[!UICONTROL **&#x200B;クエリ&#x200B;**]** 左側のレール（の下）から **[!UICONTROL **&#x200B;データ管理&#x200B;**]**) をクリックします。

   2. 選択 **[!UICONTROL **&#x200B;資格情報&#x200B;**]** をクリックします。

   3. 接続文字列をコピーするには、 ![コピー](assets/Smock_Copy_18_N.svg) 内 **[!UICONTROL ** PSQL コマンド&#x200B;**]** 」セクションに入力します。

2. PostgresSQL CLI を開きます。

3. ログインしてクエリの実行を開始するには、PostgresSQL CLI に接続文字列を貼り付けます。

+++

詳しくは、 [クエリエディター UI ガイド](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) を参照してください。


### BI ツール

現在、CJA SQL コネクタは、Power BIと Tableau に対してサポートされています。

+++ Power BI

1. Adobe Experience Platform UI で、PostgresSQL 資格情報の詳細を検索します。

   1. 選択 **[!UICONTROL **&#x200B;クエリ&#x200B;**]** 左側のレール（の下）から **[!UICONTROL **&#x200B;データ管理&#x200B;**]**) をクリックします。

   2. 選択 **[!UICONTROL **&#x200B;資格情報&#x200B;**]** をクリックします。

   3. 用途 ![コピー](assets/Smock_Copy_18_N.svg) 各 Postgres 資格情報パラメーター ([!UICONTROL ホスト], [!UICONTROL ポート], [!UICONTROL データベース], [!UICONTROL ユーザー名]（など）必要に応じてPower BIで使用します。

2. Power BI内：

   1. メインウィンドウで、「 」を選択します。 **[!UICONTROL **&#x200B;データの取得&#x200B;**]** をクリックします。

   2. 選択 **[!UICONTROL **&#x200B;さらに詳しく…**]** をクリックします。

   3. 内 **データの取得** 画面、検索 `PostgresSQL` をクリックし、 **[!UICONTROL ** PostgresSQL データベース&#x200B;**]** を選択します。

   4. 内 **[!UICONTROL ** PostgressSQL データベース&#x200B;**]** ダイアログ：

      1. 貼り付け **[!UICONTROL **&#x200B;ホスト&#x200B;**]** パラメーター (Experience Platformクエリから ) [!UICONTROL 資格情報] into **[!UICONTROL **&#x200B;サーバー&#x200B;**]** テキストフィールド。

      2. 貼り付け **[!UICONTROL **&#x200B;データベース&#x200B;**]** パラメーター (Experience Platformクエリから ) [!UICONTROL 資格情報] in **[!UICONTROL **&#x200B;データベース&#x200B;**]** テキストフィールド。

         追加 `?FLATTEN` から **[!UICONTROL **&#x200B;データベース&#x200B;**]** パラメーターは次のように読み込まれます。 `prod:all?FLATTEN` 例： 詳しくは、 [ネストされたデータ構造を統合して、サードパーティの BI ツールで使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) を参照してください。

      3. 次を求められた場合： **[!UICONTROL **&#x200B;データ接続&#x200B;**]** モード、選択 **[!UICONTROL ** DirectQuery **]** を使用して、データ構造が適切にフラット化されていることを確認します。

      4. 次のメッセージが表示されます。 **[!UICONTROL **&#x200B;ユーザー名&#x200B;**]** および **[!UICONTROL **&#x200B;パスワード&#x200B;**]**. Experience Platform・クエリーの同等のパラメータを使用 [!UICONTROL 資格情報].
   5. ログインに成功すると、CJA データビューの表がPower BIの **[!UICONTROL **&#x200B;ナビゲーター&#x200B;**]**. データビューテーブルは、 `dv_` 彼らの名前に


   6. 使用するデータビューテーブルを選択し、「 」を選択します。 **[!UICONTROL **&#x200B;読み込み&#x200B;**]**.

   選択した 1 つ以上のテーブルに関連付けられているすべてのディメンションと指標が右側のウィンドウに表示され、ビジュアライゼーションで使用できる状態になります。

   詳しくは、 [Power BIをクエリサービスに接続](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) を参照してください。

+++

+++Tableau

1. Experience PlatformUI で、PostgresSQL 資格情報の詳細を検索します。

   1. 選択 **[!UICONTROL **&#x200B;クエリ&#x200B;**]** 左側のレール（の下）から **[!UICONTROL **&#x200B;データ管理&#x200B;**]**) をクリックします。

   2. 選択 **[!UICONTROL **&#x200B;資格情報&#x200B;**]** をクリックします。

   3. 用途 ![コピー](assets/Smock_Copy_18_N.svg) 各 Postgres 資格情報パラメーター ([!UICONTROL ホスト], [!UICONTROL ポート], [!UICONTROL データベース], [!UICONTROL ユーザー名]（その他）必要に応じて、Tableau で使用します。

2. Tableau の場合：

   1. 選択 **[!UICONTROL **&#x200B;詳細&#x200B;**]** から **[!UICONTROL **&#x200B;サーバーへ&#x200B;**]** をクリックします。

   2. 選択 **[!UICONTROL ** PostgresSQL **]** を選択します。

   3. 内 [!UICONTROL PostgresSQL] ダイアログ：

      1. 貼り付け **[!UICONTROL **&#x200B;ホスト&#x200B;**]** パラメーター (Experience Platformクエリから ) [!UICONTROL 資格情報] into **[!UICONTROL **&#x200B;サーバー&#x200B;**]** テキストフィールド。

      2. 貼り付け **[!UICONTROL **&#x200B;ポート&#x200B;**]** パラメーター (Experience Platformクエリから ) [!UICONTROL 資格情報] into **[!UICONTROL **&#x200B;ポート&#x200B;**]** テキストフィールド。

      3. 貼り付け **[!UICONTROL **&#x200B;データベース&#x200B;**]** パラメーター (Experience Platformクエリから ) [!UICONTROL 資格情報] into **[!UICONTROL **&#x200B;データベース&#x200B;**]** テキストフィールド。

         追加 `%3FFLATTEN` から **[!UICONTROL **&#x200B;データベース&#x200B;**]** パラメーターは次のように読み込まれます。 `prod:all%3FFLATTEN` 例： 詳しくは、 [ネストされたデータ構造を統合して、サードパーティの BI ツールで使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) を参照してください。

      4. 選択 **[!UICONTROL **&#x200B;ユーザー名とパスワード&#x200B;**]** から **[!UICONTROL **&#x200B;認証&#x200B;**]** リスト。

      5. 貼り付け **[!UICONTROL **&#x200B;ユーザー名&#x200B;**]** パラメーター (Experience Platformクエリから ) [!UICONTROL 資格情報] into **[!UICONTROL **&#x200B;ユーザー名&#x200B;**]** テキストフィールド。

      6. 貼り付け **[!UICONTROL **&#x200B;パスワード&#x200B;**]** パラメーター (Experience Platformクエリから ) [!UICONTROL 資格情報] into **[!UICONTROL **&#x200B;パスワード&#x200B;**]** テキストフィールド。

      7. 選択 **[!UICONTROL **&#x200B;ログイン&#x200B;**]**.
   4. CJA データビューは、 **[!UICONTROL **&#x200B;テーブル&#x200B;**]** リスト。 データビューテーブルには、「 `dv_`.

   5. 使用するテーブルをキャンバスにドラッグします。

   これで、データビューテーブルのデータを操作して、レポートとビジュアライゼーションを作成できます。

   詳しくは、 [Tableau をクエリサービスに接続](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) を参照してください。

+++

詳しくは、 [クエリサービスにクライアントを接続](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 」の概要と使用可能な様々なツールの詳細を参照してください。

## 機能

デフォルトでは、データビューには、わかりやすい名前から生成されたテーブルセーフ名が付けられます。 例えば、 [!UICONTROL マイ Web データ] にはビュー名があります `dv_my_web_data`.

データビュー ID をテーブル名として使用する場合は、オプションで `CJA_USE_IDS` を接続時にデータベース名に設定します。 例： `prod:all?CJA_USE_IDS` は、次のような名前でデータビューを表示します。 `dv_ABC123`.

### データガバナンス

データガバナンス関連のCustomer Journey Analyticsは、Adobe Experience Platformから継承されます。 CJA と Adobe Experience Platform のデータガバナンスの統合により、機密性の高い CJA データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platform で使用されるデータセットに関して作成されたプライバシーラベルとポリシーは、 CJA データビューワークフローで表示できます。 したがって、CJA SQL Connector を使用してクエリされたデータは、定義されたプライバシーラベルとポリシーに従わない場合、適切な警告またはエラーを表示します。

### リストデータビュー

標準の PostgreSQL CLI では、 `\dv`

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

### ネストとフラット化

デフォルトでは、データビューのスキーマは、元の XDM スキーマと同様に、ネストされた構造を使用します。 この統合では、 `FLATTEN` オプション。 このオプションを使用すると、データビュー（およびセッション内の他のテーブル）のスキーマを強制的にフラット化できます。 フラット化は、構造化されたスキーマをサポートしない BI ツールで使いやすくします。 詳しくは、 [クエリサービスでのネストされたデータ構造の使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) を参照してください。

### サポートされる SQL

詳しくは、 [クエリサービス SQL リファレンス](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) を参照して、サポートされる SQL のタイプに関する完全な参照を確認してください。

パターンと例の概要については、以下のパターンの表を参照してください。

+++パターン

| パターン | 例 |
|---|---|
| スキーマの検出 | <pre>* FROM dv1 WHERE 1=0 を選択します。</pre> |
| ランク/分類 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DV1 から<br/>ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DV1 から<br/>ここで、「2022-01-01」と「2022-01-02」との間の「timestamp」<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DV1 から<br/>ここで、「2022-01-01」と「2022-01-02」との間の「timestamp」<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| HAVING 句 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DV1 から<br/>ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>GROUP BY dim1<br/>m1 > 100 |
| ユニーク、トップ <br/>ディメンション値 | <pre>DV1 から DISTINCT dim1 を選択</pre><pre>DIM1 AS dv1 を選択<br/>DV1 から<br/>ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>GROUP BY dim1</pre><pre>DIM1 AS dv1 を選択<br/>DV1 から<br/>ここで、「timestamp」 >= 「2022-01-01」および「timestamp」 &lt; 「2022-01-02」です<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>上限 15</pre> |
| 指標の合計 | <pre>SUM(metric1) AS m1 を選択します。<br/>DV1 から<br/>ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です</pre> |
| 多次元<br/>分類<br/>そして最も顕著な | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DV1 から<br/>ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DV1 から<br/>ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>1、2 でグループ化<br/>1、2 別の注文</pre><pre>SELECT DISTINCT dim1, dim2<br/>DV1 から</pre> |
| サブ選択：<br/>その他の結果<br/>フィルタリング | <pre>SELECT dim1, m1<br/>開始 (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DV1 から<br/>  ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| サブ選択：<br/>との結合<br/>データセットが次の値に含まれていません：<br/>CJA | <pre>SELECT b.key, a.dim1, a.m1<br/>開始 (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DV1 から<br/>  ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>  GROUP BY dim1<br/>)<br/>a.dim1 = b.key に対する LEFT JOIN 検索</pre> |
| サブ選択：<br/>クエリ<br/>data-views | <pre>SELECT key, SUM(m1) AS total<br/>開始 (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  DV1 から<br/>  ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>  GROUP BY dim1<br/><br/>  和集合<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  DV2 から<br/>  ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>  GROUP BY dim2<br/>キーでグループ化<br/>合計注文</pre> |
| サブ選択： <br/>レイヤソース <br/>フィルター <br/>および集計 | サブセレクトを使用してレイヤー化：<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>開始 (<br/>  \_.dim1,\_.m1 を選択<br/>  開始 (<br/>    DV1 から\*を選択<br/>    ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>  ) \_<br/>  ここで、\_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) 行<br/>1 でグループ化<br/>合計注文</pre><br/>CTE を使用する画層：<br/><pre>行を (<br/>  \_ AS (<br/>    SELECT * FROM data_ares<br/>    ここで、「timestamp」は「2021-01-01」と「2021-02-01」の間です<br/>  )<br/>  _から_.item, _.units を選択<br/>  ここで、_.ITEM が NULL ではない場合<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>(&#39;A&#39;, &#39;B&#39;, &#39;C&#39;) の ROWS.item を含む行から<br/>GROUP BY rows.item</pre> |
| を<br/>指標が次の値より前に<br/> またはが混在している<br/>寸法 | <pre>SUM(metric1) AS m1, dim1 を選択します。<br/>DV1 から<br/>ここで、「timestamp」は「2022-01-01」と「2022-01-02」の間です<br/>2 でグループ化</pre> |

{style="table-layout:auto"}

+++

### ディメンション

デフォルトで使用可能な任意のディメンションまたはデータビューで定義されたディメンションを選択できます。 ID でディメンションを選択します。

### 指標

選択できる指標は次のとおりです。

- デフォルトで使用可能な指標

- データビューで定義される

- ユーザーがアクセスできるデータビューと互換性のある計算指標。

指標は、 `SUM(metric)` 式は、他の SQL ソースで使用する場合と同様に使用します。

:

- `SELECT COUNT(*)` または `COUNT(1)` 回数指標を取得します。

- `SELECT COUNT(DISTINCT dimension)` または `SELECT APPROX_COUNT_DISTINCT(dimension)` ：ディメンションの個別概算値をカウントします。 詳しくは、 [区別のカウント](#counting-distincts).

- [インライン計算](#inline-calculations) を使用して、即座に指標を組み合わせたり、計算を行ったりできます。

#### 区別のカウント

CJA の仕組みの基本的な性質により、正確なカウントを取得できるディメンションは、 `adobe_personid` ディメンション。 次の SQL 文 `SELECT COUNT(DISTINCT adobe_personid)` または `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` ユニークユーザーの数であるデフォルトの訪問者指標の値を返します。 その他のディメンションの場合は、約個別カウントが返されます。

#### 条件付き指標

埋め込む `IF` または `CASE` 条項 `SUM` または `COUNT` 関数を使用して、選択した指標に固有のフィルターを追加できます。 これらの句を追加することは、Workspace レポートテーブルの指標列にフィルターを適用することに似ています。

例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### インライン計算

指標の式に、 `SELECT` 計算指標で数値を定義する代わりに、を使用する必要があります。 次の表に、サポートされる式のタイプを示します。

| 演算子または関数 | 詳細 |
|---|---|
| `+`, `-`, `*`, `/`、および `%` | 加算、減算、乗算、除算、剰余 |
| `-X` または`+X` | X が指標の式である記号または指標の変更 |
| `PI()` | π定数 |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`、および `TANH` | 単項数学関数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | バイナリ数学関数 |

{style="table-layout:auto"}

### 特殊な列

**タイムスタンプ**

この `timestamp` 特別な列は、クエリの日付範囲を指定するために使用されます。 日付範囲は、 `BETWEEN` 表現または一対の `timestamp` `>`, `>=`, `<`, `<=` チェック `AND`一緒に
この `timestamp` はオプションで、全範囲を指定しない場合は、デフォルトが使用されます。

- 最小値のみが指定されている場合 (`timestamp > X` または ` timestamp >= X`) の値を指定する場合、範囲は X から現在までです。

- 最大値 (`timestamp < X` または `timestamp <= X`) の値を指定する場合、X ～ 30 日の範囲です。

- 指定しなかった場合、現在から 30 日までの範囲です。

タイムスタンプの範囲は、RankedRequest の日付範囲グローバルフィルタに変換されます。
timestamp フィールドは、解析するために Date-Time 関数で使用し、イベントタイムスタンプを切り捨てることもできます。

**日付範囲**

この `daterange` 特別な列は次のように機能します。  `timestamp`ただし、フィルタリングは 1 日に制限されます。 この `daterange` はオプションで、の範囲のデフォルトはと同じです。 `timestamp`.
この `daterange` フィールドは、日付/時刻関数で解析するために使用し、イベントの日付を切り捨てることができます。

**filterId**

この `filterId` special 列はオプションで、外部定義のフィルターをクエリに適用するために使用します。 外部的に定義されたフィルターをクエリに適用する方法は、Workspace のパネルでフィルターをドラッグする場合と似ています。 で複数のフィルター ID を指定できます `AND` — 彼らを呼びながら。

### WHERE 句

WHERE 句は、次の 3 つの手順で処理されます。

1. 日付範囲を `timestamp` 特殊フィールド。

2. 外部で定義された項目を検索 `filterId`フィルターに含める s。

3. 残りの式をアドホックフィルターに変換します。

この処理は、 `AND`の `WHERE` 句を使用します。 各最上位レベル `AND`ed 式は上記のいずれかと一致する必要があります。 第 1 レベルの `AND`s、または ( `WHERE` 句の使用 `OR`の最上位レベルでは、はアドホックフィルターとして処理されます。

### 並べ替え順

デフォルトでは、クエリは、最初に選択された指標を降順で並べ替えます。 デフォルトの並べ替え順は、 `ORDER BY ... ASC` または `ORDER BY ... DESC`. 次を使用する場合、 `ORDER BY`を指定する必要があります。 `ORDER BY` を選択します。

また、 `-` （マイナス）を指標の前に表示します。 以下の両方の文は、同じ順序になります。

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般的な機能のサポート

| 関数 | 例 | 詳細 |
|---|---|---|
| [CAST（列 AS 型）](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` または<br/> `` `timestamp`::string `` | タイプキャストは現在サポートされていませんが、エラーは発生しません。 この `CAST` 関数は無視されます。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 時間文字列をタイムスタンプとして解析し、 `WHERE` 句を使用します。 |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 時間文字列をタイムスタンプとして解析し、 `WHERE` 句を使用して、オプションでその時間文字列の形式を指定します。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 日付文字列をタイムスタンプとして解析し、 `WHERE` 句を使用します。 |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 日付文字列をタイムスタンプとして解析し、 `WHERE` 句を使用して、必要に応じてその日付文字列の形式を指定します。 |

{style="table-layout:auto"}

### Dimension機能のサポート

これらの関数は、 `SELECT`, `WHERE` 句、または条件付き指標で使用できます。

**文字列関数**

| 関数 | 例 | 詳細 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 渡されたフィールドで動的ディメンション ID を生成します。 |

{style="table-layout:auto"}

**日付 — 時間関数**

| 関数 | 例 | 詳細 |
|---|---|---|
| [YEAR（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [MONTH（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [DAY（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [DAYOFWEEK（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 名前ではない数値が必要なので、値の代わりに項目 ID を使用します。 |
| [DAYOFYEAR（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [WEEK（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [QUARTER（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [HOUR（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 名前ではない数値が必要なので、値の代わりに項目 ID を使用します。 |
| [MINUTE（日付または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 |
| [EXTRACT（パーツの開始日時）](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 この関数の一部では、わかりやすい名前ではない数値が必要なので、値の代わりに項目 ID を使用します。<br/>次のパーツがサポートされています。<br> — キーワード： `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/> — 文字列：  `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`または `'MINUTE'`. |
| [DATE_PART（部分、日付、または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。 この関数の一部では、わかりやすい名前ではない数値が必要なので、値の代わりに項目 ID を使用します。<br/>サポートされる文字列部分は次のとおりです。 `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`または `'MINUTE'`. |
| [DATE_TRUNC（精度、日付、または日時）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 渡されたフィールドで動的ディメンション ID を生成します。<br/>サポートされる文字列の精度は次のとおりです。 `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`または `'MINUTE'`. |

{style="table-layout:auto"}

