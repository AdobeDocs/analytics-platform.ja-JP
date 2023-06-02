---
description: Adobeは、使用できる様々な計算指標を提供します。 このページでは、これらの指標とその意図された用途を示します。
title: デフォルトの計算指標
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 5e69b1aceb767343882b9cc85c0011bb1593f4af
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 25%

---

# デフォルトの計算指標

Customer Journey Analyticsでは、最も一般的な使用例を示す次の計算指標が提供されます。

| 計算指標名 | 説明 | 数式 |
|---------|----------|---------|
| セッション開始率 | セッションの最初のイベントで発生した任意のディメンション項目の割合。<p>この計算指標は、 `[Session Starts]` [標準コンポーネント](/help/data-views/component-reference.md) の [データビュー](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| 個人別滞在時間 | 特定のディメンション項目に対して人が費やした平均時間。<p>この計算指標は、 `[Time Spent (seconds)]` [標準コンポーネント](/help/data-views/component-reference.md) の [データビュー](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| 1 人あたりのセッション数 | 1 人あたりのセッションの平均数。 | `[Sessions] / [Users]` |
| セッションごとに費やされた時間 | 特定のディメンション項目でセッションごとに人が費やした平均時間。<p>この計算指標は、 `[Time Spent (seconds)]` [標準コンポーネント](/help/data-views/component-reference.md) の [データビュー](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| セッション終了率 | セッションの最後のイベントで発生した任意のディメンション項目の割合。 <p>この計算指標は、 `[Session Ends]` [標準コンポーネント](/help/data-views/component-reference.md) の [データビュー](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
