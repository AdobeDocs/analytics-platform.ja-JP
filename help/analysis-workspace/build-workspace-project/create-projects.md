---
description: Analysis Workspace でプロジェクトを作成する方法を学ぶ
title: プロジェクトの作成
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 41%

---

# プロジェクトの作成 {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_countrepeatinstances"
>title="繰り返しインスタンスのカウント"
>abstract="レポート内でレポートインスタンスがカウントされるかどうかを指定します。<br/><br/> メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。"

<!-- markdownlint-enable MD034 -->


Analysis Workspaceの [ プロジェクト ](/help/analysis-workspace/build-workspace-project/freeform-overview.md) を使用すると、ビジネスクリティカルな分析を作成および表示できます。  これらの分析は、組織内または組織外の関係者と共有できます。

1. Customer Journey Analyticsで、「**[!UICONTROL Workspace]**」を選択します。

1. 左側のパネルで「**[!UICONTROL プロジェクト]**」を選択し、「**[!UICONTROL プロジェクトを作成]**」を選択します。

1. **空のWorkspace プロジェクト** を選択して、ブラウザーを使用してWorkspace プロジェクトを作成します。

   モバイルアプリを使用して他の関係者と共有できるモバイルスコアカードプロジェクトを作成する方法については、[ 空のモバイルスコアカード ](/help/mobile-app/curator.md) を参照してください。 また、ガイド付き分析プロジェクトの作成に使用できる様々なオプションについて詳しくは、[ ガイド付き分析 ](/help/guided-analysis/overview.md) を参照してください。

1. 「[!UICONTROL **作成**]」を選択します。


空のWorkspace プロジェクトを作成したので、[Analysis Workspace](/help/analysis-workspace/home.md) のユーザーインターフェイスをよく理解できました。 完了したら、プロジェクトを構築できます。 それには、以下の手順を実行します。

![ サンプルプロジェクト ](assets/example-project.png)

* プロジェクトに [ パネル ](/help/analysis-workspace/c-panels/panels.md) を追加します。 例えば、**[!DNL Example Panel]** は➊です。

* パネルに [ ビジュアライゼーション ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) を追加します。 次に例を示します。
   * **[!DNL Line Graph]** [ 折れ線グラフ ](/help/analysis-workspace/visualizations/line.md) ビジュアライゼーション ➋
   * **[!DNL Countries]** [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ビジュアライゼーション➌
* ビジュアライゼーションに [ コンポーネント ](/help/components/overview.md) を追加します。 次に例を示します。
   * **[!DNL Store Country]** [dimension](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [metric](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [ 計算指標 ](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [ フィルター ](/help/components/filters/filters-overview.md) ➐
   * **[!DNL Last Month]** [ 日付範囲 ](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [ 注釈 ](/help/components/annotations/overview.md) ➒


## プロジェクト情報および設定 {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="繰り返しインスタンスのカウント"
>abstract="レポート内でレポートインスタンスがカウントされるかどうかを指定します。<br/> メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。"

<!-- markdownlint-enable MD034 -->


プロジェクト設定は、現在アクティブなプロジェクトに関するプロジェクトレベルの情報を提供します。

![ プロジェクト情報および設定ウィンドウ ](./assets/projectinfo.png)

「設定」には次の項目が含まれます。

| 設定 | 説明 |
|---|---|
| プロジェクト名 | プロジェクトに設定された名前。名前をダブルクリックすると編集できます。 |
| 所有者 | プロジェクト所有者名。 |
| 最終変更日 | プロジェクトの最終変更日。 |
| タグ | 分類を簡単にするためにプロジェクトに適用されたタグのリスト。 |
| 説明 | 説明は、プロジェクトの目的を明確にするのに役立ちます。説明をダブルクリックすると編集できます。 |
| 繰り返しインスタンスのカウント | レポート内で繰り返しインスタンスをカウントするかどうかを指定します。 注意：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。 |
| 注釈を表示 | このプロジェクトの注釈を表示するかどうかを指定してください。 |
| [プロジェクトカラーパレット](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Workspace で使用する分類カラーパレットを変更するには、色弱のユーザー向け用に最適化されている既定のパレットを選択するか、カスタムパレットを指定します。この機能は、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。 |
| [表示密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 左側のパネル、フリーフォームテーブルおよびコホートテーブルの垂直方向のパディングを減らすことで、画面上に表示できるデータを増やすことができます。 |



