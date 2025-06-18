---
title: Customer Journey Analytics B2B クイックスタートガイド
description: Customer Journey AnalyticsのB2B editionのクイックスタートガイド
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---


# B2B edition クイックスタートガイド

Customer Journey Analytics B2B editionを実装するには、まず B2B に特有の概念や機能を理解しておく必要があります。 また、Customer Journey Analyticsを実装するための従来のワークフローについても理解しておく必要があります。

このドキュメントでは、Customer Journey Analyticsの実装に固有のワークフローに焦点を当てます。

## 前提条件

Customer Journey Analytics B2B editionを実装するには、次の前提条件が適用されます。

* Customer Journey Analyticsで管理タスクを実行するために必要な [ アクセス制御と権限 ](/help/technotes/access-control.md) を持っている。
* Customer Journey Analytics B2B edition アドオンパッケージをパッケージ化しました。


## ワークフロー

| タスク | 詳細 |
| --- | --- |
| **手順 1:B2B データのExperience Platformへの取り込み** | この手順は、Experience Platformで実行され、いくつかのサブ手順が必要となります。<ul><li>**手順 1a：データスキーマの準備**: [Adobe Experience Data Model （XDM） ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja) を使用して、B2B データを標準化し、B2B データの [ スキーマを定義 ](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) します。</li><li>**手順 1b：スキーマに基づいたデータセットの作成**:Platform 内のデータは、アカウントデータ、商談データ、購入グループデータ、キャンペーンデータ、マーケティングリストデータ、メールデータセット、CRM データセット、POS データセットなどのデータセットで構成されます。 各データセットは、データのスキーマとバッチで構成されます。[Experience Platform でデータセットを作成](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ja)できます。</li><li>**手順 1c:Experience Platformへのデータの取り込み**:[ 複数のオプション ](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/home) を使用できます。</li></ul> |
| **手順 2：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成する** | 接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。Experience Platform データセットに関するレポートを作成するには、まずExperience PlatformとWorkspaceのデータセット間で接続を確立する必要があります。 B2B editionとの接続を設定する際には、さらにオプションがあります。 <br>詳しくは、[接続の作成または編集](/help/connections/create-connection.md)を参照してください。 |
| **手順 3：データビューの作成** | データビューは、データの *フィルター済み* ビューです。 同じ接続に対して異なるデータビューを作成し、訪問タイムアウト、アトリビューションなどに異なる設定を指定できます。 1 つのデータセットに対して複数のデータビューを作成できます。B2B editionを使用する場合、データビューを設定する際に追加のオプションを使用できます。<br>[データビューの作成](/help/data-views/create-dataview.md)を参照してください。 |
| **手順 4：ワークスペースでのクロスチャネルデータのレポート** | 接続とデータビューを作成したら、Analysis Workspaceの機能と柔軟性を使用して、取り込んだ B2B データを分析します。<br>[基本分析の実行](/help/analysis-workspace/perform-basic-analysis.md)および[詳細分析の実行](/help/analysis-workspace/perform-adv-analysis.md)を参照してください。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->