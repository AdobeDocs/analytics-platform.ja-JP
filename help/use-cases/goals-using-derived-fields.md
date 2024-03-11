---
title: 派生フィールドを使用した目標のレポート
description: 派生フィールドを使用して、Workspace プロジェクトの目標（ターゲット）をレポートする方法を説明します。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 2%

---

# 派生フィールドを使用した目標のレポート

この使用例では、派生フィールドの機能を使用して特定のディメンションの目標を設定し、Workspace プロジェクトでこれらの目標を使用する方法を説明します。

派生フィールドについて詳しくない場合は、 [チュートリアル](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html) および [ドキュメント](../data-views/derived-fields/derived-fields.md) を参照してください。


## 目標の定義

目標を定義するには、新しい派生フィールドを作成します。派生フィールドの定義で既にルールから生成された値を使用して、カスタムの数値を直接または間接的に明示的に設定します。


### 月別ギフト券注文目標

2023 年 7 月～ 2023 年 10 月の 4 か月間、ギフト券の注文の目標を明示的に設定したい場合。 次に手順を示します。

1. 名前を持つ新しい派生フィールドを作成します `Monthly Gift Certificate Orders Goal (Incremental)`.

1. 各月に対して CASE WHEN ルールを使用し、 **[!UICONTROL カスタム数値]**. 以下の「月別製品目標」のルールを参照してください。

   ![月別製品目標](assets/goals-derived-field-product-goals-1.png)


### マーケティングチャネルの売上高目標

各マーケティングチャネルに対して月別の売上高目標を設定する必要がある。 次に手順を示します。

1. 新しい派生フィールドを作成する場合は、 [マーケティングチャネル機能テンプレート](/help/data-views/derived-fields/derived-fields.md#marketing-channels) という名前の `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. URL PARSE ルールと CASE WHEN ルールの組み合わせに基づいて、各マーケティングチャネルを正しく識別するすべてのルールを定義します。 次に例を示します。

   ![マーケティングチャネル派生フィールドのルールの定義](assets/goals-derived-field-marketing-channel-1.png)

1. 最終的な「CASE WHEN」ルールで、 **[!UICONTROL カスタム数値]**. 詳しくは、 [!DNL Monthly Goal] ルールを下に示します。

   ![月別目標](assets/goals-derived-field-marketing-channel-2.png)



## 目標の使用

Workspace プロジェクトで目標を使用するには、計算指標機能を使用して、派生フィールドを元の静的値に「正規化」し直します。 目標を定義する派生フィールドに設定した静的値はイベントごとに増分されるので、この正規化が必要です。

### 月別ギフト券注文目標

1. という名前の計算指標フィールドを作成します。 `Monthly Gift Certificate Orders Goal`（定義： ）

   ![注文の目標](assets/calculated-metric-ordersgoals.png)

1. 例えば、追加の計算フィールドを作成できます。 `% of Monthly Gift Certificate Orders Goal`目標に対する実際の進捗を表示するには、次のように指定します。

   ![注文の目標の割合](assets/calculated-metric-ordersgoalspercent.png)

これらの計算指標を使用して、フリーフォームテーブルおよびビジュアライゼーションでの進行状況をレポートできます。 次に例を示します。

![マーケティング売上高目標を示すフリーフォームテーブル](assets/freeform-table-product-order-goals.png)


### マーケティングチャネルの売上高目標

1. という名前の計算指標フィールドを作成します。 `Marketing Channel Revenue Goal`（定義： ）

   ![収益目標](assets/calculated-metric-revenuegoals.png)

1. 例えば、追加の計算フィールドを作成できます。 `% of Marketing Channel Revenue Goal`目標に対する実際の進捗を表示するには、次のように指定します。

   ![収益目標の割合](assets/calculated-metric-revenuegoalspercent.png)

これらの計算指標を使用して、フリーフォームテーブルおよびビジュアライゼーションでの進行状況をレポートできます。 次に例を示します。

![マーケティング売上高目標を示すフリーフォームテーブル](assets/freeform-table-marketing-channel-revenue-goals.png)
