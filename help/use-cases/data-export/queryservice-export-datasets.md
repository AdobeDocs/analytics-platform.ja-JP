---
title: Experience Platformクエリサービス（Data Distiller）とデータセットの書き出し
description: クエリサービス（データDistiller）とデータセットの書き出しを使用してデータを書き出す方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '2475'
ht-degree: 10%

---

# クエリサービス（Data Distiller）とデータセットの書き出し

この記事では、Experience Platformクエリサービス（Data Distiller）とデータセット書き出しの組み合わせを使用して、以下を実装する方法について説明します [データ書き出しのユースケース](overview.md):

- データの検証
- データレイク、BI ツールのData Warehouse
- 人工知能と機械学習の準備。


Adobe Analyticsでは、のコンポーネントを使用してこれらのユースケースを実装できます [データフィード](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) 機能。 データフィードは、Adobe Analytics から生データを取得するための強力な方法です。この記事では、上記のユースケースを実装できるよう、Experience Platformから同様のタイプの生データを取得する方法について説明します。 該当する場合、この記事で説明されている機能をAdobe Analytics データフィードと比較して、データとプロセスの違いを明確にします。

## はじめに

クエリサービス（Data Distiller）とデータセット書き出しを使用したデータの書き出しは、次の要素で構成されています。

- の定義 **スケジュール済みクエリ** は、データフィードのデータを出力データセットとして生成します ![出力データセット](../assets/output-dataset.svg)、使用 **クエリサービス**.
- の定義 **スケジュールされたデータセット書き出し** を使用して、出力データセットをクラウドストレージの宛先に書き出す **データセットの書き出し**.

![データフィード](../assets/queryservice-export-datasets.svg)


## 前提条件

このユースケースで説明している機能を使用する前に、次の要件をすべて満たしていることを確認してください。

- Experience Platformのデータレイクにデータを収集する実用的な実装。
- バッチクエリを実行する権限を持っていることを確認するには、Data Distiller アドオンにアクセスします。 参照： [クエリサービスのパッケージ化](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging) を参照してください。
- Real-Time CDP Prime または Ultimate パッケージ、Adobe Journey OptimizerまたはCustomer Journey Analyticsを購入した場合に使用できる、データセットの書き出し機能にアクセスできます。 参照： [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) を参照してください。
- データフィードの生データの書き出し先となる、1 つ以上の設定済みの宛先（例：Amazon S3、Google Cloud Storage）。


## クエリサービス

Experience Platformクエリサービスを使用すると、Experience Platformデータレイク内のデータセットに対して、データベースのテーブルと同じようにクエリを実行して結合できます。 その後、結果を新しいデータセットとして取得し、レポートや書き出しでさらに使用できます。

クエリサービスを使用できます [ユーザーインターフェイス](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview), a [postgresql プロトコルを使用して接続されたクライアント](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview)、または [RESTful API](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) データフィードのデータを収集するクエリを作成およびスケジュールします。

### クエリを作成

SELECT 文やその他の制限付きコマンドに標準 ANSI SQL のすべての機能を使用して、データフィードのデータを生成するクエリを作成および実行できます。 参照： [SQL 構文](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax) を参照してください。 この SQL 構文を超えて、Adobeでは次の機能をサポートしています。

