---
title: ガイド付き分析の概要
description: Customer Journey Analytics のデータ分析方法の 1 つで、製品チームが高品質のインサイトを迅速に得られるようにします。
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1849'
ht-degree: 97%

---

# ガイド付き分析の概要

ガイド付き分析を使用すると、マーケティング担当者、製品担当者からアナリストに至る様々なユーザーは Customer Journey Analytics のクロスチャネルデータに基づいて構築されたガイド付きワークフローを通じて、カスタマージャーニーに関する高品質のデータとインサイトをセルフサービスで提供できます。Analysis Workspace やモバイルスコアカードと同様に、ガイド付き分析では、[データビュー](/help/data-views/data-views.md)のデータを使用します。このビューは、[接続](../connections/overview.md)を通じて Adobe Experience Platform のデータを参照します。ガイド付き分析で作成した多くのレポートは、Analysis Workspace にシームレスに転送して、さらに調査できます。

次のガイド付き分析が使用可能です。

| アイコン | 分析 | 説明 |
| :----:|--- | --- |
| ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) | [アクティブな増加率](types/active-growth.md) | 新規、継続、再来訪または休眠状態のユーザーを特定します。 |
| ![ConversionTrens](/help/assets/icons/ConversionTrends.svg) | [コンバージョントレンド](types/conversion-trends.md) | コンバージョン率の推移を追跡します。 |
| ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) | [エンゲージメント](types/engagement.md) | 機能エンゲージメントの幅と深度を理解します。 |
| ![FirstUse](/help/assets/icons/FirstUse.svg) | [初回使用の影響](types/first-use-impact.md) | 機能の初回使用が主要指標に与える影響を測定します。 |
| ![ヒストグラム](/help/assets/icons/Histogram.svg) | [頻度](types/frequency.md) | 使用頻度別にエンゲージメントを測定します。 |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [ファネル](types/funnel.md) | ステップ間のコンバージョン率を比較します。 |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [純増加率](types/net-growth.md) | ユーザーは増加していますか、それとも減少していますか？ |
| ![Release](/help/assets/icons/Release.svg) | [リリースの影響](types/release-impact.md) | リリース前とリリース後の同じ期間にわたるパフォーマンスを比較します。 |
| ![Retention](/help/assets/icons/Retention.svg) | [リテンション](types/retention.md) | ユーザーの継続的な再来訪習慣を測定します。 |
| ![Timeline](/help/assets/icons/Timeline.svg) | [タイムライン](types/timeline.md) | セッションアクティビティのパターンを探索します。 |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [トレンド](types/trends.md) | ユーザーエンゲージメントの推移を測定します。 |



## アクセス

Customer Journey Analytics ホームページからガイド付き分析にアクセスできます。

1. ホームページで「**[!UICONTROL ガイド付き分析]**」を選択すると、[トレンド分析](types/trends.md)に直接移動します。

   ![ランディングページタイル](assets/landing-page-tile.png){style="border:1px solid gray"}

1. 「**[!UICONTROL 新規作成]**」を選択して様々な表示オプションを確認し、分析用に別の開始点を選択します。

   ![新しいモーダルの作成](assets/create-new-modal.png){style="border:1px solid gray"}

また、Analysis Workspace プロジェクト内からガイド付き分析にアクセスすることもできます。

1. ホームページから「**[!UICONTROL 空のプロジェクト]**」を選択して、空の Workspace プロジェクトを作成します。

   ![空のプロジェクトの作成](assets/blank-project.png){style="border:1px solid gray"}

