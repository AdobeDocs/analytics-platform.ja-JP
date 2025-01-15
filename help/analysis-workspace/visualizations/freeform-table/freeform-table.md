---
title: フリーフォームテーブルの概要
description: フリーフォームテーブルは、Workspace のデータ分析の基盤となっています。
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: f8abf388e0cb1e2e2eb9ff69fed2c542a26dcd66
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 25%

---

# フリーフォームテーブルの概要 {#freeform-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="フリーフォームテーブル"
>abstract="ディメンション、セグメント、指標および日付範囲を使用して作成できる、空のフリーフォームテーブルのビジュアライゼーションを作成します。フリーフォームテーブルを他のビジュアライゼーションの基礎として使用できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*この記事では、![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics**のフリーフォームテーブル ビジュアライゼーションについて説明します。<br/> この記事の [AdobeAnalytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table)**Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) バージョンについては ![ フリーフォームテーブル**を参照してください。*

>[!ENDSHADEBOX]


Analysis Workspaceでは、![ テーブル ](/help/assets/icons/Table.svg) フリーフォームテーブル **[!UICONTROL ビジュアライゼーション]** インタラクティブなデータ分析の基盤となります。 [コンポーネント](/help/components/overview.md)の組み合わせを行と列にドラッグ＆ドロップして、分析用のカスタムテーブルを作成できます。各コンポーネントがドロップされると、テーブルが直ちに更新されるので、分析したり、深く掘り下げたりすることができます。

![ 複数の web ページの訪問およびオンライン注文を含む、行と列のコンポーネントを表示するフリーフォームテーブル。](assets/opening-section.png)

[!UICONTROL  フリーフォームテーブル ] を作成して設定するには：

* ![ テーブル ](/help/assets/icons/Table.svg) フリーフォームテーブル **[!UICONTROL ビジュアライゼーション]** 追加します。 [ パネルへのビジュアライゼーションの追加 ](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel) を参照してください。

## 自動化されたテーブル

テーブルを最もすばやく作成するには、空のプロジェクト、パネル、またはフリーフォームテーブルにコンポーネントを直接ドロップします。フリーフォームテーブルは、推奨される形式で作成されます。 [こちら](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace)から、チュートリアルをご覧ください。

![ 訪問コンポーネントを作業スペースにドロップした新しいパネル。](assets/automated-table.png)

## フリーフォームテーブルビルダー

最初に複数のコンポーネントをテーブルに追加し、次にデータをレンダリングすると、**[!UICONTROL テーブルビルダーを有効にする]** を選択できます。 ビルダーを有効にすれば、ディメンション、分類、指標およびフィルターをドラッグ&amp;ドロップして、より複雑な質問に回答するテーブルを作成できます。 「**[!UICONTROL ビルド]**」を選択すると、データが更新されます。

![](assets/table-builder.png) を表示するフリーフォームテーブルビルダー

## インタラクション

フリーフォームテーブルは、様々な方法で操作およびカスタマイズできます。

### フィルターと並べ替え

* テーブル内のデータを [ フィルターおよび並べ替え ](filter-and-sort.md) できます。

### 行

