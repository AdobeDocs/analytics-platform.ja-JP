---
title: スコープコンポーネント設定
description: 総母集団レポートに対するコンポーネントのスコープを設定します。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 18%
---

# 範囲コンポーネント設定 {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="範囲"
>abstract="レポートで使用される際のコンポーネントの範囲を決定します。 イベントベース、プロファイルベース、合計ベースのいずれかを選択できます。"

指標コンポーネントの範囲によって、レポートでのコンポーネントの使用方法が決まります。

| 範囲 | 説明 |
|---|---|
| イベントベース | 指標コンポーネントの範囲は、イベントベースです。 |
| プロファイルベース | 指標コンポーネントの範囲は、プロファイルベースです。 コンポーネントがレポートで使用される場合、指標は、パネルに適用された日付範囲に関係なく、プロファイルデータから母集団を返します。 日付フィルターと日付範囲の比較は、この指標のレポートには影響しません。 |
| 合計ベース | 指標コンポーネントの範囲は、プロファイルとイベントベースです。 コンポーネントがレポートで使用される場合、指標は、パネルに適用された日付範囲に関係なく、プロファイルデータとイベントデータから母集団を返します。 日付フィルターと日付範囲の比較は、この指標のレポートには影響しません。 |

