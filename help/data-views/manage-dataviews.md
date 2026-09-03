---
title: データビューの管理
description: データビューの管理方法を説明します。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c5cf15ab-3eb1-4e6b-93a3-3d89694ca0ea
autotag-review: '2026-05-19T10:45:24.919Z'
TQID: 'https://experienceleague.adobe.com/fPYOLKGTjiZDeSWLRhvkywKht8Yoq4k54EOcazJw74M'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 933
ht-degree: 12%

---

# データビューの管理


1つ以上のデータビュー](/help/data-views/create-dataview.md)を[作成または編集したら、**[!UICONTROL データビュー]**&#x200B;でそれらを管理できます。

Customer Journey Analyticsのメインメニューバーから&#x200B;**[!UICONTROL Data Management]** > **[!UICONTROL Data views]**&#x200B;を選択します。

**[!UICONTROL データビュー]** インターフェイスには、使用可能なすべてのデータビューのテーブルが表示されます。

![ データビューインターフェイス ](/help/data-views/assets/data-views.png)

次の列とアイコンを表に示します。

| 列またはアイコン | 説明 |
| --- | --- |
| **[!UICONTROL 名前]** | データビューの名前。 |
| ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | データビューに関する情報を表示するには、データビュー名の横にある![InfoOutline](/help/assets/icons/InfoOutline.svg)を選択します。<br/> データビューに関する詳細がポップアップウィンドウに表示されます。 |
| ![詳細情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 「![その他](/help/assets/icons/More.svg)」を選択すると、コンテキストメニューが開きます。 データビューを<br/>![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** ～ [編集](#edit-data-views)を選択できます。<br/>![ コピー](/help/assets/icons/Copy.svg) **[!UICONTROL コピー]**&#x200B;から[ データビューをコピー](#copy-data-views)。<br/>![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]**&#x200B;から[delete](#delete-data-views) データビューを削除します。<br/>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV]**&#x200B;に書き出して[ データビューの詳細をCSV ファイルに書き出します](#export-data-views-to-csv)。<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]**&#x200B;から[新しいWorkspace プロジェクト ](#create-project-from-data-views)を作成します。<br/>![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable forEnable for]** a}を1}の1}を1}を1}有効にをををに有効に有効有効してをを有効を有効有効有効使用して{a}します。Data Insights Agent.<br/>![RemoveCircle](/help/assets/icons/RemoveCircle.svg)**[!UICONTROL Data Insights Agent]**&#x200B;を無効にして、Data Insights Agentのデータビューを無効にします。 |
| **[!UICONTROL 接続]** | データビューに関連付けられている接続の名前。 |
| **[!UICONTROL サンドボックス]** | データビューに関連付けられているサンドボックスの名前。 |
| **[!UICONTROL 所有者]** | データビューの所有者。 |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | データビューの[Data Insights Agent](/help/data-analysis-ai.md)が&#x200B;**[!UICONTROL 有効]**&#x200B;か&#x200B;**[!UICONTROL 無効]**&#x200B;かを示します。 <br/> 「![InfoOutline](/help/assets/icons/InfoOutline.svg)」を選択すると、データビュー全体で&#x200B;**[!UICONTROL Data Insights Agentのステータス]**&#x200B;を含むポップアップが表示されます。 <br/>![Data Insights Agentの使用状況](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL 統合]** | 他のソリューションとの統合のリスト。 例：Adobe Audience Analysis、Content Analytics、Brand Concierge、Journey Optimizer、GenStudio、Usage Analytics |
| **[!UICONTROL CJA で使用]** | データビューをCustomer Journey Analyticsで使用するかどうかを示します。 この値は、Adobe Journey Optimizer統合の一部として自動生成されるデータビューに対してのみ&#x200B;**[!UICONTROL Off]**&#x200B;です。 |
| **[!UICONTROL 作成日]** | データビューの作成時のタイムスタンプ。 |
| **[!UICONTROL 最終変更日]** | データビューが最も最近変更されたタイムスタンプ。 |

テーブルに表示する列を設定するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg)を選択します。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログで、表示する列を選択します。 次に、**[!UICONTROL 適用]**&#x200B;を選択します。


## データビューを検索

![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) ボックスを使用して、データビューをすばやく検索できます。

## データビューのフィルタリング

データビューのリストにフィルターを適用するには、![ フィルター](/help/assets/icons/Filter.svg) アイコンを選択し、次のフィルターオプションから選択します。

| フィルターオプション | 説明 |
|---------|----------|
| **[!UICONTROL 接続]** | 選択した接続に関連付けられているデータビューのみが表示されます。 |
| **[!UICONTROL 所有者]** | 選択したユーザーが所有するデータビューのみが表示されます。 |
| **[!UICONTROL サンドボックス]** | 選択したサンドボックスで使用可能なデータビューのみが表示されます。 |
| **[!UICONTROL 統合]** | 選択した統合を持つデータビューのみが表示されます。 |
| **[!UICONTROL CJA で使用]** | 「**[!UICONTROL On]**」を選択すると、Customer Journey Analyticsでの使用が有効なデータビューのみが表示されます。 「**[!UICONTROL Off]**」を選択すると、Customer Journey Analyticsでの使用がまだ有効になっていないデータビューのみが表示されます。 |


「![ フィルター](/help/assets/icons/Filter.svg) **[!UICONTROL フィルターを非表示]**」を選択して、フィルターペインを非表示にします。

## データビューの作成

[新しいデータビューを作成](/help/data-views/create-dataview.md)するには、**[!UICONTROL 新しいデータビューを作成]**&#x200B;を選択します。


## データビューの編集

[ データビューを編集する場合](/help/data-views/create-dataview.md):

1. データビュー名の横にある![詳細](/help/assets/icons/More.svg)を選択します。
1. コンテキストメニューから ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。

または、次の操作を実行できます。

1. データビュー行を選択します。
1. 青色のアクションバーから ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。


## データビューをコピー

データビューをコピーする場合：

1. データビュー名の横にある![詳細](/help/assets/icons/More.svg)を選択します。
1. コンテキストメニューから「![ コピー](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]**」を選択します。

または、次の操作を実行できます。

1. 1つ以上のデータビュー行を選択します。
1. 青いアクションバーから「![ コピー](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]**」を選択します。

データビューがコピーされ、名前に&#x200B;**[!UICONTROL （コピー）]**&#x200B;が追加されてリストに追加されます。


## データビューの削除

データビューを削除する場合：

1. データビュー名の横にある![詳細](/help/assets/icons/More.svg)を選択します。
1. コンテキストメニューから「![削除](/help/assets/icons/Delete.svg) **[!UICONTROL 削除]**」を選択します。

または、次の操作を実行できます。

1. 1つ以上のデータビュー行を選択します。
1. 青色のアクションバーから ![削除](/help/assets/icons/Delete.svg) **[!UICONTROL 削除]** を選択します。

1つ以上のデータビューを削除すると、**[!UICONTROL データビューを削除]** パネルに、影響を受けるプロジェクトが示されます。

![ データビューを削除](/help/data-views/assets/delete-data-view.png)


* ➊ **[!UICONTROL 確認]**&#x200B;では、データビューの削除の影響が示されます。
* データ ビューを完全に削除するには、**[!UICONTROL 削除]**&#x200B;を選択します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。


## データビューをCSVにエクスポート

データビューをCSV ファイルに書き出すことができます。

1. データビュー名の横にある![詳細](/help/assets/icons/More.svg)を選択します。
1. コンテキストメニューから「![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV]**&#x200B;に書き出し」を選択します。

または、次の操作を実行できます。

1. 1つ以上のデータビュー行を選択します。
1. 青いアクションバーから「![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSVに書き出し]**」を選択します。

選択したデータビューの詳細は、ブラウザーのダウンロードフォルダーの`Data views List (x).csv`という名前のCSV ファイルに書き出されます。


## データビューからプロジェクトを作成

Workspace プロジェクトは、データビューインターフェイスから直接作成できます。

1. データビュー名の横にある![詳細](/help/assets/icons/More.svg)を選択します。
1. コンテキストメニューから「![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL プロジェクトを作成]**」を選択します。

または、次の操作を実行できます。

1. データビュー行を選択します。
1. 青いアクションバーから「![ProjectAdd](/help/assets/icons/ProjectAdd.svg)**[!UICONTROL プロジェクトを作成]**」を選択します。


## Data Insights Agentのデータビューを有効または無効にする

[Data Insights Agent](/help/data-analysis-ai.md)のデータビューを有効または無効にできます。

1. データビュー名の横にある![詳細](/help/assets/icons/More.svg)を選択します。
1. コンテキストメニューから「![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]**」または「![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]**」を選択します。

または、次の操作を実行できます。

1. Data Insights Agentに対して無効または有効になっている1つ以上のデータビュー行を選択します。
1. 青いアクションバーから「![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable for Data Insights Agent]**」または「![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable for Data Insights Agent]**」を選択します。
