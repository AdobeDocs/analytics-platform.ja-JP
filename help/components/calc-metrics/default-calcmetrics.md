---
description: アドビでは、ユーザーが使用できる様々な計算指標を提供しています。 このページでは、これらの指標とその使用目的を一覧表示します。
title: 計算指標テンプレート
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
TQID: https://experienceleague.adobe.com/-jngIXgXeFZZkfL5jSHLuX8ZmcWU5rIfLqb26ovn6QY
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 83%

---

# 計算指標テンプレート

Customer Journey Analyticsには、最も一般的なユースケースをカバーする以下の計算指標テンプレートが用意されています。 これらのAdobe定義の計算指標は、小さな![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) ロゴによって識別されます。 これらの指標をすばやくフィルターするには、[ コンポーネントフィルター](/help/components/overview.md#filter)で![ ラベル ](/help/assets/icons/Label.svg) **[!UICONTROL Adobe テンプレート]**&#x200B;を選択します。

| 計算指標名 | 説明<br/>数式 |
|---------|----------|
| **[!UICONTROL セッション開始率]** | セッションの最初のイベントでディメンション項目が発生した割合。<p>この計算指標は、[データビュー](/help/data-views/create-dataview.md)に[!UICONTROL セッション開始] [標準コンポーネント](/help/data-views/component-reference.md)を含めると、Workspace に自動的に追加されます。</p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **セッション開始** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **セッション** **）** |
| **[!UICONTROL ユーザー別滞在時間]** | 特定のディメンション項目に対して人が費やした平均時間。<p>この計算指標は、[データビュー](/help/data-views/create-dataview.md)に[!UICONTROL 滞在時間（秒）] [標準コンポーネント](/help/data-views/component-reference.md)を含めると、Workspace に自動的に追加されます。 セグメント「セッションの最後のイベントを除外」が「人物」指標に適用されます。 セグメントは、データセット内の各セッションの最後のイベントを除外します。 この除外により、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析できます。</p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **滞在時間（秒）** ![除算](/help/assets/icons/Divide.svg) ![セグメント化](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![イベント](/help/assets/icons/Event.svg) **人物））** |
| **[!UICONTROL 1 人あたりのセッション数]** | 1 人あたりの平均セッション数。<p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **セッション** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **人物** **）** |
| **[!UICONTROL セッションごとの滞在時間]** | 特定のディメンション項目でセッションごとに人が費やした平均時間。<p>この計算指標は、[データビュー](/help/data-views/create-dataview.md)に[!UICONTROL 滞在時間（秒）] [標準コンポーネント](/help/data-views/component-reference.md)を含めると、Workspace に自動的に追加されます。 セグメント「セッションの最後のイベントを除外」がセッション指標に適用されます。 セグメントは、データセット内の各セッションの最後のイベントを除外します。 この除外により、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析できます。</p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **滞在時間（秒）** ![除算](/help/assets/icons/Divide.svg) ![セグメント化](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![イベント](/help/assets/icons/Event.svg) **セッション））** |
| **[!UICONTROL セッション終了率]** | セッションの最後のイベントでディメンション項目が発生した割合。 <p>この計算指標は、[データビュー](/help/data-views/create-dataview.md)に[!UICONTROL セッション終了] [標準コンポーネント](/help/data-views/component-reference.md)を含めると、Workspace に自動的に追加されます。</p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **セッション終了** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **セッション** **）** |
| **[!UICONTROL Web セッション]** | Web サイトで発生したセッション数。 |
| **[!UICONTROL 調査の完了率]** | 調査を開始した後、その調査を完了した人物の割合。 |
| **[!UICONTROL マルチチャネルセッション率]** | 1 つのチャネルのみを含むセッションと比較した、複数のチャネル (web トラフィックやモバイルトラフィックなど) を含む、発生したセッションの割合。 |
| **[!UICONTROL マルチチャネルユーザー率]** | 1 つのチャネルにのみ参加した人物と、複数のチャネルに参加した人物の比率。 |
| **[!UICONTROL モバイルアプリセッション]** | モバイルアプリで発生したセッション数。 |
| **[!UICONTROL Web + アプリクロスチャネルセッション]** | Web トラフィックとモバイルトラフィックの両方を含む、発生したセッション数 |
| **[!UICONTROL 通話コスト]** | コールセンターコールの合計コスト。<!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL 平均呼び出し時間]** | コールセンターに対して行われた呼び出しの平均時間。 |
| **[!UICONTROL 通話あたりの平均コスト]** | コールセンターへの平均通話コスト。 |
| **[!UICONTROL 平均通話調査スコア]** | コールセンターへの通話に関する平均調査スコア。 |

{style="table-layout:auto"}
