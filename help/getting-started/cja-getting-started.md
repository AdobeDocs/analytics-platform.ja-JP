---
title: Customer Journey Analytics を使い始める
description: Customer Journey Analytics を実装するのに必要な前提条件およびワークフローについて把握します。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: bfaf76fa5f225e9aa3153fc4ee10c5be8f3164e7
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 98%

---

# Customer Journey Analytics を使い始める

Customer Journey Analytics を実装するには、次のワークフローに従う必要があります。初期タスクの中には、Adobe Experience Platform で実行されるものと、Customer Journey Analytics で実行されるものがあります。

## 前提条件

Customer Journey Analytics を利用できる人物は次のとおりです。

* [Adobe Experience Platform](https://www.adobe.com/jp/experience-platform.html) 用にプロビジョニングされている
* Customer Journey Analytics SKU を購入している。

## ワークフロー

| タスク | 詳細 |
| --- | --- |
| **手順 1：Adobe Analytics から Customer Journey Analytics に移行する場合は、データを移行し、プロジェクトをレプリケートします。** | Adobe Analytics から Customer Journey Analytics へのデータの移行について詳しくは、以下を参照してください。 <ul><li>[Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)</li><li>[従来の Adobe Analytics からのデータの取り込みと使用](../data-ingestion/analytics.md)</li></ul><p>Adobe Analytics プロジェクトの Customer Journey Analytics でのレプリケーションと、Adobe Analytics レポートスイートから Customer Journey Analytics データビューへのプロジェクトコンポーネントのマッピングについて詳しくは、以下を参照してください。</p><ul><li>[Adobe Analytics から Customer Journey Analytics へのコンポーネントとプロジェクトの移行](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html?lang=ja)</li></ul> |
| **手順 2：他のデータを Adobe Experience Platform に取り込む** | この手順は、Adobe Experience Platform で実行され、いくつかのサブ手順が必要となります。<ul><li>**手順 2a：データスキーマの準備**：[Adobe Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用して顧客体験データを標準化し、顧客体験管理の[スキーマを定義](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja)します。</li><li>**手順 2b：スキーマに基づいたデータセットの作成**：Platform 内のデータは、メールデータセット、CRM データセット、POS データセット、Adobe Analytics データセットなどのデータセットで構成されます。各データセットは、データのスキーマとバッチで構成されます。[Experience Platform でデータセットを作成](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ja)できます。</li><li>**手順 2c：Experience Platform へのデータの取り込み**：いくつかのオプションがあります。</li></ul> |
| **手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続の作成** | 接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。Experience Platform データセットに関するレポートを作成するには、まず Experience Platform とワークスペースのデータセット間で接続を確立する必要があります。<br>詳しくは、 [接続の作成または編集](/help/connections/create-connection.md). |
| **手順 4：データビューの作成** | データ表示は、データの「フィルタリングされた」表示です。同じ接続に対して異なるデータビューを作成し、訪問のタイムアウト、アトリビューションなどに関する設定を変えることができます。1 つのデータセットに対して複数のデータビューを作成できます。<br>[データビューの作成](/help/data-views/create-dataview.md)を参照してください。 |
| **手順 5：ワークスペースでのクロスチャネルデータのレポート** | 接続とデータビューを作成した後、Analysis Workspace の機能と柔軟性を使用して、取得したデータを分析します。<br>[基本分析の実行](/help/analysis-workspace/perform-basic-analysis.md)および[詳細分析の実行](/help/analysis-workspace/perform-adv-analysis.md)を参照してください。 |

## クイックスタートガイド

[データ取り込み](../data-ingestion/data-ingestion.md)の節では、上記のワークフローに関するクイックスタートガイドを提供しています。これらのクイックスタートガイドでは、Adobe Experience Platform で様々なソース（Adobe Analytics など）のデータを取り込んで Customer Journey Analytics で使用する方法について説明しています。
