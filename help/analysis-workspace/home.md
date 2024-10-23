---
keywords: Analysis Workspace
title: Analysis Workspace の概要
description: Analysis Workspace 機能の概要
feature: Workspace Basics
exl-id: 9075518e-54fe-49a6-9601-aa9468187b8f
solution: Customer Journey Analytics
role: User
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 13%

---

# Analysis Workspace の概要 {#analysis-workspace-overview}

Analysis Workspaceを使用すると、分析をすばやく構築してインサイトを収集し、それらのインサイトを他のユーザーと共有できます。 ドラッグ&amp;ドロップブラウザーインターフェイスを使用して、分析を作成し、ビジュアライゼーションを追加してデータに活気を与え、データセットをキュレーションし、[ プロジェクト ](/help/analysis-workspace/build-workspace-project/freeform-overview.md) を任意のユーザーと共有し、スケジュールすることができます。


+++ Analytics Workspaceの可能性を示すビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/26266/?quality=12)

{{videoaa}}

+++

## インターフェイス

次の画像と付属の表に、Analysis Workspace ユーザーインターフェイスの主な要素を示します。

![ 左端のパネルと左側のパネル、キャンバスおよびデータビューのドロップダウンメニューがハイライト表示されたAnalysis Workspace ウィンドウ。](assets/analysis-workspace-overview.png)

