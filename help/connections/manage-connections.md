---
title: Customer Journey Analytics での接続の管理方法
description: Customer Journey Analytics（Customer Journey Analytics）でExperience Platformデータセットへの接続を管理する方法について説明します。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '4023'
ht-degree: 12%

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
| [!UICONTROL データセット] | 接続に含まれるデータセットへの 1 つ以上のリンク。 データセットのハイパーリンクを選択して、接続内のデータセットを表示できます。 選択した接続に属するデータセットが他にもある場合は、「**[!UICONTROL +*x* more]**」を選択して **[!UICONTROL 含まれるデータセット]** パネルを表示します。 このパネルには、すべてのデータセットへのリンクと、接続の一部である特定のデータセットを検索するオプションが表示されます。<p><img src="./assets/datasets-included.png" alt="含まれるデータアセット" width="400"/><p>データセット名を選択すると、Experience PlatformUI のデータセットが新しいタブで開きます。 |
| [!UICONTROL サンドボックス] | このExperience Platformがデータセットを取得する ](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)0} 接続サンドボックス。 [このサンドボックスは、接続を初めて作成したときに選択されています。変更できません。 |
| [!UICONTROL 所有者] | 接続を作成したユーザー。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータス： <p>![ ステータスが緑 ](assets/status-green.svg)）    **[!UICONTROL _x _On]**：新しいデータを読み込むように設定されたデータセットの場合<p>![ ステータスがグレー ](assets/status-gray.svg)   新しいデータをインポートするように設定されていないデータセットの場合は **[!UICONTROL _x Off_]**。 |
| [!UICONTROL 作成日] | 接続が作成されたときのタイムスタンプ。 |
| [!UICONTROL 最終変更日] | 接続が最後に更新されたときのタイムスタンプ。 |
| [!UICONTROL データをバックフィル] | データセット間でのバックフィルデータのステータス。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _バックフィルに失敗しました]**データセット間で失敗したバックフィルの数<p>![ ステータスオレンジ ](assets/status-orange.svg)   **[!UICONTROL _x _件のバックフィル処理]**複数のデータセットをまたいだ処理バックフィルの数<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル]**データセットの完了したバックフィルの数<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** 接続内のデータセットに対してバックフィルが定義されていない場合。 |

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
| 日付範囲セレクター | 開始日または終了日を編集するか、「![ カレンダー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)」を選択して日付範囲セレクターを開きます。 日付範囲セレクターで、定義済みの期間の 1 つ（例：**[!UICONTROL 過去 6 か月]**）を使用して日付範囲を選択するか、カレンダーを使用して開始日と終了日を選択します。 「**[!UICONTROL 適用]**」を選択して、新しい日付範囲を適用します。 |
| [!UICONTROL  使用可能なイベントデータのレコード ] | **接続全体について**、レポートに使用できるイベントデータセットの行の合計数。 この数は、カレンダーの設定とは無関係です。データセットセレクターからデータセットを選択するか、テーブル内のデータセットを選択すると、カウントが変わります。 データが追加されると、データがレポートに表示されるまで、1 ～ 2 時間の遅延が発生します。 |
| [!UICONTROL 指標] | 追加、スキップ、および削除されたイベント、ルックアップ、プロファイル、および概要データセットレコードと、追加されたバッチ数を要約します。 これらの指標は、**選択したデータセットと日付範囲** に基づいています。<p>「**[!UICONTROL 詳細を確認]**」を選択して、「**[!UICONTROL スキップされた詳細を確認]** ポップアップを表示します。 ポップアップに、スキップされたレコード数と、すべてのイベントデータセットまたは選択したデータセットの理由が一覧表示されます。<p><img src="./assets/skipped-records.png" width="500"/><p>詳細情報が表示されている ![ 情報 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ポップアップを選択します。 [!UICONTROL  空の訪問者 ID] などの理由でスキップされた場合、ポップアップに EQS （クエリサービスのExperience Platform）のサンプル PSQL が表示されます。[ クエリサービス ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home) で使用すると、データセット内のスキップされたレコードをクエリできます。 「![ コピー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)**[!UICONTROL EQS 用サンプル PSQL をコピー]**」を選択して、SQL をコピーします。 |
| [!UICONTROL 追加されたレコード] | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に追加された行数を示します。10 分ごとに更新されます。 |
| [!UICONTROL スキップされたレコード] | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間にスキップされた行数を示します。レコードをスキップした理由には、タイムスタンプの欠落、ユーザー ID の欠落または無効なユーザー ID などがあります。 10 分ごとに更新されます。 <p>無効なユーザー ID （`undefined`、`00000000`、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL  ユーザー ID] の数字と文字の任意の組み合わせ）は、特定のユーザーまたは人物に関連付けることのできない ID です。 これらの行はシステムに取り込むことができないので、取り込みやレポートの際にエラーが発生しやすくなります。 無効なユーザー ID を修正する方法として、次の 3 つのオプションがあります。<ul><li>[ ステッチ ](/help/stitching/overview.md) を使用して、未定義またはすべてがゼロのユーザー ID の代わりに有効なユーザー ID を生成する。</li><li>ユーザー ID を空白にする。この ID は取り込み時にスキップされます（ユーザー ID が無効またはすべてゼロとなっているよりも望ましい）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| [!UICONTROL  レコード ] 削除されました | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に削除された行数を示します。例えば、[!DNL Experience Platform] 内のデータセットが削除された可能性があります。 10 分ごとに更新されます。<p>場合によっては、ステッチやルックアップデータセットの更新など、置き換えられたレコードがこの値に含まれることもあります。 次の例をご覧ください。</p><ul><li>1 つのレコードを XDM 個人プロファイルデータセットにアップロードし、このCustomer Journey Analyticsはプロファイルルックアップデータとして取り込むように設定されています。 接続詳細では、このデータセットには 1 件のレコードが追加されて表示されます。</li><li>元のレコードの複製を、2 つのレコードを含む同じ AEP データセットにアップロードします。 Customer Journey Analyticsは、プロファイルルックアップデータセットから追加のレコードを取り込みます。 そのユーザー ID の接続にプロファイルレコードが既に取り込まれているのを確認すると、Customer Journey Analyticsは以前のバージョンを削除し、新しいプロファイルデータを追加します。 Customer Journey Analyticsでは、取り込まれたユーザー ID の最新のプロファイル参照データのみが保持されるので、接続詳細では、このアクションは、追加されたレコード 1 件と削除されたレコード 1 件を表します。</li><li>AEP データセットには、合計で同じになる 2 つのレコードが含まれています。 個別に、Customer Journey Analytics接続の詳細には、取り込んだデータのステータス（このプロファイルデータセットに対して追加された 2 つのレコードと削除された 1 つのレコード）が表示されます。 </li></ul> |
| ![ 検索 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)_データセット名または ID を検索_ | データセット検索フィールド。 データセット名または [!UICONTROL  データセット ID] でデータセットテーブルを検索できます。 |
| [!UICONTROL  データセットテーブル ] | 接続に含まれるデータセットです。 |
| [!UICONTROL データセット] | 接続に含まれるデータセットの名前。 ハイパーリンクを選択すると、Experience PlatformUI の新しいタブでデータセットが開きます。 行またはチェックボックスを選択して、選択したデータセットの詳細のみを表示できます。 |
| [!UICONTROL データセット ID] | Experience Platformによって自動生成されます。 |
| [!UICONTROL 追加されたレコード] | 選択した時間間隔で接続に追加されたデータセットレコード （行）の数。 |
| [!UICONTROL スキップされたレコード] | 選択した時間間隔で、接続のデータ転送中にスキップされたデータセットレコード （行）の数。 |
| [!UICONTROL 削除されたレコード] | 選択した時間間隔で接続から削除されたデータセットレコード （行）の数。 |
| [!UICONTROL 追加されたバッチ] | 接続に追加されたデータセットバッチの数。 |
| [!UICONTROL 前回追加した日時] | 接続に追加されたデータセットからの最新のバッチのタイムスタンプ。 |
| [!UICONTROL データソースタイプ] | データセットのソースタイプ。 接続を作成する際に、ソースタイプを定義します。 |
| [!UICONTROL データセットタイプ] | このデータセットのデータセットタイプ。 タイプは、[!UICONTROL  イベント ]、[!UICONTROL  プロファイル ]、[!UICONTROL  ルックアップ ]、[!UICONTROL  概要 ] のいずれかです。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection) |
| スキーマ | データセットのベースとなるExperience Platformスキーマ。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータス： <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _On]**新しいデータを読み込むようにデータセットが設定されている場合、および<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]** 新しいデータインポートをインポートしないようにデータセットが設定されている場合。 |
| [!UICONTROL  データを変換 ] | 適用可能な B2B ルックアップデータセットの変換ステータス。 詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _On]**変換が有効になっている該当するデータセットの場合、 <p>![ ステータスがグレー ](assets/status-gray.svg)   変換が有効になっていない該当するデータセットの **[!UICONTROL _x オフ_]**<p>他のすべてのデータセットに対して **[!UICONTROL なし]**、変換には適用されません。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータス。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _失敗したバックフィル]**失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _処理中のバックフィル]**処理のバックフィル数<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル数]**完了したバックフィル数、<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータス： <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _オン]**新しいデータを読み込むようにデータセットが設定されている場合。<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]** 新しいデータを読み込まないようにデータセットが設定されている場合。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータス。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _失敗したバックフィル]**失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _処理中のバックフィル]**処理のバックフィル数<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル数]**完了したバックフィル数、<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合。 |

