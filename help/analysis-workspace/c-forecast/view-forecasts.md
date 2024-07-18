---
description: テーブルまたは折れ線グラフで予測を表示する方法を説明します。
title: Analysis Workspaceでの需要予測の表示方法
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: fea1b12a594a820ab2e55f850ca95c5a373184f0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Analysis Workspace での予測表示

予測は、フリーフォームテーブルまたは折れ線グラフで表示できます。

## テーブルでの予測の表示

時系列フリーフォームテーブルで予測を表示できます。 [ ユーザー環境設定 ](../user-preferences.md) のフリーフォームテーブルで [!UICONTROL  予測を表示 ] が有効になっている場合、テーブルに追加された最初の指標列に対して予測が自動的に表示されます。 その他の列に対して：

1. 列ヘッダーの列設定アイコン ![ 列設定 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) を選択し、オプションのリストで **[!UICONTROL 予測を表示]** が選択されていることを確認します。 詳しくは、[列設定](../visualizations/freeform-table/column-row-settings/column-settings.md)を参照してください。

1. **[!UICONTROL 列設定]** メニューの外側をクリックして、設定を保存し、更新したテーブルを表示します。

表は、下記の通り業績予想を示しております。

![ テーブルに予測を表示 ](assets/show-forecast-table.png)

* 各セルの予測値とパーセンテージが **ダークグレー** で表示されます。
* 予測値を示すには、予測記号 <img src="./assets/forecast.svg" alt="予測記号" width="20" /> は、セルの右上隅に表示されます。


## 折れ線グラフで予測を表示

折れ線グラフは、予測を表示できる唯一のビジュアライゼーションです。

1. ビジュアライゼーションヘッダーで設定アイコン ![ 列設定 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) を選択し、オプションのリストで **[!UICONTROL 予測を表示]** が選択されていることを確認します。

1. （オプション）予測でグラフのスケールを適切に設定するには、「**[!UICONTROL 予測で Y 軸のスケールを設定する]**」を選択します。 読みにくいグラフがレンダリングされる場合があるので、このオプションは、デフォルトでは選択されていません。

1. **[!UICONTROL 設定]** メニューの外側をクリックして、更新された折れ線グラフを表示します。

なお、予測は折れ線グラフで以下のように表示しています。

![ 折れ線グラフに予測を表示 ](assets/show-forecast-linechart.png)

* 折れ線グラフ内の指標の現在の値は、縦棒で示されます。 この縦線の上にマウスポインターを置くと、最新の日付を含むポップアップが表示されます。
* 1 つ以上の指標の予測値が、点線を使用して垂直バーから直接表示されます。 指標の任意のデータポイントにポインタを合わせることができます。 次のポップアップが表示されます。
   * 予測の日付
   * 指標の予測値
   * 指標の予測値の上限
   * 指標の予測値の下限
* 影になっている部分は、予測の信頼帯を示しています。
