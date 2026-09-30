---
title: Google Analytics データのストリーミングの設定
description: Google データレイヤーを Adobe Experience Platform に送信するための実装の設定方法について説明します
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T09:49:39.181Z'
TQID: 'https://experienceleague.adobe.com/xav7bGdbGLjYXm70GJBSxnDMfNDZpYp5qij1IqkaZSY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
    internal-label: Analytics integration
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 90%
---
# Google Analytics データのストリーミングの設定

このページでは、ライブ Google Analytics のデータを Adobe Experience Platform に取り込み、Customer Journey Analytics 内のデータビューでそのデータセットを参照する方法について重点的に説明します。 このページの手順を、履歴データを含むデータセットの生成方法を説明した [Google Analytics 履歴データの Adobe Experience Platform への取り込み](backfill.md)ページと組み合わせることができます。 ストリーミングデータセットとバックフィルデータセットを組み合わせることで、Customer Journey Analytics で過去と現在のデータをシームレスに確認できます。

データ収集を設定するには、次の手順を実行します。

1. [Adobe Experience Platform のタグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)を実装する。 基本的な実装環境のインストールおよび導入について詳しくは、[クイックスタートガイド](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=ja)を参照してください。
1. [Google データレイヤー拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=ja)をインストールする。 この拡張機能は、Web SDK 拡張機能をインストールする代替手段として機能し、Google データレイヤーに特化しています。
1. Adobe Experience Platform データ収集に[データストリームを作成](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja)する。 データを Adobe Experience Platform に送信するようデータストリームを設定します。 現時点では、ここで各 Google データレイヤーオブジェクトを該当する XDM フィールドにマッピングする必要があります。 アドビでは今後、このマッピングワークフローを簡略化する予定です。

サイトに目的のタグを実装して公開したら、[接続の作成](/help/connections/create-connection.md)に進み、[ データビューの作成](/help/data-views/create-dataview.md)に進むことができます。