>[!IMPORTANT]
>
>2021 年 8 月 13 日（PT）より前に取り込まれたデータは、[!UICONTROL Connections] インターフェイスには反映されません。

#### 接続パネル

データセットテーブルでデータセットが選択されていない場合、接続インターフェイスの右側のパネルに接続オプションと詳細が表示されます。

| オプション | 説明 |
| --- | --- |
| ![ 更新 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL  更新 ] | 接続を更新し、最近追加したレコードを反映するには、「![ 更新 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)**[!UICONTROL 更新]**」を選択します。 |
| ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)、**[!UICONTROL 削除]** | [ 削除 ](#delete-a-connection) この接続。 |
| ![ データビューを追加 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)**[!UICONTROL データビューを作成]** | この接続に基づいて ](#create-a-data-view) データビューを作成 [ します。 詳しくは、[ データビュー ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/data-views) を参照してください。 |
| [!UICONTROL 接続名] | 接続のわかりやすい名前。 |
| [!UICONTROL 接続の説明] | この接続の目的を説明する、より詳細な説明。 |
| [!UICONTROL サンドボックス] | この接続がデータセットを取得する ](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)0}Experience Platformサンドボックス。このサンドボックスは、接続を初めて作成したときに選択されています。 [変更できません。 |
| [!UICONTROL 接続 ID] | この ID は、Experience Platformで生成されます。 ![ コピー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) を使用して、ID をコピーできます。 |
| [!UICONTROL 接続を使用するデータビュー] | この接続を使用するすべてのデータビューを表示します。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータス： <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _On]**新しいデータをインポートするように設定されているデータセットの数<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]**：新しいデータの読み込みがオフになっているデータセットの数。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータス。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _バックフィルに失敗しました]**データセット間で失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _件のバックフィル処理]**複数のデータセットをまたいだ処理バックフィルの数<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル]**データセットの完了したバックフィルの数<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** 接続内のデータセットに対してバックフィルが定義されていない場合。 |
| データを変換 | 適用可能な B2B ルックアップデータセットの変換ステータス。 詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ ステータスが緑 ](assets/status-green.svg)   変換が有効になっているデータセットの数に対して **[!UICONTROL _x _On]**。 |
| [!UICONTROL 作成者] | 接続を作成したユーザーの名前。 |
| [!UICONTROL 最終変更日] | 接続に対する最後の変更のタイムスタンプ。 |
| [!UICONTROL 最終変更者] | 接続を最後に変更した人物。 |

