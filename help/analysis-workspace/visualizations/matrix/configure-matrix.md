---
title: Analysis Workspaceでの行列ビジュアライゼーションの設定
description: Customer Journey Analytics Analysis Workspaceで行列ビジュアライゼーションを設定する方法について説明します。これには、コンポーネント、表示オプション、設定が含まれます。
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 4%
---

# 行列ビジュアライゼーションの設定

マトリックスのビジュアライゼーションは、2つのディメンションのディメンション項目がどのように重なり、相互に関連付けられるかを示す値のグリッドです。 各セルには、行のディメンション項目と列のディメンション項目との交点が表示されます。

![行列の可視化](assets/matrix-overview.png)

## マトリックスの概要

行列の可視化について詳しくは、[行列の概要](/help/analysis-workspace/visualizations/matrix/matrix.md)を参照してください。

* 主な特長

* 潜在的なインサイト

* 行列、フリーフォームテーブル、ベン、散布図の違い

## 行列ビジュアライゼーションの作成

1. プロジェクトに空のパネルを追加し、左側のパネルで「[!UICONTROL **ビジュアライゼーション**]」アイコンを選択してから、[!UICONTROL **マトリックス**] ビジュアライゼーションをパネルにドラッグします。<!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   または

   [ ビジュアライゼーションの概要](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)の「[ ビジュアライゼーションをパネル ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)に追加」セクションで説明されている方法で、行列ビジュアライゼーションを追加します。

   <!-- add screenshot of the Matrix configuration fields -->

