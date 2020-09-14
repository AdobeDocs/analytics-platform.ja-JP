---
title: Customer Journey Analytics用のデータ取り込みオプション
description: データをCustomer Journey Analyticsに取り込む様々な方法を理解する
translation-type: tm+mt
source-git-commit: a48ebc2fbd4cb43de4424e9c1805504752a44fce
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 28%

---


# Customer Journey Analytics用のデータ取り込みオプション

データをCustomer Journey Analyticsに取り込むときには、様々な選択肢があります。 伝統的なAdobe Analyticsのデータを移動したいと思う人もいれば、Adobe Experience Platformから直接データを取り込むと思う人もいます。 このリファレンスでは、以下に示す高度な手順について説明します。

## 伝統的なAdobe Analyticsのデータを取り込む

このワークフローは、Adobe Analyticsデータコネクタを使用します。タグマネージャーとしてDTMを使用するか、Launchを使用するかによって異なります。

### Dynamic Tag Management(DTM)を使用

1. [データレイヤーの作成](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)まだ行っていない場合は、行います。 データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. 使用する [DTM](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/other/dtm/dtm-implementation-overview.html) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。 Dynamic Tag Management では、単一のデータ層で複数のソースのデータをプッシュできます。
1. Folio Builder [Adobe Analyticsソースコネクタ](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) adobe experience platformで このソースコネクターは、Analyticsデータを、 [エクスペリエンスデータモデル(XDM)システム](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html).
1. 使用する [Customer Journey Analytics](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートに通知する1つ以上の接続とデータ表示を作成します。

### 開始を使用

1. [データレイヤーの作成](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)まだ行っていない場合は、行います。 データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. 使用する [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。 Launch は、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。オファーを他のソリューションや製品と統合して起動し、カスタムコードを導入できます。 これらのタスクはすべて、貴社の開発チームに依存しなくても実行でき、サイトのコードを更新できます。
1. Folio Builder [Adobe Analyticsソースコネクタ](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) adobe experience platformで このソースコネクターは、Analyticsデータを、 [エクスペリエンスデータモデル(XDM)システム](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. 使用する [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートに通知する1つ以上の接続とデータ表示を作成します。
