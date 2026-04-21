---
title: 派生フィールドを使用した目標に関するレポート
description: 派生フィールドを使用して、Workspace プロジェクトの目標（ターゲット）をレポートする方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 35d365dec8bc9afdfd55405dbcfa082280515b18
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 6%

---

# 派生フィールドを使用した目標に関するレポート

このユースケースでは、派生フィールドの力を使用して特定のディメンションの目標を設定し、これらの目標をWorkspace プロジェクトで使用する方法について説明します。

派生フィールドについて詳しくない場合は、[&#x200B; チュートリアル &#x200B;](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=ja)および[&#x200B; ドキュメント &#x200B;](/help/data-views/derived-fields/derived-fields.md)を参照して、概要を確認してください。


## 目標の定義

目標を定義するには、新しい派生フィールドを作成します。このフィールドでは、派生フィールド定義の早い段階のルールから得られる値を使用して、カスタム数値を直接または間接的に明示的に設定します。


### 毎月のギフト券の注文目標

2023年7月から2023年10月までの4か月間のギフト券の注文の目標を明示的に設定します。 次に手順を示します。

1. `Monthly Gift Certificate Orders Goal (Incremental)`という名前の新しい派生フィールドを作成します。

1. CASE WHEN ルールを使用して、毎月&#x200B;**[!UICONTROL カスタム数値]**&#x200B;を設定して静的値を設定します。 以下の月間製品目標ルールを参照してください。

   ![月間製品の目標](assets/goals-derived-field-product-goals-1.png)


### マーケティングチャネルの売上目標

各マーケティングチャネルの月間売上目標を設定します。 次に手順を示します。

1. [という名前の](/help/data-views/derived-fields/derived-fields.md#marketing-channels) マーケティングチャネル関数テンプレート `Monthly Marketing Channel Revenue Goal (Incremental)`を使用して、新しい派生フィールドを作成します。

1. URL PARSE ルールとCASE WHEN ルールの組み合わせに基づいて、各マーケティングチャネルを適切に識別するためのすべてのルールを定義します。 次に例を示します。

   ![&#x200B; マーケティングチャネル派生フィールドのルールの定義](assets/goals-derived-field-marketing-channel-1.png)

1. **[!UICONTROL カスタム数値]**&#x200B;を設定することで、最終的なCASE WHEN ルールの特定のマーケティングチャネルに対して、毎月の売上目標を表す静的な値を明示的に設定します。 以下の[!DNL Monthly Goal] ルールを参照してください。

   ![月間目標](assets/goals-derived-field-marketing-channel-2.png)



## 目標の使用

Workspace プロジェクトで目標を使用するには、計算指標の機能を使用して、派生フィールドを元の静的値に「正規化」します。 目標を定義する派生フィールドに設定した静的値は、イベントごとに増分されるため、この正規化は必須です。

### 毎月のギフト券の注文目標

1. `Monthly Gift Certificate Orders Goal`という名前の計算指標フィールドを作成し、次のように定義します。

   ![注文数の目標](assets/calculated-metric-ordersgoals.png)

1. 目標に対する実際の進捗状況を示すために、追加の計算フィールド（例：`% of Monthly Gift Certificate Orders Goal`）を作成できます。例：

   ![注文数の目標の割合](assets/calculated-metric-ordersgoalspercent.png)

これらの計算指標を使用して、フリーフォームテーブルやビジュアライゼーションの進行状況をレポートできます。 次に例を示します。

マーケティング売上目標を示す![&#x200B; フリーフォームテーブル &#x200B;](assets/freeform-table-marketing-channel-revenue-goals.png)




### マーケティングチャネルの売上目標

1. `Marketing Channel Revenue Goal`という名前の計算指標フィールドを作成し、次のように定義します。

   ![売上目標](assets/calculated-metric-revenuegoals.png)

1. 目標に対する実際の進捗状況を示すために、追加の計算フィールド（例：`% of Marketing Channel Revenue Goal`）を作成できます。例：

   ![売上目標の割合](assets/calculated-metric-revenuegoalspercent.png)

これらの計算指標を使用して、フリーフォームテーブルやビジュアライゼーションの進行状況をレポートできます。 次に例を示します。

マーケティング売上目標を示す![&#x200B; フリーフォームテーブル &#x200B;](assets/freeform-table-product-order-goals.png)
