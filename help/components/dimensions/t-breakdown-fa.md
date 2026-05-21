---
description: Analysis Workspaceでディメンションとディメンション項目を分割する方法について説明します。
keywords: Analysis Workspace
title: ディメンションの分類
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
TQID: https://experienceleague.adobe.com/GTRg4PodKPvehRu0CwAq8QTMUmoOtY2qIU1kHzmwHRI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 57%

---

# ディメンションの分類

Analysis Workspaceでは、適切な指標やディメンション、セグメント、タイムラインなどの分析ブレークダウン値を使用してクエリを構築し、特定のニーズに合わせて無制限にデータを分類できます。

1. [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)で、選択した1つ以上の行のコンテキストメニューから、**[!UICONTROL 分類]** ![ シェブロン右](/help/assets/icons/ChevronRight.svg)を選択します。

   ![選択範囲からアラートを作成を表示する手順の結果。](assets/breakdown.png)

1. サブメニューから、**[!UICONTROL ディメンション]**、**[!UICONTROL 指標]**、**[!UICONTROL セグメント]**&#x200B;または&#x200B;**[!UICONTROL 日付範囲]**&#x200B;を選択し、項目を選択します。 または、**[!UICONTROL *検索&#x200B;*]**フィールドでコンポーネントを検索します。

選択した期間で、ディメンション項目またはオーディエンスセグメントで指標を分類できます。 より詳細なレベルまで、さらに詳しく調べることもできます。

>[!NOTE]
>
>テーブルに表示する分類の数は、400 までに制限されています。 この制限は、分類をエクスポートする場合は増加します。

## 位置で分類

デフォルトでは、分類は静的な行アイテムに固定されています。 例えば、上位 3 つのページディメンション項目（ホームページ、検索結果、チェックアウト）をマーケティングチャネル別に分類するとします。 その後、プロジェクトを終了し、2 週間後に戻ります。 プロジェクトを再度開くと、トップ 3 ページが変更され、ホームページ、検索結果、チェックアウトがトップ 4 ～ 6 ページになりました。 デフォルトでは、マーケティングチャネルの分類は、現在は 4～6 行になっているにもかかわらず、ホームページ、検索結果、チェックアウトの下に引き続き表示されます。

対照的に、**位置による分類**&#x200B;は、これらの項目が何であるかに関係なく、常に上位3つの項目を分類します。 例に戻って参照すると、プロジェクトを再度開く際、マーケティングチャネルの分類はテーブルの上位 3 ページに関連付けられます。 また、現在、4～6 行になっているホームページ、検索結果、チェックアウトには関連付けられません。 この設定の設定方法については、[行の設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)を参照してください。

## 分類へのアトリビューションモデルの適用

テーブル内の分類には、任意のアトリビューションモデルを適用することもできます。 このアトリビューションモデルは、親列と同じ場合と異なる場合があります。 例えば、マーケティングチャネルディメンションで線形の注文件数を分析するものの、チャネル内の特定のトラッキングコードには U 字形の注文件数を適用するといったことができます。 分類に適用されたアトリビューションモデルを編集するには、分類モデルにカーソルを合わせて、**[!UICONTROL 編集]**&#x200B;を選択します。

![分類の設定を示す注文属性比較](assets/breakdown-attribution.png)

アトリビューションモデルを分類に適用したり編集したりする際に想定される動作です。

* 他のアトリビューションが存在しないときにアトリビューションを適用すると、そのアトリビューションは列ツリー全体に適用されます。

* アトリビューションが適用された後に分類を追加した場合は、追加された特定の分類に対してデフォルトが使用されます（そのディメンションにデフォルトが設定されている場合）。 それ以外の場合は、親列の分類が使用されます。 一部のディメンションにはデフォルトの割り当てがあります。 例えば、時間ディメンションとリファラーは同一タッチを使用します。 製品ディメンションでは、ラストタッチを使用します。 他のディメンションにはデフォルトはなく、親列の割り当てが使用されます。

* 列ツリーに既にアトリビューションが存在する場合、アトリビューションの変更は、編集中のアトリビューションにのみ影響します。

>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis WorkspaceのDimension](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの内訳](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ ディメンションと指標の追加](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ フリーフォームテーブルでのディメンションの操作](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの位置別の内訳](https://video.tv.adobe.com/v/24033){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]



