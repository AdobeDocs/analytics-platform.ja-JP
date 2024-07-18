---
title: Customer Journey Analytics での接続の管理方法
description: Customer Journey Analytics（Customer Journey Analytics）でExperience Platformデータセットへの接続を管理する方法について説明します。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: c0599526e6a6a9ac9788a4ce29bcf44256b6c4df
workflow-type: tm+mt
source-wordcount: '3277'
ht-degree: 14%

---

# 接続の管理

[1 つ以上の接続を作成または編集 ](/help/connections/create-connection.md) したら、**[!UICONTROL 接続]** で管理できます。 接続を使用すると、次のことができます。

* すべての接続を、所有者、サンドボックス、接続が作成および変更された日時を含め、一覧で表示します。
* 接続を編集します。
* 接続を削除する。
* 接続からデータビューを作成する。
* 接続内のすべてのデータセットを表示する。
* 接続データセットのステータスと取り込みプロセスのステータスを確認します。 例えば、Analysis Workspaceでレポートや分析を開始できるように、データが利用可能なタイミングです。
* 設定ミスに起因するデータの相違を識別します。 欠落している行があるか。その場合、欠落している行とその理由は何か。 接続の設定の誤りが原因でCustomer Journey Analyticsのデータが欠落したのか。
* すべての接続における、取り込まれた行とレポート可能な行の使用状況に関するインサイトを取得します。

