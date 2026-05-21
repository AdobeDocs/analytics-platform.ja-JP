---
description: 計算指標の例を示します。
title: 計算指標の例
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
TQID: https://experienceleague.adobe.com/awAk0boIVigYBssgLcSz3t-5eExHhasCVDtwoa3v19k
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 4%

---

# 計算指標の例

この記事では、より高度な計算指標を定義する方法の例を示します。

## バウンス率

バウンス率を計算することができます。

+++ 詳細

バウンスの定義は別のディスカッションの対象ですが、この例では、Session Startが1に、Session Endsが1に等しいバウンス イベントセグメントを定義します。 このセグメントを使用すると、セッションに対するバウンス率を定義できます。


### セグメント

![&#x200B; イベントのバウンス &#x200B;](assets/example-bounce-bouncedevents.png)

### 計算指標

![バウンス率](assets/example-bounce-rate.png)


### 派生フィールド

または、派生フィールド [&#128279;](/help/data-views/derived-fields/derived-fields.md#bounces)を使用して直帰率を定義することもできます。

派生フィールドは、データビューの一部であり、すべてのユーザーがバウンス率指標の定義を上書きまたは変更できるわけではないという利点があります。 その利点は限界も生み出しました。 データビューにアクセスできないユーザーは、派生フィールドを使用できず、バウンス率を定義するためにセグメントと計算指標に頼る必要があります。

Customer Journey Analyticsでのバウンス率とバウンス率の計算方法について詳しくは、この[&#x200B; ブログ記事](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=ja)を参照してください。

+++


## 条件付きページビュー

100回を超えるセッションで訪問されたページのページビューのみを計算する計算指標を定義します。

+++ 詳細 

![条件付きページビュー](assets/conditional-page-views.png)

+++

## 上位30%のセッションのページビュー

上位30%のセッションのページビューのみを計算する計算指標を定義します。

+++ 詳細

![上位30% ページビュー](assets/top30-page-views.png)

+++
