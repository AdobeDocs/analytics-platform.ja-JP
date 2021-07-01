---
title: 接続の管理
description: Customer Journey Analytics(CJA)でExperience Platformデータセットへの接続を管理する方法について説明します。
mini-toc-levels: 3
source-git-commit: fb0b35173d7a2b0daa17c34272b2b2b271095f4a
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 8%

---

# 接続の管理

管理者ユーザーは、[1つ以上の接続](/help/connections/create-connection.md)を作成したら、[!UICONTROL 接続]マネージャーでそれらを管理できます。 接続エクスペリエンスの最新の更新により、接続の詳細ページに2つの重要な機能が追加されました。詳しくは、このページで詳しく説明します。

* 接続のデータセットとインジェストプロセスの&#x200B;**ステータスを確認できます。**&#x200B;このステータスチェックを使用すると、データが使用可能になったタイミングを把握して、Analysis Workspaceに移動して分析を開始できます。

* これにより、設定ミスに起因するデータの相違&#x200B;**を識別できます。**&#x200B;何か足りない？ 「はい」の場合、欠落している行と理由 接続の設定が誤っていて、CJAにデータが欠落している原因は何ですか。

>[!NOTE]
> この機能は、2021年7月27日に一般に提供されます。

## 接続マネージャ {#connections-manager}

接続マネージャでは、次の操作を実行できます。

* 所有者、サンドボックス、接続の作成日時や変更日時など、すべての接続を一目で表示します。
* 接続内のすべてのデータセットを表示します。
* 接続のステータスを確認します。
* 接続を削除する。
* 接続名を変更する。
* 接続からデータビューを作成する。

![接続の管理](assets/conn-manager.png)

| 設定 | 説明 |
| --- | --- |
| [!UICONTROL 名前] | 接続のわかりやすい名前。 ハイパーリンク名をクリックすると、以下に説明する接続の詳細ページに移動します。 |
| 接続情報 | 接続名の横にある情報アイコンをクリックして、次の情報を表示します。![接続情報を表示](assets/conn-info.png) |
| 接続の編集 | 接続名の横の省略記号(...)をクリックし、「[!UICONTROL 編集]」をクリックします。![接続を](assets/conn-edit-delete.png) 編集詳しくは、以下の「接続を編集」を参照してください。 |
| 接続の削除 | 接続名の横の省略記号(...)をクリックし、「[!UICONTROL 削除]」をクリックします。 詳しくは、以下の「接続の削除」の見出しを参照してください。 |
| データビューを作成 | 接続名の横にある省略記号(...)をクリックし、「[!UICONTROL データビューを作成]」をクリックします。 このアクションは、この接続に基づいて新しいデータビューを作成します。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL データセット] | 接続に含まれるデータセット。 ハイパーリンクをクリックすると、接続内のすべてのデータセットを表示できます。 データセットをクリックすると、Adobe Experience Platformでそのデータセットが新しいタブで開きます。 |
| [!UICONTROL サンドボックス] | この接続がデータセットを作成する[Adobe Experience Platformサンドボックス](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en)。 このサンドボックスは、接続を初めて作成したときに選択されています。 変更はできません。 |
| [!UICONTROL 所有者] | 接続を作成したユーザー。 |
| [!UICONTROL データセットの読み込み] | 以前の「データストリーミング」を有効または無効にできます。 |
| [!UICONTROL 作成日] | 接続が最初に作成された日付。 |
| [!UICONTROL 最終変更日] | 接続が最後に更新された日付。 |

### 接続の削除 {#connections-delete}

管理者のみが接続を削除する権限を持っています。 このアクションは、管理者以外には表示されません。

1. 接続名の横にある省略記号(...)をクリックします。
1. [!UICONTROL 削除] をクリックします。

[!UICONTROL Customer Journey Analytics]で接続を削除すると、次の内容を示すエラーメッセージが表示されます。

* 削除した接続に基づいて作成されたデータビューは機能しなくなります。
* 同様に、削除した接続のデータビューに依存する Workspace プロジェクトは動作しなくなります。

[削除の影](/help/getting-started/cja-deletion.md) 響について詳しく説明します。

### 接続またはデータセットの検索

上部の[!UICONTROL 接続]タイトルの下にある検索バーを使用して、接続を検索できます。

### 接続の並べ替え

各列ヘッダーをクリックし、上または下に並べ替えることで、接続を並べ替えることができます。

## 接続の詳細ページ {#connection-detail}

新しい接続の詳細ページには、接続のステータスに関する非常に詳細な情報が表示されます。

次の操作が可能です。

* 接続のデータセットのステータスと取り込みプロセスのステータスを確認します。
* スキップまたは削除されたレコードを引き起こす設定の問題を特定します。
* データがレポートに使用できるタイミングを確認します。

以下に、ウィジェットと設定の説明を示します。

![接続の詳細の表示](assets/conn-details.png)

