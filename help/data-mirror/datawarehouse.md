---
title: Data Warehouse ネイティブソリューションの設定
description: Customer Journey Analytics用のExperience Platform Data Mirrorの Data Warehouse ネイティブソリューションを設定する方法を理解します
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Data Warehouse ネイティブソリューションの設定

{{release-limited-testing}}

Customer Journey AnalyticsのExperience Platform Data Mirrorをサポートするには、3 つのサポートされている Data Warehouse ネイティブソリューション（[[!DNL Azure Databricks]](#azure-databricks)、[[!DNL Google BigQuery]](#google-bigquery)、[[!DNL Snowflake]](#snowflake)）の使用するデータで change data capture を有効化する必要があります。


## [!DNL Azure Databricks]

ソース接続で変更データキャプチャを使用するには、**テーブルで** 変更データフィード [!DNL Azure Databricks] を有効にします。

以下のコマンドを使用して、テーブルで変更データフィードを有効にします。

**新規テーブル**

変更データフィードを新しいテーブルに適用するには、`delta.enableChangeDataFeed` コマンドでテーブルプロパティ `TRUE` を `CREATE TABLE` に設定する必要があります。

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**既存のテーブル**

変更データフィードを既存のテーブルに適用するには、`delta.enableChangeDataFeed` コマンドでテーブルプロパティ `TRUE` を `ALTER TABLE` に設定する必要があります。

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**すべての新規テーブル**

すべての新規テーブルに変更データフィードを適用するには、デフォルトのプロパティを `TRUE` に設定する必要があります。

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

詳しくは、[[!DNL Azure Databricks]  変更データフィードの有効化に関するガイド &#x200B;](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed) を参照してください。

[!DNL Azure Databricks] ソース接続の change data capture を有効にする手順については、次のドキュメントを参照してください。

* [&#x200B; ベース接続  [!DNL Azure Databricks]  作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks)。
* [&#x200B; データベースのソース接続の作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)。

## [!DNL Google BigQuery]

[!DNL Google BigQuery] ソース接続で Change Data Capture を使用するには、[!DNL Google BigQuery] コンソールの [!DNL Google Cloud] ページに移動し、`enable_change_history` を `TRUE` に設定します。 このプロパティは、データ テーブルの変更履歴を有効にします。

詳しくは、[&#x200B; のデータ定義言語ステートメント  [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list) に関するガイドを参照してください。

[!DNL Google BigQuery] ソース接続の change data capture を有効にする手順については、次のドキュメントを参照してください。

* [&#x200B; ベース接続  [!DNL Google BigQuery]  作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery)。
* [&#x200B; データベースのソース接続の作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)。

## [!DNL Snowflake]

**テーブルで** 変更の追跡 [!DNL Snowflake] を有効にして、ソース接続で変更データ キャプチャを使用します。

[!DNL Snowflake] では、`ALTER TABLE` を使用し、`CHANGE_TRACKING` を `TRUE` に設定して、変更の追跡を有効にします。

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

詳しくは、[[!DNL Snowflake] changes 句の使用に関するガイド &#x200B;](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes) を参照してください。

[!DNL Snowflake] ソース接続の change data capture を有効にする手順については、次のドキュメントを参照してください。

* [&#x200B; ベース接続  [!DNL Snowflake]  作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake)。
* [&#x200B; データベースのソース接続の作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)。


>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：モデルベースのデータをミラーリングして使用する &#x200B;](model-based.md)
>
