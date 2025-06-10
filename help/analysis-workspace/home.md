---
keywords: Analysis Workspace
title: Analysis Workspace の概要
description: Analysis Workspace 機能の概要
feature: Workspace Basics
exl-id: 9075518e-54fe-49a6-9601-aa9468187b8f
solution: Customer Journey Analytics
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 99%

---

# Analysis Workspace の概要 {#analysis-workspace-overview}

Analysis Workspace では、分析をすばやく作成してインサイトを収集し、他のユーザーと共有できます。ドラッグ＆ドロップのブラウザーインターフェイスを使用して、分析の作成、データを活用するビジュアライゼーションの追加、データセットのキュレーション、選択した任意のユーザーとの[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)の共有とスケジュールを行うことができます。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace の概要](https://video.tv.adobe.com/v/35774/?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

## インターフェイス

次の画像と付属の表では、Analysis Workspace ユーザーインターフェイスの主な要素を説明します。

![インターフェイスの様々なセクションがハイライト表示された、Analysis Workspace ウィンドウ](assets/analysis-workspace-overview.png)

| 場所 | 名前と機能 |
|:---------:|----------|
| A | プロジェクトの名前、機能にアクセスするメニュー構造、プロジェクトリストに戻る「![戻るボタン](/help/assets/icons/ChevronLeft.svg)」、[Workspace プロジェクトを共有する](/help/analysis-workspace/curate-share/share-projects.md)「**[!UICONTROL 共有]**」ボタンが含まれています。<br/>いつでもプロジェクトの名前（新規プロジェクトなど）を選択して、名前を変更します。<br/>「![お気に入りから外す](/help/assets/icons/StarOutline.svg)」を選択して、プロジェクトをお気に入りのプロジェクト「![お気に入りに追加](/help/assets/icons/Star.svg)」として登録します。 |
| B | **ボタンパネル：** Analysis Workspace の主要な[機能](#features)にアクセスするボタンが含まれています。<ul><li>![Web ページ](/help/assets/icons/WebPage.svg) [[!UICONTROL パネル]](/help/analysis-workspace/c-panels/panels.md)</li><li>![ガイド付き分析](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL ガイド付き分析]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL ビジュアライゼーション]](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>[[!UICONTROL コンポーネント]](/help/components/overview.md)を![キュレーション](/help/assets/icons/Curate.svg)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL 目次]](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![ブックマーク](/help/assets/icons/Bookmark.svg) [[!UICONTROL データ辞書]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **左パネル：**&#x200B;この領域には、個々のパネル、ビジュアライゼーション、コンポーネントまたはリストが含まれます。コンテンツは、ボタンパネルで選択したボタンによって異なります。 |
| D | **キャンバス：**&#x200B;これは、左パネルからコンテンツをドラッグしてプロジェクトを作成する主な領域です。パネルの追加、パネルへのビジュアライゼーションの追加、ビジュアライゼーションへのコンポーネントの追加を行うと、プロジェクトは動的に更新されます。複数のパネルを作成でき、各パネル内で複数のビジュアライゼーションを作成できます。<br/>各パネルは、選択したデータビューに基づいています。選択したデータビューによって、指標やディメンションなど、使用可能なコンポーネントが決まります。詳しくは、[パネル - データビュー](/help/analysis-workspace/c-panels/panels.md#data-view)を参照してください。 |

## 機能

Analysis Workspace の主な機能は、ボタンパネルから使用できます。

| アイコン | 機能 | 説明 |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL パネル]** | [パネル](/help/analysis-workspace/c-panels/panels.md)を使用すると、プロジェクト内の分析を整理し、多数のテーブルやビジュアライゼーションを含めることができます。Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。 |
| ![ガイド付き分析](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL ガイド付き分析]** | [ガイド付き分析](../guided-analysis/overview.md)では、ガイド付きワークフローを通じて、カスタマージャーニーに関する高品質のデータとインサイトをセルフサービスで提供できます。分析を作成して Workspace プロジェクトに含めたり、以前に保存した既存の分析を含めたりできます。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL ビジュアライゼーション]** | 棒グラフや折れ線グラフなどの[ビジュアライゼーション](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)を使用して、データを視覚的に表示できます。左端のパネルで、中央の&#x200B;**[!UICONTROL ビジュアライゼーション]**&#x200B;アイコンを選択し、使用可能なビジュアライゼーションの完全なリストを表示します。 |
| ![キュレート](/help/assets/icons/Curate.svg) | **[!UICONTROL コンポーネント]** | [コンポーネント](/help/components/overview.md)には、次の要素が含まれます。<ul><li>![ディメンション](/help/assets/icons/Dimensions.svg) [ディメンション](/help/components/dimensions/overview.md)</li><li>![イベント](/help/assets/icons/Event.svg) [指標](/help/components/apply-create-metrics.md)</li><li>![ セグメント化 ](/help/assets/icons/Segmentation.svg) セグメ [ ト ](/help/components/segments/seg-overview.md)</li><li>![カレンダー](/help/assets/icons/Calendar.svg) [日付範囲](/help/components/date-ranges/overview.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL 目次]** | 目次は、プロジェクトに含まれているすべてのパネルとビジュアライゼーションを折りたたみ可能なリストに整理されているので、特定のパネルやビジュアライゼーションにすばやくアクセスできます。 |
| ![ブックマーク](/help/assets/icons/Bookmark.svg) | **データ辞書** | [データ辞書](/help/components/data-dictionary/data-dictionary-overview.md)は、ユーザーと管理者の両方にとって、Analytics 環境のコンポーネントを追跡したり、理解を深めたりするのに役立ちます。 |