| ウィジェット/設定 | 説明 |
| --- | --- |
| データセット selector | 接続内の1つまたはすべてのデータセットを選択できます。 データセットを複数選択することはできません。 デフォルトは[!UICONTROL すべてのデータセット]です。 |
| カレンダー/日付範囲 | 日付範囲は、接続にデータを追加した日時を示します。 すべての標準カレンダープリセットが含まれています。 日付範囲はカスタマイズできますが、ドロップダウンにはカスタム日付範囲は表示されません。 |
| [!UICONTROL 使用可能なレコ] ードウィジェット | レポートに使用できる行の合計数を表します。**は、接続全体**&#x200B;の行数です。 この数は、カレンダーの設定とは無関係です。 データセットセレクターからデータセットを選択するか、テーブル内のデータセットを選択すると、データセットが変わります。 （データが追加されると、データがレポートに表示されるまでに1 ～ 2時間の遅延が生じます。） |
|  Metricswidget | 追加/スキップ/削除したレコードと、選択したデータセットと日付範囲&#x200B;**に対して追加されたバッチ数**&#x200B;の概要を示します。 |
| [!UICONTROL レコードの] 追加ウィジェット | 選択した期間に追加された行数（**を選択したデータセットと日付範囲の**）を示します。 10分ごとに更新されます。 |
| [!UICONTROL スキップされた] ウィジェット | 選択した期間（**を選択したデータセットおよび日付範囲）でスキップされた行数を示します。** レコードをスキップする理由は次のとおりです。タイムスタンプの欠落、ユーザーIDの欠落など。 10分ごとに更新されます。 |
| [!UICONTROL deletedwidgetのレ] コード | 選択した期間（**を選択したデータセットと日付範囲）で削除された行数**&#x200B;を示します。 例えば、データセット内のExperience Platformを削除した可能性があります。 10分ごとに更新されます。 |
| データセット検索ボックス | データセット名または[!UICONTROL データセットID]で検索できます。 |
| [!UICONTROL データセット] | 接続に含まれるデータセットを表示します。 ハイパーリンクをクリックすると、接続内のすべてのデータセットを表示できます。 |
| [!UICONTROL データセット ID] | このIDはAdobe Experience Platformによって自動的に生成されます。 |
| [!UICONTROL バッチ] | このデータセットに追加されたデータバッチの数を示します。 |
| [!UICONTROL 前回追加した日時] | このデータセットに最後に追加されたバッチのタイムスタンプを表示します。 |
| [!UICONTROL データセットタイプ] | このデータセットのデータセットタイプは、[!UICONTROL Event]、[!UICONTROL Lookup]、[!UICONTROL Profile]のいずれかです。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| スキーマ | この接続のデータセットの基になるAdobe Experience Platformスキーマ。 |
| **接続レベルの右側のレール** |  |
| [!UICONTROL 更新] | 接続を更新して、最近追加したレコードを反映させます。 |
| [!UICONTROL 削除] | この接続を削除します。 |
| [!UICONTROL データビューを作成] | この接続に基づいて新しいデータビューを作成します。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL 接続名] | 接続のわかりやすい名前を表示します。 |
| [!UICONTROL 接続の説明] | この接続の目的を理想的に説明する詳細な説明を表示します。 |
| [!UICONTROL ユーザー ID] | Experience Platform内のデータセットスキーマで定義されたIDを表示します。 これは、接続の作成時に選択した[!UICONTROL ユーザーID]です。 異なるIDのデータセットを含む接続を作成すると、レポートに反映されます。 データセットを実際に結合するには、同じ[!UICONTROL ユーザーID]を使用する必要があります。 |
| [!UICONTROL サンドボックス] | この接続がデータセットを描画する[Adobe Experience Platformサンドボックス](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en)。このサンドボックスは、接続を初めて作成したときに選択されています。 変更はできません。 |
| [!UICONTROL 接続 ID] | このIDは、Adobe Experience Platformでシステム生成されます。 |
| [!UICONTROL IMS Org ID] | プロビジョニングしたExperience Cloud会社に関連付けられた[組織ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)。 以前は「ログイン会社」と呼ばれていました。 |
| [!UICONTROL 接続を使用するデータビュー] | この接続を使用するすべてのデータビューを表示します。 |
| [!UICONTROL 新しいデータをインポート] | 新しいデータバッチを履歴（バックフィル）データに追加するかどうかを示します。 |
| **データセットレベルの右側パネル** |  |
| [!UICONTROL データセットの説明] | この接続内の各データセットのパラメーターについて説明します。 |
| [!UICONTROL 使用可能なレコード] | カレンダーを通じて選択した特定の期間における、このデータセットに対して取り込まれる行の合計数を表します。 データが追加されると、レポートに表示されるデータの取得に遅延は発生しません。 (例外は、まったく新しい接続を作成する場合、[待ち時間](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.-getting-data-into-customer-journey-analytics)が発生することです。 |
| [!UICONTROL 追加されたレコード] | 選択した期間に追加された行数。 |
| [!UICONTROL スキップされたレコード] | 選択した期間の取り込み中にスキップされた行数。 |
| [!UICONTROL スキップされたエラーを記録] | レコードがスキップされた理由をここに示します。 タイムスタンプが見つからない、ユーザーIDが見つからないなどが含まれる場合があります。 |
| [!UICONTROL 取り込まれたバッチ] | このデータセットに追加されたデータバッチの数。 |
| [!UICONTROL 前回追加した日時] | 最後のバッチが追加された日時。 |
| [!UICONTROL データセットタイプ] | [!UICONTROL Event]、[!UICONTROL Lookup]、[!UICONTROL Profile]のいずれかです。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL スキーマ] | このデータセットのベースとなるAdobe Experience Platformスキーマ。 |
| [!UICONTROL データセット ID] | このIDは、Adobe Experience Platformでシステム生成されます。 |
| [!UICONTROL データをバックフィル] | バックフィル（履歴）データは、次の3つの状態で追跡されます。[!UICONTROL キュー]、[!UICONTROL 処理中]（進行状況の割合が示されます）、[!UICONTROL 完了]。 |

### 接続を編集

管理者が接続を編集できるようにします。 接続を選択し、「[!UICONTROL 接続を編集]」をクリックしてこのダイアログに移動します。 ここでは、次の操作を実行できます。

* 新しいデータのインポートを開始および停止します。 このプロセスは、以前は「データストリーミング」と呼ばれていました。
* 接続名を変更する。
