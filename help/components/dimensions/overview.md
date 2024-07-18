---
title: ディメンションの概要
description: ディメンションの概要とCustomer Journey Analyticsでの使用方法を説明します
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 1564c91616015311393a643fe7fcecd429cf3a36
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 37%

---

# ディメンションの概要

Dimensionは、データの分析に使用されるCustomer Journey Analyticsのコンポーネントタイプです。 例えば、ディメンションは、[Analysis Workspace](/help/analysis-workspace/home.md) または [Report Builder](/help/report-builder/report-buider-overview.md) でレポートを作成する際に使用します。

Customer Journey Analyticsのサイズには制限はありません。値には、数値、テキスト、オブジェクト、リスト、またはすべてが混在する場合があります。

Customer Journey Analyticsの基本レポートは、指標の列（一般的には数値）に対して、ディメンションの行（一般的には文字列値）を表示します。

例えば、「ページ」ディメンションと「訪問回数」指標を組み合わせると、最も訪問されたページを示すランクレポートが表示されます。

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

各ディメンションは、サイトの異なる部分またはファセットを表します。これらのディメンションのうち 1 つ以上を 1 つ以上の指標と組み合わせて、必要なレポートを作成できます。

## ディメンションの作成

Customer Journey Analytics管理者は [ データビュー内でディメンションを作成 ](/help/data-views/create-dataview.md#components) できます。

## ディメンションの説明の追加

Customer Journey Analytics管理者は、データビュー内または直接Analysis Workspace内で、ディメンションやその他のコンポーネントの説明を追加できます。 ディメンションに説明を追加する方法について詳しくは、[コンポーネントの説明の追加](/help/components/add-component-descriptions.md)を参照してください。
