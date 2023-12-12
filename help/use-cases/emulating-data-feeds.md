---
title: データフィード機能のエミュレート
description: Experience Platformでデータを使用してAdobe Analyticsデータフィードをエミュレートする方法を説明します。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: a4d9272b1e813a34f11e4b42c3369129b57c6ef0
workflow-type: tm+mt
source-wordcount: '2107'
ht-degree: 4%

---

# データフィード機能のエミュレート

Adobe Analyticsのデータフィードは、Adobe Analyticsから生データを取得するための強力な方法です。 この使用例では、Experience Platformから類似したタイプの生データを取得し、Adobe以外の他のプラットフォームおよび組織の裁量で使用する方法を説明します。

## 前提条件

この使用例で説明する機能を使用する前に、次の要件をすべて満たしていることを確認してください。

* オンラインとオフラインのデータをExperience Platformのデータレイクに送信する実装。
* プラットフォームベースのアプリケーションまたは Data Distillerアドオンの一部としてパッケージ化されたクエリサービスへのアクセス。 詳しくは、 [クエリサービスのパッケージ化](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) を参照してください。
* データセットのエクスポート機能へのアクセス。Real-Time CDP Prime または Ultimate パッケージ、Adobe Journey Optimizer、またはCustomer Journey Analyticsを購入したお客様が利用できます。 詳しくは、 [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja) を参照してください。
* データフィードの生データを書き出すために設定された、1 つ以上の宛先 ( 例：Amazon S3、Google Cloud Storage)。

## はじめに

Adobe Analyticsデータフィードのエミュレートには、次のものが含まれます。

* 定義 **スケジュール済みクエリ** を使用して、データフィードのデータを出力データセットとして生成します。 **クエリサービス**.
* 定義 **スケジュール済みのデータセットの書き出し** を使用して出力データセットをクラウドストレージの宛先に書き出す **データセットの書き出し**.


![データフィード](assets/data-feed.svg)


## クエリサービス

Experience Platformクエリサービスを使用すると、Experience Platformデータレイク内の任意のデータセットを、データベーステーブルと同じようにクエリして結合できます。 その後、結果を新しいデータセットとして取り込み、レポートでさらに使用したり、書き出したりできます。

