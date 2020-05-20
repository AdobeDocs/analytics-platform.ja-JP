---
title: 顧客の遍歴分析はじめに
description: カスタマージャーニー分析はじめにを参照してください。
translation-type: tm+mt
source-git-commit: e30bbae59e11bbf93668ffe072508727f6efdd51
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 10%

---


# 顧客の遍歴分析はじめに

顧客の遍歴分析を導入するには、次のワークフローに従う必要があります。 初期タスクの中には、Adobe Experience Platformで実行されるものと、Customer Jeurney Analyticsで実行されるものがあります。

## 前提条件

カスタマージャーニー分析は、

* Adobe Analyticsの [お客様は](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) 、
* Adobe Experience Platform用にプロビジョニングされ [ているか](https://www.adobe.com/jp/experience-platform.html)、
* 顧客の遍歴分析SKUを購入済み

## ワークフロー

| タスク | 詳細 |
|---|---|---|
| **手順1: データをAdobe Experience Platformに取り込む** | この手順は、Adobe Experience Platformで実行され、次のいくつかのサブ手順を含みます。<br>**手順1a: データスキーマの準備&#x200B;**: Adobe Experience Data Model([XDM)を使用して、顧客体験データを標準化し](https://www.adobe.io/apis/experienceplatform/home/xdm.html)、顧客体験管理のスキーマを[定義します](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)。<br>**手順1b: スキーマに基づいてデータセットを作成します**。 プラットフォームのデータは、電子メールデータセット、CRMデータセット、POSデータセット、Adobe Analyticsデータセットなどのデータセットで構成されます。 各データセットは、スキーマとデータのバッチで構成されます。 Experience Platform [でデータセットを作成できます](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)。<br>**手順1c: データをエクスペリエンスプラットフォームに取り込む&#x200B;**: 標準搭載のAdobe Analytics Platform Connectorを使用して、従来のAdobe Analyticsデータをプラットフォームに取り込みます。 レポートスイートごとに1つのソース接続を作成できます。 Adobe Experience Platformドキュメントの[Adobe Analyticsを使用したソース接続の](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)作成を参照してください。 接続が作成されると、ターゲットスキーマとデータセットが自動的に作成され、受信データが格納されます。 さらに、データのバックフィルが発生し、最大13か月の履歴データが取り込まれます。 初回インジェストが完了したら、先に進んで、このAnalyticsデータセット`Step 2`とCustomer Jeurney Analyticsとの間の接続を作成できます。<br>また、[バッチ取り込み](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)、ストリーミング取り込み[、](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)他のソースコネクタを使用して、他のデータタイプを取り込むこともできます[](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)。 |
| **手順2: プラットフォームデータセットとCustomer Jeurney Analytics間の接続の作成** | 接続を使用すると、Adobe Experience PlatformのデータセットをWorkspaceに統合できます。 エクスペリエンスプラットフォームのデータセットに関するレポートを作成するには、まずExperience PlatformとWorkspaceのデータセット間の接続を確立する必要があります。<br>「接続の [作成](/help/connections/create-connection.md)」を参照してください。 |
| **手順3: データ表示の作成** | データ表示は、データの「フィルタされた」表示です。 同じ接続に対して異なるデータ表示を作成でき、訪問のタイムアウト、属性などに関する設定を変えることができます。 1つのデータセットに対して複数のデータ表示を作成できます。<br>データ表示の [作成を参照してください](/help/data-views/create-dataview.md)。 |
| **手順4: Workspaceでのクロスチャネルデータのレポート** | 接続とデータ表示を作成したら、分析ワークスペースのパワーと柔軟性を使用して導入したデータを分析します。<br>基本分析 [の実行](/help/projects/perform-basic-analysis.md) および詳細分析 [の実行を参照してください](/help/projects/perform-adv-analysis.md)。 |