[!UICONTROL Connections] には、[[!UICONTROL List]](#list) と [[!UICONTROL Usage]](#usage) の 2 つのインターフェイスがあります。


## リスト

[!UICONTROL  リスト ] インターフェイスは、接続のデフォルトのインターフェイスです。 選択されていない場合は、「**[!UICONTROL リスト]**」タブを選択して、インターフェイスにアクセスします。

![ リスト表示 ](assets/list-view.png)

[!UICONTROL  リスト ] インターフェイスには、使用可能なすべての接続のテーブルが表示されます。 「検索 ![ 検索 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) ボックスを使用して、接続をすばやく検索できます。

テーブルでは、以下の列またはアイコンを使用できます。

| 列またはアイコン | 説明 |
| --- | --- |
| [!UICONTROL 名前] | 接続のわかりやすい名前です。接続の詳細を確認するには、ハイパーリンク名を選択します。 [ 接続の詳細 ](#connection-details) を参照してください。 |
| ![ 情報 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | [!UICONTROL  含まれるデータセット ]、[!UICONTROL  サンドボックス ]、[!UICONTROL  所有者 ] などに関する情報を表示するには、接続名の横にある ![ 情報 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) を選択します。<p>ポップアップウィンドウに詳細が表示されます。 <p><img src="./assets/conn-info.png" alt="接続情報の表示" width="400"/> |
| ![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 接続の [ データビューを作成する ](#create-a-data-view) には、![ データビュー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) を選択します。 このアイコンは、接続に関連付けられているデータビューが既にない場合にのみ表示されます。 |
| ![詳細情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | ![ その他 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択して、次の操作を行います。 <p>![ 編集 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)[ 編集 ](#edit-a-connection) 接続。<p>![ 削除 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)[ 削除 ](#delete-a-connection) 接続。<p>![ データビュー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)[ 新しいデータビューを作成 ](#create-a-data-view)。 接続に追加のデータビューを作成する |
| [!UICONTROL データセット] | 接続に含まれるデータセットへの 1 つ以上のリンクを表示します。 データセットのハイパーリンクを選択して、接続内のデータセットを表示できます。 選択した接続に属するデータセットが他にもある場合は、「**[!UICONTROL +*x* more]**」を選択して **[!UICONTROL 含まれるデータセット]** パネルを表示します。 このパネルには、すべてのデータセットへのリンクと、接続の一部である特定のデータセットを検索するオプションが表示されます。<p><img src="./assets/datasets-included.png" alt="含まれるデータアセット" width="400"/><p>データセット名を選択すると、Experience PlatformUI のデータセットが新しいタブで開きます。 |
| [!UICONTROL サンドボックス] | この接続がデータセットを取得する ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)0}Experience Platformサンドボックス } を示します。 [このサンドボックスは、接続を初めて作成したときに選択されています。変更できません。 |
| [!UICONTROL 所有者] | 接続を作成したユーザー。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータスを表示します。 <p>![ ステータスが緑 ](assets/status-green.svg)）    **[!UICONTROL _x _On]**：新しいデータを読み込むように設定されたデータセットの場合<p>![ ステータスがグレー ](assets/status-gray.svg)   新しいデータをインポートするように設定されていないデータセットの場合は **[!UICONTROL _x Off_]**。 |
| [!UICONTROL 作成日] | 接続が作成されたときのタイムスタンプ。 |
| [!UICONTROL 最終変更日] | 接続が最後に更新されたときのタイムスタンプ。 |
| [!UICONTROL データをバックフィル] | データセット間のバックフィルデータのステータスを表示します。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _バックフィルに失敗しました]**データセット間で失敗したバックフィルの数<p>![ ステータスオレンジ ](assets/status-orange.svg)   **[!UICONTROL _x _件のバックフィル処理]**複数のデータセットをまたいだ処理バックフィルの数<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル]**データセットの完了したバックフィルの数<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** 接続内のデータセットに対してバックフィルが定義されていない場合。 |

表示する列を設定するには、「![ テーブルをカスタマイズ ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」ダイアログを表示する **列設定** を選択します。このダイアログでは、テーブルの列のオン/オフを切り替えることができます。

### 接続の編集

1. 接続名の横にある ![ 詳細 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します
1. コンテキストメニューから ![ 編集 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)**[!UICONTROL 編集]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青いバーから ![ 編集 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)**[!UICONTROL 編集]** を選択します。

接続の編集時には、次の操作を実行できます。

* 新しいデータの読み込みを開始および停止します。
* 接続名を変更する。
* データセットを更新します。
* 接続からデータセットを削除します。

詳しくは、[ 接続の作成または編集 ](create-connection.md) を参照してください。


### 接続の削除 {#connections-delete}

1. 接続名の横にある ![ 詳細 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
1. 「![ 削除 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL 削除]**」を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青いバーから ![ 削除 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL 削除]** を選択します。

接続を削除すると、削除されるデータビューと影響を受けるワークスペースプロジェクトが **[!UICONTROL 接続を削除]** パネルに表示されます。

![ 接続を削除 ](assets/delete-connection.png)

「**[!UICONTROL 続行]**」を選択して、接続を削除します。

接続の削除について詳しくは、[ 削除の影響 ](/help/technotes/deletion.md) を参照してください。


### 接続のデータビューの作成

* 接続に関連付けられているデータビューがない場合：

   1. 接続名の横にある「![ データビューを追加 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)」を選択します。

* 接続に対して 1 つ以上のデータビューが既に作成されている場合：

   1. 接続名の横にある ![ 詳細 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
   1. ![ データビューを追加 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)**[!UICONTROL 新しいデータビューを作成]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青いボタンバーから ![ データビューを追加 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)**[!UICONTROL データビューを作成]** を選択します。

詳しくは、[データビューの作成または編集](/help/data-views/create-dataview.md)を参照してください。

### 接続の詳細 {#connection-detail}

接続の詳細に移動するには、接続テーブルで接続名を選択します。

![ ウィジェットと設定を表示するすべてのデータセット ウィンドウ ](assets/conn-details.png)

接続の詳細インターフェイスには、接続のステータスの詳細ビューが表示されます。 次のことができます。

* 接続データセットのステータスと取り込みプロセスのステータスを確認します。
* レコードのスキップまたは削除の原因となる可能性がある設定の問題を特定します。
* データをレポートに使用できるタイミングを確認します。

| ユーザーインターフェイス | 説明 |
| --- | --- |
| ![ 編集 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)[!UICONTROL  接続を編集 ] | 接続の詳細を編集するには、![ 編集 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 接続を編集]** を選択します。 詳しくは、[ 接続の作成または編集 ](create-connection.md) を参照してください。 |
| データセットセレクター | 接続内の 1 つまたはすべてのデータセットを選択できます。複数のデータセットを選択することはできません。デフォルトは[!UICONTROL すべてのデータセット]です。 |
| 日付範囲セレクター | 開始日、終了日を編集するか、「![ カレンダー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)」を選択して、データ範囲セレクターを開きます。 日付範囲セレクターで、定義済みの期間の 1 つ（例：**[!UICONTROL 過去 6 か月]**）を使用して日付範囲を選択するか、カレンダーを使用して開始日と終了日を選択します。 「**[!UICONTROL 適用]**」を選択して、新しいデータ範囲を適用します。 |
| [!UICONTROL  使用可能なイベントデータのレコード ] | **接続全体について**、レポートに使用できるイベントデータセットの行の合計数。 この数は、カレンダーの設定とは無関係です。データセットセレクターからデータセットを選択するか、テーブル内のデータセットを選択すると、カウントが変わります。 データが追加されると、データがレポートに表示されるまで、1 ～ 2 時間の遅延が発生します。 |
| [!UICONTROL 指標] | 追加、スキップおよび削除されたイベント、ルックアップ、プロファイルデータセットレコード、および追加されたバッチ数の概要を示します **選択したデータセットと日付範囲に関して**。<p>「**[!UICONTROL 詳細を確認]**」を選択して、「**[!UICONTROL スキップされた詳細を確認]** ポップアップを表示します。 ポップアップに、スキップされたレコード数と、すべてのイベントデータセットまたは選択したデータセットの理由が一覧表示されます。<p><img src="./assets/skipped-records.png" width="500"/><p>詳細情報が表示されている ![ 情報 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ポップアップを選択します。 [!UICONTROL  空の訪問者 ID] などの理由でスキップされた場合、ポップアップに EQS （クエリサービスのExperience Platform）のサンプル PSQL が表示されます。[ クエリサービス ](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja) で使用すると、データセット内のスキップされたレコードをクエリできます。 「![ コピー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)**[!UICONTROL EQS 用サンプル PSQL をコピー]**」を選択して、SQL をコピーします。 |
| [!UICONTROL 追加されたレコード] | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に追加された行数を示します。10 分ごとに更新されます。 |
| [!UICONTROL スキップされたレコード] | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間にスキップされた行数を示します。レコードをスキップした理由には、タイムスタンプの欠落、ユーザー ID の欠落または無効なユーザー ID などがあります。 10 分ごとに更新されます。 <p>無効なユーザー ID （`undefined`、`00000000`、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL  ユーザー ID] の数字と文字の任意の組み合わせ）は、特定のユーザーまたは人物に関連付けることのできない ID です。 これらの行はシステムに取り込むことができないので、取り込みやレポートの際にエラーが発生しやすくなります。 無効なユーザー ID を修正する方法として、次の 3 つのオプションがあります。<ul><li>[ ステッチ ](/help/stitching/overview.md) を使用して、未定義またはすべてがゼロのユーザー ID の代わりに有効なユーザー ID を生成する。</li><li>ユーザー ID を空白にする。この ID は取り込み時にスキップされます（ユーザー ID が無効またはすべてゼロとなっているよりも望ましい）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| [!UICONTROL  レコード ] 削除されました | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に削除された行数を示します。例えば、[!DNL Experience Platform] 内のデータセットが削除された可能性があります。 10 分ごとに更新されます。<p>場合によっては、ステッチやルックアップデータセットの更新など、置き換えられたレコードがこの値に含まれることもあります。 次の例をご覧ください。</p><ul><li>1 つのレコードを XDM 個人プロファイルデータセットにアップロードし、CJA はこれをプロファイルルックアップデータとして取り込むように設定します。 接続詳細では、このデータセットには 1 件のレコードが追加されて表示されます。</li><li>元のレコードの複製を、2 つのレコードを含む同じ AEP データセットにアップロードします。 CJA は、追加のレコードをプロファイルルックアップデータセットから取り込みます。 その人物 ID の接続にプロファイルレコードが既に取り込まれているのを確認すると、CJA は以前のバージョンを削除して、新しいプロファイルデータを追加します。 接続詳細では、CJA は取り込まれたユーザー ID の最新のプロファイルルックアップデータのみを保持するので、このアクションは、追加されたレコード 1 件と削除されたレコード 1 件を表します。</li><li>AEP データセットには、合計で同じになる 2 つのレコードが含まれています。 個別に、CJA 接続の詳細には、取り込んだデータのステータス（このプロファイルデータセットに対して追加された 2 つのレコードと削除された 1 つのレコード）が表示されます。 </li></ul> |
| ![ 検索 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)_データセット名または ID を検索_ | データセット検索フィールド。 データセット名または [!UICONTROL  データセット ID] でデータセットテーブルを検索できます。 |
| [!UICONTROL  データセットテーブル ] | 接続に含まれるデータセットを表示します。 |
| [!UICONTROL データセット] | 接続に含まれるデータセットの名前を表示します。 ハイパーリンクを選択すると、Experience PlatformUI の新しいタブでデータセットが開きます。 行またはチェックボックスを選択して、選択したデータセットの詳細のみを表示できます。 |
| [!UICONTROL データセット ID] | Experience Platformによって自動生成されます。 |
| [!UICONTROL 追加されたレコード] | 選択した時間間隔で接続に追加されたデータセットレコード （行）の数。 |
| [!UICONTROL スキップされたレコード] | 選択した時間間隔で、接続のデータ転送中にスキップされたデータセットレコード （行）の数。 |
| [!UICONTROL 削除されたレコード] | 選択した時間間隔で接続から削除されたデータセットレコード （行）の数。 |
| [!UICONTROL 追加されたバッチ] | 接続に追加されたデータセットバッチの数。 |
| [!UICONTROL 前回追加した日時] | 接続に追加されたデータセットからの最新のバッチのタイムスタンプ。 |
| [!UICONTROL データソースタイプ] | データセットのソースタイプ。 接続を作成する際に、ソースタイプを定義します。 |
| [!UICONTROL データセットタイプ] | このデータセットのデータセットタイプ。 タイプは、[!UICONTROL  イベント ]、[!UICONTROL  ルックアップ ] または [!UICONTROL  プロファイル ] です。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#configure-dataset) |
| スキーマ | データセットのベースとなるExperience Platformスキーマ。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータスを表示します。 <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _On]**新しいデータを読み込むようにデータセットが設定されている場合、および<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]** データセットが新しいデータインポートをインポートしないように設定されている場合。 |
| [!UICONTROL  データを変換 ] | 適用可能な B2B ルックアップデータセットの変換ステータスを表示します。 詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _On]**変換が有効になっている該当するデータセットの場合、 <p>![ ステータスがグレー ](assets/status-gray.svg)   変換が有効になっていない該当するデータセットの **[!UICONTROL _x オフ_]**<p>他のすべてのデータセットに対して **[!UICONTROL なし]**、変換には適用されません。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータスを表示します。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _失敗したバックフィル]**失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _件のバックフィル処理]**件のバックフィル数の処理<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル数]**完了したバックフィル数、<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータスを表示します。 <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _オン]**新しいデータを読み込むようにデータセットが設定されている場合。<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]** 新しいデータを読み込まないようにデータセットが設定されている場合。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータスを表示します。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _失敗したバックフィル]**失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _件のバックフィル処理]**件のバックフィル数の処理<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル数]**完了したバックフィル数、<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合。 |

