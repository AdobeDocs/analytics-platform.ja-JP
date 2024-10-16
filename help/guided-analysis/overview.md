---
title: ガイド付き分析の概要
description: Customer Journey Analytics内のデータを分析する手法。製品部門は、高品質のインサイトを迅速に得ることができます。
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: ce04e69d2c933f893eeeff04abb0f56fb4000e6f
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 72%

---

# ガイド付き分析の概要

ガイド付き分析を使用すると、マーケティングから製品、アナリストに至るまで、Customer Journey Analyticsのクロスチャネルデータに基づいて構築されたガイド付きワークフローを通じて、カスタマージャーニーに関する高品質のデータとインサイトをセルフサービスで提供できます。 Analysis Workspace やモバイルスコアカードと同様に、ガイド付き分析では、[データビュー](/help/data-views/data-views.md)のデータを使用します。このビューは、[接続](../connections/overview.md)を通じて Adobe Experience Platform のデータを参照するものです。ガイド付き分析で作成した多くのレポートは、Analysis Workspace にシームレスに転送して、さらに調査することができます。

次のガイド付き分析を利用できます。

| アイコン | 分析 | 説明 |
| :----:|--- | --- |
| ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) | [ 積極的成長 ](types/active-growth.md) | 新規、継続、再来訪または休眠状態のユーザーを特定します。 |
| ![ConversionTrens](/help/assets/icons/ConversionTrends.svg) | [コンバージョントレンド](types/conversion-trends.md) | コンバージョン率の推移を追跡します。 |
| ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) | [エンゲージメント](types/engagement.md) | 機能エンゲージメントの幅と深度を理解します。 |
| ![FirstUse](/help/assets/icons/FirstUse.svg) | [ 初回使用時の影響 ](types/first-use-impact.md) | 機能の初回使用が主要指標に与える影響を測定します。 |
| ![ヒストグラム](/help/assets/icons/Histogram.svg) | [頻度](types/frequency.md) | 使用頻度別にエンゲージメントを測定します。 |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [ファネル](types/funnel.md) | ステップ間のコンバージョン率を比較します。 |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [純増加率](types/net-growth.md) | ユーザーは増加していますか、それとも減少していますか？ |
| ![リリース](/help/assets/icons/Release.svg) | [ リリースの影響 ](types/release-impact.md) | リリース前とリリース後の同じ期間にわたるパフォーマンスを比較します。 |
| ![リテンション](/help/assets/icons/Retention.svg) | [リテンション](types/retention.md) | ユーザーの継続的な再来訪習慣を測定します。 |
| ![タイムライン](/help/assets/icons/Timeline.svg) | [タイムライン](types/timeline.md) | セッションアクティビティのパターンを探索します。 |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [トレンド](types/trends.md) | ユーザーエンゲージメントの推移を測定します。 |

{style="table-layout:auto"}

## アクセス

Customer Journey Analyticsホームページからガイド付き分析にアクセスできます。

1. ホームページから **[!UICONTROL ガイド付き分析]** を選択すると、[ 使用状況のトレンド表示 ](types/trends.md) に直接移動します。

   ![ランディングページタイル](assets/landing-page-tile.png){style="border:1px solid gray"}

1. 「**[!UICONTROL 新規作成]**」を選択して様々な表示オプションを表示し、分析の別の開始点を選択します。

   ![新しいモーダルの作成](assets/create-new-modal.png){style="border:1px solid gray"}

また、Analysis Workspace プロジェクト内からガイド付き分析にアクセスすることもできます。

1. ホームページから **[!UICONTROL 空のプロジェクト]** を選択して、空のWorkspace プロジェクトを作成します。

   ![ 空のプロジェクトを作成 ](assets/blank-project.png){style="border:1px solid gray"}

