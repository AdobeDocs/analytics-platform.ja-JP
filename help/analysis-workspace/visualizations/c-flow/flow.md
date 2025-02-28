---
description: Web サイトやアプリを通じた顧客パスを表示するフロー機能について説明します。
title: フローの概要
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 25%

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
>abstract="1 つのタッチポイントから次のタッチポイントへの訪問または訪問者のフローを分析します。 開始元および終了元のコンポーネント（指標、ディメンション、または項目）を指定します。 オプションで、詳細設定を定義して、ビジュアライゼーションをさらに設定できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_ CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics![ のフロービジュアライゼーションについて説明します**。_<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 版については、[](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) フロー _を参照してください。

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg)**[!UICONTROL フロー]** ビジュアライゼーションには、web サイトやアプリを介した顧客パスが表示されます。

ビジュアライゼーションを使用すると、次のことができます。

* Web サイトまたはアプリケーションを通じたカスタマージャーニーを視覚化します。
* 顧客が指定のチェックポイントの前後に移動する場所（入口、特定のディメンション、出口など）を分析します。
* 選択したパス内の特定のポイントを指定してフィルターを作成します。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ フロービジュアライゼーションの作成 ](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


## ディメンション間のフロー

[ディメンション間のフロー](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)を表示できます。例えば、ページと部門を 1 つの図に組み合わせることができます。この場合、フローは、ホームページからメンズページを経て、靴部門に移動することが考えられます。

各列は、異なるディメンションを表示することがあります。ディメンションをドラッグしてドロップゾーンにドロップし、そのディメンションを図に追加します。

>[!MORELIKETHIS]
>
>[ フロービジュアライゼーションの設定 ](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。
>

## フロー、フォールアウト、ジャーニーのいずれかのキャンバスビジュアライゼーションを選択します

フロービジュアライゼーションは、[ フォールアウトビジュアライゼーション ](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) および [ジャーニーキャンバスビジュアライゼーション ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) と似ていますが、重要な違いがあります。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### フローを使用するタイミング

フロービジュアライゼーションは、次の場合に最適です。

* パス上の次のタッチポイントに対する探索的アドホック分析。 （事前に定義された一連のページを含むジャーニーや、最終的なパスを使用するジャーニーでは、ジャーニーキャンバスを使用します）。

* 複数のエントリポイントとパスを持つ非線形ジャーニー。 （事前に定義されたページのシーケンスを含むジャーニーにはジャーニーキャンバスを使用します）。

[ 上の表 ](#understand-the-differences) を使用して、フロー、フォールアウトおよびジャーニーキャンバスの違いを理解します。