#### データセットパネル

データセットテーブルでデータセットが選択されていると、接続インターフェイスの右側にあるパネルに、選択したデータセットの詳細が表示されます。

| 詳細 | 説明 |
| --- | --- |
| [!UICONTROL ユーザー ID] | Experience Platformのデータセットスキーマで定義された ID。 この ID は、接続の作成時に選択したユーザー ID です。 異なる ID のデータセットを含む接続を作成すると、レポートにはそれが反映されます。 データセットを結合するには、データセット間で同じユーザー ID を使用する必要があります。 |
| [!UICONTROL キー] | ルックアップデータセットに指定したキー。 |
| [!UICONTROL 一致するキー] | ルックアップデータセットに指定した、一致するキー。 |
| [!UICONTROL タイムスタンプ] | イベントデータセットに定義されたタイムスタンプ。 |
| [!UICONTROL 使用可能なレコード] | カレンダーで選択した特定の期間に、このデータセットに対して取り込まれた行の合計数です。 データが追加されると、レポートに表示されるデータの取得に遅延は発生しません。ただし、新しい接続を作成する場合は、[ 待ち時間 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq) が発生します。 |
| [!UICONTROL 追加されたレコード] | 選択した期間に追加された行数。 |
| [!UICONTROL 削除されたレコード] | 選択した期間に削除されたレコードの数。 |
| [!UICONTROL 追加されたバッチ] | このデータセットに追加されたデータバッチの数。 |
| [!UICONTROL スキップされたレコード] | 選択した期間の取り込み中にスキップされた行数。<p>レコードをスキップした理由には、タイムスタンプの欠落、ユーザー ID の欠落または無効なユーザー ID などがあります。 10 分ごとに更新されます。<p>無効なユーザー ID （`undefined`、`00000000`、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL  ユーザー ID] の数字と文字の任意の組み合わせ）は、特定のユーザーまたは人物に関連付けることのできない ID です。 これらの行はシステムに取り込むことができないので、取り込みやレポートの際にエラーが発生しやすくなります。 無効なユーザー ID を修正する方法として、次の 3 つのオプションがあります。<ul><li>[ ステッチ ](/help/stitching/overview.md) を使用して、未定義またはすべてがゼロのユーザー ID の代わりに有効なユーザー ID を生成する。</li><li>ユーザー ID を空白にする。この ID は取り込み中にスキップされます（ユーザー ID が無効またはすべてゼロとなっているよりも望ましい）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| [!UICONTROL 前回追加した日時] | 前回バッチが追加されたタイムスタンプ。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータの読み込みステータス： <p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _オン]**新しいデータを読み込むようにデータセットが設定されている場合。<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _x オフ_]** 新しいデータを読み込まないようにデータセットが設定されている場合。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータス。<p>![ ステータスが赤 ](assets/status-red.svg)   **[!UICONTROL _x _失敗したバックフィル]**失敗したバックフィルの数<p>![ ステータスが赤 ](assets/status-orange.svg)   **[!UICONTROL _x _処理中のバックフィル]**処理のバックフィル数<p>![ ステータスが緑 ](assets/status-green.svg)   **[!UICONTROL _x _完了したバックフィル数]**完了したバックフィル数、<p>![ ステータスがグレー ](assets/status-gray.svg)   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合。<p>データセットの過去のバックフィルの概要を示すダイアログを表示するには、次を選択します <img src="./assets/pastbackfill.svg" alt="過去のバックフィル" width="15"/> **[!UICONTROL 過去のバックフィル]**。 |
| [!UICONTROL データソースタイプ] | データセットを接続に追加する際に定義されるデータソースタイプ。 |
| [!UICONTROL データセットタイプ] | [!UICONTROL  イベント ]、[!UICONTROL  プロファイル ]、[!UICONTROL  ルックアップ ]、[!UICONTROL  概要 ] のいずれかです。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL スキーマ] | このデータセットのベースとなるExperience Platformスキーマ。 |
| [!UICONTROL データセット ID] | このデータセット ID は、Experience Platformで生成されます。 |


