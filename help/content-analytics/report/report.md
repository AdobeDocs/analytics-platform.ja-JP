---
title: Content Analytics レポート
description: Content Analytics についてのレポート方法
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 95%

---

# Content Analytics レポートの概要

[Analysis Workspace](/help/analysis-workspace/home.md) 内で Content Analytics についてレポートし、分析を実行して、インサイトを得ます。特定の Workspace [テンプレート](#template)を使用できるので、関連するコンテンツインサイトを含む事前入力された Workspace プロジェクトに直ちにアクセスできます。

Content Analytics についてのレポートをゼロから開始するには：

1. Workspace で[新しいプロジェクトを作成](/help/analysis-workspace/build-workspace-project/create-projects.md)するか、[既存のプロジェクトを開き](/help/analysis-workspace/build-workspace-project/open-projects.md)ます。
1. Content Analytics レポート用に[データビューを選択](/help/analysis-workspace/c-panels/panels.md#data-view)します。Content Analytics レポートは、Content Analytics で[設定](/help/content-analytics/config/configuration.md)されたデータビューでのみ使用できます。
1. ![テーブル](/help/assets/icons/Table.svg) [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)ビジュアライゼーションをキャンバスにドラッグします。
1. [&#x200B; 特定のContent Analytics コンポーネント &#x200B;](components.md) およびその他の汎用 [&#x200B; コンポーネント &#x200B;](/help/components/overview.md) （セグメント、日付範囲、注釈など）を使用して、Content Analytics インサイトを構築します。

## サムネイル

プロジェクトで使用する Content Analytics 固有のディメンションに基づいて、アセットとディメンションにサムネイルが表示されます。

![Content Analytics サムネイル](../assets/aca-thumbnails.png)

デフォルトでは、関連する Content Analytics ディメンションのサムネイルが表示されます。Content Analytics ディメンションのサムネイルの表示を設定するには：

* Content Analytics ディメンションのヘッダー行にポインタを合わせます。例えば、**[!UICONTROL アセット ID]** や **[!UICONTROL エクスペリエンス ID]** などです。
* 「![設定](/help/assets/icons/Setting.svg)」を選択します。
* **[!UICONTROL 行設定]**&#x200B;ポップアップの&#x200B;**[!UICONTROL 設定]**&#x200B;の下の「**[!UICONTROL サムネイルを表示]**」をオンまたはオフにします。


## プレビュー

Content Analytics ディメンションの行にサムネイルが表示される場合は、プレビューポップアップウィンドウを開くことができます。

次の詳細を含むプレビューを開くには：

* ![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択します。次の詳細が表示されます。

  | エクスペリエンスのプレビュー | アセットのプレビュー |
  |---|---|
  | ![Content Analytics エクスペリエンスのプレビュー](../assets/aca-experience-preview.png) | ![Content Analytics アセットのプレビュー](../assets/aca-asset-preview.png) |
  | ディメンションの名前（例：**[!UICONTROL エクスペリエンス ID]）** | アセットディメンションの名前（例：**[!UICONTROL アセット ID]）** |
  | **[!UICONTROL インプレッション（通算）]**：エクスペリエンスのインプレッション数。 | **[!UICONTROL インプレッション（通算）]**：アセットのインプレッション数。 |
  | **[!UICONTROL アセット]**：このエクスペリエンスに含まれるアセットの数。<br/>![分類](/help/assets/icons/Breakdown.svg) **[!UICONTROL 分類]**&#x200B;を選択してアセットを調査します。 | **[!UICONTROL エクスペリエンス]**：このアセットが表示されるエクスペリエンスの数。<br/>![分類](/help/assets/icons/Breakdown.svg) **[!UICONTROL 分類]**&#x200B;を選択してアセットを調査します。 |
  | **[!UICONTROL 最初のインプレッション]**：エクスペリエンスの最初のインプレッションの日付。 | **[!UICONTROL 最初のインプレッション]**：アセットの最初のインプレッションの日付。 |
  | **[!UICONTROL 最新のインプレッション]**：エクスペリエンスの最新のインプレッションの日付。 | **[!UICONTROL 最新のインプレッション]**：アセットの最新のインプレッションの日付。 |
  | **[!UICONTROL エクスペリエンス属性]**：エクスペリエンスの[属性](/help/content-analytics/report/components.md#experience-attributes)。 | **[!UICONTROL アセット属性]**：アセットの[属性](/help/content-analytics/report/components.md#asset-attributes)。 |


## テンプレート

Content Analytics[&#x200B; テンプレート &#x200B;](/help/analysis-workspace/templates/use-templates.md) を使用すると、最もパフォーマンスの高いコンテンツやコンテンツ属性を把握できます。 テンプレートは [web チャネルとエンゲージメントのユースケース](/help/analysis-workspace/templates/use-templates.md#web-engagement)の一部であり、コンテンツのパフォーマンスをきめ細かく示します。個々のアセットや特定の属性のパフォーマンスを確認できます。

学習内容に基づいて、様々な操作を行うことができます。ホームページで高パフォーマンスのアセットを昇格させるのと同様に、特定のセグメント用にコンテンツをパーソナライズして高パフォーマンスの属性を含めたり、古くなり始めたコンテンツを交代させたりします。

テンプレートを使用するには：

1. メインメニューから「**[!UICONTROL Workspace]**」を選択します。
1. Content Analytics 用に設定されているデータビューが選択されていることを確認します。
1. **&#x200B; **&#x200B;[!UICONTROL チャネル] **&#x200B; の場合はセグメント（**&#x200B;[!UICONTROL Web]&#x200B;**、**&#x200B;**[!UICONTROL ユースケース]** の場合はエンゲージメント [!UICONTROL &#x200B; を検索または使用して、&lbrace;8]Content Analytics **[!UICONTROL テンプレートを検索および選択します。]**
1. 「**[!UICONTROL テンプレートを使用]**」を選択します。
1. **[!UICONTROL テンプレートを設定]**&#x200B;ダイアログで、**[!UICONTROL コンバージョン指標を選択]**&#x200B;ダイアログから指標を選択します。例えば、**[!UICONTROL アセット CTR]** を選択します。
1. 「**[!UICONTROL 続行]**」を選択します。

**[!UICONTROL Content Analytics の概要]**&#x200B;プロジェクトが [Analysis Workspace](/help/analysis-workspace/home.md) で開きます。プロジェクトは 4 つの[パネル](/help/analysis-workspace/c-panels/panels.md)で構成され、各パネルには特定の質問に回答するための[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)および[ビジュアライゼーション](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)が表示されます。

* **最もパフォーマンスが高いコンテンツは何ですか？**
このパネルを使用すると、エンゲージメントとコンバージョンに寄与しているエクスペリエンスと、それらのエクスペリエンス内のアセットを理解できます。エクスペリエンスは、特定の時間にキャプチャされた完全な web ページです。エクスペリエンスには、テキストと複数の個々の画像アセットの両方を含めることができます。アセットは個々の画像です。

  パネルは、次のビジュアライゼーションで構成されています。

   * **エクスペリエンス**。

     >[!NOTE]
     >
     >これらのビジュアライゼーションは、Content Analytics 設定に[エクスペリエンスを含めた](/help/content-analytics/config/guided.md#experience-capture-and-definition)場合にのみ表示されます。
     > 

      * **エクスペリエンス CTR**：エクスペリエンス CTR を表示する[変更概要](/help/analysis-workspace/visualizations/summary-number-change.md)ビジュアライゼーション。
      * **上位のコンバージョンエクスペリエンス**：選択したコンバージョン指標に基づいて、上位のコンバージョンエクスペリエンスを表示する[横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md)ビジュアライゼーション。
      * **上位のパフォーマンスエクスペリエンス**：上位のパフォーマンスエクスペリエンスの[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)（[サムネイル](#thumbnails)および[プレビュー](#previews)を含む）。

   * **Assets**

      * **アセット CTR**
アセット CTR を表示する[変更概要](/help/analysis-workspace/visualizations/summary-number-change.md)ビジュアライゼーション。
      * **上位のコンバージョンアセット**
選択したコンバージョン指標に基づいて、上位のコンバージョンアセットを表示する[横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md)ビジュアライゼーション。
      * **上位のパフォーマンスアセット**
上位のパフォーマンスアセットの[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)（[サムネイル](#thumbnails)および[プレビュー](#previews)を含む）。
      * **アセット - ビューとコンバージョンの比較。**
アセットビューとアセットコンバージョンの散布図を表示する[散布図](/help/analysis-workspace/visualizations/scatterplot.md)ビジュアライゼーション。

* **コンバージョンに貢献するアセット属性はどれですか？**
Content Analytics では、AI と生成 AI を使用して、被写体、シーン、前景色などのすべてのアセットメタデータを自動的に割り当てます。属性は、アセットまたはエクスペリエンスの内容を説明する、AI によって割り当てられたメタデータタグです。例：<code>前景色：赤</code> は、自動的に割り当てられる属性です。ビジュアライゼーションは、アセットのどの属性がコンバージョンに最も貢献しているかを特定するのに役立ちます。

  パネルは、次のビジュアライゼーションで構成されています。

   * **上位のコンバージョンアセット属性**
選択したコンバージョン指標に基づいて、上位のコンバージョンアセット属性を表示する[横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md)。
   * **過去 30 日間と比較した上位のコンバージョンアセット属性**
選択したコンバージョン指標に基づいて、過去 30 日間と比較して上位のコンバージョンアセット属性を表示する[横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md)ビジュアライゼーション。
   * **上位のコンバージョンアセット属性データ**
選択したコンバージョン指標に基づいて、上位のコンバージョン属性を表示する[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。テーブルの行を選択して、属性トレンドビジュアライゼーションを更新します。
   * **属性トレンド**
選択した上位のコンバージョンアセット属性に関する属性トレンドを示す[折れ線グラフ](/help/analysis-workspace/visualizations/line.md)ビジュアライゼーション。
   * **アセットの前景色**
単一のアセット属性カテゴリの項目のパフォーマンスを比較する[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)の例：前景色。このアセット属性は、他のアセット属性カテゴリディメンションに置き換えることができます。

* **コンバージョンに貢献するエクスペリエンス属性はどれですか？**

  >[!NOTE]
  >
  >このパネルは、Content Analytics 設定に[エクスペリエンスを含めた](/help/content-analytics/config/guided.md#experience-capture-and-definition)場合にのみ表示されます。
  > 

  アセット属性が画像の視覚的特性に焦点を当てるのに対して、エクスペリエンス属性はページのテキストに焦点を当てます。以下のビジュアライゼーションを使用すると、どのエクスペリエンス属性がコンバージョンに貢献しているかを調べることができます。また、これらの属性は、AI モデルと生成 AI モデルを使用して自動的に割り当てられます。

  パネルは、次のビジュアライゼーションで構成されています。

   * **上位のコンバージョンエクスペリエンス属性**
選択したコンバージョン指標に基づいて、上位のコンバージョンエクスペリエンス属性を表示する[横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md)ビジュアライゼーション。
   * **過去 30 日間と比較した上位のコンバージョンエクスペリエンス属性**
選択したコンバージョン指標に基づいて、過去 30 日間と比較して上位のコンバージョンエクスペリエンス属性を表示する[横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md)ビジュアライゼーション。
   * **上位のコンバージョンエクスペリエンス属性データ**
選択したコンバージョン指標に基づいて、上位のコンバージョンエクスペリエンスを表示する[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。テーブルの行を選択して、折れ線グラフのビジュアライゼーションを更新します。
   * **折れ線グラフ**
選択した上位のコンバージョンエクスペリエンス属性のトレンドを示す[折れ線グラフ](/help/analysis-workspace/visualizations/line.md)ビジュアライゼーション。
   * **エクスペリエンスキーワード**
選択したコンバージョン指標に基づいて上位のエクスペリエンスキーワードを表示する[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。

* **アセットはサイトのどこに表示されますか？**
最も多く閲覧されたアセットがサイトのどこに表示されるかの詳細を示す、1 つのフリーフォームテーブルで構成されるパネル。

  このパネルは、次の 1 つのビジュアライゼーションで構成されます。

   * **最も多く閲覧されたアセットはどこに表示されますか？**
アセットをディメンション別に分類すると、その画像がどこに表示されるかをより深く理解できます。

     サンプルの[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)（[サムネイル](#thumbnails)および[プレビュー](#previews)を含む）では、**[!UICONTROL アセット ID]** の代わりに[!UICONTROL アセット認識 ID] が使用されています。時には、異なる画像 URL を持つまったく同じ画像が、サイトに複製されることがあります。[!UICONTROL アセット認識 ID] 属性を使用すると、これらの重複を 1 つの ID にグループ化できます。

     アセットはページ上で変更できるため、各アセットを&#x200B;**[!UICONTROL エクスペリエンス ID]** 別に分類して、アセットが表示されたページのバージョンを識別します。[!UICONTROL エクスペリエンス ID] は、サイト上のアセットの場所を把握するのに役立つ他のディメンションに置き換えることができます。例えば、[!UICONTROL ページ名]、[!UICONTROL ページ URL]、または[!UICONTROL サイトセクション]などに置き換えることができます。

     また、[!UICONTROL アセット認識 ID] を[!UICONTROL アセット ID] に置き換えて、特定の画像 URL が参照されている場所のレコードを取得することもできます。


>[!MORELIKETHIS]
>
>[Content Analytics コンポーネント](components.md)
>&#x200B;>[テンプレートを使用](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
