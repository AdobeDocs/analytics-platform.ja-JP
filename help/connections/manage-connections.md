---
title: Customer Journey Analytics での接続の管理方法
description: Customer Journey Analytics（Customer Journey Analytics）で Experience Platform データセットへの接続を管理する方法について説明します。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '4288'
ht-degree: 90%

---

# 接続の管理

[1 つ以上の接続を作成または編集](/help/connections/create-connection.md)したら、**[!UICONTROL 接続]**&#x200B;で管理できます。接続により、次の操作を実行できます。

* 所有者、サンドボックス、接続の作成日時や変更日時など、すべての接続を一覧表示する。
* 接続を編集する。
* 接続を削除する。
* 接続からデータビューを作成する。
* 接続内のすべてのデータセットを表示する。
* 接続のデータセットのステータスと取り込みプロセスのステータスを確認する。例えば、Analysis Workspace でレポート作成と分析を開始できるように、データが利用可能になるタイミングなどです。
* 誤った設定によるデータの不一致を識別する。欠落している行があるか。ある場合、欠落している行とその理由は何か。接続の設定の誤りが原因で Customer Journey Analytics のデータが欠落したのか。
* すべての接続をまたいで取り込まれた行とレポート可能な行の使用状況に関するインサイトを取得する。

[!UICONTROL 接続]には、[[!UICONTROL リスト]](#list)と[[!UICONTROL 使用状況]](#usage)の 2 つのインターフェイスがあります。


## リスト

[!UICONTROL リスト]インターフェイスは、接続のデフォルトのインターフェイスです。選択されていない場合は、「**[!UICONTROL リスト]**」タブを選択してインターフェイスにアクセスします。

![リストビュー](assets/list-view.png)

[!UICONTROL リスト]インターフェイスには、使用可能なすべての接続のテーブルが表示されます。検索 ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) ボックスを使用して、接続をすばやく検索できます。

テーブルでは、次の列またはアイコンを使用できます。

