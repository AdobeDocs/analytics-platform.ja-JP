---
title: Data Mirrorの概要
description: Data Warehouse ネイティブソリューションとCustomer Journey Analyticsの間でデータを同期する方法を理解します。
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: 25d0647c6a764d8f4306a5c049a7a68e0426cef9
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 2%

---

# Experience Platform Data Mirrorの概要

{{release-limited-testing}}

Data Mirrorは、モデルベースのスキーマを使用して、外部データベースからデータレイクに行レベルの変更を取り込めるExperience Platform機能です。 アップストリームの抽出、変換、読み込み（ETL）プロセスを必要とせずに、データの関係を保持し、一意性を確保し、バージョン管理をサポートします。

Experience Platform Data Mirrorを使用して、外部 Data Warehouse ネイティブソリューション（[!DNL Snowflake]、[!DNL Azure Databricks]、[!DNL Google BigQuery]）からの挿入、更新、削除（可変データ）をExperience Platformのデータと直接同期します。 Data Mirrorを使用すると、データをExperience Platformに取り込む際に、既存のデータベースモデル構造とデータ整合性を維持できます。

## 機能とメリット

Data Mirrorには、データベース同期に必要な次の機能が用意されています。

* **プライマリキーが適用されています。** データセット内の一意性を確保し、取り込み中にレコードが重複するのを防ぎます。
* **行レベルの変更取り込み。** 正確な制御によるアップサートや削除を含む、きめ細かいデータ変更をサポートします。
* **スキーマの関係。** 記述子を使用してデータセット間の外部キーとプライマリキーの関係を有効にします。
* **順不同のイベント処理。** プロセスは、順不同で到着した場合でも、バージョンとタイムスタンプの記述子を使用してイベントを変更します。
* **ウェアハウスの直接統合。** は、サポートされているクラウドデータウェアハウスと接続して、リアルタイムの変更同期を実現します。

Data Mirrorを使用して、ソースシステムから直接変更内容を取り込み、スキーマの整合性を適用し、分析、journey orchestration、コンプライアンスワークフローでデータを使用できるようにします。 Data Mirrorを使用すると、既存のデータベースモデルを直接ミラーリングできるので、複雑なアップストリーム ETL プロセスが不要になり、実装が迅速化されます。 この排除により、削除やデータハイジーン操作を正確に制御して、データガバナンスを強化できます。

Data Mirrorに関する [Experience Platformのドキュメントも参照してください ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}。

## Customer Journey AnalyticsのData Mirror

>[!NOTE]
>
>Customer Journey AnalyticsのExperience Platform Data Mirror機能は、2026 年 3 月 25 日まで **パブリックベータ版** で利用できます。 お客様は、ソースコネクタを介して、1 日あたり最大 200 万行の変更行をAdobe Experience Platform Data Lake に取り込むことができます。 Adobeは、お客様の組織がこれらの制限を超えた場合、Experience Platform Data Mirror機能へのベータ版のアクセスを終了する権利を留保します。 <br/> この機能へのアクセスをリクエストするには、Adobe アカウントチームにお問い合わせください。
>

Customer Journey Analytics用Experience Platform Data Mirrorは、選択した data warehouse ネイティブソリューション（[!DNL Azure Databricks]、[!DNL Google BigQuery] および [!DNL Snowflake]）で使用できます。 Customer Journey Analytics版のExperience Platform Data Mirrorでは、次のアプリケーションまたはコンポーネントを適切に設定する必要があります。

* [データウェアハウスネイティブソリューション](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：モデルベースのデータをミラーリングして使用する ](model-based.md)
>>[Data Mirror（Experience Platform ドキュメント） ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>>[モデルベースのスキーマ（Experience Platform ドキュメント） ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