クエリサービスを使用する [ユーザーインターフェイス](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [PostgresSQL プロトコルを使用して接続されたクライアント](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=ja)または [RESTful API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) ：データフィードのデータを収集するクエリを作成し、スケジュールを設定します。

### クエリを作成

SELECT 文およびその他の制限付きコマンドに対して、標準 ANSI SQL のすべての機能を使用して、データフィードのデータを生成するクエリを作成および実行できます。 詳しくは、 [SQL 構文](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) を参照してください。 この SQL 構文以外で、Adobeは次の機能をサポートします。

* 事前定義済み [Adobe定義関数 (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) Experience Platformデータレイクに保存されたイベントデータに関する一般的なビジネス関連タスクを実行するのに役立つ、次の機能を含む： [セッション化](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=ja) および [帰属](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=ja),
* 複数の組み込み [Spark SQL 関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [metadata PostgreSQL コマンド](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [準備済み文書](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### 例

データフィードのデータを収集するクエリの例を以下に示します。 以下の例では、 `demo_system_event_dataset_for_website_global_v1_1` を、顧客が web サイトとやり取りする際に収集したデータを含むサンプルエクスペリエンスイベントデータセットとして使用する。

+++トップ 5 の製品

*Web サイトで閲覧された上位 5 つの製品は何ですか。*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++製品インタラクションファネル

*Web サイト全体での様々な製品インタラクションは何ですか。*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++人々の行動

*セッションの 3 番目のページとして、「サービスのキャンセル」ページに到達する前に、人々はサイト上で何をしますか？*

このクエリでは、Adobe定義関数を使用 `SESS_TIMEOUT` および `NEXT`.

* `SESS_TIMEOUT()` は、Adobe Analytics で見つかった訪問のグループ化を再現します。時間ベースのグループ化と同様の動作を実行しますが、パラメーターはカスタマイズ可能です。
* `NEXT()` および `PREVIOUS()` は、顧客がサイトをどのように移動したかを理解するのに役立ちます。

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++時間

*「サービスのキャンセル」ページにアクセスした後、訪問者がコールセンターに電話をかけるまでにどのくらいの時間がありますか。*

この種のクエリに回答するには、 `TIME_BETWEEN_NEXT_MATCH()` Adobe定義関数。 前の一致と次の一致の間の時間関数は、特定のインシデントから経過した時間を測定する新しいディメンションを提供します。

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++結果は何ですか？

*コールセンターに電話をかけるお客様の結果は何ですか。*

このクエリの場合、 `demo_system_event_dataset_for_website_global_v1_1` データセットが例と結合されている `demo_system_event_dataset_for_call_center_global_v1_1` コールセンターのインタラクションを含むデータセット。

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++マーケティングチャネルのエンゲージメント (Adobe Analyticsデータ )

*イタリアに焦点を当てた Web トラフィックに対するマーケティングチャネル全体でのエンゲージメントはどのようなものですか？*

この例では、Adobe Analyticsソースコネクタによって自動的に作成されたデータセットを使用します。例えば、 `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

その他の（高度な）サンプルクエリについては、 [離脱した参照](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [アトリビューション分析](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [ボットフィルタリング](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)、 、および「クエリサービスガイド」のその他の例。


#### ID

Experience Platformでは、様々な ID を使用できます。 ID に対して正しくクエリを実行していることを確認します。 上記の例では、ECID は、コアオブジェクトの一部として定義されます。これ自体は識別オブジェクトの一部で、両方とも、エクスペリエンスイベントコアフィールドグループを使用してスキーマに追加されます ( 例： `_sampleorg.identification.core.ecid`) をクリックします。 ECID は、スキーマ内で別々に整理される場合があります。

または、 `identityMap` をクリックして id をクエリします。 このオブジェクトのタイプはです `Map` とは、 [ネストされたデータ構造](#nested-data-structure).

Adobe Analyticsソースコネクタを使用して取り込まれたデータの場合は、複数の ID を使用できる場合があります。 主な識別子は、ECID または AAID のどちらが存在するかによって異なります。 詳しくは、 [Adobe Analyticsデータのプライマリ識別子](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) および [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=ja) 詳細情報

#### データフィード列

クエリで使用できるフィールド（列）は、データセットの基となるスキーマ定義によって異なります。 データセットの基になるスキーマを理解していることを確認します。

例えば、 [クエリの例](#examples) あなたは問い合わせました *ページ名*.

* Adobe Analyticsデータフィードの UI で、次のように選択します。 **[!UICONTROL pagename]** をデータフィード定義に追加する列として使用します。
* クエリサービスで、以下を含めます。 `web.webPageDetails.name` から `demo_system_event_dataset_for_website_global_v1_1` データセット ( **デモシステム — Web サイトのイベントスキーマ (Gobal v1.1)** エクスペリエンスイベントスキーマ ) をクエリに含める必要があります。 詳しくは、 [Web 詳細スキーマフィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) を参照してください。

エクスペリエンスイベントデータセットと基になるスキーマの以前のAdobe Analyticsデータ列と XDM フィールドのマッピングについて詳しくは、 [Analytics フィールドのマッピング](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ja) そして [Adobe Analytics ExperienceEvent Full Extension スキーマフィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) を参照してください。

さらに、Experience PlatformWeb SDK が（初期設定で）自動的に収集する情報は、クエリの列を識別するのにも関連する場合があります。 詳しくは、 [自動的に収集された情報](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) を参照してください。


#### 参照

他のデータセットからデータを検索するには、標準の SQL 機能（WHERE 句、INNER JOIN、OUTER JOIN など）を使用します。 詳しくは、 [結果は何ですか？](#examples) クエリを使用して、例を確認します。

#### 計算

フィールド（列）に対して計算を実行するには、標準の SQL 関数 ( 例： `COUNT(*)` （内） [製品インタラクションファネル](#examples) 例のクエリ ) または [数学および統計の演算子と関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) Spark SQL の一部。

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

以下を使用すると、 [`explode()` またはその他の配列関数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) Spark SQL から、ネストされたデータ構造内のデータに移動します。

次に例を示します。

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

または、ドット表記を使用して個々の要素を参照することもできます。 次に例を示します。

```sql
select identityMap,ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

詳しくは、[クエリサービスでのネストされたデータ構造の操作](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en)を参照してください。

### スケジュールクエリ

クエリをスケジュールして、クエリが実行され、結果が希望の間隔で生成されるようにします。 クエリのスケジュールを設定する際に、出力データセットを定義します。

#### クエリエディターの使用

クエリエディターを使用して、クエリをスケジュールできます。 クエリのスケジュールを定義する際に、出力データセットを定義できます。 詳しくは、 [クエリスケジュール](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) を参照してください。


#### クエリサービス API の使用

または、RESTful API を使用して、クエリを定義し、クエリのスケジュールを設定できます。 詳しくは、 [クエリサービス API ガイド](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) を参照してください。
オプションのの一部として出力データセットを必ず定義してください `ctasParameters` プロパティを使用してクエリを作成する ([クエリの作成](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) またはクエリのスケジュールを作成する際に ([スケジュール済みクエリの作成](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)) をクリックします。



## データセットの書き出し

クエリを作成し、スケジュールし、出力データセットの結果が要件に合っていることを確認したら、生のデータセットをクラウドストレージの宛先に書き出すことができます。 このエクスポートは、Experience Platformの宛先に関する用語で、データセットのエクスポート先と呼ばれます。 詳しくは、 [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja) 」を参照してください。

次のクラウドストレージの宛先がサポートされます。

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [Data Landing Zone](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google Cloud Storage](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### Experience PlatformUI

Experience PlatformUI を使用して、出力データセットの書き出しとスケジュール設定をおこなうことができます。 この節では、関連する手順について説明します。

#### 宛先を選択

出力データセットを書き出すクラウドストレージの宛先を決定した場合は、 [宛先を選択](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). 優先クラウドストレージの宛先をまだ設定していない場合は、次の手順を実行します。 [新しい宛先接続を作成する](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=ja).

宛先の設定の一環として、ファイルタイプ（JSON または Parquet）、結果のファイルを圧縮するかどうか、およびマニフェストファイルを含めるかどうかを定義できます。


#### データセットを選択

宛先を選択したら、次の **[!UICONTROL データセットを選択]** 手順では、データセットのリストから出力データセットを選択する必要があります。 複数のスケジュール済みクエリを作成し、出力データセットを同じクラウドストレージの宛先に送信する場合は、対応する出力データセットを選択できます。 詳しくは、 [データセットを選択](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) を参照してください。

#### データセット書き出しのスケジュール設定

最後に、 **[!UICONTROL スケジュール]** 手順 この手順では、スケジュールと、出力データセットのエクスポートを増分にするかどうかを定義できます。 詳しくは、 [データセットの書き出しをスケジュール](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) を参照してください。


#### 最終手順

[レビュー](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) 選択が完了し、正しい場合は、出力データセットのクラウドストレージの宛先への書き出しを開始します。

次の条件を満たす必要があります。 [確認](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) データのエクスポートが成功しました。 データセットを書き出す際、Experience Platformは 1 つ以上の `.json` または `.parquet` ファイルを格納します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に保存されることを想定します。 Experience Platformは、選択した宛先の一部として指定した格納場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出し時に、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

### フローサービス API

または、API を使用して、出力データセットの書き出しとスケジュールを設定することもできます。 関連する手順については、 [フローサービス API を使用したデータセットのエクスポート](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### 基本を学ぶ

次の条件を満たしていることを確認します。 [必要な権限](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) ：データセットと、出力データセットの送信先である宛先が、データセットの書き出しをサポートしている書き出し先。 次に、次の操作を行う必要があります。 [必須ヘッダーとオプションヘッダーの値の収集](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) API 呼び出しでを使用し、 [宛先の接続仕様 ID とフロー仕様 ID を特定します。](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) データセットをに書き出す予定です。

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

[検証](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) データのエクスポートが成功しました。 データセットを書き出す際、Experience Platformは 1 つ以上の `.json` または `.parquet` ファイルを格納します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に保存されることを想定します。 Experience Platformは、選択した宛先の一部として指定した格納場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出し時に、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

## まとめ

つまり、Adobe Analyticsデータフィード機能をエミュレートする場合、クエリサービスを使用してクエリをスケジュール設定し、その結果を使用してスケジュールされたデータセットの書き出しを実行します。

>[!IMPORTANT]
>
>この使用例には、2 つのスケジューラーが関与しています。 エミュレートされたデータフィード機能の適切な動作を保証するには、クエリサービスとデータのエクスポートで設定したスケジュールが干渉しないようにします。

