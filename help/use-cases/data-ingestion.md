---
title: Customer Journey Analytics のデータ取り込みオプション
description: Customer Journey Analytics にデータを取り込む様々な方法について
translation-type: tm+mt
source-git-commit: 8a3a868ff4e2fbbcdf83ff7769382c6a92f78ec2
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 72%

---


# Customer Journey Analytics のデータ取り込みオプション

Customer Journey Analytics へのデータの取り込みには、様々なオプションがあります。従来の Adobe Analytics データを移動することを想定しているものもあれば、Adobe Experience Platform から直接データを取り込むことを想定しているものもあります。このリファレンスでは、従うべき手順の概要と、より詳細な情報へのリンクを示します。

## 従来の Adobe Analytics からのデータの取り込み

このワークフローでは、Adobe Analytics データコネクタを使用し、タグマネージャーとして DTM を使用するか、Launch を使用するかによって異なります。

### Dynamic Tag Management（DTM）

1. [データレイヤーの作成](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/prepare/data-layer.html)をまだおこなっていない場合は、おこないます。データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [DTM](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/other/dtm/dtm-implementation-overview.html) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。Dynamic Tag Management では、単一のデータ層で複数のソースのデータをプッシュできます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)を作成します。このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

### Launch を使用

1. [データレイヤーの作成](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)をまだおこなっていない場合は、おこないます。データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/launch/overview.html) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。Launch は、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。Launch は他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)を作成します。このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## Adobe Experience PlatformWeb SDKとEdgeネットワークを介したデータの取り込み

[Adobe Experience PlatformWeb ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDKは、Adobe Experience Cloudのお客様がAdobe Experience Platformエッジネットワークを介してExperience Cloud内の様々なサービスとやり取りできるようにする、クライアント側のJavaScriptライブラリです。

1. [AEP Web SDK Extensionを](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) Launchで設定し、WebプロパティからAdobe Experience Platformエッジネットワーク経由でAdobe Experience Cloudにデータを送信します。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## データの取り込みとバッチ取り込みとストリーミング取り込み

Adobe Experience Platform では、複数のソースからのデータを統合し、マーケターが顧客の行動をより深く理解できるようにします。Adobe Experience Platform のデータ取り込みは、Platform がこれらのソースからデータを取り込む複数の方法と、そのデータがデータレイク内でどのように保持されてダウンストリームの Platform サービスで使用されるかを表します。

### バッチ取得

1. [バッチインジェスト](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch)を設定し、データをバッチファイルとしてAdobe Experience Platformに取り込めるようにします。 CRM システムのフラットファイルのプロファイルデータ（Parquet ファイルなど）、または Experience Data Model（XDM）レジストリの既知のスキーマに適合するデータを取り込むことができます。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

### ストリーミング取得

1. [ストリーミング取り込み](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming)を設定して、クライアントおよびサーバ側のデバイスからExperience Platformにデータをリアルタイムで送信します。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## Google Analyticsデータを取り込んでCustomer Journey Analyticsで分析する

[Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives)を使用してGoogle Analyticsデータを解析する方法について、このチュートリアルを参照してください。

## Bulk Data Insertion APIを使用してデータをAnalyticsに取り込み、Experience PlatformでAdobeソースコネクタを介して取り込む

1. [Bulk Data Insertion ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) APIを使用して、サーバー側の収集データをAdobe Analyticsに送信します。イベントデータを含むCSV形式のファイルを送信できます。
1. [Adobe Analyticsソース](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) コネクタを作成して、このコンシューマデータをAdobe Experience Platformに取り込みます。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。