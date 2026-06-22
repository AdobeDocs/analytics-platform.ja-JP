---
title: Content Analytics レポート
description: 自由形式の表、棒グラフ、散布図などのビジュアライゼーションを使用してContent Analyticsでレポートを作成する方法について説明します。
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
TQID: https://experienceleague.adobe.com/IM7-a-jp-lLfuGKj-CM2McnFXcus2-x-ffLC8UUKAmY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 537fc30db0f6e6bddc54df7bbcc04d802226958f
workflow-type: tm+mt
source-wordcount: 1215
ht-degree: 51%

---


# Content Analytics レポートの概要

[Analysis Workspace](/help/analysis-workspace/home.md)内の[!DNL Content Analytics]に関するレポート、分析を実行し、インサイトを得ることができます。 特定の Workspace [テンプレート](#template)を使用できるので、関連するコンテンツインサイトを含む事前入力された Workspace プロジェクトに直ちにアクセスできます。

独自のContent Analytics レポートをゼロから作成するには、次の手順に従います。

1. [新しいプロジェクト &#x200B;](/help/analysis-workspace/build-workspace-project/create-projects.md)を作成するか、Workspaceで[既存のプロジェクト &#x200B;](/help/analysis-workspace/build-workspace-project/open-projects.md)を開きます。
1. Content Analytics レポート用に[データビューを選択](/help/analysis-workspace/c-panels/panels.md#data-view)します。 Content Analytics レポートは、Content Analytics で[設定](/help/content-analytics/config/configuration.md)されたデータビューでのみ使用できます。
1. ![表](/help/assets/icons/Table.svg) [自由形式の表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)のビジュアライゼーションをキャンバスにドラッグします。
1. [特定のコンテンツ分析コンポーネント](components.md)およびその他の汎用[コンポーネント](/help/components/overview.md)（セグメント、日付範囲、注釈など）を使用して、コンテンツ分析インサイトを作成します。
1. 他の[&#x200B; ビジュアライゼーション &#x200B;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)を使用して、プロジェクトを強化します。


## サムネイル

プロジェクトで使用するContent Analytics固有のディメンションに基づいて、サムネールは次のビジュアライゼーションに表示されます。

### フリーフォームテーブル

![Content Analytics サムネイル](../assets/aca-thumbnails.png)

デフォルトでは、サムネールは[&#x200B; フリーフォームテーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)に表示されます。 Content Analytics ディメンションのサムネイルの表示を設定するには：

* Content Analytics ディメンションのヘッダー行にポインタを合わせます。 例えば、**[!UICONTROL アセット ID]** や **[!UICONTROL エクスペリエンス ID]** などです。
* 「![設定](/help/assets/icons/Setting.svg)」を選択します。
* **[!UICONTROL 行設定]**&#x200B;ポップアップの&#x200B;**[!UICONTROL 設定]**&#x200B;の下の「**[!UICONTROL サムネイルを表示]**」をオンまたはオフにします。


### 棒グラフ（積み上げ）と横棒グラフ（積み上げ）

![棒グラフのContent Analytics サムネール &#x200B;](/help/content-analytics/assets/aca-bar-thumbnail.png)

サムネールは、垂直軸または水平軸に凡例の一部として表示されます。 [横棒（積み重ね） &#x200B;](/help/analysis-workspace/visualizations/bar.md)と[横棒（積み重ね） &#x200B;](/help/analysis-workspace/visualizations/horizontal-bar.md)の棒にカーソルを合わせると、サムネールも表示されます。


### 散布図

![散布用Content Analyticsのサムネール &#x200B;](/help/content-analytics/assets/aca-scatter-thumbnail.png)

[散布図](/help/analysis-workspace/visualizations/scatterplot.md)のデータポイントにカーソルを合わせると、サムネールが表示されます。


### 行

行![&#128279;](/help/content-analytics/assets/aca-line-thumbnail.png)のContent Analytics サムネール

[行](/help/analysis-workspace/visualizations/line.md)のデータポイントにカーソルを合わせると、サムネールが表示されます。

## プレビュー

プレビューポップアップウィンドウを開くことができます。 それには、次の手順を実行します。

* [自由形式テーブル &#x200B;](#freeform-table)で![InfoOutline](/help/assets/icons/InfoOutline.svg)を選択します。
* [棒](#bar-and-horizontal-bar)または[横棒](#bar-and-horizontal-bar) ビジュアライゼーションの特定の棒グラフ、または[散布図](#scatter) ビジュアライゼーションのデータポイントを選択します。


次の詳細が表示されます。

| エクスペリエンスのプレビュー | アセットのプレビュー |
|---|---|
| ![Content Analytics エクスペリエンスのプレビュー](../assets/aca-experience-preview.png) | ![Content Analytics アセットのプレビュー](../assets/aca-asset-preview.png) |
| ディメンションの名前（例：**[!UICONTROL エクスペリエンス ID]）** | アセットディメンションの名前（例：**[!UICONTROL アセット ID]）** |
| **[!UICONTROL インプレッション（通算）]**：エクスペリエンスのインプレッション数。 | **[!UICONTROL インプレッション（通算）]**：アセットのインプレッション数。 |
| **[!UICONTROL アセット]**：このエクスペリエンスに含まれるアセットの数。 <br/>![分類](/help/assets/icons/Breakdown.svg) **[!UICONTROL 分類]**&#x200B;を選択してアセットを調査します。 | **[!UICONTROL エクスペリエンス]**：このアセットが表示されるエクスペリエンスの数。 <br/>![分類](/help/assets/icons/Breakdown.svg) **[!UICONTROL 分類]**&#x200B;を選択してアセットを調査します。 |
| **[!UICONTROL 最初のインプレッション]**：エクスペリエンスの最初のインプレッションの日付。 | **[!UICONTROL 最初のインプレッション]**：アセットの最初のインプレッションの日付。 |
| **[!UICONTROL 最新のインプレッション]**：エクスペリエンスの最新のインプレッションの日付。 | **[!UICONTROL 最新のインプレッション]**：アセットの最新のインプレッションの日付。 |
| **[!UICONTROL エクスペリエンス属性]**：エクスペリエンスの[属性](/help/content-analytics/report/components.md#experience-attributes)。 | **[!UICONTROL アセット属性]**：アセットの[属性](/help/content-analytics/report/components.md#asset-attributes)。 |


## テンプレート

Content Analytics [&#x200B; テンプレート &#x200B;](/help/analysis-workspace/templates/use-templates.md)を使用すると、どのコンテンツとコンテンツ属性が最も効果的かを確認できます。 テンプレートは [web チャネルとエンゲージメントのユースケース](/help/analysis-workspace/templates/use-templates.md#web-engagement)の一部であり、コンテンツのパフォーマンスをきめ細かく示します。 個々のアセットや特定の属性のパフォーマンスを確認できます。

学習内容に基づいて、様々な操作を行うことができます。 ホームページで高パフォーマンスのアセットを昇格させるのと同様に、特定のセグメント用にコンテンツをパーソナライズして高パフォーマンスの属性を含めたり、古くなり始めたコンテンツを交代させたりします。

テンプレートを使用するには：

1. メインメニューから「**[!UICONTROL Workspace]**」を選択します。
1. Content Analytics 用に設定されているデータビューが選択されていることを確認します。
1. セグメント（**[!UICONTROL チャネル]**&#x200B;の場合は **[!UICONTROL web]**、**[!UICONTROL ユースケース]** の場合は&#x200B;**[!UICONTROL エンゲージメント]**）を検索または使用して、**[!UICONTROL コンテンツ分析]**&#x200B;テンプレートを検索して選択します。
1. 「**[!UICONTROL テンプレートを使用]**」を選択します。
1. **[!UICONTROL テンプレートを設定]**&#x200B;ダイアログで、**[!UICONTROL コンバージョン指標を選択]**&#x200B;ダイアログから指標を選択します。 例えば、**[!UICONTROL アセット CTR]** を選択します。
1. 「**[!UICONTROL 続行]**」を選択します。

**[!UICONTROL Content Analytics の概要]**&#x200B;プロジェクトが [Analysis Workspace](/help/analysis-workspace/home.md) で開きます。 プロジェクトは4つの[&#x200B; パネル &#x200B;](/help/analysis-workspace/c-panels/panels.md)で構成され、各パネルには[自由形式テーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)と[&#x200B; ビジュアライゼーション &#x200B;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)が用意され、特定の質問に答えることができます。

**[!UICONTROL コンテンツチャネル]**&#x200B;の分類を使用して、興味のあるコンテンツチャネルのパネルを[分類](/help/analysis-workspace/c-panels/panels.md#break-down-a-panel)することができます：**[!UICONTROL web]**&#x200B;または&#x200B;**[!UICONTROL モバイル]**。

![Analysis Workspaceのパネルでのコンテンツチャネルの分類](/help/content-analytics/assets/aca-content-channel-selector.png)

4つのパネルは次のとおりです。

* **最もパフォーマンスが高いコンテンツは何ですか？**
エンゲージメントとコンバージョンを促進するエクスペリエンスとアセットを特定します。エクスペリエンスとは、特定の時間にキャプチャされたweb ページ全体、またはモバイルアプリ内で定義されたテキスト、アセット、CTAの組み合わせです。

   * **エクスペリエンス**。

     >[!NOTE]
     >
     >これらのビジュアライゼーションは、Content Analyticsの設定に[&#x200B; エクスペリエンスを含めるようにシステムを設定した場合にのみ、テンプレートに表示されます。](/help/content-analytics/config/guided.md#experience-capture-and-definition)
     > 

      * **Experience CTR**: Experience CTRを示す[要約変更](/help/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。
      * **上位のコンバージョンエクスペリエンス**：選択したコンバージョン指標に基づいて、上位のコンバージョンエクスペリエンスを表示する[横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md)ビジュアライゼーション。
      * **パフォーマンスが最も高いエクスペリエンス**：パフォーマンスが最も高いエクスペリエンスの[&#x200B; フリーフォームテーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （[&#x200B; サムネール &#x200B;](#thumbnails)と[&#x200B; プレビュー](#previews)を含む）。

   * **Assets**

      * **アセット CTR**
アセットのCTRを示す[要約変更](/help/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション。
      * **最もコンバージョン率の高いアセット**
選択したコンバージョン指標に基づいて、最もコンバージョン率の高いアセットを表示する[横長バー](/help/analysis-workspace/visualizations/horizontal-bar.md)のビジュアライゼーション。
      * **パフォーマンスが最も高いアセット**
パフォーマンスが最も高いアセットの[&#x200B; フリーフォームテーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （[&#x200B; サムネール &#x200B;](#thumbnails)と[&#x200B; プレビュー](#previews)を含む）。
Assets - コンバージョンと比較したビュー。
アセットビューとアセット変換の散布図を示す[散布図](/help/analysis-workspace/visualizations/scatterplot.md) ビジュアライゼーション。

* **コンバージョンに貢献するアセット属性はどれですか？**
Content Analyticsは、AIと生成AIを活用して、被写体、シーン、前景色などのメタデータや属性をあらゆるアセットに自動的に割り当てます。

   * **アセット属性を変換中の上位**
選択したコンバージョン指標に基づいて、最もコンバージョン率の高いアセット属性を表示する[横棒](/help/analysis-workspace/visualizations/horizontal-bar.md)。
   * **過去30日間に最も多くコンバージョンしたアセット属性**
選択したコンバージョン指標に基づいて、過去30日間と比較して、最もコンバージョン率の高いアセット属性を示す[横長バー](/help/analysis-workspace/visualizations/horizontal-bar.md)のビジュアライゼーション。
   * **アセット属性データの変換上位**
選択したコンバージョン指標に基づいて最もコンバージョン率の高い属性を表示する[&#x200B; フリーフォームテーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 テーブルの行を選択して、属性トレンドビジュアライゼーションを更新します。
   * **属性トレンド**
選択したコンバージョン上位アセット属性の属性傾向を示す[行](/help/analysis-workspace/visualizations/line.md)のビジュアライゼーション。
   * **アセットの描画色**
単一のアセット属性カテゴリの項目のパフォーマンスを比較する例[自由形式テーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)：描画色。 このアセット属性は、他のアセット属性カテゴリディメンションに置き換えることができます。

* **コンバージョンに貢献するエクスペリエンス属性はどれですか？**

  >[!NOTE]
  >
  >このパネルは、Content Analytics 設定に[エクスペリエンスを含めた](/help/content-analytics/config/guided.md#experience-capture-and-definition)場合にのみ表示されます。
  > 

  アセット属性が画像の視覚的特性に焦点を当てるのに対して、エクスペリエンス属性はページのテキストに焦点を当てます。 以下のビジュアライゼーションを使用すると、どのエクスペリエンス属性がコンバージョンに貢献しているかを調べることができます。 また、これらの属性は、AI モデルと生成 AI モデルを使用して自動的に割り当てられます。

  パネルは、次のビジュアライゼーションで構成されています。

   * **エクスペリエンス属性の変換中**
選択したコンバージョン指標に基づいて、最もコンバージョン率の高いエクスペリエンス属性を表示する[水平バー](/help/analysis-workspace/visualizations/horizontal-bar.md)のビジュアライゼーション。
過去30日間と比較した、コンバージョン率の高いエクスペリエンス属性
選択したコンバージョン指標に基づいて、過去30日間と比較して、最もコンバージョン率の高いエクスペリエンス属性を示す[水平バー](/help/analysis-workspace/visualizations/horizontal-bar.md)のビジュアライゼーション。
   * **変換中のエクスペリエンス属性データ**
選択したコンバージョン指標に基づいて、最もコンバージョン率の高いエクスペリエンスを表示する[&#x200B; フリーフォームテーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 テーブルの行を選択して、折れ線グラフのビジュアライゼーションを更新します。
   * **行**
選択したコンバージョン上位のエクスペリエンス属性の傾向を示す[行](/help/analysis-workspace/visualizations/line.md)のビジュアライゼーション。
   * **エクスペリエンスキーワード**
選択したコンバージョン指標に基づく上位エクスペリエンス キーワードを表示する[&#x200B; フリーフォーム テーブル &#x200B;](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。

* **アセットはサイトのどこに表示されますか？**
このフリーフォームテーブルは、最も閲覧されたアセットが表示される場所を詳細に示します。この分析を利用して、パフォーマンスの高いページを特定し、アセットの配置を最適化することができます。

   * **最も閲覧されたアセットはどこに表示されますか？**
任意のアセットをディメンションごとに分類することで、画像がどこで表示されるのかを的確に把握できます。

     サンプルの[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)（[サムネイル](#thumbnails)および[プレビュー](#previews)を含む）では、**[!UICONTROL アセット ID]** の代わりに[!UICONTROL アセット認識 ID] が使用されています。 時には、異なる画像 URL を持つまったく同じ画像が、サイトに複製されることがあります。 [!UICONTROL アセット認識 ID] 属性を使用すると、これらの重複を 1 つの ID にグループ化できます。

     アセットはページ上で変更できるので、システムは各アセットを&#x200B;**[!UICONTROL Experience Id]**&#x200B;で分類して、アセットが表示されたページのバージョンを特定します。 [!UICONTROL エクスペリエンス ID] は、サイト上のアセットの場所を把握するのに役立つ他のディメンションに置き換えることができます。 例えば、[!UICONTROL ページ名]、[!UICONTROL ページ URL]、または[!UICONTROL サイトセクション]などに置き換えることができます。

     また、[!UICONTROL アセット認識 ID] を[!UICONTROL アセット ID] に置き換えて、特定の画像 URL が参照されている場所のレコードを取得することもできます。


>[!MORELIKETHIS]
>
>[Content Analytics コンポーネント &#x200B;](components.md)
>[&#x200B; テンプレートを使用](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
