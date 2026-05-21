---
description: 時間分割ディメンションが、収集したイベントのタイムスタンプをどのように取得し、これらのイベントをより有意義なディメンション（時間帯や曜日など）に分割するかをご紹介します。
title: 時間分割ディメンション
feature: Dimensions
exl-id: 5c3c2867-58de-4765-a4e1-91eac1891b38
role: User
TQID: https://experienceleague.adobe.com/pWuE5mm3euhky9BVYY9CqSsdOUgESs8S8LiizcWp6t4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 28%

---

# 時間分割ディメンション

時間分割では、収集したイベントのタイムスタンプを取得し、**時間**&#x200B;や&#x200B;**曜日**&#x200B;など、より意味のあるディメンションに分割します。

時間分割ディメンションは、データビューのタイムゾーンに基づいています。 これらのディメンションはAnalysis Workspaceで利用でき、次の質問に答えるのに役立ちます。

* 幅広い日付範囲で、ユーザーがサイトやアプリにアクセスする最も人気のある時間帯は何ですか？
* サイトやアプリで、コンバージョン率が高い曜日や時間帯はありますか？
* ウィークエンドの売上とウィークエンドの売上の比較はどうなりますか？
* 「特定のマーケティング施策は、午前中にコンバージョン率を向上させますか？」

| ディメンション | 値の例 |
|--- |--- |
| **[!UICONTROL 時間帯]** | 0 ～ 23 |
| **[!UICONTROL 午前／午後]** | AM、PM |
| **[!UICONTROL 曜日]** | 月曜日、火曜日、水曜日、木曜日、金曜日、土曜日、日曜日 |
| **[!UICONTROL 平日／週末]** | 平日、週末 |
| **[!UICONTROL 月間通算日]** | 1 ～ 31 |
| **[!UICONTROL 年間通算月]** | 1 月 ～ 12 月 |
| **[!UICONTROL 年間通算日]** | 1 ～ 366 |
| **[!UICONTROL 四半期]** | 第 1 四半期、第 2 四半期、第 3 四半期、第 4 四半期 |
