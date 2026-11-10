---
title: Customer Journey Analytics データフィードからのParquet ファイルの使用
description: Customer Journey Analytics データフィードがParquet ファイルを提供する理由、ParquetとCSV、TSV、およびJSONの比較、およびファイルのクエリまたは読み込み方法について説明します。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: f77f416ad958b28a8489d7a6eb13100ba699236e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%
---
# データフィードでのParquet ファイルの操作

{{release-limited-testing}}

Customer Journey Analytics データフィードは、Parquet形式でファイルを配信します。 最新のほとんどのデータウェアハウスでは、Parquet ファイルを直接読み取ることができるため、通常、使用する前にファイルを変換する必要はありません。

次の情報を使用して、データフィードでParquetを使用する理由、Parquetと他のファイル形式の比較、データウェアハウスでParquet ファイルをクエリまたは読み込む方法を理解します。

## データフィードにParquetを使用する利点

Parquetは、次の理由により、CSV、TSV、JSONよりもデータフィード出力に適しています。

* **幅の広いフィード**: データフィードには数百の列を含めることができます。 Parquetを使用すると、クエリは必要な列のみを読み取ることができます。

* **ネストされたフィールド**: Parquetは、製品リストなどのネストされたフィールドをネイティブで表します。 CSVとTSVは、それらを文字列にエンコードすることによってのみ、それらを表すことができます。 詳しくは、「[&#x200B; データフィードのサブイベントコンポーネント &#x200B;](/help/components/exports/cja-data-feeds/df-sub-event.md)」を参照してください。

* **ビルトインスキーマ**：各Parquet ファイルには、列名、データタイプ、ネストされた構造など、独自のスキーマが格納されます。 スキーマはファイル内にあるので、データウェアハウスはファイルから直接テーブルを作成できます。 ヘッダーファイルやスキーマ定義を別途指定する必要はなく、データウェアハウスがデータ型を推測する必要もありません。

* **大量の書き出し**: Parquetは通常、保管および転送コストを削減します。 また、データを読み込む際のテキスト解析も回避します。

## ParquetとCSV、TSV、JSONの比較

CSV、TSV、およびJSONは、一般的なテキストベースのファイル形式です。

* **CSVおよびTSV**: データの各行はプレーンテキストの行で、値はコンマ （CSV）またはタブ （TSV）で区切られます。 Adobe AnalyticsのデータフィードはTSV ファイルを配信します。 Customer Journey AnalyticsとAdobe Analyticsのデータフィードのその他の違いについては、[Adobe AnalyticsとCustomer Journey Analyticsのデータフィードの比較](/help/components/exports/cja-data-feeds/df-comparison.md)を参照してください。

* **JSON**：各レコードは、名前付きフィールドを含むテキストとして保存され、ネストされた配列とオブジェクトを含めることができます。

次の表は、Parquet、CSV、TSV、およびJSONの違いを示しています。

| 特性 | PARQUET | CSVまたはTSV | JSON |
| --- | --- | --- | --- |
| **クエリの速度** | スピード。 クエリは、必要な列のみを読み取ります。 | 遅い。 行全体を読み取って解析する必要があります。 | 遅い。 行全体を読み取って解析する必要があります。 |
| **データタイプ** | タイプ済み： スキーマはファイルに埋め込まれています。 | 未入力： すべての値はテキストであり、データを読み込むときに型が推測されます。 | 緩く入力された。 |
| **ネストされたデータ** | 配列とオブジェクトはネイティブでサポートされています。 | サポートされていません。 配列とオブジェクトは、フラット化するか、文字列としてエンコードする必要があります。 | 配列とオブジェクトはネイティブでサポートされています。 |
| **読みやすさ** | データウェアハウス、DuckDB、Pythonなどのツールが必要です。 | テキストエディターまたはスプレッドシートで開きます。 | テキストエディターで開きます。 |

## Parquet ファイルのクエリまたは読み込み

データフィードファイルは、[&#x200B; データフィードを作成したときに選択したクラウドストレージの場所](/help/components/exports/cja-data-feeds/create-feed.md)にParquet形式で配信されます。

通常、ファイルをダウンロードするのではなく、データウェアハウスをストレージの場所に接続します。 その後、次のいずれかの方法でParquet ファイルを使用できます。

### 配置されたファイルのクエリ

クラウドストレージ内のファイルを指す外部テーブルを定義します。 クエリを実行すると、データウェアハウスはファイルを読み取ります。

* **Snowflake**：外部ステージに対する外部テーブルまたはクエリ
* **Databricks**: Amazon S3、Azure Data Lake Storage （ADLS）、またはGoogle Cloud Storage上の外部テーブル
* **BigQuery**: Google Cloud Storage上の外部テーブル
* **Amazon Redshift**: Amazon S3上のRedshift Spectrum

### ファイルを管理テーブルにロードする

ファイルを管理テーブルに読み込むことは、繰り返しワークロードの一般的な選択肢です。 次に例を示します。

* **Snowflake**: `COPY INTO`
* **BigQuery**: ジョブの読み込み
* **Databricks**: `COPY INTO`または自動ローダー

## Parquet データをCSVまたはJSONに変換

下流プロセスでCSVまたはJSON ファイルが必要な場合、ほとんどのデータウェアハウスおよびツールは、読み込み後にParquet データをいずれかの形式に書き出すことができます。 例えば、Snowflakeでは、クエリの結果を`COPY INTO`を含むCSVまたはJSONとしてアンロードできます。
