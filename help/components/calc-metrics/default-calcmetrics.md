---
description: Adobeでは、使用可能な様々な計算指標を提供します。 このページでは、これらの指標とその使用目的を一覧表示します。
title: デフォルトの計算指標
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 28%

---

# デフォルトの計算指標

Customer Journey Analyticsでは、最も一般的なユースケースに対応するために、次の計算指標を提供しています。

| 計算指標名 | 説明 | 数式 |
|---------|----------|---------|
| セッション開始率 | セッションの最初のイベントでディメンション項目が発生した割合。<p>この計算指標は、`[Session Starts]`[ 標準コンポーネント ](/help/data-views/component-reference.md) を [ データビュー ](/help/data-views/create-dataview.md) に含めると、Workspaceに自動的に追加されます。</p> | `[Session Starts] / [Sessions]` |
| ユーザー別滞在時間 | 特定のディメンション項目に対して人が費やした平均時間。<p>この計算指標は、`[Time Spent (seconds)]`[ 標準コンポーネント ](/help/data-views/component-reference.md) を [ データビュー ](/help/data-views/create-dataview.md) に含めると、Workspaceに自動的に追加されます。</p> | `[Time Spent (seconds)] / [Users]` |
| 1 人あたりのセッション数 | 1 人あたりの平均セッション数。 | `[Sessions] / [Users]` |
| セッションごとに費やされた時間 | 特定のディメンション項目でセッションごとに人が費やした平均時間。<p>この計算指標は、`[Time Spent (seconds)]`[ 標準コンポーネント ](/help/data-views/component-reference.md) を [ データビュー ](/help/data-views/create-dataview.md) に含めると、Workspaceに自動的に追加されます。</p> | `[Time Spent (seconds)] / [Sessions]` |
| セッション終了率 | セッションの最後のイベントでディメンション項目が発生した割合。 <p>この計算指標は、`[Session Ends]`[ 標準コンポーネント ](/help/data-views/component-reference.md) を [ データビュー ](/help/data-views/create-dataview.md) に含めると、Workspaceに自動的に追加されます。</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