1. 左パネルで「![ガイド付き分析](/help/assets/icons/GuidedAnalysis.svg)」、**[!UICONTROL ガイド付き分析]**&#x200B;を選択します。

   ![Workspace 左パネル](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. 新しい分析を Workspace キャンバスにドラッグし、「**[!UICONTROL 作成]**」を選択して目的の分析を生成します（例：**[!UICONTROL トレンドを作成]**）。また、既存の分析を「**[!UICONTROL 保存済み]**」セクションの下から Workspace キャンバスにドラッグすることもできます。

   ![パネルの作成](assets/create-guided-analysis-panel.gif)

## インターフェイス

ガイド付き分析のインターフェイスは、質問と回答の形式に従っています。クエリパネルで質問を作成し、書き込まれたインサイト、グラフ、テーブルを含む回答を取得します。分析とビジュアライゼーションの設定を使用して、次の質問をすることができます。

ガイド付き分析では、次の UI 要素を使用します。

| インターフェイスのプレビュー | UI 要素 | 説明 |
| --- | --- | --- |
| ![クエリパネル](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL クエリパネル]** | 分析を構成する目的のコンポーネント（イベント、プロパティ、セグメント）を選択して「*質問*」を設定します。次のオプションは、すべての分析で使用でき、追加の設定はビューごとに使用できます。 <ul><li>**表示**：新しい分析に切り替えるには、オプションから選択します。クエリの選択は、新しい分析で許可されている制限内に維持されます。</li><li>**イベント**：測定するイベントです。各分析では、設定可能なイベント数に対して異なる制限が適用されます。イベントには、**[!UICONTROL 開始イベントと復帰イベント]**、**[!UICONTROL 手順]**、**[!UICONTROL 主要指標]**&#x200B;というラベルが付いていることがあります。分析では、イベントは 1、2、...を使用して識別されます。<br/>新しいイベントを追加するには、![追加](/help/assets/icons/Add.svg) **[!UICONTROL イベントの追加]**&#x200B;を選択します。</li><li>**[!UICONTROL 要因]**：可能な場合、日付の開始日時や初回イベントなどの要因を指定できます。</li><li>**次としてカウント**：選択したイベントに適用するカウント方法。ドロップダウンメニューからを選択します。</li><li>**セグメント**：測定するセグメント。各分析では、設定可能なセグメント数に対して異なる制限が適用されます。分析では、セグメントは A、B、...を使用して識別されます。<br/>新しいセグメントを追加するには、![追加](/help/assets/icons/Add.svg) **[!UICONTROL セグメントを追加]**&#x200B;を選択します。</li><li>**[!UICONTROL 分類]**：分析に適用する分類（使用可能な場合）。</li></ul>一部の設定では、追加の設定を使用できます。<ul><li>**フィルター**：![フィルター](assets/filter.png)を使用して、特定のディメンションごとにイベントやセグメントを絞り込みます。ディメンションを選択すると、標準フィルター条件（**[!UICONTROL 次に等しい]**、**[!UICONTROL 次を含む]**&#x200B;または&#x200B;**[!UICONTROL 次で終わる]**）と上位 1000 個のディメンション値の両方を使用できます。<br/>「![フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターを追加します。<br/>「![削除](/help/assets/icons/Remove.svg)」を選択して、フィルターを削除します。</li><li>**その他のアクション**：![その他](/help/assets/icons/More.svg)を使用して、次のようなアクションを選択します<ul><li>![名前を変更](/help/assets/icons/Rename.svg) **[!UICONTROL 名前を変更]**：イベントまたはセグメントの名前を変更します。</li><li>![複製](/help/assets/icons/Duplicate.svg) **[!UICONTROL 複製]**：イベントまたはセグメントを複製します。</li><li>![削除](/help/assets/icons/Delete.svg) **[!UICONTROL 削除]**：イベント、セグメントまたは分類を削除します。</li><li>![ セグメントの編集 ](/help/assets/icons/Edit.svg)**[!UICONTROL セグメントの編集]**: [ セグメントビルダー ](/help/components/filters/filter-builder.md) でセグメントを編集します。</li><li>![ スター ](/help/assets/icons/Star.svg)**[!UICONTROL お気に入りに追加]**: [ セグメントマネージャー ](/help/components/filters/manage-filters.md) のお気に入りセグメントリストにセグメントを追加します。</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL 名前を付けて保存]**：セグメントを新しいコンポーネントとして保存します。**[!UICONTROL セグメントをコンポーネントに保存]**&#x200B;ダイアログで、セグメント名と説明を指定できます。「![StarOutline](/help/assets/icons/StarOutline.svg)」を選択すると、新しいセグメントをお気に入りに登録できます。「**[!UICONTROL 保存]**」を選択して、セグメントを新しいセグメントとして保存します。</li><li>![リンク](/help/assets/icons/Link.svg) **[!UICONTROL 開始および再来訪イベントをリンク]**：[リテンション](types/retention.md)分析で開始イベントと再来訪イベントをリンクします。</li><li>![リンク解除](/help/assets/icons/Unlink.svg) **[!UICONTROL 開始イベントと再来訪イベントのリンク解除]**：[リテンション](types/retention.md)分析で開始イベントと再来訪イベントのリンクを解除します。</li></ul></li></ul> |
| ![グラフ](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL グラフ]** | クエリパネルと設定からの入力に基づいて返されるデータのビジュアライゼーション。どのビジュアライゼーションが表示されるかは、グラフ上のビューと設定によって異なります。グラフには次も含まれます。 <ul><li>**ツールチップ**：グラフのデータポイントの上にマウスポインターを置くと、詳細情報を含むツールチップが表示されます。</li><li>**凡例**：グラフの凡例系列の上にポインタを合わせると、定義がある場合はその系列の定義を表示したり、その系列に焦点を当てたり、他の系列を一時的に非表示にしたりできます。凡例のシリーズを選択すると、シリーズが非表示になります。</li><li>**注釈**：適用可能な[注釈](../components/annotations/overview.md)は、ビジュアライゼーションと凡例の間に表示されます。注釈の設定された色で![注釈アイコン](assets/annotation.png) アイコンとして表示されます。時間の経過に伴うデータを表示する分析では、設定された日付または日付範囲の下に![注釈アイコン](assets/annotation.png)が配置されます。時間の経過に伴うデータを表示しない分析では、グラフの右下隅に![注釈アイコン](assets/annotation.png)が表示されます。</li><li>**アクションを選択**：任意のデータポイントを選択して、使用可能な次のアクションを表示します。オプションには「**セグメントを保存**」が含まれます。</li></ul> |
| ![テーブル](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL テーブル]** | クエリパネルからの入力と設定に基づいて返されるデータのテーブル表示域。イベント（1、2、...）およびセグメント識別子（A、B、...）を参照として使用したテーブルの行。テーブルの列は、グラフ上の分析によって異なります。この表には、各行に対して次の内容も含まれます。 <ul><li>**アクションを選択**：![非表示アイコンを表示](assets/hide-in-chart.png)を切り替えて、行のグラフシリーズを表示にしたり非表示にしたりします。追加のアクションについては、「![その他](/help/assets/icons/More.svg)」を選択します。オプションには「**セグメントを保存**」が含まれます。</li></ul> |
| ![ビジュアライゼーション設定](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL ビジュアライゼーション設定]** | グラフ上にあるオプション。次の質問をしたり、グラフとテーブルがデータを返す方法をカスタマイズしたりできます。次のオプションは、すべての分析で使用でき、追加の設定は分析ごとに使用できます。 <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **グラフ設定**：グラフやテーブルの表示を微調整します。使用できるオプションは、選択した分析によって異なります。</li><li>![レイヤー](/help/assets/icons/Layer.svg) **オーバーレイ設定**：オーバーレイを追加します。使用できるオプションは、選択した分析によって異なります。</li><li>![バケット](/help/assets/icons/Bucket.svg) **[!UICONTROL バケット設定]**：自動バケットするか、またはカスタムバケット設定をデータに適用します。使用できるオプションは、選択した分析によって異なります。<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL 比較設定]**：特定の日付範囲とデータを比較します。使用できるオプションは、選択した分析によって異なります。</li><li>![足跡](/help/assets/icons/Footsteps.svg) **[!UICONTROL 表示設定]**：データの表示方法を選択します。使用できるオプションは、選択した分析によって異なります。<li>![カレンダー](/help/assets/icons/Calendar.svg) **日付範囲**：カレンダーピッカーを使用すると、分析の日付範囲を決定できます。日別、週別、月別など、トレンド分析の間隔を選択することもできます。</li><li>![LightBulb](/help/assets/icons/LightBulb.svg) **インサイト**：表示する分析に応じたコンテキストインサイト。これらのインサイトは、現在の分析に関する考察を提供します。複数のインサイトがある場合は、右側の矢印を使用して表示できます。右上の電球アイコンを使用して、このボックスの表示／非表示を切り替えることができます。</li></ul> |
| ![メニューアイコン](assets/menu.png){style="border:1px solid gray"} | ガイド付き分析プロジェクトで使用可能な&#x200B;**[!UICONTROL メニュー]**<br/> | ガイド付き分析プロジェクトの右上にあるコマンドで、分析の包括的なアクションを提供します。<ul><li>![データアイコン](/help/assets/icons/Data.svg) ***データビュー名***：分析で使用するデータビューを変更します。データビューを変更すると、クエリパネルの使用可能なコンポーネントも変更されます。</li><li>![リンクアイコン](/help/assets/icons/Link.svg) **リンクをコピー**：分析へのリンクをクリップボードにコピーします。共有する前に保存するよう求めるメッセージが表示されます。</li><li>**共有**：共有モーダルを開きます。個々のユーザーまたはグループに共有するためのその他のオプションがあります。他のユーザーと分析を共有したり、任意のユーザーと共有するためのリンクを生成したりできます。</li><li>**保存**：分析を保存します。新しい分析を保存する場合、名前と説明をリクエストする&#x200B;**[!UICONTROL 分析を保存]**&#x200B;ダイアログが表示されます。保存すると、**[!UICONTROL 分析保存済み]**&#x200B;ダイアログで分析を共有できます。</li><li>![Workspace に追加アイコン](/help/assets/icons/MultipleAdd.svg) **[!UICONTROL Workspace に追加]**：この分析を追加できる使用可能な Workspace プロジェクトを表示します。Workspace プロジェクトを選択すると、そのWorkspace プロジェクトが新しいタブで開き、プロジェクトの下部に分析が追加されます。</li></ul>![その他アイコン](/help/assets/icons/More.svg) を選択すると、次のようなその他のアクションが表示されます。<ul><li>**[!UICONTROL 別名で保存]**：現在の分析とは別に分析を保存し、コピーを作成します。新しい名前と説明をリクエストするダイアログが表示されます。</li><li>**[!UICONTROL Workspace にエクスポート]**：Analysis Workspace で現在のガイド付き分析クエリを再作成します。Workspace プロジェクトは新しいタブで作成されるので、ガイド付き分析での作業が中断されることはありません。分析のコピーであり、開いた後は元の分析と同期しません。このコマンドは、アナリストチームに引き渡す場合や、分析で可能な範囲よりも詳細なデータを取得する場合に使用します。</li><li>**[!UICONTROL クリップボードにグラフをコピー]**：グラフのグラフィックをクリップボードにコピーして、他のアプリケーションに貼り付けます。クエリパネルとテーブルは、グラフィックに含まれていません。</li><li>**[!UICONTROL PNG のダウンロード]**：グラフのグラフィックを `.png` としてダウンロードします。クエリパネルとテーブルは、グラフィックに含まれていません。</li><li>**[!UICONTROL CSV のダウンロード]**：テーブルデータを `.csv` としてダウンロードします。クエリパネルとグラフはファイルに含まれていません。</li></ul> |
| ![メニュービジュアライゼーション](assets/menu-visualization.png){style="border:1px solid gray"} | Analysis Workspace のガイド付き分析ビジュアライゼーションで使用可能な&#x200B;**メニュー**<br/>。 | Analysis Workspace のガイド付き分析ビジュアライゼーションのコマンド。<ul><li>![GraphScatter](/help/assets/icons/GraphScatter.svg) **[!UICONTROL グラフ]**：分析のグラフのみを表示します。</li><li>![テーブル](/help/assets/icons/Table.svg) **[!UICONTROL テーブル]**：分析のテーブルのみを表示します。</li><li>![TableAndChart](/help/assets/icons/TableAndChart.svg) **[!UICONTROL すべて]**：分析のグラフとテーブルを表示します。</li><li>![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**：分析の設定を編集します。</li><li>![カレンダー](/help/assets/icons/Calendar.svg) **[!UICONTROL *日付範囲&#x200B;*]**：分析の日付範囲を設定します。</li></ul> |


