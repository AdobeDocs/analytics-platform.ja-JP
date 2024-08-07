---
title: フリーフォームテーブル
description: フリーフォームテーブルは、Workspace のデータ分析の基盤となっています。
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 90%

---

# フリーフォームテーブル

Analysis Workspaceでは、フリーフォームテーブルはインタラクティブなデータ分析の基盤となっています。[コンポーネント](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=ja)の組み合わせを行と列にドラッグ＆ドロップして、分析用のカスタムテーブルを作成できます。各コンポーネントが削除されると、テーブルは直ちに更新されるので、分析や掘り下げを迅速におこなうことができます。

![ 複数の web ページの訪問およびオンライン注文を含む、行と列のコンポーネントを表示するフリーフォームテーブル。](assets/opening-section.png)

## 自動化されたテーブル

テーブルを最もすばやく作成するには、空のプロジェクト、パネル、またはフリーフォームテーブルにコンポーネントを直接ドロップします。推奨される形式のフリーフォームテーブルが自動的に作成されます。[こちら](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=ja)から、チュートリアルをご覧ください。

![ 訪問コンポーネントを作業スペースにドロップした新しいパネル。](assets/automated-table.png)

## フリーフォームテーブルビルダー

最初に複数のコンポーネントをテーブルに追加し、次にデータをレンダリングすると、フリーフォームテーブルビルダーを有効にできます。ビルダーを有効にすれば、多くのディメンション、分類、指標およびフィルターをドラッグ＆ドロップして、より複雑な質問に回答するテーブルを作成できます。データはその場では更新されず、「**[!UICONTROL ビルド]**」をクリックすると更新されます。

![](assets/table-builder.png) を表示するフリーフォームテーブルビルダー

## テーブルの操作

フリーフォームテーブルは、様々な方法で操作およびカスタマイズできます。

* **行**
   * プロジェクトの[表示密度](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=ja)を調整すると、1 つの画面に表示する行を増やすことができます。
   * 各ディメンション行は、ページネーションの前に最大 400 行を表示できます。「行」の横の数字をクリックすると、ページに行が表示されます。ヘッダーのページ矢印を使用して、別のページに移動します。
   * 行は、追加のコンポーネントで分類できます。複数の行を一度に分類するには、複数の行を選択し、次のコンポーネントを選択した行の上にドラッグします。[分類](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html?lang=ja)について説明します。
   * 行を[フィルタリング](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=ja)して、表示する項目数を減らすここができます。[行設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=ja)で追加の設定を使用できます。

* **列**
   * 列内にコンポーネントを積み重ねて、フィルター適用済み指標やクロスタブ分析などを作成できます。
   * 各列の表示は、[列設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=ja)で調整できます。
   * [右クリックメニュー](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html?lang=ja)からは、いくつかの操作を実行できます。テーブルのヘッダー、行または列をクリックしたかどうかに応じて、このメニューに表示されるアクションが変わります。

## フリーフォームテーブルデータの書き出し

Analysis Workspace のすべてのデータエクスポートオプションについては、[こちら](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja)から確認できます。

* 右クリック >「**[!UICONTROL データソースをクリップボードにコピー]**」：表示されているテーブルデータを書き出します。テーブルを選択すると、このオプションが「**[!UICONTROL 選択範囲をクリップボードにコピー]**」に変わります。ホットキー **Ctrl + C** を使用して、選択したデータをコピーすることもできます。
* 右クリック >「**[!UICONTROL データを CSV 形式でダウンロード]**」：表示されているテーブルデータが CSV 形式でダウンロードされます。テーブルを選択すると、このオプションが「**[!UICONTROL 選択内容を CSV 形式でダウンロード]**」に変わります。
* 右クリック >**[!UICONTROL 「プロジェクト」>「項目を CSV 形式でダウンロード」]**：選択したディメンションの最大 50,000 個のディメンション項目がエクスポートされます。

Analysis Workspace のすべてのデータエクスポートオプションついては、[こちら](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja)から確認できます。

![ 書き出しオプションと「データをクリップボードにコピー」が選択されていることを示すフリーフォームテーブル ](assets/export-options.png)
