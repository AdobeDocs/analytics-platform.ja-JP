---
description: Analysis Workspace でプロジェクトを作成する方法について説明します。
title: プロジェクトの作成
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
TQID: https://experienceleague.adobe.com/DWTWJ2Bd9iEPO2awiiOLcUzUGPc-clZul3dNFcyWvxk
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 459
ht-degree: 88%

---

# プロジェクトの作成 {#create-projects}


Analysis Workspace の[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)を使用すると、ビジネスクリティカルな分析を作成および表示できます。  これらの分析は、組織内外の関係者と共有できます。

1. Customer Journey Analytics で、「**[!UICONTROL Workspace]**」を選択します。

1. 左パネルで「**[!UICONTROL プロジェクト]**」を選択し、「**[!UICONTROL プロジェクトを作成]**」を選択します。

1. 「**空の Workspace プロジェクト**」を選択し、ブラウザーを使用してWorkspace プロジェクトを作成します。

   モバイルアプリを使用して他の関係者と共有できるモバイルスコアカードプロジェクトを作成する方法について詳しくは、[空のモバイルスコアカード](/help/mobile-app/curator.md)を参照してください。 また、ガイド付き分析プロジェクトの作成に使用できる様々なオプションについて詳しくは、[ガイド付き分析](/help/guided-analysis/overview.md)を参照してください。

1. 「[!UICONTROL **作成**]」を選択します。


空の Workspace プロジェクトを作成したので、[Analysis Workspace](/help/analysis-workspace/home.md) のユーザーインターフェイスをもう理解できたはずです。 理解できていれば、自分のプロジェクトを構築できます。 それには、次の手順を実行します。

![サンプルプロジェクト](assets/example-project.png)

* プロジェクトに[パネル](/help/analysis-workspace/c-panels/panels.md)を追加します。 例えば、 **[!DNL Example Panel]** は ➊ です。

* パネルに[ビジュアライゼーション](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)を追加します。 例：
   * **[!DNL Line Graph]**[&#x200B;折れ線グラフ](/help/analysis-workspace/visualizations/line.md)ビジュアライゼーション➋
   * **[!DNL Countries]**[&#x200B;フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)ビジュアライゼーション➌
* ビジュアライゼーションに[コンポーネント](/help/components/overview.md)を追加します。 例：
   * **[!DNL Store Country]**[&#x200B;ディメンション](/help/components/dimensions/overview.md)➍
   * **[!DNL People]**[&#x200B;指標](/help/components/apply-create-metrics.md)➎
   * **[!DNL Avg Order Value]**[&#x200B;計算指標](/help/components/calc-metrics/calc-metr-overview.md)➏
   * **[!DNL Mobile App Sessions]**[&#x200B;セグメント](/help/components/segments/seg-overview.md)➐
   * **[!DNL Last Month]**[&#x200B;日付範囲](/help/components/date-ranges/overview.md)➑
   * **[!DNL Example]**[&#x200B;注釈](/help/components/annotations/overview.md)➒


## プロジェクト情報および設定 {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="繰り返しインスタンスをカウント"
>abstract="レポート内で繰り返しインスタンスがカウントされるかどうかを指定します。<br/><br/>メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。"

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="繰り返しインスタンスをカウント"
>abstract="レポート内で繰り返しインスタンスがカウントされるかどうかを指定します。<br/>メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。"


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="コメントを許可"
>abstract="有効にすると、Analysis Workspace でプロジェクトの右側のパネルにコメント領域が表示されます。"


プロジェクト設定は、現在アクティブなプロジェクトに関するプロジェクトレベルの情報を提供します。

![プロジェクト情報および設定ウィンドウ](./assets/projectinfo.png)。

「設定」には次の項目が含まれます。

| 設定 | 説明 |
|---|---|
| プロジェクト名 | プロジェクトに指定された名前。 名前をダブルクリックして編集できます。 |
| 所有者 | プロジェクト所有者名 |
| 最終変更日 | プロジェクトの最終変更日。 |
| タグ | プロジェクトに適用されているタグを一覧表示して、分類を容易にします。 |
| 説明 | 説明は、プロジェクトの目的を明確にするのに役立ちます。 説明をダブルクリックして編集できます。 |
| 繰り返しインスタンスをカウント | レポート内でレポートインスタンスがカウントされるかどうかを指定します。 メモ：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。 |
| 注釈を表示 | このプロジェクトに対して注釈を表示するかどうかを指定します。 |
| [プロジェクトカラーパレット](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Workspace で使用する分類カラーパレットを変更するには、色弱のユーザー向け用に最適化されている既定のパレットを選択するか、カスタムパレットを指定します。 この機能は、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。 |
| [表示密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 左パネル、フリーフォームテーブル、コホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。 |
| コメントを許可 | このオプションが有効になっている場合、Analysis Workspace のプロジェクトの右側のパネルでコメント領域が使用できます。 詳しくは、[プロジェクトへのコメントの追加と管理](/help/analysis-workspace/build-workspace-project/comment-projects.md)を参照してください。 |



