---
title: ディメンションの概要
description: ディメンションの概要とCustomer Journey Analyticsでの使用方法を説明します
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 65b4339b4a1b27c41cfe442482a54661989d704b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 26%

---

# ディメンションの概要

ディメンションは、データの分析に使用されるCustomer Journey Analyticsのコンポーネントタイプです。 例えば、[&#128279;](/help/report-builder/rb-overview.md)Analysis Workspaceや [Report Builder](/help/analysis-workspace/home.md) でレポートを作成する場合にディメンションを使用し  す。

Customer Journey Analyticsのディメンションの種類は無制限です。値には、数値、テキスト、オブジェクト、リストまたはすべてが混在する場合があります。

Customer Journey Analyticsの基本レポートでは、指標の列（一般的には数値）に対する、ディメンションの行（一般的には文字列値）が表示されます。

例えば、ページ ディメンションを人物指標と組み合わせると、訪問回数の多いページを人物で示したランクレポートが表示されます。

| ページ | ユーザー |
| --- | ---: |
| ホームページ | 800 |
| 製品紹介ページ | 500 |
| 購入ページ | 100 |

{style="table-layout:fixed"}

各ディメンションは、サイトの異なる部分またはファセットを表します。これらのディメンションのうち 1 つ以上を 1 つ以上の指標と組み合わせて、必要なレポートを作成できます。


## ディメンションの作成

Customer Journey Analytics管理者は [ データビュー内でディメンションを作成する ](/help/data-views/create-dataview.md#components) ことができます。

## 標準寸法

データビューを作成する場合、デフォルトでは、次のコンポーネントがディメンションとしてデータビューに追加されます。

{{standard-dimensions}}


## ディメンションの説明の追加

Customer Journey Analytics管理者は、データビュー内または直接Analysis Workspace内で、ディメンションやその他のコンポーネントの説明を追加できます。 ディメンションに説明を追加する方法について詳しくは、[コンポーネントの説明の追加](/help/components/add-component-descriptions.md)を参照してください。
