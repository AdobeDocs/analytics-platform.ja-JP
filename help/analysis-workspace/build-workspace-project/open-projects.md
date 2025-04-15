---
description: プロジェクトを開くためのオプションについて説明します。
title: プロジェクトを開く
feature: Workspace Basics
role: User
exl-id: 5ef235e2-50d8-4202-bad7-06090102cf73
source-git-commit: ab78583eb36d6158630724fbab9eb8148bcdbe23
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 10%

---

# プロジェクトを開く

[ プロジェクト ](/help/analysis-workspace/build-workspace-project/freeform-overview.md) ページから直接プロジェクトを開くことができます。 リストでプロジェクトを探します。 [ 検索 ](/help/analysis-workspace/build-workspace-project/freeform-overview.md#search) または [ セグメントパネル ](/help/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel) を使用して、リストを絞り込みます。

* プロジェクトのタイトルをクリックして、Analysis Workspaceでプロジェクトを開きます。

別のプロジェクトで作業中にプロジェクトを開くこともできます。

* **[!UICONTROL プロジェクト]** メニューから **[!UICONTROL 開く]** を選択します。 [ プロジェクト ](/help/analysis-workspace/build-workspace-project/freeform-overview.md) ページに似たダイアログが表示されます。  [ 検索 ](/help/analysis-workspace/build-workspace-project/freeform-overview.md#search) または [ セグメントパネル ](/help/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel) を使用して、リストを絞り込みます。
* プロジェクトのタイトルをクリックして、Analysis Workspaceでプロジェクトを開きます。

プロジェクトが見つからず、新規プロジェクトを開始する場合は、「**[!UICONTROL 新規作成]**」を選択します。

## 以前のバージョンを開く

以前に保存したバージョンのプロジェクトを開くには：

1. **[!UICONTROL プロジェクト]** メニューから **[!UICONTROL 以前のバージョンを開く]** を選択します。

   ![ 以前保存したプロジェクトバージョンのリストと、すべてのバージョンまたはメモ付きのバージョンのみを表示するオプション ](assets/open-previously-saved.png)

1. **[!UICONTROL 以前に保存したバージョン]** ダイアログで、使用可能な以前のバージョンのリストを確認します。 **[!UICONTROL すべてのバージョン]** と **[!UICONTROL メモ付きのバージョンのみ]** を切り替えることができます。

   各バージョンについて、リストにはタイムスタンプ、エディター、保存されたメモが表示されます。


1. 以前のバージョンを選択し、「**[!UICONTROL 読み込み]**」をクリックします。
その後、以前のバージョンが通知と共に読み込まれます。「**[!UICONTROL 保存]**」をクリックするまで、以前のバージョンはプロジェクトの現在の保存バージョンになりません。読み込まれたバージョンから移動すると、以前のバージョンをもう一度開きたい場合に、最後に保存されたバージョンが表示されます。


## 互換性のないデータビュー

プロジェクトを開くと、「互換性のないデータビュー **[!UICONTROL 警告ダイアログが表示される場合が]** ります。 このダイアログでは、プロジェクト内の特定のコンポーネントが、プロジェクト内のパネルの選択されたデータビューで有効になっていないことが説明されます。

![ 互換性なし ](assets/incompatible-data-view.png)

この警告を修正するには、次の操作を行います。

* **[!UICONTROL データビューを変更]**。 **[!UICONTROL データビューを変更：]** ![ データ ](/help/assets/icons/Data.svg) から適切なデータビューを選択します。 選択したデータビューが有効な場合、プロジェクトはAnalysis Workspaceで開きます。
* **[!UICONTROL ランディングページに戻る]**。 選択したプロジェクトは開かれておらず、別のプロジェクトを選択できます。
* **[!UICONTROL 続行する]**。 プロジェクトはAnalysis Workspaceで開きますが、ビジュアライゼーションの一部でエラーが表示され、互換性のないデータビューには、データビューの名前の前にアラート ![ アラート ](/help/assets/icons/Alert.svg) が付いています。
