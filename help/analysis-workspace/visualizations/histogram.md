---
description: ヒストグラムは、棒グラフに似ていますが、数値を範囲（バケット）にグループ化します。
title: ヒストグラム
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 42%

---

# ヒストグラム {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_histogram_button"
>title="ヒストグラム"
>abstract="数値データの分布を範囲のグループに表す、ヒストグラムのビジュアライゼーションを作成します。"

<!-- markdownlint-enable MD034 -->


![ ヒストグラム ](/help/assets/icons/Histogram.svg)**[!UICONTROL ヒストグラム]** ビジュアライゼーションは、[!UICONTROL  棒グラフ ] ビジュアライゼーションに似ていますが、数値を範囲（バケット）にグループ化します。 Analytics は、数から範囲への「グループ化」を自動化しますが、[詳細設定](#advanced-settings)で設定を変更できます。

## 用途

ヒストグラムを作成するには

1. ![ ヒストグラム ](/help/assets/icons/Histogram.svg)**[!UICONTROL ヒストグラム]** ビジュアライゼーションを追加します。 [ パネルへのビジュアライゼーションの追加 ](freeform-analysis-visualizations.md#add-visualizations-to-a-panel) を参照してください。
1. **[!UICONTROL 指標]** コンポーネントリストから指標をドラッグするか、[!UICONTROL *指標を追加*] ドロップダウンメニューから指標を選択します。
1. （任意）「**[!UICONTROL 詳細設定を表示]**」を選択します。 [ 詳細設定 ](#advanced-settings) を参照してください。
1. 「**[!UICONTROL 作成]**」を選択します。

>[!NOTE]
>
>ヒストグラムは、計算指標ではなく、標準指標のみをサポートします。

次の例では、ヒストグラムを使用して、人数のセッションをバケット化します。 ヒストグラムは、ほとんどの人が選択したデータ範囲に対して 16～21 のセッションを持っていることを示しています。

![](assets/histogram.png)

## 詳細設定

ビジュアライゼーションの一部として、特定のヒストグラム設定を使用できます。

| ヒストグラムの設定 | 説明 |
|---|---|
| **[!UICONTROL 開始バケット]** | どのグループからヒストグラムが始まるかを決定します。1 がデフォルトです。開始の数を 0 から無限大まで（負の数はなし）設定できます。 |
| **[!UICONTROL 指標バケット]** | データ範囲（グループ）の数を増減できます。グループの最大数は 50 です。 |
| **[!UICONTROL 指標バケットのサイズ]** | 各グループのサイズを設定できます。例えば、グループサイズを 1 ページビューから 2 ページビューに変更できます。 |
| **[!UICONTROL カウント方法]** | **[!UICONTROL ユーザー]**、**[!UICONTROL セッション]** または **[!UICONTROL イベント]** から選択します。 例えば、セッションごとのページビュー、1 人あたりのページビュー、1 つのイベントあたりのページビューなどです。 |

<!--Russ or Meike - Check Hit Type link above. -->

**例**：

| 開始バケット | 指標グループ | 指標バケットのサイズ | 結果 |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![ ヒストグラム、開始バケット 1、指標バケット 5、指標バケット サイズ 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![ ヒストグラム、開始バケット 0、指標バケット 3、指標バケット サイズ 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[ パネルへのビジュアライゼーションの追加 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[ビジュアライゼーション設定 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[ビジュアライゼーションコンテキストメニュー ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


## ブログ投稿

[ ヒストグラムを使用して予期しないデータ値を識別する ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168) に関する情報については、このブログ投稿を参照してください。
