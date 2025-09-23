---
title: Data Mirrorの概要
description: Data Warehouse ネイティブソリューションとCustomer Journey Analyticsの間でデータを同期する方法を理解します。
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="ベータ版"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: a6cdade9790ef4bc222eb5979b7370f7403b5ad5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 1%

---

# Experience Platform Data Mirrorの概要

{{release-limited-testing}}

Data Mirrorは、モデルベースのスキーマを使用して、外部データベースからデータレイクに行レベルの変更を取り込めるExperience Platform機能です。 アップストリームの抽出、変換、読み込み（ETL）プロセスを必要とせずに、データの関係を保持し、一意性を確保し、バージョン管理をサポートします。

Data Mirrorを使用して、[!DNL Snowflake]、[!DNL Azure Databricks]、[!DNL Google BigQuery] などの外部データウェアハウスネイティブソリューションからの挿入、更新、削除（可変データ）をExperience Platformに直接同期します。 Data Mirrorを使用すると、データをExperience Platformに取り込む際に、既存のデータベースモデル構造とデータ整合性を維持できます。


## 機能とメリット

Data Mirrorには、データベース同期に必要な次の機能が用意されています。

* **プライマリ キーの適用**. データセット内の一意性を確保し、取り込み中にレコードが重複するのを防ぎます。
* **行レベルの変更の取得**。 精度の高い制御で、アップサートや削除を含む、きめ細かいデータ変更をサポートします。
* **スキーマの関係**。 記述子を使用してデータセット間の外部キーとプライマリキーの関係を有効にします。
* **順不同のイベント処理**。 は、順不同で到着した場合でも、バージョンとタイムスタンプの記述子を使用して変更イベントを処理します。
* **ウェアハウスの直接統合**. は、サポートされているクラウドデータウェアハウスと接続して、リアルタイムの変更同期を実現します。

Data Mirrorを使用して、ソースシステムから直接変更内容を取り込み、スキーマの整合性を適用し、分析、journey orchestration、コンプライアンスワークフローでデータを使用できるようにします。 Data Mirrorを使用すると、既存のデータベースモデルを直接ミラーリングできるので、複雑なアップストリーム ETL プロセスが不要になり、実装が迅速化されます。 この排除により、削除やデータハイジーン操作を正確に制御して、データガバナンスを強化できます。

<!-- Add link when AEP docs are ready... -->

Data Mirrorに関するExperience Platformのドキュメントも参照してください。


## Customer Journey AnalyticsのData Mirror

>[!NOTE]
>
>Customer Journey AnalyticsのExperience Platform Data Mirror機能は、2026 年 3 月 25 日まで **パブリックベータ版** で利用できます。 ベータ版の期間中、CDC （Change Data Capture）のアップデートは、Customer Journey Analyticsが使用できる 1 日あたり 1,000 万行の変更行の制限を受けます。 Adobeは、お客様の組織がこの制限を超えた場合に、Experience Platform Data Mirror機能へのベータ版のアクセスを終了する権利を留保します。 請求の影響を含む、機能の詳細については、Experience League ドキュメントのこの節を参照してください。
>

Experience Platform Data Mirror for Customer Journey Analytics機能は、選択した Data Warehouse ネイティブソリューション（[!DNL Azure Databricks]、[!DNL Google BigQuery]、[!DNL Snowflake]）で使用できます。 Customer Journey Analytics バージョンのData Mirror機能を使用するには、次のいくつかのコンポーネントを適切にセットアップし設定する必要があります。

* [データウェアハウスネイティブソリューション](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：モデルベースのデータをミラーリングして使用する ](model-based.md)
>
