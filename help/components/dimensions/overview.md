---
title: ディメンションの概要
description: ディメンションの概要と Customer Journey Analytics での使用方法について学ぶ
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 6cabedc5ed58dac450577fc3505be5f95b7a959d
workflow-type: ht
source-wordcount: '235'
ht-degree: 100%

---

# ディメンションの概要

ディメンションは、データの分析に使用される Customer Journey Analytics のコンポーネントタイプです。例えば、[Analysis Workspace](/help/analysis-workspace/home.md) や [Report Builder](/help/report-builder/rb-overview.md) でレポートを作成する場合にディメンションを使用します。

Customer Journey Analytics のディメンションは無制限タイプです。値には、数値、テキスト、オブジェクト、リスト、すべての組み合わせを使用できます。

Customer Journey Analytics の基本レポートでは、指標の列（一般的には数値）に対する、ディメンションの行（一般的には文字列値）が表示されます。

例えば、「ページ」ディメンションと「人物」指標を組み合わせると、最も多くの人にアクセスされたページを示すランクレポートが表示されます。

| ページ | 人物 |
| --- | ---: |
| ホームページ | 800 |
| 製品ページ | 500 |
| 購入ページ | 100 |

{style="table-layout:fixed"}

各ディメンションは、サイトの異なる部分またはファセットを表します。これらのディメンションのうち 1 つ以上を 1 つ以上の指標と組み合わせて、必要なレポートを作成できます。


## ディメンションの作成

Customer Journey Analytics 管理者は[データビュー内でディメンションを作成する](/help/data-views/create-dataview.md#components)ことができます。

## 標準ディメンション

データビューを作成する場合、デフォルトでは、次のコンポーネントがディメンションとしてデータビューに追加されます。

{{standard-dimensions}}


## ディメンションの説明の追加

Customer Journey Analytics 管理者は、データビュー内または直接 Analysis Workspace 内で、ディメンションやその他のコンポーネントの説明を追加できます。ディメンションに説明を追加する方法について詳しくは、[コンポーネントの説明の追加](/help/components/add-component-descriptions.md)を参照してください。

>[!MORELIKETHIS]
>
>[イベント深度機能を使用して、より深い顧客インサイトを得る](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>

