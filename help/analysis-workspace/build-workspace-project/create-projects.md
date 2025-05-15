---
description: Analysis Workspace でプロジェクトを作成する方法を学ぶ
title: プロジェクトの作成
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: fb7e0e911de2a4a702d6069ca2f53d7769ec608b
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 83%

---

# プロジェクトの作成 {#create-projects}


Analysis Workspace の[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)を使用すると、ビジネスクリティカルな分析を作成および表示できます。これらの分析は、組織内外の関係者と共有できます。

1. Customer Journey Analytics で、「**[!UICONTROL Workspace]**」を選択します。

1. 左パネルで「**[!UICONTROL プロジェクト]**」を選択し、「**[!UICONTROL プロジェクトを作成]**」を選択します。

1. 「**空の Workspace プロジェクト**」を選択し、ブラウザーを使用してWorkspace プロジェクトを作成します。

   モバイルアプリを使用して他の関係者と共有できるモバイルスコアカードプロジェクトを作成する方法について詳しくは、[空のモバイルスコアカード](/help/mobile-app/curator.md)を参照してください。また、ガイド付き分析プロジェクトの作成に使用できる様々なオプションについて詳しくは、[ガイド付き分析](/help/guided-analysis/overview.md)を参照してください。

1. 「[!UICONTROL **作成**]」を選択します。


空の Workspace プロジェクトを作成したので、[Analysis Workspace](/help/analysis-workspace/home.md) のユーザーインターフェイスをもう理解できたはずです。理解できていれば、自分のプロジェクトを構築できます。それには、次の手順を実行します。

![サンプルプロジェクト](assets/example-project.png)

* プロジェクトに[パネル](/help/analysis-workspace/c-panels/panels.md)を追加します。例えば、**[!DNL Example Panel]** は ➊ です。

* パネルに[ビジュアライゼーション](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)を追加します。例：
   * **[!DNL Line Graph]** [ 折れ線グラフ ](/help/analysis-workspace/visualizations/line.md) ビジュアライゼーション ➋
   * **[!DNL Countries]** [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ビジュアライゼーション ➌
* ビジュアライゼーションに[コンポーネント](/help/components/overview.md)を追加します。例：
   * **[!DNL Store Country]** [dimension](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [metric](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [ 計算指標 ](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [ セグメント ](/help/components/filters/filters-overview.md) ➐
   * **[!DNL Last Month]** [ 日付範囲 ](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [ 注釈 ](/help/components/annotations/overview.md) ➒


## プロジェクト情報および設定 {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="繰り返しインスタンスをカウント"
>abstract="レポート内でレポートインスタンスがカウントされるかどうかを指定します。<br/><br/>メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。"

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="繰り返しインスタンスをカウント"
>abstract="レポート内でレポートインスタンスがカウントされるかどうかを指定します。<br/>メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。"


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="コメントの許可"
>abstract="有効になっている場合、Analysis Workspace のプロジェクトの右側のパネルでコメント領域が使用できます。"


プロジェクト設定は、現在アクティブなプロジェクトに関するプロジェクトレベルの情報を提供します。

![プロジェクト情報および設定ウィンドウ](./assets/projectinfo.png)。

「設定」には次の項目が含まれます。

| 設定 | 説明 |
|---|---|
| プロジェクト名 | プロジェクトに設定された名前。名前をダブルクリックすると編集できます。 |
| 所有者 | プロジェクト所有者名 |
| 最終変更日 | プロジェクトの最終変更日。 |
| タグ | 分類を簡単にするためにプロジェクトに適用されたタグのリスト。 |
| 説明 | 説明は、プロジェクトの目的を明確にするのに役立ちます。説明をダブルクリックすると編集できます。 |
| 繰り返しインスタンスをカウント | レポート内でレポートインスタンスがカウントされるかどうかを指定します。メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。 |
| 注釈を表示 | このプロジェクトに対して注釈を表示するかどうかを指定します。 |
| [プロジェクトカラーパレット](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Workspace で使用する分類カラーパレットを変更するには、色弱のユーザー向け用に最適化されている既定のパレットを選択するか、カスタムパレットを指定します。この機能は、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。 |
| [表示密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 左パネル、フリーフォームテーブル、コホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。 |
| コメントの許可 | **メモ：** この機能は、リリースの限定的テスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analytics リリースプロセスについて詳しくは、[Customer Journey Analytics機能リリース ](/help/release-notes/releases.md) を参照してください。 <p>このオプションを有効にすると、Analysis Workspaceのプロジェクトの右側のパネルにコメント領域が表示されます。 詳しくは、[ プロジェクトへのコメントの追加と管理 ](/help/analysis-workspace/build-workspace-project/comment-projects.md) を参照してください。</p> |



