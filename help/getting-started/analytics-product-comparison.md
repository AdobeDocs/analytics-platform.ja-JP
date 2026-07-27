---
title: Customer Journey Analyticsと製品の比較
description: Analysis Workspace、Report Builder、テーブルの書き出し、データフィード、API、MCPなどのジャーニー分析レポートツールと書き出しツールのお客様の属性を比較します。
keywords: clickstream；データフィード；データフィード；製品比較；Analysis Workspace;Report Builder；テーブルの書き出し
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 53%

---


# Adobe Analyticsと製品の比較

このページでは、主要な属性に関するCustomer Journey Analyticsのレポートツールとエクスポートツールを比較し、分析やデータ書き出しのニーズに適したツールを選択するのに役立ちます。

| 製品名とヘルプリンク | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md) | [データフィード](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP |
|---|---|---|---|---|---|---|
| **アクセス方法** | ブラウザー | Microsoft Excel | ブラウザー | ブラウザーで設定 | RESTful API ツール | MCP対応ツール |
| **データの精度** | 集計 | 集計 | 集計 | イベント | 集計 | 集計 |
| **Experience Cloud ID（ECID）が使用可能** | いいえ | いいえ | いいえ | はい | いいえ | いいえ |
| **タイムスタンプが使用可能** | いいえ | いいえ | いいえ | はい | いいえ | いいえ |
| **処理レベル** | 完全処理 | 完全処理 | 完全処理 | 完全処理 | 完全処理 | 完全処理 |
| **ボットフィルターデータが含まれています** | いいえ | いいえ | いいえ | いいえ | いいえ | いいえ |
| **表示される行数制限（ページ分割前）** | 400 | 50,000 | 階層に応じて、300 万行、3,000 万行、1 億 5,000 万行、3 億行の制限 | 階層に応じて、300 万行、3,000 万行、1 億 5,000 万行、3 億行の制限 | 50,000 | 50,000 |
| **複数のデータビュー** | はい。プロジェクトには複数のデータビューのデータを含めることができます | はい。プロジェクトには複数のデータビューのデータを含めることができます | いいえ。書き出しには、1つのデータビューのデータのみを含めることができます | いいえ。書き出しには、1つのデータビューのデータのみを含めることができます | はい | はい |
| **分類の数** | 制限なし | ～ 2 | 制限なし | 制限なし | 制限なし（複数のクエリに対して実行） | 制限なし |
| **セグメント化** <br> [詳細情報](/help/components/segments/seg-overview.md) | はい | はい | はい | ○（[制限あり](/help/components/exports/cja-data-feeds/df-segmentation.md)） | はい | はい |
| **計算指標** <br> [詳細情報](/help/components/calc-metrics/calc-metr-overview.md) | はい | はい | ○（[制限あり](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support)） | いいえ | はい | はい |
| **派生フィールド** <br> [詳細情報](/help/data-views/derived-fields/derived-fields.md) | はい | はい | はい | はい | はい | はい |
| **コホート分析** | [○](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | いいえ | いいえ | いいえ | いいえ | いいえ |
| **属性** <br> [詳細情報](/help/analysis-workspace/attribution/overview.md) | はい | 制限あり | いいえ | いいえ | はい | はい |
| **キュレーション** <br> [詳細情報](/help/analysis-workspace/curate-share/curate.md) | はい、でプロジェクトとデータビューで | いいえ | いいえ | はい、データビュー内で | はい、データビュー内で | はい、データビュー内で |
| **プロジェクトの共有** <br> [詳細情報](/help/analysis-workspace/curate-share/share-projects.md) | はい（プロジェクトロールあり） | いいえ | いいえ | いいえ | いいえ | いいえ |
| **配信予定** | はい | はい | はい | はい | いいえ | いいえ |
| **配信先** | 電子メール | メール | Amazon S3、Azure RBAC、Azure SAS、GCP | Amazon S3、Azure RBAC、Azure SAS、GCP | — | — |
| **データビューのレポート時処理** <br> [詳細情報](/help/data-views/data-views.md) | はい | はい | いいえ | いいえ | はい | はい |

{style="table-layout:auto"}
