---
title: Customer Journey Analytics での接続の管理方法
description: Customer Journey Analytics(Customer Journey Analytics) でExperience Platformデータセットへの接続を管理する方法について説明します。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 0cf1f69d5623a827cba64427c8db614b690968a0
workflow-type: tm+mt
source-wordcount: '2484'
ht-degree: 26%

---

# 接続の管理

一度 [1 つ以上の接続を作成または編集しました](/help/connections/create-connection.md)を使用する場合、 **[!UICONTROL 接続]**. 接続を使用すると、次のことができます。

* 所有者、サンドボックス、接続の作成日時や変更日時など、すべての接続を一目で表示します。
* 接続を編集します。
* 接続を削除する。
* 接続からデータビューを作成する。
* 接続内のすべてのデータセットを表示する。
* 接続のデータセットのステータスと取り込みプロセスのステータスを確認します。 例えば、Analysis Workspaceでのレポートと分析を開始できるように、データが使用可能になるタイミングを指定します。
* 設定ミスによるデータの相違を特定します。 欠落している行があるか。その場合、欠落している行とその理由を教えてください。 接続の構成を誤っておき、Customer Journey Analyticsにデータが欠落している原因を特定した場合は、


表に、使用可能なすべての接続が示されます。 検索を使用して、接続をすばやく検索できます。 ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) ボックス。

テーブルでは、次の列/アイコンを使用できます。

| 列/アイコン | 説明 |
| --- | --- |
| [!UICONTROL 名前] | 接続のわかりやすい名前です。接続の詳細を確認するには、ハイパーリンク名を選択します。 詳しくは、 [接続の詳細](#connection-details). |
| ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 次に関する情報を表示するには： [!UICONTROL 含まれるデータセット], [!UICONTROL サンドボックス], [!UICONTROL 所有者]を選択し、その他を選択します。 ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 接続名の横に表示されます。<p>ポップアップウィンドウに詳細が表示されます。 <p><img src="./assets/conn-info.png" alt="接続情報を表示" width="50%" /> |
| ![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 宛先 [データビューの作成](#create-a-data-view) 接続の場合、「 」を選択します。 ![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . このアイコンは、データビューが接続に既に関連付けられていない場合にのみ表示されます。 |
| ![詳細情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 選択 ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 移動先： <p>![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [編集](#edit-a-connection) 接続。<p>![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [削除](#delete-a-connection) 接続。<p>![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [新しいデータビューを作成](#create-a-data-view). 接続の追加のデータビューを作成するには、これを使用します。 |
| [!UICONTROL データセット] | 接続に含まれるデータセットへのリンクを 1 つ以上表示します。 データセットのハイパーリンクを選択して、接続にあるデータセットを表示できます。 選択した接続に他のデータセットが含まれている場合は、「 」を選択します。 **[!UICONTROL +*x* その他]** 見せる **[!UICONTROL 含まれるデータセット]** パネル。 このパネルには、すべてのデータセットへのリンクと、接続に含まれる特定のデータセットを検索するためのオプションが表示されます。<p><img src="./assets/datasets-included.png" alt="含まれるデータセット" width="50%" /><p>データセット名を選択すると、新しいタブでExperience PlatformUI にデータセットが開きます。 |
| [!UICONTROL サンドボックス] | 次を表示： [Experience Platformサンドボックス](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja) この接続がデータセットを描画する元となる このサンドボックスは、接続を初めて作成したときに選択されています。変更できません。 |
| [!UICONTROL 所有者] | 接続を作成したユーザー。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータのインポートのステータスを示します。 <p><span style="color:green">●</span>   **[!UICONTROL _x _オン]**新しいデータを読み込むように設定されたデータセットの数。&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x オフ_]** ：新しいデータの読み込みがオフになっているデータセットの数。 |
| [!UICONTROL 作成日] | 接続が作成されたときのタイムスタンプ。 |
| [!UICONTROL 最終変更日] | 接続が最後に更新されたときのタイムスタンプ。 |
| [!UICONTROL データをバックフィル] | データセットをまたいでデータをバックフィルするステータスを表示します。<p><span style="color:red">●</span>   **[!UICONTROL _x _バックフィルに失敗しました]**（データセット全体で失敗したバックフィルの数）<p><span style="color:orange">●</span>   **[!UICONTROL _x _バックフィル処理]**（データセットをまたいだ処理バックフィルの数）<p><span style="color:green">●</span>   **[!UICONTROL _x _バックフィル完了]**（データセットの完了したバックフィルの数）、<p><span style="color:grey">●</span>   **[!UICONTROL _オフ_]** 接続内のデータセットにバックフィルが定義されていない場合。 |

表示する列を設定するには、 ![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). これにより、 **テーブルをカスタマイズ** ダイアログで、テーブルの列のオン/オフを切り替えることができます。

## 接続の編集

管理者に接続の編集を許可します。

1. 選択 ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 接続名の横に
1. 選択 ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 選択 ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** 青いバーから

接続を編集する際に、次の操作を実行できます。

* 新しいデータのインポートを開始および停止します。
* 接続名を変更する。
* データセットを更新します。
* 接続からデータセットを削除します。

詳しくは、 [接続の作成または編集](create-connection.md) を参照してください。


## 接続の削除 {#connections-delete}

管理者に接続の削除を許可します。

1. 選択 ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 接続名の横に表示されます。
1. 選択 ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 削除]**.

または、次の操作を実行できます。

1. 接続行を選択します。

1. 選択 ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 削除]** 青いバーから

接続を削除すると、 **[!UICONTROL 接続を削除]** パネルは、削除されるデータビューと影響を受けるワークスペースプロジェクトを示します。

<img src="./assets/delete-connection.png" alt="接続を削除" width="50%" />

選択 **[!UICONTROL 続行]** 接続を削除します。

詳しくは、 [削除の影響](/help/admin/cja-deletion.md) を参照してください。


## データレイヤーの作成

管理者が接続のデータビューを作成できるようにします。

* 接続に関連付けられているデータビューがない場合：

   1. 選択 ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) 接続名の横に表示されます。

* 接続用に 1 つ以上のデータビューが既に作成されている場合：

   1. 選択 ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 接続名の横に表示されます。
   1. 選択 ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 新しいデータビューを作成]**.

または、次の操作を実行できます。

1. 接続行を選択します。

1. 選択 ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL データビューを作成]** 青いボタンバーから

