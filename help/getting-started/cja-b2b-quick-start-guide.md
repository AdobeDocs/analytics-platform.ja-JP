---
title: Customer Journey Analytics B2B のクイックスタートガイド
description: Customer Journey Analytics B2B Edition のクイックスタートガイド。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
TQID: https://experienceleague.adobe.com/SjixkRCOmeUYuhZCVO7-7tLHalpnXO6QCVE1BiG9h2E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 431
ht-degree: 88%

---

# B2B Edition のクイックスタートガイド

Customer Journey Analytics B2B Edition を実装するには、まず B2B に固有の概念や機能を理解しておく必要があります。 また、Customer Journey Analytics を実装するための従来のワークフローについても理解しておく必要があります。

このドキュメントでは、Customer Journey Analytics の実装に固有のワークフローに焦点を当てます。

## 前提条件

Customer Journey Analytics B2B Edition を実装する場合、次の前提条件が適用されます。

* Customer Journey Analytics で管理タスクを実行するために必要な[アクセス制御と権限](/help/technotes/access-control.md)を持っている。
* Customer Journey Analytics B2B Edition のアドオンパッケージを購入している。


## ワークフロー

| タスク | 詳細 |
| --- | --- |
| **手順 1：B2B データの Experience Platform への取り込み** | この手順は Experience Platform で実行されますが、いくつかのサブ手順が必要です。<ul><li>**手順 1a：データスキーマの準備**：[Adobe エクスペリエンスデータモデル（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用して B2B データを標準化し、B2B データ管理の[スキーマを定義](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/schemas/b2b)します。</li><li>**手順 1b：スキーマに基づいたデータセットの作成**：Platform 内のデータは、アカウントデータ、商談データ、購買グループデータ、キャンペーンデータ、マーケティングリストデータ、メールデータセット、CRM データセット、POS データセットなどのデータセットで構成されます。 各データセットは、データのスキーマとバッチで構成されます。 [Experience Platform でデータセットを作成](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ja)できます。</li><li>**手順 1c：Experience Platform へのデータの取り込み**：[いくつかのオプションがあります](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/home)。</li></ul> |
| **手順 2：プラットフォームデータセットと Customer Journey Analytics 間の接続の作成** | 接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。 Experience Platform データセットに関するレポートを作成するには、まず Experience Platform とワークスペースのデータセット間で接続を確立する必要があります。 B2B Edition との接続を設定する際には、追加のオプションがあります。 <br>詳しくは、[接続の作成または編集](/help/connections/create-connection.md)を参照してください。 |
| **手順 3：データビューの作成** | データビューとは、データが&#x200B;*フィルタリングされている*&#x200B;ビューです。 訪問のタイムアウト、アトリビューションなどの様々な設定を使用して、同じ接続に対して異なるデータビューを作成します。 1 つのデータセットに対して複数のデータビューを作成できます。 B2B editionを使用している場合は、データビューを設定する際に、さらにオプションがあります。<br>詳しくは、[&#x200B; データビューの作成](/help/data-views/create-dataview.md)を参照してください。 |
| **手順 4：ワークスペースでのクロスチャネルデータのレポート** | 接続とデータビューを作成したら、Analysis Workspaceの機能と柔軟性を使用して、取り込んだB2B データを分析します。<br>詳しくは、[基本分析](/help/analysis-workspace/perform-basic-analysis.md)および[高度な分析](/help/analysis-workspace/perform-adv-analysis.md)を実行するを参照してください。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->