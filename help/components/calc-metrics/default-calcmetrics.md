---
description: Adobeでは、使用可能な様々な計算指標を提供します。 このページでは、これらの指標とその使用目的を一覧表示します。
title: デフォルトの計算指標
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a507417c945f827ebb8bc92f7b5f54a9c4e6faa0
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 9%

---

# デフォルトの計算指標

Customer Journey Analyticsでは、最も一般的なユースケースに対応するために、次のデフォルトの計算指標を提供しています。 これらのAdobe定義のデフォルト計算指標は、小さな ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) ロゴで識別されます。 これらの指標をすばやくフィルタリングするには、{ コンポーネントフィルター ]**の ![ ラベル ](/help/assets/icons/Label.svg) {2[Adobeテンプレート ](/help/components/overview.md#filter) を選択します。**[!UICONTROL 

| 計算指標名 | 説明 <br/> 数式 |
|---------|----------|
| **[!UICONTROL セッション開始率]** | セッションの最初のイベントでディメンション項目が発生した割合。<p>この計算指標は、[!UICONTROL  データビュー ](/help/data-views/create-dataview.md) に [ セッション開始 ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **セッション開始** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **セッション** **）** |
| **[!UICONTROL 1 人あたりの滞在時間]** | 特定のディメンション項目に対して人が費やした平均時間。<p>この計算指標は、「[ データビュー ](/help/data-views/create-dataview.md) に [!UICONTROL  滞在時間（秒） ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。 フィルター「セッションの最後のイベントを除外」が人物指標に適用されます。 フィルターでは、データセット内の各セッションの最後のイベントが除外されます。 この除外は、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析するのに役立ちます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **滞在時間（秒）** ![ 除算 ](/help/assets/icons/Divide.svg) ![ セグメント化 ](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![ イベント ](/help/assets/icons/Event.svg) **人物））** |
| **[!UICONTROL セッション/人]** | 1 人あたりの平均セッション数。<p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **セッション** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **人物** **）** |
| **[!UICONTROL セッションあたりの滞在時間]** | 特定のディメンション項目でセッションごとに人が費やした平均時間。<p>この計算指標は、「[ データビュー ](/help/data-views/create-dataview.md) に [!UICONTROL  滞在時間（秒） ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。 フィルター「セッションの最後のイベントを除外」がセッション指標に適用されます。 フィルターでは、データセット内の各セッションの最後のイベントが除外されます。 この除外は、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析するのに役立ちます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **滞在時間（秒）** ![ 除算 ](/help/assets/icons/Divide.svg) ![ セグメント化 ](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![ イベント ](/help/assets/icons/Event.svg) **セッション））** |
| **[!UICONTROL セッション終了率]** | セッションの最後のイベントでディメンション項目が発生した割合。 <p>この計算指標は、[!UICONTROL  データビュー ](/help/data-views/create-dataview.md) に [ セッション終了 ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **セッション終了** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **セッション** **）** |

{style="table-layout:auto"}
