---
description: Analysis Workspaceのカスタム日付範囲の例。
keywords: Analysis Workspace
title: カスタム日付範囲の例
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 4%

---

# カスタム日付範囲の例

この記事では、カスタム日付範囲のその他の例を示します



## 最後の 2 か月前

+++ 詳細

2 か月前を定義するカスタムの日付範囲を定義する場合。 いずれかのプリセットを使用します。

![ 過去 2 か月前 ](assets/date-range-example-simple.png)

+++


## 先週末までローリング

+++ 詳細

1 週間前の現在の日付から先週の同じ曜日の終わりまでの期間を定義する日付範囲を定義する場合。 例えば、今日が 2024 年 9 月 11 日水曜日の場合。 2024 年 9 月 4 日水曜日（PT）から 2024 年 9 月 7 日土曜日までの日付範囲が必要です。 9月

![ 日付範囲の例 ](assets/date-range-example.png)

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