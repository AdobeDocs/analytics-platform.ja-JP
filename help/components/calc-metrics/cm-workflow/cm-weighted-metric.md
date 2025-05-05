---
description: 計算指標の例を示します。
title: 計算指標の例
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# 計算指標の例

この記事では、より高度な計算指標を定義する方法の例について説明します。

## バウンス率

バウンス率を計算する必要があります。

+++ 詳細

バウンスの定義は別のディスカッションの対象となりますが、この例では、「セッション開始」が 1 と等しく、「セッション終了」が 1 と等しいバウンスイベントセグメントを定義します。 このセグメントを使用して、セッションへのバウンスセッションの割合を定義します。


### セグメント

![ バウンスイベント ](assets/example-bounce-bouncedevents.png)

### 計算指標

![バウンス率](assets/example-bounce-rate.png)


### 派生フィールド

または、[ 派生フィールドを使用したバウンス率 ](/help/data-views/derived-fields/derived-fields.md#bounces) を定義できます。

派生フィールドは、すべてのユーザーがバウンス率指標の定義を上書きまたは変更できるわけではないという利点を持つデータビューの一部です。 この利点には、制限も伴いました。 データビューへのアクセス権を持たないユーザーは、派生フィールドを使用できず、バウンス率を定義するためにセグメントや計算指標に頼る必要があります。

Customer Journey Analyticsでのバウンス数とバウンス率の計算方法について詳しくは、この [ ブログ投稿 ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=ja) を参照してください。

+++


## 条件付きページビュー

100 を超えるセッションで訪問したページのページビューのみを計算する計算指標を定義します。

+++ 詳細

![ 条件付きページビュー ](assets/conditional-page-views.png)

+++

## 上位 30% セッションのページビュー

上位 30% のセッションのページビューのみを計算する計算指標を定義する場合。

+++ 詳細

![ 上位 30% のページビュー ](assets/top30-page-views.png)

+++
