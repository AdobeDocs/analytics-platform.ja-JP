---
title: コンテンツ分析レポート
description: コンテンツ分析のレポート方法
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: df3a877feed82f6cbd181561da68837373bdafb8
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 0%

---

# コンテンツ分析レポートの概要

>[!WARNING]
>
>この記事は、今後の最終バージョンの非公式ドラフトバージョンであり、コンテンツ分析ドキュメントの一部です。 すべてのコンテンツは変更される可能性があり、この記事の現在のバージョンから法的義務を引き出すことはできません。
>

{{release-limited-testing}}

コンテンツ分析に関するレポートは、Analysis Workspace内で行われます。 特定のWorkspace[ テンプレート ](#template) を使用できるので、関連するコンテンツインサイトを含む事前入力されたWorkspace プロジェクトに直ちにアクセスできます。

コンテンツ分析に関するレポートをゼロから開始するには：

1. Workspaceで [ 新しいプロジェクトを作成 ](/help/analysis-workspace/build-workspace-project/create-projects.md) または [ 既存のプロジェクトを開く ](/help/analysis-workspace/build-workspace-project/open-projects.md) ことができます。
1. Content Analyticsのレポート用に [ データビューを選択 ](/help/analysis-workspace/c-panels/panels.md#data-view) してください。 Content Analytics レポートは、Content Analyticsで [ 設定 ](/help/content-analytics/config/configuration.md) されたデータビューでのみ使用できます。
1. ![ テーブル ](/help/assets/icons/Table.svg) フリーフォームテーブル [ ビジュアライゼーションをキャンバス ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ドラッグします。
1. [ 特定のコンテンツ分析コンポーネント ](components.md) およびその他の汎用 [ コンポーネント ](/help/components/overview.md) （フィルター、日付範囲、注釈など）を使用して、コンテンツ分析インサイトを作成します。 または、[ コンテンツ分析テンプレート ](#template) を使用します。

## サムネール

プロジェクトで使用する Content Analytics 固有のディメンションに基づいて、アセットとディメンションにサムネイルが表示されます。

![Content Analytics のサムネール ](../assets/aca-thumbnails.png)

## プレビュー

サムネールのあるディメンション（アセット名、エクスペリエンス名など）の場合は、プレビューポップアップウィンドウを開くことができます。

次の詳細を含むプレビューを開くには：

* ![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択します。 次の詳細が表示されます。

  | エクスペリエンスのプレビュー | アセットのプレビュー |
  |---|---|
  | ![Content Analytics エクスペリエンスのプレビュー ](../assets/aca-experience-preview.png) | ![Content Analytics アセットのプレビュー ](../assets/aca-asset-preview.png) |
  | **[!UICONTROL エクスペリエンスの名前]** | **[!UICONTROL アセットの名前]** |
  | **[!UICONTROL インプレッション数（常に）]**：エクスペリエンスのインプレッション数。 | **[!UICONTROL インプレッション数（常に）]**：アセットのインプレッション数。 |
  | **[!UICONTROL Assets]**：このエクスペリエンスに含まれるアセットの数。 ![ 分類 ](/help/assets/icons/Breakdown.svg)**[!UICONTROL 分類]** を選択して、アセットを調べます。 | **[!UICONTROL エクスペリエンス]**：このアセットが表示されるエクスペリエンスの数。 ![ 分類 ](/help/assets/icons/Breakdown.svg)**[!UICONTROL 分類]** して、アセットを調べます。 |
  | **[!UICONTROL ファーストインプレッション]**：エクスペリエンスのファーストインプレッションの日付。 | **[!UICONTROL 最初のインプレッション]**：アセットの最初のインプレッションの日付。 |
  | **[!UICONTROL 最新のインプレッション]**：エクスペリエンスの最新のインプレッションの日付。 | **[!UICONTROL 最新のインプレッション]**：アセットの最新のインプレッションの日付。 |
  | **[!UICONTROL エクスペリエンス属性]**：エクスペリエンスの属性。 | **[!UICONTROL アセット属性]**：アセットの属性。 |


## テンプレート

コンテンツ分析 [ テンプレート ](/help/analysis-workspace/templates/use-templates.md) を使用すると、最もパフォーマンスの高いコンテンツやコンテンツ属性を把握できます。 テンプレートは [web チャネルとエンゲージメントのユースケース ](/help/analysis-workspace/templates/use-templates.md#web-engagement) の一部であり、コンテンツのパフォーマンスをきめ細かく示します。 個々のアセットや特定の属性のパフォーマンスを確認できます。

学んだことに基づいて、いくつかの作業を行うことができます。 ホームページで高パフォーマンスのアセットを昇格するのと同様に、特定のセグメント用にコンテンツをパーソナライズして高パフォーマンスの属性を含めたり、古くなり始めたコンテンツを回転させたりします。

テンプレートを使用するには：

1. メインメニューから ]**0}Workspace} を選択します。**[!UICONTROL 
1. Content Analytics用に設定されたデータビューを選択していることを確認します。
1. **[!UICONTROL チャネル]** の場合はフィルター（**[!UICONTROL Web]** を、**[!UICONTROL  ユースケース **[!UICONTROL の場合は ] エンゲージメント]** を検索**たは使用して、**[!UICONTROL コンテンツ分析]** テンプレートを検索して選択します。
1. **[!UICONTROL テンプレートを使用]** を選択します。
1. **[!UICONTROL テンプレートの設定]** ダイアログで、**[!UICONTROL コンバージョン指標を選択]** ダイアログから指標を選択します。 例えば、**[!UICONTROL Asset CTR]** と入力します。
1. 「**[!UICONTROL 続行]**」を選択します。

Workspaceに **[!UICONTROL Content Analyticsの概要]** プロジェクトが開きます。 このプロジェクトは 4 つのパネルで構成され、それぞれが特定の質問に回答します。

* **最もパフォーマンスの高いコンテンツは何ですか？**
このパネルを使用すると、エンゲージメントとコンバージョンに寄与しているエクスペリエンスと、それらのエクスペリエンス内のアセットを理解できます。 エクスペリエンスは、特定の時間にキャプチャされた完全な web ページです。 エクスペリエンスには、テキストと複数の個々の画像アセットの両方を含めることができます。 アセットは個々の画像です。

  このパネルは、次のビジュアライゼーションで構成されます。

   * **エクスペリエンス**

      * **エクスペリエンス CTR**：エクスペリエンス CTR を表示する、変更概要ビジュアライゼーション。
      * **エクスペリエンスの上位変換**：選択したコンバージョン指標に基づいて、上位のコンバージョンエクスペリエンスを表示する横棒グラフビジュアライゼーション。
      * **最もパフォーマンスの高いエクスペリエンス**：最もパフォーマンスの高いエクスペリエンスに関するフリーフォームテーブル（サムネールとプレビューを含む）。

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
サイト上で最も多くのビューアセットが表示される場所の詳細を示す 1 つのフリーフォームテーブルで構成されるパネル。

  このパネルは、次の 1 つのビジュアライゼーションで構成されます。

   * **最も多く表示されたアセットはどこに表示されますか？**
アセット ID をディメンション別に分類すると、その画像が表示される場所をより深く理解できます。

     この例 [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （[ サムネール ](#thumbnails) および [ プレビュー ](#previews) を含む）では、[!UICONTROL *アセット ID*] の代わりに [!UICONTROL *アセット認識 ID*] が使用されます。 サイト上で全く同じ画像が異なる画像 URL で重複する場合があります。 [!UICONTROL _アセット認識_] 属性は、これらの重複を 1 つの ID の下にグループ化するのに役立ちます。 アセットはページ上で変更できるので、各アセットを [!UICONTROL _エクスペリエンス ID_] で分類して、そのアセットが表示されたページのバージョンを識別します。

     [!UICONTROL _エクスペリエンス ID_] を、サイト上のアセットの場所を理解するのに役立つ他のディメンションに置き換えることができます。 例えば、[!UICONTROL _ページ名_]、[!UICONTROL _ページ URL_]、または [!UICONTROL _サイトセクション_] です。

     また、[!UICONTROL _知覚 ID_] を [!UICONTROL _アセット ID_] に置き換えて、特定の画像 URL が参照されている場所の記録を取得することもできます。


>[!MORELIKETHIS]
>
>[Content Analytics コンポーネント ](components.md)
>[テンプレートを使用する ](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