- ビルド済み [Adobe定義関数（ADF）](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) これにより、イベントデータレイクに保存されたExperience Platformデータに対して、次のような一般的なビジネス関連タスクを実行できます [セッション化](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) および [帰属](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- 複数のビルトイン [Spark SQL 関数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [メタデータ PostgreSQL コマンド](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [準備済み文](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### データフィード列

クエリで使用できる XDM フィールドは、データセットが基づいているスキーマ定義によって異なります。 データセットの基礎となるスキーマを理解していることを確認します。 詳細については、を参照してください [データセット UI ガイド](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide).

データフィード列と XDM フィールド間のマッピングを定義するには、を参照してください。 [Analytics フィールドのマッピング](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). 関連トピック [スキーマ UI の概要](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields) スキーマ、クラス、フィールドグループ、データタイプなど、XDM リソースの管理方法について詳しくは、こちらを参照してください。

例えば、を使用する場合 *ページ名* データフィードの一部として、次の操作を行います。

- Adobe Analytics データフィードの UI では、次のように選択します **[!UICONTROL pagename]** をデータフィード定義に追加する列として使用します。
- クエリサービスでは、次の操作を実行します `web.webPageDetails.name` から `sample_event_dataset_for_website_global_v1_1` データセット（ **Web サイトのサンプルイベントスキーマ（グローバル v1.1）** （クエリ内の）エクスペリエンスイベントスキーマ。 を参照してください。 [Web 詳細スキーマフィールドグループ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details) を参照してください。


#### ID

Experience Platformとして、様々な ID を使用できます。 クエリを作成する場合は、ID に対して正しくクエリを実行していることを確認します。


ID は、多くの場合、別のフィールドグループで見つかります。 実装 ECID （`ecid`）は、 `core` オブジェクト（それ自体は AEM の一部） `identification` オブジェクト（例： `_sampleorg.identification.core.ecid`）に設定します。 ECID の整理はスキーマによって異なる場合があります。

または、以下を使用できます。 `identityMap` にアクセスして ID をクエリします。 この `identityMap` のタイプは `Map` およびでは、 [ネストされたデータ構造](#nested-data-structure).

参照： [UI での ID フィールドの定義](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) Experience Platformで ID フィールドを定義する方法の詳細を参照してください。

こちらを参照してください [Analytics データ内のプライマリ識別情報](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) Analytics ソースコネクタを使用する際にAdobe Analytics ID をExperience Platform ID にマッピングする方法を理解するために説明します。 このマッピングは、Analytics ソースコネクタを使用していない場合でも、ID を設定するためのガイダンスとして機能する場合があります。


#### ヒットレベルのデータと識別

実装方法に基づいて、従来Adobe Analyticsで収集されていたヒットレベルのデータが、タイムスタンプ付きのイベントデータとしてExperience Platformに保存されるようになりました。 次のテーブルは、から抽出されます。 [Analytics フィールドのマッピング](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) また、ヒットレベル固有のAdobe Analytics データフィード列を、クエリの対応する XDM フィールドにマッピングする方法の例を示します。 また、この表は、XDM フィールドを使用してヒット、訪問、訪問者を識別する方法の例も示しています。

| データフィード列 | XDM フィールド | タイプ | 説明 |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | ヒットを識別する一意の ID。 |
| `hitid_low` | `_id` | string | 使用対象 `hitid_high` ヒットを一意に識別する。 |
| `hitid_high` | `_id` | string | 使用対象 `hitid_high` ヒットを一意に識別する。 |
| `hit_time_gmt` | `receivedTimestamp` | string | ヒットのタイムスタンプ（UNIX® 時間に基づく）。 |
| `cust_hit_time_gmt` | `timestamp` | string | このタイムスタンプは、タイムスタンプが有効なデータセットでのみ使用されます。 このタイムスタンプは、UNIX® 時間に基づいて、ヒットと共に送信されます。 |
| `visid_high` + `visid_low` | `identityMap` | オブジェクト | 訪問の一意の ID。 |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | 訪問の一意の ID。 |
| `visid_high` | `endUserIDs._experience.aaid.primary` | ブール型 | 使用対象 `visid_low` 訪問を一意に識別する。 |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | 使用対象 `visid_low` 訪問を一意に識別する。 |
| `visid_low` | `identityMap` | オブジェクト | 使用対象 `visid_high` 訪問を一意に識別する。 |
| `cust_visid` | `identityMap` | オブジェクト | 顧客訪問者 ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | オブジェクト | 顧客訪問者 ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | ブール型 | 顧客訪問者 ID 名前空間コード。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | 使用対象 `visid_low` 顧客訪問者 id を一意に識別します。 |
| `geo\_*` | `placeContext.geo.* ` | 文字列、数値 | ジオロケーションデータ（国、地域、都市など） |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`、...、 `_experience.analytics.event901_1000.*` | string | ヒットに対してトリガーされる標準コマースイベントとカスタムイベント。 |
| `page_event` | `web.webInteraction.type` | string | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、離脱リンク、クリックされたカスタムリンク）。 |
| `page_event` | `web.webInteraction.linkClicks.value` | number | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、離脱リンク、クリックされたカスタムリンク）。 |
| `page_event_var_1` | `web.webInteraction.URL` | string | リンクトラッキングイメージリクエストでのみ使用される変数。この変数には、クリックされたダウンロードリンク、離脱リンク、またはカスタムリンクの URL が含まれます。 |
| `page_event_var_2` | `web.webInteraction.name` | string | リンクトラッキングイメージリクエストでのみ使用される変数。このリストは、リンクのカスタム名をリスト表示します（指定されている場合）。 |
| `paid_search` | `search.isPaid` | ブール型 | ヒットが有料検索の検出に一致した場合に設定されるフラグ。 |
| `ref_type` | `web.webReferrertype` | string | ヒットのリファラルのタイプを表す数値 ID。 |

#### 列を投稿

Adobe Analytics データフィードでは、を持つ列という概念を使用します。 `post_` 処理後のデータを格納する列であるプレフィックス。 詳しくは、[データフィードに関する FAQ](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post) を参照してください。

Experience PlatformEdge Network（Web SDK、Mobile SDK、Server API）を使用してデータセットに収集されたデータには、次の概念はありません `post_` フィールド。 その結果、 `post_` プレフィックスが「and」 *non*-`post_` プレフィックスが付いたデータフィード列は、同じ XDM フィールドにマッピングされます。 例：両方 `page_url` および `post_page_url` データフィード列が同じ列にマッピングされる `web.webPageDetails.URL` XDM フィールド。

参照： [Adobe AnalyticsとCustomer Journey Analytics間でのデータ処理の比較](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) ：データ処理の違いの概要

この `post_` ただし、Experience Platformデータレイクで収集されるデータのプレフィックス列タイプでは、データフィードのユースケースで使用する前に高度な変換が必要です。 クエリでこれらの高度な変換を実行するには、以下を使用します [Adobe定義関数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) セッション化、アトリビューション、重複排除の場合。 参照： [例](#examples) これらの関数の使用方法については、を参照してください。

#### 参照

他のデータセットからのデータを検索するには、標準の SQL 機能（`WHERE` 句、 `INNER JOIN`, `OUTER JOIN`、など）。

#### 計算

フィールド（列）に対して計算を実行するには、標準の SQL 関数を使用します（例： `COUNT(*)`）、または [数学および統計の演算子と関数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) spark SQL の一部です。 また、 [ウィンドウ関数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) 集計を更新し、順序付きサブセットの各行の単一の項目を返すサポートを提供します。 参照： [例](#examples) これらの関数の使用方法については、を参照してください。

#### ネストされたデータ構造

データセットのベースとなるスキーマには、多くの場合、ネストされたデータ構造など、複雑なデータタイプが含まれています。 前述の `identityMap` はネストされたデータ構造の例です。 次に例を示します `identityMap` データ。

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

を使用できます [`explode()` またはその他の配列関数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) spark SQL からネストされたデータ構造内のデータにアクセスする。例：

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

- [参照を中止](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [属性分析](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [ボットフィルタリング](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- とその他件 [クエリサービスガイドでサポートされているユースケース](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview).


### スケジュール クエリ

クエリをスケジュールして、クエリが実行され、結果が好みの間隔で生成されるようにします。

#### クエリエディターの使用

クエリエディターを使用してクエリをスケジュールできます。 クエリをスケジュールする場合は、出力データセットを定義します。 参照： [クエリスケジュール](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules) を参照してください。


#### Query Service API の使用

または、RESTful API を使用してクエリを定義し、クエリのスケジュールを設定することもできます。 を参照してください。 [Query Service API ガイド](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) を参照してください。
出力データセットをオプションのの一部として必ず定義してください `ctasParameters` クエリ作成時のプロパティ （[クエリの作成](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)）またはクエリのスケジュールを作成する場合（[スケジュール済みクエリの作成](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)）に設定します。



## データセットを書き出し

クエリを作成し、スケジュールを設定し、結果を確認したら、生のデータセットをクラウドストレージの宛先に書き出すことができます。 この書き出しは、データセット書き出し宛先と呼ばれるExperience Platformー宛先の用語で使用されます。 参照： [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) を参照してください。

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

出力データセットの書き出し先となるクラウドストレージの宛先を決定した場合、 [宛先を選択](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). 優先クラウドストレージの宛先をまだ設定していない場合は、次の操作を行う必要があります [新しい宛先接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

宛先の設定の一環として、次のことができます

- ファイルタイプ（JSON または Parquet）を定義します。
- 結果のファイルが圧縮されるかどうか、および
- マニフェストファイルを含めるかどうか。


#### データセットを選択

宛先を選択した場合、次の **[!UICONTROL データセットを選択]** 手順データセットのリストから出力データセットを選択する必要があります。 複数のスケジュールされたクエリを作成し、出力データセットを同じクラウドストレージ宛先に送信する場合、対応する出力データセットを選択できます。 参照： [データセットを選択](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) を参照してください。

#### データセット書き出しのスケジュール設定

最後に、の一部としてデータセットの書き出しをスケジュールします **[!UICONTROL スケジュール]** ステップ。 その手順では、スケジュールと、出力データセットの書き出しを増分にするかどうかを定義できます。 参照： [データセットの書き出しをスケジュール](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) を参照してください。


#### 最終手順

[レビュー](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) 選択した内容が正しければ、クラウドストレージの宛先への出力データセットの書き出しを開始します。

あなたは必要があります [検証](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) データの書き出しが成功した。 データセットを書き出す際に、Experience Platformが 1 つ以上のデータセットを作成する `.json` または `.parquet` 宛先で定義されたストレージの場所にあるファイル。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出しのたびに、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

### フローサービス API

または、API を使用して出力データセットの書き出しを書き出し、スケジュールすることもできます。 関連する手順は、に記載されています。 [Flow Service API を使用したデータセットの書き出し](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### 基本を学ぶ

データセットを書き出すには、次があることを確認します [必要な権限](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). また、出力データセットの送信先がデータセットの書き出しをサポートしていることを確認します。 次に、以下を行う必要があります [必須ヘッダーおよびオプションヘッダーの値の収集](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) api 呼び出しで使用する。 また、次の操作も必要です [宛先の接続仕様およびフロー仕様 ID の特定](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) データセットをに書き出そうとしています。

#### 適格なデータセットの取得

次のことができます [適格なデータセットのリストの取得](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) エクスポートの場合は、を使用して、出力データセットがそのリストに含まれているかどうかを確認します。 [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API です。


#### ソース接続を作成

次に、以下を行う必要があります [ソース接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) 出力データセットの一意の ID を使用して、クラウドストレージ宛先に書き出します。 を使用します [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API です。

#### 宛先に対する認証（ベース接続の作成）

次に、以下を行う必要があります [ベース接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) を使用して、資格情報を認証し、クラウドストレージの宛先に安全に保存するには [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API です。


#### エクスポートパラメーターの指定

次に、以下を行う必要があります [エクスポートパラメーターを格納する追加のターゲット接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) もう一度を使用する出力データセットの場合、 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API です。 これらの書き出しパラメーターには、場所、ファイル形式、圧縮などが含まれます。

#### データフローの設定

最後に、あなたは [データフローの設定](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) を使用して、出力データセットがクラウドストレージの宛先に確実に書き出されるようにするには、 [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API です。 この手順では、を使用して書き出しのスケジュールを定義できます `scheduleParams` パラメーター。

#### データフローの検証

終了 [データフローの正常な実行の確認](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)、を使用します [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API。データフロー ID をクエリパラメーターとして指定します。 このデータフロー ID は、データフローを設定したときに返される識別子です。

[検証](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) データの書き出しが成功した。 データセットを書き出す際に、Experience Platformが 1 つ以上のデータセットを作成する `.json` または `.parquet` 宛先で定義されたストレージの場所にあるファイル。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出しのたびに、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

## まとめ

つまり、Adobe Analytics データフィード機能のエミュレートは、クエリサービスを使用してスケジュール済みクエリを設定し、これらのクエリの結果をスケジュール済みデータセット書き出しで使用することを意味します。

>[!IMPORTANT]
>
>このユースケースには、2 つのスケジューラーが含まれています。 エミュレートされたデータフィード機能が適切に動作することを保証するには、クエリサービスとデータ書き出しで設定されたスケジュールが干渉しないようにしてください。
