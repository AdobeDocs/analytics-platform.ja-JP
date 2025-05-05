---
description: web サイトおよびアプリでの顧客パスを表示するフロー機能について説明します。
title: フローの概要
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 96%

---

# フロー {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="フロー"
>abstract="1 つのチェックポイントから次のチェックポイントへのユーザーフローを表示するビジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="フロー"
>abstract="1 つのタッチポイントから次のタッチポイントへの訪問または訪問者のフローを分析します。開始元および終了元のコンポーネント（指標、ディメンションまたは項目）を指定します。オプションで、詳細設定を定義して、ビジュアライゼーションをさらに設定できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** のフロービジュアライゼーションについて説明します。_<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** バージョンについて詳しくは、[フロー](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)を参照してください。_

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL フロー]**&#x200B;ビジュアライゼーションは、web サイトおよびアプリの顧客パスを表示します。

ビジュアライゼーションを使用すると、次のことができます。

* Web サイトやアプリケーションでのカスタマージャーニーを視覚化
* 入口、特定のディメンション、出口など、指定したチェックポイントの前後で顧客がどこに移動するかを分析
* 選択したパス内の特定の点を指定してセグメントを作成します。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [フロービジュアライゼーションの作成](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


## ディメンション間のフロー

[ディメンション間のフロー](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)を表示できます。例えば、ページと部門を 1 つの図に組み合わせることができます。この場合、フローは、ホームページからメンズページを経て、靴部門に移動することが考えられます。

各列は、異なるディメンションを表示することがあります。ディメンションをドラッグしてドロップゾーンにドロップし、そのディメンションを図に追加します。

>[!MORELIKETHIS]
>
>[フロービジュアライゼーションの設定](/help/analysis-workspace/visualizations/c-flow/create-flow.md)
>

## フロー、フォールアウト、ジャーニーキャンバスのいずれかのビジュアライゼーションを選択

フロービジュアライゼーションは、[フォールアウトビジュアライゼーション](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)や[ジャーニーキャンバスビジュアライゼーション](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)と似ていますが、重要な違いがあります。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### フローを使用するタイミング

フロービジュアライゼーションは、次の場合に最適です。

* パス上の次のタッチポイントに対する探索的、Ad Hoc Analysis。（事前に定義された一連のページを含むジャーニーや、最終的なパスを使用するジャーニーでは、ジャーニーキャンバスを使用します。）

* 複数のエントリポイントとパスを持つ非線形ジャーニー。（事前に定義された一連のページを含むジャーニーにはジャーニーキャンバスを使用します。）

フロー、フォールアウトおよびジャーニーキャンバスの違いを理解するには、[上記の表](#understand-the-differences)を参照してください。