| 場所 | 名前と機能 |
|:---------:|----------|
| ?? | プロジェクトの名前、機能にアクセスするためのメニュー構造、プロジェクトリストに戻るためのボタン ![ChevronLeft](/help/assets/icons/ChevronLeft.svg)、および [Workspace プロジェクトを共有 ]**するためのボタン**[!UICONTROL  共有 ](/help/analysis-workspace/curate-share/share-projects.md) が含まれています。 <br/> プロジェクトの名前を変更するには、いつでもプロジェクトの名前（例：新規プロジェクト）を選択します。 <br/> 「![StarOutline](/help/assets/icons/StarOutline.svg)」を選択して、プロジェクトをお気に入りのプロジェクト ![Star](/help/assets/icons/Star.svg) としてマークします。 |
| ?? | **ボタンパネル：** Analysis Workspaceの主要な [ 機能 ](#features) にアクセスするためのボタンが含まれています。<ul><li>![Web ページ ](/help/assets/icons/WebPage.svg) [[!UICONTROL  パネル ]](/help/analysis-workspace/c-panels/panels.md)</li><li>![ ガイド付き分析 ](/help/assets/icons/GuidedAnalysis.svg)[[!UICONTROL  ガイド付き分析 ]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg)[[!UICONTROL  ビジュアライゼーション ]](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Curate](/help/assets/icons/Curate.svg)[[!UICONTROL Components]](/help/components/overview.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg)[[!UICONTROL  目次 ]](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![ ブックマーク ](/help/assets/icons/Bookmark.svg)[[!UICONTROL  データディクショナリ ]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| ?? | **左パネル：** この領域には、個々のパネル、ビジュアライゼーション、コンポーネントまたはリストが含まれます。 コンテンツは、ボタンパネルで選択したボタンによって異なります。 |
| ?? | **キャンバス：** 左側のパネルからコンテンツをドラッグしてプロジェクトを構築するメイン領域です。 パネルの追加、パネルへのビジュアライゼーションの追加、ビジュアライゼーションへのコンポーネントの追加を行うと、プロジェクトは動的に更新されます。 複数のパネルを作成でき、各パネル内で複数のビジュアライゼーションを作成できます。<br/> 各パネルは、選択したデータビューに基づいています。 選択したデータビューによって、指標やディメンションなど、使用可能なコンポーネントが決まります。 詳しくは、[ パネル – データビュー ](/help/analysis-workspace/c-panels/panels.md#data-view) を参照してください。 |

## 機能

Analysis Workspaceの主な機能は、ボタンパネルから使用できます。

| アイコン | 機能 | 説明 |
|:---:|---|---|
| ![Web ページ ](/help/assets/icons/WebPage.svg) | **[!UICONTROL パネル]** | [パネル](/help/analysis-workspace/c-panels/panels.md) を使用すると、プロジェクト内の分析を整理し、多数のテーブルやビジュアライゼーションを含めることができます。Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。 |
| ![ ガイド付き分析 ](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL ガイド付き分析]** | [ ガイド付き分析 ](../guided-analysis/overview.md) では、ガイド付きワークフローを通じて、カスタマージャーニーに関する高品質のデータとインサイトをセルフサービスで提供できます。 分析を作成してWorkspace プロジェクトに含めたり、以前に保存した既存の分析を含めたりできます。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL ビジュアライゼーション]** | 棒グラフや折れ線グラフなどの [ ビジュアライゼーション ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) を使用して、データに命を吹き込むことができます。 左端のパネルで、中央の **[!UICONTROL ビジュアライゼーション]** アイコンを選択し、使用可能なビジュアライゼーションの完全なリストを表示します。 |
| ![ キュレーション ](/help/assets/icons/Curate.svg) | **[!UICONTROL コンポーネント]** | [ コンポーネント ](/help/components/overview.md) 次の要素があります。<ul><li>![Dimension](/help/assets/icons/Dimensions.svg) [Dimension](/help/components/dimensions/overview.md)</li><li>![ イベント ](/help/assets/icons/Event.svg)[ 指標 ](/help/components/apply-create-metrics.md)</li><li>![ セグメント化 ](/help/assets/icons/Segmentation.svg)[ フィルター ](/help/components/filters/filters-overview.md)</li><li>![ カレンダー ](/help/assets/icons/Calendar.svg)[ 日付範囲 ](/help/components/date-ranges/overview.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL 目次]** | 目次は、プロジェクトに含まれているすべてのパネルとビジュアライゼーションを折りたたみ可能なリストに整理していて、特定のパネルやビジュアライゼーションにすばやくアクセスできます。 |
| ![ ブックマーク ](/help/assets/icons/Bookmark.svg) | **データディクショナリ** | [ データ要素 ](/help/components/data-dictionary/data-dictionary-overview.md) は、ユーザーと管理者の両方が Analytics 環境のコンポーネントを追跡し、よりよく理解するのに役立ちます。 |


## メニュー

Analysis Workspaceのほとんどの機能は、ドラッグ&amp;ドロップのほか、パネル、ビジュアライゼーションおよびコンポーネント内のコンテキストメニューから利用できます。

Workspace メニューとショートカットまたはホットキーを使用して、機能を利用することもできます。 ショートカットキーは、ブラウザーを実行しているオペレーティングシステムによって異なります。 概要については、以下の表を参照してください。

キーボードでは、次の記号が使用される場合があります。

- **[!UICONTROL *shift *]**の場合は**⇧**。
- **[!UICONTROL *cmd *]**（コマンド）の場合は**⌘**。
- **[!UICONTROL *ctrl *]**（コントロール）の場合は**⌃**。
- **[!UICONTROL *⌥opt *]**の****（オプション）。
- **[!UICONTROL *alt *]**の場合は**⎇**（代替）。

使用可能なメニューの概要については、次の表を参照してください。

| **[!UICONTROL プロジェクト]** | ショートカットMac | ショートカットウィンドウ | 説明 |
|---|---|---|---|
| **[!UICONTROL プロジェクトの作成]** | **[!UICONTROL *shift+cmd+p *]** | **[!UICONTROL *shift+ctrl+p *]** | 新しいプロジェクトを作成します。 |
| **[!UICONTROL モバイルスコアカードの作成]** | | | [ 新しいモバイルスコアカードの作成 ](/help/mobile-app/create-scorecard.md)。 |
| **[!UICONTROL 開く…]** | **[!UICONTROL *cmd+o *]** | **[!UICONTROL *ctrl+o *]** | [ 既存のプロジェクトを開く ](/help/analysis-workspace/build-workspace-project/save-projects.md#open-another-project)。 |
| **[!UICONTROL 以前のバージョンを開く…]** | **[!UICONTROL *opt+cmd+o *]** | **[!UICONTROL *alt+ctrl+o *]** | [ 以前のバージョンのプロジェクトを開きます ](/help/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version)。 |
| **[!UICONTROL 保存]** | **[!UICONTROL *cmd+s *]** | **[!UICONTROL *ctrl+s *]** | [ プロジェクトを保存 ](/help/analysis-workspace/build-workspace-project/save-projects.md#save-projects) します。 |
| **[!UICONTROL メモと共に保存…]** | **[!UICONTROL *opt+cmd+s *]** | **[!UICONTROL *alt+ctrl+s *]** | [ 保存するプロジェクトバージョンにメモを追加します ](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 別名で保存…]** | **[!UICONTROL *shift+cmd+s *]** | **[!UICONTROL *shift+ctrl+s *]** | [ 別の名前と詳細を使用してプロジェクトを保存します ](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL プロジェクトを更新]** | **[!UICONTROL *opt+r *]** | **[!UICONTROL *alt+r *]** | プロジェクトを更新します。 |
| **[!UICONTROL CSV をダウンロード]** | **[!UICONTROL *shift+cmd+v *]** | **[!UICONTROL *shift+ctrl+v *]** | プロジェクトを CSV ファイルとしてダウンロードします。 |
| **[!UICONTROL ダウンロードPDF]** | **[!UICONTROL *shift+cmd+b *]** | **[!UICONTROL *shift+ctrl+b *]** | プロジェクトをPDFドキュメントとしてダウンロードします。 |
| **[!UICONTROL プロジェクト情報および設定]** | | | 名前、タグ、カラーパレットなど、プロジェクトの設定を定義します。 |
| **[!UICONTROL ユーザー設定]** | | | [Analysis Workspaceを使用するための環境設定を行います ](/help/analysis-workspace/user-preferences.md)。 |


| **[!UICONTROL 編集]** | ショートカットMac | ショートカットウィンドウ | 説明 |
|---|---|---|---|
| **[!UICONTROL 元に戻す]** | **[!UICONTROL *cmd+z *]** | **[!UICONTROL *ctrl+z *]** | 前のアクションを取り消します。 |
| **[!UICONTROL やり直し]** | **[!UICONTROL *cmd+shift+z *]** | **[!UICONTROL *ctrl+shift+z *]** | 前のアクションをやり直します。 |
| **[!UICONTROL すべてクリア]** | **[!UICONTROL *opt+w *]** | **[!UICONTROL *alt+w *]** | 現在のプロジェクトのすべてのパネルをクリアします。 |

| **[!UICONTROL 挿入]** | ショートカットMac | ショートカットウィンドウ | 説明 |
|---|---|---|---|
| **[!UICONTROL 空のパネル]** | **[!UICONTROL *opt+b *]** | **[!UICONTROL *alt+b *]** | [ 空のパネル ](/help/analysis-workspace/c-panels/blank-panel.md) を挿入します。 |
| **[!UICONTROL メディア同時閲覧者数]** | **[!UICONTROL *opt+h *]** | **[!UICONTROL *alt-h *]** | [ メディア同時視聴者数 ](/help/analysis-workspace/c-panels/media-concurrent-viewers.md) パネルを挿入します。 |
| **[!UICONTROL メディア再生滞在時間]** | **[!UICONTROL *opt+i *]** | **[!UICONTROL *alt+i *]** | [ メディア再生滞在時間 ](/help/analysis-workspace/c-panels/media-playback-time-spent.md) パネルを挿入します。 |
| **[!UICONTROL メディア分平均オーディエンス]** | **[!UICONTROL *opt+m *]** | **[!UICONTROL *alt+m *]** | [ メディア分平均オーディエンス ](/help/analysis-workspace/c-panels/average-minute-audience-panel.md) パネルを挿入します。 |
| **[!UICONTROL アトリビューション]** | **[!UICONTROL *opt+e *]** | **[!UICONTROL *alt+e *]** | [ アトリビューション ](/help/analysis-workspace/c-panels/attribution.md) パネルを挿入します。 |
| **[!UICONTROL フリーフォーム]** | **[!UICONTROL *opt+a *]** | **[!UICONTROL *alt+a *]** | [ フリーフォーム ](/help/analysis-workspace/c-panels/freeform-panel.md) パネルを挿入します。 |
| **[!UICONTROL クイックインサイト]** | **[!UICONTROL *opt+j *]** | **[!UICONTROL *alt+j *]** | [ クイックインサイト ](/help/analysis-workspace/c-panels/quickinsight.md) パネルを挿入します。 |
| **[!UICONTROL 実験]** | **[!UICONTROL *opt+x *]** | **[!UICONTROL *alt+x *]** | [ 実験 ](/help/analysis-workspace/c-panels/experimentation.md) パネルを挿入します。 |
| **[!UICONTROL フリーフォームテーブル]** | **[!UICONTROL *opt+1 *]** | **[!UICONTROL *alt+1 *]** | [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ビジュアライゼーションを挿入します。 |
| **[!UICONTROL 行]** | **[!UICONTROL *opt+2 *]** | **[!UICONTROL *alt+2 *]** | [ 折れ線グラフ ](/help/analysis-workspace/visualizations/line.md) ビジュアライゼーションを挿入します。 |
| **[!UICONTROL 棒グラフ]** | **[!UICONTROL *opt+3 *]** | **[!UICONTROL *alt+3 *]** | [ 棒グラフ ](/help/analysis-workspace/visualizations/bar.md) ビジュアライゼーションを挿入します。 |
| **[!UICONTROL コンボ]** | **[!UICONTROL *opt+4 *]** | **[!UICONTROL *alt+4 *]** | [ コンボ ](/help/analysis-workspace/visualizations/combo-charts.md) ビジュアライゼーションを挿入します。 |


| **[!UICONTROL コンポーネント]** | ショートカットMac | ショートカットウィンドウ | 説明 |
|---|---|---|---|
| **[!UICONTROL フィルターを作成…]** | **[!UICONTROL *shift+cmd+e *]** | **[!UICONTROL *shift+ctrl+e *]** | 新規 [ フィルター ](/help/components/filters/create-filters.md) を作成します。 |
| **[!UICONTROL 指標を作成…]** | **[!UICONTROL *shift+cmd+c *]** | **[!UICONTROL *shift+ctrl+c *]** | 新しい [ 計算指標 ](/help/components/calc-metrics/calc-metr-overview.md) を作成します。 |
| **[!UICONTROL 日付範囲を作成…]** | **[!UICONTROL *shift+cmd+d *]** | **[!UICONTROL *shift+ctrl+d *]** | 新しい [ 日付範囲 ](/help/components/date-ranges/overview.md) を作成します |
| **[!UICONTROL 注釈を作成…]** | **[!UICONTROL *shift+cmd+o *]** | **[!UICONTROL *shift+ctrl+o *]** | 新規 [ 注釈 ](/help/components/annotations/overview.md) を作成します。 |
| **[!UICONTROL オーディエンスを作成…]** | **[!UICONTROL *shift+cmd+u *]** | **[!UICONTROL *shift+ctrl+u *]** | 新しい [ オーディエンス ](/help/components/audiences/audiences-overview.md) を作成します。 |
| **[!UICONTROL コンポーネントを参照]** | **[!UICONTROL *opt+shift+r *]** | **[!UICONTROL *alt+shift+r *]** | プロジェクトのコンポーネントを更新します。 |

| **[!UICONTROL 共有]** | ショートカットMac | ショートカットウィンドウ | 説明 |
|---|---|---|---|
| **[!UICONTROL Workspace ユーザーと共有]** | **[!UICONTROL *cmd+h *]** | **[!UICONTROL *ctrl+h *]** | [ プロジェクトを他のWorkspace ユーザーと共有します ](/help/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization)。 |
| **[!UICONTROL 任意のユーザーと共有]** | **[!UICONTROL *opt+l *]** | **[!UICONTROL *alt+l *]** | [ プロジェクトの読み取り専用バージョンを任意のユーザーと共有する ](/help/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project) |
| **[!UICONTROL ファイルを送信]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s *]** | [ プロジェクトを CSV またはPDFファイルとして他の受信者に送信します ](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL ファイルの書き出しをスケジュール]** | **[!UICONTROL *shift+opt+s *]** | **[!UICONTROL *shift+alt+s *]** | [ スケジュールに従って、プロジェクトを CSV またはPDFファイルとして他の受信者に送信します ](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL プロジェクトデータをキュレート]** | **[!UICONTROL *shift+cmd+g *]** | **[!UICONTROL *shift+ctrl+g *]** | [ プロジェクトデータをキュレーション ](/help/analysis-workspace/curate-share/curate.md) します。 |

| ヘルプ | ショートカットMac | ショートカットウィンドウ | 説明 |
|---|---|---|---|
| **[!UICONTROL ビデオ]** | | | 新しいブラウザータブで、Customer Journey AnalyticsYouTubeチャネルを開きます。 |
| **[!UICONTROL ヘルプドキュメント]** | | | 新しいブラウザータブでドキュメントを開きます（実際には読んでいるところです）。 |
| **[!UICONTROL ヘルプフォーラム]** | | | 新しいブラウザータブで、Adobe Analytics Experience Leagueコミュニティフォーラムを開きます。 |
| **[!UICONTROL ホットキー]** | | | Workspaceで使用できるホットキー（ショートカット）の概要を示します。 |
| **[!UICONTROL デバッガーの有効化]** |  | | デバッガーを有効にします。 プロジェクトが再読み込みされます。 |
| **[!UICONTROL デバッガーを無効にする]** | | | デバッガーを無効にします。 プロジェクトが再読み込みされます。 |
| **[!UICONTROL パフォーマンス]** | | | **[!UICONTROL Analysis Workspaceのパフォーマンス]** に関する指標を表示するダイアログを表示します。 **[!UICONTROL CSV としてダウンロード]** を使用して、パフォーマンス指標の CSV ファイルをダウンロードします。 |
| **[!UICONTROL Workspaceについて]** | | | バージョン情報、機能アクセスレベル、アクティブな機能フラグを含む **[!UICONTROL Analysis Workspaceについて]** ダイアログを表示します。 |

## データソース

ビジュアライゼーションを同期して、ビジュアライゼーションに対応するデータテーブルまたはデータソースを制御します。 詳しくは、[ データソースの管理 ](/help/analysis-workspace/visualizations/t-sync-visualization.md) を参照してください。

## Analysis Workspaceの使用


Analysis Workspaceを使い始めるには：

1. [Adobe Experience Cloud](https://experience.adobe.com) にログインします。
1. インターフェイスの右上にあるアプリ切り替えボタン ![ アプリ ](/help/assets/icons/Apps.svg) から「**[!UICONTROL Customer Journey Analytics]**」を選択します。
1. Analysis Workspaceの **[!UICONTROL プロジェクト]** ページがデフォルトで表示されます。 特定のプロジェクトが選択されている場合や、最近作業を行った場合は、そのプロジェクトがデフォルトで表示されます。

### プロジェクトの作成

Analysis Workspace での分析は、[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)と呼ばれます。

[プロジェクトの作成](/help/analysis-workspace/build-workspace-project/create-projects.md)で説明したように、Analysis Workspace でプロジェクトを作成できます。

[Analysis Workspace のフォルダー](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)で説明したように、プロジェクトはフォルダーとサブフォルダーに整理できます。

### プロジェクトの保存および共有

Analysis Workspace で分析を作成すると、作業内容は[自動保存](/help/analysis-workspace/build-workspace-project/save-projects.md)されます。

プロジェクトの構築が完了し、実用的なインサイトが収集されると、他のユーザーがプロジェクトを使用したいかもしれません。 プロジェクトは、組織内のユーザーやグループだけでなく、組織外の人物と共有することもできます。プロジェクトの共有について詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)を参照してください。

## その他のリソース {#resources}

- Customer Journey Analyticsの [ ラーニングランディング ](/help/getting-started/landing.md#learning) ページ。 このページは、Analysis Workspaceを知るのに最適な方法です。 特にラーニングWorkspaceファンダメンタル。 このテンプレートでは、Workspaceで最初の分析を作成するための一般的な用語と手順について説明します
- アドビでは、数百もの[Analytics ビデオトレーニングチュートリアル](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/overview)を提供しています。
- 新機能の最新情報については、 [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current) を参照してください。