| 列またはアイコン | 説明 |
| --- | --- |
| [!UICONTROL 名前] | 接続のわかりやすい名前です。接続の詳細を表示するには、ハイパーリンクされた名前を選択します。[接続の詳細](#connection-details)を参照してください。 |
| ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | [!UICONTROL 含まれるデータセット]、[!UICONTROL サンドボックス]、[!UICONTROL 所有者]などの情報を表示するには、接続名の横にある ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) を選択します。<p>ポップアップウィンドウに詳細が表示されます。 <p><img src="./assets/conn-info.png" alt="接続の詳細を表示" width="400"/> |
| ![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 接続の[データビューを作成](#create-a-data-view)するには、![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) を選択します。このアイコンは、接続にデータビューがまだ関連付けられていない場合にのみ表示されます。 |
| ![詳細情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択して、次の操作を実行します。 <p>![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) 接続を[編集](#edit-a-connection)します。<p>![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) 接続を[削除](#delete-a-connection)します。<p>![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [新しいデータビューを作成し](#create-a-data-view)、接続の追加データビューを作成します。<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) 接続マップ 接続の接続マップを表示するには、次の手順に従います。 |
| **[!UICONTROL データセット]** | 接続の一部であるデータセットへの 1 つ以上のリンク。データセットのハイパーリンクを選択すると、接続内のデータセットを表示できます。選択した接続にさらにデータセットを含める場合は、「**[!UICONTROL +*x* 以上]**」を選択して、**[!UICONTROL 含まれるデータセット]**&#x200B;パネルを表示します。このパネルには、すべてのデータセットへのリンクと、接続の一部である特定のデータセットを検索するオプションが表示されます。<p><img src="./assets/datasets-included.png" alt="含まれるデータセット" width="400"/><p>データセット名を選択すると、Experience Platform UI の新しいタブにデータセットが開きます。 |
| **[!UICONTROL サンドボックス]** | この接続がデータセットを取得する [Experience Platform サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)。このサンドボックスは、接続を初めて作成したときに選択されています。変更できません。 |
| **[!UICONTROL 所有者]** | 接続を作成したユーザー。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ ステータスが緑 ](assets/status-green.svg)    **[!UICONTROL _x _On]**：新しいデータを読み込むように設定されたデータセットの場合<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：新しいデータを読み込むように設定されていないデータセットの場合。 |
| **[!UICONTROL 作成日]** | 接続が作成されたときのタイムスタンプ。 |
| **[!UICONTROL 最終変更日]** | 接続が最後に更新されたときのタイムスタンプ。 |
| **[!UICONTROL データをバックフィル]** | データセットをまたいだバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：データセットをまたいで失敗したバックフィルの数の場合。<p>![ステータス（オレンジ色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：データセットをまたいで処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：データセットをまたいで完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：接続内のデータセットに対してバックフィルが定義されていない場合。 |

表示する列を設定するには、![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) を選択します。これにより、**テーブルをカスタマイズ**&#x200B;ダイアログが表示され、テーブル内の列をオンまたはオフにすることができます。

### 接続の編集

接続を編集するには：

1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します
1. コンテキストメニューから ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青色のバーから ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** を選択します。

接続を編集すると、次の操作を実行できます。

* 新しいデータの読み込みを開始および停止する。
* 接続名を変更する。
* データセットを更新します。
* 接続からデータセットを削除します。

詳しくは、[接続の作成または編集](create-connection.md)を参照してください。


### 接続の削除 {#connections-delete}

接続を削除するには：

1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
1. ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 削除]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青色のバーから ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 削除]** を選択します。

接続を削除すると、削除されたデータビューと影響を受けるワークスペースプロジェクトが&#x200B;**[!UICONTROL 接続を削除]**&#x200B;パネルに表示されます。

![接続を削除](assets/delete-connection.png)

「**[!UICONTROL 続行]**」を選択して、接続を削除します。

接続の削除について詳しくは、[削除の影響](/help/technotes/deletion.md)を参照してください。


### 接続のデータビューの作成

接続の新しいデータビューを作成するには

* 接続にデータビューが関連付けられていない場合：

   1. 接続名の横にある ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) を選択します。

* 接続に対して 1 つ以上のデータビューが既に作成されている場合：

   1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
   1. ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 新しいデータビューを作成]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青色のボタンバーから ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL データビューを作成]** を選択します。

詳しくは、[データビューの作成または編集](/help/data-views/create-dataview.md)を参照してください。


### 接続のマッピング

