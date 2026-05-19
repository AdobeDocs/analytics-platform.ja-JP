---
title: データウェアハウスネイティブソリューションの設定
description: Experience Platform Data Mirror Customer Journey Analytics向けのデータウェアハウスネイティブソリューションの設定方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
autotag-review: '2026-05-19T08:56:46.637Z'
TQID: 'https://experienceleague.adobe.com/A3GkkNVAO9qpbOqCrZnf6PNJfRuwMaodJVOOuSRg0w8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 0%

---

# データウェアハウスネイティブソリューションの設定

{{release-limited-testing}}

Customer Journey Analytics用Experience Platform Data Mirrorをサポートするには、サポートされている3つのデータウェアハウスネイティブソリューション（[[!DNL Azure Databricks]](#azure-databricks)、[[!DNL Google BigQuery]](#google-bigquery)、[[!DNL Snowflake]](#snowflake)）から使用するデータを変更データキャプチャ用に有効にする必要があります。


## [!DNL Azure Databricks]

[!DNL Azure Databricks] テーブルの&#x200B;**データフィードの変更**&#x200B;を有効にして、ソース接続で変更データキャプチャを使用します。

次のコマンドを使用して、テーブルのデータフィードの変更を有効にします。

**新しいテーブル**

変更データ フィードを新しいテーブルに適用するには、`CREATE TABLE` コマンドでテーブル プロパティ `delta.enableChangeDataFeed`を`TRUE`に設定する必要があります。

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**既存のテーブル**

既存のテーブルに変更データ フィードを適用するには、`ALTER TABLE` コマンドでテーブル プロパティ `delta.enableChangeDataFeed`を`TRUE`に設定する必要があります。

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**すべての新しいテーブル**

すべての新しいテーブルに変更データ フィードを適用するには、既定のプロパティを`TRUE`に設定する必要があります。

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

詳しくは、変更データフィードの有効化に関する[[!DNL Azure Databricks]  ガイド &#x200B;](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed)を参照してください。

[!DNL Azure Databricks] ソース接続の変更データキャプチャを有効にする手順については、次のドキュメントを参照してください。

* [&#x200B; ベース接続 [!DNL Azure Databricks] を作成](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks)。
* [&#x200B; データベース &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)のソース接続を作成します。

## [!DNL Google BigQuery]

[!DNL Google BigQuery] ソース接続で変更データキャプチャを使用するには、[!DNL Google Cloud] コンソールの[!DNL Google BigQuery] ページに移動し、`enable_change_history`を`TRUE`に設定します。 このプロパティは、データテーブルの変更履歴を有効にします。

詳しくは、 [!DNL GoogleSQL][&#128279;](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list)の データ定義言語ステートメントに関するガイドを参照してください。

[!DNL Google BigQuery] ソース接続の変更データキャプチャを有効にする手順については、次のドキュメントを参照してください。

* [&#x200B; ベース接続 [!DNL Google BigQuery] を作成](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery)。
* [&#x200B; データベース &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)のソース接続を作成します。

## [!DNL Snowflake]

[!DNL Snowflake] テーブルの&#x200B;**変更トラッキング**&#x200B;を有効にして、ソース接続で変更データキャプチャを使用します。

[!DNL Snowflake]で、`ALTER TABLE`を使用して`CHANGE_TRACKING`を`TRUE`に設定し、変更追跡を有効にします。

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

詳細については、[[!DNL Snowflake] 変更条項の使用に関するガイド &#x200B;](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes)を参照してください。

[!DNL Snowflake] ソース接続の変更データキャプチャを有効にする手順については、次のドキュメントを参照してください。

* [&#x200B; ベース接続 [!DNL Snowflake] を作成](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake)。
* [&#x200B; データベース &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)のソース接続を作成します。


>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：リレーショナルデータのミラーと使用](relational.md)
>
