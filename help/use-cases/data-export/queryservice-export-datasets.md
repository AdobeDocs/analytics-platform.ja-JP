---
title: Experience Platformクエリサービス（Data Distiller）とデータセットの書き出し
description: クエリサービス（データDistiller）とデータセットの書き出しを使用してデータを書き出す方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 3568aad27001b322da77f5d1fb762db5ba6d433d
workflow-type: tm+mt
source-wordcount: '2642'
ht-degree: 9%

---

# クエリサービス（Data Distiller）とデータセットの書き出し

この記事では、Experience Platformクエリサービス（データDistiller）とデータセット書き出しの組み合わせを使用して、次の [ データ書き出しの使用例 ](overview.md) を実装する方法の概要を説明します。

- データの検証
- データレイク、BI ツールのData Warehouse
- 人工知能と機械学習の準備。


Adobe Analyticsでは、[ データフィード ](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) 機能を使用して、これらのユースケースを実装できます。 データフィードは、Adobe Analytics から生データを取得するための強力な方法です。この記事では、上記のユースケースを実装できるよう、Experience Platformから同様のタイプの生データを取得する方法について説明します。 該当する場合、この記事で説明されている機能をAdobe Analytics データフィードと比較して、データとプロセスの違いを明確にします。

## はじめに

クエリサービス（Data Distiller）とデータセット書き出しを使用したデータの書き出しは、次の要素で構成されています。

- **クエリサービス** を使用して、データフィードのデータを出力データセット ![ 出力データセット ](../assets/output-dataset.svg) として生成する **スケジュールされたクエリ** を定義する。
- **データセット書き出し** を使用して、出力データセットをクラウドストレージの宛先に書き出す **スケジュールされたデータセット書き出し** を定義する。

![ データフィード ](../assets/queryservice-export-datasets.svg)


## 前提条件

このユースケースで説明している機能を使用する前に、次の要件をすべて満たしていることを確認してください。

- Experience Platformのデータレイクにデータを収集する実用的な実装。
- バッチクエリを実行する権限を持っていることを確認するには、Data Distiller アドオンにアクセスします。 詳しくは、[ クエリサービスのパッケージ化 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging) を参照してください。
- Real-Time CDP Prime または Ultimate パッケージ、Adobe Journey OptimizerまたはCustomer Journey Analyticsを購入した場合に使用できる、データセットの書き出し機能にアクセスできます。 詳しくは、[ クラウドストレージの宛先へのデータセットの書き出し ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) を参照してください。
- データフィードの生データの書き出し先となる、1 つ以上の設定済みの宛先（例：Amazon S3、Google Cloud Storage）。


## クエリサービス

Experience Platformクエリサービスを使用すると、Experience Platformデータレイク内のデータセットに対して、データベースのテーブルと同じようにクエリを実行して結合できます。 その後、結果を新しいデータセットとして取得し、レポートや書き出しでさらに使用できます。

クエリサービス [ ユーザーインターフェイス ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview)、PostgresQL プロトコルを介して接続された [ クライアント ](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview)、または [RESTful API](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) を使用して、データフィードのデータを収集するクエリを作成およびスケジュールできます。

### クエリを作成

SELECT 文やその他の制限付きコマンドに標準 ANSI SQL のすべての機能を使用して、データフィードのデータを生成するクエリを作成および実行できます。 詳しくは、[SQL 構文 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax) を参照してください。 この SQL 構文を超えて、Adobeでは次の機能をサポートしています。

- 事前に作成された [Adobe定義関数（ADF）は ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions)Experience Platformデータレイクに保存されたイベントデータに対して一般的なビジネス関連タスクを実行するのに役立ちます。これには、[ セッション化 ](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) および [ アトリビューション ](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview) の関数が含まれます。
- いくつかのビルトイン [Spark SQL 関数 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions)、
- [ メタデータ PostgreSQL コマンド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata)、
- [ 準備済みステートメント ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements)。

#### データフィード列