>[!IMPORTANT]
>
>2021 年 8 月 13 日（PT）より前に取り込まれたデータは、[!UICONTROL Connections] インターフェイスには反映されません。

#### 接続パネル

データセットテーブルでデータセットが選択されていない場合、接続インターフェイスの右側のパネルに接続オプションと詳細が表示されます。

| オプション/詳細 | 説明 |
| --- | --- |
| ![ 更新 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL  更新 ] | 接続を更新し、最近追加したレコードを反映するには、「![ 更新 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)**[!UICONTROL 更新]**」を選択します。 |
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL Delete]** | [ 削除 ](#delete-a-connection) この接続。 |
| ![ データビューを追加 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)**[!UICONTROL データビューを作成]** | この接続に基づいて ](#create-a-data-view) データビューを作成 [ します。 詳しくは、[ データビュー ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja) を参照してください。 |
| [!UICONTROL 接続名] | 接続のわかりやすい名前を表示します。 |
| [!UICONTROL 接続の説明] | この接続の目的を説明する詳細な説明を表示します。 |
| [!UICONTROL サンドボックス] | この接続がデータセットを取得する ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)0}Experience Platformサンドボックス。このサンドボックスは、接続を初めて作成したときに選択されています。 [変更できません。 |
| [!UICONTROL 接続 ID] | この ID は、Experience Platformで生成されます。 ![ コピー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) を使用して、ID をコピーできます。 |
| [!UICONTROL 接続を使用するデータビュー] | この接続を使用するすべてのデータビューを表示します。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータスを表示します。 <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _On]**新しいデータをインポートするように設定されているデータセットの数<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]**：新しいデータの読み込みがオフになっているデータセットの数。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータスを表示します。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _バックフィルに失敗しました]**データセット間で失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _件のバックフィル処理]**複数のデータセットをまたいだ処理バックフィルの数<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル]**データセットの完了したバックフィルの数<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** 接続内のデータセットに対してバックフィルが定義されていない場合。 |
| データを変換 | 適用可能な B2B ルックアップデータセットの変換ステータスを表示します。 詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ ステータスが緑 ](assets/status-green.svg)   変換が有効になっているデータセットの数に対して **[!UICONTROL _x _On]**。 |
| [!UICONTROL 作成者] | 接続を作成したユーザーの名前を表示します。 |
| [!UICONTROL 最終変更日] | 接続に対する最後の変更のタイムスタンプを表示します。 |
| [!UICONTROL 最終変更者] | 接続を最後に変更した人物を表示します。 |

