---
title: Customer Journey Analytics での接続の管理方法
description: Customer Journey Analytics（Customer Journey Analytics）で Experience Platform データセットへの接続を管理する方法について説明します。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '4886'
ht-degree: 60%

---

# 接続の管理 {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="Journey Optimizer 接続の使用"
>abstract="Journey Optimizer で高度な Customer Journey Analytics レポート機能を活用します。"

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="Journey Optimizer 接続のキャンセル"
>abstract="Journey Optimizer で高度な Customer Journey Analytics レポート機能をキャンセルします。"


[1 つ以上の接続を作成または編集](/help/connections/create-connection.md)したら、**[!UICONTROL 接続]**&#x200B;で管理できます。[!UICONTROL &#x200B; 接続 &#x200B;] インターフェイスでは、次のことが可能です。

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

**[!UICONTROL リスト]**&#x200B;インターフェイスは、接続のデフォルトのインターフェイスです。選択されていない場合は、「**[!UICONTROL リスト]**」タブを選択してインターフェイスにアクセスします。

![リストビュー](assets/list-view.png)

[!UICONTROL &#x200B; リスト &#x200B;] インターフェイスには、使用可能なすべての接続のテーブルが表示されます。

### 接続を検索

検索 ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) ボックスを使用して、接続をすばやく検索できます。

### 接続のリストにフィルターを適用する

接続のリストにフィルターを適用するには、フィルターアイコンを選択してから、次のフィルターオプションから選択します。

| フィルターオプション | 説明 |
|---------|----------|
| **[!UICONTROL データセット]** | 選択したデータセットに関連付けられている接続のみが表示されます。 |
| **[!UICONTROL 所有者]** | 選択したユーザーが所有する接続のみが表示されます。 |
| **[!UICONTROL サンドボックス]** | 選択したサンドボックスで使用可能な接続のみが表示されます。 |
| **[!UICONTROL CJAでの使用]** | 「**[!UICONTROL オン]**」を選択すると、Customer Journey Analyticsで使用できる接続のみが表示されます。 **[!UICONTROL オフ]** を選択すると、Customer Journey Analyticsでの使用がまだ有効になっていない接続のみを表示します。 |

### 使用可能な列

テーブルでは、次の列またはアイコンを使用できます。