接続に含まれるデータセット間の関係の詳細を示す [ 接続マップ ](/help/connections/create-connection.md#connection-map) を表示するには、次の手順を実行します。

1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
1. ![GraphPathing](/help/assets/icons/GraphPathing.svg)**[!UICONTROL Connection map]** を選択します。

### 接続の詳細 {#connection-detail}

接続の詳細に移動するには、接続テーブルで接続名を選択します。

![ウィジェットと設定を示すすべてのデータセットウィンドウ](assets/conn-details.png)

接続の詳細インターフェイスでは、接続のステータスの詳細なビューが提供されます。次のことができます。

* 接続データセットのステータスと取り込みプロセスのステータスを確認します。
* レコードのスキップや削除の原因となる可能性のある設定の問題を識別します。
* データをレポートに使用できるタイミングを確認します。

| ユーザーインターフェイス | 説明 |
| --- | --- |
| ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 接続を編集]** | 接続の詳細を編集するには、![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 接続を編集]** を選択します。詳しくは、[接続の作成または編集](create-connection.md)を参照してください。 |
| **[!UICONTROL *データセットセレクター&#x200B;*]** | 接続内の 1 つまたはすべてのデータセットを選択できます。複数のデータセットを選択することはできません。デフォルトは&#x200B;**[!UICONTROL すべてのデータセット]**&#x200B;です。 |
| **[!UICONTROL *日付範囲セレクター&#x200B;*]** | 開始日、終了日を編集するか、![カレンダー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) を選択して日付範囲セレクターを開きます。日付範囲セレクターで、定義済みの期間の 1 つ（例：**[!UICONTROL 過去 6 か月間]**）を使用して日付範囲を選択するか、カレンダーを使用して開始日と終了日を選択します。新しい日付範囲を適用するには、「**[!UICONTROL 適用]**」を選択します。 |
| **[!UICONTROL 使用可能なイベントデータのレコード]** | **接続全体について**、レポートに使用できるイベントデータセット行の合計数。この数は、カレンダーの設定とは無関係です。データセットセレクターからデータセットを選択するか、テーブルでデータセットを選択すると、カウントが変更されます。データを追加すると、そのデータがレポートに表示されるまでに 1～2 時間の遅延が発生します。 |
| [!UICONTROL **[!UICONTROL 指標]**] | 追加、スキップおよび削除されたイベント、ルックアップ、プロファイル、概要データセットレコードと、追加されたバッチの数を要約します。これらの指標は、**選択したデータセットと日付範囲**&#x200B;に基づいています。<p>「**[!UICONTROL 詳細を確認]**」を選択すると、**[!UICONTROL スキップされた詳細を確認]**&#x200B;ポップアップが表示されます。ポップアップには、すべてのイベントデータセットまたは選択したデータセットのスキップされたレコードの数と理由が一覧表示されます。<p><img src="./assets/skipped-records.png" width="500"/><p>詳細情報が表示されている ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ポップアップを選択します。[!UICONTROL 空の訪問者 ID] など、スキップされた理由によっては、ポップアップに EQS（クエリサービス用の Experience Platform）のサンプル PSQL が表示され、[クエリサービス](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home)で使用してデータセット内のスキップされたレコードのクエリを実行できます。![コピー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL EQS 用サンプル PSQL をコピー]** を選択して SQL をコピーします。 |
| **[!UICONTROL 追加されたレコード]** | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に追加された行数を示します。10 分ごとに更新されます。 |
| **[!UICONTROL スキップされたレコード]** | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間にスキップされた行数を示します。レコードをスキップした理由には、タイムスタンプの欠落、欠落または無効、またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} などがあります。 10 分ごとに更新されます。 <p>無効な ID （`undefined`、`00000000`、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL  ユーザー ID] の数字と文字の任意の組み合わせなど）は、特定のユーザーまたは人物に関連付けることができない ID です。 これらの行はシステムに取り込むことができないため、取り込みやレポートでエラーが発生しやすくなります。無効なユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} を修正するには、次の 3 つのオプションがあります。<ul><li>[ステッチ](/help/stitching/overview.md)を使用して、未定義またはすべてがゼロのユーザー ID に有効なユーザー ID を入力する。</li><li>ユーザー ID を空白にする。この ID は取り込み時にスキップされます（無効なユーザー ID やすべてがゼロのユーザー ID よりも優先されます）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| **[!UICONTROL 削除されたレコード]** | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に削除された行数を示します。例えば、[!DNL Experience Platform] でデータセットが削除された可能性があるとします。10 分ごとに更新されます。<p>シナリオによっては、ステッチや一部のルックアップデータセットの更新などにより、この値に置き換えられたレコードが含まれる場合もあります。この例では、次を考慮します。</p><ul><li>1 つのレコードを XDM 個人プロファイルデータセットにアップロードします。これにより、Customer Journey Analytics がプロファイルルックアップデータとして取り込むように設定されます。接続の詳細では、このデータセットには 1 つのレコードが追加されたと表示されます。</li><li>元のレコードの複製を同じ AEP データセットにアップロードします。これにより、2 つのレコードが含まれるようになります。 Customer Journey Analyticsは、プロファイルまたはアカウント [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} ルックアップデータセットから追加のレコードを取り込みます。 プロファイルまたはアカウントレコードが、その人物 ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} の接続に既に取り込まれているのを確認すると、Customer Journey Analyticsは以前のバージョンを削除して、新しいプロファイルデータを追加します。 Customer Journey Analyticsでは、取り込まれたユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} の最新のプロファイル参照データのみが保持されるので、接続詳細では、このアクションは、追加されたレコード 1 件と削除されたレコード 1 件を表します。</li><li>合計すると、AEP データセットには同一の 2 つのレコードが含まれます。 これとは別に、Customer Journey Analytics 接続の詳細には、このプロファイルデータセットに対して 2 つのレコードが追加され、1 つのレコードが削除されました、という取り込まれたデータのステータスが表示されます。 </li></ul> |
| ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | データセット検索フィールド。データセット名または[!UICONTROL データセット ID] でデータセットテーブルを検索できます。 |
| [!UICONTROL データセットテーブル] | 接続に含まれるデータセットを表示します。詳しくは、以下のタブを参照してください。 |

