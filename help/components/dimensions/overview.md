---
title: ディメンションの概要
description: ディメンションの概要と Customer Journey Analytics での使用方法について説明します。
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
TQID: https://experienceleague.adobe.com/bMM7desF2wr71h-SR1mzD7-oSwm-8cPvmeU7SeM7-fU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 253
ht-degree: 100%

---

# ディメンションの概要

ディメンションは、データの分析に使用される Customer Journey Analytics のコンポーネントタイプです。 例えば、[Analysis Workspace](/help/analysis-workspace/home.md) や [Report Builder](/help/report-builder/rb-overview.md) でレポートを作成する場合にディメンションを使用します。

Customer Journey Analytics のディメンションは無制限タイプです。値には、数値、テキスト、オブジェクト、リスト、すべての組み合わせを使用できます。

Customer Journey Analytics の基本レポートでは、指標の列（一般的には数値）に対する、ディメンションの行（一般的には文字列値）が表示されます。

例えば、「ページ」ディメンションと「人物」指標を組み合わせると、最も多くの人にアクセスされたページを示すランクレポートが表示されます。

| ページ | People |
| --- | ---: |
| ホームページ | 800 |
| 製品ページ | 500 |
| 購入ページ | 100 |

{style="table-layout:fixed"}

各ディメンションは、サイトの異なる部分またはファセットを表します。 これらのディメンションのうち 1 つ以上を 1 つ以上の指標と組み合わせて、必要なレポートを作成できます。


## ディメンションの作成

Customer Journey Analytics 管理者は[データビュー内でディメンションを作成する](/help/data-views/create-dataview.md#components)ことができます。

## 標準ディメンション

データビューを作成する場合、デフォルトでは、次のコンポーネントがディメンションとしてデータビューに追加されます。

{{standard-dimensions}}


## ディメンションの説明の追加

Customer Journey Analytics 管理者は、データビュー内または直接 Analysis Workspace 内で、ディメンションやその他のコンポーネントの説明を追加できます。 ディメンションに説明を追加する方法について詳しくは、[コンポーネントの説明の追加](/help/components/add-component-descriptions.md)を参照してください。

>[!MORELIKETHIS]
>
>[イベント深度機能を使用して、より深い顧客インサイトを得る](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947?profile.language=ja#M576)
>

