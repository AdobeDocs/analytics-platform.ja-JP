---
description: Analysis Workspaceでディメンションとディメンション項目を分類する方法について説明します。
keywords: Analysis Workspace
title: ディメンションの分類
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 56%

---

# ディメンションの分類

Analysis Workspaceでは、具体的なニーズに合わせて様々な方法でデータを分類できます。関連する指標、ディメンション、セグメント、タイムライン、その他の分析分類値を使用するクエリを作成できます。

1. [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) で、選択した 1 つ以上の行のコンテキストメニューから、「**[!UICONTROL 分類]**![ 山形の右 ](/help/assets/icons/ChevronRight.svg)」を選択します。

   ![ 選択した項目からアラートを作成を示すステップ結果。](assets/breakdown.png)

1. サブメニューから **[!UICONTROL ディメンション]**、**[!UICONTROL 指標]**、**[!UICONTROL セグメント]** または **[!UICONTROL 日付範囲]** を選択し、項目を選択します。 または、「**[!UICONTROL *検索&#x200B;*]**フィールドでコンポーネントを検索します。

選択した期間で、ディメンション項目またはオーディエンスセグメントで指標を分類できます。より詳細なレベルまで、さらに詳しく調べることもできます。

>[!NOTE]
>
>テーブルに表示する分類の数は、200 までに制限されています。この制限は、分類をエクスポートする場合は増加します。

## 位置で分類

デフォルトでは、分類は静的な行項目に固定されています。 例えば、上位 3 つのページディメンション項目（ホームページ、検索結果、チェックアウト）をマーケティングチャネル別に分類するとします。その後、プロジェクトを終了し、2 週間後に戻ります。プロジェクトを再度開くと、トップ 3 ページが変更され、ホームページ、検索結果、チェックアウトがトップ 4 ～ 6 ページになりました。マーケティングチャネルの分類は、現在 4～6 行目ですが、デフォルトでは、ホームページ、検索結果、チェックアウトの下に表示されます。

これに対し **位置で分類** は、上位 3 つのアイテムが何であるかに関係なく、常に分類されます。 例に戻って参照すると、プロジェクトを再度開く際、マーケティングチャネルの分類はテーブルの上位 3 ページに関連付けられます。ホームページ、検索結果、チェックアウトは 4～6 行目に表示されるようになりました。 この設定の設定方法については、[ 行設定 ](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) を参照してください。



## 分類へのアトリビューションモデルの適用

テーブル内の分類には、任意のアトリビューションモデルを適用することもできます。このアトリビューションモデルは、親列と同じ場合と異なる場合があります。例えば、マーケティングチャネルディメンションで線形の注文件数を分析するものの、チャネル内の特定のトラッキングコードには U 字形の注文件数を適用するといったことができます。分類に適用されたアトリビューションモデルを編集するには、分類モデルにカーソルを合わせて **[!UICONTROL 編集]** を選択します。

![ 分類設定を示す順序アトリビューション比較 ](assets/breakdown-attribution.png)

アトリビューションモデルを分類に適用したり編集したりする際に想定される動作です。

* 他のアトリビューションが存在しないときにアトリビューションを適用すると、そのアトリビューションは列ツリー全体に適用されます。

* アトリビューションが適用された後に分類を追加した場合は、追加された特定の分類に対してデフォルトが使用されます（そのディメンションにデフォルトが設定されている場合）。それ以外の場合は、親列の分類が使用されます。一部のディメンションにはデフォルトの割り当てがあります。例えば、時間ディメンションとリファラーは同一タッチを使用します。製品ディメンションでは、ラストタッチを使用します。他のディメンションにはデフォルトはなく、親列の割り当てが使用されます。

* 列ツリーに既にアトリビューションが存在する場合、アトリビューションの変更は、編集中のアトリビューションにのみ影響します。

>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis WorkspaceのDimension](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの分類 ](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ ディメンションと指標の追加 ](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ フリーフォームテーブルでのディメンションの操作 ](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの位置別分類 ](https://video.tv.adobe.com/v/24033){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]