データセットテーブルには、次の列が表示されます。

| 列 | 説明 |
| --- | --- |
| **[!UICONTROL データセット]** | 接続の一部であるデータセットの名前。ハイパーリンクを選択すると、Experience Platform UI の新しいタブでデータセットを開くことができます。行を選択するか、チェックボックスをオンにすると、選択したデータセットの詳細のみを表示できます。 |
| **[!UICONTROL データセット ID]** | Experience Platform によって自動的に生成されます。 |
| **[!UICONTROL 追加されたレコード]** | 選択した時間間隔で接続に追加されたデータセットのレコード（行）の数。 |
| **[!UICONTROL スキップされたレコード]** | 選択した時間間隔で接続のデータ転送中にスキップされたデータセットのレコード（行）の数。 |
| **[!UICONTROL 削除されたレコード]** | 選択した時間間隔で接続から削除されたデータセットのレコード（行）の数。 |
| **[!UICONTROL 追加されたバッチ]** | 接続に追加されたデータセットのバッチの数。 |
| **[!UICONTROL 前回追加した日時]** | 接続に追加されたデータセットからの最新のバッチのタイムスタンプ。 |
| **[!UICONTROL データソースタイプ]** | データセットのソースタイプ。接続を作成する際に、ソースタイプを定義します。 |
| **[!UICONTROL データセットタイプ]** | このデータセットのデータセットタイプ。タイプには、[!UICONTROL イベント]、[!UICONTROL プロファイル]、[!UICONTROL ルックアップ]または[!UICONTROL 概要]を指定できます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL スキーマ]** | データセットのベースとなる Experience Platform スキーマ。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：データセットが新しいデータを読み込むように設定されている場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：データセットが新しいデータを読み込むように設定されていない場合。 |
| **[!UICONTROL データセットを変換]** | 適用可能な B2B ルックアップデータセットの変換ステータス。詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：変換に対して有効である適用可能なデータセットの場合。 <p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：変換に対して有効でない適用可能なデータセットの場合。<p>**[!UICONTROL 該当なし]**：変換に対して適用可能でない他のすべてのデータセットの場合。 |
| **[!UICONTROL データをバックフィル]** | データセットのバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：失敗したバックフィルの数の場合。<p>![ステータス（赤色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：バックフィルが定義されていない場合。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：データセットが新しいデータを読み込むように設定されている場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：データセットが新しいデータを読み込むように設定されていない場合。 |
| **[!UICONTROL データをバックフィル]** | データセットのバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：失敗したバックフィルの数の場合。<p>![ステータス（赤色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：バックフィルが定義されていない場合。 |

>[!IMPORTANT]
>
>2021年8月13日（PT）より前に取り込まれたデータは、[!UICONTROL 接続]インターフェイスに反映されません。

#### 接続パネル

データセットテーブルでデータセットを選択していない場合、接続インターフェイスの右側のパネルに接続オプションと詳細が表示されます。

| オプション | 説明 |
| --- | --- |
| ![更新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 更新] | 接続を更新し、最近追加されたレコードを反映するには、![更新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 更新]** を選択します。 |
| ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)、**[!UICONTROL 削除]** | この接続を[削除](#delete-a-connection)します。 |
| ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL データビューを作成]** | この接続に基づいて[データビューを作成します](#create-a-data-view)。詳しくは、[データビュー](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/data-views)を参照してください。 |
| **[!UICONTROL 接続名]** | 接続のわかりやすい名前。 |
| **[!UICONTROL 接続の説明]** | この接続の目的を説明するより詳細な説明。 |
| **[!UICONTROL サンドボックス]** | この接続がデータセットを取得する [Experience Platform サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)。このサンドボックスは、最初に接続を作成した際に選択されました。変更できません。 |
| **[!UICONTROL 接続 ID]** | この ID は、Experience Platform で生成されます。ID をコピーするには、![コピー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) を使用します。 |
| **[!UICONTROL 接続を使用するデータビュー]** | この接続を使用するすべてのデータビューを表示します。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：データセットの数が新しいデータを読み込むように設定されている場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：新しいデータ読み込みがオフになっているデータセットの数の場合。 |
| **[!UICONTROL データをバックフィル]** | データセットのバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：データセットをまたいで失敗したバックフィルの数の場合。<p>![ステータス（赤色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：データセットをまたいで処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：データセットをまたいで完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：接続内のデータセットに対してバックフィルが定義されていない場合。 |
| **[!UICONTROL データセットを変換]** | 適用可能な B2B ルックアップデータセットの変換ステータス。詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：変換に対して有効であるデータセットの数の場合。 |
| **[!UICONTROL 作成者]** | クエリを作成したユーザーの名前。 |
| **[!UICONTROL 最終変更日]** | 接続に対する最後の変更のタイムスタンプ。 |
| **[!UICONTROL 最終変更者]** | 接続を最後に変更したユーザー。 |

#### データセットパネル

データセットテーブルでデータセット行が選択されると、接続インターフェイスの右側にあるパネルに、選択したデータセットの詳細が表示されます。

| 詳細 | 説明 |
| --- | --- |
| **[!UICONTROL ユーザー ID]** | Experience Platform のデータセットスキーマで定義された ID。この ID は、接続の作成中に選択したユーザー ID です。異なる ID のデータセットを含む接続を作成すると、レポートに反映されます。データセットを結合するには、データセットをまたいで同じユーザー ID を使用する必要があります。 |
| **[!UICONTROL キー]** | ルックアップデータセットに指定したキー。 |
| **[!UICONTROL 一致するキー]** | ルックアップデータセットに指定した一致するキー。 |
| **[!UICONTROL タイムスタンプ]** | イベントデータセットに定義されたタイムスタンプ。 |
| **[!UICONTROL 使用可能なレコード]** | カレンダーを通じて選択された特定の期間に、このデータセットに対して取り込まれた行の合計数。データが追加されると、レポートに表示されるデータの取得に遅延は発生しません。ただし、最新の接続を作成すると、[遅延](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-faq)が発生します。 |
| **[!UICONTROL 追加されたレコード]** | 選択した期間に追加された行数。 |
| **[!UICONTROL 削除されたレコード]** | 選択した期間中に削除されたレコードの数。 |
| **[!UICONTROL 追加されたバッチ]** | このデータセットに追加されたデータバッチの数。 |
| **[!UICONTROL スキップされたレコード]** | 選択した期間の取り込み中にスキップされた行数。<p>レコードをスキップした理由には、タイムスタンプの欠落、ユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} の欠落または無効などがあります。 10 分ごとに更新されます。<p>無効な ID （`undefined`、`00000000`、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL  ユーザー ID] の数字と文字の任意の組み合わせなど）は、特定のユーザーまたは人物に関連付けることができない ID です。 これらの行はシステムに取り込むことができないため、取り込みやレポートでエラーが発生しやすくなります。無効なユーザー ID またはアカウント ID を修正する方法として、次の 3 つのオプションがあります。<ul><li>[ステッチ](/help/stitching/overview.md)を使用して、未定義またはすべてがゼロのユーザー ID に有効なユーザー ID を入力する。</li><li>ユーザー ID を空白にする。この ID は取り込み時にスキップされます（無効なユーザー ID やすべてがゼロのユーザー ID よりも優先されます）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| **[!UICONTROL 前回追加した日時]** | 最後のバッチが追加されたタイムスタンプ。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：データセットが新しいデータを読み込むように設定されている場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：データセットが新しいデータを読み込むように設定されていない場合。 |
| **[!UICONTROL データをバックフィル]** | データセットのバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：失敗したバックフィルの数の場合。<p>![ステータス（赤色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：バックフィルが定義されていない場合。<p>データセットの過去のバックフィルの概要を示すダイアログを表示するには、 <img src="./assets/pastbackfill.svg" alt="過去のバックフィル" width="15"/> **[!UICONTROL 過去のバックフィル]** を選択します。 |
| **[!UICONTROL データソースタイプ]** | データセットを接続に追加する際に定義されるデータソースタイプ。 |
| **[!UICONTROL データセットタイプ]** | [!UICONTROL イベント]、[!UICONTROL プロファイル]、[!UICONTROL ルックアップ]または[!UICONTROL 概要]のいずれかです。 [詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL スキーマ]** | このデータセットのベースとなる Experience Platform スキーマ。 |
| **[!UICONTROL データセット ID]** | このデータセット ID は、Experience Platform で生成されます。 |


## 使用状況 {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="主要な使用状況指標"
>abstract="コアおよび履歴のレポート可能行数の月別および合計データを指定します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="月別の取り込み行数"
>abstract="月別にシステムに追加されるレコードの合計数を測定し、データの増加と取り込み率に関するインサイトを指定します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="月別のレポート可能行数"
>abstract="レポートに使用できる行数を追跡します。 レポート可能行数は、取り込まれた行数から、取り込み中にスキップおよび削除された行数を除いたものです。レポート可能行数は、課金とデータ使用量の主要な指標として機能します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="詳細な分類。"
>abstract="データの CSV ファイルをダウンロードするオプションを使用して、接続別、データセット別、サンドボックス別、タグ別に詳細な指標を表示できます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="その他のデータセット"
>abstract="2024年9月より前の数か月間については、データはデータセットレベルで収集され、わかりやすくするために&#x200B;*その他のデータセット*&#x200B;として表示されます。2024年9月以降、データは詳細なデータセットレベルで収集され、*その他のデータセット*&#x200B;は表示されなくなります。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="不明なデータセットまたは接続"
>abstract="不明なデータセットまたは接続は、ID を使用して表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="データは使用できません"
>abstract="システムの制限により、2024年9月より前の履歴データは使用できません。指標は、2024年9月以降に収集され、表示されます。グラフには過去 18 か月のタイムラインが表示され、今後のデータはデータが使用可能になると表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="コアのレポート可能な行数"
>abstract="過去 13 か月間に使用できる行の合計数を表示します。例えば、2024年2月1日（PT）の数は、2023年1月から 2024年1月までのイベントタイムスタンプで使用できる行の合計数を示します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="履歴のレポート可能な行数"
>abstract="13 か月より前の期間に使用できる行の合計数を表示します。例えば、2024年2月1日（PT）の数は、2023年1月より古いイベントタイムスタンプで使用できる行の合計数を示します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="主要な使用状況指標"
>abstract="コアおよび履歴のレポート可能行数の月別および合計データを指定します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="月別の取り込み行数"
>abstract="月別にシステムに追加されるレコードの合計数を測定し、データの増加と取り込み率に関するインサイトを指定します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="月別のレポート可能行数"
>abstract="レポートに使用できる行数を追跡します。 レポート可能行数は、取り込まれた行数から、取り込み中にスキップおよび削除された行数を除いたものです。レポート可能行数は、課金とデータ使用量の主要な指標として機能します。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="詳細な分類。"
>abstract="データの CSV ファイルをダウンロードするオプションを使用して、接続別、データセット別、サンドボックス別、タグ別に詳細な指標を表示できます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="その他のデータセット"
>abstract="2024年9月より前の数か月間については、データはデータセットレベルで収集され、わかりやすくするために&#x200B;*その他のデータセット*&#x200B;として表示されます。2024年9月以降、データは詳細なデータセットレベルで収集され、*その他のデータセット*&#x200B;は表示されなくなります。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="不明なデータセットまたは接続"
>abstract="不明なデータセットまたは接続は、ID を使用して表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="データは使用できません"
>abstract="システムの制限により、2024年9月より前の履歴データは使用できません。指標は、2024年9月以降に収集され、表示されます。グラフには過去 18 か月のタイムラインが表示され、今後のデータはデータが使用可能になると表示されます。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="コアのレポート可能な行数"
>abstract="過去 13 か月間に使用できる行の合計数を表示します。例えば、2024年2月1日（PT）の数は、2023年1月から 2024年1月までのイベントタイムスタンプで使用できる行の合計数を示します。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="履歴のレポート可能な行数"
>abstract="13 か月より前の期間に使用できる行の合計数を表示します。例えば、2024年2月1日（PT）の数は、2023年1月より古いイベントタイムスタンプで使用できる行の合計数を示します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="コアのレポート可能な行数"
>abstract="コアレポート可能行数はスナップショット値であり、集計合計ではありません。これらの値は、選択した日付範囲の最後の月に基づいて動的に更新されます。お客様が 1 月から 3 月を選択した場合、値は 3 月のスナップショットを反映します。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="履歴のレポート可能な行数"
>abstract="履歴レポート可能行数はスナップショット値であり、集計合計ではありません。これらの値は、選択した日付範囲の最後の月に基づいて動的に更新されます。お客様が 1 月から 3 月を選択した場合、値は 3 月のスナップショットを反映します。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="累積レポート可能行数"
>abstract="累積レポート可能行数はスナップショット値であり、集計合計ではありません。これらの値は、選択した日付範囲の最後の月に基づいて動的に更新されます。お客様が 1 月から 3 月を選択した場合、値は 3 月のスナップショットを反映します。"

<!-- markdownlint-enable MD034 -->



[!UICONTROL 使用状況]インターフェイスには、すべての接続で取り込まれた行とレポート可能な行の使用状況が表示されます。選択されていない場合は、「**[!UICONTROL 使用状況]**」タブを選択してインターフェイスにアクセスします。

このインターフェイスは、Customer Journey Analytics の使用状況が契約上の合意事項に準拠しているかどうかを判断するのに役立ちます。監視目的に加えて、使用状況インターフェイスを使用して、Customer Journey Analytics ライセンスの更新を計画することもできます。

使用状況インターフェイスでは、次の指標を使用します

| Metric name | 説明 |
|---|---|
| 履歴のレポート可能な行数 | 13 か月を超える期間の行数。 |
| コアのレポート可能な行数 | 過去 13 か月間の行数。 |
| 取り込まれた行数 | 特定の期間に取り込まれた行数。 |
| レポート可能な行数 | 特定の期間の接続の一部として保持されるデータの行数。 |
| 累積行数 | 特定の月までに取り込まれた行数。 |

>[!NOTE]
>
>データは、2024年7月からコア、履歴、合計レコードについて収集されます。以前の履歴データについては、アドビ担当営業または販売店にお問い合わせください。
>



使用状況インターフェイスは、次の 2 つのパネルで構成されます。

* **[!UICONTROL 主要使用状況指標]**&#x200B;パネル：コアデータと履歴データのレポート可能な行数を示します。また、このパネルでは、コアデータと履歴データの行数の両方について、前月と比較した割合の変化も追跡します。

  パネルは、次のビジュアライゼーションで表示されます。

   * **[!UICONTROL コアデータのレポート可能な行数]**。

     過去 13 か月間でレポート可能な行の数。概要数値は、先月（例：2024年12月）のコアのレポート可能な行の数（例：741M）です。

   * **[!UICONTROL 履歴データのレポート可能な行数]**。

     13 か月を超える期間のレポート可能な行の数。概要数値は、先月（例：2024年12月）の履歴のレポート可能な行の数（例：127M）です。

  ビジュアライゼーション内の積み重ね棒グラフにポインタを合わせると、ポップアップに棒グラフの特定の部分の行数が表示されます（例）。


  ![主要使用状況指標](assets/usage-key-usage-metrics.png)

* 次の 3 つのサブパネルを表示する組み合わせパネル：

+++ 取り込まれた行数

  **[!UICONTROL 取り込まれた行数]**&#x200B;サブパネルは、月別でシステムに追加されるレコードの合計数を測定し、データの増加と取り込み率に関するインサイトを提供します。サブパネルには、今月取り込まれた行数の合計数と前月からの変化の概要が表示されます。

  ![取り込まれた行数](assets/usage-ingested-rows.png)

  ビジュアライゼーションのデータポイントにポインタを合わせると、詳細を含むポップアップが表示されます。

+++

+++ レポート可能な行数

  **[!UICONTROL レポート可能な行数]**&#x200B;のビジュアライゼーションでは、取り込んだ行からスキップされた行と削除された行を減算することで、レポートに使用できる行数を追跡します。これは、課金とデータ使用状況の主要指標として機能します。サブパネルには、次の 2 つの概要が表示されます。

   * **[!UICONTROL 先月の合計数]**：今月までのレポート可能な行数の合計数の概要。
   * **[!UICONTROL 今月]**：今月のレポート可能な行数の合計数と前月からの変化の概要。

  ![レポート可能な行数](assets/usage-reportable-rows.png)

  ビジュアライゼーションのデータポイントにポインタを合わせると、詳細を含むポップアップが表示されます。

+++

+++ 詳細分類

  **[!UICONTROL 詳細分類]**&#x200B;テーブルを使用すると、、接続別、データセット別別、サンドボックス別、タグ別に詳細な指標を表示できます。データセット名はレポート期間中に変更される場合があるので、データセットは名前ではなく ID を使用してレポートされます。不明なデータセットまたは接続は、ID を使用してレポートされます。

  2024年9月より前の数か月間については、データはデータセットレベルで収集され、わかりやすくするために[!UICONTROL その他のデータセット]として表示されます。2024年9月以降、データは詳細なデータセットレベルで収集され、[!UICONTROL その他のデータセット]は表示されなくなります。

   * 分類を変更するには、「**[!UICONTROL 表示別]**」と「**[!UICONTROL 分類別]**」の組み合わせを選択します。

     | 「**[!UICONTROL 表示別]**」オプション | 「**[!UICONTROL 分類別]**」オプション |
     |---|---|
     | **[!UICONTROL 接続]** | **[!UICONTROL -]** および&#x200B;**[!UICONTROL データセット]** |
     | **[!UICONTROL データセット]** | **[!UICONTROL -]** |
     | **[!UICONTROL サンドボックス]** | **[!UICONTROL 接続]** |
     | **[!UICONTROL タグ]** | **[!UICONTROL 接続]** |

  ![詳細分類](assets/usage-detail-breakdown.png)

+++

  レポートする&#x200B;**[!UICONTROL 時間範囲]**&#x200B;を月単位で定義できます。時間範囲を選択するには、![カレンダー](/help/assets/icons/Calendar.svg) を使用します。

>[!MORELIKETHIS]
>
>[接続設定の表示、トラブルシューティング、変更](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja)チュートリアル。
>[Customer Journey Analyticsの使用状況の管理 ](/help/technotes/estimate-usage.md)
>
