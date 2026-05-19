---
title: Customer Journey AnalyticsでQuantum Metric ヒートマップを使用する
description: Quantum Metric Heatmap データを使用して、ページレベルのエンゲージメントをより深く理解し、消費者の行動にもとづいてページを最適化します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
autotag-review: '2026-05-19T09:50:41.180Z'
TQID: 'https://experienceleague.adobe.com/EvPGghY3E7eoiJb6TcWnaOhneS6oQJj4bcwU3K2v3Ng'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 1%

---

# Customer Journey AnalyticsでQuantum Metric ヒートマップを使用する

量子指標のヒートマッピングをCJAデータにリンクすることで、ページレベルのエンゲージメントをより深く理解し、消費者の行動にもとづいてページを最適化できます。 Workspaceを使用すると、消費者のユーザーフローを把握し、消費者があるページから次のページに至るまでの経路を確認できます。 ハイパーリンクされたページ URLをクリックすると、ユーザーがコンテンツにどのように関与するかを視覚的にヒートマップできます。 Quantum Metric HeatmappingをCJAにリンクすることで、ページレベルのインタラクションをビジネス成果に関連付け、分析を次のレベルに引き上げることができます。

テーブルはそのセグメント内のすべてのセッションを返し、そのうちの1つをクリックしてQMでさらに詳しく調べることができます。  Quantum Metric セッションリプレイの詳細については、https://www.quantummetric.com/platform/session-replayを参照してください。

## 前提条件

Quantum Metricのヒートマップ機能にアクセスするには、Quantum Metricの&#x200B;**UX Ops** パッケージの使用権限が必要です。

## 手順1:Analysis Workspaceでのリンクの設定

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. Customer Journey Analyticsに移動し、上部メニューの&#x200B;**[!UICONTROL Workspace]**&#x200B;を選択します。
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)を作成します。
1. ページ URL ディメンションをWorkspace キャンバスにドラッグします。
1. ディメンション列ヘッダーを右クリックし、**[!UICONTROL すべてのディメンション項目のハイパーリンクを作成]**&#x200B;を選択します。
1. **[!UICONTROL カスタム URLを作成]**&#x200B;を選択します。
1. 次のURL構造を貼り付けます。

   ```
   $value?qm-visible=true
   ```

1. 「**[!UICONTROL 作成]**」をクリックします。
1. リンクの1つをテストして、Quantum Metric拡張機能が表示されているURLで開くかどうかを確認します。 これらのリンクは新しいタブで開くため、Workspace プロジェクトは開いたままになります。

![ ヒートマップ ](assets/heatmap.png)

## ステップ 2: Customer Journey Analytics内のリンクをクリックしてヒートマップを表示する

ヒートマッピングを調べたいページが見つかったら、それを目的のパネルに適用できます。 このテーブルは、Quantum Metricを使用して、ヒートマップ、スクロール深度、およびインタラクション用のキーゾーンを探索できるURLを返します。 詳しくは、[量子指標ヒートマップ製品の概要](https://www.quantummetric.com/platform/interaction-heatmaps)を参照してください。 また、Quantum Metric カスタマーサポート担当者にお問い合わせいただくか、[Quantum Metric カスタマーリクエストポータル ](https://community.quantummetric.com/s/public-support-page)からリクエストを送信することもできます。
