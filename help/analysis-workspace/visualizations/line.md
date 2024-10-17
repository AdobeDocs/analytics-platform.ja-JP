---
description: 折れ線グラフのビジュアライゼーションを使用すると、トレンド（時間ベース）のデータセットを表現できます
title: 行
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 24%

---

# 行 {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_line_button"
>title="行"
>abstract="一定期間にわたる値の変化を示す、折れ線グラフのビジュアライゼーションを作成します。折れ線グラフのビジュアライゼーションは、ディメンションとして時間を使用する場合にのみ使用できます。"

<!-- markdownlint-enable MD034 -->


![GraphTrend](/help/assets/icons/GraphTrend.svg)**[!UICONTROL 折れ線グラフ]** ビジュアライゼーションは、線を使用して指標を表し、一定期間の値の変化を示します。 折れ線グラフのビジュアライゼーションは、時間がディメンションとして使用される場合にのみ使用できます。

<!--
>[!NOTE]
>
>The Line visualization soon feature [intelligent captions](/help/analysis-workspace/visualizations/intelligent-captions.md).

The Line visualization represents metrics using a line to show how values change over a period of time. A line chart can be used only when time is used as a dimension.
-->

![行のビジュアライゼーション](assets/line-viz.png)


## 設定

[ ビジュアライゼーション設定 ](freeform-analysis-visualizations.md#settings) の一部として、特定の折れ線ビジュアライゼーション設定を使用できます。

| 設定 | 説明 |
|---|---|
| **[!UICONTROL 精度]** | 精度ドロップダウンから選択して、毎日のトレンドビジュアライゼーションを毎週から毎月のに変更するなど、 データソーステーブルの精度も更新されます。 |
| **[!UICONTROL 最小値を表示]** <br/>**[!UICONTROL  最大値を表示 ]** | 最小値と最大値のラベルをオーバーレイして、指標の最小値と最大値をハイライト表示できます。 最小値と最大値は、ディメンション内のすべての値ではなく、ビジュアライゼーション内に表示されたデータポイントから得られます。<br/>![ 最小値と最大値のラベルを持つオーバーレイ。](assets/min-max-labels.png) |
| **[!UICONTROL トレンドラインを表示]** | 線系列に回帰または移動平均のトレンドラインを追加することを選択できます。 近似曲線は、データにより明確なパターンを示すのに役立ちます。 選択した場合、リストからモデルを選択します。 使用可能なモデルの概要および説明については、[ モデル ](#models) を参照してください。<br/>![ 線形近似曲線 ](assets/show-linear-trendline.png). |

>[!TIP]
>
>トレンドラインは、今日（データの一部）や未来の日付を含まないデータに適用することをお勧めします。 今日または将来の日付は、トレンドラインをゆがめます。 ただし、未来の日付を含める必要がある場合は、データからゼロを削除して、それらの日のゆがみを防ぎます。 ビジュアライゼーションのデータソーステーブルに移動し、指標列を選択して、**[!UICONTROL 列設定]**/**[!UICONTROL ゼロを値なしで解釈]** を有効にします。



### モデル

すべての回帰モデルのトレンドラインは、通常の最小二乗法を使用して求めます。

| モデル | 説明 |
| --- | --- |
| **[!UICONTROL 線形]** | 単純な線形データセットに最適な直線を作成します。これは、データが一定の割合で増加または減少する場合に役立ちます。 数式：`y = a + b * x` |
| **[!UICONTROL 対数]** | 最適な曲線を作成します。これは、データの変化率が急速に増加または減少し、その後レベル アウトする場合に便利です。 対数近似曲線には、負の値と正の値を使用できます。数式：`y = a + b * log(x)` |
| **[!UICONTROL 指数]** | 曲線を作成すると、データの増加や減少が頻繁に発生する場合に便利です。 データに 0 または負の値が含まれる場合は、このオプションを使用しないでください。数式：`y = a + e^(b * x)` |
| **[!UICONTROL パワー]** | 曲線を作成し、特定の割合で増加する測定値を比較するデータセットに便利です。 データに 0 または負の値が含まれる場合は、このオプションを使用しないでください。数式：`y = a * x^b` |
| **[!UICONTROL 二次方程式]** | 放物線（凹形の上または下）のような形状のデータセットの最適フィットを検索します。 数式：`y = a + b * x + c * x^2` |
| **[!UICONTROL 移動平均]** | 平均値のセットに基づいて、滑らかなトレンドラインを作成します。 移動平均は、ローリング平均とも呼ばれ、特定数のデータポイント（「[!UICONTROL  精度 ]」セクションで決定される）を使用して、それらを平均し、その平均値を折れ線グラフのポイントとして使用します。 例えば、7 日の移動平均や 4 週間の移動平均があります。 |

>[!MORELIKETHIS]
>
>[ パネルへのビジュアライゼーションの追加 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[ビジュアライゼーション設定 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[ビジュアライゼーションコンテキストメニュー ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

