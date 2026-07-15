---
description: 棒グラフに似ていますが、数値を範囲（バケット）にグループ化するヒストグラムの使用方法を説明します。
title: ヒストグラム
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
autotag-review: '2026-05-19T08:31:33.712Z'
TQID: 'https://experienceleague.adobe.com/X9T4RpAiJ8uL0clPhyjffdl02kwd-k2Jv3O5t6iHfss'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 494
ht-degree: 68%

---

# ヒストグラム {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="ヒストグラム"
>abstract="数値データの分布を範囲のグループに表す、ヒストグラムのビジュアライゼーションを作成します。"


>[!BEGINSHADEBOX]

_この記事では、この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版の[ ヒストグラム ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/histogram)を参照してください。_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)_**Customer Journey Analytics**。_<br/>_&#x200B;この記事のヒストグラム _の概要を説明します。

>[!ENDSHADEBOX]


![ヒストグラム](/help/assets/icons/Histogram.svg) **[!UICONTROL ヒストグラム]**&#x200B;ビジュアライゼーションは、[!UICONTROL 棒グラフ]ビジュアライゼーションに似ていますが、数値を範囲（バケット）にグループ化します。 Analytics は、数から範囲への「グループ化」を自動化しますが、[詳細設定](#advanced-settings)で設定を変更できます。

## 使用

ヒストグラムを作成するには

1. ![ヒストグラム](/help/assets/icons/Histogram.svg) **[!UICONTROL ヒストグラム]**&#x200B;ビジュアライゼーションを追加します。 [パネルへのビジュアライゼーションの追加](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。
1. **[!UICONTROL 指標]** コンポーネントリストから指標をドラッグするか、[!UICONTROL *指標を追加*] ドロップダウンメニューから指標を選択します。
1. （オプション）「**[!UICONTROL 詳細設定を表示]**」を選択します。 [詳細設定](#advanced-settings)を参照してください。
1. 「**[!UICONTROL 作成]**」を選択します。

>[!NOTE]
>
>ヒストグラムは、計算指標ではなく、標準指標のみをサポートします。

次の例では、ヒストグラムを使用してセッションをユーザー数別のバケットに分類しています。 ヒストグラムは、ほとんどの人が、選択した日付範囲で 16～21 のセッションを行っていることを示しています。

![ヒストグラム](assets/histogram.png)

## 詳細設定

ビジュアライゼーションの一部として、特定のヒストグラム設定を使用できます。

| ヒストグラム設定 | 説明 |
|---|---|
| **[!UICONTROL 開始バケット]** | ヒストグラムの開始位置となるバケットを指定します。 「1」がデフォルトです。 0から無限大（負の数は含まない）までの開始数を設定できます。 |
| **[!UICONTROL 指標バケット]** | データ範囲（バケット）の数を増減できます。 グループの最大数は 50 です。 |
| **[!UICONTROL 指標バケットのサイズ]** | 各バケットのサイズを設定できます。 例えば、バケットのサイズを1つのページビューから2つのページビューに変更できます。 |
| **[!UICONTROL カウント方法]** | **[!UICONTROL グローバルアカウント]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL アカウント]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 購買グループ]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 商談]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 人物]**、**[!UICONTROL セッション]**、**[!UICONTROL イベント]**、または&#x200B;**[!UICONTROL オブジェクト]**&#x200B;から選択します。 例えば、アカウント [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} ごとのページビュー数、セッションごとのページビュー数、ユーザーごとのページビュー数、イベントごとのページビュー数などです。 **[!UICONTROL オブジェクト]**&#x200B;を選択すると、サブイベント分析用に[ カスタムコンテナ ](/help/data-views/create-dataview.md#containers-1)が選択されます。 |

<!--Russ or Meike - Check Hit Type link above. -->

**例**：

| 開始バケット | 指標バケット | 指標バケットのサイズ | 結果 |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![ヒストグラム、開始バケット 1、指標バケット 5、指標バケットのサイズ 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![ヒストグラム、開始バケット 0、指標バケット 3、指標バケットのサイズ 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[ パネルへのビジュアライゼーションの追加ビジュアライゼーション設定ビジュアライゼーションコンテキストメニューヒストグラムを使用して予期しないデータ値を識別する](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