詳しくは、[データビューの作成または編集](/help/data-views/create-dataview.md)を参照してください。

## 接続の詳細 {#connection-detail}

接続の詳細に移動するには、接続テーブルで接続名を選択します。

![ウィジェットと設定を表示するすべてのデータセットウィンドウ](assets/conn-details.png)

[ 接続の詳細 ] インターフェイスには、接続の状態の詳細が表示されます。 次のことができます。

* 接続データセットのステータスと取り込みプロセスのステータスを確認します。
* スキップまたは削除されたレコードを引き起こす可能性のある設定の問題を特定します。
* データをレポートに使用できるタイミングを確認します。

| ユーザーインターフェイス | 説明 |
| --- | --- |
| ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL 接続を編集] | 接続の詳細を編集するには、 ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 接続を編集]** . 詳しくは、 [接続の作成または編集](create-connection.md) を参照してください。 |
| データセットセレクター | 接続内の 1 つまたはすべてのデータセットを選択できます。複数のデータセットを選択することはできません。デフォルトは[!UICONTROL すべてのデータセット]です。 |
| 日付範囲セレクター | 開始日/終了日の編集または選択 ![カレンダー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) をクリックして、データ範囲セレクターを開きます。 日付範囲セレクターで、事前定義された期間 ( 例： **[!UICONTROL 最近の 6 か月間]**) またはカレンダーを使用して、開始日と終了日を選択します。 選択 **[!UICONTROL 適用]** をクリックして新しいデータ範囲を適用します。 |
| [!UICONTROL 使用可能なイベントデータのレコード] | **接続全体について**、レポートに使用できるイベントデータセットの行の合計数を表します。この数は、カレンダーの設定とは無関係です。データセットセレクターでデータセットを選択するか、テーブル内のデータセットを選択すると、カウントは変わります。 データが追加されると、データがレポートに表示されるまでに 1 ～ 2 時間の遅延が生じます。 |
| [!UICONTROL 指標] | **選択したデータセットと日付範囲に対して**、追加／スキップ／削除したイベントレコードと、追加したバッチ数の概要を示します。<p>選択 **[!UICONTROL 詳細を確認]** 見せる **[!UICONTROL スキップされた詳細を確認]** ポップアップ、すべてのイベントデータセットまたは選択したデータセットのリストに、スキップされたレコードの数と理由が表示されます。<p><img src="./assets/skipped-records.png" width="70%"/><p>選択 ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ポップアップに詳細情報を表示します。 以下のようなスキップされた理由があります。 [!UICONTROL 空の訪問者 ID]に設定すると、ポップアップに、 [クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja) をクエリして、データセット内のスキップされたレコードを照会します。 選択 ![コピー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL EQS 用のサンプル PSQL のコピー]** SQL をコピーします。 |
| [!UICONTROL 追加されたレコード] | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に追加された行数を示します。10 分ごとに更新されます。 |
| [!UICONTROL スキップされたレコード] | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間にスキップされた行数を示します。レコードをスキップする理由には、タイムスタンプの欠落、ユーザー ID の欠落、無効などがあります。 10 分ごとに更新されます。 <p>無効なユーザー ID（「未定義」、「00000000」、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL 人物 ID] の文字と数字の任意の組み合わせ）を、特定のユーザーまたは人物に関連付けることはできません。これらはシステムに取り込むことができず、取り込みやレポートでエラーが発生しやすくなります。無効なユーザー ID を修正する方法として、次の 3 つのオプションがあります。<ul><li>用途 [ステッチ](/help/stitching/overview.md) 未定義またはゼロのユーザー ID を有効なユーザー ID で入力する場合。</li><li>ユーザー ID を空白にします。この ID は取り込み中にスキップされます（無効またはゼロのユーザー ID よりも望ましい）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| [!UICONTROL レコード] 削除済み | **選択したデータセットと日付範囲**&#x200B;に対して、選択した期間に削除された行数を示します。たとえば、Experience Platform 内のデータセットが削除された可能性があります。10 分ごとに更新されます。 |
| ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _データセット名または ID を検索_ | データセット検索フィールド。 データセット名または [!UICONTROL データセット ID]. |
| [!UICONTROL データセットテーブル] | 接続に含まれるデータセットを表示します。 |
| [!UICONTROL データセット] | 接続に含まれるデータセットの名前を表示します。 ハイパーリンクを選択して、Experience PlatformUI のデータセットを新しいタブで開くことができます。 行またはチェックボックスを選択して、選択したデータセットの詳細のみを表示できます。 |
| [!UICONTROL データセット ID] | Experience Platformで自動生成。 |
| [!UICONTROL 追加されたレコード] | 選択した期間に接続に追加されたデータセットのレコード/行の数。 |
| [!UICONTROL スキップされたレコード] | 選択した時間間隔で、接続のデータ転送中にスキップされたデータセットレコード/行の数。 |
| [!UICONTROL 削除されたレコード] | 選択した期間に接続から削除されたデータセットのレコード/行の数。 |
| [!UICONTROL 追加されたバッチ] | 接続に追加されたデータセットバッチの数。 |
| [!UICONTROL 前回追加した日時] | 接続に追加されたデータセットからの最新のバッチのタイムスタンプ。 |
| [!UICONTROL データソースタイプ] | データセットのソースタイプ。 接続を作成する際に、ソースのタイプを定義します。 |
| [!UICONTROL データセットタイプ] | このデータセットのデータセットタイプ。 タイプは、 [!UICONTROL イベント], [!UICONTROL 参照]または [!UICONTROL プロファイル]. [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#configure-dataset) |
| スキーマ | Experience Platformセットの基になるデータスキーマ。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータのインポートのステータスを示します。 <p><span style="color:green">●</span>   **[!UICONTROL _x _オン]**データセットが新しいデータを読み込むように設定されている場合、および<p><span style="color:gray">●</span>   **[!UICONTROL _x オフ_]** データセットが新しいデータインポートをインポートしないように設定されている場合。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータスを表示します。<p><span style="color:red">●</span>   **[!UICONTROL _x _バックフィルに失敗しました]**失敗したバックフィルの数<p><span style="color:orange">●</span>   **[!UICONTROL _x _バックフィル処理]**（バックフィル処理の数）<p><span style="color:green">●</span>   **[!UICONTROL _x _バックフィル完了]**完了したバックフィルの数、および<p><span style="color:grey">●</span>   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合に備えて、 |

>[!IMPORTANT]
>
>2021 年 8 月 14 日より前に取り込まれたデータは、 [!UICONTROL 接続] インターフェイス。

### 接続パネル

データセットテーブルでデータセットが選択されていない場合、接続インターフェイスの右側にあるパネルに、接続オプションと詳細が表示されます。

| オプション/詳細 | 説明 |
| --- | --- |
| ![更新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 更新] | 接続を更新し、最近追加したレコードを反映させるには、 ![更新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 更新]**. |
| ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 削除]** | [削除](#delete-a-connection) この接続。 |
| ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL データビューを作成]** | [データビューの作成](#create-a-data-view) この接続に基づいて 詳しくは、 [データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja) を参照してください。 |
| [!UICONTROL 接続名] | 接続のわかりやすい名前を表示します。 |
| [!UICONTROL 接続の説明] | この接続の目的を説明する詳細な説明を表示します。 |
| [!UICONTROL サンドボックス] | The [Experience Platformサンドボックス](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja) この接続がデータセットを取り込む元となる。このサンドボックスは、接続を初めて作成したときに選択されました。 変更できません。 |
| [!UICONTROL 接続 ID] | この ID は、Experience Platformで生成されます。 以下を使用できます。 ![コピー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) をクリックして ID をコピーします。 |
| [!UICONTROL 接続を使用するデータビュー] | この接続を使用するすべてのデータビューを表示します。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータのインポートのステータスを示します。 <p><span style="color:green">●</span>   **[!UICONTROL _x _オン]**：新しいデータを読み込むように設定されているデータセットの数、<p><span style="color:gray">●</span>   **[!UICONTROL _x オフ_]** ：新しいデータの読み込みがオフになっているデータセットの数。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータスを表示します。<p><span style="color:red">●</span>   **[!UICONTROL _x _バックフィルに失敗しました]**（データセット全体で失敗したバックフィルの数）<p><span style="color:orange">●</span>   **[!UICONTROL _x _バックフィル処理]**（データセットをまたいだ処理バックフィルの数）<p><span style="color:green">●</span>   **[!UICONTROL _x _バックフィル完了]**（データセットの完了したバックフィルの数）、<p><span style="color:grey">●</span>   **[!UICONTROL _オフ_]** 接続内のデータセットにバックフィルが定義されていない場合。 |
| [!UICONTROL 作成者] | 接続を作成した人物の名前を表示します。 |
| [!UICONTROL 最終変更日] | 接続に対する最後の変更のタイムスタンプを表示します。 |
| [!UICONTROL 最終変更者] | 接続を最後に変更した人物を表示します。 |

### データセットパネル

データセットテーブルでデータセットを選択すると、接続インターフェイスの右側にあるパネルに、選択したデータセットの詳細が表示されます。

| 詳細 | 説明 |
| --- | --- |
| [!UICONTROL ユーザー ID] | Experience Platform 内のデータセットのスキーマで定義された ID を表示します。これは、接続の作成時に選択したユーザー ID です。 異なる ID のデータセットを含む接続を作成すると、レポートに反映されます。 データセットを結合するには、データセット間で同じユーザー ID を使用する必要があります。 |
| [!UICONTROL キー] | ルックアップデータセットに対して指定したキーを表示します。 |
| [!UICONTROL 一致するキー] | ルックアップデータセットに対して指定した一致するキーを表示します。 |
| [!UICONTROL タイムスタンプ] | イベントデータセットに定義されたタイムスタンプを表示します。 |
| [!UICONTROL 使用可能なレコード] | カレンダーで選択した特定の期間に、このデータセットに対して取り込まれた行の合計数を表します。データが追加されると、レポートに表示されるデータの取得に遅延は発生しません。ただし、新しい接続を作成すると、次のようになります。 [待ち時間](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#3-getting-data-into-customer-journey-analytics). |
| [!UICONTROL 追加されたレコード] | 選択した期間に追加された行数を示します。 |
| [!UICONTROL 削除されたレコード] | 選択した期間に削除されたレコード数を示します。 |
| [!UICONTROL 追加されたバッチ] | このデータセットに追加されたデータバッチの数を示します。 |
| [!UICONTROL スキップされたレコード] | 選択した期間の取り込み中にスキップされた行数をし示します。<p>レコードをスキップする理由には、タイムスタンプの欠落、ユーザー ID の欠落、無効などがあります。 10 分ごとに更新されます。<p>無効なユーザー ID（「未定義」、「00000000」、または特定の月において 100 万回を超えるイベントに存在する [!UICONTROL 人物 ID] の文字と数字の任意の組み合わせ）を、特定のユーザーまたは人物に関連付けることはできません。これらはシステムに取り込むことができず、取り込みやレポートでエラーが発生しやすくなります。無効なユーザー ID を修正する方法として、次の 3 つのオプションがあります。<ul><li>用途 [ステッチ](/help/stitching/overview.md) 未定義またはゼロのユーザー ID を有効なユーザー ID で入力する場合。</li><li>ユーザー ID を空白にします。この ID は取り込み中にスキップされます（無効またはゼロのユーザー ID よりも望ましい）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| [!UICONTROL 前回追加した日時] | 最後のバッチが追加された日時を示します。 |
| [!UICONTROL 新しいデータをインポート] | データセットの新しいデータのインポートのステータスを示します。 <p><span style="color:green">●</span>   **[!UICONTROL _x _オン]**データセットが新しいデータを読み込むように設定されている場合、および<p><span style="color:gray">●</span>   **[!UICONTROL _x オフ_]** データセットが新しいデータインポートをインポートしないように設定されている場合。 |
| [!UICONTROL データをバックフィル] | データセットのバックフィルデータのステータスを表示します。<p><span style="color:red">●</span>   **[!UICONTROL _x _バックフィルに失敗しました]**失敗したバックフィルの数<p><span style="color:orange">●</span>   **[!UICONTROL _x _バックフィル処理]**（バックフィル処理の数）<p><span style="color:green">●</span>   **[!UICONTROL _x _バックフィル完了]**完了したバックフィルの数、および<p><span style="color:grey">●</span>   **[!UICONTROL _オフ_]** バックフィルが設定されていない場合に備えて、<p>データセットの過去のバックフィルの概要を示すダイアログを表示するには、 <img src="./assets/pastbackfill.svg" alt="過去のバックフィル" width="2%" /> **[!UICONTROL 過去のバックフィル]**. |
| [!UICONTROL データソースタイプ] | データセットを接続に追加する際に定義されるデータソースタイプ。 |
| [!UICONTROL データセットタイプ] | [!UICONTROL イベント]、[!UICONTROL ルックアップ]、[!UICONTROL プロファイル]のいずれかです。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#configure-dataset) |
| [!UICONTROL スキーマ] | このデータセットの基になるExperience Platformスキーマを表示します。 |
| [!UICONTROL データセット ID] | このデータセット ID は、Experience Platformで生成されます。 |


>[!MORELIKETHIS]
>
>[接続設定の表示、トラブルシューティング、変更](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) チュートリアル
