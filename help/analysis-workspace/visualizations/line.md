---
description: 折れ線グラフのビジュアライゼーションを使用して、（時間ベースの）データセットを視覚化します。
title: 行
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
autotag-review: '2026-05-19T08:29:43.526Z'
TQID: 'https://experienceleague.adobe.com/ekT5diDY2vDPhjZ5I2oe-lgqjQ--Ri-bO-UljZUUmJw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 566
ht-degree: 83%

---

# 行 {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="行"
>abstract="一定期間にわたる値の変化を示す、折れ線グラフのビジュアライゼーションを作成します。 折れ線グラフのビジュアライゼーションは、ディメンションとして時間を使用する場合にのみ使用できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** バージョンの[Line](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/line)を参照してください。_

>[!ENDSHADEBOX]


![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL 折れ線グラフ]**&#x200B;ビジュアライゼーションでは、時間の経過に伴う値の変化を確認できるように、折れ線で指標が表されます。 折れ線グラフビジュアライゼーションは、時間がディメンションとして使用される場合にのみ使用できます。

![行のビジュアライゼーション](assets/line-viz.png)


## 設定

[ビジュアライゼーション設定](freeform-analysis-visualizations.md#settings)の一部として、特定の折れ線グラフビジュアライゼーション設定を使用できます。

| 設定 | 説明 |
|---|---|
| **[!UICONTROL 精度]** | 精度ドロップダウンから選択して、トレンドのビジュアライゼーションを日単位から週単位へ、月単位などに変更します。データソーステーブルでも精度が更新されます。 |
| **[!UICONTROL 最小値を表示]** <br/>**[!UICONTROL 最大値を表示&#x200B;]** | 最小値と最大値のラベルをオーバーレイして、指標の最小値と最大値をハイライト表示できます。 メモ：最小値と最大値は、ディメンション内のすべての値ではなく、ビジュアライゼーション内に表示されたデータポイントから得られます。<br/>![最小値と最大値のラベルを持つオーバーレイ。](assets/min-max-labels.png) |
| **[!UICONTROL トレンドラインを表示]** | 回帰または移動平均トレンドラインを線系列に追加できます。 トレンドラインは、データのパターンをより明確に表現するのに役立ちます。 選択した場合、リストからモデルを選択します。 使用可能なモデルの概要および説明について詳しくは、[モデル](#models)を参照してください。<br/>![線形トレンドライン](assets/show-linear-trendline.png)。<p>**ヒント：**&#x200B;現在（部分的なデータ）または将来の日付を含まないデータには、トレンドラインを適用することをお勧めします。 本日または未来の日付は、トレンドラインをゆがめます。 ただし、未来の日付を含める必要がある場合は、データからゼロを削除して、それらの日のゆがみを防ぎます。 ビジュアライゼーションのデータソーステーブルに移動し、指標列を選択して、**[!UICONTROL 列設定]**／**[!UICONTROL ゼロを値なしで解釈]**&#x200B;を有効にします。</p> |

### モデル

すべての回帰モデルのトレンドラインは、通常の最小二乗法を使用して求めます。

| モデル | 説明 |
| --- | --- |
| **[!UICONTROL 線形]** | 単純な線形データセットに対して最適な直線を作成します。この直線は、データが一定速度で増減する場合に便利です。 数式：`y = a + b * x` |
| **[!UICONTROL 対数]** | 最適な曲線を作成し、データの変化率が急速に増減し、次にレベルアウトする場合に便利です。 対数近似曲線には、負の値と正の値を使用できます。 数式：`y = a + b * log(x)` |
| **[!UICONTROL 指数]** | 曲線を作成します。データが一貫して加速し上昇または下降する場合に便利です。 データに 0 または負の値が含まれる場合は、このオプションを使用しないでください。 数式：`y = a + e^(b * x)` |
| **[!UICONTROL 累乗]** | 曲線を作成します。これは、特定の速度で増加する測定値を比較するデータセットに便利です。 データに 0 または負の値が含まれる場合は、このオプションを使用しないでください。 数式：`y = a * x^b` |
| **[!UICONTROL 二次方程式]** | 放物線（上または下に凹面）のような形状のデータセットに最適なデータを検索します。 数式：`y = a + b * x + c * x^2` |
| **[!UICONTROL 移動平均]** | 平均値のセットに基づいて、滑らかなトレンドラインを作成します。 移動平均は、ローリング平均とも呼ばれ、特定数のデータポイント（「[!UICONTROL 精度]」セクションで決定される）を使用して、それらを平均し、その平均値を折れ線グラフのポイントとして使用します。 例えば、7 日の移動平均や 4 週間の移動平均があります。 |


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [行](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/visualizations/line-visualization){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

>[!MORELIKETHIS]
>
>[ パネルへのビジュアライゼーションの追加](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[ビジュアライゼーション設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[ビジュアライゼーションコンテキストメニュー](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

