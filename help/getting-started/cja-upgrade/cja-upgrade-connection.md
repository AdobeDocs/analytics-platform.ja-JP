---
title: Customer Journey Analytics のスキーマの作成
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパスについて説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 22d3e7b8-4a4d-48a8-a98d-5172a9876286
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1635'
ht-degree: 97%

---

# Customer Journey Analytics で使用する接続の作成と設定 {#upgrade-create-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-connection"
>title="Customer Journey Analytics で接続を作成する"
>abstract="接続を使用すると、Adobe Experience Platform からのデータを Customer Journey Analytics レポート用に最適化された形式に変換できます。Customer Journey Analytics での接続の作成は簡単で、完了するまでに数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/connections/create-connection.md -->

次の情報では、接続を作成および設定する方法と、作成した接続に Experience Platform データセットを追加する方法について説明します。接続の作成と設定について詳しくは、[接続の作成または編集](/help/connections/create-connection.md)を参照してください。

## 接続の作成と設定 {#create-connection}

1. Customer Journey Analyticsで、必要に応じて ]**データ管理**[!UICONTROL  から「**[!UICONTROL 接続]**」を選択します。
1. 「**[!UICONTROL 新しい接続を作成]**」を選択します。

   ![名称未設定の接続設定](assets/create-conn1.png)

1. 接続を設定します。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL 接続名]** | 接続の一意の名前を入力します。 |
   | **[!UICONTROL 接続の説明]** | この接続の目的を記述します。 |
   | **[!UICONTROL サンドボックス]** | 接続を作成するデータセットを含む Experience Platform のサンドボックスを選択します。<p>Adobe Experience Platform は、単一の Platform インスタンスを別々の仮想環境に分割して、デジタルエクスペリエンスアプリケーションの開発と発展を支援する仮想[サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)を提供します。 サンドボックスは、データセットを含む「データサイロ」と考えることができます。 サンドボックスは、データセットへのアクセスを制御するために使用します。<p>サンドボックスを選択すると、左側のパネルに、取り出し元となるサンドボックス内のすべてのデータセットが表示されます。 |
   | **[!UICONTROL 周期的なデータ時間枠を有効にする]** | このチェックボックスをオンにすると、Customer Journey Analytics データ保持を接続レベルでの月単位（1 か月、3 か月、6 か月など）の周期的な時間枠として定義できます。<p>データ保持は、イベントデータセットのタイムスタンプに基づいており、イベントデータセットにのみ適用されます。 適用可能なタイムスタンプがないので、プロファイルまたはルックアップデータセットには、周期的なデータ時間枠設定は存在しません。 ただし、接続に（1 つ以上のイベントデータセットに加えて）プロファイルまたはルックアップデータセットが含まれる場合、そのデータは、同じ期間だけ保持されます。<p> 主な利点は、該当する有用なデータのみを保存またはレポートして、有用でなくなった古いデータを削除できるという点です。 契約上の上限を超えないようにし、超過コストのリスクを軽減します。<p>デフォルト（オフ）のままにすると、Adobe Experience Platform のデータ保持設定によって保持期間が置き換えられます。 Experience Platform に 25 か月分のデータがある場合、Customer Journey Analytics はバックフィルを通じて 25 か月分のデータを取得します。 Platform でこのうち 10 か月を削除すると、Customer Journey Analytics は残りの 15 か月を保持します。 |
   | **[!UICONTROL データセットを追加]**（後述） | データセットリストにデータセットが表示されない場合は、データセットを追加します。 |
   | **[!UICONTROL データセット名]** | Customer Journey Analytics に取り込むデータセットを 1 つ以上選択して、「**[!UICONTROL 追加]**」を選択します。<p>（選択できるデータセットが多数ある場合は、データセットのリスト上部にある「データセットを検索」検索バーを使用して、適切なデータセットを検索できます）。 |
   | **[!UICONTROL 最終更新日]** | イベントデータセットの場合のみ、この設定は、Experience Platform のイベントベースのスキーマからデフォルトのタイムスタンプフィールドに自動的に設定されます。 「該当なし」は、このデータセットにデータが含まれていないことを意味します。 |
   | **[!UICONTROL レコード数]** | Experience Platform 内のデータセットの先月の合計レコード数。 |
   | **[!UICONTROL スキーマ]** | Adobe Experience Platform で作成されたデータセット基づく[スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition)。 |
   | **[!UICONTROL データセットタイプ]** | Customer Journey Analytics は、この接続に追加した各データセットに対して、受信するデータに基づいてデータセットタイプを自動的に設定します。 データセットには、イベントデータ、プロファイルデータおよびルックアップデータの 3 種類があります。 データセットのタイプについて詳しくは、次の表を参照してください。 |
   | **[!UICONTROL 精度]** | データセット内のデータの精度。概要データセットにのみ適用できます。 |
   | **[!UICONTROL データソースタイプ]** | データセットのデータソースタイプ。 概要データセットには適用できません。 |
   | **[!UICONTROL ユーザー ID]** | 使用可能な ID のドロップダウンメニューからユーザー ID を選択します。 これらの ID は、Experience Platform 内のデータセットスキーマで定義されています。 ユーザー ID として ID マップを使用する方法については、次を参照してください。<p>重要：選択するユーザー ID がない場合は、1 つ以上のユーザー ID がスキーマで定義されていないことを意味します。 Experience Platform で ID を定義する方法については、[このビデオ](https://www.youtube.com/watch?v=G_ttmGl_LRU)をご覧ください。 |
   | **[!UICONTROL キー]** | データセットのルックアップのみ（as _id など）。 |
   | **[!UICONTROL 一致するキー]** | データセットのルックアップのみ（as _id など）。 |
   | **[!UICONTROL 新しいデータをインポート]** | オンまたはオフに設定します。 |
   | **[!UICONTROL データをバックフィル]** | データセット内のデータのバックフィルをリクエストできます。 例えば、過去 7 日間のデータのバックフィルをリクエストできます。 データセットを正しく設定し、接続をテストします。 問題がないようであれば、残りのすべてのデータを簡単にバックフィルできます。<p>また、データセット別に新しいデータの読み込みを有効にすることもできます。 |
   | **[!UICONTROL バックフィルのステータス]** | このステータスは、バックフィルデータが処理中かどうかを示します。 |

   {style="table-layout:auto"}

## データセットの追加と設定 {#add-dataset}

接続を作成する際に、Experience Platform データセットを追加できます。

1. 接続設定ダイアログで、「**[!UICONTROL データセットを追加]**」を選択します。

1. [!UICONTROL データセットを選択]手順では、Experience Platform データセットのリストが表示されます。

   ![データセットの選択](assets/select-datasets.png)

   各データセットに対して、リストには次が表示されます。

   | 列 | 説明 |
   |---|---|
   | データセット | データセットの名前。 名前を選択すると、Experience Platform のデータセットに移動します。 ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)を選択すると、データセットの詳細を含むポップアップが表示されます。 「**[!UICONTROL Platform で編集]**」を選択すると、Experience Platform でデータセットを直接編集できます。 |
   | データセットタイプ | データセットのタイプ（イベント、プロファイル、ルックアップ、概要）。 |
   | レコード数 | Experience Platform 内のデータセットの先月の合計レコード数。 |
   | スキーマ | データセットのスキーマ。 名前を選択すると、Experience Platform のスキーマに移動します。 |
   | 前回のバッチ | Experience Platform で最後に取り込まれたバッチの状態。 詳しくは、[バッチの状態](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/batch/troubleshooting#batch-states)を参照してください。 |
   | データセット ID | データセットの ID。 |
   | 最終更新日時 | データセットの最終更新日タイムスタンプ。 |


1. 1 つ以上のデータセットを選択して、「**[!UICONTROL 次へ]**」を選択します。 少なくとも 1 つのイベントデータセットを接続に含める必要があります。
   * データセットのリストに表示される列を変更するには、「![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」をクリックし、[!UICONTROL テーブルをカスタマイズ]ダイアログで表示する列を選択します。
   * 特定のデータセットを検索するには、「![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)」検索フィールドを使用します。
   * 選択したデータセットの表示や非表示を切り替えるには、「![選択](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg)」、「**[!UICONTROL 選択した項目を非表示]**」または「**[!UICONTROL 選択した項目を表示]**」の順に選択します。
   * 選択したデータセットのリストからデータセットを削除するには、「![閉じる](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg)」を使用します。 選択したすべてのデータセットを削除するには、「**[!UICONTROL すべてクリア]**」を選択します。




1. 次に、データセットを 1 つずつ設定します。

   ![データセットの設定](assets/add-dataset.png)

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL ユーザー ID]** | イベントデータセットとプロファイルデータセットでのみ使用できます。 使用可能な ID のドロップダウンメニューからユーザー ID を選択します。 これらの ID は、Experience Platform 内のデータセットスキーマで定義されています。 ユーザー ID として ID マップを使用する方法については、次を参照してください。<p>選択するユーザー ID がない場合は、1 つ以上のユーザー ID がスキーマで定義されていないことを意味します。 詳しくは、[UI で ID フィールドを定義](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity)を参照してください。 <p>選択したユーザー ID の値は、大文字と小文字が区別されると見なされます。 例えば、`abc123` と `ABC123` は 2 つの異なる値です。 |
   | **[!UICONTROL タイムスタンプ]** | イベントおよび概要データセットの場合のみ、この設定は、Experience Platform のイベントベースのスキーマからデフォルトのタイムスタンプフィールドに自動的に設定されます。 |
   | **[!UICONTROL キー]** | ルックアップデータセットでのみ使用できます。 ルックアップデータセットに使用するキーです。 |
   | **[!UICONTROL 一致するキー]** | ルックアップデータセットでのみ使用できます。 いずれかのイベントデータセットで結合するための一致するキーです。 このリストが空の場合は、イベントデータセットを追加または設定していない可能性があります。 |
   | **[!UICONTROL タイムゾーン]** | 概要データでのみ使用できます。 時系列の概要データに適したタイムゾーンを選択します。 |
   | **[!UICONTROL データソースタイプ]** | データソースのタイプを選択します。 <br/>データソースのタイプを以下に示します。 <ul><li>[!UICONTROL Web データ]</li><li>[!UICONTROL モバイルアプリデータ]</li><li>[!UICONTROL POS データ]</li><li>[!UICONTROL CRM データ]</li><li>[!UICONTROL サーベイデータ]</li><li>[!UICONTROL コールセンターデータ]</li><li>[!UICONTROL 製品データ]</li><li> [!UICONTROL アカウントデータ]</li><li> [!UICONTROL トランザクションデータ]</li><li>[!UICONTROL 顧客フィードバックデータ]</li><li> [!UICONTROL その他]</li></ul>このフィールドは、使用中のデータソースのタイプを調査するために使用します。 |
   | **[!UICONTROL 新しいデータをインポート]** | 継続的な接続を確立する場合は、このオプションを有効にします。 継続的な接続を行うと、データセットに追加された新しいデータバッチが Workspace で自動的に使用できます。 |
   | **[!UICONTROL データセットのバックフィル]** | 既存のすべてのデータを確実にバックフィルするには、「**[!UICONTROL 既存のすべてのデータをバックフィル]**」を有効にします。<br/><br/>特定の期間の履歴データをバックフィルするには、「**[!UICONTROL バックフィルをリクエスト]**」を選択します。 データセットのバックフィル期間を最大 10 個定義できます。<ol><li>開始データと終了データを入力するか、![カレンダー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) を使用して日付を選択して期間を定義します。</li><li>「**[!UICONTROL キューのバックフィル]**」を選択してバックフィルをリストに追加するか、「**[!UICONTROL キャンセル]**」を選択してキャンセルします。</li></ol>各エントリについて、期間を編集するには ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) を選択し、エントリを削除するには ![削除](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) を選択します。<br/><br/>バックフィルについて：<ul><li>各データセットを個別にバックフィルできます。</li><li>接続内のデータセットに追加された新しいデータが優先されるので、この新しいデータの待ち時間が最も短くなります。</li><li>バックフィル（履歴）データのインポートには時間がかかります。 履歴データの量は待ち時間に影響を与えます。</li><li>Analytics ソースコネクタは、実稼動用サンドボックスに（サイズに関係なく）最大 13 か月分のデータを読み込みます。 非実稼動用サンドボックスのバックフィルは、3 か月に制限されています。</li></ul> |
   | **[!UICONTROL データセットを変換]** | 特定の B2B ルックアップデータセットでは、適切な B2B ユーザーベースのレポートシナリオに対応するデータセットの変換を有効にすることができます。 |
   | **[!UICONTROL バックフィルのステータス]** | 次に、使用可能なステータスインジケーターを示します。<ul><li>成功</li><li>X 個のバックフィルが処理中</li><li>オフ</li></ul> |
   | **[!UICONTROL データセット ID]** | この ID は自動的に生成されます。 |
   | **[!UICONTROL 説明]** | 作成された際に、このデータセットに付与された説明。 |
   | **[!UICONTROL データセットサイズ]** | データセットのサイズ。 |
   | **[!UICONTROL スキーマ]** | Adobe Experience Platform で作成されたデータセットに基づくスキーマ。 |
   | **[!UICONTROL データセット]** | データセットの名前。 |
   | **[!UICONTROL プレビュー：*データセット名&#x200B;*]** | 日付、自分の ID、識別子の列を含むデータセットをプレビューします。 |
   | **[!UICONTROL 削除]** | 接続全体を削除しなくても、データセットを削除して、ユーザー ID を変更できます。 削除すると、データの取り込みに伴うコストと、接続全体および関連するデータビューを再作成する煩雑なプロセスが削減されます。 |

   {style="table-layout:auto"}

{{upgrade-final-step}}
