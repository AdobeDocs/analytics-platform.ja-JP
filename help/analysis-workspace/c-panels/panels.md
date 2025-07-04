---
description: パネルと、Analysis Workspaceでのパネルの使用方法について説明します。
title: パネルの概要
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '2143'
ht-degree: 99%

---

# パネルの概要 {#panels-overview}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="リアルタイム更新"
>abstract="このパネルのデータとビジュアライゼーションをリアルタイムで更新できます。"


[!UICONTROL パネル] は、テーブルとビジュアライゼーションのコレクションです。パネルには、Workspace の左上のアイコンまたは[空のパネル](/help/analysis-workspace/c-panels/blank-panel.md)からアクセスできます。パネルは、期間、データビュー、分析ユースケースに従ってプロジェクトを整理する場合に役立ちます。

## パネルタイプ

[!UICONTROL Customer Journey Analytics] の Analysis Workspace では、次のパネルタイプを使用できます。

| パネル名 | 説明 |
| --- | --- |
| [空のパネル](/help/analysis-workspace/c-panels/blank-panel.md) | 使用可能なパネルおよびビジュアライゼーションから選択し、分析を開始します。 |
| [アトリビューション](attribution.md) | 任意のディメンションとコンバージョン指標を使用して、アトリビューションモデルをすばやく比較および視覚化します。 |
| [実験](experimentation.md) | 様々なユーザーエクスペリエンス、マーケティングまたはメッセージングのバリエーションを比較して、特定の結果を導くのに最適なものを判断します。 |
| [フリーフォーム](freeform-panel.md) | 無制限の比較および分類を実行し、ビジュアライゼーションを追加して豊かなデータのストーリーを示します。 |
| [メディア分平均オーディエンス](average-minute-audience-panel.md) | 特定のコンテンツまたはカスタマイズされた期間での分平均オーディエンスを分析します。 |
| [メディア同時閲覧者数](media-concurrent-viewers.md) | 同時実行のピークの詳細と分類および比較機能を使用して、経時的に同時視聴者を分析します。 |
| [メディア再生滞在時間](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | 再生に費やした時間を分析して、同時実行のピークが発生した場所やドロップオフが発生した場所を把握します。 |
| [次または前の項目](next-previous.md) | ユーザーが移動する次のページまたは前のページを表示します。 |
| [クイックインサイト](quickinsight.md) | フリーフォームテーブルとそれに伴うビジュアライゼーションを素早く作成し、インサイトを迅速に分析して取得します。 |


分析を開始するには、[!UICONTROL クイックインサイト]パネル、[!UICONTROL 空白]パネル、[!UICONTROL フリーフォーム]パネルが最適です。一方、[!UICONTROL アトリビューション]は、より高度な分析に適しています。キャンバスの下部に ![AddCircle](/help/assets/icons/AddCircle.svg) が表示されるので、いつでも空白のパネルを追加できます。

デフォルトの開始パネルは[!UICONTROL フリーフォーム]パネルですが、[空白パネル](/help/analysis-workspace/c-panels/blank-panel.md)または[クイックインサイト](/help/analysis-workspace/c-panels/quickinsight.md)をデフォルトにすることができます。詳しくは、[プロジェクトと分析の環境設定](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences)を参照してください。


## パネルの作成

パネルを作成するには：

* 左パネルから&#x200B;**[!UICONTROL パネル]**&#x200B;をキャンバスにドラッグ＆ドロップします。
* [空白のパネル](blank-panel.md)からパネルを選択します。
* Workspace の&#x200B;**[!UICONTROL 挿入]**&#x200B;メニューを使用してパネルを選択します。または、任意の[ショートカット](../build-workspace-project/fa-shortcut-keys.md)を使用してパネルを挿入することもできます。

  ![パネルの作成](assets/create-panel.png)

次のことができます。

* 任意のパネル&#x200B;**内**&#x200B;の ![AddCircle](/help/assets/icons/AddCircle.svg) を選択して、別のビジュアライゼーションを追加します。ビジュアライゼーションを選択できるポップアップが表示されます。

  ![使用可能なビジュアライゼーションを示すポップアップ](assets/blank-panel.png)

  | ..を選択 | ...を作成するには |
  |---|---|
  | ![テーブル](/help/assets/icons/Table.svg) | [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![折れ線グラフ](/help/assets/icons/GraphTrend.svg) | [折れ線グラフ](/help/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [棒グラフ](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [数値の概要](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![テキスト](/help/assets/icons/Text.svg) | [テキスト](/help/analysis-workspace/visualizations/text.md) |
  | ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [フォールアウト](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![ワークフロー](/help/assets/icons/GraphPathing.svg) | [フロー](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [積み重ね面グラフ](/help/analysis-workspace/visualizations/area.md) |
  | ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [コホートテーブル](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [ブレット](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [ドーナツ](/help/analysis-workspace/visualizations/donut.md) |
  | ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [変更の概要](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![ヒストグラム](/help/assets/icons/Histogram.svg) | [ヒストグラム](/help/analysis-workspace/visualizations/histogram.md) |
  | ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散布図](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![タイプ](/help/assets/icons/TwoDots.svg) | [ベン図](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [ツリーマップ](/help/analysis-workspace/visualizations/treemap.md) |

* ワークスペースの最後のパネル&#x200B;**外**&#x200B;の ![AddCircle](/help/assets/icons/AddCircle.svg) を選択し、別の[空白のパネル](blank-panel.md)を追加します。


## データビュー

各パネルは、[データビュー](/help/data-views/data-views.md)に関連付けられており、パネルの右上にあるドロップダウンメニューの&#x200B;**[!UICONTROL *データビュー&#x200B;*]**&#x200B;の![データ名](/help/assets/icons/Data.svg)で識別されます。

空の Workspace プロジェクトを作成する場合、最初のパネルのデフォルトのデータビューは、前回 Customer Journey Analytics で作業したデータビューです。

新しいパネルを作成する場合、デフォルトのデータビューは、Workspace プロジェクトで最後に作業したパネルのデータビューに基づいています。

>[!IMPORTANT]
>
>選択したデータビューによって、パネル内のビジュアライゼーションの作成に使用できるディメンション、指標、セグメントが決まります。
>
>
>パネルのデータビューを切り替えると、その新しいデータビューで一部のコンポーネントを使用できなくなる場合があります。この変更により、ビジュアライゼーションが正しくレンダリングされない可能性があります。次のような警告が表示される場合があります。
>
>* このパネルには、選択したデータビューで有効になっていないコンポーネントが含まれています。データビューを変更するか、データビューで必要なコンポーネントを有効にしてください。
>* ビジュアライゼーションをレンダリングできません。列と行で有効なコンポーネントが含まれていることを確認してください。
>

## カレンダー

パネルカレンダーは、パネル内のテーブルおよびビジュアライゼーションのレポート日付範囲を制御します。

>[!NOTE]
>
>![カレンダー](/help/assets/icons/Calendar.svg)日付範囲コンポーネントがビジュアライゼーションまたはパネル内で（例えばセグメントとして）使用されている場合、日付範囲コンポーネントがパネルカレンダーを上書きします。
>


![選択した日付範囲を示すカレンダーウィンドウ。](assets/panel-calendar.png)

1. 最初に開始日を選択し、次に終了日を選択して、日付範囲を選択します。
または、**[!UICONTROL プリセットを選択]**&#x200B;ドロップダウンメニューから「[!UICONTROL *プリセット*]」を選択できます。

1. オプションで、「**[!UICONTROL 詳細設定を表示]**」を選択して、次の操作を行います。

   * デフォルトの `12:00 AM`（`0:00`）と `11:59 PM`（`23:59`）以外の&#x200B;**[!UICONTROL 開始時間]**&#x200B;と&#x200B;**[!UICONTROL 終了時間]**&#x200B;を指定します。終了時間には常に 59 秒が含まれます。日付範囲が何日にもわたる場合、開始時間は日付範囲の最初の日、終了時間は日付範囲の最終日に適用されます。**[!UICONTROL 日時の値をリセット]**&#x200B;を使用して、開始時間と終了時間をデフォルトにリセットします。
   * **[!UICONTROL パネルカレンダーを基準とした日付範囲コンポーネントの作成]**&#x200B;無効にした場合、パネルで使用される日付範囲コンポーネントは現在の時刻を基準とします。有効にした場合、パネルで使用される日付範囲コンポーネントがパネルカレンダーに関連付けられます。
   * **[!UICONTROL 相対日付の使用]**&#x200B;有効にした場合、現在の日付と時間の進行状況に応じて、プリセットされた日付範囲（**[!UICONTROL 過去 7 日間]**&#x200B;など）が動的に更新されます。無効にすると、そのようなプリセットは適用されると更新されません。

     ![周期的な日付](assets/calendar-rolling.png)

     角括弧で囲まれたテキスト（例：**[!UICONTROL 固定開始 - 日周期]**）を選択して、パネルを拡張し、**[!UICONTROL 開始]**&#x200B;と&#x200B;**[!UICONTROL 終了]**&#x200B;の詳細を指定できます。

      1. 「**[!UICONTROL 開始日]**」、「**[!UICONTROL 終了日]**」または「**[!UICONTROL 固定日]**」を選択します。
      1. 「**[!UICONTROL 開始日]**」または「**[!UICONTROL 終了日]**」を選択すると、完全な式を作成できます。例：**[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**。式の個々の部分に適した値を選択します。
         * 現在の値を選択します。例：**[!UICONTROL current year]**。
         * 追加の計算の値を選択します。例：**[!UICONTROL plus]**。
         * 追加の計算を指定した場合は、値を指定します。例：`1`。
         * 追加の計算を指定した場合は、計算に使用する期間を選択します。例：**[!UICONTROL day]**。

     周期的な日付の計算の詳細を非表示にするには、「**[!UICONTROL 詳細を非表示]**」を選択します。

1. 「**[!UICONTROL 適用]**」を選択して、カレンダーを呼び出したパネルに日付範囲を適用します。
「**[!UICONTROL すべてのパネルに適用]**」を選択すると、Workspace プロジェクトのすべてのパネルに日付範囲が適用されます。


## ドロップゾーン {#dropzone}

パネルドロップゾーンを使用すると、パネル内のすべてのテーブルおよびビジュアライゼーションにセグメントおよびドロップダウンセグメントを適用できます。1 つのパネルに 1 つまたは複数のセグメントを適用できます。

### セグメント

パネルのドロップゾーンに左パネルからセグメントをドラッグ＆ドロップして、パネルのセグメント化を開始します。このプロセスを繰り返して、パネルにセグメントを追加します。セグメントは、パネルの上部に並んで表示されます。

![左パネルには、パネルのドロップゾーンにドラッグされた使用可能な指標とモバイル顧客指標が表示されます。](assets/segment-filter.png)

#### クイックセグメント

セグメント以外のコンポーネントをドロップゾーンに直接ドラッグしてクイックセグメントを作成することもできるので、[セグメントビルダー](/help/components/segments/seg-builder.md)への移行にかかる時間と手間を省くことができます。この方法で作成されたセグメントは、イベントレベルのセグメントとして自動的に定義されます。この定義は、セグメント名の横にある「![編集](/help/assets/icons/Edit.svg)」を選択すると、すばやく変更できます。


詳しくは、[クイックセグメント](/help/components/segments/seg-quick.md)を参照してください。

![公開されてドロップゾーンにドロップされるアドホックセグメント](assets/adhoc-segment-filter.png)

### ドロップダウンセグメント

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ドロップダウンセグメント](https://video.tv.adobe.com/v/327487?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


#### 静的ドロップダウンセグメント

静的ドロップダウンセグメントを使用すると、制御された方法でデータを操作できます。例えば、モバイルデバイスタイプにドロップダウンセグメントを追加すして、タブレット、携帯電話、デスクトップ別にパネルをセグメント化できます。

静的ドロップダウンセグメントを使用して、多くのプロジェクトを 1 つに統合することもできます。例えば、同じプロジェクトに異なる国セグメントが適用された複数のバージョンがある場合、すべてのバージョンを 1 つのプロジェクトに統合して「国」ドロップダウンセグメントを追加できます。

![マーケットチャネル「ダイレクト」セグメントがハイライト表示された静的ドロップダウンセグメント。](assets/dropdown-filter-intro.png)

##### 静的ドロップダウンセグメントの作成

* ディメンション項目を使用したドロップダウンセグメントの場合は、左パネルから 1 つのディメンションを選択し、⇧（*Shift*）キーを押したまま、パネルのドロップゾーンにドロップします。この操作により、そのディメンションに関連付けられたすべてのディメンション項目を選択できる、ドロップダウンセグメントが作成されます。

  または、ディメンションに関連付けられた特定のディメンション項目のみをドロップダウンセグメントに含める場合は、左パネルで、目的のディメンションの横にある右矢印アイコンを選択します。このアクションにより、使用可能なすべてのディメンション項目が表示されます。⇧ キーを押しながら![選択](/help/assets/icons/Select.svg)（*Shift* キーを押しながら&#x200B;*選択*）または ^ キーを押しながら![選択](/help/assets/icons/Select.svg)（*Ctrl* キーを押しながら&#x200B;*選択*）を使用して、このリストから複数のディメンション項目を選択し、⇧ キーを&#x200B;**押しながら**、それらをパネルのドロップゾーンにドロップします。

* 単一のコンポーネントタイプ（ディメンションのみ、セグメントのみ、指標のみなど）を使用するドロップダウンセグメントの場合は、⇧ キーを押しながら![選択](/help/assets/icons/Select.svg)、または ^ を押しながら![選択](/help/assets/icons/Select.svg)を使用して、左パネルから同じタイプの複数の項目を選択します。次に、⇧ キーを&#x200B;**押しながら**、項目をパネルのドロップゾーンにドロップします。

  選択したコンポーネントを使用して、1 つのドロップダウンセグメントが作成されます。

* コンポーネントタイプの組み合わせ（2 つの指標と 3 つのセグメントなど）を使用するドロップダウンセグメントの場合は、⇧ キーを押しながら![選択](/help/assets/icons/Select.svg)、または ^ キーを押しながら![選択](/help/assets/icons/Select.svg)を使用して、複数のコンポーネントを選択します。⇧ キーを&#x200B;**押しながら**、選択内容をパネルのドロップゾーンにドロップします。このコンテキストでは、すべてのコンポーネントタイプは個別のドロップダウンセグメントとして扱われます。例えば、指標とディメンション項目の両方を選択範囲に含める場合、2 つの異なるドロップダウンセグメントが作成されます。1 つのドロップダウンセグメントにはディメンション項目、もう 1 つには指標が含まれます。

ドロップダウンセグメントには、次のコンテキストメニューオプションがあります。

* **[!UICONTROL ドロップダウンを削除]**：パネルからドロップダウンセグメントを削除します。
* **[!UICONTROL ラベルを削除]**：ドロップダウンセグメントの上にあるテキストを削除します。ラベルを変更するには、ラベルの上にポインタを合わせて、「![ドロップダウンセグメントのラベルを編集](/help/assets/icons/Edit.svg)」を選択します。
* **[!UICONTROL ラベルを追加]**：プロジェクトにドロップダウンセグメントを追加すると、ラベルが自動的にコンポーネント名に設定されます。ラベルを削除した場合は、このオプションを使用して再度追加できます。
* **[!UICONTROL 選択を要求]**：パネルにセグメントが設定されている必要があります。

##### 静的ドロップダウンセグメントの使用

ユーザーは、次のいずれかの方法でドロップダウンセグメントメニューを使用して、パネルをセグメント化できます。

* ドロップダウンセグメントからセグメントを選択して、1 つのセグメントをパネルに適用します。

* ドロップダウンセグメントから複数のセグメントを選択して、パネルに複数のセグメントを適用します。パネルがセグメント化され、選択したセグメントのいずれかが含まれます。


#### 動的ドロップダウンセグメント

動的ドロップダウンセグメントを使用すると、パネルのレポート範囲内のデータと他のドロップダウンセグメントの値に基づいて、使用可能な値を決定できます。例えば、国ディメンションと市区町村ディメンションを使用して、2 つの動的なドロップダウンを作成できます。**[!UICONTROL 国]**&#x200B;ドロップダウンリストから国を選択すると、**[!UICONTROL 市区町村]**&#x200B;ドロップダウンリストが動的に調整され、その国内の市区町村のみが表示されます。

これと同じ概念がすべてのディメンションに適用され、パネルの日付範囲内に表示されるディメンション項目と選択したセグメントのみが表示されます。静的ドロップダウンセグメントで選択したディメンション項目は、動的ドロップダウンセグメントで使用できる値に影響します。ただし、その逆は成り立ちません。動的ドロップダウンセグメントで選択したディメンション項目は、静的ドロップダウンセグメントで使用可能な値には影響しません。

将来収集される特定のディメンション項目が予想される場合は、ディメンション項目を手動で選択できます。また、動的ドロップダウンセグメントをクリアして、値が含まれないようにすることもできます。それにより、他の動的ドロップダウンセグメントにより多くの値を含めることができます。「**[!UICONTROL すべてをリセット]**」を選択すると、そのパネルのすべてのドロップダウンセグメントから選択内容をクリアできます。

動的ドロップダウンセグメントを作成するには：

* ⇧ キーを&#x200B;**押しながら**、1 つのディメンションをパネルのドロップゾーンにドラッグ＆ドロップします。

動的ドロップダウンセグメントは、指標、セグメントまたは日付範囲では使用できないことに注意してください。

動的ドロップダウンセグメントには、静的ドロップダウンセグメントと同じコンテキストメニューオプションがあります。


## コンテキストメニュー

パネルの追加機能は、パネルのヘッダーのコンテキストメニュー（右クリック）から使用できます。

![パネルヘッダーの右クリックオプション。](assets/right-click-menu.png)

次のオプションがあります。

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL コピーしたパネルを挿入]** | コピーしたパネルをプロジェクト内の別の場所または別のプロジェクトにペーストできます。 |
| **[!UICONTROL コピーしたビジュアライゼーションを挿入]** | コピーしたビジュアライゼーションをプロジェクト内の別の場所または別のプロジェクトにペーストできます。 |
| **[!UICONTROL データビューをすべてのパネルに適用]** | このパネルのデータビューをプロジェクト内の他のすべてのパネルに適用します。 |
| **[!UICONTROL パネルをコピー]** | パネルをコピーして、プロジェクト内の別の場所または別のプロジェクトに挿入できます。 |
| **[!UICONTROL パネルを複製]** | 現在のパネルの完全な複製を作成して、修正できます。 |
| **[!UICONTROL すべてのパネルを折りたたむ]** | すべてのプロジェクトパネルを折りたたみます。 |
| **[!UICONTROL すべてのパネルを展開]** | すべてのプロジェクトパネルを展開します。 |
| **[!UICONTROL パネル内のすべてのビジュアライゼーションを折りたたむ]** | 現在のパネルのすべてのビジュアライゼーションを折りたたみます。 |
| **[!UICONTROL パネル内のすべてのビジュアライゼーションを展開]** | 現在のパネル内のすべてのビジュアライゼーションを展開します。 |
| **[!UICONTROL 説明を編集]** | パネルの説明テキストを追加（または編集）します。 |
| **[!UICONTROL パネルリンクを取得]** | プロジェクト内の特定のパネルに他のユーザーを誘導します。受信者は、リンクを選択した後、リンク先の正確なパネルにリダイレクトされる前にログインする必要があります。 |

## 設定

一部のパネル（[!UICONTROL アトリビューション]、[!UICONTROL 実験]、[!UICONTROL メディア分平均オーディエンス]など）には、ビジュアライゼーションの構築を支援する設定ダイアログがあります。パネルの上部にある「![編集](/help/assets/icons/Edit.svg)」を使用して、設定にアクセスして変更します。

![パネルの設定](/help/analysis-workspace/c-panels/assets/configure-panel.png)
