---
description: Analysis Workspace でプロジェクトを作成する方法を学ぶ
title: プロジェクトの作成
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '602'
ht-degree: 100%

---

# プロジェクトの作成

Analysis Workspace の[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)を使用すると、組織内外の関係者と共有できるビジネスクリティカルな分析を表示できます。

Analysis Workspace を使って開始する方法の一般情報について詳しくは、[Analysis Workspace の概要](/help/analysis-workspace/home.md)を参照してください。

次の節では、プロジェクトを作成し、任意の Analysis Workspace プロジェクトの主要な構成要素（パネル、ビジュアライゼーション、コンポーネント）の追加を開始する方法について説明します。

## プロジェクトの作成を開始

1. Adobe Analytics で、「[!UICONTROL **Workspace**]」を選択します。

1. 「[!UICONTROL **Workspace**]」タブで、ページの左側にある「[!UICONTROL **プロジェクト**]」タブを選択し、「[!UICONTROL **プロジェクトを作成**]」を選択します。

1. 空のプロジェクトまたは空のモバイルスコアカードのどちらを作成するかを選択します。

   * ブラウザーから分析を共有する予定の場合、**空のプロジェクト**&#x200B;を選択します。
   * Adobe Analytics ダッシュボードモバイルアプリから分析を共有する予定の場合、[**空のモバイルスコアカード**](/help/mobile-app/curator.md)&#x200B;を選択します。

1. 「[!UICONTROL **作成**]」を選択します。

1. 次に、パネル、ビジュアライゼーションおよびコンポーネントをプロジェクトに追加する必要があります。まず、[プロジェクトへのパネルの追加](#add-panels-to-the-project)の説明に従って、Analysis Workspace のプロジェクトにパネルを追加します。その後、任意のパネルにビジュアライゼーションを追加できます。最後に、任意のパネルまたはビジュアライゼーションにコンポーネントを追加できます。

## プロジェクトへのパネルの追加 {#panels}

[パネル](/help/analysis-workspace/c-panels/panels.md)は、Analysis Workspace の任意のプロジェクトの基盤です。パネルを使用して、プロジェクトのコンテンツ（ビジュアライゼーションやコンポーネント）を整理します。

Analysis Workspace で提供される多くのパネルは、いくつかのユーザー入力に基づいてフルセットの分析を生成します。

パネルを追加するには、次の手順に従います。

1. 左側のパネルの&#x200B;[!UICONTROL **パネル**]&#x200B;アイコンを選択します。

   ![パネルを選択アイコンおよび使用可能なパネルのリスト。](assets/build-panels.png)

1. 追加するパネルを検索します。左側のパネルに表示されたら、プロジェクトにドラッグします。

1. [プロジェクトへのビジュアライゼーションの追加](#add-visualizations-to-the-project)の説明に従って、パネルにビジュアライゼーションを追加します。

   または、[プロジェクトへのコンポーネントの追加](#add-components-to-the-project)の説明に従って、コンポーネントをパネルに直接追加できます。

## プロジェクトへのビジュアライゼーションの追加

[ビジュアライゼーション](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)（フリーフォームテーブル、棒グラフ、折れ線グラフなど）を使用して、データを視覚的に活用できます。

>[!TIP]
>
>フリーフォームテーブルは、最も一般的なタイプのビジュアライゼーションで、インタラクティブなデータ分析の基盤となります。Analysis Workspace でフリーフォームテーブルを使用する方法について詳しくは、[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)を参照してください。

ビジュアライゼーションを追加するには、次の手順に従います。

1. 左側のパネルの&#x200B;**[!UICONTROL ビジュアライゼーション]**&#x200B;アイコンを選択します。

   ![選択したビジュアライゼーションアイコンおよび使用可能なビジュアライゼーションのリスト。](assets/build-visualizations.png)

1. 追加するビジュアライゼーションを検索します。左側のパネルに表示されたら、プロジェクト内のパネルにドラッグします。

1. [プロジェクトへのコンポーネントの追加](#add-components-to-the-project)の説明に従って、ビジュアライゼーションにコンポーネントを追加します。

## プロジェクトへのコンポーネントの追加

[コンポーネント](/help/components/overview.md)は、プロジェクトの実際のデータを構成します。コンポーネントをビジュアライゼーションまたはパネルに追加できます。

>[!TIP]
>
>各コンポーネントについて詳しくは、左側のパネルでコンポーネントの名前の横にある情報アイコンを選択するか、[コンポーネントの概要](/help/components/overview.md)を参照してください。

コンポーネントを追加するには、次の手順に従います。

1. 左側のパネルにある&#x200B;**[!UICONTROL コンポーネント]**&#x200B;アイコンを選択します。

   ![選択したコンポーネントアイコンおよび使用可能なディメンションのリスト。](assets/build-components.png)

1. 追加するコンポーネントを検索します。左側のパネルに表示されたら、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. （オプション）[プロジェクトの保存と共有](#save-and-share-the-project)の説明に従って、プロジェクトを共有します。

## プロジェクトの保存と共有

Analysis Workspace で分析を作成すると、作業内容は[自動保存](/help/analysis-workspace/build-workspace-project/save-projects.md)されます。

プロジェクトの作成が完了し、実用的なインサイトを収集すると、そのプロジェクトを他のユーザーが使用できる準備が整います。プロジェクトは、組織内のユーザーやグループだけでなく、組織外の人物と共有することもできます。プロジェクトの共有について詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)を参照してください。
