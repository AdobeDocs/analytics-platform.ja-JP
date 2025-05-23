---
title: コンテンツ分析レポート
description: Content Analyticsのレポート方法
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Content Analytics レポートの概要

[Analysis Workspace](/help/analysis-workspace/home.md) 内でContent Analyticsについてレポートし、分析を実行して、インサイトを得ます。 特定のWorkspace[ テンプレート ](#template) を使用できるので、関連するコンテンツインサイトを含む事前入力されたWorkspace プロジェクトに直ちにアクセスできます。

コンテンツ分析に関するレポートをゼロから開始するには：

1. Workspaceで [ 新しいプロジェクトを作成 ](/help/analysis-workspace/build-workspace-project/create-projects.md) または [ 既存のプロジェクトを開く ](/help/analysis-workspace/build-workspace-project/open-projects.md) ことができます。
1. Content Analyticsのレポート用に [ データビューを選択 ](/help/analysis-workspace/c-panels/panels.md#data-view) してください。 Content Analytics レポートは、Content Analyticsで [ 設定 ](/help/content-analytics/config/configuration.md) されたデータビューでのみ使用できます。
1. ![ テーブル ](/help/assets/icons/Table.svg) フリーフォームテーブル [ ビジュアライゼーションをキャンバス ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ドラッグします。
1. [ 特定のContent Analytics コンポーネント ](components.md) およびその他の汎用 [ コンポーネント ](/help/components/overview.md) （セグメント、日付範囲、注釈など）を使用して、コンテンツ分析インサイトを構築します。

## サムネール

プロジェクトで使用するContent Analytics固有のディメンションに基づいて、アセットとディメンションにサムネールが表示されます。

![Content Analyticsのサムネイル ](../assets/aca-thumbnails.png)

デフォルトでは、関連するContent Analytics ディメンションのサムネールが表示されます。 Content Analytics ディメンションのサムネールの表示を設定するには：

* Content Analytics ディメンションのヘッダー行にポインタを合わせます。 例えば、**[!UICONTROL アセット名]** や **[!UICONTROL エクスペリエンス ID]** などです。
* ![ 設定 ](/help/assets/icons/Setting.svg) を選択します。
* **[!UICONTROL 行設定]** ポップアップの **[!UICONTROL 設定]** の下の **[!UICONTROL サムネールを表示]** をチェックまたはチェック解除します。


## プレビュー

Content Analytics ディメンションの行にサムネールが表示される場合は、プレビューポップアップウィンドウを開くことができます。

次の詳細を含むプレビューを開くには：

* ![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択します。 次の詳細が表示されます。

  | エクスペリエンスのプレビュー | アセットのプレビュー |
  |---|---|
  | ![Content Analytics エクスペリエンスのプレビュー ](../assets/aca-experience-preview.png) | ![Content Analytics アセットのプレビュー ](../assets/aca-asset-preview.png) |
  | ディメンションの名前（例：**[!UICONTROL エクスペリエンス ID]）** | アセットディメンションの名前（例：**[!UICONTROL アセット ID]）** |
  | **[!UICONTROL インプレッション数（常に）]**：エクスペリエンスのインプレッション数。 | **[!UICONTROL インプレッション数（常に）]**：アセットのインプレッション数。 |
  | **[!UICONTROL Assets]**：このエクスペリエンスに含まれるアセットの数。 <br/>![ 分類 ](/help/assets/icons/Breakdown.svg)**[!UICONTROL 分類]** を選択して、アセットを調べます。 | **[!UICONTROL エクスペリエンス]**：このアセットが表示されるエクスペリエンスの数。 <br/>![ 分類 ](/help/assets/icons/Breakdown.svg)**[!UICONTROL 分類]** を選択して、アセットを調べます。 |
  | **[!UICONTROL ファーストインプレッション]**：エクスペリエンスのファーストインプレッションの日付。 | **[!UICONTROL 最初のインプレッション]**：アセットの最初のインプレッションの日付。 |
  | **[!UICONTROL 最新のインプレッション]**：エクスペリエンスの最新のインプレッションの日付。 | **[!UICONTROL 最新のインプレッション]**：アセットの最新のインプレッションの日付。 |
  | **[!UICONTROL エクスペリエンス属性]**：エクスペリエンスの [ 属性 ](/help/content-analytics/report/components.md#experience-attributes)。 | **[!UICONTROL アセット属性]**：アセットの [ 属性 ](/help/content-analytics/report/components.md#asset-attributes)。 |


## テンプレート

コンテンツ分析 [ テンプレート ](/help/analysis-workspace/templates/use-templates.md) を使用すると、最もパフォーマンスの高いコンテンツやコンテンツ属性を把握できます。 テンプレートは [web チャネルとエンゲージメントのユースケース ](/help/analysis-workspace/templates/use-templates.md#web-engagement) の一部であり、コンテンツのパフォーマンスをきめ細かく示します。 個々のアセットや特定の属性のパフォーマンスを確認できます。

学んだことに基づいて、いくつかの作業を行うことができます。 ホームページで高パフォーマンスのアセットを昇格するのと同様に、特定のセグメント用にコンテンツをパーソナライズして高パフォーマンスの属性を含めたり、古くなり始めたコンテンツを回転させたりします。

テンプレートを使用するには：

1. メインメニューから **0&rbrace;Workspace&rbrace; を選択します。**
1. Content Analytics用に設定されたデータビューを選択していることを確認します。
1. **[!UICONTROL チャネル]** の場合はセグメント（**[!UICONTROL Web]**、**[!UICONTROL &#x200B; ユースケース &#x200B;** [!UICONTROL の場合は &#x200B;] エンゲージメント] **&#x200B; を検索**&#x200B;たは使用して、**[!UICONTROL コンテンツ分析]** テンプレートを検索して選択します。
1. **[!UICONTROL テンプレートを使用]** を選択します。
1. **[!UICONTROL テンプレートの設定]** ダイアログで、**[!UICONTROL コンバージョン指標を選択]** ダイアログから指標を選択します。 例えば、**[!UICONTROL Asset CTR]** と入力します。
1. 「**[!UICONTROL 続行]**」を選択します。

**[!UICONTROL Content Analyticsの概要]** プロジェクトが [Analysis Workspace](/help/analysis-workspace/home.md) で開きます。 プロジェクトは 4 つの [ パネル ](/help/analysis-workspace/c-panels/panels.md) で構成され、各パネルには特定の質問に回答するための [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) および [ ビジュアライゼーション ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) が表示されます。

* **最もパフォーマンスの高いコンテンツは何ですか？**
このパネルを使用すると、エンゲージメントとコンバージョンに寄与しているエクスペリエンスと、それらのエクスペリエンス内のアセットを理解できます。 エクスペリエンスは、特定の時間にキャプチャされた完全な web ページです。 エクスペリエンスには、テキストと複数の個々の画像アセットの両方を含めることができます。 アセットは個々の画像です。

  このパネルは、次のビジュアライゼーションで構成されます。

   * **エクスペリエンス**。

     >[!NOTE]
     >
     >これらのビジュアライゼーションは、Content Analytics設定に [ エクスペリエンスを含める ](/help/content-analytics/config/guided.md#experience-capture-and-definition) を加えた）場合にのみ表示されます。
     > 

      * **エクスペリエンス CTR**：エクスペリエンス CTR を表示する [ 変更概要 ](/help/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。
      * **上位のエクスペリエンスのコンバージョン**：選択したコンバージョン指標に基づいて、上位のコンバージョンエクスペリエンスを表示する [ 横棒 ](/help/analysis-workspace/visualizations/horizontal-bar.md) ビジュアライゼーション。
      * **最もパフォーマンスの高いエクスペリエンス**：最もパフォーマンスの高いエクスペリエンスの [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （[ サムネール ](#thumbnails) および [ プレビュー ](#previews) を含む）。

   * **Assets**

      * **アセット CTR**
アセット CTR を表示する [ 変更概要 ](/help/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。
      * **上位のコンバージョンアセット**
選択したコンバージョン指標に基づいて、コンバージョン率上位のアセットを表示する [ 横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) ビジュアライゼーション。
      * **最もパフォーマンスの高いアセット**
最もパフォーマンスの高いアセットの [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （[ サムネール ](#thumbnails) および [ プレビュー ](#previews) を含む）。
      * **Assets - ビューとコンバージョン。**
アセットビューとアセットのコンバージョンの散布図を表示する [ 散布図 ](/help/analysis-workspace/visualizations/scatterplot.md) ビジュアライゼーション。

* **コンバージョンに貢献するアセット属性はどれですか？**
Content Analyticsでは、AI と GenAI を使用して、被写体、シーン、前景色などのすべてのアセットメタデータを自動的に割り当てます。 属性は、アセットまたはエクスペリエンスの内容を説明する、AI によって割り当てられたメタデータタグです。 例：<code> 前景色：赤</code> は、自動的に割り当てられる属性です。 ビジュアライゼーションは、アセットのどの属性がコンバージョンに最も貢献しているかを特定するのに役立ちます。

  このパネルは、次のビジュアライゼーションで構成されます。

   * **アセット属性の変換上位**
[ 横棒 ](/help/analysis-workspace/visualizations/horizontal-bar.md)：選択したコンバージョン指標に基づいて、変換上位のアセット属性を表示します。
   * **過去 30 日間と比較したアセット属性のコンバージョン上位**
[ 横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) のビジュアライゼーション。選択したコンバージョン指標に基づいて、過去 30 日間と比較してコンバージョンの上位のアセット属性を表示します。
   * **アセット属性データの上位への変換**
選択したコンバージョン指標に基づいて、上位のコンバージョン属性を表示する [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 テーブルの行を選択して、属性トレンドビジュアライゼーションを更新します。
   * **属性トレンド**
選択した上位の変換アセット属性に関する属性トレンドを示す [ 折れ線グラフ ](/help/analysis-workspace/visualizations/line.md) ビジュアライゼーション。
   * **アセットの前景色**
単一のアセット属性カテゴリの項目のパフォーマンスを比較する [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) の例：前景色。 このアセット属性は、他のアセット属性カテゴリ分析コードに置き換えることができます。

* **コンバージョンに貢献するエクスペリエンス属性はどれですか？**

  >[!NOTE]
  >
  >このパネルは、Content Analyticsの設定に [ エクスペリエンスを含める ](/help/content-analytics/config/guided.md#experience-capture-and-definition) を行った場合にのみ表示されます。
  > 

  アセット属性が画像の視覚的特性に焦点を当てるのに対して、エクスペリエンス属性はページのテキストに焦点を当てます。 以下のビジュアライゼーションを使用すると、コンバージョンに貢献するエクスペリエンス属性を調べることができます。 また、これらの属性は、AI モデルと GenAI モデルを使用して自動的に割り当てられます。

  このパネルは、次のビジュアライゼーションで構成されます。

   * **エクスペリエンス属性の変換上位**
選択したコンバージョン指標に基づいて、変換上位のエクスペリエンス属性を表示する [ 横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) ビジュアライゼーション。
   * **過去 30 日間と比較したエクスペリエンス属性の上位のコンバージョン**
選択したコンバージョン指標に基づいて、過去 30 日間と比較して上位のコンバージョンエクスペリエンス属性を表示する [ 横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) ビジュアライゼーション。
   * **エクスペリエンス属性データの上位への変換**
選択したコンバージョン指標に基づいて、上位のコンバージョンエクスペリエンスを表示する [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 テーブルの行を選択して、線のビジュアライゼーションを更新します。
   * **行**
選択した上位のコンバージョンエクスペリエンス属性のトレンドを示す [ 折れ線グラフ ](/help/analysis-workspace/visualizations/line.md) ビジュアライゼーション。
   * **エクスペリエンスキーワード**
選択したコンバージョン指標に基づいて上位のエクスペリエンスキーワードを表示する [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。

* **アセットはサイト上のどこに表示されますか？**
最も多く表示されたアセットがサイト上で表示される場所の詳細を示す 1 つのフリーフォームテーブルで構成されるパネル。

  このパネルは、次の 1 つのビジュアライゼーションで構成されます。

   * **最も多く表示されたアセットはどこに表示されますか？**
アセットをディメンション別に分類すると、その画像が表示される場所をより深く理解できます。

     例 [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （[ サムネール ](#thumbnails) および [ プレビュー ](#previews) を含む）では、**[!UICONTROL アセット ID]** の代わりに [!UICONTROL &#x200B; アセット認識 ID] が使用されます。 サイト上で全く同じ画像が異なる画像 URL で重複する場合があります。 [!UICONTROL &#x200B; アセット知覚 ID] 属性を使用すると、これらの重複を 1 つの ID の下にグループ化できます。

     アセットはページ上で変更できるので、各アセットを **[!UICONTROL エクスペリエンス ID]** で分類して、アセットが表示されたページのバージョンを識別します。 [!UICONTROL &#x200B; エクスペリエンス ID] を、サイト上のアセットの場所を理解するのに役立つ他のディメンションに置き換えることができます。 例えば、[!UICONTROL &#x200B; ページ名 &#x200B;]、[!UICONTROL &#x200B; ページ URL]、または [!UICONTROL &#x200B; サイトセクション &#x200B;] です。

     また、[!UICONTROL &#x200B; アセット認識 ID] を [!UICONTROL &#x200B; アセット ID] に置き換えて、特定の画像 URL が参照されている場所の記録を取得することもできます。


>[!MORELIKETHIS]
>
>[Content Analytics コンポーネント ](components.md)
>[テンプレートを使用する ](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