#### データセットパネル

データセットテーブルでデータセットが選択されていると、接続インターフェイスの右側にあるパネルに、選択したデータセットの詳細が表示されます。

| 詳細 | 説明 |
| --- | --- |
| [!UICONTROL ユーザー ID] | Experience Platform 内のデータセットのスキーマで定義された ID を表示します。この ID は、接続の作成時に選択したユーザー ID です。 異なる ID のデータセットを含む接続を作成すると、レポートにはそれが反映されます。 データセットを結合するには、データセット間で同じユーザー ID を使用する必要があります。 |
| [!UICONTROL キー] | ルックアップデータセットに指定したキーを表示します。 |
| [!UICONTROL 一致するキー] | ルックアップデータセットに指定した、一致するキーを表示します。 |
| [!UICONTROL タイムスタンプ] | イベントデータセットに定義されたタイムスタンプを表示します。 |
| [!UICONTROL 使用可能なレコード] | カレンダーで選択した特定の期間に、このデータセットに対して取り込まれた行の合計数を表示します。 データが追加されると、レポートに表示されるデータの取得に遅延は発生しません。ただし、新しい接続を作成する場合は、[ 待ち時間 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#3-getting-data-into-customer-journey-analytics) が発生します。 |
| [!UICONTROL 追加されたレコード] | 選択した期間に追加された行数を表示します。 |
| [!UICONTROL 削除されたレコード] | 選択した期間に削除されたレコードの数を表示します。 |
| [!UICONTROL 追加されたバッチ] | このデータセットに追加されたデータバッチの数を表示します。 |
| [!UICONTROL スキップされたレコード] | 選択した期間の取り込み中にスキップされた行数を表示します。<p>レコードをスキップした理由には、タイムスタンプの欠落、ユーザー ID の欠落または無効なユーザー ID などがあります。 10 分ごとに更新されます。<p>無効なユーザー ID （`undefined`、`00000000`、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL  ユーザー ID] の数字と文字の任意の組み合わせ）は、特定のユーザーまたは人物に関連付けることのできない ID です。 これらの行はシステムに取り込むことができないので、取り込みやレポートの際にエラーが発生しやすくなります。 無効なユーザー ID を修正する方法として、次の 3 つのオプションがあります。<ul><li>[ ステッチ ](/help/stitching/overview.md) を使用して、未定義またはすべてがゼロのユーザー ID の代わりに有効なユーザー ID を生成する。</li><li>ユーザー ID を空白にする。この ID は取り込み中にスキップされます（ユーザー ID が無効またはすべてゼロとなっているよりも望ましい）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| [!UICONTROL 前回追加した日時] | 最後のバッチが追加された日時を表示します。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータスを表示します。 <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _オン]**新しいデータを読み込むようにデータセットが設定されている場合。<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]** 新しいデータを読み込まないようにデータセットが設定されている場合。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータスを表示します。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _失敗したバックフィル]**失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _件のバックフィル処理]**件のバックフィル数の処理<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル数]**完了したバックフィル数、<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合。<p>データセットの過去のバックフィルの概要を示すダイアログを表示するには、次を選択します <img src="./assets/pastbackfill.svg" alt="過去のバックフィル" width="15"/> **[!UICONTROL 過去のバックフィル]**。 |
| [!UICONTROL データソースタイプ] | データセットを接続に追加する際に定義されるデータソースタイプ。 |
| [!UICONTROL データセットタイプ] | [!UICONTROL イベント]、[!UICONTROL ルックアップ]、[!UICONTROL プロファイル]のいずれかです。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#configure-dataset) |
| [!UICONTROL スキーマ] | このデータセットのベースとなるExperience Platformスキーマを示します。 |
| [!UICONTROL データセット ID] | このデータセット ID は、Experience Platformで生成されます。 |