1. 次の情報を指定して、行列のビジュアライゼーションを設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **行ディメンション**] | 項目が行列の行として表示されるディメンション。 |
   | [!UICONTROL **列ディメンション**] | 項目が行列の列として表示されるディメンション。 <p>行ディメンションと列ディメンションの両方に同じディメンションを選択した場合、行列のビジュアライゼーションはディメンション項目を互いに比較します。 例えば、両方のディメンションが&#x200B;_デバイスタイプ_&#x200B;の場合、各セルには、2つのデバイスタイプ（_携帯電話_&#x200B;や&#x200B;_タブレット_&#x200B;など）の重複または相関関係が表示されます。 対角線上と対角線下の値は互いにミラーされます。</p> |
   | [!UICONTROL **指標**] | 行ディメンション項目と列ディメンション項目の組み合わせについて、各セルが示す指標。 |
   | [!UICONTROL **コンテナ**] | 行ディメンション項目と列ディメンション項目の重複の範囲を決定するコンテナ。 （コンテナ名が以下に示すデフォルト名と異なる場合は、データビューでカスタマイズされています）<ul><li>**人物：** （デフォルト）行ディメンション項目と列ディメンション項目が、同じ人物に対して任意の数のセッションで発生した場合に重なります。</li><li>**セッション：**&#x200B;行ディメンション項目と列ディメンション項目が同じセッションで発生した場合に重なります。</li><li>**イベント：**&#x200B;行ディメンション項目と列ディメンション項目が、同じイベントで発生した場合に重なります。</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. （オプション）次のいずれかの設定を変更します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **行数の上限**] | 行列ビジュアライゼーションで表示される最大行数。 デフォルトは10です。<!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **重なりパレット**] | マトリックスに[重複数](#view-overlap-count-or-correlation-strength)が表示されているときのセルのカラースケール。 |
   | [!UICONTROL **相関関係パレット**] | マトリックスに[相関強度](#view-overlap-count-or-correlation-strength)が表示されているときのセルのカラースケール。 負と正の相関関係は異なる色を使用します。 |
   | [!UICONTROL **相関精度**] | **[!UICONTROL 日]**&#x200B;など、[相関強度](#view-overlap-count-or-correlation-strength)の計算に使用される時間粒度。 この値は、パネルの日付範囲に基づいて自動的に設定されます。 それを変更することはできません。 <p>パネルの日付範囲に応じて、次の精度が選択されます。</p><ul><li>[!UICONTROL **時間**]:7日以内の日付範囲で選択されました</li><li>[!UICONTROL **日**]:7日を超える期間、最大3か月の期間で選択されました</li><li>[!UICONTROL **週**]:3か月を超える期間（最大1年）に選択された日付</li><li>[!UICONTROL **月**]: 1年を超える日付範囲で選択されました</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **対角線のセル値**] | 行列のビジュアライゼーションで、ディメンション項目が自身を満たすセルを表示する方法。 この設定は、行ディメンションと列ディメンションが同じ場合にのみ使用できます。<ul><li>**[!UICONTROL Show]:**&#x200B;値を表示します。</li><li>**[!UICONTROL Dash]:**&#x200B;値の代わりにダッシュが表示されます。</li><li>**[!UICONTROL 空白]:** セルを空のままにします。</li></ul> |

1. 「[!UICONTROL **作成**]」を選択します。

   <!-- add screenshot -->

1. 次の節に進み、[重複数または相関強度を表示](#view-overlap-count-or-correlation-strength)します。

## 重複カウントまたは相関強度の表示

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="重複数と相関強度の比較"
>abstract="<p>**重複数**&#x200B;は、行ディメンション項目と列ディメンション項目が重複する、選択した指標の値です。</p><p>**相関強度**&#x200B;は、2つのディメンション項目の指標が時間の経過とともにどの程度近く移動するかを示す–1から+1までの線形相関関係です。 値が+1の場合は、それらが一緒に立ち上がり、一緒に立ち下がることを意味し、0の場合は関係がないことを意味し、-1の場合は逆方向に移動します。 相関強度は重ね合わせとは別に計算されるので、重なり合いが少ないディメンション項目でも強い相関関係を持つことができます。</p>"

<!-- markdownlint-enable MD034 -->

マトリックスのビジュアライゼーションを切り替えて、重複数または相関強度を表示できます。 重複カウントはデフォルトで表示されます。

1. Analysis Workspaceで、行列ビジュアライゼーションを開くか、[新しいビジュアライゼーションを作成](#build-a-matrix-visualization)します。

1. 行列ビジュアライゼーションの左上隅で、次のオプションから選択します。

   * [!UICONTROL **重複数**]：各列ディメンション項目を含む各行ディメンション項目の重複数を表示します。 各セルには、両方のディメンション項目が発生する人物、セッション、またはイベント（コンテナに応じて）に対して、選択した指標の値が表示されます。

   * [!UICONTROL **相関強度**]：各行ディメンション項目と各列ディメンション項目に対して選択した指標が、パネルの日付範囲でどの程度密接に移動するかを、-1 ～ +1の線形相関関係として示します。 値+1は、2つのディメンション項目が常に一緒に上昇して落下することを意味し、0は関係がないことを意味し、-1は常に逆方向に移動することを意味します。 相関強度は重ね合わせとは別に計算されるので、重なり合いが少ないディメンション項目でも強い相関関係を持つことができます。 相関関係は、[!UICONTROL **相関精度**]&#x200B;設定に表示されている時間の精度で計算されます。<!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   マトリックスのビジュアライゼーションの右上隅にある凡例は、現在のビューのカラースケールを示します。重なり数の場合は低から高、相関強度の場合は負（–1）から正（+1）です。

## インサイトの表示

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

行列ビジュアライゼーションの下部にあるinsight カードは、行列データ内の注目すべきパターンを記述します。

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

インサイトを表示するには：

1. 行列ビジュアライゼーションで、ビジュアライゼーションの下部にあるinsight カードを表示します。

1. Insightカードの矢印を使用して、利用可能なインサイトを確認します。

## 行列の設定の編集

行列ビジュアライゼーションを作成した後、ディメンション、指標、コンテナなどの設定を変更できます。

行列の設定を編集するには：

1. 行列ビジュアライゼーションで、ビジュアライゼーションの上部にある字幕の横にある![編集](/help/assets/icons/Edit.svg)を選択します。 サブタイトルには、指標やディメンションなどの現在の設定が要約されます。

1. [行列ビジュアライゼーションの作成](#build-a-matrix-visualization)で説明されているいずれかの設定を変更します。

1. 「[!UICONTROL **作成**]」を選択します。

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## トレンドデータの表示

[行のビジュアライゼーション ](/help/analysis-workspace/visualizations/line.md)で、セルの傾向データを表示できます。 線のビジュアライゼーションは、選択した指標がパネルの日付範囲でどのように変化するかを示します。 表示される行は、行列が[重複数または相関強度](#view-overlap-count-or-correlation-strength)を示すかどうかに応じて異なります。

トレンドデータを表示するには：

1. 行列ビジュアライゼーションで、トレンドデータを表示するセルを右クリックします。

1. 「[!UICONTROL **トレンド**]」を選択します。

   行列ビジュアライゼーションの上にあるパネルに線ビジュアライゼーションが追加されます。

   * [!UICONTROL **重複数**]：選択した指標が1行に表示され、行ディメンション項目と列ディメンション項目の両方でフィルタリングされます。

   * [!UICONTROL **相関強度**]：選択した指標を2行に表示します。1行は行ディメンション項目、1行は列ディメンション項目を示します。 線を比較して、2つのディメンション項目がどれだけ近い傾向を持っているかを確認します。

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## ベンのビジュアライゼーションで重複を表示する

[ ベン ビジュアライゼーション ](/help/analysis-workspace/visualizations/venn.md)では、行ディメンション項目とセルの列ディメンション項目の重なりを表示できます。

行列のビジュアライゼーションまたはベンのビジュアライゼーションを使用するタイミングについて詳しくは、[行列の概要](/help/analysis-workspace/visualizations/matrix/matrix.md)の行列、フリーフォームテーブル、ベンまたは散布図のビジュアライゼーション ](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations)を参照してください。[

ベンのビジュアライゼーションでオーバーラップを表示するには：

1. 行列ビジュアライゼーションで、重なり合うセルを右クリックします。

1. 「[!UICONTROL **ベンで表示**]」を選択します。

   ベンのビジュアライゼーションがパネルに追加されます。 1つの円は行ディメンション項目を表し、もう1つの円は列ディメンション項目を表します。 ベンのビジュアライゼーションでは、マトリックスのビジュアライゼーションと同じ指標を使用します。<!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## 分類の適用

セルのデータを別のディメンションで分類して、セル値に貢献するディメンション項目を確認できます。

分類を適用するには：

1. 行列ビジュアライゼーションで、分類を適用するセルを右クリックします。

1. 「[!UICONTROL **分類**]」を選択します。

1. 分類に使用するディメンションを選択します。

   分類ディメンションの上位ディメンション項目が、新しいフリーフォームテーブルに表示されます。<!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


