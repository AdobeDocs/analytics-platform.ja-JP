---
description: データフィードを使用してCustomer Journey Analyticsから生データを取得する方法を説明します。 データフィードを使用するための前提条件と次に行うべきことについて説明します。
keywords: クリックストリーム;データフィード;データフィード;データフィード
title: Analytics データフィードの概要
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 66a8a96da6710d20b01b9315fe87ba38c54c2511
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 21%

---

# データフィードの概要

{{release-limited-testing}}

データフィードは、Customer Journey Analyticsから生データを取得する強力な方法です。 自社の裁量により、Adobe以外のプラットフォームでもこの生データを使用できます。 データは、各時間の終了時に時間単位のバッチで、または毎日の終わりに日単位のバッチで配信されます。

## 前提条件

データフィードを使用する前に、次のすべての要件を満たしていることを確認してください。

* Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->にデータを取り込む作業中の実装
* アカウントがAnalytics製品管理者であるか、アカウントがデータフィード <!--???-->へのアクセス権を持つ製品プロファイルに属しています
* [!DNL Amazon S3]、[!DNL Google Cloud Platform]、[!DNL Azure RBAC]または[!DNL Azure SAS]に構成されたバケット

## 基本を学ぶ

Customer Journey Analyticsのデータフィードの使用を開始するには、まず、Customer Journey AnalyticsのデータフィードとAdobe Analyticsのデータフィードの違いを理解します。 違いを理解したら、Adobe Analytics データフィードをCustomer Journey Analyticsにマッピングしてから、データフィードの作成を開始できます。

1. [Customer Journey AnalyticsとAdobe Analyticsのデータ フィードの違いを理解する](/help/components/exports/cja-data-feeds/df-comparison.md)。

1. [Adobe Analytics データフィード列をCustomer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)にマッピングします。

1. [ データフィードを作成](/help/components/exports/cja-data-feeds/create-feed.md)。

