---
title: ガイド付き分析に関するよくある質問
description: ガイド付き分析に関するよくある質問。
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: ht
source-wordcount: '434'
ht-degree: 100%

---

# ガイド付き分析に関するよくある質問

ガイド付き分析に関するよくある質問。

+++**組織をガイド付き分析用にプロビジョニングする方法**

ガイド付き分析は、Adobe Product Analytics の一部で、Customer Journey Analytics の有料アドオンです。このアドオンの使用を開始する場合は、アドビのアカウントチームにお問い合わせください。

+++

+++**ガイド付き分析を使用する上で必要な実装変更**

現在既に Customer Journey Analytics を使用している場合、追加の実装変更は必要ありません。ガイド付き分析では、[Analysis Workspace](../analysis-workspace/home.md) などの他の CJA インターフェイスと同じ[データビュー](../data-views/data-views.md)と[接続](../connections/overview.md)を使用します。

ガイド付き分析でエンドユーザーの成功を最大限に導くには、Adobe Experience Platform と[データビュー](../data-views/data-views.md)で強力なイベントスキーマと管理戦略を導入することをお勧めします。

+++

+++**ガイド付き分析や Analysis Workspace を使用すべきタイミング**

**ガイド付き分析**&#x200B;により、ユーザーは質の高い分析情報を迅速に入手できます。これは、製品チーム、より自信を持ってデータを扱いたいユーザー、さらにはアナリストが深い分析に着手する際に有益です。

**[Analysis Workspace](../analysis-workspace/home.md)** は、より自由なスペースで、データを詳細に分析して、より多くのインサイトを引き出すことができます。データをよく理解し、深く掘り下げたいアナリストやパワーユーザーに役立ちます。

+++

+++**ガイド付き分析と Analysis Workspace の用語の比較方法**

ガイド付き分析では、製品チーム間でより頻繁に使用される用語を使用します。ガイド付き分析と [Analysis Workspace](../analysis-workspace/home.md) を切り替える際に、このテーブルを参照できます。

| ガイド付き分析の用語 | Analysis Workspace の用語 |
| --- | --- |
| イベント | 指標 |
| ユーザー | ユーザー |
| プロパティ | ディメンション |
| 値 | ディメンション項目 |
| セグメント | フィルター |

{style="table-layout:auto"}

+++

+++**ガイド付き分析と Analysis Workspace アプローチのレポートの相違点**

[Analysis Workspace](../analysis-workspace/home.md) とガイド付き分析では同じ基礎データを使用しますが、各ツールでそのデータのクエリを作成する方法が異なります。

* **Analysis Workspace は、ディメンションを中心としたエクスペリエンスです。** テーブルは通常、ディメンションの行で構成され、列は通常、指標です。行と列の両方にフィルターを適用して、目的のデータを取得できます。

* **ガイド付き分析は、イベントやユーザー中心のエクスペリエンスです。** 各分析は、まずイベントを選択することで開始し、ディメンションとフィルターを追加して、そのイベントデータを絞り込むことができます。

![Analysis Workspace とガイド付き分析のビュー](assets/structure.png){style="border:1px solid gray"}

Web サイトのホームページに関するデータに焦点を当てる次の例を考えてみましょう。チームが類似した質問をしますが、分析のアプローチは異なる場合があります。

* ディメンションを中心にした Analysis Workspace の一般的なアプローチでは、「ホームページを見て、受け取ったページビュー数を確認」します。

  ![ディメンション中心](assets/dimension-centered.png){style="border:1px solid gray"}

* イベントやユーザーを中心にした一般的な分析アプローチでは、「ホームページを訪問したユーザーの数を確認」します。

  ![イベント中心](assets/event-centered.png){style="border:1px solid gray"}

+++