## 用途 {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="主要な使用状況指標"
>abstract="コアおよび履歴レポート可能行の月別および合計データを提供します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="月別の取り込まれた行数"
>abstract="システムに毎月追加される合計レコード数を測定して、データの増加と取り込み率に関するインサイトを提供します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="月別のレポート可能な行数"
>abstract="レポートに使用できる行数をトラッキングします。 レポート可能な行は、取り込まれた行から、取り込み中にスキップおよび削除された行を引いたものです。 レポート可能行は、請求とデータ使用の主要な指標として機能します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="詳細な分類。"
>abstract="データの CSV ファイルをダウンロードするオプションを使用して、接続別、データセット別、サンドボックス別およびタグ別に詳細な指標を表示できます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="その他のデータセット"
>abstract="2024 年 9 月より前の数か月間は、データがデータセットレベルで収集され、わかりやすくするために *その他のデータセット* として表示されていました。 2024 年 9 月以降、データはきめ細かいデータセットレベルで収集され、*その他のデータセット* は表示されなくなります。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="不明なデータセットまたは接続"
>abstract="不明なデータセットまたは接続が、その ID を使用して表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="データを使用できません"
>abstract="2024 年 9 月より前の履歴データは、システム制限により利用できません。 指標は、2024 年 9 月以降に収集され、表示されます。 グラフはタイムラインの過去 18 か月を表示し、データが利用可能になると将来のデータが表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="コアのレポート可能な行数"
>abstract="過去 13 か月間に使用可能な行の合計数を表示します。 例えば、2024 年 2 月 1 日の場合、この数は、2023 年 1 月から 2024 年 1 月のイベントタイムスタンプで使用可能な合計行を示します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="履歴のレポート可能な行数"
>abstract="13 か月を超える期間で使用可能な行の合計数を表示します。 例えば、2024 年 2 月 1 日の場合、この数は、2023 年 1 月より古いイベントタイムスタンプで使用可能な合計行を示します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="主要な使用状況指標"
>abstract="コアおよび履歴レポート可能行の月別および合計データを提供します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="月別の取り込まれた行数"
>abstract="システムに毎月追加される合計レコード数を測定して、データの増加と取り込み率に関するインサイトを提供します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="月別のレポート可能な行数"
>abstract="レポートに使用できる行数をトラッキングします。 レポート可能な行は、取り込まれた行から、取り込み中にスキップおよび削除された行を引いたものです。 レポート可能行は、請求とデータ使用の主要な指標として機能します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="詳細な分類。"
>abstract="データの CSV ファイルをダウンロードするオプションを使用して、接続別、データセット別、サンドボックス別およびタグ別に詳細な指標を表示できます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="その他のデータセット"
>abstract="2024 年 9 月より前の数か月間は、データがデータセットレベルで収集され、わかりやすくするために *その他のデータセット* として表示されていました。 2024 年 9 月以降、データはきめ細かいデータセットレベルで収集され、*その他のデータセット* は表示されなくなります。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="不明なデータセットまたは接続"
>abstract="不明なデータセットまたは接続が、その ID を使用して表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="データを使用できません"
>abstract="2024 年 9 月より前の履歴データは、システム制限により利用できません。 指標は、2024 年 9 月以降に収集され、表示されます。 グラフはタイムラインの過去 18 か月を表示し、データが利用可能になると将来のデータが表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="コアのレポート可能な行数"
>abstract="過去 13 か月間に使用可能な行の合計数を表示します。 例えば、2024 年 2 月 1 日の場合、この数は、2023 年 1 月から 2024 年 1 月のイベントタイムスタンプで使用可能な合計行を示します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="履歴のレポート可能な行数"
>abstract="13 か月を超える期間で使用可能な行の合計数を表示します。 例えば、2024 年 2 月 1 日の場合、この数は、2023 年 1 月より古いイベントタイムスタンプで使用可能な合計行を示します。"

