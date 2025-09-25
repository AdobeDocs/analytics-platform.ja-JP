---
title: Experience Platformの設定
description: Customer Journey Analytics用Experience Platform Data Mirrorのスキーマおよびデータセットを設定する方法について
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="ベータ版"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: 578e19d8a8205bdfa034900c45d7d4a2d8f6a797
workflow-type: tm+mt
source-wordcount: '471'
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

ミラー化するデータウェアハウスネイティブテーブルをモデル化する [ モデルベースのスキーマ ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based){target="_blank"} を作成する必要があります。 モデルベースのスキーマを作成する場合、次の要件が満たされていることを確認します。

* モデルベースのスキーマのタイプを要求するプロンプトが表示されたら、必ず手動オプションを選択します。
* データのタイプに適したスキーマを選択します。 Experience Platform Data Mirrorは、ほとんどの場合、時系列データ（イベントデータなど）に使用されます。

* スキーマ内のフィールドとその属性を定義します
* モデルベースのスキーマのフィールドに必要な属性を設定します。

   * プライマリキー
   * バージョン識別子
   * タイムスタンプ識別子（時系列データ用）。

## データセット

事前にスキーマのデータセットを設定することも、ソースコネクタを設定する際にデータセットを作成することもできます。
事前にデータセットを作成したりデータセットを選択したりする場合は、以前に作成したモデルベースの [ スキーマ ](#schema) をデータで使用していることを確認します。


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

前に作成したモデルベースのスキーマに基づいて、新しいデータセットまたは既存のデータセットを指定します。 データフローの詳細インターフェイスで他のオプションを指定して選択します。


### マッピング

データウェアハウスネイティブソリューションのテーブルのフィールドを、モデルベースのスキーマに指定したフィールドにマッピングします。


### スケジュール設定

Data Warehouse ネイティブソリューションのテーブルのデータをExperience Platformのデータセットにミラーリングするスケジュールを定義します。


### レビュー

データミラーおよび変更データキャプチャをサポートする Data Warehouse ネイティブソリューションへのソースコネクタの設定を確認します。


ソースコネクタの設定が完了すると、データフローが作成されます。 その時点から、データウェアハウスネイティブソリューションのデータ変更（挿入、更新、削除）が、指定されたデータセットにミラーリングされます。


>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：モデルベースのデータをミラーリングして使用する ](model-based.md)
>&#x200B;>[Data Mirror（Experience Platform ドキュメント） ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>&#x200B;>[モデルベースのスキーマ（Experience Platform ドキュメント） ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
