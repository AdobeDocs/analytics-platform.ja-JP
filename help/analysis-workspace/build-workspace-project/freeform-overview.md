---
description: メニューバーと設定を含む Workspace プロジェクトの概要
keywords: Analysis Workspace
title: プロジェクトの概要
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 10751991e3c40cfefac7d32cea0b5cc557133232
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 64%

---

# プロジェクトの概要

Workspace プロジェクトでは、データコンポーネント、テーブル、およびビジュアライゼーションを組み合わせて、分析を作成し、組織内の任意のユーザーと共有できます。最初のプロジェクトを開始する前に、プロジェクトへのアクセス方法、プロジェクト間の移動方法、およびプロジェクトの管理方法について説明します。

## プロジェクトリスト {#project-list}

最初に **[!UICONTROL Analytics]**/**[!UICONTROL Workspace]** に移動すると、自分が所有するすべてのプロジェクトまたは自分に共有されるプロジェクトがページに表示されます。 これは、以前にカスタムのランディングページを設定した場合を除き、Adobe Analytics のランディングページでもあります。

![ プロジェクトリストを表示するプロジェクトランディングページ ](assets/sample-project.png)

プロジェクト ページには、次の情報が含まれます。

>[!NOTE]
>
>デフォルトでは表示されない列もあります。 表示される列をカスタマイズするには、「**テーブルをカスタマイズ**」アイコン ![ テーブルをカスタマイズ ](assets/projects-page-customize-columns-icon.png) をクリックします。

| 要素 | 説明 |
|---|---|
| [ 環境設定を編集 ](/help/analysis-workspace/user-preferences.md) | 作成するすべての新規プロジェクトまたはパネルについて、Analysis Workspaceおよびその関連コンポーネントの設定を管理します。 |
| [ フォルダーを作成 ](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | プロジェクトとフォルダーのリストに新しいフォルダーまたはサブフォルダーを追加します。 |
| [プロジェクトの作成](/help/analysis-workspace/build-workspace-project/create-projects.md) | 新しいプロジェクトをゼロから開始します。 |
| さらに表示 | 空のプロジェクトまたはモバイルスコアカードの作成、[ トレーニングチュートリアルの表示 ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=ja) または [ リリースノートの表示 ](/help/release-notes/latest.md) のオプションが表示されます。 |
| フォルダーとプロジェクトを表示 | プロジェクトのフォルダー構造を表示するかどうかを選択します。 詳しくは、[Analytics のフォルダーについて](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)を参照してください。 |
| テーブルをカスタマイズ （アイコン） | プロジェクト ページで各プロジェクトに表示される情報をカスタマイズできます。 |
| 名前 | Workspace プロジェクトの名前。 |
| タイプ | これがWorkspace プロジェクト、フォルダーまたは [ モバイルスコアカード ](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=ja) のいずれであるかを示します。 |
| タグ | プロジェクトに適用されたタグです。 |
| スケジュール済み | プロジェクトがスケジュールに従って受信者にメールで送信されるようにスケジュールされているかどうかを示します。 [ プロジェクトデータの他のユーザーへの送信 ](/help/analysis-workspace/export/t-schedule-report.md) を参照してください。 |
| 共有リンク (任意のユーザー) | プロジェクトは、Analysis Workspaceへのアクセス権を持たないユーザーでも、誰とでも共有できます。 この列には、プロジェクトがこのようにして共有されたかどうかが表示されます。 詳しくは、[ プロジェクトを共有 ](/help/analysis-workspace/curate-share/share-projects.md) の「プロジェクトを任意のユーザーと共有する [ ログインは不要） ](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) を参照してください。 |
| データビュー | プロジェクトが関連付けられているデータビュー。 |
| [プロジェクトの役割](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja) | プロジェクトの役割（所有者、編集、重複、表示）を示します。 |
| 所有者 | このプロジェクトを作成したユーザー（ユーザー自身、またはユーザー自身とそのプロジェクトを共有した他のユーザー）。 |
| 共有先 | プロジェクトが共有されているユーザー。 |
| 最終変更日 | プロジェクトが最後に変更された日付。 |
| 前回開いた日時 | プロジェクトが最後に開かれた日時。 |
| プロジェクト ID | プロジェクトの ID。 |
| 最長の日付範囲 | プロジェクトの最長の日付範囲。 |
| クエリ数 | プロジェクトに含まれるクエリの合計数。 |
| 場所 | プロジェクトが存在するフォルダー。 |

## メニューバー {#menu-bar}

プロジェクト内のメニューには、プロジェクトの管理、コンポーネントの追加、ヘルプの検索などを行うためのオプションが表示されます。各メニューオプションには、キーボード[ショートカット](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を使用してアクセスできます。

![ 新規プロジェクトオプション（プロジェクト、編集、挿入、コンポーネント、共有、ヘルプの各オプションを含む） ](assets/menu.png)

| メニュー項目 | 説明 |
|---|---|
| プロジェクト | プロジェクト管理の一般的なアクション（新規、開く、保存、名前を付けて保存など）が含まれます。 また、「プロジェクトを更新」をクリックして、プロジェクト全体を更新し、最新のデータと定義を取得することもできます。[ プロジェクトデータをダウンロード ](/help/analysis-workspace/export/download-send.md) オプションを使用すると、Workspaceからデータを書き出すことができます。 「**プロジェクト情報および設定**」（以下を参照）には、プロジェクトを管理するための多くのオプションが用意されています。 |
| テンプレートを | 前回の操作を元に戻すか、やり直します。「すべてクリア」を選択すると、プロジェクトが最初の空白の状態にリセットされます。 |
| 前に | このメニューから、新しいパネルまたはビジュアライゼーションを挿入します。また、左側のパネルから新しいパネルやビジュアライゼーションを挿入することもできます。 |
| [コンポーネント](/help/components/overview.md) | プロジェクトから、新しいフィルター、計算指標、日付範囲またはアラートの各コンポーネントを作成します。また、左側のパネルから新しいコンポーネントを作成することもできます。コンポーネント定義が最近変更された場合は、「コンポーネントを更新」を選択すると最新の定義を取得できます。 |
| [共有](/help/analysis-workspace/curate-share/send-schedule-files.md) | 組織の受信者に対して PDF／CSV プロジェクトのキュレーション、共有およびスケジュール設定を行います。 |
| ヘルプ | ヘルプドキュメント、ビデオおよび Analytics [Experience League コミュニティ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ja)にアクセスします。Workspace のヒントの表示と[デバッガー](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md)の表示を管理します。Workspace の詳細と、プロジェクトの[パフォーマンス](/help/technotes/optimizing-performance.md)に影響を与える要因を確認します。 |
| 「共有」ボタンまたは「所有者」 | プロジェクトを所有または編集している場合は、右上の「共有」ボタンからワンクリックでアクセスして、プロジェクト受信者を管理できます。プロジェクトを複製または役割を表示している場合は、プロジェクト所有者の名前が表示されます。 |

### プロジェクト情報および設定 {#info-settings}

**[!UICONTROL Workspace]**/**[!UICONTROL プロジェクト]**/**[!UICONTROL プロジェクト情報および設定]** では、現在アクティブなプロジェクトに関するプロジェクトレベルの情報が提供されます。

![ プロジェクト情報および設定ウィンドウ ](assets/projectinfo.png)

「設定」には次の項目が含まれます。

| 設定 | 説明 |
|---|---|
| プロジェクト名 | プロジェクトに設定された名前。名前をダブルクリックすると編集できます。 |
| 作成者 | プロジェクト所有者名。 |
| 最終変更日 | プロジェクトの最終変更日。 |
| タグ | 分類を簡単にするためにプロジェクトに適用されたタグのリスト。 |
| 説明 | 説明は、プロジェクトの目的を明確にするのに役立ちます。説明をダブルクリックすると編集できます。 |
| プロジェクトで繰り返しのインスタンスをカウントします | レポート内でレポートインスタンスがカウントされるかどうかを指定します。注意：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。 |
| [プロジェクトカラーパレット](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Workspace で使用する分類カラーパレットを変更するには、色弱のユーザー向け用に最適化されている既定のパレットを選択するか、カスタムパレットを指定します。この機能は、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。 |
| [表示密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 左側のパネル、フリーフォームテーブル、コホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。 |

## 左側のパネル {#left-rail}

プロジェクト内の左側のパネルでは様々なアイコンを使用でき、それぞれがプロジェクトの重要な部分を表しています。

* [ パネル ](/help/analysis-workspace/c-panels/panels.md)![ パネルアイコン ](assets/panels-icon.png)

* [ ビジュアライゼーション ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![ ビジュアライゼーションアイコン ](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components アイコン ](assets/components-icon.png)

* [ データ要素 ](/help/components/data-dictionary/data-dictionary-overview.md)![ データ要素アイコン ](assets/data-dictionary-icon.png)

* [ 目次 ](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)![ 目次アイコン ](assets/toc-icon.png)

左側のパネルのコンポーネント（ディメンション、指標、フィルター、日付範囲）は、アクティブなパネルデータビューに関連しています。アクティブなパネルは、それを囲む青い境界線で識別され、アクティブなデータビューはコンポーネントパネルの上部にリストされます。

![ 業界横断的なデモデータビューのアクティブなパネルデータビューに関連するコンポーネント。](assets/left-rail.png)

## プロジェクトキャンバス {#canvas}

プロジェクトキャンバスでは、パネル、テーブル、ビジュアライゼーションおよびコンポーネントをまとめ、分析を作成できます。プロジェクトには多数のパネルを含めることができます。また、各パネルには多数のテーブルやビジュアライゼーションを含めることができます。

パネルは、期間、データビュー、分析ユースケースに従ってプロジェクトを整理する場合に役立ちます。アクティブパネルの周囲に青い境界線が表示され、左側のパネルから使用できるコンポーネントが決定されます。

プロジェクトの開始時に選択した内容に応じて、キャンバスに[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)または[空のパネル](/help/analysis-workspace/c-panels/blank-panel.md)が表示されます。分析を最も簡単に開始するには、1 つまたは複数のコンポーネントを選択し、それらをプロジェクトキャンバスにドラッグ＆ドロップします。データのテーブルが自動的にレンダリングされます。[こちら](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)からテーブルを作成するための様々なオプションについて確認してください。または、アドビの[トレーニングチュートリアル](/help/analysis-workspace/home.md)を活用して、初めてプロジェクトを作成する際の手順を確認してください。

![ プロジェクトのフリーフォームテーブル。](assets/canvas.png)

## プロジェクトマネージャー {#manager}

Analysis Workspace プロジェクトは、**Analytics／コンポーネント／プロジェクト**&#x200B;で管理できます。プロジェクトマネージャーには、特定のユーザーが作成した項目が表示されます。 管理者/ Analytics ユーザーおよびAssets / Assetsを転送で、プロジェクトの所有権を新しいユーザーに転送できます。

プロジェクトマネージャーでは、追加、タグ付け、共有、複製/コピーなどを行うことができます。 検索バーまたは左側のパネルのフィルターオプションを使用して、プロジェクトを検索します。タグ、所有者、プロジェクトのタイプなどでフィルターできます。

![ プロジェクトマネージャータグ検索フィールドとタイトル検索フィールド。](assets/project-manager.png)

以下は、プロジェクトマネージャの一般的な操作です。これらは、1 つまたは複数のプロジェクトに対して一度に実行できます。

| アクション | 説明 |
|---|---|
| 追加 | 新しいプロジェクトをゼロから作成します。 |
| タグまたは承認 | 「タグ」または「承認」を選択して、プロジェクトを整理し、検索しやすくします。 |
| [共有](/help/analysis-workspace/curate-share/share-projects.md) | プロジェクトを組織内の他の Analysis Workspace ユーザーも利用できるようになります。 |
| 削除 | プロジェクトを削除します。 |
| 名前変更 | プロジェクトの名前を編集します。 |
| コピー | プロジェクトの複製を作成します。これで、新しいプロジェクトとプロジェクト ID が作成されます。元のプロジェクトに関連付けられた共有またはスケジュールはコピーされません。 |
| CSV に書き出し | プロジェクトを CSV ファイルとしてダウンロードします。このファイルには、プレーンテキストデータが含まれます。 |
