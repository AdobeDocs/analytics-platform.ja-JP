---
description: Analysis Workspace のディメンションおよびディメンション項目を分類します。
keywords: Analysis Workspace
title: ディメンションの分類
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
source-git-commit: 4bea8d7997d4084cfb87c1035689c0eea6b1f3b1
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 100%

---

# Workspace のディメンションの分類

>[!NOTE]
>
>Customer Journey Analytics 内の Analysis Workspace に関するドキュメントを表示しています。この機能セットは、[従来の Adobe Analytics の Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) とは少し異なります。[詳細情報...](/help/getting-started/cja-aa.md)

Analysis Workspace のディメンションおよびディメンション項目を分類します。

特定のニーズに合わせて様々な方法でデータを分類し、関連する指標、ディメンション、フィルター、タイムライン、その他の分析分類値を使用するクエリを作成します。

1. データテーブルを使用して[プロジェクトを作成](/help/analysis-workspace/home.md)します。
1. データテーブルで行項目を右クリックし、**[!UICONTROL 分類]**／*`<item>`*&#x200B;を選択します。

   ![手順の結果](assets/fa_data_table_actions.png)

   選択した期間で、ディメンション項目またはオーディエンスフィルターで指標を分類できます。より詳細なレベルまで、さらに詳しく調べることもできます。

   >[!NOTE]
   >
   >テーブルに表示する分類の数は、200 までに制限されています。この制限は、分類をエクスポートする場合は増加します。

**ビデオ：Analysis Workspace のディメンション**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**ビデオ：ディメンションの分類**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## 分類へのアトリビューションモデルの適用

テーブル内の分類には、任意のアトリビューションモデルを適用することもできます。このアトリビューションモデルは、親列と同じ場合と異なる場合があります。例えば、マーケティングチャネルディメンションで線形の注文件数を分析するものの、チャネル内の特定のトラッキングコードには U 字形の注文件数を適用するといったことができます。分類に適用されるアトリビューションモデルを編集するには、その分類モデルの上にマウスポインターを置いて「**[!UICONTROL 編集]**」をクリックするだけです。

![分類の設定](assets/breakdown_settings.png)

アトリビューションモデルを分類に適用したり編集したりする際に想定される動作です。

* 他のアトリビューションが存在しないときにアトリビューションを適用すると、そのアトリビューションは列ツリー全体に適用されます。

* アトリビューションが適用された後に分類を追加した場合は、追加された特定の分類に対してデフォルトが使用されます（そのディメンションにデフォルトが設定されている場合）。 それ以外の場合は、親列の分類が使用されます。 一部のディメンションにはデフォルトの割り当てがあります。例えば、時間ディメンションとリファラーは同一タッチを使用します。 製品ディメンションでは、ラストタッチを使用します。 他のディメンションにはデフォルトはなく、親列の割り当てが使用されます。

* 列ツリーに既にアトリビューションが存在する場合、アトリビューションの変更は、編集中のアトリビューションにのみ影響します。

## ビデオ

Analysis Workspace でのプロジェクトへのディメンションと指標の追加：

>[!VIDEO](https://video.tv.adobe.com/v/30606)

フリーフォームテーブルでのディメンションの操作：

>[!VIDEO](https://video.tv.adobe.com/v/40179)

ディメンションを位置で分類：

>[!VIDEO](https://video.tv.adobe.com/v/24033)
