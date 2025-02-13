---
description: Adobeには、使用可能な様々な計算指標が用意されています。 このページでは、これらの指標とその使用目的を一覧表示します。
title: 計算指標テンプレート
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d13f980d1fbae3f608bf64587f59dc22c3fac9ce
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 6%

---

# 計算指標テンプレート

Customer Journey Analyticsは、最も一般的なユースケースに対応するために、次の計算指標テンプレートを提供します。 これらのAdobeで定義された計算指標は、小さな ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) ロゴで識別されます。 これらの指標をすばやくフィルタリングするには、{ コンポーネントフィルター ]**の ![ ラベル ](/help/assets/icons/Label.svg) [**[!UICONTROL  Adobe テンプレート ](/help/components/overview.md#filter) を選択します。

| 計算指標名 | 説明 <br/> 数式 |
|---------|----------|
| **[!UICONTROL セッション開始率]** | セッションの最初のイベントでディメンション項目が発生した割合。<p>この計算指標は、[!UICONTROL  データビュー ](/help/data-views/create-dataview.md) に [ セッション開始 ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **セッション開始** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **セッション** **）** |
| **[!UICONTROL 1 人あたりの滞在時間]** | 特定のディメンション項目に対して人が費やした平均時間。<p>この計算指標は、「[ データビュー ](/help/data-views/create-dataview.md) に [!UICONTROL  滞在時間（秒） ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。 フィルター「セッションの最後のイベントを除外」が人物指標に適用されます。 フィルターでは、データセット内の各セッションの最後のイベントが除外されます。 この除外は、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析するのに役立ちます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **滞在時間（秒）** ![ 除算 ](/help/assets/icons/Divide.svg) ![ セグメント化 ](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![ イベント ](/help/assets/icons/Event.svg) **人物））** |
| **[!UICONTROL セッション/人]** | 1 人あたりの平均セッション数。<p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **セッション** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **人物** **）** |
| **[!UICONTROL セッションあたりの滞在時間]** | 特定のディメンション項目でセッションごとに人が費やした平均時間。<p>この計算指標は、「[ データビュー ](/help/data-views/create-dataview.md) に [!UICONTROL  滞在時間（秒） ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。 フィルター「セッションの最後のイベントを除外」がセッション指標に適用されます。 フィルターでは、データセット内の各セッションの最後のイベントが除外されます。 この除外は、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析するのに役立ちます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **滞在時間（秒）** ![ 除算 ](/help/assets/icons/Divide.svg) ![ セグメント化 ](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![ イベント ](/help/assets/icons/Event.svg) **セッション））** |
| **[!UICONTROL セッション終了率]** | セッションの最後のイベントでディメンション項目が発生した割合。 <p>この計算指標は、[!UICONTROL  データビュー ](/help/data-views/create-dataview.md) に [ セッション終了 ][ 標準コンポーネント ](/help/data-views/component-reference.md) を含めると、Workspaceに自動的に追加されます。</p>概要：**（** ![ イベント ](/help/assets/icons/Event.svg) **セッション終了** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **セッション** **）** |
| **[!UICONTROL Web セッション]** | Web サイトで発生したセッション数。 |
| **[!UICONTROL 調査修了率]** | ユーザーが開始後にアンケートを完了した割合。 |
| **[!UICONTROL マルチチャネルセッションレート]** | 単一のチャネルのみを含むセッションと比較した、複数のチャネル（web トラフィックやモバイルトラフィックなど）を含む発生したセッションの割合。 |
| **[!UICONTROL マルチチャネルユーザーレート]** | 単一のチャネルにのみ参加した人と比較した、複数のチャネルに参加した人の割合。 |
| **[!UICONTROL モバイルアプリセッション]** | モバイルアプリで発生したセッションの数。 |
| **[!UICONTROL Web+アプリのクロスチャネルセッション]** | Web トラフィックとモバイルトラフィックの両方を含む、発生したセッションの数。 |
| **[!UICONTROL 通話コスト]** | コールセンターコールの合計コスト。<!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL 平均呼び出し時間]** | コールセンターに対して行われた呼び出しの平均時間。 |
| **[!UICONTROL 呼び出しあたりの平均コスト]** | コールセンターへの通話の平均コスト。 |
| **[!UICONTROL 平均問い合わせ調査スコア]** | コールセンターへの通話に関する平均調査スコア。 |

{style="table-layout:auto"}