## 用途

[!UICONTROL  使用状況 ] インターフェイスには、取り込んだ行とレポート可能な行の使用状況がすべての接続で表示されます。 このインターフェイスを使用すると、Customer Journey Analyticsの使用状況が契約上の合意内容に準拠しているかどうかを判断できます。 使用状況 UI を使用すると、モニタリングの目的に加えて、Customer Journey Analyticsライセンスの更新をより適切に計画できます。

Customer Journey Analyticsの使用状況を監視する時間範囲（過去 6 か月、年初から今日、または過去 2 年）と間隔（月または四半期）を選択できます。 インターフェイスは、次の 2 つのセクションに分かれています。

* 取り込み済み行：すべての CJA 接続でイベントデータセットから取り込まれ/送信された行の総数（取り込み時にスキップされたレコードを含む）
* レポート可能行：すべての CJA 接続にわたるすべてのイベントデータを含むレポート可能行の合計

![usage-view](assets/usage-view.png)

**[!UICONTROL 使用状況]** タブを選択して、インターフェイスにアクセスします。

### 使用状況のレポート

1. **[!UICONTROL 時間範囲]** を選択します。 **[!UICONTROL 過去 6 か月]**、**[!UICONTROL 年累計]**、または **[!UICONTROL 過去 2 年]** から選択できます。
1. **[!UICONTROL 間隔]** を選択します。 **[!UICONTROL 毎月]** または **[!UICONTROL 四半期]** から選択できます。

