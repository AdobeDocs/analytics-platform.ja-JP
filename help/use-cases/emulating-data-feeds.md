---
title: データフィード機能のエミュレート
description: Experience Platformでデータを使用してAdobe Analyticsデータフィードをエミュレートする方法を説明します。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
role: Admin
exl-id: 71dd9e4e-1d71-424b-b984-492a3e39af5f
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '2402'
ht-degree: 10%

---

# データフィード機能のエミュレート

Adobe Analyticsのデータフィードは、Adobe Analyticsから生データを取得するための強力な方法です。 この使用例では、Experience Platformから類似したタイプの生データを取得する方法を説明します。これにより、他のプラットフォーム、Adobe以外のツール、組織の裁量でデータを使用できます。

## はじめに

Adobe Analyticsデータフィードのエミュレートには、次のものが含まれます。

* 定義 **スケジュール済みクエリ** データフィードのデータを出力データセットとして生成する ![出力データセット](assets/output-dataset.svg)，次を使用 **クエリサービス**.
* 定義 **スケジュール済みのデータセットの書き出し** を使用して出力データセットをクラウドストレージの宛先に書き出す **データセットの書き出し**.

![データフィード](assets/data-feed.svg)


## 前提条件

この使用例で説明する機能を使用する前に、次の要件をすべて満たしていることを確認してください。

* データをデータレイクに収集するExperience Platform実装。
* Data Distillerアドオンにアクセスして、バッチクエリを実行する権利をユーザーに付与する。 詳しくは、 [クエリサービスのパッケージ化](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html) を参照してください。
* データセットの書き出し機能へのアクセス (Real-Time CDP Prime、Ultimate パッケージ、Adobe Journey Optimizer、Customer Journey Analyticsの購入時に使用可能 )。 詳しくは、 [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja) を参照してください。
* データフィードの生データを書き出すために設定された、1 つ以上の宛先 ( 例：Amazon S3、Google Cloud Storage)。


## クエリサービス

Experience Platformクエリサービスを使用すると、データベーステーブルであるかのように、Experience Platformデータレイク内の任意のデータセットをクエリして結合できます。 その後、結果を新しいデータセットとして取り込み、レポートでさらに使用したり、書き出したりできます。

クエリサービスを使用する [ユーザーインターフェイス](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=ja), a [PostgresQL プロトコルを使用して接続されたクライアント](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html)または [RESTful API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=ja) ：データフィードのデータを収集するクエリを作成し、スケジュールを設定します。

### クエリを作成

SELECT 文およびその他の制限付きコマンドに対して、標準 ANSI SQL のすべての機能を使用して、データフィードのデータを生成するクエリを作成および実行できます。 詳しくは、 [SQL 構文](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html) を参照してください。 この SQL 構文以外で、Adobeは次の機能をサポートします。

