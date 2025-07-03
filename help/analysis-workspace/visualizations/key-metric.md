---
description: 主要指標の概要ビジュアライゼーションを使用すると、2 つのタイムラインにわたる指標のパフォーマンスを比較できます。
title: 主要指標の概要
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 94%

---

# 主要指標の概要 {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="主要指標の概要"
>abstract="折れ線グラフ、変更概要グラフおよび数値の概要グラフを組み合わせたビジュアライゼーションを作成します。このビジュアライゼーションを使用すると、2 つの期間での重要な指標のトレンドを比較できます。"


>[!BEGINSHADEBOX]

_この記事では、_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** の主要指標の概要ビジュアライゼーションについて説明します。_<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** バージョンについて詳しくは、[主要指標の概要](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/key-metric)を参照してください。_

>[!ENDSHADEBOX]


![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 主要指標の概要]**&#x200B;ビジュアライゼーションを使用すると、1 つの期間内で重要な指標のトレンドを確認できます。また、2 つの期間にわたる指標のパフォーマンスを比較することもできます。次のような複数のビジュアライゼーションが 1 つのビジュアライゼーションに統合されるメリットがあります。

* プライマリ日付範囲と比較日付範囲での指標のトレンドを表示する&#x200B;**[!UICONTROL 折れ線グラフ]**&#x200B;ビジュアライゼーション

* プライマリ日付範囲と比較日付範囲の間の指標の増減を示す&#x200B;**[!UICONTROL 変化率の概要]**

* 指標の現在の合計値（[!UICONTROL **数値概要**]）

## ユースケース

このビジュアライゼーションは、次のような様々な一般的なユースケースに対応しています。

* アナリストは前年の同じ期間と比較して今月の機会創出の様相を把握しようとしています。

* マーケターは特定のリードタイプのリードジェネレーションが今月から先月にかけてどのように変化したかを調べています。

* エグゼクティブは新規予約が今四半期から前四半期にどのように変化したかを理解したいと考えています。

## 使用

1. ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 主要指標の概要]**&#x200B;ビジュアライゼーションを追加します。 [パネルへのビジュアライゼーションの追加](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。

1. **[!UICONTROL 指標]**、**[!UICONTROL 比較日付範囲]** **[!UICONTROL 、（プライマリ日付範囲]** （オプション）および **[!UICONTROL セグメント]** （オプション）を選択して、ビジュアライゼーションを設定します。

   ![指標、プライマリ日付範囲、比較日付範囲およびセグメントのオプションを表示する主要指標の設定。](assets/key-metrics-config.png)

   | オプション | 説明 |
   | --- | --- |
   | **[!UICONTROL 指標]** | 調査の対象となる指標を選択します。すべての指標がサポートされています。 |
   | **[!UICONTROL プライマリ日付範囲]** | フリーフォームテーブルの現在の日付範囲。<p>データビューで使用可能な日付範囲から選択します。</p> <p>ビジュアライゼーションがあるパネルで使用されているのと同じ日付範囲を使用する場合は、「[!UICONTROL **パネルの日付範囲**]」を選択します。</p> |
   | **[!UICONTROL 比較日付範囲]** | プライマリ日付範囲の比較対象となる日付範囲。 |
   | **[!UICONTROL セグメント (オプション)]** | この概要で関心のあるセグメント。 |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >「[!UICONTROL **プライマリ日付範囲**]」フィールドが&#x200B;[!UICONTROL **パネル日付範囲**]&#x200B;に設定されている場合、選択した&#x200B;**[!UICONTROL 比較日付範囲]**&#x200B;オプションがプライマリ日付範囲に対して相対的であるか固定であるかに応じて、**[!UICONTROL 比較日付範囲]**&#x200B;が自動的に更新されます。
   >
   >* **相対的**：「**[!UICONTROL 比較日付範囲]**」フィールドがプライマリ日付範囲に相対的なオプション（[!UICONTROL **前日**]、[!UICONTROL **先週の同じ日**]、[!UICONTROL **4 週間前の同じ日**]&#x200B;など）に設定されている場合、「[!UICONTROL **プライマリ日付範囲**]」フィールドを更新すると、**[!UICONTROL 比較日付範囲]**&#x200B;はパネル日付範囲の直後の期間に自動的に更新されます。
   >* **固定：**「[!UICONTROL **比較日付範囲**]」フィールドが固定日付範囲（**2023年2月3日（PT）**&#x200B;など）に設定されている場合、「[!UICONTROL **プライマリ日付範囲**]」フィールドまたはパネル日付範囲に行われた変更は&#x200B;[!UICONTROL **比較日付範囲**]&#x200B;に影響しません。ただし、パネル日付範囲を更新すると、[!UICONTROL **プライマリ日付範囲**]&#x200B;が自動的に更新されます。

