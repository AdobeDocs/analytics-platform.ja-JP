---
title: データビューの管理
description: データビューの管理方法について説明します。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c5cf15ab-3eb1-4e6b-93a3-3d89694ca0ea
source-git-commit: e65dd6f71c75c06aac078c22ea7d77eed75cd381
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 10%

---

# データビューの管理


[1 つ以上のデータビューを作成または編集 ](/help/data-views/create-dataview.md) したら、**[!UICONTROL データビュー]** で管理できます。

Customer Journey Analyticsのメインメニューバーから **[!UICONTROL データ管理]**/**[!UICONTROL データビュー]** を選択します。

**[!UICONTROL データビュー]** インターフェイスには、使用可能なすべてのデータビューのテーブルが表示されます。

![ データビューインターフェイス ](/help/data-views/assets/data-views.png)

テーブルでは、次の列とアイコンを使用できます。

| 列またはアイコン | 説明 |
| --- | --- |
| **[!UICONTROL 名前]** | データビューの名前。 |
| ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | データ・ビューに関する情報を表示するには、データ・ビュー名の横にある ![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択します。<br/> ポップアップウィンドウにデータビューの詳細が表示されます。 |
| ![詳細情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 「![その他](/help/assets/icons/More.svg)」を選択すると、コンテキストメニューが開きます。データビューを選択：<br/>![ 編集 ](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** して [ 編集 ](#edit-data-views) することができます。<br/>![ コピー ](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]** して [ データビューをコピー ](#copy-data-views) します。データビューを <br/>![ 削除 ](/help/assets/icons/Delete.svg)**[!UICONTROL 削除]** して [ 削除 ](#delete-data-views) します。<br/>![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL Export to CSV]** to[export the details of the data view to a CSV file](#export-data-views-to-csv).<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg)**[!UICONTROL プロジェクトを作成]** をクリックして、データビューの [ 新しいWorkspace プロジェクトを作成 ](#create-project-from-data-views) します。<br/>![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Data Insights Agentで有効にする]** をクリックして、Data Insights Agentのデータビューを有効にします。<br/>![RemoveCircle](/help/assets/icons/RemoveCircle.svg)**[!UICONTROL Data Insights Agentの無効化]** をクリックして、Data Insights Agentのデータビューを無効にします。 |
| **[!UICONTROL 接続]** | データビューに関連付けられている接続の名前。 |
| **[!UICONTROL サンドボックス]** | データビューに関連付けられているサンドボックスの名前。 |
| **[!UICONTROL 所有者]** | データビューの所有者。 |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | データビューの [0}Data Insights Agent} が ](/help/data-analysis-ai.md) 有効 **[!UICONTROL か]** 無効 **[!UICONTROL かを示します。]**<br/>![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、データビュー全体で **[!UICONTROL Data Insights Agent ステータス]** のポップアップが表示されます。 <br/>![Data Insights Agentの使用状況 ](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL 統合]** | 他のソリューションとの統合のリスト。 例：Adobe Audience Analysis、Content Analytics、Brand Concierge、Journey Optimizer、GenStudio、Usage Analytics。 |
| **[!UICONTROL CJA で使用]** | データビューがCustomer Journey Analyticsで使用されるかどうかを示します。 この値は、Adobe Journey Optimizer統合の一環として自動生成されるデータビューの場合のみ **[!UICONTROL オフ]** となります。 |
| **[!UICONTROL 作成日]** | データビューが作成されたときのタイムスタンプ。 |
| **[!UICONTROL 最終変更日]** | データビューが最後に変更されたときのタイムスタンプ。 |

テーブルに表示する列を設定するには、「![ColumnSetting](/help/assets/icons/ColumnSetting.svg)」を選択します。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログで、表示する列を選択します。 次に、「**[!UICONTROL 適用]**」を選択します。


## データビューを検索

「![ 検索 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) ボックスを使用して、データビューをすばやく検索できます。

## データビューのフィルタリング

データビューのリストにフィルターを適用するには、「![ フィルター ](/help/assets/icons/Filter.svg)」アイコンを選択し、次のフィルターオプションから選択します。

| フィルターオプション | 説明 |
|---------|----------|
| **[!UICONTROL 接続]** | 選択した接続に関連付けられているデータビューのみが表示されます。 |
| **[!UICONTROL 所有者]** | 選択したユーザーが所有するデータビューのみが表示されます。 |
| **[!UICONTROL サンドボックス]** | 選択したサンドボックスで使用可能なデータビューのみが表示されます。 |
| **[!UICONTROL 統合]** | 選択した統合を持つデータビューのみが表示されます。 |
| **[!UICONTROL CJA で使用]** | 「**[!UICONTROL オン]**」を選択すると、Customer Journey Analyticsで使用できるデータビューのみを表示します。 まだCustomer Journey Analyticsでの使用が有効になっていないデータビューのみを表示する場合は、「**[!UICONTROL オフ]**」を選択します。 |


「![ フィルター ](/help/assets/icons/Filter.svg) **[!UICONTROL フィルターを非表示]**」を選択して、フィルターウィンドウを非表示にします。

## データビューの作成

[ 新しいデータビューを作成 ](/help/data-views/create-dataview.md) するには、「**[!UICONTROL 新しいデータビューを作成]**」を選択します。


## データビューを編集

[ データビューを編集 ](/help/data-views/create-dataview.md) する場合：

1. データビュー名の横にある ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
1. コンテキストメニューから ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。

または、次の操作を実行できます。

1. データビュー行を選択します。
1. 青色のアクションバーから ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。


## データビューをコピー

データビューをコピーする場合：

1. データビュー名の横にある ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
1. コンテキストメニューから「![ コピー ](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]**」を選択します。

または、次の操作を実行できます。

1. 1 つ以上のデータビュー行を選択します。
1. 青いアクションバーから ![ コピー ](/help/assets/icons/Copy.svg) **[!UICONTROL コピー]** を選択します。

データビューがコピーされ、「**[!UICONTROL （コピー）]**」が名前に追加された状態でリストに追加されます。


## データビューの削除

データビューを削除する場合：

1. データビュー名の横にある ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
1. コンテキストメニューから「![ 削除 ](/help/assets/icons/Delete.svg)**[!UICONTROL 削除]**」を選択します。

または、次の操作を実行できます。

1. 1 つ以上のデータビュー行を選択します。
1. 青色のアクションバーから ![削除](/help/assets/icons/Delete.svg) **[!UICONTROL 削除]** を選択します。

1 つ以上のデータビューを削除すると、影響を受けるプロジェクトが **[!UICONTROL データビューを削除]** パネルに表示されます。

![ データビューを削除 ](/help/data-views/assets/delete-data-view.png)


* ➊ 確認 **[!UICONTROL では、データビューの削除の影響が表示されます。]**
* データビューを完全に削除するには、「**[!UICONTROL 削除]**」を選択します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。


## データビューを CSV に書き出し

データビューを CSV ファイルに書き出すことができます。

1. データビュー名の横にある ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
1. コンテキストメニューから ![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL Export to CSV]** を選択します。

または、次の操作を実行できます。

1. 1 つ以上のデータビュー行を選択します。
1. 青いアクションバーから ![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL Export to CSV]** を選択します。

選択したデータビューの詳細は、ブラウザーのダウンロードフォルダーにある `Data views List (x).csv` という名前の CSV ファイルに書き出されます。


## データビューからプロジェクトを作成

データビューインターフェイスから直接Workspace プロジェクトを作成できます。

1. データビュー名の横にある ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
1. コンテキストメニューから「![ プロジェクト追加 ](/help/assets/icons/ProjectAdd.svg)**[!UICONTROL プロジェクトを作成]**」を選択します。

または、次の操作を実行できます。

1. データビュー行を選択します。
1. 青いアクションバーから ![ プロジェクト追加 ](/help/assets/icons/ProjectAdd.svg)**[!UICONTROL プロジェクトを作成]** を選択します。


## Data Insights Agentのデータビューを有効または無効にする

[Data Insights Agent](/help/data-analysis-ai.md) のデータビューを有効または無効にできます。

1. データビュー名の横にある ![ 詳細 ](/help/assets/icons/More.svg) を選択します。
1. コンテキストメニューから ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Data Insights Agentに対して有効]** または ![RemoveCircle](/help/assets/icons/RemoveCircle.svg)**[!UICONTROL Data Insights Agentに対して無効]** を選択します。

または、次の操作を実行できます。

1. Data Insights Agentで無効または有効になっている 1 つ以上のデータビュー行を選択します。
1. 青いアクションバーから ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Data Insights Agentに対して有効にする]** または ![RemoveCircle](/help/assets/icons/RemoveCircle.svg)**[!UICONTROL Data Insights Agentに対して無効にする]** を選択します。