1. 左パネルで「![ ガイド付き分析 ](/help/assets/icons/GuidedAnalysis.svg)**[!UICONTROL ガイド付き分析]**」を選択します。

   ![Workspace左レール ](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. 新しい分析をWorkspace キャンバスにドラッグし、「**[!UICONTROL 作成]**」を選択して目的の分析を生成します（例：**[!UICONTROL トレンドを作成]**）。 また、既存の分析を「保存済み **[!UICONTROL セクションの下からWorkspace キャンバスにドラッグす]** こともできます。

   ![ パネルを作成 ](assets/create-guided-analysis-panel.gif)

## インターフェイス

ガイド付き分析のインターフェイスは、質問と回答の形式に従っています。クエリパネルで質問を作成し、書き込まれたインサイト、グラフ、テーブルを含む回答を取得します。表示タイプとビジュアライゼーションの設定を使用して、次の質問をすることができます。

ガイド付き分析では、次の UI 要素を使用します。

| インターフェイスのプレビュー | UI 要素 | 説明 |
| --- | --- | --- |
| ![クエリパネル](assets/query-rail.png){style="border:1px solid gray"} | クエリパネル | 分析を構成する目的のコンポーネント（イベント、プロパティ、セグメント）を選択して「質問」を設定します。次のオプションは、すべての表示タイプで使用でき、追加の設定はビューごとに使用できます。 <ul><li>**分析セレクター**：新しい分析タイプに切り替えることができるドロップダウン。クエリの選択は、新しい分析タイプで許可されている制限内に維持されます。</li><li>**イベント**：測定するイベントです。各ビュータイプでは、設定可能なイベント数に対して異なる制限が適用されます。</li><li>**フィルター**:「イベントまたはセグメント」セクションの ![ フィルター ](assets/filter.png) アイコンを使用して、特定のディメンションごとに絞り込みます。 ディメンションを選択した場合は、標準フィルター条件（[!UICONTROL  次に等しい ]、[!UICONTROL  次を含む ]、[!UICONTROL  次で終わる ] など）および上位 1000 個のディメンション値の両方を使用できます。</li><li>**次としてカウント**：選択したイベントに適用するカウント方法。</li><li>**セグメント**：測定するセグメント。各ビュータイプでは、設定可能なセグメントの数に対して異なる制限が適用されます。</li></ul> |
| ![グラフ](assets/chart.png){style="border:1px solid gray"} | グラフ | クエリパネルと設定からの入力に基づいて返されるデータのビジュアライゼーション。どのビジュアライゼーションが表示されるかは、グラフ上のビューと設定によって異なります。グラフには次も含まれます。 <ul><li>**ツールチップ**：グラフのデータポイントの上にマウスポインターを置くと、詳細情報を含むツールチップが表示されます。</li><li>**凡例**：グラフの凡例系列の上にポインタを合わせると、定義がある場合はその系列の定義を表示したり、その系列に焦点を当てたり、他の系列を一時的に非表示にしたりできます。凡例内の系列をクリックして非表示にします。</li><li>**注釈**：適用可能な[注釈](../components/annotations/overview.md)は、ビジュアライゼーションと凡例の間に表示されます。注釈の設定された色で![注釈アイコン](assets/annotation.png) アイコンとして表示されます。時間の経過に伴うデータを表示するビュータイプでは、設定された日付または日付範囲の下に![注釈アイコン](assets/annotation.png) アイコンが配置されます。時間の経過に伴うデータを表示しないビュータイプでは、グラフの右下隅に![注釈アイコン](assets/annotation.png) アイコンが表示されます。</li><li>**アクションを選択**：任意のデータポイントを選択して、使用可能な次のアクションを公開します。 オプションには「**セグメントを保存**」が含まれます。</li></ul> |
| ![テーブル](assets/table.png){style="border:1px solid gray"} | テーブル | クエリパネルからの入力と設定に基づいて返されるデータのテーブル表示域。テーブルの列は、グラフ上の表示タイプによって異なります。このテーブルには、次の項目も含まれます。 <ul><li>**アクションの選択**：各行の ![ 非表示アイコンを表示 ](assets/hide-in-chart.png) アイコンを切り替えて、グラフシリーズを表示または非表示にします。 **[!UICONTROL その他]** メニューを選択すると、追加のアクションを使用できます。 オプションには「**セグメントを保存**」が含まれます。</li></ul> |
| ![ビジュアライゼーション設定](assets/visualization-settings.png){style="border:1px solid gray"} | ビジュアライゼーション設定 | グラフ上にあるオプション。次の質問をしたり、グラフとテーブルがデータを返す方法をカスタマイズしたりできます。次のオプションは、すべての表示タイプで使用でき、追加の設定はビューごとに使用できます。 <ul><li>**グラフ設定**：グラフやテーブルの表示を微調整します。使用できるオプションは、選択した表示によって異なります。</li><li>**日付範囲**：分析の日付範囲を決定できるカレンダーピッカー。日別、週別、月別など、トレンド表示の間隔を選択することもできます。</li><li>**インサイト**：表示する分析に応じたコンテキストインサイト。これらのインサイトは、現在の分析に関する考察を提供します。複数のインサイトがある場合は、右側の矢印を使用して表示できます。右上の電球アイコンを使用して、このボックスの表示／非表示を切り替えることができます。</li></ul> |
| ![メニュー](assets/menu.png){style="border:1px solid gray"} | メニュー | ガイド付き分析の右上にあるコマンドで、分析のための包括的なアクションを提供します。<ul><li>**データビューセレクター**：分析で使用するデータビューを変更します。データビューを変更すると、クエリパネルの使用可能なコンポーネントも変更されます。</li><li>**リンクをコピー**：分析へのリンクをクリップボードにコピーします。共有する前に保存するよう求めるメッセージが表示されます。</li><li>**共有**：共有モーダルを開きます。個々のユーザーまたはグループに共有するためのその他のオプションがあります。他のユーザーと分析を共有したり、任意のユーザーと共有するためのリンクを生成したりできます。</li><li>**保存**：分析を保存します。新しい分析を保存する場合、名前と説明をリクエストするモーダルウィンドウが表示されます。</li><li>**別名で保存**：現在の分析とは別に分析を保存し、コピーを作成します。新しい名前と説明をリクエストするモーダルウィンドウが表示されます。</li><li>**Workspaceに書き出し**：現在のガイド付き分析クエリをAnalysis Workspaceに再作成します。 Workspace プロジェクトは新しいタブで作成されるので、ガイド付き分析での作業が中断されることはありません。分析のコピーであり、開いた後は元のガイド付き分析と同期しません。このコマンドは、アナリストチームに引き渡す場合や、ガイド付き分析で可能な範囲よりも詳細なデータを取得する場合に使用します。</li><li>**クリップボードにコピー**：グラフのグラフィックをクリップボードにコピーして、他のアプリケーションに貼り付けます。クエリパネルとテーブルは、グラフィックに含まれていません。</li><li>**PNG のダウンロード**：グラフのグラフィックを `.png` としてダウンロードします。クエリパネルとテーブルは、グラフィックに含まれていません。</li><li>**CSV のダウンロード**：テーブルデータを `.csv` としてダウンロードします。クエリパネルとグラフはファイルに含まれていません。</li></ul> |

{style="table-layout:auto"}

## プロビジョニング

ガイド付き分析は、次の方法でCustomer Journey Analyticsパッケージに含まれています。

| パッケージ | 利用可能な分析 |
| --- | --- |
| [!UICONTROL Customer Journey Analyticsアドオン ] | アクティブな増加、コンバージョンのトレンド、頻度、ファネル、純増加、定着、トレンド |
| [!UICONTROL Customer Journey Analytics基盤 ] | 傾向 |
| [!UICONTROL Customer Journey Analyticsを選択 ] | 基盤となるビュー+ アクティブな成長、コンバージョンのトレンド、頻度、ファネル、純成長、定着 |
| [!UICONTROL Customer Journey Analyticsプライム ] | ビュー+ エンゲージメント、初回使用の影響、リリースの影響、タイムラインを選択 |
| [!UICONTROL Ultimate Customer Journey Analytics] | Prime ビュー数 |

{style="table-layout:auto"}

製品プロファイル管理者は、Adobe Admin Console でガイド付き分析へのアクセスを追加または削除できます。

1. [Adobe Admin Console](https://adminconsole.adobe.com) にログインします。
1. 製品リストから **[!UICONTROL Customer Journey Analytics]** を選択します。
1. 編集する権限に必要な製品プロファイルを選択します。
1. 「**[!UICONTROL 権限]**」タブを選択し、「**[!UICONTROL レポートツール [!UICONTROL  の下にある]** 編集 ] をクリックします。
1. ![ 使用可能な権限項目 ](/help/assets/icons/AddCircle.svg) のリストの **[!UICONTROL ガイド付き分析アクセス]** の横にある [!UICONTROL AddCircle] を選択すると、[!UICONTROL  含まれる権限項目 ] のリストに追加されます。
1. 「**[!UICONTROL 保存]**」を選択します。

詳しくは、[ ユーザーレベルアクセス ](/help/technotes/access-control.md#user-level-access) を参照してください。

>[!TIP]
>
>管理者によっては、Customer Journey Analytics の新規ユーザーに対してガイド付き分析を有効にし、Analysis Workspace を無効ににすることを好む場合があります。これらのユーザーが製品と組織のデータに慣れてきたら、Analysis Workspace へのアクセスを有効にできます。
