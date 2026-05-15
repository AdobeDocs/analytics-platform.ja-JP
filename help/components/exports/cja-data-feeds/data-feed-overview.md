---
description: データフィードを使用してCustomer Journey Analyticsから生データを取得する方法を説明します。 データフィードを使用するための前提条件と次に行うべきことについて説明します。
keywords: クリックストリーム;データフィード;データフィード;データフィード
title: Analytics データフィードの概要
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 5e77857ca846767e3b9e7479baa4a4b18c6e3c8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 21%

---

# データフィードの概要

データフィードは、Customer Journey Analyticsから生データを取得する強力な方法です。 自社の裁量により、Adobe以外のプラットフォームでもこの生データを使用できます。 データは、各時間の終了時に時間単位のバッチで、または毎日の終わりに日単位のバッチで配信されます。

## 前提条件

データフィードを使用する前に、次のすべての要件を満たしていることを確認してください。

* Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->にデータを取り込む作業中の実装
* アカウントがAnalytics製品管理者であるか、アカウントがデータフィード <!--???-->へのアクセス権を持つ製品プロファイルに属しています
* {DNL Amazon S3}、{DNL Google Cloud Platform}、{DNL Azure RBAC}または {DNL Azure SAS}

## 基本を学ぶ

Customer Journey Analyticsのデータフィードの使用を開始するには、まず、Customer Journey AnalyticsのデータフィードとAdobe Analyticsのデータフィードの違いを理解します。 違いを理解したら、Adobe Analytics データフィードをCustomer Journey Analyticsにマッピングしてから、データフィードの作成を開始できます。

1. [Customer Journey AnalyticsとAdobe Analyticsのデータ フィードの違いを理解する](/help/components/exports/cja-data-feeds/df-comparison.md)。

1. [Adobe Analytics データフィード列をCustomer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)にマッピングします。

1. [ データフィードを作成](/help/components/exports/cja-data-feeds/create-feed.md)。
