---
description: アドビには、使用可能な様々な計算指標が用意されています。このページでは、これらの指標とその使用目的を一覧表示します。
title: 計算指標テンプレート
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 83%

---

# 計算指標テンプレート

Customer Journey Analyticsは、最も一般的なユースケースに対応するために、次の計算指標テンプレートを提供します。 これらのAdobeで定義された計算指標は、小さな ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) ロゴで識別されます。 これらの指標をすばやくフィルタリングするには、&lbrace; コンポーネントフィルター ![&#x200B; の &#x200B;](/help/assets/icons/Label.svg) ラベル **&#x200B;**&#x200B;[Adobe テンプレート &#x200B;](/help/components/overview.md#filter) を選択します。

| 計算指標名 | 説明<br/>数式 |
|---------|----------|
| **[!UICONTROL セッション開始率]** | セッションの最初のイベントでディメンション項目が発生した割合。<p>この計算指標は、[データビュー](/help/data-views/create-dataview.md)に[!UICONTROL セッション開始] [標準コンポーネント](/help/data-views/component-reference.md)を含めると、Workspace に自動的に追加されます。</p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **セッション開始** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **セッション** **）** |
| **[!UICONTROL ユーザー別滞在時間]** | 特定のディメンション項目に対して人が費やした平均時間。<p>この計算指標は、[データビュー](/help/data-views/create-dataview.md)に[!UICONTROL 滞在時間（秒）] [標準コンポーネント](/help/data-views/component-reference.md)を含めると、Workspace に自動的に追加されます。「セッションの最後のイベントを除外」セグメントは、人物指標に適用されます。 セグメントからは、データセット内の各セッションの最後のイベントが除外されます。 この除外により、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析できます。</p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **滞在時間（秒）** ![除算](/help/assets/icons/Divide.svg) ![セグメント化](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![イベント](/help/assets/icons/Event.svg) **人物））** |
| **[!UICONTROL 1 人あたりのセッション数]** | 1 人あたりの平均セッション数。<p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **セッション** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **人物** **）** |
| **[!UICONTROL セッションごとの滞在時間]** | 特定のディメンション項目でセッションごとに人が費やした平均時間。<p>この計算指標は、[データビュー](/help/data-views/create-dataview.md)に[!UICONTROL 滞在時間（秒）] [標準コンポーネント](/help/data-views/component-reference.md)を含めると、Workspace に自動的に追加されます。「セッションの最後のイベントを除外」セグメントは、セッション指標に適用されます。 セグメントからは、データセット内の各セッションの最後のイベントが除外されます。 この除外により、最終的なアクション自体を除外しながら、購入やフォーム送信などのイベントやアクションに至るユーザーの行動を分析できます。</p>概要：**（** ![イベント](/help/assets/icons/Event.svg) **滞在時間（秒）** ![除算](/help/assets/icons/Divide.svg) ![セグメント化](/help/assets/icons/Segmentation.svg) **セッションの最後のイベントを除外（** ![イベント](/help/assets/icons/Event.svg) **セッション））** |
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