## メニュー

Analysis Workspace のほとんどの機能は、ドラッグ＆ドロップのほか、パネル、ビジュアライゼーションおよびコンポーネント内のコンテキストメニューから利用できます。

Workspace メニューとショートカットまたはホットキーを使用して、機能を利用することもできます。ショートカットキーは、ブラウザーを実行しているオペレーティングシステムによって異なります。概要について詳しくは、以下の表を参照してください。

キーボードでは、次の記号が使用される場合があります。

- **[!UICONTROL *Shift キー&#x200B;*]**&#x200B;の代わりに&#x200B;**⇧**。
- **[!UICONTROL *cmd *]**（コマンド）の&#x200B;**⌘**。
- **[!UICONTROL *ctrl *]**（コントロール）の&#x200B;**⌃**。
- **[!UICONTROL *オプト&#x200B;*]**（オプション）の&#x200B;**⌥**。
- **[!UICONTROL *alt *]**（代替）の&#x200B;**⎇**。

利用できるメニューの概要について詳しくは、以下の表を参照してください。

| **[!UICONTROL プロジェクト]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL プロジェクトの作成]** | **[!UICONTROL *Shift + Cmd + P キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + P キー&#x200B;*]** | 新しいプロジェクトを作成します。 |
| **[!UICONTROL モバイルスコアカードの作成]** | | | [新しいモバイルスコアカードを作成します](/help/mobile-app/create-scorecard.md)。 |
| **[!UICONTROL 開いています...]** | **[!UICONTROL *Cmd + O キー&#x200B;*]** | **[!UICONTROL *Ctrl + O キー&#x200B;*]** | [既存のプロジェクトを開きます](/help/analysis-workspace/build-workspace-project/save-projects.md#open-another-project)。 |
| **[!UICONTROL 以前のバージョンを開いています...]** | **[!UICONTROL *Opt + Cmd + O キー&#x200B;*]** | **[!UICONTROL *Alt + Ctrl + O キー&#x200B;*]** | [以前のバージョンのプロジェクトを開きます](/help/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version)。 |
| **[!UICONTROL 保存]** | **[!UICONTROL *Cmd + S キー&#x200B;*]** | **[!UICONTROL *Ctrl + S キー&#x200B;*]** | [プロジェクトを保存します](/help/analysis-workspace/build-workspace-project/save-projects.md#save-projects)。 |
| **[!UICONTROL メモと共に保存...]** | **[!UICONTROL *Opt + Cmd + S キー&#x200B;*]** | **[!UICONTROL *Alt + Ctrl + S キー&#x200B;*]** | [保存するプロジェクトバージョンにメモを追加します](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 名前を付けて保存...]** | **[!UICONTROL *Shift + Cmd + S キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + S キー&#x200B;*]** | [別の名前と詳細を使用してプロジェクトを保存します](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL プロジェクトを更新]** | **[!UICONTROL *Opt + R キー&#x200B;*]** | **[!UICONTROL *Alt + R キー&#x200B;*]** | プロジェクトを更新します。 |
| **[!UICONTROL CSV をダウンロード]** | **[!UICONTROL *Shift + Cmd + V キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + V キー&#x200B;*]** | プロジェクトを CSV ファイルとしてダウンロードします。 |
| **[!UICONTROL PDF をダウンロード]** | **[!UICONTROL *Shift + Cmd + B キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + B キー&#x200B;*]** | プロジェクトを PDF ドキュメントとしてダウンロードします。 |
| **[!UICONTROL プロジェクト情報および設定]** | | | 名前、タグ、カラーパレットなど、プロジェクトの設定を定義します。 |
| **[!UICONTROL ユーザー設定]** | | | [Analysis Workspace の使用に適した環境設定を行います](/help/analysis-workspace/user-preferences.md)。 |


| **[!UICONTROL 編集]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL 元に戻す]** | **[!UICONTROL *Cmd + Z キー&#x200B;*]** | **[!UICONTROL *Ctrl + Z キー&#x200B;*]** | 前のアクションを取り消します。 |
| **[!UICONTROL やり直し]** | **[!UICONTROL *Cmd + Shift + Z キー&#x200B;*]** | **[!UICONTROL *Ctrl + Shift + Z キー&#x200B;*]** | 前のアクションをやり直します。 |
| **[!UICONTROL すべてクリア]** | **[!UICONTROL *Opt + W キー&#x200B;*]** | **[!UICONTROL *Alt + W キー&#x200B;*]** | 現在のプロジェクトのすべてのパネルをクリアします。 |

| **[!UICONTROL 挿入]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL 空のパネル]** | **[!UICONTROL *Opt + B キー&#x200B;*]** | **[!UICONTROL *Alt + B キー&#x200B;*]** | [空のパネル](/help/analysis-workspace/c-panels/blank-panel.md)を挿入します。 |
| **[!UICONTROL メディア同時閲覧者数]** | **[!UICONTROL *Opt + H キー&#x200B;*]** | **[!UICONTROL *Alt + H キー&#x200B;*]** | [メディア同時視聴者](/help/analysis-workspace/c-panels/media-concurrent-viewers.md)パネルを挿入します。 |
| **[!UICONTROL メディア再生滞在時間]** | **[!UICONTROL *Opt + I キー&#x200B;*]** | **[!UICONTROL *Alt + I キー&#x200B;*]** | [メディア再生滞在時間](/help/analysis-workspace/c-panels/media-playback-time-spent.md)パネルを挿入します。 |
| **[!UICONTROL メディア分平均オーディエンス]** | **[!UICONTROL *Opt + M キー&#x200B;*]** | **[!UICONTROL *Alt + M キー&#x200B;*]** | [メディア分平均オーディエンス](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)パネルを挿入します。 |
| **[!UICONTROL アトリビューション]** | **[!UICONTROL *Opt + E キー&#x200B;*]** | **[!UICONTROL *Alt + E キー&#x200B;*]** | [アトリビューション](/help/analysis-workspace/c-panels/attribution.md)パネルを挿入します。 |
| **[!UICONTROL フリーフォーム]** | **[!UICONTROL *Opt + A キー&#x200B;*]** | **[!UICONTROL *Alt + A キー&#x200B;*]** | [フリーフォーム](/help/analysis-workspace/c-panels/freeform-panel.md)パネルを挿入します。 |
| **[!UICONTROL クイックインサイト]** | **[!UICONTROL *Opt + J キー&#x200B;*]** | **[!UICONTROL *Alt + J キー&#x200B;*]** | [クイックインサイト](/help/analysis-workspace/c-panels/quickinsight.md)パネルを挿入します。 |
| **[!UICONTROL 実験]** | **[!UICONTROL *Opt + X キー&#x200B;*]** | **[!UICONTROL *Alt + X キー&#x200B;*]** | [実験](/help/analysis-workspace/c-panels/experimentation.md)パネルを挿入します。 |
| **[!UICONTROL フリーフォームテーブル]** | **[!UICONTROL *Opt + 1 キー&#x200B;*]** | **[!UICONTROL *Alt + 1 キー&#x200B;*]** | [フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)ビジュアライゼーションを挿入します。 |
| **[!UICONTROL 折れ線グラフ]** | **[!UICONTROL *Opt + 2 キー&#x200B;*]** | **[!UICONTROL *Alt + 2 キー&#x200B;*]** | [折れ線グラフ](/help/analysis-workspace/visualizations/line.md)ビジュアライゼーションを挿入します。 |
| **[!UICONTROL 棒グラフ]** | **[!UICONTROL *Opt + 3 キー&#x200B;*]** | **[!UICONTROL *Alt + 3 キー&#x200B;*]** | [棒グラフ](/help/analysis-workspace/visualizations/bar.md)ビジュアライゼーションを挿入します。 |
| **[!UICONTROL コンボ]** | **[!UICONTROL *Opt + 4 キー&#x200B;*]** | **[!UICONTROL *Alt + 4 キー&#x200B;*]** | [コンボ](/help/analysis-workspace/visualizations/combo-charts.md)ビジュアライゼーションを挿入します。 |


| **[!UICONTROL コンポーネント]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL セグメントを作成…]** | **[!UICONTROL *Shift + Cmd + E キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + E キー&#x200B;*]** | 新しい[セグメント](/help/components/segments/seg-create.md)を作成します。 |
| **[!UICONTROL 指標を作成…]** | **[!UICONTROL *Shift + Cmd + C キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + C キー&#x200B;*]** | 新しい[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を作成します。 |
| **[!UICONTROL 日付範囲を作成...]** | **[!UICONTROL *Shift + Cmd + D キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + D キー&#x200B;*]** | 新しい[日付範囲](/help/components/date-ranges/overview.md)を作成します。 |
| **[!UICONTROL 注釈を作成…]** | **[!UICONTROL *Shift + Cmd + O キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + O キー&#x200B;*]** | 新しい[注釈](/help/components/annotations/overview.md)を作成します。 |
| **[!UICONTROL オーディエンスを作成...]** | **[!UICONTROL *Shift + Cmd + U キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + U キー&#x200B;*]** | 新しい[オーディエンス](/help/components/audiences/audiences-overview.md)を作成します。 |
| **[!UICONTROL コンポーネントを更新]** | **[!UICONTROL *Opt + Shift + R キー&#x200B;*]** | **[!UICONTROL *Alt + Shift + R キー&#x200B;*]** | プロジェクトのコンポーネントを更新します。 |

| **[!UICONTROL 共有]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL Workspace ユーザーと共有]** | **[!UICONTROL *Cmd + H キー&#x200B;*]** | **[!UICONTROL *Ctrl + H キー&#x200B;*]** | [プロジェクトを他の Workspace ユーザーと共有します](/help/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization)。 |
| **[!UICONTROL 任意のユーザーと共有]** | **[!UICONTROL *Opt + L キー&#x200B;*]** | **[!UICONTROL *Alt + L キー&#x200B;*]** | [プロジェクトの読み取り専用バージョンを任意のユーザーと共有します](/help/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project)。 |
| **[!UICONTROL ファイルを送信]** | **[!UICONTROL Opt + S キー]** | **[!UICONTROL *Alt + S キー&#x200B;*]** | [プロジェクトを CSV または PDF ファイルとして他の受信者に送信します](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL ファイルの書き出しをスケジュール]** | **[!UICONTROL *Shift + Opt + S キー&#x200B;*]** | **[!UICONTROL *Shift + Alt + S キー&#x200B;*]** | [スケジュールに従って、プロジェクトを CSV または PDF ファイルとして他の受信者に送信します](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL プロジェクトデータをキュレート]** | **[!UICONTROL *Shift + Cmd + G キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + G キー&#x200B;*]** | [プロジェクトデータをキュレートします](/help/analysis-workspace/curate-share/curate.md)。 |

| ヘルプ | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL ビデオ]** | | | 新しいブラウザータブで、Customer Journey Analytics の YouTube チャネルを開きます。 |
| **[!UICONTROL ヘルプドキュメント]** | | | 新しいブラウザータブでドキュメントを開きます（実際には今読んでいるところです）。 |
| **[!UICONTROL ヘルプフォーラム]** | | | 新しいブラウザータブで、Adobe Analytics Experience League コミュニティフォーラムを開きます。 |
| **[!UICONTROL ホットキー]** | | | Workspace で使用できるホットキー（ショートカット）の概要を示します。 |
| **[!UICONTROL デバッガーの有効化]** |  | | デバッガーを有効にします。プロジェクトが再読み込みされます。 |
| **[!UICONTROL デバッガーの無効化]** | | | デバッガーを無効にします。プロジェクトが再読み込みされます。 |
| **[!UICONTROL パフォーマンス]** | | | **[!UICONTROL Analysis Workspace のパフォーマンス]**&#x200B;に関する指標を表示するダイアログを表示します。**[!UICONTROL CSV としてダウンロード]**&#x200B;を使用して、パフォーマンス指標の CSV ファイルをダウンロードします。 |
| **[!UICONTROL Workspace について]** | | | バージョン情報、機能アクセスレベル、アクティブな機能フラグを含む **[!UICONTROL Analysis Workspaceについて]**&#x200B;ダイアログを表示します。 |

## データソース

ビジュアライゼーションを同期することで、ビジュアライゼーションに対応するデータテーブルまたはデータソースを制御できます。詳しくは、[データソースの管理](/help/analysis-workspace/visualizations/t-sync-visualization.md)を参照してください。

## Analysis Workspace の使用


Analysis Workspace の使用を開始するには：

1. [Adobe Experience Cloud](https://experience.adobe.com) にログインします。
1. インターフェイスの右上にあるアプリ切り替えボタン![アプリ](/help/assets/icons/Apps.svg)から「**[!UICONTROL Customer Journey Analytics]**」を選択します。
1. デフォルトでは、Analysis Workspace の&#x200B;**[!UICONTROL プロジェクト]**&#x200B;ページが表示されます。特定のプロジェクトが選択されている場合や、最近作業を行った場合は、そのプロジェクトがデフォルトで表示されます。

### プロジェクトの作成

Analysis Workspace での分析は、[プロジェクト](/help/analysis-workspace/build-workspace-project/freeform-overview.md)と呼ばれます。

[プロジェクトの作成](/help/analysis-workspace/build-workspace-project/create-projects.md)で説明したように、Analysis Workspace でプロジェクトを作成できます。

[Analysis Workspace のフォルダー](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)で説明したように、プロジェクトはフォルダーとサブフォルダーに整理できます。

### プロジェクトの保存および共有

Analysis Workspace で分析を作成すると、作業内容は[自動保存](/help/analysis-workspace/build-workspace-project/save-projects.md)されます。

プロジェクトの作成が完了し、実用的なインサイトを収集すると、そのプロジェクトを他のユーザーが使用できます。プロジェクトは、組織内のユーザーやグループだけでなく、組織外の人物と共有することもできます。プロジェクトの共有について詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)を参照してください。

## その他のリソース {#resources}

- Customer Journey Analytics の[ラーニングランディング](/help/getting-started/landing.md#learning)ページ。このページは、Analysis Workspace を知るのに最適です。特に Workspace の基本の学習。このテンプレートでは、Workspace で初めての分析を作成する一般的な用語と手順について説明します。
- アドビでは、数百もの[Analytics ビデオトレーニングチュートリアル](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/overview)を提供しています。
- 新機能の最新情報については、 [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/ja/docs/release-notes/experience-cloud/current) を参照してください。

