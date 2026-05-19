---
description: Analysis Workspaceのフロービジュアライゼーションの使用方法を説明します。
title: フローの概要
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
autotag-review: '2026-05-19T08:39:33.544Z'
TQID: 'https://experienceleague.adobe.com/X0VLZhluDR9Q-ax7TcTOHEcn4r0V5yu64spZlfc4fwU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 349
ht-degree: 74%

---

# フローの概要 {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="フロー"
>abstract="1 つのチェックポイントから次のチェックポイントへのユーザーフローを表示するビジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="フロー"
>abstract="1 つのタッチポイントから次のタッチポイントへの訪問または訪問者のフローを分析します。 開始元および終了元のコンポーネント（指標、ディメンションまたは項目）を指定します。 オプションで、詳細設定を定義して、ビジュアライゼーションをさらに設定できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** バージョンの[Flow](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)を参照してください。_

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL フロー]**&#x200B;ビジュアライゼーションは、web サイトおよびアプリの顧客パスを表示します。

ビジュアライゼーションを使用すると、次のことができます。

* Web サイトやアプリケーションでのカスタマージャーニーを視覚化
* 入口、特定のディメンション、出口など、指定したチェックポイントの前後で顧客がどこに移動するかを分析
* 選択したパスの特定のポイントを指定することによりセグメントを作成。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [フロービジュアライゼーションの作成](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


## ディメンション間のフロー

[ディメンション間のフロー](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)を表示できます。 例えば、ページと部門を 1 つの図に組み合わせることができます。 この場合、フローはホームページから男性ページ、次に靴部門に移動します。

各列に異なるディメンションを表示することができます。 ディメンションをドラッグしてドロップゾーンにドロップし、そのディメンションをダイアグラムに追加します。

>[!MORELIKETHIS]
>
>[フロービジュアライゼーションの設定](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。
>

## フロー、フォールアウト、ジャーニーキャンバスのいずれかのビジュアライゼーションを選択

フロービジュアライゼーションは、[フォールアウトビジュアライゼーション](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)や[ジャーニーキャンバスビジュアライゼーション](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)と似ていますが、重要な違いがあります。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### フローを使用するタイミング

フロービジュアライゼーションは、次の場合に最適です。

* パス上の次のタッチポイントに対する探索的、Ad Hoc Analysis。 （事前に定義された一連のページを含むジャーニーや、最終的なパスを使用するジャーニーでは、ジャーニーキャンバスを使用します。）

* 複数のエントリポイントとパスを持つ非線形ジャーニー。 （事前に定義された一連のページを含むジャーニーにはジャーニーキャンバスを使用します。）

フロー、フォールアウトおよびジャーニーキャンバスの違いを理解するには、[上記の表](#understand-the-differences)を参照してください。
