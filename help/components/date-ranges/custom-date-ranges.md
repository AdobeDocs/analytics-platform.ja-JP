---
description: Analysis Workspace でカスタム日付範囲を定義する方法を学習します。
keywords: Analysis Workspace
title: カスタム日付範囲の例
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
TQID: https://experienceleague.adobe.com/UqM7kI1AJmseZkWgH4cl5gTRgBhhORkAaPZWrf8WpOc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 100%

---

# カスタム日付範囲の例

この記事では、カスタム日付範囲のその他の例を示します。

## 最後の 2 か月前

+++ 詳細

2 か月前を定義するカスタム日付範囲を定義する必要があります。 いずれかのプリセットを使用します。

![最後の 2 か月前](assets/date-range-example-simple.png)

+++


## 先週末までローリング

+++ 詳細

1 週間前の現在の日付から先週の同じ曜日の終わりまでの期間を定義する日付範囲を定義する必要があります。 例えば、今日が 2024年9月11日水曜日の場合。 2024年9月4日水曜日から 2024年9月7日土曜日までの日付範囲が必要です。

![日付範囲例](assets/date-range-example.png)

+++ 

<!--
## Example: Use a 7-day rolling date range

You can create a date range that specifies a 7-day rolling window that ends one week ago:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* The Start settings would be *`current day minus 6 days`*.

* The End settings would be *`current day minus 7 days`*.

This date range can be a component that you drag onto any freeform table.
-->