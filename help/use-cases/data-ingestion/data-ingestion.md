---
title: Customer Journey Analytics のデータ取り込みオプション
description: Customer Journey Analytics にデータを取り込む様々な方法について
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T11:01:56.579Z'
TQID: 'https://experienceleague.adobe.com/Uqoyk9k3hEOB90hzLtXhoYtmfX18wmXPHp-AWxgNIwU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: bfef374d-acfd-4c57-bf74-a2b36053c545id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 827
ht-degree: 86%

---

# Customer Journey Analytics のデータ取り込みオプション

Customer Journey Analytics へのデータの取り込みには、様々なオプションがあります。 従来の Adobe Analytics データを移動することを想定しているものもあれば、Adobe Experience Platform から直接データを取り込むことを想定しているものもあります。 このリファレンスでは、従うべき手順の概要と、より詳細な情報へのリンクを示します。

## 従来の Adobe Analytics からのデータの取り込み

このワークフローでは、Analytics ソースコネクタを使用します。DTMを使用するか、Launch as a Tag Managerを使用するかによって異なります。

### Adobe Experience Platform（以前の [!UICONTROL Launch]）のタグを使用する場合

1. [データレイヤーの作成](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=ja)をまだ行っていない場合は、行います。 データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。 データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [Adobe Experience Platform タグ](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=ja)を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。 このタグ管理ソリューションを使用すると、他のタグ要件と共に Analytics コードを導入できます。 タグは、他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。 これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を作成します。 このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。 詳しくは、[Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)を参照してください。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

## Adobe Experience Platform Web SDK と Edge Network を介したデータの取り込み

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)は、Adobe CX Enterpriseのお客様がAdobe Experience Platform Edge Networkを通じてCX Enterpriseの様々なサービスと対話できるようにする、クライアントサイドのJavaScript ライブラリです。

1. [Adobe Experience Platform Web SDK拡張機能をタグ ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=ja)で構成して、Adobe Experience Platform Edge Networkを介してweb プロパティからCX Enterpriseにデータを送信します。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。

## バッチ取り込みとストリーミング取得によるデータの取り込み

Adobe Experience Platform では、複数のソースからのデータを統合し、マーケターが顧客の行動をより深く理解できるようにします。 Adobe Experience Platform のデータ取り込みは、Platform がこれらのソースからデータを取り込む複数の方法と、そのデータがデータレイク内でどのように保持されてダウンストリームの Platform サービスで使用されるかを表します。

### バッチ取り込み

1. [バッチ取り込み](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=ja#batch)を設定して、データをバッチファイルとして Adobe Experience Platform に取り込むことができます。 CRM システムのフラットファイルのプロファイルデータ（Parquet ファイルなど）、またはエクスペリエンスデータモデル（XDM）レジストリの既知のスキーマに適合するデータを取り込むことができます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。

### ストリーミング取り込み

1. [ストリーミング取り込み](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=ja#streaming)を設定して、クライアントおよびサーバーサイドのデバイスから、リアルタイムで Experience Platform にデータを送信できます。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。

## Google Analytics データを取り込んで Customer Journey Analytics で分析する

[Customer Journey Analyticsを使用して Google Analytics データを解析する方法](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html)について、このチュートリアルをご確認ください。

## Bulk Data Insertion APIを使用してデータをAnalyticsに取り込み、Experience PlatformのAnalytics ソースコネクタを介して取り込みます

1. [Bulk Data Insertion API を使用](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)して、サーバーサイドの収集データを Adobe Analytics に送信します。 イベントデータを含む CSV 形式のファイルを送信できます。
1. [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を作成して、このコンシューマデータを Adobe Experience Platform に取得します。
1. [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ja) を使用して、クロスチャネルレポートのための 1 つ以上の[接続](/help/connections/create-connection.md)と[データ表示](/help/data-views/data-views.md)を作成します。
