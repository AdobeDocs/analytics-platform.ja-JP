---
title: Report Builderでのデータビューの選択
description: Report Builderでデータビューを選択する方法について説明します。
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
TQID: https://experienceleague.adobe.com/auDJxQ6x6fqNVbDuN9reSffP9iUISZ7QgEflGWApc8A
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 1%

---

# データビューの選択

ドロップダウンメニューからデータビューを選択するか、セルからデータビューを選択して、新しいデータビューでデータブロックを自動的に更新できます。

## セルからデータビューを選択

セルからデータビューを選択すると、異なるデータビューを使用してデータブロックを簡単に更新できます。 個別のデータブロックを持つ完全に新しいレポートを作成する代わりに、セルから選択したデータビューでデータブロックを更新できます。

セルからデータビューを選択すると、次のような場合に役立ちます。

* 構造内の類似または同一の複数のデータビュー。
* カスタマイズされたコンポーネントやレイアウトを含む複雑なデータブロック形式。

セルからデータビューを選択するには、まずデータブロックを作成し、データブロック外のセルに複数のデータビューを割り当てます。 次に、**[!UICONTROL セルからのデータビュー]** パネルを使用して、異なるデータビューからデータブロックを更新します。

1. データブロックを作成します。 データブロックの作成について詳しくは、[&#x200B; データブロックの作成](/help/report-builder/create-a-data-block.md)を参照してください。

1. **[!UICONTROL データビュー]**&#x200B;で![DataViewSelector](/help/assets/icons/DataViewSelector.svg)を選択します。

1. データブロック外の![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)を使用してセルを選択します。

1. ドラッグ&amp;ドロップを使用して、**[!UICONTROL データビューから1つ以上のデータビューを追加し、セル]**&#x200B;からデータビューに追加します。 または、データビューを二重選択して、**[!UICONTROL データビューが含まれる]** リストにデータビューを追加することもできます。

   * ![検索](/help/assets/icons/Search.svg) **[!UICONTROL _データビューを選択_]**&#x200B;して、データビューを検索できます。
   * ![MoreSmall](/help/assets/icons/MoreSmall.svg)を使用してコンテキストメニューを開き、**[!UICONTROL データビューが含まれる]** リストでデータビューを上下に移動できます。
   * ![CrossSize75](/help/assets/icons/CrossSize75.svg)を使用して、含まれる&#x200B;**[!UICONTROL データビュー]** リストからデータビューを削除します。

   ![&#x200B; セルからデータビューを選択](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. 選択したデータビューを選択したセルに適用するには、**[!UICONTROL 適用]**&#x200B;を選択します。


## セルからのデータビューの変更

1. シート内のデータ ビューのセルの場所を選択します。
1. Report Builder ハブで、**[!UICONTROL クイック編集]**&#x200B;で「**[!UICONTROL セルからのデータビュー]**」リンクを選択します。
1. **[!UICONTROL データビュー]** ドロップダウンメニューからデータビューを選択します。

   ![&#x200B; セルからのデータビューの変更](assets/change-data-view-from-cell.png){zoomable="yes"}
1. オプションで、**[!UICONTROL 変更時にデータブロックを更新]**&#x200B;を選択します。

1. 「**[!UICONTROL 適用]**」を選択します。 Report Builderは、選択したデータビューに基づいてデータブロックを更新します。
