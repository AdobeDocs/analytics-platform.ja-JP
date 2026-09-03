---
title: Customer Journey Analyticsと製品の比較
description: Analysis Workspace、Report Builder、テーブルの書き出し、データフィード、API、MCPなどのジャーニー分析レポートツールと書き出しツールのお客様の属性を比較します。
keywords: clickstream；データフィード；データフィード；製品比較；Analysis Workspace;Report Builder；テーブルの書き出し
feature: Components
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Adobe Analyticsと製品の比較

このページでは、主要な属性に関するCustomer Journey Analyticsのレポートツールとエクスポートツールを比較し、分析やデータ書き出しのニーズに適したツールを選択するのに役立ちます。

| 製品名とヘルプリンク | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md) | [データフィード](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP | BI 拡張機能 | 同僚 |
|---|---|---|---|---|---|---|---|---|
| **アクセス方法** | ブラウザー | Microsoft Excel | ブラウザー | ブラウザーで設定 | RESTful API ツール | MCP対応ツール | BI ツール | MCP対応ツール |
| **データの精度** | 集計 | 集計 | 集計 | イベント | 集計 | 集計 | 集計 | 集計 |
| **Experience Cloud ID（ECID）が使用可能** | いいえ | いいえ | いいえ | はい | いいえ | いいえ | いいえ | いいえ |
| **タイムスタンプが使用可能** | いいえ | いいえ | いいえ | はい | いいえ | いいえ | いいえ | いいえ |
| **処理レベル** | 完全処理 | 完全に処理され、個別のリアルタイムレポートが表示されます | 完全処理 | 完全処理 | 完全処理 | 完全処理 | 完全処理 | 完全処理 |
| **ボットフィルタリングが適用される場所** | [ データストリーム ](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/bot-detection)内および/または[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | [ データストリーム ](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/bot-detection)内および/または[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | [ データストリーム ](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/bot-detection)内および/または[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | [ データストリーム ](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/bot-detection)内および/または[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 |  |  | [ データストリーム ](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/bot-detection)内および/または[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | |
| **表示される行数制限（ページ分割前）** | 400 | 50,000 | 階層に応じて、300 万行、3,000 万行、1 億 5,000 万行、3 億行の制限 | 層に依存 | 50,000 | 50,000 | 50,000 | 50,000 |
| **複数のデータビュー** | はい。プロジェクトには複数のデータビューのデータを含めることができます | はい。プロジェクトには複数のデータビューのデータを含めることができます | いいえ。書き出しには、1つのデータビューのデータのみを含めることができます | いいえ。書き出しには、1つのデータビューのデータのみを含めることができます | いいえ。各クエリは1つのデータビューのみを参照できます | いいえ。各クエリは1つのデータビューのみを参照できます | いいえ。各クエリは1つのデータビューのみを参照できます | はい、ユーザーからプロンプトが表示された場合 |
| **ディメンション列の数** | 最大5 | ? | 最大10 | 制限なし | 最大5 | ? | ? | ? |
| **指標の列数** | ? | ? | 最大10 | 制限なし | ? | ? | ? | ? |
| **セグメント化** <br> [詳細情報](/help/components/segments/seg-overview.md) | はい | はい | はい | ○（[制限あり](/help/components/exports/cja-data-feeds/df-segmentation.md)） | はい | はい | はい | はい |
| **計算指標** <br> [詳細情報](/help/components/calc-metrics/calc-metr-overview.md) | はい | はい | ○（[制限あり](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support)） | いいえ | はい | はい | はい | はい |
| **派生フィールド** <br> [詳細情報](/help/data-views/derived-fields/derived-fields.md) | はい | はい | はい | はい | はい | はい | はい | はい |
| **属性** <br> [詳細情報](/help/analysis-workspace/attribution/overview.md) | はい | 制限あり | ○（[制限あり](/help/analysis-workspace/export/export-cloud.md#attribution-behavior)） | いいえ | はい | はい | はい | はい |
| **配信予定** | はい | はい | はい | はい | — | — | — | — |
| **配信先** | 電子メール | メール | Amazon S3、Azure RBAC、Azure SAS、GCP | Amazon S3、Azure RBAC、Azure SAS、GCP | — | — | — | — |

{style="table-layout:auto"}
