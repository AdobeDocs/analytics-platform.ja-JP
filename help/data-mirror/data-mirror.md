---
title: Data Mirrorの概要
description: データウェアハウスネイティブソリューションとCustomer Journey Analytics間でデータを同期する方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 447
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

Data Mirror[&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}に関するExperience Platform ドキュメントも参照してください。

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
>[リレーショナルスキーマ （Experience Platform ドキュメント） &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/relational)