| 列またはアイコン | 説明 |
| --- | --- |
| **[!UICONTROL _名前_]** | 接続のわかりやすい名前です。ハイパーリンク名を選択して [&#x200B; 接続の詳細 &#x200B;](#connection-details) を表示します。 |
| ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | [!UICONTROL 含まれるデータセット]、[!UICONTROL サンドボックス]、[!UICONTROL 所有者]などの情報を表示するには、接続名の横にある ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) を選択します。<p>ポップアップウィンドウにデータセットの詳細が表示されます。 <p>![&#x200B; 接続情報のポップアップ &#x200B;](assets/connection-info-popup.png) |
| ![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 接続の[データビューを作成](#create-a-data-view)するには、![データビュー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) を選択します。このアイコンは、接続にデータビューがまだ関連付けられていない場合にのみ表示されます。 |
| ![詳細情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | ![&#x200B; 詳細 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択して、コンテキストメニューを開きます。 以下を選択できます。 <p>接続を ![&#x200B; 編集 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)**[!UICONTROL 編集]** して [&#x200B; 編集 &#x200B;](#edit-a-connection) します。<p>接続を ![&#x200B; 削除 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL 削除]** して [&#x200B; 削除 &#x200B;](#delete-a-connection) します。<p>![&#x200B; データビュー &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)**[!UICONTROL 新しいデータビューを作成]** して、接続の [&#x200B; 新しいデータビューを作成 &#x200B;](#create-a-data-view) します。<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Connection map]**：接続の [&#x200B; 接続マップ &#x200B;](#map-a-connection) を表示 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL &#x200B; 接続の種類 &#x200B;]** | 接続のタイプ：**[!UICONTROL ユーザー]** ベースまたは **[!UICONTROL アカウント]** ベースの接続。 |
| **[!UICONTROL データセット]** | 接続の一部であるデータセットへの 1 つ以上のリンク。データセットのハイパーリンクを選択すると、接続内のデータセットを表示できます。選択した接続にさらにデータセットを含める場合は、「**[!UICONTROL +*x* 以上]**」を選択して、**[!UICONTROL 含まれるデータセット]**&#x200B;パネルを表示します。このパネルには、すべてのデータセットへのリンクと、接続の一部である特定のデータセットを ![&#x200B; 検索 &#x200B;](/help/assets/icons/Search.svg) 検索」するオプションが表示されます。<p>![&#x200B; 含まれるデータセット &#x200B;](assets/datasets-included.png)<p>データセット名を選択して、Experience Platform インターフェイスの新しいタブでデータセットを開きます。 |
| **[!UICONTROL サンドボックス]** | この接続がデータセットを取得する [Experience Platform サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)。このサンドボックスは、接続を作成した際に選択します。 接続が保存されると、サンドボックスを変更できなくなります。 |
| **[!UICONTROL 所有者]** | 接続を作成したユーザー。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![&#x200B; ステータスが緑 &#x200B;](assets/status-green.svg)   **[!UICONTROL _x _On]**：新しいデータを読み込むように設定されたデータセットの場合<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：新しいデータを読み込むように設定されていないデータセットの場合。 |
| **[!UICONTROL 作成日]** | 接続が作成されたときのタイムスタンプ。 |
| **[!UICONTROL 最終変更日]** | 接続が最後に更新されたときのタイムスタンプ。 |
| **[!UICONTROL データをバックフィル]** | データセットをまたいだバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：データセットをまたいで失敗したバックフィルの数の場合。<p>![ステータス（オレンジ色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：データセットをまたいで処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：データセットをまたいで完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：接続内のデータセットに対してバックフィルが定義されていない場合。 |
| **[!UICONTROL 統合]** | この接続が有効になっているExperience Platform アプリケーションを表示します。 |
| **[!UICONTROL CJAでの使用]** | 接続がCustomer Journey Analyticsでの使用に対して有効になっているかどうかを示します。 |

テーブルに表示する列を設定するには、「![&#x200B; 列設定 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」を選択します。 テーブルをカスタマイズダイアログで、表示する列を選択します。

### 接続の編集

接続を編集するには：

1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します
1. コンテキストメニューから ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青いアクションバーから ![&#x200B; 編集 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)**[!UICONTROL 編集]** を選択します。

詳しくは、[接続の作成または編集](create-connection.md)を参照してください。


### 接続の削除 {#connections-delete}

接続を削除するには：

1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
1. ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 削除]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青いアクションバーから ![&#x200B; 削除 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL 削除]** を選択します。

接続を削除すると、削除されたデータビューと影響を受けるワークスペースプロジェクトが&#x200B;**[!UICONTROL 接続を削除]**&#x200B;パネルに表示されます。

* ➊Info **&#x200B;**&#x200B;は、接続が削除された場合の影響が示されています。

  ![接続を削除](assets/delete-connection.png)

  「**[!UICONTROL 続行]**」を選択して、削除を確定します。

* ➋&#x200B;**[!UICONTROL 確認]**」で「**[!UICONTROL 接続名を入力]**」に接続の名前を入力し、「**[!UICONTROL 削除]**」を選択して接続を削除します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

接続の削除について詳しくは、[削除の影響](/help/technotes/deletion.md)を参照してください。


### 接続のデータビューの作成

接続のデータビューを作成するには：

1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
1. ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 新しいデータビューを作成]** を選択します。

または、次の操作を実行できます。

1. 接続行を選択します。

1. 青いアクションバーから ![&#x200B; データビューを追加 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)**[!UICONTROL データビューを作成]** を選択します。

詳しくは、[データビューの作成または編集](/help/data-views/create-dataview.md)を参照してください。

### Journey Optimizer接続

Customer Journey AnalyticsのJourney Optimizer接続を使用して、接続に次のような付加価値を付加できます。

* Customer Journey Analytics内でJourney Optimizer データの詳細な分析を実行します（Journey Optimizer内の「**[!UICONTROL CJAで分析]** ボタンを使用）。

  詳しくは、Journey Optimizer ドキュメントの [Customer Journey Analyticsでの分析 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/reporting/channel-report/report-cja-manage#cja-template) を参照してください。

* Journey Optimizer接続および関連するデータビューを編集します。

  オプションの編集について詳しくは、[&#x200B; 接続の編集 &#x200B;](#edit-a-connection) を参照してください。


>[!IMPORTANT]
>
>この節で説明するように、Journey Optimizer接続をCustomer Journey Analyticsで使用できるようにすると、接続内の各行は、Customer Journey Analyticsで毎月ライセンス供与されたデータ行にカウントされ、接続使用状況 UI に表示されます。 Customer Journey Analyticsでのデータ行の使用に慣れている場合にのみ、接続の **[!UICONTROL CJAで使用]** オプションを選択してください。
>
>**2024 年 10 月から 2025 年 10 月の間にCustomer Journey AnalyticsとJourney Optimizerの両方の権利が付与された場合、[AJOが有効な接続 &#x200B;](https://view.adobe.com/viewer/1ed94fc35c7860b260766c620889e7a0#1)** に関する次のドキュメントを参照してください。

この機能を有効にするには、Customer Journey Analyticsへのアクセス権が必要です。 アクセス権がない場合は、Adobeの営業担当にお問い合わせください。

#### Journey Optimizer接続を使用 {#use-connection-in-cja}

Customer Journey AnalyticsでJourney Optimizer接続を使用するには：

1. Customer Journey Analyticsで使用するJourney Optimizer接続を見つけます。

   1. 「![&#x200B; 接続 &#x200B;](/help/assets/icons/Filter.svg)」タブで「**[!UICONTROL フィルター]** **[!UICONTROL フィルター]**」を選択します。

   1. **[!UICONTROL CJAで使用]** セクションで、「**[!UICONTROL オフ]**」を選択します。

      Customer Journey Analyticsで使用するように現在設定されていないすべてのJourney Optimizer接続が表示されます。

      ![AJOで有効になっていない接続を表示するフィルター &#x200B;](assets/remove-ajo-connection.png)

1. Journey Optimizer接続の名前を選択します。

1. ![CJAで UsersShare](/help/assets/icons/UseInCJA.svg) 使用 **[!UICONTROL を選択]** ます。

   ![&#x200B; 「CJAで使用」ボタン &#x200B;](assets/connection-use-in-cja.png)

   **[!UICONTROL Customer Journey Analyticsでこの接続を使用]** ダイアログが表示されます。

1. **[!UICONTROL CJAで接続を使用]** トグルを有効にします。

1. 「**[!UICONTROL 接続を使用]**」を選択します。<!-- double-check these dialog button names -->

#### Journey Optimizer接続の削除 {#remove-connection-in-cja}

Customer Journey AnalyticsからJourney Optimizerへの接続は、いつでも削除できます。 ただし、使用後にCustomer Journey Analyticsから接続を削除すると、次のような結果になります。

* Journey Optimizer接続と関連するすべてのデータビューがデフォルトのステートにリセットされ、編集できなくなります

* 接続に関連付けられているカスタム派生フィールドはすべて削除されます。

* Customer Journey Analytics内でJourney Optimizer データの詳細な分析を実行できなくなりました。

  つまり、Journey Optimizerの **[!UICONTROL CJAで分析]** ボタンは無効になっています。

>[!IMPORTANT]
>
>Customer Journey Analyticsの接続に対する請求には、接続が削除された 1 か月が含まれます。


Customer Journey Analyticsから接続を削除するには：

1. Customer Journey Analyticsから削除するJourney Optimizer接続を見つけます。

   1. 「![&#x200B; 接続 &#x200B;](/help/assets/icons/Filter.svg)」タブで「**[!UICONTROL フィルター]** **[!UICONTROL フィルター]**」を選択します。

   1. **[!UICONTROL CJAで使用]** セクションで、「**[!UICONTROL オン]**」を選択します。

      Customer Journey Analyticsで使用するように現在設定されているすべてのJourney Optimizer接続が表示されます。

      ![AJOで有効な接続を表示するようにフィルター &#x200B;](assets/enabled-ajo-connection.png)

1. 接続を表示するには、Customer Journey Analyticsから削除するJourney Optimizer接続の名前を選択します。

1. Journey Optimizer接続を表示する際に、「**[!UICONTROL CJAから削除]**」を選択します。

   **[!UICONTROL Customer Journey Analyticsからこの接続を削除]** ダイアログが表示されます。

   ![&#x200B; 「CJAから削除」ボタン &#x200B;](assets/connection-remove-from-cja.png)

1. 「**[!UICONTROL CJAから接続を削除]**」オプションを無効にします。

1. **[!UICONTROL 接続を削除]** を選択します。

### 接続のマッピング

接続の一部であるデータセット間の関係の詳細を示す[接続マップ](/help/connections/create-connection.md#connection-map)を表示するには：

1. 接続名の横にある ![その他](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択します。
1. ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 接続マップ]** を選択します。

### 接続の詳細 {#connection-detail}

接続の詳細に移動するには、接続テーブルでハイパーリンクされた接続名を選択します。

![ウィジェットと設定を示すすべてのデータセットウィンドウ](assets/conn-details.png)

接続の詳細インターフェイスでは、接続のステータスの詳細なビューが提供されます。次のことができます。

* 接続データセットのステータスと取り込みプロセスのステータスを確認します。
* レコードのスキップや削除の原因となる可能性のある設定の問題を識別します。
* データをレポートに使用できるタイミングを確認します。

| ユーザーインターフェイス | 説明 |
| --- | --- |
| ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 接続を編集]** | 接続の詳細を編集するには、![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 接続を編集]** を選択します。詳しくは、[接続の作成または編集](create-connection.md)を参照してください。 |
| **[!UICONTROL *データセットセレクター&#x200B;*]** | 接続の詳細を表示する 1 つまたはすべてのデータセットを選択します。 複数のデータセットを選択することはできません。デフォルトは&#x200B;**[!UICONTROL すべてのデータセット]**&#x200B;です。 |
| **[!UICONTROL *日付範囲セレクター&#x200B;*]** | 接続の詳細を表示するデータ範囲を選択します。 開始日、終了日を編集するか、![カレンダー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) を選択して日付範囲セレクターを開きます。日付範囲セレクターで、定義済みの期間の 1 つ（例：**[!UICONTROL 過去 6 か月間]**）を使用して日付範囲を選択するか、カレンダーを使用して開始日と終了日を選択します。「**[!UICONTROL 適用]**」を選択して、新しい日付範囲を接続の詳細に適用します。 |
| **[!UICONTROL 使用可能なイベントデータのレコード]** | **接続全体について**、レポートに使用できるイベントデータセット行の合計数。この数は、日付範囲やデータセットの選択とは無関係です。 |
| [!UICONTROL **[!UICONTROL 指標]**] | 追加、スキップおよび削除されたイベント、ルックアップ、プロファイル、概要データセットレコードと、追加されたバッチの数を要約します。これらの指標は、**選択したデータセットと日付範囲** に基づいています。<p>「**[!UICONTROL 詳細を確認]**」を選択すると、**[!UICONTROL スキップされた詳細を確認]**&#x200B;ポップアップが表示されます。ポップアップには、すべてのイベントデータセットまたは選択したデータセットのスキップされたレコードの数と理由が一覧表示されます。<p>![&#x200B; スキップされたレコード &#x200B;](assets/skipped-records.png)<p>詳細情報が表示されている ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ポップアップを選択します。[!UICONTROL &#x200B; 空の訪問者 ID] などの理由でスキップされた場合、ポップアップに **[!UICONTROL EQS のサンプル PSQL]** （クエリサービスのExperience Platform）が表示され、[&#x200B; クエリサービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home) で使用して、データセット内のスキップされたレコードをクエリできます。 ![コピー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL EQS 用サンプル PSQL をコピー]** を選択して SQL をコピーします。 |
| **[!UICONTROL 追加されたレコード]** | **選択したデータセットと日付範囲に** して、選択した期間に追加された行数を示すビジュアライゼーション。 10 分ごとに更新されます。 |
| **[!UICONTROL スキップされたレコード]** | **選択したデータセットと日付範囲** で、選択した期間にスキップされた行数を示すビジュアライゼーション。 レコードをスキップした理由には、タイムスタンプの欠落、ユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} の欠落または無効などがあります。 10 分ごとに更新されます。 <p>無効な ID （`undefined`、`00000000` または特定の月に 100 万回を超えるイベントに表示される[!UICONTROL ユーザー ID] 内の数字と文字の組み合わせなど）は、特定のユーザーに関連付けることができない ID です。これらの行はシステムに取り込むことができないので、取り込みやレポートでエラーが発生しやすくなります。無効な人物 ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} を修正するには、次の 3 つのオプションがあります。<ul><li>[ステッチ](/help/stitching/overview.md)を使用して、未定義またはすべてがゼロのユーザー ID に有効なユーザー ID を入力する。</li><li>ユーザー ID を空白にする。この ID は取り込み時にスキップされます（ユーザー ID が無効またはすべてゼロとなっているよりも望ましい）。</li><li>データを取り込む前に、システム内の無効なユーザー ID を修正する。</li></ul> |
| **[!UICONTROL 削除されたレコード]** | **選択したデータセットと日付範囲** で、選択した期間に削除された行数を示すビジュアライゼーション。 例えば、[!DNL Experience Platform] でデータセットが削除された可能性があるとします。10 分ごとに更新されます。<p>シナリオによっては、ステッチや一部のルックアップデータセットの更新などにより、この値に置き換えられたレコードが含まれる場合もあります。この例では、次を考慮します。</p><ul><li>1 つのレコードを XDM 個人プロファイルデータセットにアップロードします。これにより、Customer Journey Analytics がプロファイルルックアップデータとして取り込むように設定されます。接続の詳細では、このデータセットには 1 つのレコードが追加されたと表示されます。</li><li>元のレコードの複製を同じ AEP データセットにアップロードします。これにより、2 つのレコードが含まれるようになります。 Customer Journey Analytics では、プロファイルまたはアカウント [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} ルックアップデータセットから追加のレコードを取り込みます。プロファイルまたはアカウントレコードが、そのユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} の接続に既に取り込まれているのを確認すると、Customer Journey Analyticsは以前のバージョンを削除して、新しいプロファイルデータを追加します。 Customer Journey Analyticsでは、取り込まれたユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} の最新のプロファイル参照データのみが保持されるので、接続詳細では、このアクションは、追加されたレコード 1 件と削除されたレコード 1 件を表します。</li><li>合計すると、AEP データセットには同一の 2 つのレコードが含まれます。 これとは別に、Customer Journey Analytics 接続の詳細には、このプロファイルデータセットに対して 2 つのレコードが追加され、1 つのレコードが削除されました、という取り込まれたデータのステータスが表示されます。 </li></ul> |
| ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | データセット検索フィールド。データセット名またはデータセット ID でデータセットテーブルを検索できます。 |
| [!UICONTROL データセットテーブル] | 接続に含まれるデータセットです。詳しくは、次の表を参照してください。 選択したデータセットの接続の詳細のみを表示するには、1 つのデータセットを ![SelectBox](/help/assets/icons/SelectBox.svg) 選択します。 これは、**[!UICONTROL _データセットセレクター_]** からデータセットを選択することに相当します。 |

データセットテーブルには、各データセットに関する次の列が表示されます。

| 列 | 説明 |
| --- | --- |
| **[!UICONTROL データセット]** | データセットの名前。ハイパーリンクを選択すると、Experience Platform UI の新しいタブでデータセットを開くことができます。行を選択するか、チェックボックスをオンにすると、選択したデータセットの詳細のみを表示できます。 |
| **[!UICONTROL データセット ID]** | Experience Platformで生成されたデータセット ID。 |
| **[!UICONTROL 追加されたレコード]** | 選択した日付範囲で接続に追加されたデータセットレコード（行）の数。 |
| **[!UICONTROL スキップされたレコード]** | 選択した日付範囲で、接続のデータ転送中にスキップされたデータセットレコード （行）の数。 |
| **[!UICONTROL 削除されたレコード]** | 選択した日付範囲で接続から削除されたデータセットレコード （行）の数。 |
| **[!UICONTROL 追加されたバッチ]** | 選択した日付範囲内に接続に追加されたバッチの数。 |
| **[!UICONTROL 前回追加した日時]** | 接続に追加された最新のバッチのタイムスタンプ。 |
| **[!UICONTROL データソースタイプ]** | ソースタイプ。 ソースタイプは、データセットを接続に追加する際に定義します。 |
| **[!UICONTROL データセットタイプ]** | [&#x200B; データセットタイプ &#x200B;](create-connection.md#dataset-types)。 タイプは **[!UICONTROL イベント]**、**[!UICONTROL プロファイル]**、**[!UICONTROL ルックアップ]**、**[!UICONTROL 概要]** です。 アドホックまたはリレーショナルデータセットは、**[!UICONTROL （アドホック）]** または **[!UICONTROL （リレーショナル）]** によって識別されます。 例えば、**[!UICONTROL イベント （アドホック）]** または **[!UICONTROL ルックアップ （リレーショナル）]** です。 |
| **[!UICONTROL スキーマ]** | データセットのベースとなる Experience Platform スキーマ。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：データセットが新しいデータを読み込むように設定されている場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：データセットが新しいデータを読み込むように設定されていない場合。 |
| **[!UICONTROL データセットを変換]** | 適用可能な B2B ルックアップデータセットの変換ステータス。詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：変換に対して有効である適用可能なデータセットの場合。 <p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：変換に対して有効でない適用可能なデータセットの場合。<p>**[!UICONTROL 該当なし]**：変換に対して適用可能でない他のすべてのデータセットの場合。 |
| **[!UICONTROL データをバックフィル]** | データセットのバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：失敗したバックフィルの数の場合。<p>![ステータス（赤色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：バックフィルが定義されていない場合。 |

>[!IMPORTANT]
>
>2021年8月13日（PT）より前に取り込まれたデータは、[!UICONTROL 接続]インターフェイスに反映されません。
>

#### 接続パネル

データセットテーブルで個々のデータセットが選択されていない場合、右側のパネルには接続オプションと詳細が表示されます。

| オプション | 説明 |
| --- | --- |
| ![更新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 更新]** | 接続を更新し、最近追加されたレコードを反映するには、![更新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 更新]** を選択します。 |
| ![削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)、**[!UICONTROL 削除]** | この接続を[削除](#delete-a-connection)します。 |
| ![データビューを追加](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL データビューを作成]** | この接続に基づいて[データビューを作成します](#create-a-data-view)。詳しくは、[データビュー](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/data-views)を参照してください。 |
| **[!UICONTROL CJAでの使用]** | Customer Journey AnalyticsのJourney Optimizer接続を使用すると、Journey Optimizer接続にさらなる価値をもたらします。 詳しくは、[Customer Journey AnalyticsでのJourney Optimizer接続の使用 &#x200B;](#use-a-journey-optimizer-connection-in-customer-journey-analytics) を参照してください。 |
| **[!UICONTROL 接続名]** | 接続のわかりやすい名前。 |
| **[!UICONTROL 接続の説明]** | この接続の目的を説明するより詳細な説明。 |
| **[!UICONTROL サンドボックス]** | この接続がデータセットを取得する [Experience Platform サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)。このサンドボックスは、接続を作成した際に選択します。 接続が保存されると、サンドボックスを変更できなくなります。 |
| **[!UICONTROL 接続 ID]** | 接続に対して生成された識別子。 ![&#x200B; コピー &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) を使用して、値をコピーできます。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL プライマリID の種類 &#x200B;]** | 接続のプライマリ ID タイプ：ユーザーベースの接続の場合は **[!UICONTROL Person]**、アカウントベースの接続の場合は **[!UICONTROL Account]**。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL &#x200B; コンテナ &#x200B;]** | 接続に対して設定されたコンテナ。 |
| **[!UICONTROL 接続を使用するデータビュー]** | この接続を使用するデータビュー。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：データセットの数が新しいデータを読み込むように設定されている場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：新しいデータ読み込みがオフになっているデータセットの数の場合。 |
| **[!UICONTROL データをバックフィル]** | データセットのバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：データセットをまたいで失敗したバックフィルの数の場合。<p>![ステータス（赤色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：データセットをまたいで処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：データセットをまたいで完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：接続内のデータセットに対してバックフィルが定義されていない場合。 |
| **[!UICONTROL データセットを変換]** | 適用可能な B2B ルックアップデータセットの変換ステータス。詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：変換に対して有効であるデータセットの数の場合。 |
| **[!UICONTROL 作成者]** | クエリを作成したユーザーの名前。 |
| **[!UICONTROL 最終変更日]** | 接続に対する最後の変更のタイムスタンプ。 |
| **[!UICONTROL 最終変更者]** | 接続を最後に変更したユーザーの名前。 |

#### データセットパネル

データセットテーブルでデータセット行を選択すると、接続インターフェイスの右側のパネルに、選択したデータセットの詳細が表示されます。

| 詳細 | 説明 |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL グローバルアカウント ID &#x200B;]** | 接続のグローバルアカウント ID として指定した ID。 グローバルアカウントコンテナが設定されているアカウントベースの接続にのみ適用できます。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL アカウント ID &#x200B;]** | 接続のアカウント ID として指定した ID。 グローバルアカウントコンテナが設定されていないアカウントベースの接続にのみ適用できます。 |
| **[!UICONTROL ユーザー ID]** | 接続のユーザー ID として指定した ID。 |
| **[!UICONTROL キー]** | ルックアップデータセットに指定したキー。 |
| **[!UICONTROL 一致するキー]** | ルックアップデータセットに指定した一致するキー。 |
| **[!UICONTROL タイムスタンプ]** | イベントデータセットに定義されたタイムスタンプ。 |
| **[!UICONTROL 使用可能なレコード]** | カレンダーを通じて選択された特定の期間に、このデータセットに対して取り込まれた行の合計数。データが追加されると、レポートに表示されるデータの取得に遅延は発生しません。ただし、最新の接続を作成すると、[遅延](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq)が発生します。 |
| **[!UICONTROL 追加されたレコード]** | 選択した日付範囲で接続に追加されたデータセットレコード（行）の数。 |
| **[!UICONTROL スキップされたレコード]** | 選択した日付範囲で、接続のデータ転送中にスキップされたデータセットレコード （行）の数。 |
| **[!UICONTROL 追加されたバッチ]** | 接続に追加されたバッチの数。 |
| **[!UICONTROL 削除されたレコード]** | 選択した日付範囲で接続から削除されたデータセットレコード （行）の数。 |
| **[!UICONTROL 前回追加した日時]** | 接続に追加された最新のバッチのタイムスタンプ。 |
| **[!UICONTROL 新しいデータをインポート]** | データセットの新しいデータの読み込みのステータス： <p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _オン]**：データセットが新しいデータを読み込むように設定されている場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _x オフ_]**：データセットが新しいデータを読み込むように設定されていない場合。 |
| **[!UICONTROL データをバックフィル]** | データセットのバックフィルデータのステータス。<p>![ステータス（赤色）](assets/status-red.svg) **[!UICONTROL _x _バックフィル失敗]**：失敗したバックフィルの数の場合。<p>![ステータス（赤色）](assets/status-orange.svg) **[!UICONTROL _x _バックフィル処理中]**：処理中のバックフィルの数の場合。<p>![ステータス（緑色）](assets/status-green.svg) **[!UICONTROL _x _バックフィル完了]**：完了したバックフィルの数の場合。<p>![ステータス（グレー）](assets/status-gray.svg) **[!UICONTROL _オフ_]**：バックフィルが定義されていない場合。<p>データセットの過去のバックフィルの概要を示すダイアログを表示するには、 <img src="./assets/pastbackfill.svg" alt="過去のバックフィル" width="15"/> **[!UICONTROL 過去のバックフィル]** を選択します。 |
| **[!UICONTROL データソースタイプ]** | データセットが接続に追加されたときに定義されたデータソースタイプ。 |
| **[!UICONTROL データセットタイプ]** | [&#x200B; データセットタイプ &#x200B;](create-connection.md#dataset-types)。 タイプは **[!UICONTROL イベント]**、**[!UICONTROL プロファイル]**、**[!UICONTROL ルックアップ]**、**[!UICONTROL 概要]** です。 アドホックまたはリレーショナルデータセットは、**[!UICONTROL （アドホック）]** または **[!UICONTROL （リレーショナル）]** によって識別されます。 例えば、**[!UICONTROL イベント （アドホック）]** または **[!UICONTROL ルックアップ （リレーショナル）]** です。 |
| **[!UICONTROL スキーマ]** | このデータセットのベースとなる Experience Platform スキーマ。 |
| **[!UICONTROL データセット ID]** | Experience Platformで生成されたデータセット ID。 |


## 使用状況 {#connections-usage}

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="主要な使用状況指標"
>abstract="コアおよび履歴のレポート可能行数の月別および合計データを指定します。"

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="月別の取り込み行数"
>abstract="月別にシステムに追加されるレコードの合計数を測定し、データの増加と取り込み率に関するインサイトを指定します。"

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="月別のレポート可能行数"
>abstract="レポートに使用できる行数を追跡します。 レポート可能行数とは、取り込まれた行数から、取り込み中にスキップおよび削除された行数を除いたものです。レポート可能行数は、課金とデータ使用量の主要な指標として機能します。"

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="詳細な分類。"
>abstract="データの CSV ファイルをダウンロードするオプションを使用して、接続別、データセット別、サンドボックス別、タグ別に詳細な指標を表示できます。"

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="その他のデータセット"
>abstract="2024年9月より前の数か月間については、データはデータセットレベルで収集され、わかりやすくするために&#x200B;*その他のデータセット*&#x200B;として表示されます。2024年9月以降、データは詳細なデータセットレベルで収集され、*その他のデータセット*&#x200B;は表示されなくなります。"

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="不明なデータセットまたは接続"
>abstract="不明なデータセットまたは接続は、ID を使用して表示されます。"

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="データは使用できません"
>abstract="システムの制限により、2024年9月より前の履歴データは使用できません。指標は、2024年9月以降に収集され、表示されます。グラフには過去 18 か月のタイムラインが表示され、データが利用可能になると今後のデータが表示されます。"

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="コアのレポート可能な行数"
>abstract="先月と比較した変化率を含む、今月の過去 13 か月にわたって使用可能な行の合計数。例えば、2024年2月1日（PT）の数は、2023年1月から 2024年1月までのイベントタイムスタンプで使用できる行の合計数を示します。"

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="履歴のレポート可能な行数"
>abstract="今月の 13 か月を超える期間で使用可能な行の合計数と、先月と比較した変化率。例えば、2024年2月1日（PT）の数値は、2023年1月より古いイベントタイムスタンプで使用できる行の合計数を示します。"


>[!CONTEXTUALHELP]
>id="connections_averagerowsize"
>title="平均行サイズ"
>abstract="今月取り込まれ、保存されたデータの各行によって消費されたストレージの平均量（KB 単位）と、前月と比較した変化率。"


>[!CONTEXTUALHELP]
>id="connections_coredatavolume"
>title="コアデータボリューム"
>abstract="前月と比較した変化率を含む、今月のタイムスタンプが付けられたディスクに保存されたデータの合計量（TB 単位）。"


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


[!UICONTROL 使用状況]インターフェイスには、すべての接続で取り込まれた行とレポート可能な行の使用状況が表示されます。選択されていない場合は、「**[!UICONTROL 使用状況]**」タブを選択してインターフェイスにアクセスします。

このインターフェイスは、Customer Journey Analytics の使用状況が契約上の合意事項に準拠しているかどうかを判断するのに役立ちます。監視目的に加えて、使用状況インターフェイスを使用して、Customer Journey Analytics ライセンスの更新を計画することもできます。

使用状況インターフェイスでは、次の指標を使用します。

| Metric name | 説明 |
|---|---|
| **レポート可能な行の履歴** | 13 か月を超える期間の行数。 |
| **コアレポート可能行** | 過去 13 か月間の行数。 |
| **コアデータ量** | ディスクに保存されているデータの総量。 |
| **行の平均サイズ** | 取り込まれて保存されたデータの行ごとに消費されたストレージの平均量。 |
| **取り込まれた行数** | 特定の期間に取り込まれた行数。 |
| **レポート可能な行数** | 特定の期間の接続の一部として保持されるデータの行数。 |
| **累積行** | 特定の月までに取り込まれた行数。 |

>[!NOTE]
>
>データは、2024年7月からコア、履歴、合計レコードについて収集されます。以前の履歴データについては、アドビ担当営業または販売店にお問い合わせください。
>

使用状況インターフェイスは、次の 2 つのパネルで構成されます。

* 次の項目を表示する **[!UICONTROL 主要使用状況指標]** パネル。

   * 次の場合に、前月からの合計およびパーセント変更を表示する 4 つの概要ビジュアライゼーション

      * **[!UICONTROL コアデータのレポート可能な行]**。 先月と比較して変更された割合を使用した、当月の過去 13 か月で使用可能な行の合計数。 例えば、2024年2月1日（PT）の数は、2023年1月から 2024年1月までのイベントタイムスタンプで使用できる行の合計数を示します。
      * **[!UICONTROL 履歴データレポート可能な行]**。 今月の 13 か月を超える期間で使用可能な行の合計数と、先月と比較した変化率。例えば、2024年2月1日（PT）の数値は、2023年1月より古いイベントタイムスタンプで使用できる行の合計数を示します。
      * **[!UICONTROL コアデータ量]**。 前月と比較した変化率を含む、今月のタイムスタンプが付けられたディスクに保存されたデータの合計量（TB 単位）。
      * **[!UICONTROL 行の平均サイズ]**。 今月取り込まれ、保存されたデータの各行によって消費されたストレージの平均量（KB 単位）と、前月と比較した変化率。

   * 過去 13 か月間の **[!UICONTROL コアデータと履歴データのレポート可能な行]** を表示する、積み重ね縦棒ビジュアライゼーション。

     ビジュアライゼーション内の積み重ね棒の上にマウスポインターを置くと、棒の特定の部分の行数がポップアップに表示されます。 次の例では、当月（2025 年 8 月：936M （936,347,325））のコアデータのレポート可能な行を示しています。


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

  2024年9月より前の数か月間については、データはデータセットレベルで収集され、わかりやすくするために[!UICONTROL その他のデータセット]として表示されます。2024 年 9 月以降、データはきめ細かいデータセットレベルで収集され、[!UICONTROL &#x200B; その他のデータセット &#x200B;] は表示されなくなります。

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
>[Customer Journey Analytics の使用状況の管理](/help/technotes/estimate-usage.md)
>
