---
description: 新しいランディングページの機能について説明します。
title: Customer Journey Analytics のランディングページ
role: User, Admin
feature: CJA Basics
exl-id: 65c7bc26-7160-4bba-b764-5b0fa8686fca
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 96%

---

# Customer Journey Analytics のランディングページ

Customer Journey Analytics 用のランディングページには、[!DNL Analysis Workspace]、プロジェクトマネージャーのホームページ、カスタマージャーニーデータをより効果的に管理するのに役立つラーニングセクションが用意されています。

>[!VIDEO](https://video.tv.adobe.com/v/334278/?quality=12)

## 新規ランディングページの機能 {#new-features}

| 機能 | 説明 | スクリーンショット |
| --- | --- | --- |
| [!UICONTROL プロジェクト]テーブルをフルスクリーンに拡張する | テーブルを拡張するには、ハンバーガーのメニューアイコンをクリックします。この操作を実行すると、左側のパネルのタブが折りたたまれます。 | ![テーブルを拡張](assets/landing-collapse2.png) |
| 列の幅のカスタマイズ | 以前は、列の幅は固定されていました。列区切り記号をドラッグして調整できるようになりました。 | ![列の幅](assets/column-width.png) |
| ピン留めされた項目の並べ替え | ピンされた項目を上下に移動するには、ピン留めされた項目の横の省略記号をクリックし、「**[!UICONTROL 上に移動]**」または「**[!UICONTROL 下に移動]**」を選択します。 | ![ピン留めされた項目を移動](assets/move-up-down.png) |
| 新規テーブル列 | テーブルの右上に表示される「[!UICONTROL テーブルをカスタマイズ]」アイコンをクリックします。新規テーブル列は次のとおりです。 <ul><li>**[!UICONTROL 予定]**：プロジェクトがスケジュールされた際は[!UICONTROL オン]、そうでない場合は[!UICONTROL オフ]に設定します。[!UICONTROL オン]のリンクをクリックすると、スケジュールされたプロジェクトに関する情報を表示できます。また、プロジェクトの所有者である場合は[プロジェクトスケジュールを編集](../analysis-workspace/curate-share/t-schedule-report.md)できます。</li><li>**[!UICONTROL プロジェクト ID]**：プロジェクト ID は、プロジェクトのデバッグに使用できます。</li><li>**[!UICONTROL 最長の日付範囲]**：日付範囲を長くすると、プロジェクトの複雑さが増し、処理と読み込み時間が長くなる場合があります。 </li><li>**[!UICONTROL クエリ数]**：プロジェクトの読み込み時に Analytics に対して行われたリクエストの合計数です。プロジェクトクエリの数が多いと、プロジェクトが複雑になり、処理と読み込みに時間がかかる場合があります。このデータは、プロジェクトが読み込まれた後、またはスケジュールされたプロジェクトが送信された後にのみ使用できます。 </li></ul> | ![新しい列](assets/new-columns.png) |
| **[!UICONTROL プロジェクトを作成]**&#x200B;モーダルが復活しました | ワークスペースで「**[!UICONTROL プロジェクトを作成]**」をクリックすると、[!UICONTROL 空のプロジェクト]と[!UICONTROL 空のモバイルスコアカード]のどちらかを、再び選択できるようになりました。会社が作成した任意のテンプレートから選択することもできます。 | ![新規作成](assets/create-new.png) |

{style="table-layout:auto"}

## 「[!UICONTROL プロジェクト]」タブに移動する {#navigate-projects}

[!UICONTROL プロジェクト]は、[!UICONTROL ワークスペース]ホームページとして機能します。「プロジェクト」タブには、会社フォルダー、作成した個人用フォルダー、プロジェクトおよびモバイルスコアカードが表示されます。このページを使用して、フォルダー、プロジェクトおよびモバイルスコアカードを表示、作成および変更します。詳しくは、[Analytics のフォルダーについて](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)を参照してください。

![すべてランディング](assets/landing-all2.png)

**[!UICONTROL プロジェクト]**&#x200B;は、自分が作成した、または他のユーザーが作成して自身と作成および共有したデータコンポーネント、テーブル、ビジュアライゼーションを組み合わせたカスタムのデザインです。[!UICONTROL プロジェクト]は、空のプロジェクトと空のモバイルスコアカードも指します。

>[!NOTE]
>
>次の設定の一部は、セッション中およびセッション間で保持されます。例えば、選択したタブ、選択したフィルター、選択した列および列の並べ替え方向があります。検索結果は永続的ではありません。

| UI 要素 | 定義 |
| --- | --- |
| 環境設定を編集 | [!UICONTROL チュートリアルを表示]して、[ユーザー環境設定を編集](/help/analysis-workspace/user-preferences.md)できます。 |
| [!UICONTROL 新規作成] | Workspace プロジェクトやモバイルスコアカードを作成したり、会社テンプレートを開いたりできるプロジェクトモーダルを開きます。 |
| [!UICONTROL 表示を減らす<br> さらに表示] | バナーの表示／非表示を切り替えます。![トップバナー](assets/top-banner.png) |
| [!UICONTROL ワークスペースプロジェクト] | デザインおよび作成用の空の [Workspace プロジェクト](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja)を作成します。 |
| [!UICONTROL モバイルスコアカード] | デザインおよび作成用の空の[モバイルスコアカード](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html?lang=ja)を作成します。 |
| [!UICONTROL トレーニングチュートリアルを開く] | ステップバイステップのチュートリアルで新しいスタータープロジェクトの作成プロセスをガイドする Workspace トレーニングチュートリアルを開きます。 |
| [!UICONTROL リリースノートを開く] | 最新の Adobe Experience Cloud リリースノートの Adobe Analytics セクションを開きます。 |
| フィルターアイコン | タグ、データビュー、所有者、タイプおよびその他のフィルター（自分が所有、自分と共有、お気に入り、承認済み）でフィルター |
| 検索バー | テーブルのすべての列を検索します。 |
| 選択ボックス | 1 つまたは複数のプロジェクトを選択して、実行可能なプロジェクト管理アクションを表示します（**削除**、**共有**、**名前を変更**、**コピー**、**ピン留めを解除**、**上へ移動**、**下へ移動**、**タグ**、**承認**、**CSV を書き出し**&#x200B;および&#x200B;**移動**）。リストされたすべてのアクションを実行する権限がない可能性があります。 |
| [!UICONTROL お気に入り] | フィルターとして使用できるお気に入りのプロジェクトまたはフォルダーの横に星を追加します。 |
| [!UICONTROL 名前] | プロジェクトの名前を識別します。 |
| ピンアイコン | 項目をピン留めすると、リストの上部に常に表示されますが、順番を植えまたは下に移動させることで順番を再調整できます。省略記号オプションメニューを使用して、リストの&#x200B;**上へ移動**&#x200B;または&#x200B;**下へ移動**&#x200B;を選択します。 |
| 情報 (i) アイコン | プロジェクトに関する情報（タイプ、プロジェクトの役割、所有者、説明および共有相手）を表示します。また、このプロジェクトを[編集または複製](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja)できるユーザーも示します。 |
| 省略記号（...） | 実行できるプロジェクト管理アクション（**削除**、**共有**、**名前を変更**、**コピー**、**ピン留めを解除**、**上へ移動**、**下へ移動**、**タグ**、**承認**、**CSV を書き出し**&#x200B;および&#x200B;**移動**）を表示します。リストされたすべてのアクションを実行する権限がない可能性があります。 |
| [!UICONTROL タイプ] | このタイプが Workspace プロジェクト、モバイルスコアカードまたはフォルダーのいずれであるかを示します。 |
| [!UICONTROL タグ] | プロジェクトにタグ付けして、グループに整理します。 |
| [!UICONTROL プロジェクトの役割] | プロジェクトの役割（自分がプロジェクトの所有者であるかどうか、およびプロジェクトの編集または複製の権限を持っているかどうか）を識別します。 |
| [!UICONTROL データビュー] | プロジェクトに関連付けられているデータビューを識別します。<br>パネル内のテーブルとビジュアライゼーションは、パネルの右上で選択されたデータビューからデータを取得します。また、データビューでは、左パネルで使用できるコンポーネントも決定します。プロジェクト内では、分析の使用例に応じて、1 つまたは複数のデータビューを使用できます。 データビューのリストは関連度に基づいて並べ替えられます。アドビは、現在のユーザーがスイートを使用した最近の頻度と、組織内でスイートが使用された頻度に基づいて関連度を定義します。 |
| [!UICONTROL 所有者] | プロジェクトを作成した人物を識別します。 |
| [!UICONTROL 前回開いた日時] | プロジェクトを最後に開いた日付を識別します。 |
| テーブルアイコンのカスタマイズ | テーブルで表示する列を選択します。プロジェクトのリストから列を追加または削除するには、右上の列アイコン（![すべてランディング](assets/select-column.png)）をクリックしてから、列タイトルを選択または選択解除します。 |
| 表示：フォルダーとプロジェクトまたはすべてのプロジェクト | テーブルの表示設定を変更して、フォルダー組織に従ってフォルダーおよびプロジェクトを表示するか、**または**&#x200B;未整理のリストのすべてのプロジェクトを表示します。 |
| &lt;（戻るボタン） | ワークスペースプロジェクト内の最新のランディングページ設定に戻ります。ランディングページを離れた時点でのページ設定は、戻った際にも保持されます。 |

### プロジェクトマネージャーページの廃止 {#deprecate-pm-page}

新しいランディングページのリリースにより、コンポーネントマネージャーの下にリストされているプロジェクトマネージャーを廃止しました。新しいランディングページは、古いプロジェクトマネージャーページのすべての機能を処理します。

プロジェクトマネージャーページの一般的なユースケースの一つに、すべてのプロジェクトを表示することがあります。フィルターレールを使用して新しいランディングページのすべてのプロジェクトを表示するには、「**その他のフィルター**」、「**すべて表示**」の順に選択します。

![その他のフィルター](assets/other-filters.png)

「フォルダーとプロジェクト」表示を開いている場合は、「すべてのプロジェクト」ビューに切り替えるかどうかを尋ねるモーダルがポップアップ表示され、整理されたフォルダーの外ですべてのプロジェクトを簡単に表示できます。**「すべてのプロジェクト」ビューに切り替える**&#x200B;を選択して、アクセス権があるすべてのプロジェクトをわかりやすく表示します。

![「すべてのプロジェクト」に切り替える](assets/switch-all-projects-view.png)

## 「学習」タブへの移動 {#navigate-learning}

学習ページには、実践ビデオツアーとチュートリアルのほか、ドキュメントへのリンクが含まれています。

* [!UICONTROL ワークスペースの基本]ツアーでは、ワークスペースに直接アクセスし、ワークスペースのレイアウトと、最も一般的なアクションをどこで見つけて実行できるかについて説明します。このツアーは、パネルヘッダーからツールチップポップオーバーを使用して、ワークスペースでいつでも直接再起動できます。
* ビデオ／ツアーをクリックすると、「**[!UICONTROL 閲覧済み]**」タグが追加されます。このタグは、学習コンテンツの進捗状況を追跡するのに役立ちます。コンテンツをまだ完了していない場合は、タグをクリックするとタグが消えます。
* ビデオモーダルの「**[!UICONTROL 詳細情報]**」ボタンをクリックすると、先ほど視聴したビデオに関連する詳細なヘルプコンテンツが記載された Adobe Experience League ドキュメントページが表示されます。「**[!UICONTROL その他のビデオを視聴する]**」をクリックすると、Analysis Workspace YouTube の完全なプレイリスト全体が表示されます。

## ランディングページの設定 {#set-landing}

ユーザーは好みのランディングページを設定できます。

1. Analytics／[!UICONTROL コンポーネント]／[!UICONTROL 環境設定]／[!UICONTROL 一般]に移動します。
1. 希望するランディングページを確認します。

   ![ランディングページを設定](assets/landing-pref.png)

## ランディングページに関する FAQ {#landing-faq}

| 質問 | 回答 |
| --- | --- |
| ベータ版プログラム UI での作業内容は、実稼動用の[!UICONTROL ワークスペース]エクスペリエンスに引き継がれますか。 | はい、ベータ版で行った作業はすべて古い／現在の[!UICONTROL ワークスペース]エクスペリエンスに引き継がれます。 |
| ピン留めできるプロジェクトに最大数はありますか？ | いいえ。固定できるプロジェクトの数に制限はありません。 |
| 管理者は、このランディングページをユーザーに指定できますか？ | いいえ。管理者は、ユーザーの代わりにランディングページを指定することはできません。個々のユーザーは、自分で切り替えをオンにする必要があります。 |
<!-- | Are all reports that currently exist in [!DNL Reports & Analytics] still available? | No, the following reports were phased out, based on overall usage data: <ul><li>Any custom eVars/props/events/classifications<li>My Recommended Reports</li><li>Hourly/Daily/Weekly/Monthly/Quarterly/Yearly unique visitors</li><li>DailyWeekly/Monthly/Quarterly/Yearly unique customers</li><li>Action name depth</li><li>Action name summary</li><li>Add dashboard</li><li>Age</li><li>Audio support</li><li>Billing information</li><li>Clicks to page</li><li>Color depth</li><li>Cookie support</li><li>Cookies</li><li>Connection types</li><li>Creative elements</li><li>Credit card type</li><li>Cross sell</li><li>Custom event funnels</li><li>Custom links</li><li>Customer ID</li><li>Day of week</li><li>Entry action name</li><li>Exit action name</li><li>Exit links</li><li>Fallout</li><li>File downloads</li><li>Find in store</li><li>Full paths</li><li>Gender</li><li>Hit ype VISTA rule</li><li>Image support</li><li>Java</li><li>JavaScript</li><li>JavaScript version</li><li>Manage bookmarks</li><li>Manage dashboards</li><li>Monitor color depth</li><li>Monitor resolutions</li><li>Newsletter signups</li><li>Next action name</li><li>Next action name flow</li><li>Null searches</li><li>Operating system</li><li>Order review</li><li>Page of day</li><li>Pages not found</li><li>Pathfinder</li><li>Path length</li><li>Previous action name</li><li>Previous action name flow</li><li>Product activity</li><li>Product cost</li><li>Product department</li><li>Product inventory category</li><li>Product name</li><li>Product reviews</li><li>Product season</li><li>Product shares</li><li>Product zooms</li><li>Reload</li><li>Searches</li><li>Servers</li><li>Single page visits</li><li>Shipping information</li><li>Site hierarchy</li><li>Social mentions</li><li>Time of day</li><li>Time spent on action name</li><li>Video support</li><li>Visitor state</li></ul> | -->