* ![GraphBarVerticalAdd[ を使用すると、1 つ以上の行から ](../freeform-analysis-visualizations.md#visualize) 新しいビジュアライゼーションを作成 ](/help/assets/icons/GraphBarVerticalAdd.svg) をすばやく実行できます。
* プロジェクトの[表示密度](/help/analysis-workspace/build-workspace-project/view-density.md)を調整すると、1 つの画面に表示する行を増やすことができます。
* 各ディメンション行は、ページネーションの前に最大 400 行を表示できます。最初の列ヘッダーの **[!UICONTROL 行]** の横にある数字を選択して、ページにさらに行を表示します。 最初の列ヘッダーで ![ChevronRight](/help/assets/icons/ChevronRight.svg) を使用して、別のページに移動する。
* 行は、追加のコンポーネントで分類できます。 複数の行を一度に分類するには、複数の行を選択してから、選択した行の上に次のコンポーネントをドラッグします。 [分類](/help/components/dimensions/t-breakdown-fa.md)について説明します。
* 行を[フィルタリング](/help/components/filters/filters-overview.md)して、表示する項目数を減らすここができます。[行設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)で追加の設定を使用できます。

### 列

* 列内にコンポーネントを積み重ねて、フィルター適用済み指標やクロスタブ分析などを作成できます。
* 各列の表示は、[列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)で調整できます。
* [ コンテキストメニュー ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) から使用できるアクションがいくつかあります。 メニューには、テーブルのヘッダー、行、列のどちらを選択したかに応じて異なるアクションが表示されます。


## 設定

![ 設定 ](/help/assets/icons/Setting.svg) を選択して **[!UICONTROL テーブル設定]** を表示します。 次の特定のビジュアライゼーション [ 設定 ](../freeform-analysis-visualizations.md#settings) を使用できます。

### データソース

| オプション | 説明 |
|---|---|
| **[!UICONTROL リンクされたビジュアライゼーション]**. | すべてのリンクされたビジュアライゼーションをリストします。 |
| **[!UICONTROL データソースを表示]** | オフにすると、ビジュアライゼーションのデータソースとして機能するフリーフォームテーブルは、Workspaceで非表示になります。 |

### 設定

| オプション | 説明 |
|---|---|
| **[!UICONTROL 各列の日付を整列させて、すべて同じ行から始まるようにします]** | 各列の日付を整列させるか、整列させないかを、すべて同じ行から開始する場合。 |


## コンテキストメニュー

ビジュアライゼーションのヘッダーでは、次の [ コンテキストメニュー ](../freeform-analysis-visualizations.md#context-menu) オプションを使用できます。

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL  コピーしたビジュアライゼーションを挿入 ]**n | コピーしたビジュアライゼーションを、プロジェクト内の別の場所、または完全に別のプロジェクトに貼り付け（挿入）します。 |
| **[!UICONTROL データをクリップボードにコピー]** | ビジュアライゼーションからクリップボードにデータをコピーします。 |
| **[!UICONTROL 選択範囲をクリップボードにコピー]** | ビジュアライゼーションからクリップボードに選択範囲をコピーします。 |
| **[!UICONTROL 項目を CSV としてダウンロード （*ディメンション名*）]** | ビジュアライゼーションのディメンション項目（最大 50,000 個）をローカルデバイスにすぐにダウンロードします。 選択したディメンションに対して最大 50,000 個のディメンション項目。 |
| **[!UICONTROL ビジュアライゼーションをコピー]** | ビジュアライゼーションをコピーして、ビジュアライゼーションをプロジェクト内の別の場所、または完全に別のプロジェクトに挿入できるようにします。 |
| **[!UICONTROL データ CSV をダウンロード]** | ビジュアライゼーションの表示データをローカルデバイスにすぐにダウンロードします。 |
| **[!UICONTROL 完全なテーブルをエクスポート…]** | 指定したクラウドの場所にテーブル全体を書き出します。 [Customer Journey Analyticsレポートのクラウドへの書き出し ](../../export/export-cloud.md) を参照してください。 |
| **[!UICONTROL ビジュアライゼーションを複製]** | ビジュアライゼーションの完全な複製を作成します。 |
| **[!UICONTROL 説明を編集]** | ビジュアライゼーションの説明テキストを追加（または編集）します。 [ テキスト ](../text.md) を参照してください。 |
| **[!UICONTROL ビジュアライゼーションリンクを取得]** | リンクをコピーして、ビジュアライゼーションと直接共有します。 共有リンク ダイアログにリンクが表示されます。 「コピー」を選択して、リンクをクリップボードにコピーします。 |
| **[!UICONTROL やり直し]** | 現在のビジュアライゼーションの設定を削除して、ゼロから再設定できるようにします。 |


>[!MORELIKETHIS]
>
>[ パネルへのビジュアライゼーションの追加 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[ビジュアライゼーション設定 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[ビジュアライゼーションコンテキストメニュー ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
