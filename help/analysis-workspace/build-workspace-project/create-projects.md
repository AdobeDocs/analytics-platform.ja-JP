---
description: Analysis Workspaceでプロジェクトを作成する方法を説明します。
title: プロジェクトの作成
feature: Workspace Basics
role: User, Admin
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 16f1a732260ace8393d7303134fc351740fd1661
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 14%

---

# プロジェクトの作成

[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md) Analysis Workspaceでは、組織内外の関係者と共有できる、ビジネスクリティカルな分析を表示できます。

Analysis Workspaceの使用を開始する方法に関する一般的な情報については、 [Analysis Workspaceの概要](/help/analysis-workspace/home.md).

次の節では、プロジェクトを作成し、任意のAnalysis Workspaceプロジェクトの主要な構成要素（パネル、ビジュアライゼーション、コンポーネント）の追加を開始する方法について説明します。

## プロジェクトの作成を開始する

1. Adobe Analyticsで、 [!UICONTROL **Workspace**].

1. 次の日： [!UICONTROL **Workspace**] タブで、 [!UICONTROL **プロジェクト**] 」タブで、「 [!UICONTROL **プロジェクトを作成**].

1. 空のプロジェクトと空のモバイルスコアカードのどちらを作成するかを選択します

   * **空のプロジェクト** ブラウザーから分析を共有する予定の場合
   * [**空のモバイルスコアカード**](/help/mobile-app/curator.md) Adobe Analyticsダッシュボードモバイルアプリから分析を共有する予定がある場合。

1. 「[!UICONTROL **作成**]」を選択します。

1. 次に、パネル、ビジュアライゼーションおよびコンポーネントをプロジェクトに追加する必要があります。 まず、Analysis Workspaceのプロジェクトにパネルを追加します ( [プロジェクトにパネルを追加する](#add-panels-to-the-project). その後、任意のパネルにビジュアライゼーションを追加できます。 最後に、任意のパネルまたはビジュアライゼーションにコンポーネントを追加できます。

## プロジェクトにパネルを追加する {#panels}

[パネル](/help/analysis-workspace/c-panels/panels.md) は、Analysis Workspaceの任意のプロジェクトの基盤です。 パネルを使用して、プロジェクトのコンテンツ（ビジュアライゼーションおよびコンポーネント）を整理します。

Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。

パネルを追加するには：

1. を選択します。 [!UICONTROL **パネル**] アイコンをクリックします。

   ![パネルを選択アイコンと、使用可能なパネルのリスト。](assets/build-panels.png)

1. 追加するパネルを検索します。 左側のレールに表示されたら、プロジェクトにドラッグします。

1. パネルにビジュアライゼーションを追加します ( [プロジェクトへのビジュアライゼーションの追加](#add-visualizations-to-the-project).

   または、 [プロジェクトにコンポーネントを追加する](#add-components-to-the-project).

## プロジェクトへのビジュアライゼーションの追加

[ビジュアライゼーション](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) （フリーフォームテーブル、棒グラフ、折れ線グラフなど）を使用して、データを有効にします。

>[!TIP]
>
>フリーフォームテーブルは、最も一般的なタイプのビジュアライゼーションで、インタラクティブなデータ分析の基盤となります。 Analysis Workspaceでフリーフォームテーブルを使用する方法について詳しくは、 [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

ビジュアライゼーションを追加するには：

1. を選択します。 **[!UICONTROL ビジュアライゼーション]** アイコンをクリックします。

   ![選択したビジュアライゼーションアイコンと、使用可能なビジュアライゼーションのリスト。](assets/build-visualizations.png)

1. 追加するビジュアライゼーションを検索します。 左側のレールに表示されたら、プロジェクト内のパネルにドラッグします。

1. ビジュアライゼーションにコンポーネントを追加します。詳しくは、 [プロジェクトにコンポーネントを追加する](#add-components-to-the-project).

## プロジェクトにコンポーネントを追加する

[コンポーネント](/help/components/overview.md) 任意のプロジェクトの実際のデータを構成します。 コンポーネントをビジュアライゼーションまたはパネルに追加できます。

>[!TIP]
>
>各コンポーネントについて詳しくは、左側のパネルでコンポーネントの名前の横にある情報アイコンを選択するか、 [コンポーネントの概要](/help/components/overview.md).

コンポーネントを追加するには：

1. を選択します。 **[!UICONTROL コンポーネント]** アイコンをクリックします。

   ![選択したコンポーネントアイコンと、使用可能なディメンションのリスト。](assets/build-components.png)

1. 追加するコンポーネントを検索します。 左側のパネルに表示されたら、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. （オプション） [プロジェクトを保存して共有する](#save-and-share-the-project).

## プロジェクトを保存して共有する

Analysis Workspace で分析を作成すると、作業内容は[自動保存](/help/analysis-workspace/build-workspace-project/save-projects.md)されます。

プロジェクトの作成が完了し、実用的なインサイトを収集すると、そのプロジェクトを他のユーザーが使用できる準備が整います。プロジェクトは、組織内のユーザーやグループだけでなく、組織外の人物と共有することもできます。プロジェクトの共有について詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)を参照してください。
