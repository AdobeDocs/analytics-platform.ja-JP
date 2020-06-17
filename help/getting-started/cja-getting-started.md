---
title: Customer Journey Analytics を使い始める
description: Customer Journey Analytics を使い始めます。
translation-type: tm+mt
source-git-commit: 16bca45f2576d3feef8129d558fad6f236852cb9
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 71%

---


# Customer Journey Analytics を使い始める

Customer Journey Analytics を実装するには、次のワークフローに従う必要があります。初期タスクの中には、Adobe Experience Platform で実行されるものと、Customer Journey Analytics で実行されるものがあります。

## 前提条件

Customer Journey Analytics を利用できる人物は次のとおりです。

* Are Adobe Analytics [Select、Prime、または Ultimate](https://www.adobe.com/jp/analytics/compare-adobe-analytics-packages.html) のお客様
* [Adobe Experience Platform](https://www.adobe.com/jp/experience-platform.html) 用にプロビジョニングされている
* Customer Journey Analytics SKU を購入している。

## ワークフロー

| タスク | 詳細 |
|---|---|
| **手順 1：データを Adobe Experience Platform に取り込む** | この手順は、Adobe Experience Platformで実行され、次のいくつかのサブ手順を含みます。<ul><li>**手順1a: データスキーマの準備**: Adobe Experience Data Model( [XDM)を使用して、顧客体験データを標準化し](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.translate.html) 、顧客体験管理のスキーマを [定義します](https://docs.adobe.com/content/help/ja-JP/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) 。</li><li>**手順1b: スキーマに基づいてデータセットを作成します**。 Platform内のデータは、電子メールデータセット、CRMデータセット、POSデータセット、AdobeAnalyticsデータセットなどのデータセットで構成されます。 各データセットは、スキーマとデータのバッチで構成されます。[Experience Platform](https://docs.adobe.com/content/help/ja-JP/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md) でデータセットを作成できます。</li><li>**手順1c: データをExperience Platformに取り込む**: 標準搭載のAdobeAnalyticsPlatformコネクタを使用して、従来のAdobeAnalyticsデータをPlatformに取り込みます。 レポートスイートごとに 1 つのソース接続を作成できます。Adobe Experience Platform ドキュメントの [Adobe Analytics を使用したソース接続の作成](https://docs.adobe.com/content/help/ja-JP/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)を参照してください。接続が作成されると、ターゲットスキーマとデータセットが自動的に作成され、受信データが格納されます。さらに、データのバックフィルが発生し、最大 13 か月の履歴データが取り込まれます。初回の取り込みが完了したら `Step 2` に進み、この Analytics データセットと Customer Journey Analytics の接続を作成します。また、 [バッチ取り込み](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)、[ストリーミング取り込み](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)、 [他のソースコネクタを使用して、他のデータタイプを取り込むこともできます](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)。</li></ul> |
| **手順 2：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成する** | 接続を使用すると、Adobe Experience PlatformのデータセットをWorkspaceに統合できます。 Experience Platformデータセットをレポートするには、まずExperience PlatformとWorkspaceのデータセット間の接続を確立する必要があります。<br>[接続の作成](/help/connections/create-connection.md)を参照してください。 |
| **手順 3：データビューの作成** | データ表示は、データの「フィルタされた」表示です。 同じ接続に対して異なるデータビューを作成し、訪問のタイムアウト、アトリビューションなどに関する設定を変えることができます。1 つのデータセットに対して複数のデータビューを作成できます。<br>[データビューの作成](/help/data-views/create-dataview.md)を参照してください。 |
| **手順 4：Workspace でのクロスチャネルデータのレポート** | 接続とデータビューを作成した後、Analysis Workspace の機能と柔軟性を使用して、取得したデータを分析します。<br>[基本分析の実行](/help/analysis-workspace/perform-basic-analysis.md)および[詳細分析の実行](/help/analysis-workspace/perform-adv-analysis.md)を参照してください。 |