* 事前定義済み [Adobe定義関数 (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html) Experience Platformデータレイクに保存されたイベントデータに関する一般的なビジネス関連タスクを実行するのに役立つ、次の機能を含む： [セッション化](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html) および [帰属](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=ja),
* 複数の組み込み [Spark SQL 関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html),
* [metadata PostgreSQL コマンド](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html),
* [準備済み文書](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html).

#### データフィード列

クエリで使用できる XDM フィールドは、データセットの基となるスキーマ定義に応じて異なります。 データセットの基になるスキーマを理解していることを確認します。 詳しくは、 [データセット UI ガイド](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja) を参照してください。

データフィード列と XDM フィールド間のマッピングを定義する方法については、 [Analytics フィールドマッピング](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ja). 関連トピック [スキーマ UI の概要](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html#defining-xdm-fields) XDM リソース（スキーマ、クラス、フィールドグループ、データ型など）の管理方法について詳しくは、こちらを参照してください。

例えば、 *ページ名* をデータフィードの一部として使用する場合：

* Adobe Analyticsデータフィードの UI で、次のように選択します。 **[!UICONTROL pagename]** をデータフィード定義に追加する列として使用します。
* クエリサービスで、以下を含めます。 `web.webPageDetails.name` から `sample_event_dataset_for_website_global_v1_1` データセット ( **Web サイト用のサンプルイベントスキーマ (Global v1.1)** エクスペリエンスイベントスキーマ ) をクエリに含める必要があります。 詳しくは、 [Web 詳細スキーマフィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html) を参照してください。

<!--
To understand the mapping between Adobe Analytics data feed columns and XDM fields in your experience event dataset and underlying schema, see [Analytics fields mapping](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html) and [Adobe Analytics ExperienceEvent Full Extension schema field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html) for more information.

Furthermore, the [automatically collected information by the Experience Platform Web SDK (out of the box)](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) might be relevant to identify columns for your query.
-->

#### ID

Experience Platformでは、様々な ID を使用できます。 クエリを作成する場合は、ID に対して正しくクエリを実行していることを確認します。


多くの場合、ID は別のフィールドグループで見つかります。 実装 ECID(`ecid`) は、 `core` それ自体が一部であるオブジェクト `identification` オブジェクト ( 例： `_sampleorg.identification.core.ecid`) をクリックします。 ECID は、スキーマ内で別々に整理される場合があります。

または、 `identityMap` をクリックして id をクエリします。 このオブジェクトのタイプはです `Map` とは、 [ネストされたデータ構造](#nested-data-structure).

詳しくは、 [UI での ID フィールドの定義](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html) 「Experience Platform」で id フィールドを定義する方法の詳細については、を参照してください。

参照： [Analytics データのプライマリ識別子](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html#primary-identifiers-in-analytics-data) を参照してください。 これは、Analytics ソースコネクタを使用していない場合でも、ID の設定に関するガイダンスとして機能する場合があります。


#### ヒットレベルのデータと識別

実装に基づいて、従来Adobe Analyticsで収集されていたヒットレベルのデータは、タイムスタンプ付きのイベントデータとしてExperience Platformに保存されるようになりました。 次の表は、 [Analytics フィールドマッピング](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html#generated-mapping-fields) およびでは、ヒットレベル固有のAdobe Analyticsデータフィード列を、クエリ内の対応する XDM フィールドにマッピングする方法の例を示します。 また、この表は、XDM フィールドを使用してヒット、訪問および訪問者を識別する方法の例も示しています。

| データフィード列 | XDM フィールド | タイプ | 説明 |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | string | ヒットを識別する一意の ID。 |
| `hitid_low` | `_id` | string | と共に使用 `hitid_high` ヒットを一意に識別する。 |
| `hitid_high` | `_id` | string | と共に使用 `hitid_high` ヒットを一意に識別する。 |
| `hit_time_gmt` | `receivedTimestamp` | string | ヒットのタイムスタンプ (UNIX®時間 )。 |
| `cust_hit_time_gmt` | `timestamp` | string | タイムスタンプが有効なデータセットでのみ使用されます。UNIX®時間に基づいて、ヒットと共に送信されるタイムスタンプです。 |
| `visid_high` + `visid_low` | `identityMap` | オブジェクト | 訪問の一意の ID。 |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | string | 訪問の一意の ID。 |
| `visid_high` | `endUserIDs._experience.aaid.primary` | ブール型 | と共に使用 `visid_low` を使用して、訪問を一意に識別します。 |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | string | と共に使用 `visid_low` を使用して、訪問を一意に識別します。 |
| `visid_low` | `identityMap` | オブジェクト | と共に使用 `visid_high` を使用して、訪問を一意に識別します。 |
| `cust_visid` | `identityMap` | オブジェクト | 顧客訪問者 ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | オブジェクト | 顧客訪問者 ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | ブール型 | 顧客訪問者 ID 名前空間コード。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | string | と共に使用 `visid_low` を使用して、顧客訪問者 id を一意に識別します。 |
| `geo\_*` | `placeContext.geo.* ` | 文字列、数値 | 国、地域、市区町村などの位置情報データ |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | string | 標準コマースおよびカスタムイベントがヒット時にトリガーされました。 |
| `page_event` | `web.webInteraction.type` | string | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、離脱リンク、クリックされたカスタムリンク）。 |
| `page_event` | `web.webInteraction.linkClicks.value` | number | イメージリクエストで送信されるヒットのタイプ（標準的なヒット、ダウンロードリンク、離脱リンク、クリックされたカスタムリンク）。 |
| `page_event_var_1` | `web.webInteraction.URL` | string | リンクトラッキングイメージリクエストでのみ使用される変数。この変数には、クリックされたダウンロードリンク、離脱リンク、またはカスタムリンクの URL が含まれます。 |
| `page_event_var_2` | `web.webInteraction.name` | string | リンクトラッキングイメージリクエストでのみ使用される変数。このリストは、リンクのカスタム名をリスト表示します（指定されている場合）。 |
| `paid_search` | `search.isPaid` | ブール型 | ヒットが有料検索の検出に一致した場合に設定されるフラグ。 |
| `ref_type` | `web.webReferrertype` | string | ヒットのリファラルのタイプを表す数値 ID。 |

#### POST 列

Adobe Analyticsデータフィードは、列の概念を使用し、 `post_` プレフィックス。処理後のデータを含む列です。 詳しくは、[データフィードに関する FAQ](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html#post) を参照してください。

Experience PlatformEdge Network（Web SDK、モバイル SDK、Server API）を使用してデータセットで収集されたデータには、 `post_` フィールド。 その結果、 `post_` 先頭に *non*-`post_` プレフィックスが付いたデータフィード列は、同じ XDM フィールドにマッピングされます。 例えば、 `page_url` および `post_page_url` データフィード列を同じにマッピングする `web.webPageDetails.URL` XDM フィールド。

詳しくは、 [Adobe AnalyticsとCustomer Journey Analyticsでのデータ処理の比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html) ：データの処理の違いの概要。

The `post_` プレフィックス列タイプのデータをExperience Platformデータレイクで収集する場合、データフィードの使用例で使用する前に、高度な変換が必要になります。 クエリでこれらの高度な変換を実行するには、 [Adobe定義関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html) セッション化、アトリビューションおよび重複排除の場合。 詳しくは、 [例](#examples) これらの関数の使用方法に関する説明。

#### 参照

他のデータセットからデータを検索するには、標準の SQL 機能 (`WHERE` 条項 `INNER JOIN`, `OUTER JOIN`、など )。

#### 計算

フィールド（列）に対して計算を実行するには、標準の SQL 関数 ( 例： `COUNT(*)`)、または [数学および統計の演算子と関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html#math) Spark SQL の一部。 また、 [窓関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html#window-functions) は、集計を更新し、順序付けされたサブセットの各行に対して単一の項目を返す機能を提供します。 詳しくは、 [例](#examples) これらの関数の使用方法に関する説明。

#### ネストされたデータ構造

データセットのベースとなるスキーマには、多くの場合、ネストされたデータ構造を含む複雑なデータタイプが含まれています。 前述 `identityMap` は、ネストされたデータ構造の一例です。 以下に、 `identityMap` データ。

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

以下を使用すると、 [`explode()` またはその他の配列関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html#arrays) Spark SQL からネストされたデータ構造内のデータに移動します。次に例を示します。

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

または、ドット表記を使用して個々の要素を参照することもできます。 次に例を示します。

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

詳しくは、[クエリサービスでのネストされたデータ構造の操作](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html)を参照してください。


#### 例

Experience Platformデータレイクのデータセットのデータを使用するクエリで、は、Adobe定義関数や Spark SQL の追加機能をタップし、同等のAdobe Analyticsデータフィードと同様の結果を提供するクエリについては、

* [離脱した参照](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html)
* [アトリビューション分析](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html)
* [ボットフィルタリング](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html)
* およびクエリサービスガイドのその他の使用例を参照してください。


### スケジュールクエリ

クエリをスケジュールして、クエリが実行され、結果が希望の間隔で生成されるようにします。

#### クエリエディターの使用

クエリエディターを使用して、クエリをスケジュールできます。 クエリのスケジュールを設定する際に、出力データセットを定義します。 詳しくは、 [クエリスケジュール](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html) を参照してください。


#### クエリサービス API の使用

または、RESTful API を使用して、クエリを定義し、クエリのスケジュールを設定できます。 詳しくは、 [クエリサービス API ガイド](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=ja) を参照してください。
オプションのの一部として出力データセットを必ず定義してください `ctasParameters` プロパティを使用してクエリを作成する ([クエリの作成](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) またはクエリのスケジュールを作成する際に ([スケジュール済みクエリの作成](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)) をクリックします。



## データセットの書き出し

クエリを作成し、スケジュールし、出力データセットの結果が要件に合っていることを確認したら、生のデータセットをクラウドストレージの宛先に書き出すことができます。 このエクスポートは、Experience Platformの宛先に関する用語で、データセットのエクスポート先と呼ばれます。 詳しくは、 [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja) 」を参照してください。

次のクラウドストレージの宛先がサポートされます。

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=ja)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=ja)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=ja)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html#changelog)


### Experience PlatformUI

Experience PlatformUI を使用して、出力データセットの書き出しとスケジュール設定をおこなうことができます。 この節では、関連する手順について説明します。

#### 宛先を選択

出力データセットを書き出すクラウドストレージの宛先を決定した場合は、 [宛先を選択](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#select-destination). 優先クラウドストレージの宛先をまだ設定していない場合は、次の手順を実行します。 [新しい宛先接続を作成する](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=ja).

宛先の設定の一環として、ファイルタイプ（JSON または Parquet）、結果のファイルを圧縮するかどうか、およびマニフェストファイルを含めるかどうかを定義できます。


#### データセットを選択

宛先を選択したら、次の **[!UICONTROL データセットを選択]** 手順では、データセットのリストから出力データセットを選択する必要があります。 複数のスケジュール済みクエリを作成し、出力データセットを同じクラウドストレージの宛先に送信する場合は、対応する出力データセットを選択できます。 詳しくは、 [データセットを選択](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#select-datasets) を参照してください。

#### データセット書き出しのスケジュール設定

最後に、 **[!UICONTROL スケジュール]** 手順 この手順では、スケジュールと、出力データセットのエクスポートを増分にするかどうかを定義できます。 詳しくは、 [データセットの書き出しをスケジュール](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#scheduling) を参照してください。


#### 最終手順

[レビュー](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#review) 選択が完了し、正しい場合は、出力データセットのクラウドストレージの宛先への書き出しを開始します。

次の条件を満たす必要があります。 [確認](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja#verify) データのエクスポートが成功しました。 データセットを書き出す際、Experience Platformは 1 つ以上の `.json` または `.parquet` ファイルを格納します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に保存されることを想定します。 Experience Platformは、選択した宛先の一部として指定した格納場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出し時に、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

### フローサービス API

または、API を使用して、出力データセットの書き出しとスケジュールを設定することもできます。 関連する手順については、 [フローサービス API を使用したデータセットのエクスポート](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### 基本を学ぶ

データセットを書き出すには、 [必要な権限](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions). また、出力データセットの送信先が、データセットの書き出しをサポートしていることを確認します。 次に、次の操作を行う必要があります。 [必須ヘッダーとオプションヘッダーの値の収集](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) API 呼び出しで使用する また、 [宛先の接続仕様 ID とフロー仕様 ID を特定します。](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) データセットをに書き出す予定です。

#### 適格なデータセットの取得

以下が可能です。 [適格なデータセットのリストの取得](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) エクスポートの場合は、出力データセットがそのリストに含まれているかどうかを、 [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### ソース接続を作成

次に、 [ソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) クラウドストレージの宛先に書き出す一意の ID を使用して、出力データセットのデータを取得します。 次を使用します。 [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### 宛先に対する認証（ベース接続を作成）

次の手順に従います。 [基本接続を作成する](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) を使用して、資格情報を適切に認証し、クラウドストレージの宛先に安全に保存するには、次の手順を実行します。 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### 書き出しパラメーターの指定

次に、 [書き出しパラメーターを格納する追加のターゲット接続を作成する](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) を使用して出力データセットに対し、再度 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. これらの書き出しパラメータには、場所、ファイルフォーマット、圧縮などが含まれます。

#### データフローの設定

最後に、 [データフローの設定](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) を使用して出力データセットをクラウドストレージの宛先に確実に書き出すには、次の手順を実行します。 [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. この手順では、 `scheduleParams` パラメーター。

#### データフローを検証

宛先 [データフローの実行が成功したかどうかを確認します。](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs)を使用する場合は、 [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API（クエリパラメーターとしてデータフロー ID を指定） このデータフロー ID は、データフローを設定する際に返される識別子です。

[検証](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja#verify) データのエクスポートが成功しました。 データセットを書き出す際、Experience Platformは 1 つ以上の `.json` または `.parquet` ファイルを格納します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に保存されることを想定します。 Experience Platformは、選択した宛先の一部として指定した格納場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出し時に、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

## まとめ

つまり、Adobe Analyticsデータフィード機能をエミュレートする場合、クエリサービスを使用してクエリをスケジュール設定し、その結果を使用してスケジュールされたデータセットの書き出しを実行します。

>[!IMPORTANT]
>
>この使用例には、2 つのスケジューラーが関与しています。 エミュレートされたデータフィード機能の適切な動作を保証するには、クエリサービスとデータのエクスポートで設定したスケジュールが干渉しないようにします。