クエリで使用できる XDM フィールドは、データセットが基づいているスキーマ定義によって異なります。 データセットの基礎となるスキーマを理解していることを確認します。 詳しくは、[ データセット UI ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide) を参照してください。

データフィード列と XDM フィールド間のマッピングを定義するには、[Analytics フィールドマッピング ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) を参照してください。 スキーマ、クラス、フィールドグループ、データタイプなど、XDM リソースの管理方法について詳しくは、[ スキーマ UI の概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields) も参照してください。

例えば、*ページ名* をデータフィードの一部として使用する場合は、次のようになります。

- Adobe Analytics データフィードの UI では、列として **[!UICONTROL pagename]** を選択すると、データフィードの定義に追加されます。
- クエリサービスでは、**Web サイトのサンプルイベントスキーマ（グローバル v1.1）** エクスペリエンスイベントスキーマに基づいて） `sample_event_dataset_for_website_global_v1_1` データセットの `web.webPageDetails.name` をクエリに含めます。 詳しくは、[Web 詳細スキーマフィールドグループ ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details) を参照してください。


#### ID

Experience Platformとして、様々な ID を使用できます。 クエリを作成する場合は、ID に対して正しくクエリを実行していることを確認します。


ID は、多くの場合、別のフィールドグループで見つかります。 実装では、ECID （`ecid`）は、`core` オブジェクトを持つフィールドグループの一部として定義できます。このフィールドグループは、それ自体が `identification` オブジェクトの一部です（例：`_sampleorg.identification.core.ecid`）。 ECID の整理はスキーマによって異なる場合があります。