1. 「**[!UICONTROL 作成]**」を選択します。

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

主要指標の概要の出力は次のようになります。

![指標、変更の概要、数値の概要、折れ線グラフを表示する主要指標の出力。](assets/key-metrics.png)

出力を表示する際は、次の点を考慮してください。

* **[!UICONTROL 前の期間]**&#x200B;の折れ線グラフ（常にグレーで表示）は、設定手順の&#x200B;**[!UICONTROL 比較日付範囲]**&#x200B;に対応しています。

* 比較日付範囲が設定時に指定されていない場合やビジュアライゼーション設定で非表示になっている場合は、プライマリ日付範囲の折れ線グラフのみが表示されます。 変更の概要は非表示になります。

* ここから、折れ線グラフの上にマウスポインターを置くと、個々の日の統計情報を表示できます。


## 設定

ビジュアライゼーションを作成した後、元の設定を編集できます。

1. ビジュアライゼーションの上部にある ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL ビジュアライゼーションを設定]**&#x200B;を選択します。

   元の設定ダイアログに戻ります。

1. 必要に応じて設定を変更します。現在の設定をリセットするには、「**[!UICONTROL リセット]**」を選択します。「**[!UICONTROL 作成]**」を選択して、ビジュアライゼーションを再作成します。

## 設定

ビジュアライゼーション設定の一部として、特定の主要指標の概要設定を使用できます。

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 変化率を強調]** | ビジュアライゼーションの中央に目立つ太字で変更概要を表示します |
| **[!UICONTROL 数値を強調]** | ビジュアライゼーションの中央に目立つ太字で数値概要を表示します |
| **[!UICONTROL 凡例を表示]** | ビジュアライゼーションの下部に凡例を表示または非表示にします |
| **[!UICONTROL 注釈を表示]** | 管理者に追加された注釈を表示または非表示にします |
| **[!UICONTROL タイトルを非表示]** | ビジュアライゼーションのタイトルを非表示にします。 |
| **[!UICONTROL 割合 (％)]** | ビジュアライゼーションを数値ではなく割合で表示します。 |
| **[!UICONTROL トレンドラインを表示]** | ビジュアライゼーションにトレンドラインを表示します。 |
| **[!UICONTROL トレンドラインに最大値と最小値を表示]** | プライマリ折れ線グラフと比較折れ線グラフの最小値と最大値を表示または非表示 |
| **[!UICONTROL 比較率とトレンドラインを表示]** | 比較データを表示または非表示にします。 非表示の場合、比較折れ線グラフと変更概要オブジェクトの両方が非表示になります。 |
| **[!UICONTROL 合計数を表示]** | 数値概要を表示または非表示 |
| **[!UICONTROL 生の差異を表示]** | プライマリ日付範囲とセカンダリ日付範囲の指標の合計値の生の差異を表示または非表示 |
| **[!UICONTROL 値を短縮]** | 数値をインテリジェントに短縮するには、「**[!UICONTROL 値を短縮]**」を選択します。選択した場合、短縮の量を定義する数値を入力します。次に例を示します。<br/><table><tr><td>**元の値**</td><td>**短縮**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選択</td><td align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>選択済み、1 に設定</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、2 に設定</td><td align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、2 に設定</td><td align="right">$12.011M</td></tr><tr><td>$12,011,141.25</td><td>選択、3 に設定</td><td align="right">$12.011M</td></tr></table> |

## ビジュアライゼーションの編集

ビジュアライゼーションを作成したら、元の設定を編集できます。

1. ビジュアライゼーションの右上隅にある「![ 編集 ](/help/assets/icons/Edit.svg)」を選択します。

   元の [ 設定ビュー ](#configure) に戻ります。

1. 必要に応じて、指標、プライマリ日付範囲、比較日付範囲またはセグメントを変更します。

>[!MORELIKETHIS]
>
>[パネルへのビジュアライゼーションの追加](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[ビジュアライゼーション設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[ビジュアライゼーションコンテキストメニュー](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
