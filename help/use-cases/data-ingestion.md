---
title: Customer Journey Analytics のデータ取り込みオプション
description: Customer Journey Analytics にデータを取り込む様々な方法について
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
source-git-commit: 15312a57f0f122d22d0575f2008d547bcb8ab2ed
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 98%

---

# Customer Journey Analytics のデータ取り込みオプション

Customer Journey Analytics へのデータの取り込みには、様々なオプションがあります。従来の Adobe Analytics データを移動することを想定しているものもあれば、Adobe Experience Platform から直接データを取り込むことを想定しているものもあります。このリファレンスでは、従うべき手順の概要と、より詳細な情報へのリンクを示します。

## 従来の Adobe Analytics からのデータの取り込み

このワークフローでは、Adobe Analytics データコネクタを使用し、タグマネージャーとして DTM を使用するか、Launch を使用するかによって異なります。

### Dynamic Tag Management（DTM）

1. [データレイヤーの作成](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=ja)をまだおこなっていない場合は、おこないます。データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [DTM](https://experienceleague.adobe.com/docs/analytics/implementation/other/dtm/dtm-implementation-overview.html) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。Dynamic Tag Management では、単一のデータ層で複数のソースのデータをプッシュできます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を作成します。このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

### Launch を使用

1. [データレイヤーの作成](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html)をまだおこなっていない場合は、おこないます。データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=ja) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。Launch は、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。Launch は他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)を作成します。このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## Adobe Experience Platform Web SDK と Edge ネットワークを介したデータの取得

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) は、Adobe Experience Cloud のお客様が Experience Cloud の様々なサービスを操作できるようにする、クライアントサイド JavaScript ライブラリです。

1. [AEP Web SDK 拡張機能を Launchで設定し](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=en)、Web プロパティから Adobe Experience Platform Edge ネットワーク経由で Adobe Experience Cloud にデータを送信します。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## バッチ取得とストリーミング取得によるデータの取得

Adobe Experience Platform では、複数のソースからのデータを統合し、マーケターが顧客の行動をより深く理解できるようにします。Adobe Experience Platform のデータ取り込みは、Platform がこれらのソースからデータを取り込む複数の方法と、そのデータがデータレイク内でどのように保持されてダウンストリームの Platform サービスで使用されるかを表します。

### バッチ取得

1. [バッチ取得](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=ja#batch)を設定してデータをバッチファイルとして Adobe Experience Platform に取得することができます。CRM システムのフラットファイルのプロファイルデータ（Parquet ファイルなど）、または Experience Data Model（XDM）レジストリの既知のスキーマに適合するデータを取り込むことができます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

### ストリーミング取得

1. [ストリーミング取得](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja#streaming)を設定して、クライアントおよびサーバーサイドのデバイスから、リアルタイムで Experience Platform にデータを送信できます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## Google Analytics データを取り込んで Customer Journey Analytics で分析する

[Customer Journey Analyticsを使用して Google Analytics データを解析する方法](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=ja#objectives)について、このチュートリアルをご確認ください。

## 一括データ挿入 API を使用してデータを Analytics に取り込み、Experience Platform で Adobe ソースコネクタを介して取得する

1. [一括データ取得 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) を使用して、サーバーサイドの収集データを Adobe Analytics に送信します。イベントデータを含む CSV 形式のファイルを送信できます。
1. [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を作成して、このコンシューマデータを Adobe Experience Platform に取得します。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。