[!UICONTROL  取り込まれた行 ] の場合：

* 月の 2 日ごとに更新されたすべての接続のすべてのイベントデータを含んだ、取り込まれた行の合計がパネルに表示されます。 パネル内で以下を行います。
   * ボックスには、先月に取り込んだ行の数と、先月からの変化が % で（▲または▼で示されます）表示されます。
   * 折れ線グラフに、◼︎[!UICONTROL  毎月取り込まれた行 ] が表示されます。<br/>1 か月に取得した月の行数を表示するポップアップを表示するには、折れ線グラフの任意のデータポイントにポインタを合わせます。


[!UICONTROL  レポート可能な行 ] について：

* 月の 2 日ごとに更新されたすべての接続にわたるすべてのイベントデータを含んだ、レポート可能な行の合計がパネルに表示されます。 パネル内で以下を行います。
   * レポート可能な行の累積合計数がボックスに表示されます。
   * ボックスには、先月のレポート可能な行の合計数と、先月からの変化が % で表示されます（▲または▼で示されます）。
   * 折れ線グラフには、◼︎[!UICONTROL  月別レポート可能行 ] が表示されます。<br/> 特定の月についてレポート可能な累積行の数を表示するポップアップを表示するには、折れ線グラフの任意のデータポイントにポインタを合わせます。
   * 折れ線グラフに、◼︎[!UICONTROL  レポート可能な累積行 ] が表示されます。<br/>1 か月についてレポート可能な月の行数を表示するポップアップを表示するには、折れ線グラフの任意のデータポイントにポインタを合わせます。


>[!MORELIKETHIS]
>
>[ 接続設定の表示、トラブルシューティング、変更 ](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html) チュートリアル