## プロビジョニング

ガイド付き分析は、次の方法で Customer Journey Analytics パッケージに含まれています。

| パッケージ | 利用可能な分析 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics アドオン] | アクティブな増加率、コンバージョンのトレンド、頻度、ファネル、純増加率、リテンション、トレンド |
| [!UICONTROL Customer Journey Analytics 基盤] | トレンド |
| [!UICONTROL Customer Journey Analytics 選択] | 基盤となるビュー + アクティブな増加率、コンバージョンのトレンド、頻度、ファネル、純増加率、リテンション |
| [!UICONTROL Customer Journey Analytics Prime] | ビュー + エンゲージメント、初回使用の影響、リリースの影響、タイムラインを選択 |
| [!UICONTROL Customer Journey Analytics Ultimate] | Prime ビュー数 |

{style="table-layout:auto"}

製品プロファイル管理者は、Adobe Admin Console でガイド付き分析へのアクセスを追加または削除できます。

1. [Adobe Admin Console](https://adminconsole.adobe.com) にログインします。
1. 製品リストから **[!UICONTROL Customer Journey Analytics]** を選択します。
1. 編集する権限に必要な製品プロファイルを選択します。
1. 「**[!UICONTROL 権限]**」タブをクリックし、[!UICONTROL レポートツール]の下の「**[!UICONTROL 編集]**」をクリックします。
1. [!UICONTROL 使用可能な権限項目]のリストで&#x200B;**[!UICONTROL ガイド付き分析アクセス]**&#x200B;の横の ![AddCircle](/help/assets/icons/AddCircle.svg) を選択すると、[!UICONTROL 含まれる権限項目]のリストに追加されます。
1. 「**[!UICONTROL 保存]**」を選択します。

詳しくは、[ユーザーレベルアクセス](/help/technotes/access-control.md#user-level-access)を参照してください。

>[!TIP]
>
>管理者によっては、Customer Journey Analytics の新規ユーザーに対してガイド付き分析を有効にし、Analysis Workspace を無効にすることを好む場合があります。これらのユーザーが製品と組織のデータに慣れてきたら、Analysis Workspace へのアクセスを有効にできます。