<!-- markdownlint-enable MD034 -->


[!UICONTROL  使用状況 ] インターフェイスには、取り込んだ行とレポート可能な行の使用状況がすべての接続で表示されます。 選択されていない場合は、「**[!UICONTROL 使用状況]**」タブを選択してインターフェイスにアクセスします。

このインターフェイスを使用すると、Customer Journey Analyticsの使用状況が契約上の合意内容に準拠しているかどうかを判断できます。 使用状況インターフェイスでは、モニタリングの目的に加え、Customer Journey Analyticsライセンスの更新を計画することもできます。

使用状況インターフェイスでは、次の指標を使用します

| Metric name | 説明 |
|---|---|
| 履歴のレポート可能な行数 | 13 か月を超える期間の行数。 |
| コアのレポート可能な行数 | 過去 13 か月間の行数。 |
| 取り込まれた行数 | 特定の期間に取り込まれた行数。 |
| レポート可能な行数 | 特定の期間の接続の一部として持つデータの行数。 |
| 累積行 | 特定の月までに取り込まれた行数。 |

>[!NOTE]
>
>コアレコード、履歴レコードおよび合計レコードについて、2024 年 7 月からデータが収集されます。 以前の履歴データについては、担当のアカウントマネージャーにお問い合わせください。
>