または、`identityMap` を使用して ID をクエリできます。 `identityMap` は `Map` 型で、[ ネストされたデータ構造 ](#nested-data-structure) を使用します。

Experience Platformで ID フィールドを定義する方法について詳しくは、[UI での ID フィールドの定義 ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity) を参照してください。

Analytics ソースコネクタを使用する際にAdobe Analytics ID がプライマリ ID にどのようにマッピングされるかについては [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data)Analytics データのExperience Platform ID を参照してください。 このマッピングは、Analytics ソースコネクタを使用していない場合でも、ID を設定するためのガイダンスとして機能する場合があります。


#### ヒットレベルのデータと識別

実装方法に基づいて、従来Adobe Analyticsで収集されていたヒットレベルのデータが、タイムスタンプ付きのイベントデータとしてExperience Platformに保存されるようになりました。 次の表は、[Analytics フィールドマッピング ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) から抽出したもので、ヒットレベル固有のAdobe Analytics データフィード列をクエリ内の対応する XDM フィールドにマッピングする方法の例を示しています。 また、この表は、XDM フィールドを使用してヒット、訪問、訪問者を識別する方法の例も示しています。

| データフィード列 | XDM フィールド | タイプ | 説明 |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | ヒットを識別する一意の ID。 |
| `hitid_low` | `_id` | string | `hitid_high` と共に使用して、ヒットを一意に識別します。 |
| `hitid_high` | `_id` | string | `hitid_high` と共に使用して、ヒットを一意に識別します。 |
| `hit_time_gmt` | `receivedTimestamp` | string | ヒットのタイムスタンプ（UNIX® 時間に基づく）。 |
| `cust_hit_time_gmt` | `timestamp` | string | このタイムスタンプは、タイムスタンプが有効なデータセットでのみ使用されます。 このタイムスタンプは、UNIX® 時間に基づいて、ヒットと共に送信されます。 |
| `visid_high` + `visid_low` | `identityMap` | オブジェクト | 訪問の一意の ID。 |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | 訪問の一意の ID。 |
| `visid_high` | `endUserIDs._experience.aaid.primary` | ブール型 | `visid_low` と共に使用して、訪問を一意に識別します。 |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | `visid_low` と共に使用して、訪問を一意に識別します。 |
| `visid_low` | `identityMap` | オブジェクト | `visid_high` と共に使用して、訪問を一意に識別します。 |
| `cust_visid` | `identityMap` | オブジェクト | 顧客訪問者 ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | オブジェクト | 顧客訪問者 ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | ブール型 | 顧客訪問者 ID 名前空間コード。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | `visid_low` と共に使用して、顧客訪問者 ID を一意に識別します。 |
| `geo\_*` | `placeContext.geo.* ` | 文字列、数値 | ジオロケーションデータ（国、地域、都市など） |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | string | ヒットに対してトリガーされる標準コマースイベントとカスタムイベント。 |
| `page_event` | `web.webInteraction.type` | string | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、離脱リンク、クリックされたカスタムリンク）。 |
| `page_event` | `web.webInteraction.linkClicks.value` | number | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、離脱リンク、クリックされたカスタムリンク）。 |
| `page_event_var_1` | `web.webInteraction.URL` | string | リンクトラッキングイメージリクエストでのみ使用される変数。この変数には、クリックされたダウンロードリンク、離脱リンク、またはカスタムリンクの URL が含まれます。 |
| `page_event_var_2` | `web.webInteraction.name` | string | リンクトラッキングイメージリクエストでのみ使用される変数。このリストは、リンクのカスタム名をリスト表示します（指定されている場合）。 |
| `paid_search` | `search.isPaid` | ブール型 | ヒットが有料検索の検出に一致した場合に設定されるフラグ。 |
| `ref_type` | `web.webReferrertype` | string | ヒットのリファラルのタイプを表す数値 ID。 |

#### 列を投稿

Adobe Analytics データフィードでは、`post_` プレフィックスが付いた列という概念を使用します。プレフィックスは、処理後のデータを含む列です。 詳しくは、[データフィードに関する FAQ](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post) を参照してください。

Experience PlatformEdge Network（Web SDK、Mobile SDK、Server API）を使用してデータセットに収集されたデータには、`post_` フィールドという概念はありません。 その結果、プレフィックス `post_` 付けられたデータフィード列と *非* プレフィックスのデータフィード列は、同じ XDM フィールドにマッピ `post_` グされます。 例えば、`page_url` と `post_page_url` の両方のデータフィード列が同じ `web.webPageDetails.URL` XDM フィールドにマッピングされるとします。

データ処理の違いの概要については、[Adobe AnalyticsとCustomer Journey Analytics間のデータ処理の比較 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) を参照してください。

ただし、Experience Platformデータレイクで収集されるデータの `post_` プレフィックス列タイプでは、データフィードのユースケースで使用する前に高度な変換が必要です。 クエリでこれらの高度な変換を実行するには、セッション化、アトリビューション、重複排除に [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions)0&rbrace;Adobe定義関数を使用する必要があります。 これらの関数の使用方法については、[ 例 ](#examples) を参照してください。

#### 参照

他のデータセットからのデータを検索するには、標準の SQL 機能（`WHERE` 句、`INNER JOIN`、`OUTER JOIN` など）を使用します。

#### 計算

フィールド（列）に対して計算を実行するには、標準の SQL 関数（例：`COUNT(*)`）または Spark SQL の一部である [ 数学演算子と統計演算子および関数 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) を使用します。 また、[window 関数 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) は、集計を更新し、順序付きサブセット内の各行の単一の項目を返すサポートを提供します。 これらの関数の使用方法については、[ 例 ](#examples) を参照してください。

#### ネストされたデータ構造

データセットのベースとなるスキーマには、多くの場合、ネストされたデータ構造など、複雑なデータタイプが含まれています。 前述の `identityMap` は、ネストされたデータ構造の例です。 `identityMap` データの例については、以下を参照してください。

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

Spark SQL の [`explode()` 関数またはその他の配列関数を使用して ](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) ネストされたデータ構造内のデータにアクセスできます。次に例を示します。

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

または、ドット表記を使用して個々の要素を参照することもできます。 次に例を示します。

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

詳しくは、[クエリサービスでのネストされたデータ構造の操作](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures)を参照してください。


#### 例

クエリ：

- Experience Platformデータレイク内のデータセットのデータを使用する
- は、Adobe定義関数や Spark SQL、あるいはこれらのいずれかのその他の機能を活用しています。
- 同等のAdobe Analytics データフィードと同様の結果が得られます。

詳しくは、

- [ 参照を中止 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [ アトリビューション分析 ](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [ ボットフィルタリング ](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- およびその他 [ クエリサービスガイドでサポートされているその他のユースケース ](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview)。

以下に、セッション間でアトリビューションを適切に適用する例と、その方法を示します

- 過去 90 日間をルックバックとして使用します。
- セッション化やアトリビューションなどのウィンドウ関数を適用する。
- `ingest_time` に基づいて出力を制限します。

+++
詳細

  そのためには…

   - 処理ステータステーブル `checkpoint_log` を使用して、現在の取り込み時間と最後の取り込み時間を追跡します。 詳しくは、[ このガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/incremental-load) を参照してください。
   - システム列の削除を無効にして、`_acp_system_metadata.ingestTime` を使用できるようにします。
   - 最も内側の `SELECT` を使用して、使用するフィールドを取得し、セッション化やアトリビューションの計算のためにイベントをルックバック期間に制限します。 例：90 日。
   - 次のレベルの `SELECT` を使用して、セッション化やアトリビューションウィンドウ関数、その他の計算を適用します。
   - 出力テーブルで `INSERT INTO` を使用して、ルックバックを前回の処理時間以降に到達したイベントのみに制限します。 これを行うには、処理ステータステーブルに最後に保存された時間に対して `_acp_system_metadata.ingestTime ` フィルタリングします。

  **セッション化ウィンドウ関数の例**

  ```sql
  $$ BEGIN
     -- Disable dropping system columns
     set drop_system_columns=false; 
  
     -- Initialize variables
     SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
     -- Get the last processed batch ingestion time
     SET @from_batch_ingestion_time = SELECT coalesce(last_batch_ingestion_time, 'HEAD') 
        FROM checkpoint_log a 
        JOIN (
              SELECT MAX(process_timestamp) AS process_timestamp 
              FROM checkpoint_log
              WHERE process_name = 'data_feed' 
              AND process_status = 'SUCCESSFUL'
        ) b
        ON a.process_timestamp = b.process_timestamp;
  
     -- Get the last batch ingestion time
     SET @to_batch_ingestion_time = SELECT MAX(_acp_system_metadata.ingestTime) 
        FROM events_dataset;
  
     -- Sessionize the data and insert into data_feed.
     INSERT INTO data_feed
     SELECT *
     FROM (
        SELECT
              userIdentity,
              timestamp,
              SESS_TIMEOUT(timestamp, 60 * 30) OVER (
                 PARTITION BY userIdentity
                 ORDER BY timestamp
                 ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
              ) AS session_data,
              page_name,
              ingest_time
        FROM (
              SELECT
                 userIdentity,
                 timestamp,
                 web.webPageDetails.name AS page_name,
                 _acp_system_metadata.ingestTime AS ingest_time
              FROM events_dataset
              WHERE timestamp >= current_date - 90
        ) AS a
        ORDER BY userIdentity, timestamp ASC
     ) AS b
     WHERE b.ingest_time >= @from_batch_ingestion_time;
  
     -- Update the checkpoint_log table
     INSERT INTO checkpoint_log
     SELECT
        'data_feed' process_name,
        'SUCCESSFUL' process_status,
        cast(@to_batch_ingestion_time AS string) last_batch_ingestion_time,
        cast(@last_updated_timestamp AS TIMESTAMP) process_timestamp
  END
  $$;
  ```

  **アトリビューションウィンドウ関数の例**

  ```sql
  $$ BEGIN
   SET drop_system_columns=false;
  
  -- Initialize variables
   SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
  -- Get the last processed batch ingestion time 1718755872325
   SET @from_batch_ingestion_time =
       SELECT coalesce(last_snapshot_id, 'HEAD')
       FROM checkpoint_log a
       JOIN (
           SELECT MAX(process_timestamp) AS process_timestamp
           FROM checkpoint_log
           WHERE process_name = 'data_feed'
           AND process_status = 'SUCCESSFUL'
       ) b
       ON a.process_timestamp = b.process_timestamp;
  
   -- Get the last batch ingestion time 1718758687865
   SET @to_batch_ingestion_time =
       SELECT MAX(_acp_system_metadata.ingestTime)
       FROM demo_data_trey_mcintyre_midvalues;
  
   -- Sessionize the data and insert into new_sessionized_data
   INSERT INTO new_sessionized_data
   SELECT *
   FROM (
       SELECT
           _id,
           timestamp,
           struct(User_Identity,
           cast(SESS_TIMEOUT(timestamp, 60 * 30) OVER (
               PARTITION BY User_Identity
               ORDER BY timestamp
               ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
           ) as string) AS SessionData,
           to_timestamp(from_unixtime(ingest_time/1000, 'yyyy-MM-dd HH:mm:ss')) AS IngestTime,      
           PageName,
           first_url,
           first_channel_type
             ) as _demosystem5
       FROM (
           SELECT
               _id,
               ENDUSERIDS._EXPERIENCE.MCID.ID as User_Identity,
               timestamp,
               web.webPageDetails.name AS PageName,
              attribution_first_touch(timestamp, '', web.webReferrer.url) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_url,
              attribution_first_touch(timestamp, '',channel.typeAtSource) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_channel_type,
               _acp_system_metadata.ingestTime AS ingest_time
           FROM demo_data_trey_mcintyre_midvalues
           WHERE timestamp >= current_date - 90
       )
       ORDER BY User_Identity, timestamp ASC    
   )
   WHERE _demosystem5.IngestTime >= to_timestamp(from_unixtime(@from_batch_ingestion_time/1000, 'yyyy-MM-dd HH:mm:ss'));
  
  -- Update the checkpoint_log table
  INSERT INTO checkpoint_log
  SELECT
     'data_feed' as process_name,
     'SUCCESSFUL' as process_status,
     cast(@to_batch_ingestion_time AS string) as last_snapshot_id,
     cast(@last_updated_timestamp AS timestamp) as process_timestamp;
  
  END
  $$;
  ```

+++


### スケジュール クエリ

クエリをスケジュールして、クエリが実行され、結果が好みの間隔で生成されるようにします。

#### クエリエディターの使用

クエリエディターを使用してクエリをスケジュールできます。 クエリをスケジュールする場合は、出力データセットを定義します。 詳しくは、[ クエリスケジュール ](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules) を参照してください。


#### Query Service API の使用

または、RESTful API を使用してクエリを定義し、クエリのスケジュールを設定することもできます。 詳しくは、[Query Service API ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) を参照してください。
クエリを作成する場合（[ クエリを作成する ](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)）やクエリのスケジュールを作成する場合（[ スケジュールされたクエリを作成する ](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)）は、出力データセットをオプションの `ctasParameters` プロパティの一部として定義していることを確認します。



## データセットの書き出し

クエリを作成し、スケジュールを設定し、結果を確認したら、生のデータセットをクラウドストレージの宛先に書き出すことができます。 この書き出しは、データセット書き出し宛先と呼ばれるExperience Platformー宛先の用語で使用されます。 詳しくは、[ クラウドストレージの宛先へのデータセットの書き出し ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) を参照してください。

次のクラウドストレージの宛先がサポートされています。

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### EXPERIENCE PLATFORMUI

Experience PlatformUI を使用して、出力データセットの書き出しをスケジュールできます。 この節では、関連する手順について説明します。

#### 宛先を選択

出力データセットを書き出すクラウドストレージの宛先を決定したら、[ 宛先を選択 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination) します。 優先クラウドストレージの宛先をまだ設定していない場合は、[ 新しい宛先接続を作成する ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination) 必要があります。

宛先の設定の一環として、次のことができます

- ファイルタイプ（JSON または Parquet）を定義します。
- 結果のファイルが圧縮されるかどうか、および
- マニフェストファイルを含めるかどうか。


#### データセットを選択

宛先を選択したら、次の **[!UICONTROL データセットを選択]** 手順で、データセットのリストから出力データセットを選択する必要があります。 複数のスケジュールされたクエリを作成し、出力データセットを同じクラウドストレージ宛先に送信する場合、対応する出力データセットを選択できます。 詳しくは [ データセットの選択 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) を参照してください。

#### データセット書き出しのスケジュール設定

最後に、**[!UICONTROL スケジュール設定]** 手順の一部としてデータセットの書き出しをスケジュールします。 その手順では、スケジュールと、出力データセットの書き出しを増分にするかどうかを定義できます。 詳しくは [ データセットの書き出しをスケジュール ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) を参照してください。


#### 最終手順

[ 確認 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) 選択し、正しければ、出力データセットのクラウドストレージ宛先への書き出しを開始します。

データの書き出しが正常に行われたことを [ 確認 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) する必要があります。 データセットを書き出す際、Experience Platformは、書き出し先に定義されたストレージの場所に 1 つまたは複数の `.json` ファイルまたは `.parquet` ファイルを作成します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM` のパターンに従って、書き出しのたびに新しいフォルダーが作成されます。 デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

### フローサービス API

または、API を使用して出力データセットの書き出しを書き出し、スケジュールすることもできます。 含まれる手順は、[Flow Service API を使用したデータセットの書き出し ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets) に記載されています。

#### 基本を学ぶ

データセットを書き出すには、[ 必要な権限 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions) があることを確認します。 また、出力データセットの送信先がデータセットの書き出しをサポートしていることを確認します。 次に、API 呼び出しで使用する [ 必須ヘッダーとオプションヘッダーの値を収集する ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) 必要があります。 また、データセットを書き出す [ 宛先の接続仕様 ID とフロー仕様 ID](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) を識別する必要もあります。

#### 適格なデータセットの取得

書き出し用に [ 適格なデータセットのリストを取得 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) し、[`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API を使用して、出力データセットがそのリストに含まれているかどうかを確認できます。


#### ソース接続を作成

次に、クラウドストレージ宛先に書き出す、出力データセット用に一意の ID を使用して、[ ソース接続を作成 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) する必要があります。 [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API を使用します。

#### 宛先に対する認証（ベース接続の作成）

[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API を使用して認証を行い、クラウドストレージの宛先に資格情報を安全に保存するには、[ ベース接続を作成 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) する必要があります。


#### エクスポートパラメーターの指定

次に、もう一度 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API を使用して、出力データセット用に [ 書き出しパラメーターを保存する追加のターゲット接続を作成 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) する必要があります。 これらの書き出しパラメーターには、場所、ファイル形式、圧縮などが含まれます。

#### データフローの設定

最後に、[ データフローの設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) を行い、[`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API を使用して出力データセットがクラウドストレージの宛先に書き出されるようにします。 この手順では、`scheduleParams` パラメーターを使用して、書き出しのスケジュールを定義できます。

#### データフローの検証

[ データフローの正常な実行を確認 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) するには、[`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API を使用して、データフロー ID をクエリパラメーターとして指定します。 このデータフロー ID は、データフローを設定したときに返される識別子です。

[ 検証 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) 成功したデータ書き出し。 データセットを書き出す際、Experience Platformは、書き出し先に定義されたストレージの場所に 1 つまたは複数の `.json` ファイルまたは `.parquet` ファイルを作成します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM` のパターンに従って、書き出しのたびに新しいフォルダーが作成されます。 デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

## まとめ

つまり、Adobe Analytics データフィード機能のエミュレートは、クエリサービスを使用してスケジュール済みクエリを設定し、これらのクエリの結果をスケジュール済みデータセット書き出しで使用することを意味します。

>[!IMPORTANT]
>
>このユースケースには、2 つのスケジューラーが含まれています。 エミュレートされたデータフィード機能が適切に動作することを保証するには、クエリサービスとデータ書き出しで設定されたスケジュールが干渉しないようにしてください。
