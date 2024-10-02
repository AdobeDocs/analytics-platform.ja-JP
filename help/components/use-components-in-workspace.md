---
description: Analysis Workspaceでプロジェクトにコンポーネントを追加する方法を説明します
title: Analysis Workspace でのコンポーネントの使用
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 590a3ddbe988d27341fe96a3fa866960d1641e24
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 7%

---

# Analysis Workspace でのコンポーネントの使用

コンポーネントは、Analysis Workspaceの任意のプロジェクトの実際のデータを構成します。 コンポーネントは、ディメンション、指標、フィルターおよび日付範囲で構成されています。 コンポーネントをビジュアライゼーションまたはパネルにドラッグすることで、プロジェクトに追加できます。

追加できるコンポーネントのタイプについて詳しくは、[ コンポーネントの概要 ](/help/components/overview.md) を参照してください。

>[!TIP]
>
>各コンポーネントの詳細については、![InfoOutline](/help/assets/icons/InfoOutline.svg) を使用してください。 詳しくは、[ コンポーネント情報 ](#component-info) を参照してください

## プロジェクトへのコンポーネントの追加

1. [Analysis Workspaceでプロジェクトを作成します ](/help/analysis-workspace/build-workspace-project/create-projects.md)。

1. Analysis Workspaceのプロジェクトに [ パネルを追加 ](/help/analysis-workspace/c-panels/panels.md#create-a-panel) または [ ビジュアライゼーションを追加 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) します。 空のプロジェクトにコンポーネントを追加すると、フリーフォームテーブルビジュアライゼーションが既に作成されています。

1. ボタンパネルから「![ キュレーション ](/help/assets/icons/Curate.svg)**[!UICONTROL コンポーネント]**」を選択します。 左側のパネルに、使用可能なすべてのコンポーネントが表示されます。 詳しくは、[ インターフェイス ](/help/analysis-workspace/home.md#interface) を参照してください。

1. 追加するコンポーネントまでスクロールするか検索し、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. オプションで、コンポーネントをパネルヘッダーのフィルタードロップゾーンにドラッグできます。 このドラッグ&amp;ドロップでは、コンポーネントがフィルターとして定義され、パネル内のすべてのコンテンツにフィルターが適用されます。
パネル上でフィルタードロップゾーンを使用してパネルをフィルタリングする方法について詳しくは、「[ パネルの概要 ](/help/analysis-workspace/c-panels/panels.md)」の [ ドロップゾーン ](/help/analysis-workspace/c-panels/panels.md#drop-zone) を参照してください。

1. 詳しくは、次の節を参照してください。

   * [プロジェクトへのディメンションの追加](#add-dimensions-to-a-project)

   * [プロジェクトへの指標の追加](#add-metrics-to-a-project)

   * [プロジェクトへのフィルターの追加](#add-filters-to-a-project)

   * [プロジェクトへの日付範囲の追加](#add-date-ranges-to-a-project)

### プロジェクトへのディメンションの追加

[Dimension](/help/components/dimensions/overview.md) は、通常、文字列値を含むCustomer Journey Analytics内の変数です。 一方、[指標](/help/components/calc-metrics/calc-metr-overview.md)には、ディメンションに結び付く数値が含まれます。基本レポートは、文字列値（ディメンション）の行と数値（指標）の列を示します。

1. [ プロジェクトへのコンポーネントの追加 ](#add-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトへのディメンションの追加を開始します。

1. 次のいずれかの方法を選択して、ディメンションを追加し、分析するデータのタイプを決定します。

   ![ ディメンションの追加 ](/help/components/assets/add-dimension.gif)

   * ディメンションをAnalysis Workspaceのビジュアライゼーション（フリーフォームテーブルなど）にドラッグします。

   * [ プロジェクトへのフィルターの追加 ](#add-filters-to-a-project) の説明に従って、左側のパネルから 1 つ以上のディメンションをフィルタードロップゾーンにドラッグして、クイックフィルターを作成します。

1. オプションで、Analysis Workspace内のディメンションおよびディメンション項目を他のコンポーネントで分類できます。 詳しくは、[Workspaceでのディメンションの分類 ](/help/components/dimensions/t-breakdown-fa.md) を参照してください。

Analysis Workspaceでのディメンションの使用方法について詳しくは、[ ディメンションのプレビュー ](/help/components/dimensions/view-dimensions.md)、[ ディメンションの分類 ](/help/components/dimensions/t-breakdown-fa.md) および [ 時間分割ディメンション ](/help/components/dimensions/time-parting-dimensions.md) を参照してください。

### プロジェクトへの指標の追加

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

Analysis Workspaceでプロジェクトに指標を追加するには：

1. [ プロジェクトへのコンポーネントの追加 ](#add-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトに指標を追加し始めます。



1. Analysis Workspaceに指標を追加するには、次のいずれかの方法を選択します。

   ![ 指標の追加 ](/help/components/assets/add-metric.gif)

   * 空のフリーフォームテーブルの指標ドロップゾーンに指標をドラッグすると、プロジェクトの日付期間中のその指標のトレンドを確認できます。

   * ディメンションが存在する場合に指標をドラッグすると、各ディメンション項目の指標を表示できます。

   * 指標を既存の指標ヘッダーの上にドラッグすると、指標を置き換えることができます。

   * 既存の指標ヘッダーの左隣にある指標をドラッグして、新しい指標を追加します。

   * 指標を既存の指標ヘッダーの上または下にドラッグして、指標の重複を作成します。


指標について詳しくは、「[ 指標 ](/help/components/apply-create-metrics.md)」を参照してください。

### プロジェクトへのフィルターの追加

[ フィルター ](/help/components/filters/filters-overview.md) を使用すると、特性や特定のインタラクションに基づいて、人物、セッションまたはイベントのサブセットを識別できます。

Analysis Workspaceでは、次のいずれかの方法でフィルターを使用できます。

* パネルへのフィルターの追加
パネルにフィルターを追加すると、フィルターはパネル内のすべてのコンテンツに適用されます。
パネル上でフィルタードロップゾーンを使用してパネルをフィルタリングする方法について詳しくは、「[ パネルの概要 ](/help/analysis-workspace/c-panels/panels.md)」の [ ドロップゾーン ](/help/analysis-workspace/c-panels/panels.md#drop-zone) を参照してください。

* ビジュアライゼーションへのフィルターの追加
フリーフォームテーブルの列にフィルターを追加すると、そのフィルターはテーブル列内のすべてのコンテンツに適用されます。 また、フォールアウトビジュアライゼーションの一部としてフィルターを追加することもできます。

* コンポーネントでのフィルターの使用
[ 計算指標 ](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md)、[ 注釈 ](/help/components/annotations/create-annotations.md#annotation-builder)、さらには [ フィルター ](/help/components/filters/filter-builder.md) などのコンポーネントを定義する場合、定義の一部としてフィルターを使用できます。


### プロジェクトへの日付範囲の追加

[ 日付範囲 ](/help/components/date-ranges/overview.md) は、Analysis Workspaceでのレポート時間枠を決定します。プロジェクト内の 1 つ以上のパネルや、一部のビジュアライゼーション（フリーフォームテーブルなど）に適用できます。

各パネルには、デフォルトで日付範囲が含まれています。 パネルの日付範囲を更新する方法はいくつかあります。 Analysis Workspaceのパネルの日付範囲を更新する 1 つの方法は、左側のパネルから日付範囲コンポーネントをドラッグすることです。

1. 必要に応じて、[ プロジェクトへのコンポーネントの追加 ](#add-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトに日付範囲を追加します。

1. 左側のパネルから日付範囲を次の場所にドラッグ&amp;ドロップします。

   * パネルの日付範囲を変更するための、現在の日付範囲。

     ![ 日付範囲のドロップ ](assets/add-date-range.gif)

   * フリーフォームテーブルビジュアライゼーションの指標またはディメンション。 詳しくは、[ データ範囲の使用 ](/help/components/date-ranges/overview.md#use-date-ranges) を参照してください。

Analysis Workspaceでの日付範囲の使用方法と管理方法について詳しくは、[ 日付範囲の概要 ](/help/components/date-ranges/overview.md) を参照してください。

## コンポーネント情報

任意のコンポーネントの上にマウスポインターを置くと、![ 詳細情報 ](/help/assets/icons/InfoOutline.svg) が表示されます。 選択すると、コンポーネントの追加情報を含むポップアップが表示されます。

![ コンポーネント情報 ](assets/component-info.png)

アクセス制御に基づいて、次の操作を実行できます。

* コンポーネントの ![ ブックマーク ](/help/assets/icons/Bookmark.svg)[!UICONTROL  データディクショナリ ] 定義にアクセスします。
* コンポーネントが定義されている ![ 編集 ](/help/assets/icons/Edit.svg) コンポーネントビルダーまたはデータビューにアクセスします。
