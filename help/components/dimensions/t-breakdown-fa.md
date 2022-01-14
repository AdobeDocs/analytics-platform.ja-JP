---
description: Analysis Workspace のディメンションおよびディメンション項目を分類します。
keywords: Analysis Workspace
title: ディメンションの分類
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
source-git-commit: af15a6cad05b274c7eeaeca8f32617bed07c9382
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 79%

---

#  Workspace のディメンションの分類

>[!NOTE]
>
>Customer Journey Analytics 内の Analysis Workspace に関するドキュメントを表示しています。この機能セットは、[従来の Adobe Analytics の Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) とは少し異なります。[詳細情報...](/help/getting-started/cja-aa.md)

Analysis Workspace のディメンションおよびディメンション項目を分類します。

特定のニーズに合わせて、無制限の方法でデータを分類する。関連する指標、ディメンション、フィルター、タイムライン、その他の分析分類値を使用してクエリを作成します。

1. データテーブルを使用して[プロジェクトを作成](/help/analysis-workspace/home.md)します。
1. データテーブルで行項目を右クリックし、**[!UICONTROL 分類]**／*`<item>`*&#x200B;を選択します。

   ![手順の結果](assets/fa_data_table_actions.png)

   選択した期間で、ディメンション項目またはオーディエンスフィルターで指標を分類できます。 より詳細なレベルまで、さらに詳しく調べることもできます。

   >[!NOTE]
   >
   >テーブルに表示する分類の数は、200 までに制限されています。この制限は、分類をエクスポートする場合は増加します。

**ビデオ：Analysis WorkspaceのDimension**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**ビデオ：Dimensionの分類**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## 分類へのアトリビューションモデルの適用

テーブル内の分類には、任意のアトリビューションモデルを適用することもできます。このアトリビューションモデルは、親列と同じ場合と異なる場合があります。例えば、マーケティングチャネルディメンションで線形の注文件数を分析するものの、チャネル内の特定のトラッキングコードには U 字形の注文件数を適用するといったことができます。分類に適用されるアトリビューションモデルを編集するには、その分類モデルの上にマウスポインターを置いて「**[!UICONTROL 編集]**」をクリックするだけです。

![分類の設定](assets/breakdown_settings.png)
