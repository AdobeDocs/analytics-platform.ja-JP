---
description: Analysis Workspace でプロジェクトを作成する方法について学ぶ
title: Analysis Workspace でのコンポーネントの使用
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 100%

---

# Analysis Workspace でのコンポーネントの使用

コンポーネントは、Analysis Workspace において、あらゆるプロジェクトの実際のデータを作成します。コンポーネントは、ディメンション、指標、セグメントおよび日付範囲で構成されています。コンポーネントをビジュアライゼーションまたはパネルにドラッグすることで、プロジェクトに追加できます。

追加できるコンポーネントのタイプについて詳しくは、[コンポーネントの概要](/help/components/overview.md)を参照してください。

>[!TIP]
>
>各コンポーネントの詳細については、![InfoOutline](/help/assets/icons/InfoOutline.svg) を使用してください。詳しくは、[コンポーネント情報](#component-info)を参照してください。

## プロジェクトへのコンポーネントの追加

1. [Analysis Workspace で新しいプロジェクトを作成します](/help/analysis-workspace/build-workspace-project/create-projects.md)。

1. Analysis Workspace のプロジェクトに[パネルを追加](/help/analysis-workspace/c-panels/panels.md#create-a-panel)するか、[ビジュアライゼーションを追加](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)します。空のプロジェクトにコンポーネントを追加すると、フリーフォームテーブルビジュアライゼーションが作成されます。

1. ボタンパネルから「![キュレート](/help/assets/icons/Curate.svg) **[!UICONTROL コンポーネント]**」を選択します。左側のパネルに、使用可能なすべてのコンポーネントが表示されます。詳しくは、[インターフェイス](/help/analysis-workspace/home.md#interface)を参照してください。

1. 追加するコンポーネントまでスクロールするか、それを検索し、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. オプションで、コンポーネントをパネルヘッダーのセグメントドロップゾーンにドラッグできます。このドラッグ＆ドロップは、コンポーネントをセグメントとして定義し、そのセグメントをパネル内のすべてのコンテンツ適用します。パネル上のセグメントドロップゾーンを使用してパネルをセグメント化する方法について詳しくは、[パネルの概要](/help/analysis-workspace/c-panels/panels.md)の[ドロップゾーン](/help/analysis-workspace/c-panels/panels.md#drop-zone)を参照してください。

1. 詳しくは、次の節を参照してください。

   * [プロジェクトへのディメンションの追加](#add-dimensions-to-a-project)

   * [プロジェクトへの指標の追加](#add-metrics-to-a-project)

   * [プロジェクトへのセグメントの追加](#add-segments-to-a-project)

   * [プロジェクトへの日付範囲の追加](#add-date-ranges-to-a-project)

### プロジェクトへのディメンションの追加

[ディメンション](/help/components/dimensions/overview.md)は、Customer Journey Analytics の変数であり、通常は文字列値を含みます。一方、[指標](/help/components/calc-metrics/calc-metr-overview.md)には、ディメンションに結び付く数値が含まれます。基本レポートは、文字列値（ディメンション）の行と数値（指標）の列を示します。

1. [プロジェクトへのコンポーネントの追加](#add-components-to-a-project)の説明に従って、まず、Analysis Workspace のプロジェクトにディメンションを追加します。

1. 次のいずれかの方法を選択して、ディメンションを追加し、分析するデータのタイプを決定します。

   ![ディメンションの追加](/help/components/assets/add-dimension.gif)

   * ディメンションを Analysis Workspace のビジュアライゼーション（フリーフォームテーブルなど）にドラッグします。

   * [プロジェクトへのセグメントの追加](#add-filters-to-a-project)の説明に従って、左側のパネルから 1 つ以上のディメンションをセグメントドロップゾーンにドラッグして、クイックセグメントを作成します。

1. オプションで、Analysis Workspace 内のディメンションおよびディメンション項目を他のコンポーネントを使って分類できます。詳しくは、[Workspace でのディメンションの分類](/help/components/dimensions/t-breakdown-fa.md)を参照してください。

Analysis Workspace でのディメンションの使用方法について詳しくは、[ディメンションのプレビュー](/help/components/dimensions/view-dimensions.md)、[ディメンションの分類](/help/components/dimensions/t-breakdown-fa.md)および[時間分割ディメンション](/help/components/dimensions/time-parting-dimensions.md)を参照してください。

### プロジェクトへの指標の追加

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

Analysis Workspace のプロジェクトに指標を追加するには

1. [プロジェクトへのコンポーネントの追加](#add-components-to-a-project)の説明に従って、Analysis Workspace のプロジェクトに指標を追加します。



1. Analysis Workspace に指標を追加するには、次のいずれかの方法を選択します。

   ![指標の追加](/help/components/assets/add-metric.gif)

   * 指標を空のフリーフォームテーブルにドラッグすると、プロジェクトの日付期間にわたる指標のトレンドを確認できます。

   * ディメンションが存在する場合に指標をドラッグすると、各ディメンジョン項目にその指標が表示されます。

   * 既存の指標ヘッダーの上に指標をドラッグすると、置き換えることができます。

   * 右側にある既存の指標ヘッダーの左端に指標をドラッグして、新しい指標を追加します。

   * 既存の指標ヘッダーの上または下に指標をドラッグして、指標の重複を作成します。


詳しくは、[指標](/help/components/apply-create-metrics.md)を参照してください。

### プロジェクトへのセグメントの追加

[セグメント](/help/components/segments/seg-overview.md)を使用すると、特性や特定のインタラクションに基づいて、ユーザー、セッションまたはイベントのサブセットを識別できます。

Analysis Workspace では、次のいずれかの方法でセグメントを使用できます。

* パネルへのセグメントの追加
パネルにセグメントを追加すると、そのセグメントはパネル内のすべてのコンテンツに適用されます。
パネル上のセグメントドロップゾーンを使用してパネルをセグメント化する方法について詳しくは、[パネルの概要](/help/analysis-workspace/c-panels/panels.md)の [ドロップゾーン](/help/analysis-workspace/c-panels/panels.md#drop-zone)を参照してください。

* ビジュアライゼーションへのセグメントの追加
フリーフォームテーブルの列にセグメントを追加すると、そのセグメントはテーブルの列内のすべてのコンテンツに適用されます。また、セグメントをフォールアウトビジュアライゼーションの一部として追加することもできます。

* コンポーネントでのセグメントの使用
[計算指標](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md)、[注釈](/help/components/annotations/create-annotations.md#annotation-builder)または[セグメント](/help/components/segments/seg-builder.md)などのコンポーネントを定義する場合、セグメントを定義の一部として使用できます。


### プロジェクトへの日付範囲の追加

[日付範囲](/help/components/date-ranges/overview.md)は、Analysis Workspace でのレポート時間枠を決定します。プロジェクト内の 1 つ以上のパネルや、一部のビジュアライゼーション（フリーフォームテーブルなど）に適用できます。

各パネルには、デフォルトで日付範囲が含まれています。パネルの日付範囲を更新するには、いくつかの方法があります。その方法の 1 つとして、左側のパネルから日付範囲コンポーネントをドラッグして、Analysis Workspace のパネルの日付範囲を更新します。

1. 必要に応じて、[プロジェクトへのパネルの追加](#add-components-to-a-project)の説明に従って、Analysis Workspace のプロジェクトに日付範囲を追加します。

1. 左側のパネルから日付範囲を次の場所にドラッグ＆ドロップします。

   * パネルの日付範囲を変更するための現在の日付範囲。

     ![日付範囲をドロップ](assets/add-date-range.gif)

   * フリーフォームテーブルビジュアライゼーションの指標またはディメンション。詳しくは、[日付範囲の使用](/help/components/date-ranges/overview.md#use-date-ranges)を参照してください。

Analysis Workspace での日付範囲の使用方法と管理方法について詳しくは、[日付範囲の概要](/help/components/date-ranges/overview.md)を参照してください。

## コンポーネント情報

任意のコンポーネントにポインターを合わせると、![詳細情報](/help/assets/icons/InfoOutline.svg)が表示されます。選択すると、コンポーネントの追加情報がポップアップで表示されます。

![コンポーネント情報](assets/component-info.png)

アクセス制御に基づいて、次の操作を実行できます。

* コンポーネントの ![ブックマーク](/help/assets/icons/Bookmark.svg) [!UICONTROL データディクショナリ]定義にアクセスします。
* コンポーネントが定義されている ![編集](/help/assets/icons/Edit.svg) コンポーネントビルダーまたはデータビューにアクセスします。
