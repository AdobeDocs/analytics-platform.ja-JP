---
title: Experience Platformの設定
description: Experience Platform Data Mirror Customer Journey Analyticsのスキーマとデータセットを設定する方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
autotag-review: '2026-05-19T07:18:47.007Z'
TQID: 'https://experienceleague.adobe.com/nAfDMtaQvsVRAEm31fRwleirW8LaS-yS0tGTdReux0Y'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 604
ht-degree: 6%

---

# Experience Platformの設定

{{release-limited-testing}}

Experience Platform Data Mirror Customer Journey Analytics版では、複数のExperience Platform コンポーネントを適切に設定する必要があります。

* スキーマ
* データセット
* ソースコネクタ

これらの各コンポーネントを設定する際に考慮すべき詳細を以下に示します。

## スキーマ

ミラーリングするデータウェアハウスネイティブテーブルである[&#x200B; リレーショナルスキーマ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/relational){target="_blank"}を作成する必要があります。 リレーショナルスキーマを構築する場合は、次の要件が満たされていることを確認します。

* リレーショナルスキーマのタイプを求めるプロンプトが表示されたら、「手動」オプションを選択します。
* データのタイプに適したスキーマを選択します。 Experience Platform Data Mirrorは、主に時系列データ（イベントデータなど）に使用されますが、レコードベースのデータ（ルックアップやプロファイル）にも使用できます。

* スキーマのフィールドとその属性を定義します
* リレーショナルスキーマのフィールドに必要な属性を設定します。

   * **プライマリキー**。
   * **バージョン記述子**&#x200B;です。これは、連続番号（整数フィールドタイプ）またはDateTime フィールドタイプとして設定する必要があります。 DateTime フィールドタイプを使用する場合、バージョン記述子は、データの変更のタイムスタンプを定義します。例えば、最後に変更されたタイムスタンプを含むようにします。
   * **タイムスタンプ記述子** （時系列データ用）。イベントがキャプチャされた時点での不変タイムスタンプを定義します。 レコードベースのリレーショナルスキーマにタイムスタンプ記述子は必要ありません。



## データセット

スキーマのデータセットを事前に設定することも、ソースコネクタを設定するときにデータセットを作成することもできます。
事前にデータセットを作成するか、データセットを選択する場合は、先ほど作成したリレーショナル [&#x200B; スキーマ &#x200B;](#schema)をデータが使用していることを確認してください。


## ソースコネクタ

サポートされているデータウェアハウスネイティブソリューションにソースコネクタを設定するには、設定をガイドするソースワークフローを使用します。 そのワークフローは次の手順で構成されます。

### 認証

サポートされているデータウェアハウスネイティブソリューションに対する認証については、関連するExperience Platformのドキュメントを参照してください。

* [Azure Databricks](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/databases/snowflake)


### データを選択

データウェアハウスネイティブソリューションに正常に接続したら、データミラーに使用するデータウェアハウスネイティブソリューションからテーブルを選択します。 選択すると、データの内容のプレビューが表示されます。


### データフローの詳細

変更データキャプチャを有効にします。 変更データ取得の要件を説明する情報パネルが表示されます。

前に作成したリレーショナルスキーマに基づく新規または既存のデータセットを指定します。 データフローの詳細インターフェイスで他のオプションを指定して選択します。


### マッピング

データウェアハウスネイティブソリューションのテーブルのフィールドを、リレーショナルスキーマに指定したフィールドにマッピングします。


### スケジュール設定

データウェアハウスネイティブソリューションのテーブルのデータをExperience Platformのデータセットにミラーリングするスケジュールを定義します。


### レビュー

データミラーをサポートし、データキャプチャを変更するデータウェアハウスネイティブソリューションへのソースコネクタの設定を確認します。


ソースコネクタの設定が完了すると、データフローが作成されます。 その時点から、データウェアハウスネイティブソリューションでのデータの変更（挿入、更新、削除）は、指定されたデータセットに反映されます。


>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：リレーショナルデータのミラーと使用](relational.md)
>[Data Mirror （Experience Platform ドキュメント）](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/data-mirror/overview)
>[リレーショナルスキーマ （Experience Platform ドキュメント） &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/relational)
