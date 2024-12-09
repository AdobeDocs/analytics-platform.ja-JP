---
description: Analysis Workspace でデータを視覚的に表します。
keywords: Analysis Workspace
title: ビジュアライゼーションの概要
feature: Visualizations
exl-id: ca9e0561-7a54-487a-9fdc-3bcf34f9bdb1
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '1616'
ht-degree: 17%

---

# ビジュアライゼーションの概要

Workspaceには、データを視覚的に表現できる様々なビジュアライゼーションが用意されています。 棒グラフ、ドーナツグラフ、ヒストグラム、折れ線グラフ、マップ、散布図などがあります。

## タイプ

Analysis Workspace では、次のビジュアライゼーションタイプを利用できます。

| アイコン | 名前 | 説明 |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [面グラフ](/help/analysis-workspace/visualizations/area.md) | 面グラフのビジュアライゼーション。 折れ線グラフに似ていますが、線の下に色付きの領域があります。指標が複数あり、2 個以上の指標の交差により表現される領域を視覚化する場合は、面グラフを使用します。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [棒グラフ](/help/analysis-workspace/visualizations/bar.md) | 1 つ以上の指標の様々な値を表す縦棒を持つ棒グラフビジュアライゼーション。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [ 積み重ね棒グラフ ](/help/analysis-workspace/visualizations/bar.md) | 1 つ以上の指標の様々な値を表す縦棒を持つ積み重ね棒グラフビジュアライゼーション。 |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [ブレット](/help/analysis-workspace/visualizations/bullet-graph.md) | 目的の値と他のパフォーマンス範囲（目標）との比較または測定を示すブレットグラフのビジュアライゼーション。 |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [コホートテーブル](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | コホートビジュアライゼーションは、特定の期間、共通の特性を共有する人々のグループです。 コホートテーブルは、リテンション、チャーン、または待ち時間の分析に役立ちます。 |
| ![コンボ](/help/assets/icons/ComboChart.svg) | [コンボ](combo-charts.md) | コンボグラフを使用すると、最初にテーブルを作成しなくても、比較ビジュアライゼーションをすばやく作成できます。 |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [ドーナツ](/help/analysis-workspace/visualizations/donut.md) | ドーナツビジュアライゼーションは、円グラフと同様に、データを全体の一部またはフィルターとして表示します。 |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [フォールアウト](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | フォールアウトビジュアライゼーションは、事前に定義された一連のページ間で、ユーザーが離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。 |
| ![ グラフパス ](/help/assets/icons/GraphPathing.svg) | [フロー](/help/analysis-workspace/visualizations/c-flow/flow.md) | フロービジュアライゼーションは、web サイトとアプリを介した正確な顧客パスを表示します。 |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | フリーフォームテーブルのビジュアライゼーションは、インタラクティブなビジュアライゼーションです。 フリーフォームテーブルのビジュアライゼーションは、Workspaceのデータ分析の基盤です。 |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [ヒストグラム](/help/analysis-workspace/visualizations/histogram.md) | ヒストグラムビジュアライゼーションは、指標の量に基づいて、個人、訪問、またはイベントをバケットにまとめます。 |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [横棒グラフ](/help/analysis-workspace/visualizations/horizontal-bar.md) | 横棒グラフビジュアライゼーションには、1 つ以上の指標の様々な値を表す横棒グラフが表示されます。 |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [ 積み重ね横棒グラフ ](/help/analysis-workspace/visualizations/horizontal-bar.md) | 積み重ね横棒グラフビジュアライゼーションには、1 つ以上の指標の様々な値を表す横棒グラフが表示されます。 |
| ![ ブランチ 3](/help/assets/icons/Branch3.svg) | [ジャーニー キャンバス ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | ジャーニーキャンバスのビジュアライゼーションは、ユーザーや顧客に提供するジャーニーを分析し、インサイトを得るのに役立ちます。 |
| ![ 主要指標 ](/help/assets/icons/KeyMetrics.svg) | [ 主要指標の概要 ](/help/analysis-workspace/visualizations/key-metric.md) | 主要指標の概要ビジュアライゼーションは、折れ線グラフ、変更概要および数値概要のビジュアライゼーションを組み合わせます。 |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [折れ線グラフ](/help/analysis-workspace/visualizations/line.md) | 折れ線グラフのビジュアライゼーションは、線を使用して指標を表し、時間の経過に伴う値の変化を示します。 折れ線グラフは、X 軸で時間を表します。 |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散布図](/help/analysis-workspace/visualizations/scatterplot.md) | 散布図のビジュアライゼーションには、ディメンション項目と最大 3 つの指標との関係が表示されます。 |
| ![PageRule](/help/assets/icons/PageRule.svg) | [ セクションヘッダー ](section-header.md) | パネル内のセクションを識別し、明確にする。 |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [変更の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | 変更概要ビジュアライゼーションには、選択したセル間の変更が 1 つの大きな数値またはパーセンテージで表示されます。 |
| ![123](/help/assets/icons/123.svg)</p> | [数値の概要](/help/analysis-workspace/visualizations/summary-number-change.md) | 数値の概要ビジュアライゼーションには、選択したセルが 1 つの大きな数値として表示されます。 |
| ![テキスト](/help/assets/icons/Text.svg) | [テキスト](/help/analysis-workspace/visualizations/text.md) | テキストビジュアライゼーションを使用すると、ユーザー定義のテキストをWorkspaceに追加できます。 パネルおよびビジュアライゼーションの説明の活用に加えて、分析とインサイトにコンテキストを追加するのに役立ちます。 |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [ツリーマップ](/help/analysis-workspace/visualizations/treemap.md)<p> | ツリーマップビジュアライゼーションでは、ネストされた長方形のセットとして、（ツリー構造の）階層データが表示されます。 |
| ![タイプ](/help/assets/icons/TwoDots.svg) | [ベン図](/help/analysis-workspace/visualizations/venn.md) | ベン図ビジュアライゼーションでは、円を使用して、最大 3 つのフィルターの指標の重複を表します。 |

<!-- Add beneath Horizontal bar in the table above: | [Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | Similar to Fallout, Journey canvas shows where persons left (fell out) and continued through (fell through) a predefined sequence of pages. <p>Unlike Fallout, Journey canvas supports not only linear journeys, but any number of entry points and paths. Furthermore, journeys can be created in Adobe Journey Optimizer and then analyzed in Journey canvas.</p> | -->

## パネルへのビジュアライゼーションの追加

1. ビジュアライゼーションを追加するWorkspace プロジェクトを開きます。

1. 次のいずれかの方法を使用して、ビジュアライゼーションを追加します。

   ![ ビジュアライゼーションを追加 ](assets/add-visualization.png)

   * 左側のパネルで「![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg)**ビジュアライゼーション**」を選択し、ビジュアライゼーションを追加するパネルにビジュアライゼーションをドラッグします。

   * ビジュアライゼーションを追加するパネルで「![AddCircle](/help/assets/icons/AddCircle.svg)」を選択し、追加するビジュアライゼーションを表すアイコンを選択します。 各ビジュアライゼーションのアイコンにマウスポインターを置くと、名前が表示されます。

   * [ 空のパネル ](/help/analysis-workspace/c-panels/blank-panel.md) を追加してから、追加するビジュアライゼーションを選択します。

   * Analysis Workspace プロジェクト内の既存のビジュアライゼーションのコンテキストメニューから、**[!UICONTROL ビジュアライゼーションを複製]** または **[!UICONTROL ビジュアライゼーションをコピー]** を選択します。

   * Workspace **[!UICONTROL 挿入]** メニューを使用して、ビジュアライゼーションを挿入します。

   * フリーフォームテーブルのコンテキストメニューから、「**[!UICONTROL 視覚化]**」を選択します。 次に、サブメニューからビジュアライゼーションを選択します。 Workspaceは、テーブル内の現在の選択内容に基づいて、提供するビジュアライゼーションを判断し、データを解釈してリクエストされたビジュアライゼーションを作成します。


## 凡例

ビジュアライゼーションの凡例を使用すると、ソーステーブルの日付をビジュアライゼーション内のプロットされたシリーズに関連付けることができます。凡例はインタラクティブです。凡例項目を選択して、ビジュアライゼーション内のシリーズの表示/非表示を切り替えることができます。これは、視覚化するデータを簡略化する場合に役立ちます。

また、凡例ラベルの名前を変更して、図をより使いやすくすることができます。メモ：凡例の編集は、ツリーマップ、ブレットグラフ、変更の概要／数値の概要、テキスト、フリーフォーム、ヒストグラム、コホート、またはフローのビジュアライゼーションには&#x200B;**適用されません**。

凡例ラベルを編集するには、次の手順を実行します。

1. 凡例ラベルの 1 つを右クリックします。
1. 「**[!UICONTROL ラベルを編集]**」をクリックします。

   ![ 凡例ラベルと「ラベルを編集」オプション。](assets/edit-label.png)

1. 新しいラベルテキストを入力します。
1. **[!UICONTROL Enter]** キーを押して保存します。


## 設定

ビジュアライゼーションごとに独自の設定があります。 ビジュアライゼーション設定にアクセスするには、ビジュアライゼーションヘッダーで ![ 設定 ](/help/assets/icons/Setting.svg) **[!UICONTROL 設定]** を選択して、ポップアップを表示します。

ビジュアライゼーションに応じて、次を設定できます

* [**[!UICONTROL  データソース ]**](#data-source) タブを介したビジュアライゼーションのデータソースの詳細。
* [**[!UICONTROL  設定 ]**](#settings-1) タブを使用したビジュアライゼーションの設定。

![ビジュアライゼーション設定](assets/visualization-settings.png)

### データソース

ビジュアライゼーションに対応するデータソースと、そのデータソース内の項目または位置を制御できます。 詳しくは、[ データソースの管理 ](t-sync-visualization.md) を参照してください。

### 設定

使用できるビジュアライゼーション設定は、ビジュアライゼーションによって異なります。 次の表に、最も一般的な設定を示します。 一部のビジュアライゼーションには特定の設定があります。 詳しくは、個々のビジュアライゼーションのドキュメントを参照してください。

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL ビジュアライゼーションのタイプ]** | データの視覚化に使用するビジュアライゼーションのタイプを変更します。 |
| **[!UICONTROL 精度]** | トレンドのビジュアライゼーションの時間の精度を変更する。 この変更は、データソーステーブルにも適用されます。 |
| **[!UICONTROL 割合 (％)]** | 値をパーセンテージで表示します。 |
| **[!UICONTROL 100% の積み重ね]** | グラフを 100% 積み重ねビジュアライゼーションに変更します。  面グラフ、棒グラフ、積み重ね横棒グラフのビジュアライゼーションにのみ適用できます。 |
| **[!UICONTROL 凡例を表示]** | 凡例のテキストを表示します。 |
| **[!UICONTROL 項目数の上限を設定]** | ビジュアライゼーションで表示する項目の数を制限します。 選択した場合、最大項目数を定義します。 |
| **[!UICONTROL 注釈を表示]** | このビジュアライゼーション用に作成された注釈を表示します。 |
| **[!UICONTROL タイトルを非表示]** | ビジュアライゼーションのタイトルを非表示にします。 |
| **[!UICONTROL Y 軸をゼロに固定]** | Y 軸の一番下を強制的にゼロにします。 グラフにプロットされるすべての値がゼロを大幅に上回る場合、グラフのデフォルトでは y 軸の一番下がゼロ以外になります。 このオプションを有効にすると、Y 軸がゼロに設定され、グラフが再描画されます。 |
| **[!UICONTROL 二重軸を表示]** | 2 つの異なる指標の左右の Y 軸を表示します。 このオプションは、2 つの指標がある場合にのみ適用されます。 2 軸は、プロットされた指標の大きさが異なる場合に役立ちます。 |
| **[!UICONTROL X 軸を表示]** | ビジュアライゼーションに X 軸を表示します。 |
| **[!UICONTROL Y 軸を表示]** | ビジュアライゼーションに y 軸を表示します。 |
| **[!UICONTROL 線上にバーベルを表示]** | 複合グラフビジュアライゼーションの折れ線グラフのビジュアライゼーションにバーベルを表示します。 |
| **[!UICONTROL 正規化]** | 指標を均等な比率にします。 等しい比率は、プロットされた指標の大きさが異なる場合に役立ちます。 |
| **[!UICONTROL 異常値を表示]** | 異常値検出を表示することで、折れ線グラフとフリーフォームテーブルを強化します。 線のビジュアライゼーションでの異常値検出には、期待値（破線）と期待範囲（影付きの帯）が含まれます。 |
| **[!UICONTROL 予測を表示]** | 予測値を表示して、折れ線グラフとフリーフォームテーブルを強化します。 |
| **[!UICONTROL 最小値を表示]** | ビジュアライゼーションに最小値を表示します。 |
| **[!UICONTROL 最大値を表示]** | ビジュアライゼーションに最大値を表示します。 |
| **[!UICONTROL トレンドラインを表示]** | ビジュアライゼーションにトレンドラインを表示します。 選択した場合、トレンドラインのタイプをドロップダウンメニューから選択できます。 |



作成するすべてのビジュアライゼーションの設定をカスタマイズできます。 詳しくは、[ユーザー環境設定](/help/analysis-workspace/user-preferences.md)を参照してください。


## コンテキストメニュー {#right-click}

ビジュアライゼーションのヘッダーのコンテキストメニュー（代替選択を通じて使用可能。例えば、マウスを使用して右クリックする）を使用して、ビジュアライゼーションの追加機能にアクセスします。 すべてのビジュアライゼーションですべてのオプションを使用できるわけではありません。

![ 右クリックオプションが表示された追加のビジュアライゼーション設定。 オプションについては、次のセクションで説明します。](assets/right-click.png)

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL コピーしたビジュアライゼーションを挿入]** | コピーしたビジュアライゼーションを、プロジェクト内の別の場所、または完全に別のプロジェクトに貼り付け（挿入）します。 |
| **[!UICONTROL データをクリップボードにコピー]** | ビジュアライゼーションからクリップボードにデータをコピーします。 |
| **[!UICONTROL 選択範囲をクリップボードにコピー]** | ビジュアライゼーションからクリップボードに選択範囲をコピーします。 |
| **[!UICONTROL 項目を CSV としてダウンロード （*ディメンション名*）]** | ビジュアライゼーションのディメンション項目（最大 50,000 個）をローカルデバイスにダウンロードします。 選択したディメンションに対して最大 50,000 個のディメンション項目。 |
| **[!UICONTROL ビジュアライゼーションをコピー]** | ビジュアライゼーションをコピーして、ビジュアライゼーションをプロジェクト内の別の場所、または完全に別のプロジェクトに挿入できるようにします。 |
| **[!UICONTROL データ CSV をダウンロード]** | ビジュアライゼーションの表示データをローカルデバイスにダウンロードします。 |
| **[!UICONTROL テーブル全体をエクスポート]** | 指定したクラウドの場所にテーブル全体を書き出します。 [Customer Journey Analyticsレポートのクラウドへの書き出し ](../export/export-cloud.md) を参照してください。 |
| **[!UICONTROL ビジュアライゼーションを複製]** | ビジュアライゼーションの完全な複製を作成します。 |
| **[!UICONTROL 説明を編集]** | ビジュアライゼーションの説明テキストを追加（または編集）します。 [ テキスト ](text.md) を参照してください。 |
| **[!UICONTROL ビジュアライゼーションリンクを取得]** | リンクをコピーして、ビジュアライゼーションと直接共有します。 共有リンク ダイアログにリンクが表示されます。 「コピー」を選択して、リンクをクリップボードにコピーします。 |
| **[!UICONTROL やり直し]** | 現在のビジュアライゼーションの設定を削除して、ゼロから再設定できるようにします。 |

## 設定

一部のビジュアライゼーション（コホートテーブル、フォールアウト、フローなど）には、ビジュアライゼーションの作成を支援する設定ダイアログがあります。 ビジュアライゼーションの上部にある「![ 編集 ](/help/assets/icons/Edit.svg)」を使用して、設定にアクセスし変更します。

![ 設定ペイン ](assets/configuration.png)

## 視覚化

どのビジュアライゼーションが選択されるかわからない場合は、フリーフォームテーブルの行の ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg)**[!UICONTROL Visualize]** を選択します（カーソルを合わせると使用できます）。 この選択は、ビジュアライゼーションを追加する最も速い方法です。 Analysis Workspaceは、データに最適なビジュアライゼーションを知識に基づいて推測します。 例えば、1 つの行を選択した場合、トレンド [ 折れ線グラフ ](line.md) が作成されます。 3 つのフィルター行を選択した場合は、[ ベン ](venn.md) 図が作成されます。

![クイックビジュアライゼーション](assets/quick-viz.png)
