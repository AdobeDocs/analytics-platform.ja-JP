---
title: Report Builderのデータビューを選択する方法
description: Adobe Report Builderでデータビューを選択する方法について説明します
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# データビューの選択

ドロップダウンメニューからデータビューを選択するか、セルからデータビューを選択し、新しいデータビューでデータブロックを自動的に更新できます。

## セルからのデータビューの選択

セルからデータビューを選択すると、異なるデータビューを使用してデータブロックを簡単に更新できます。 別のデータブロックを使用して完全に新しいレポートを作成する代わりに、セルから選択したデータビューでデータブロックを更新できます。

次の場合は、セルからデータビューを選択すると役立ちます。

* 構造が互いに類似している、または同一である複数のデータビュー。
* カスタマイズされたコンポーネントやレイアウトを含む複雑なデータブロック形式。

セルからデータビューを選択するには、まずデータブロックを作成し、データブロック外のセルに複数のデータビューを割り当てます。 次に、**[!UICONTROL セルからのデータビュー]** パネルを使用して、様々なデータビューのデータブロックを更新します。

1. データブロックを作成します。 データブロックの作成について詳しくは、[&#x200B; データブロックの作成 &#x200B;](/help/report-builder/create-a-data-block.md) を参照してください。

1. ![&#x200B; データビュー &#x200B;](/help/assets/icons/DataViewSelector.svg) の **[!UICONTROL データビューセレクター]** を選択します。

1. データブロック外で ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) を使用してセルを選択します。

1. 「**[!UICONTROL セルからデータビューに追加するデータビューを選択]**」から、ドラッグ&amp;ドロップを使用して 1 つ以上のデータビューを追加します。 または、データビューをダブルクリックして、データビューを **[!UICONTROL 含まれるデータビュー]** リストに追加することもできます。

   * ![&#x200B; 検索 &#x200B;](/help/assets/icons/Search.svg)**[!UICONTROL _データビューを選択_]** を使用して、データビューを検索できます。
   * ![MoreSmall](/help/assets/icons/MoreSmall.svg) を使用してコンテキストメニューを開き、「含まれるデータビュー **[!UICONTROL リストでデータビューを上下に移動]** きます。
   * ![&#x200B; 含まれるデータビュー &#x200B;](/help/assets/icons/CrossSize75.svg) リストからデータビューを削除するには、**[!UICONTROL CrossSize75]** を使用します。

   ![&#x200B; セルからデータビューを選択 &#x200B;](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. 「**[!UICONTROL 適用]**」を選択して、選択したデータビューを選択したセルに適用します。


## セルからのデータビューの変更

1. シートのデータビューセルの場所を選択します。
1. Report Builder ハブで、「**[!UICONTROL クイック編集]**」の「**[!UICONTROL セルからのデータビュー]**」リンクをクリックします。
1. **[!UICONTROL データビュー]** ドロップダウンメニューからデータビューを選択します。

   ![&#x200B; セルからのデータビューの変更 &#x200B;](assets/change-data-view-from-cell.png){zoomable="yes"}
1. オプションとして、「**[!UICONTROL 変更時にデータブロックを更新]**」を選択します。

1. 「**[!UICONTROL 適用]**」を選択します。Report Builderは、選択したデータビューに基づいてデータブロックを更新します。
