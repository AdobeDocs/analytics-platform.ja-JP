---
title: Customer Journey Analytics を使い始める
description: Customer Journey Analytics を実装するのに必要な前提条件およびワークフローについて把握します。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 100%

---

# Customer Journey Analytics を使い始める

Customer Journey Analytics を実装するには、次のワークフローに従う必要があります。初期タスクの中には、Adobe Experience Platform で実行されるものと、Customer Journey Analytics で実行されるものがあります。

## 前提条件

Customer Journey Analytics を利用できる人物は次のとおりです。

* Adobe Analytics [Select、Prime、または Ultimate](https://www.adobe.com/jp/analytics/compare-adobe-analytics-packages.html) のお客様
* [Adobe Experience Platform](https://www.adobe.com/jp/experience-platform.html) 用にプロビジョニングされている
* Customer Journey Analytics SKU を購入している。

## ワークフロー

| タスク | 詳細 |
|---|---|
| **手順 1：データを Adobe Experience Platform に取り込む** | この手順は、Adobe Experience Platform で実行され、いくつかのサブ手順が必要となります。<ul><li>**手順 1a：データスキーマの準備**：[Adobe Experience Data Model（XDM）](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)を使用して顧客体験データを標準化し、顧客体験管理の[スキーマを定義](https://docs.adobe.com/content/help/ja-JP/experience-platform/tutorials/home.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)します。</li><li>**手順 1b：スキーマに基づいてデータセットを作成します**：Platform 内のデータは、電子メールデータセット、CRM データセット、POS データセット、Adobe Analytics データセットなどのデータセットで構成されます。各データセットは、スキーマとデータのバッチで構成されます。[Experience Platform](https://docs.adobe.com/content/help/ja-JP/experience-platform/tutorials/home.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md) でデータセットを作成できます。</li><li>**手順 1c：データを Experience Platform に取り込む**：標準搭載の Adobe Analytics Platform コネクタを使用して、従来の Adobe Analytics データを Platform に取り込みます。レポートスイートごとに 1 つのソース接続を作成できます。Adobe Experience Platform ドキュメントの [Adobe Analytics を使用したソース接続の作成](https://docs.adobe.com/content/help/ja-JP/experience-platform/tutorials/home.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)を参照してください。接続が作成されると、ターゲットスキーマとデータセットが自動的に作成され、受信データが格納されます。さらに、データのバックフィルが発生し、最大 13 か月の履歴データが取り込まれます。初回の取り込みが完了したら `Step 2` に進み、この Analytics データセットと Customer Journey Analytics の接続を作成します。また、[バッチ取り込み](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)、[ストリーミング取り込み](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)、[他のソースコネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)を使用して、他のデータタイプを取り込むこともできます。</li></ul> |
| **手順 2：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成する** | 接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。Experience Platform データセットに関するレポートを作成するには、まず Experience Platform とワークスペースのデータセット間で接続を確立する必要があります。<br>[接続の作成](/help/connections/create-connection.md)を参照してください。 |
| **手順 3：データビューの作成** | データ表示は、データの「フィルタリングされた」表示です。同じ接続に対して異なるデータビューを作成し、訪問のタイムアウト、アトリビューションなどに関する設定を変えることができます。1 つのデータセットに対して複数のデータビューを作成できます。<br>[データビューの作成](/help/data-views/create-dataview.md)を参照してください。 |
| **手順 4：ワークスペースでのクロスチャネルデータのレポート** | 接続とデータビューを作成した後、Analysis Workspace の機能と柔軟性を使用して、取得したデータを分析します。<br>[基本分析の実行](/help/analysis-workspace/perform-basic-analysis.md)および[詳細分析の実行](/help/analysis-workspace/perform-adv-analysis.md)を参照してください。 |
