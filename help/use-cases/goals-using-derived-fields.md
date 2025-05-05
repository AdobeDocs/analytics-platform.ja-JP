---
title: 派生フィールドを使用した目標に関するレポート
description: 派生フィールドを使用して、Workspace プロジェクトの目標（ターゲット）に関するレポートを作成する方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 6%

---

# 派生フィールドを使用した目標に関するレポート

このユースケースでは、派生フィールドの機能を使用して特定のディメンションの目標を設定し、それらの目標をWorkspace プロジェクトで使用する方法を説明します。

派生フィールドについて詳しくない場合は、[ チュートリアル ](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=ja) および [ ドキュメント ](../data-views/derived-fields/derived-fields.md) を参照して概要を確認してください。


## 目標を定義

目標を定義するには、派生フィールド定義で以前にルールから生成された値を使用して、カスタム数値を直接または間接的に明示的に設定した新しい派生フィールドを作成します。


### 毎月のギフト券の注文数の目標

2023 年 7 月から 2023 年 10 月までの 4 か月間、ギフト券の注文の目標を明示的に設定します。 次に手順を示します。

1. `Monthly Gift Certificate Orders Goal (Incremental)` という名前の新しい派生フィールドを作成します。

1. 各月に静的な値を設定するには、CASE WHEN RULE を使用し、**[!UICONTROL カスタム数値]** を設定します。 以下の月間製品目標ルールを参照してください。

   ![ 月間の製品目標 ](assets/goals-derived-field-product-goals-1.png)


### マーケティングチャネルの収益目標

マーケティングチャネルごとに、毎月の売上高目標を設定する必要があります。 次に手順を示します。

1. [ マーケティングチャネル関数テンプレート ](/help/data-views/derived-fields/derived-fields.md#marketing-channels) を使用して、`Monthly Marketing Channel Revenue Goal (Incremental)` という名前の新しい派生フィールドを作成します。

1. URL の解析ルールと CASE WHEN ルールの組み合わせに基づいて各マーケティングチャネルを適切に識別するために、すべてのルールを定義します。 次に例を示します。

   ![ マーケティングチャネル派生フィールドのルールの定義 ](assets/goals-derived-field-marketing-channel-1.png)

1. **[!UICONTROL カスタム数値]** を設定して、最終的な CASE WHEN ルールの特定のマーケティングチャネルに対して、毎月の収益目標を表す静的値を明示的に設定します。 以下の [!DNL Monthly Goal] ルールを参照してください。

   ![ 月間の目標 ](assets/goals-derived-field-marketing-channel-2.png)



## 目標の使用

Workspace プロジェクトで目標を使用するには、計算指標機能を使用して、派生フィールドを元の静的な値に「正規化」します。 目標を定義する派生フィールドに設定した静的な値は、イベントごとに増分されるので、この正規化は必須です。

### 毎月のギフト券の注文数の目標

1. 次のように定義された、`Monthly Gift Certificate Orders Goal` という名前の計算指標フィールドを作成します。

   ![ 注文目標 ](assets/calculated-metric-ordersgoals.png)

1. 追加の計算フィールド（例：`% of Monthly Gift Certificate Orders Goal`）を作成して、目標に対する実際の進捗を示すことができます。例：

   ![ 注文目標の割合 ](assets/calculated-metric-ordersgoalspercent.png)

これらの計算指標を使用して、フリーフォームテーブルおよびビジュアライゼーションの進行状況をレポートできます。 次に例を示します。

![ マーケティング収益の目標を示すフリーフォームテーブル ](assets/freeform-table-product-order-goals.png)


### マーケティングチャネルの収益目標

1. 次のように定義された、`Marketing Channel Revenue Goal` という名前の計算指標フィールドを作成します。

   ![ 売上高目標 ](assets/calculated-metric-revenuegoals.png)

1. 追加の計算フィールド（例：`% of Marketing Channel Revenue Goal`）を作成して、目標に対する実際の進捗を示すことができます。例：

   ![ 売上高目標の割合 ](assets/calculated-metric-revenuegoalspercent.png)

これらの計算指標を使用して、フリーフォームテーブルおよびビジュアライゼーションの進行状況をレポートできます。 次に例を示します。

![ マーケティング収益の目標を示すフリーフォームテーブル ](assets/freeform-table-marketing-channel-revenue-goals.png)
