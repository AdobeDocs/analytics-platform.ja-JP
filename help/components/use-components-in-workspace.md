---
description: Analysis Workspaceでプロジェクトにコンポーネントを追加する方法を説明します
title: Analysis Workspace でのコンポーネントの使用
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 16%

---

# Analysis Workspace でのコンポーネントの使用

コンポーネントは、Analysis Workspaceの任意のプロジェクトの実際のデータを構成します。 コンポーネントは、ディメンション、指標、フィルターおよび日付範囲で構成されています。 コンポーネントをビジュアライゼーションまたはパネルにドラッグすることで、プロジェクトに追加できます。

追加できるコンポーネントのタイプについて詳しくは、[ コンポーネントの概要 ](/help/components/overview.md) を参照してください。

>[!TIP]
>
>各コンポーネントについて詳しくは、Analysis Workspaceの左側のパネルでコンポーネント名の横にある情報アイコンをクリックしてください。

## プロジェクトへのコンポーネントの追加の開始

1. [Analysis Workspaceでプロジェクトを作成します ](/help/analysis-workspace/build-workspace-project/create-projects.md) まだ作成していない場合は。

1. Analysis Workspaceのプロジェクトに [ パネルを追加 ](/help/analysis-workspace/c-panels/panels.md) または [ ビジュアライゼーションを追加 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) します。

   空のプロジェクトにコンポーネントを追加すると、フリーフォームテーブル ビジュアライゼーションが自動的に作成されます。

1. 左側のパネルにある&#x200B;**[!UICONTROL コンポーネント]**&#x200B;アイコンを選択します。

   ![](assets/build-components.png)

1. 追加するコンポーネントまでスクロールまたは検索し、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. （任意）コンポーネントをパネルヘッダーのフィルタードロップゾーンにドラッグします。

   フィルターは、パネル内のすべてのコンテンツに適用されます。

   パネル上でフィルタードロップゾーンを使用してパネルをフィルタリングする方法について詳しくは、「[ パネルの概要 ](/help/analysis-workspace/c-panels/panels.md)」の [ ドロップゾーン ](/help/analysis-workspace/c-panels/panels.md#drop-zone) を参照してください。

   ![ドロップゾーンでのフィルターのドロップ](assets/filter-dropzone.png)

1. 詳しくは、追加するコンポーネントのタイプに応じて、次のいずれかの節に進みます。

   * [プロジェクトへのディメンションの追加](#add-dimensions-to-a-project)

   * [プロジェクトへの指標の追加](#add-metrics-to-a-project)

   * [プロジェクトへのフィルターの追加](#add-filters-to-a-project)

   * [プロジェクトへの日付範囲の追加](#add-date-ranges-to-a-project)

## プロジェクトへのディメンションの追加

[Dimension](/help/components/dimensions/overview.md) は、通常、文字列値を含むAdobe Analyticsの変数です。 一方、[指標](/help/components/calc-metrics/calc-metr-overview.md)には、ディメンションに結び付く数値が含まれます。基本レポートは、文字列値（ディメンション）の行と数値（指標）の列を示します。

1. [ プロジェクトへのコンポーネントの追加を開始 ](#begin-adding-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトへのディメンションの追加を開始します。

1. 次のいずれかの方法を選択して、ディメンションを追加し、分析するデータのタイプを決定します。

   * ディメンションをAnalysis Workspaceのビジュアライゼーション（フリーフォームテーブルなど）にドラッグします。

     ![ プロジェクトへのディメンションの追加 ](assets/add-dimensions.png)

   * 左側のパネルから 1 つ以上のディメンションをフィルタードロップゾーンにドラッグして、[ プロジェクトへのフィルターの追加 ](#add-filters-to-a-project) の説明に従って、アドホックフィルターを作成します。

1. （任意）Analysis Workspace内のディメンションおよびディメンション項目を、他のコンポーネントで分類できます。

   詳しくは、[Workspaceでのディメンションの分類 ](/help/components/dimensions/t-breakdown-fa.md) を参照してください。

Analysis Workspaceでのディメンションの使用方法について詳しくは、[ ディメンションのプレビュー ](/help/components/dimensions/view-dimensions.md)、[ ディメンションの分類 ](/help/components/dimensions/t-breakdown-fa.md) および [ 時間分割ディメンション ](/help/components/dimensions/time-parting-dimensions.md) を参照してください。

## プロジェクトへの指標の追加

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

Analysis Workspaceでプロジェクトに指標を追加するには：

1. [ プロジェクトへのコンポーネントの追加を開始 ](#begin-adding-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトに指標を追加し始めます。

1. Analysis Workspaceに指標を追加するには、次のいずれかの方法を選択します。

   * 空のフリーフォームテーブルの指標ドロップゾーンに指標をドラッグすると、プロジェクトの日付期間中のその指標のトレンドを確認できます。

     ![ プロジェクトへの指標の追加 ](assets/add-metrics.png)

   * ディメンションが存在する場合に指標をドラッグすると、その指標を各ディメンション項目と比較して確認できます。

   * 指標を既存の指標ヘッダーの上にドラッグすると、指標を置き換えることができます。

   * 指標をヘッダーの横にドラッグすると、両方の指標を並べて確認できます。

指標について詳しくは、[ 計算指標の概要 ](/help/components/calc-metrics/calc-metr-overview.md) を参照してください。

## プロジェクトへのフィルターの追加

[ フィルター ](/help/components/filters/filters-overview.md) を使用すると、特性や特定のインタラクションに基づいて訪問者のサブセットを識別できます。

Analysis Workspaceでは、次のいずれかの方法でフィルターを使用できます。

### パネルへのフィルターの追加

パネルにフィルターを追加すると、フィルターはパネル内のすべてのコンテンツに適用されます。

パネル上でフィルタードロップゾーンを使用してパネルをフィルタリングする方法について詳しくは、「[ パネルの概要 ](/help/analysis-workspace/c-panels/panels.md)」の [ ドロップゾーン ](/help/analysis-workspace/c-panels/panels.md#drop-zone) を参照してください。

### フリーフォームテーブルの列へのフィルターの追加

フリーフォームテーブルの列にフィルターを追加すると、そのフィルターはテーブル列内のすべてのコンテンツに適用されます。

### 計算指標の作成時にフィルターを使用

計算指標ビルダーでは、指標の定義内でフィルターを適用できます。

詳しくは、「[ フィルター適用済み指標 ](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md)」を参照してください。

## プロジェクトへの日付範囲の追加

[ 日付範囲 ](/help/components/date-ranges/custom-date-ranges.md) は、Analysis Workspaceでのレポート時間枠を決定します。プロジェクト内の 1 つ以上のパネルに適用できます。

各パネルには、デフォルトで日付範囲が含まれています。 パネルの日付範囲を更新する方法はいくつかあります。 Analysis Workspaceのパネルの日付範囲を更新する 1 つの方法は、日付範囲コンポーネントを左パネルからドラッグすることです。

1. [ プロジェクトへのコンポーネントの追加を開始 ](#begin-adding-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトへの日付範囲の追加を開始します。

1. 日付範囲を左側のパネルから、パネルの右上部分の現在の日付範囲にドラッグします。

   ![ 日付範囲をドロップ ](assets/daterange-drop.png)

Analysis Workspaceでのカレンダーと日付範囲の使用方法について詳しくは、[ カレンダーと日付範囲の概要 ](/help/components/date-ranges/custom-date-ranges.md) を参照してください。
