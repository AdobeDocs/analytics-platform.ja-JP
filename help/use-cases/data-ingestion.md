---
title: Customer Journey Analytics のデータ取り込みオプション
description: Customer Journey Analytics にデータを取り込む様々な方法について
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 143979330addce3fce045d1785ae969c75a78d28
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 98%

---

# Customer Journey Analytics のデータ取り込みオプション

Customer Journey Analytics へのデータの取り込みには、様々なオプションがあります。従来の Adobe Analytics データを移動することを想定しているものもあれば、Adobe Experience Platform から直接データを取り込むことを想定しているものもあります。このリファレンスでは、従うべき手順の概要と、より詳細な情報へのリンクを示します。

## 従来の Adobe Analytics からのデータの取り込み

このワークフローでは、Adobe Analytics ソースコネクタを使用し、タグマネージャとして DTM と Launch のどちらを使用するかによって異なります。

### Adobe Experience Platform（以前の [!UICONTROL Launch]）のタグを使用する場合

1. [データレイヤーの作成](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=ja)をまだ行っていない場合は、行います。データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [Adobe Experience Platform タグ](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=ja)を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。このタグ管理ソリューションを使用すると、他のタグ要件と共に Analytics コードを導入できます。タグは、他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を作成します。このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。関連トピック [Customer Journey AnalyticsでのAdobe Analyticsレポートスイートデータの利用](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## Adobe Experience Platform Web SDK と Edge Network を介したデータの取り込み

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) は、Adobe Experience Cloud のお客様が Adobe Experience Platform Edge Network. を通じて Experience Cloud の様々なサービスとやり取りできるようにする、クライアントサイド JavaScript ライブラリです。

1. [タグで AEP Web SDK 拡張機能を設定](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=ja)し、web プロパティから Adobe Experience Platform Edge Network を通じて Adobe Experience Cloud にデータを送信します。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。

## バッチ取り込みとストリーミング取り込みによるデータの取り込み

Adobe Experience Platform では、複数のソースからのデータを統合し、マーケターが顧客の行動をより深く理解できるようにします。Adobe Experience Platform のデータ取り込みは、Platform がこれらのソースからデータを取り込む複数の方法と、そのデータがデータレイク内でどのように保持されてダウンストリームの Platform サービスで使用されるかを表します。

### バッチ取り込み

1. [バッチ取り込み](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=ja#batch)を設定して、データをバッチファイルとして Adobe Experience Platform に取り込むことができます。CRM システムのフラットファイルのプロファイルデータ（Parquet ファイルなど）、または Experience Data Model（XDM）レジストリの既知のスキーマに適合するデータを取り込むことができます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。

### ストリーミング取り込み

1. [ストリーミング取り込み](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja#streaming)を設定して、クライアントおよびサーバーサイドのデバイスから、リアルタイムで Experience Platform にデータを送信できます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。

## Google Analytics データを取り込んで Customer Journey Analytics で分析する

[Customer Journey Analyticsを使用して Google Analytics データを解析する方法](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html?lang=ja)について、このチュートリアルをご確認ください。

## Bulk Data Insertion API を使用してデータを Analytics に取り込んでから、Experience Platform で Adobe ソースコネクタを介して取り込む

1. [Bulk Data Insertion API を使用](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)して、サーバーサイドの収集データを Adobe Analytics に送信します。イベントデータを含む CSV 形式のファイルを送信できます。
1. [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)を作成して、このコンシューマデータを Adobe Experience Platform に取得します。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。
