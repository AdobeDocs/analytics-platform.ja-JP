---
title: ディメンションの概要
description: ディメンションの概要とCustomer Journey Analyticsでの使用方法を説明します
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 36%

---

# ディメンションの概要

Dimensionは、データの分析に使用されるCustomer Journey Analyticsのコンポーネントタイプです。 例えば、ディメンションは、[Analysis Workspace](/help/analysis-workspace/home.md) または [Report Builder](/help/report-builder/report-buider-overview.md) でレポートを作成する際に使用します。

Customer Journey Analyticsのディメンションの種類は無制限です。値には、数値、テキスト、オブジェクト、リスト、またはすべてが混在する場合があります。

Customer Journey Analyticsの基本レポートは、指標の列（一般的には数値）に対して、ディメンションの行（一般的には文字列値）を表示します。

例えば、ページ ディメンションを人物指標と組み合わせると、訪問回数の多いページを人物で示したランクレポートが表示されます。

| ページ | ユーザー |
| --- | ---: |
| ホームページ | 800 |
| 製品紹介ページ | 500 |
| 購入ページ | 100 |

{style="table-layout:fixed"}

各ディメンションは、サイトの異なる部分またはファセットを表します。これらのディメンションのうち 1 つ以上を 1 つ以上の指標と組み合わせて、必要なレポートを作成できます。


## ディメンションの作成

Customer Journey Analytics管理者は [ データビュー内でディメンションを作成 ](/help/data-views/create-dataview.md#components) できます。

## デフォルトのディメンション

データビューを作成すると、デフォルトで次の時間ベースのコンポーネントがディメンションとしてデータビューに追加されます。

- 15 分
- 30 分
- 5 分
- 日
- 日付
- 曜日
- 年間通算日
- 時間
- 時刻
- 分
- 分 (時間)
- 月
- 月
- 四半期
- 四半期
- 2 番目
- 年間通算週
- 年

## ディメンションの説明の追加

Customer Journey Analytics管理者は、データビュー内または直接Analysis Workspace内で、ディメンションやその他のコンポーネントの説明を追加できます。 ディメンションに説明を追加する方法について詳しくは、[コンポーネントの説明の追加](/help/components/add-component-descriptions.md)を参照してください。
