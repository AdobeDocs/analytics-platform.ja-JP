---
description: プロジェクトを開くためのオプションについて説明します。
title: プロジェクトを開く
feature: Workspace Basics
role: User
exl-id: 5ef235e2-50d8-4202-bad7-06090102cf73
source-git-commit: ab78583eb36d6158630724fbab9eb8148bcdbe23
workflow-type: ht
source-wordcount: '374'
ht-degree: 100%

---

# プロジェクトを開く

[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)ページからプロジェクトを直接開くことができます。リストでプロジェクトを検索します。リストを絞り込むには、[検索](/help/analysis-workspace/build-workspace-project/freeform-overview.md#search)または[セグメントパネル](/help/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel)を使用します。

* プロジェクトのタイトルを選択して、Analysis Workspace でプロジェクトを開きます。

また、別のプロジェクトで作業中にプロジェクトを開くこともできます。

* **[!UICONTROL プロジェクト]**&#x200B;メニューから「**[!UICONTROL 開く]**」を選択します。[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)ページに類似したダイアログが表示されます。リストを絞り込むには、[検索](/help/analysis-workspace/build-workspace-project/freeform-overview.md#search)または[セグメントパネル](/help/analysis-workspace/build-workspace-project/freeform-overview.md#segment-panel)を使用します。
* プロジェクトのタイトルを選択して、Analysis Workspace でプロジェクトを開きます。

プロジェクトが見つからず、新しいプロジェクトを開始する場合は、「**[!UICONTROL 新規作成]**」を選択します。

## 以前のバージョンを開く

以前に保存したバージョンのプロジェクトを開くには：

1. **[!UICONTROL プロジェクト]**&#x200B;メニューから「**[!UICONTROL 以前のバージョンを開く]**」を選択します。

   ![以前に保存したプロジェクトバージョンのリストと、「すべてのバージョン」または「メモ付きのバージョンのみ」を示すオプション。](assets/open-previously-saved.png)

1. **[!UICONTROL 以前に保存したバージョン]**&#x200B;ダイアログで、使用可能な以前のバージョンのリストを確認します。「**[!UICONTROL すべてのバージョン]**」と「**[!UICONTROL メモ付きのバージョンのみ]**」を切り替えることができます。

   リストには、バージョン別にタイムスタンプ、編集者、保存されたメモが表示されます。


1. 以前のバージョンを選択し、「**[!UICONTROL 読み込み]**」をクリックします。
その後、以前のバージョンが通知と共に読み込まれます。「**[!UICONTROL 保存]**」をクリックするまで、以前のバージョンはプロジェクトの現在の保存バージョンになりません。読み込まれたバージョンから移動した場合、以前のバージョンをもう一度開く際に、最後に保存したバージョンが表示されます。


## 互換性のないデータビュー

プロジェクトを開くと、**[!UICONTROL 互換性のないデータビュー]**&#x200B;警告ダイアログが表示される可能性があります。このダイアログでは、プロジェクト内のパネルの 1 つで選択されたデータビューで、プロジェクト内の特定のコンポーネントが有効になっていないことについて説明しています。

![互換性なし](assets/incompatible-data-view.png)

この警告を修正するには、次の操作を実行できます。

* **[!UICONTROL データビューを変更する]**。**[!UICONTROL データビューを変更：]** ![データ](/help/assets/icons/Data.svg) から適切なデータビューを選択します。選択したデータビューが有効な場合、プロジェクトが Analysis Workspace で開きます。
* **[!UICONTROL ランディングページに戻る]**。 選択したプロジェクトは開かれず、別のプロジェクトを選択できます。
* **[!UICONTROL 強制的に続行する]**。プロジェクトは Analysis Workspace で開きますが、一部のビジュアライゼーションにエラーが表示され、互換性のないデータビューにはデータビュー名の前にアラート ![アラート](/help/assets/icons/Alert.svg) が表示されます。