使用状況インターフェイスは、次の 2 つのパネルで構成されます。

* **[!UICONTROL 主要な使用状況指標]** パネル：レポート可能なコアデータと履歴データの行が表示されます。 また、このパネルでは、コアと履歴の両方のデータ行について、前月と比較した変更率も追跡します。

  パネルがビジュアライゼーションに表示されます。

   * **[!UICONTROL コアデータのレポート可能な行]**。

     過去 13 ヶ月間にレポート可能な行の数。 概要番号は、先月（例：2024 年 12 月）のレポート可能なコア行の数（例：741M）です。

   * **[!UICONTROL 履歴データレポート可能な行]**。

     13 か月を超える期間のレポート可能な行の数。 概要番号は、先月（例：2024 年 12 月）のレポート可能な履歴行の数（例：127M）です。

  ビジュアライゼーション内の積み重ね棒の上にマウスポインターを置くと、棒の特定の部分の行数がポップアップに表示されます（例：）。


  ![ 主要な使用状況指標 ](assets/usage-key-usage-metrics.png)

* 以下の 3 つのサブパネルを表示する組み合わせパネル。

+++ 取り込まれた行数

  **[!UICONTROL 取り込まれた行]** サブパネルは、毎月システムに追加されたレコードの合計数を測定し、データの増加と取り込み率に関するインサイトを提供します。 サブパネルには、取り込まれた当月の合計行の概要と前月からの変化が表示されます。

  ![ 取り込まれた行 ](assets/usage-ingested-rows.png)

  ビジュアライゼーションのデータポイントにポインタを合わせると、詳細を含むポップアップが表示されます。

+++

+++ レポート可能な行数

  **[!UICONTROL レポート可能な行]** ビジュアライゼーションは、取り込まれた行からスキップされた行と削除された行を減算することで、レポートに使用できる行数を追跡し、請求とデータ使用の主要な指標として機能します。 サブパネルには、次の 2 つの概要が表示されます。

   * **[!UICONTROL 先月の合計]**：今月までのレポート可能な行の合計の概要。
   * **[!UICONTROL 今月]**：今月のレポート可能行の合計と先月の変化の概要。

  ![ レポート可能な行 ](assets/usage-reportable-rows.png)

  ビジュアライゼーションのデータポイントにポインタを合わせると、詳細を含むポップアップが表示されます。

+++

+++ 詳細分類

  **[!UICONTROL 詳細分類]** テーブルを使用すると、接続、データセット、サンドボックス、タグ別に詳細な指標を表示できます。 データセット名はレポート期間中に変更できるので、データセットは名前ではなく ID を使用してレポートされます。 不明なデータセットまたは接続が、ID を使用してレポートされます。

  2024 年 9 月より前の数か月間は、データがデータセットレベルで収集され、わかりやすくするために [!UICONTROL  その他のデータセット ] として表示されていました。 2024 年 9 月以降、データはきめ細かいデータセットレベルで収集され、[!UICONTROL  その他のデータセット ] は表示されなくなります。

   * 分類を変更するには、「表示別 **[!UICONTROL と「分類]** の組み合わせ **[!UICONTROL を選択し]** す。

     | **[!UICONTROL 表示別]** オプション | **[!UICONTROL 分類]** オプション |
     |---|---|
     | **[!UICONTROL 接続]** | **[!UICONTROL -]** および **[!UICONTROL データセット]** |
     | **[!UICONTROL データセット]** | **[!UICONTROL -]** |
     | **[!UICONTROL サンドボックス]** | **[!UICONTROL 接続]** |
     | **[!UICONTROL タグ]** | **[!UICONTROL 接続]** |

  ![ 詳細の分類 ](assets/usage-detail-breakdown.png)

+++

  レポートする **[!UICONTROL 時間範囲]** を月単位で定義できます。 ![ カレンダー ](/help/assets/icons/Calendar.svg) を使用して、時間範囲を選択します。

>[!MORELIKETHIS]
>
>[ 接続設定の表示、トラブルシューティング、変更 ](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) チュートリアル
