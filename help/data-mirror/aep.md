---
title: Experience Platformの設定
description: Customer Journey Analytics用Experience Platform Data Mirrorのスキーマおよびデータセットを設定する方法について
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: cd3baec708f1811a7cbc37dfe0a9c3af75eb97c3
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 3%

---

# Experience Platformの設定

{{release-limited-testing}}

Customer Journey Analytics用のExperience Platform Data Mirrorには、次のいくつかのExperience Platform コンポーネントの適切な設定が必要です。

* スキーマ
* データセット
* ソースコネクタ

これらの各コンポーネントを設定する際に考慮すべき詳細を以下に示します。

## スキーマ

ミラー化するデータウェアハウスネイティブテーブルである [ リレーショナルスキーマ ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/relational){target="_blank"} を作成する必要があります。 リレーショナルスキーマを構築する場合は、次の要件が満たされていることを確認します。

* リレーショナルスキーマのタイプを要求するプロンプトが表示されたら、必ず手動オプションを選択します。
* データのタイプに適したスキーマを選択します。 Experience Platform Data Mirrorは、ほとんどが時系列データ（イベントデータなど）に使用されますが、レコードベース（参照およびプロファイル）のデータにも使用できます。

* スキーマ内のフィールドとその属性を定義します
* リレーショナルスキーマ内のフィールドに必要な属性を設定します。

   * **プライマリキー**。
   * **バージョン記述子**：連番（整数フィールドタイプ）または日時フィールドタイプとして設定する必要があります。 DateTime フィールドタイプを使用する場合、バージョン記述子はデータの変更のタイムスタンプを定義します（例：最終変更日のタイムスタンプを含める場合）。
   * **タイムスタンプ記述子** （時系列データの場合）。イベントが取得された時点での不変タイムスタンプを定義します。 タイムスタンプ記述子は、レコードベースのリレーショナルスキーマには必要ありません。



## データセット

事前にスキーマのデータセットを設定することも、ソースコネクタを設定する際にデータセットを作成することもできます。
事前にデータセットを作成したりデータセットを選択したりする場合は、以前に作成したリレーショナル [ スキーマ ](#schema) をデータで使用していることを確認します。


## ソースコネクタ

サポートされている Data Warehouse ネイティブソリューションに対してソースコネクタを設定するには、設定の手順を示すソースワークフローを使用します。 このワークフローは、次のステップで構成されます。

### 認証

サポートされている Data Warehouse ネイティブソリューションに対する認証については、関連するExperience Platform ドキュメントを参照してください。

* [Azure Databricks](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


### データを選択

データウェアハウスネイティブソリューションに正常に接続したら、データミラーに使用するデータウェアハウスネイティブソリューションからテーブルを選択します。 選択すると、データのコンテンツのプレビューが表示されます。


### データフローの詳細

チェンジ・データ・キャプチャを必ず有効にします。 情報パネルが表示され、チェンジ・データ・キャプチャの要件が説明されます。

前に作成したリレーショナルスキーマに基づく新しいデータセットまたは既存のデータセットを指定します。 データフローの詳細インターフェイスで他のオプションを指定して選択します。


### マッピング

データウェアハウスネイティブソリューションのテーブルのフィールドを、リレーショナルスキーマに指定したフィールドにマッピングします。


### スケジュール設定

Data Warehouse ネイティブソリューションのテーブルのデータをExperience Platformのデータセットにミラーリングするスケジュールを定義します。


### レビュー

データミラーおよび変更データキャプチャをサポートする Data Warehouse ネイティブソリューションへのソースコネクタの設定を確認します。


ソースコネクタの設定が完了すると、データフローが作成されます。 その時点から、データウェアハウスネイティブソリューションのデータ変更（挿入、更新、削除）が、指定されたデータセットにミラーリングされます。


>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：リレーショナルデータをミラーリングして使用する ](relational.md)
>[Data Mirror（Experience Platform ドキュメント） ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[リレーショナルスキーマ（Experience Platform ドキュメント） ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/relational)
