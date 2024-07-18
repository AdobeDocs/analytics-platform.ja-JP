---
description: Workspace の合計の計算方法を説明します。
title: Workspace の合計
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 75%

---

# Workspace の合計

フリーフォームテーブルでは、合計行が各分類レベルに表示され、2 つの合計を示すことができます。

* **[!UICONTROL 総合計]** （灰色の「範囲外」の数） – この合計は、収集されたすべてのイベントを表します。 フィルターがパネルレベルまたはフリーフォームテーブル内で適用されると、この合計は、フィルター条件に一致するすべてのイベントを反映するように調整されます。
* **[!UICONTROL テーブル合計]**（黒い数字） - 通常、この合計は[!UICONTROL 総計]と等しいか、またはそのサブセットです。「[!UICONTROL なしを含む]」オプションなど、フリーフォームテーブル内で適用されたすべてのテーブルフィルターを反映します。

![ 総計とテーブルの合計をハイライト表示したフリーフォームテーブル。](assets/total-row.png)

## 合計設定を表示

「**[!UICONTROL 列設定]**」の下に、「**[!UICONTROL 合計を表示]**」と「**[!UICONTROL 総計を表示]**」のオプションがあります。これらの設定がオフの場合、合計はテーブルから削除されます。これは、特定の[計算指標のシナリオ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html?lang=ja)などで合計が意味をなさない場合に必要です。

![ 「合計を表示」および「付与合計を表示」のチェックマークを表示する列設定オプション ](assets/column-settings-total.png)

## 静的な行の合計の設定

[静的な行](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)の合計は、動作が異なり、「**[!UICONTROL 行設定]**」で制御されます。

* **[!UICONTROL 現在の行の合計を合計として表示]** - テーブル内の行のクライアントサイドの合計が表示されます。つまり、合計は、訪問回数や人物などの指標の重複を排除 **しません**。
* **[!UICONTROL 総計を表示]** - サーバー側の合計が表示されます。つまり、合計により、訪問回数やユーザー数などの指標の重複が排除されます。

![ 「総計を表示」が選択されていることを示す行設定。](assets/static-rows.png)

## よくある質問

| 質問 | 回答 |
|---|---|
| 灰色の列の割合は、どの「合計」を基準にしていますか。 | これは、「**[!UICONTROL 行設定]**」で選択した「**[!UICONTROL パーセンテージ]**」の設定によって異なります。<ul><li>割合を列ごとに計算 - これがデフォルト設定です。割合は、テーブル合計に基づきます。</li><li>割合を行ごとに計算 - パーセントは総計に基づきます。</li></ul> |
| 「**[!UICONTROL 未指定 (なし) を含む]**」設定は、合計にどのように影響しますか。 | 「**[!UICONTROL 未指定 (なし) を含む]**」設定がオフの場合、「なし/未指定」の行はテーブル（テーブル合計）から削除され、[「合計」の指標タイプ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html?lang=ja)を使用する計算指標にも適用されます。 |
| フリーフォームテーブルにカスタムテーブルフィルターを適用する場合、そのフィルターに対してすべての計算指標と条件付き書式設定を利用できますか。 | 現在は利用できません。「**[!UICONTROL 未指定 (なし) を含む]**」は計上されますが、カスタムテーブルフィルターは次に影響しません。<ul><li>条件付き書式で使用される列の最大／最小範囲は、すべてのデータを対象とします。</li><li>**[!UICONTROL 総計]**&#x200B;指標タイプを利用する計算指標。</li><li>フリーフォームテーブルの行をまたいで計算する関数（例：Column Sum、Column max、Column min、Count、Mean、Median、Percentile、Quartile、Row Count、Standard Deviation、Variance、Cumulative、Cumulative Average、Regression variants、T-Score、T-Test、Z-Score、Z-Test）を使用する計算指標。</li></ul> |
| 「計算指標」で、「**[!UICONTROL 総計]**」指標タイプは何を反映していますか。 | 「**[!UICONTROL 総計]**」は引き続き「**[!UICONTROL 総計]**」を参照します。また、テーブルや&#x200B;**[!UICONTROL テーブル合計]**&#x200B;に適用されたフィルターは反映されません。 |
| フリーフォームテーブルからデータをコピーして貼り付けるか、CSV でデータをダウンロードすると、合計はどのように表示されますか。 | 合計行は、**[!UICONTROL テーブル合計]**&#x200B;のみを反映し、列の&#x200B;**[!UICONTROL 合計を表示]**&#x200B;設定に従います。 |
