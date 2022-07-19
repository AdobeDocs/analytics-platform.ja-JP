---
title: モバイルスコアカードの注釈
description: モバイルスコアカードで注釈を表示する方法を説明します。
role: User, Admin
solution: Customer Journey Analytics
feature: Components
exl-id: c0f276b4-3514-4f93-8b6c-6896eb4da6e4
source-git-commit: 702d03b95b6689e1441fbdd8b2ef3a5a3fcfbad0
workflow-type: ht
source-wordcount: '367'
ht-degree: 100%

---


# モバイルスコアカードで注釈を共有

ワークスペースで作成された注釈をモバイルスコアカードに表示できます。これにより、組織とキャンペーンに関するコンテキストデータのニュアンスやインサイトを、モバイルスコアカードプロジェクト内で直接共有でき、Analytics ダッシュボードモバイルアプリで表示できます。

## モバイルスコアカードに注釈を表示

モバイルスコアカードに注釈を表示するには、まずワークスペースプロジェクトまたはコンポーネントメニューから注釈を作成します。

注釈の作成について詳しくは、[注釈を作成](create-annotations.md)を参照してください。モバイルスコアカードでは、注釈はデフォルトで無効になっており、モバイルスコアカードで表示する各スコアカードに対して有効にする必要があります。

1. 注釈を有効にします。注釈を有効にするには、[注釈の有効／無効の切り替え](overview.md#annotations-on-off)を参照してください。

1. 注釈を作成し、すべてのプロジェクトで共有されていることを確認します。ワークスペースで注釈を作成するには、[注釈を作成](create-annotations.md)を参照してください。

1. **[!UICONTROL 注釈を表示]**&#x200B;を選択し、モバイルスコアカードに注釈を表示します。

   ![](assets/show-annotations.png)

1. 「注釈を表示」が選択されていることを確認し、**[!UICONTROL プロジェクト]**／**[!UICONTROL プロジェクト情報と設定]**&#x200B;に移動します。

   ![](assets/project-info-settings.png)

## モバイルスコアカードで注釈を表示

注釈を有効にすると、スコアカードビルダーに注釈アイコンが表示されます。注釈は、詳細ビューのグラフとテーブルにのみ表示されます。注釈は、スコアカードのメインタイル表示には表示されません。

![](assets/view-annotations.png)

注釈アイコンが表示されている場合、ビルダーキャンバスで注釈を完全に表示したり操作したりすることはできません。プレビューモードを使用して、アプリに表示される注釈を表示し、操作します。![](assets/preview-icon.png)

注釈の色は、ワークスペースで注釈を作成する際に選択します。グレーの注釈は、複数の注釈が存在することを示しています。![](assets/gray-annotations1.png) ![](assets/gray-annotations2.png)

## グラフの注釈を表示

| 日付 | 外観 |
| --- | --- |
| **[!UICONTROL 1 日]** | ![](assets/single-day-mobile-annotations.png)<br></br> |
| **[!UICONTROL 日付範囲]** | ![](assets/date-range.png) |
| **[!UICONTROL 重複する注釈]** | ![](assets/overlapping-annotations.png)<br></br>Analytics ダッシュボードアプリで注釈の詳細を表示するには、注釈アイコンをタップします。<br></br>グラフで注釈を表示している場合は、左右にスワイプして、グラフに存在するすべての注釈に移動できます。テーブルに注釈を表示しているときに、左右にスワイプすると、テーブル内のその行項目に関連付けられているすべての注釈に移動できます。<br></br>![](assets/swipe-multiple-annotations.png) <br></br>ドーナツグラフや横棒グラフなど、時間ベースの *x 軸*&#x200B;がないグラフでは、右下隅にあるアイコンをタップすると、グラフに適用する注釈を確認できます。<br></br> ![](assets/charts-without-timebase.png) |
