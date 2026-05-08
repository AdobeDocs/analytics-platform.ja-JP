---
title: Data Mirrorの概要
description: データウェアハウスネイティブソリューションとCustomer Journey Analytics間でデータを同期する方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: dc3aa31c280c1a8ee8a0187edeca9bd34a2c9e2e
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Experience Platform Data Mirrorの概要

{{release-limited-testing}}

Data Mirrorは、リレーショナルスキーマを使用して、外部データベースからデータレイクに行レベルの変更取り込みを可能にするExperience Platform機能です。 データ関係を維持し、一意性を確保し、ETL （上流抽出、変換、格納）プロセスを必要とせずにバージョン管理をサポートします。

Experience Platform Data Mirrorを使用すると、外部データウェアハウスネイティブソリューション（[!DNL Snowflake]、[!DNL Azure Databricks]、または[!DNL Google BigQuery]）からの挿入、更新、削除（可変データ）を、Experience Platformのデータと直接同期できます。 Data Mirrorは、データをExperience Platformに取り込む際に、既存のデータベースモデル構造とデータの整合性を維持するのに役立ちます。

## 機能と利点

Data Mirrorには、データベースの同期に必要な次の機能が用意されています。

* **プライマリキーの適用。** データセット内で一意性を確保し、取得中のレコードの重複を防ぎます。
* **行レベルの変更の取り込み。** 高精度な制御によるアップサートや削除など、詳細なデータ変更をサポートします。
* **スキーマ関係。** 記述子を使用して、データセット間の外部キーとプライマリキーの関係を有効にします。
* **順序なしのイベント処理。** イベントがシーケンス外に到着した場合でも、バージョン記述子とタイムスタンプ記述子を使用してイベントを変更します。
* **直接ウェアハウス統合。** サポートされているクラウドデータウェアハウスと接続し、リアルタイムの変更同期を実現。

Data Mirrorを使用すると、ソースシステムから変更を直接取り込み、スキーマの整合性を適用し、データを分析、ジャーニーオーケストレーション、コンプライアンスワークフローに使用できます。 Data Mirrorでは、既存のデータベースモデルを直接ミラーリングできるので、複雑なアップストリーム ETL プロセスを排除して、実装を迅速化できます。 この排除は、削除とデータハイジーン操作の正確な制御を通じて、データガバナンスを強化できます。

Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}に関する[Experience Platform ドキュメントも参照してください。

## Data Mirror for Customer Journey Analytics

>[!NOTE]
>
>Data Mirrorは現在ベータ版で、Customer Journey Analyticsでの分析にchange data capture （CDC）を使用して一部のデータウェアハウスから取得したデータの同期をサポートしています。<br/>この機能は、2026年6月18日（PT）にCustomer Journey Analyticsで一般公開されます。 適用される製品説明を参照して、今後の年間取り込み制限消費にどのような影響を与えるかを確認してください。 Data Mirrorがベータ版から一般提供に移行しても、引き続きこの機能にアクセスできます。
>

選択したデータウェアハウスネイティブソリューション（[!DNL Azure Databricks]、[!DNL Google BigQuery]、および[!DNL Snowflake]）に対して、Customer Journey Analytics用Experience Platform Data Mirrorを使用できます。 Customer Journey Analytics バージョンのExperience Platform Data Mirrorでは、次のアプリケーションまたはコンポーネントを適切に設定する必要があります。

* [データウェアハウスネイティブソリューション](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：リレーショナルデータのミラーと使用](relational.md)
>[Data Mirror （Experience Platform ドキュメント）](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[リレーショナルスキーマ （Experience Platform ドキュメント） ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/relational)
