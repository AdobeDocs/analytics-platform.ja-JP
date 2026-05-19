---
description: 数値の概要と変更の概要ビジュアライゼーションを使用して、プロジェクト内の重要なデータポイントを表示します。
title: 概要番号と概要変更
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
autotag-review: '2026-05-19T08:30:25.509Z'
TQID: 'https://experienceleague.adobe.com/S9PlaFSE-szemwSU8Cehhfxc9r0bem1qyxfI9S8ohXg'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 534
ht-degree: 61%

---

# 数と変更の概要

>[!BEGINSHADEBOX]

_この記事では、この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**&#x200B;版の&#x200B;_CustomerJourneyAnalytics![&#128279;](/help/assets/icons/CustomerJourneyAnalytics.svg)_&#x200B;**Customer Journey Analytics**&#x200B;_<br/>_&#x200B;の[概要番号と概要変更](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change)を参照してください。_

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [数値の概要と変更の概要ビジュアライゼーション](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/visualizations/use-summary-visualizations){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

## 数値の概要 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="数値の概要"
>abstract="合計と小計を表示するビジュアライゼーションを作成します。"

<!-- markdownlint-enable MD034 -->

![要約](/help/assets/icons/123.svg) **[!UICONTROL 数値の概要]**&#x200B;ビジュアライゼーションを使用して、プロジェクト内の重要な多数の数値をハイライト表示します。 このビジュアライゼーションは、関連付けられたデータソースを使用して、次のように動作します。

* セルが選択されていない場合は、列の合計を選択します。
* 1つのセルを選択すると、そのセルの概要が表示されます。
* 複数のセルが選択されている場合は、最初に選択したセルが表示されます。
* 列が選択されている場合は、列の最初のセル値を選択します。

![数値の概要ビジュアライゼーション](asses/../assets/summary-number.png)

ビジュアライゼーション設定の一部として、特定の数値の概要オプションを使用できます。

| オプション | 定義 |
|--- |--- |
| **[!UICONTROL 値を短縮]** | 数値をインテリジェントに短縮するには、「**[!UICONTROL 値を短縮]**」を選択します。 選択した場合、短縮の量を定義する数値を入力します。 次に例を示します。<br/><table><tr><td>**元の値**</td><td>**短縮の値**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選択</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`0` に設定</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 選択済み、`1` に設定</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`2` に設定</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`3` に設定</td><td align="right">$12.011M</td></tr></table> |
| **[!UICONTROL 値の要約基準]** | 選択したデータの最大値、最小値、平均値、中央値または合計値の表示を選択します。 |

## 変更の概要 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="変更の概要"
>abstract="2 つの数値間の差分（変化）を表示するビジュアライゼーションの作成"

<!-- markdownlint-enable MD034 -->


![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 変更の概要]** ビジュアライゼーションを使用すると、2 つの数値間の差分（変化）を表示できます。<!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=ja) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=ja) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=ja) option.
-->

このビジュアライゼーションは、次のように動作します。

* セルが選択されていない場合は、列の最初の2つのセル値を比較します。
* 1つのセルが選択されている場合、セルの値を自分自身と比較するため、0と表示されます。
* 2つのセルを選択した場合、最初に選択したセルは分子、2番目のセルは分母と見なされます。
* 2つ以上のセルが選択されている場合は、最初の2つのセルのみが比較に使用されます。
* セルの範囲が選択されている場合は、最初のセルと最後に選択したセルを比較します。
* 列が選択されている場合、最初の値と自分自身を比較し、0の変化を示します。


![2 つの数値間の差分を示す変更の概要ビジュアライゼーション](assets/summary-change.png)


ビジュアライゼーション設定の一部として、特定の&#x200B;**[!UICONTROL 変更の概要オプション]**&#x200B;を使用できます。

| オプション | 定義 |
|--- |--- |
| **[!UICONTROL 変化率を表示]** | 2 つの数値間の変化率を表示します。 |
| **[!UICONTROL 生の差異を表示]** | 2 つの数値間の生の差異を表示します。 また、値の省略形を使用し、小数点以下 3 桁まで表示できます。 |
| **[!UICONTROL 値を短縮]** | 変更した値をインテリジェントに短縮するには、「**[!UICONTROL 値を短縮]**」を選択します。 選択した場合、短縮の量を定義する数値を入力します。 次に例を示します。<br/><table><tr><td>**元の値**</td><td>**短縮の値**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選択</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`0` に設定</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 選択済み、`1` に設定</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`2` に設定</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`3` に設定</td><td align="right">$12.011M</td></tr></table> |

>[!MORELIKETHIS]
>
>[&#x200B; パネルへのビジュアライゼーションの追加](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[ビジュアライゼーション設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[ビジュアライゼーションコンテキストメニュー](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
