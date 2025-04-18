---
title: 接続の作成または編集
description: Customer Journey Analytics で Experience Platform データセットへの接続を作成または編集する方法について説明します。
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '4906'
ht-degree: 83%

---

# 接続の作成または編集 {#create-or-edit-a-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="追加されたレコード"
>abstract="選択したデータセットに関して、選択した時間間隔で接続に追加されたレコード（行）の数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="スキップされたレコード"
>abstract="選択したデータセットに関して、選択した時間間隔で接続のデータ転送中にスキップされたレコード（行）の数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="削除されたレコード"
>abstract="選択したデータセットに関して、選択した時間間隔で接続から削除されたレコード（行）の数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="前回追加した日時"
>abstract="接続に転送された任意のデータセットからの最新のバッチのタイムスタンプ。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="周期的なデータ期間を有効にする"
>abstract="データ保持を月数で周期的な期間として接続レベルで定義します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_averagenumberofdailyuses"
>title="毎日の使用の平均数"
>abstract="接続全体で想定される毎日のイベント数の範囲を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsadded"
>title="追加されたレコード"
>abstract="選択したデータセットに関して、選択した時間間隔で接続に追加されたレコード（行）の数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsskipped"
>title="スキップされたレコード"
>abstract="選択したデータセットに関して、選択した時間間隔で接続のデータ転送中にスキップされたレコード（行）の数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsdeleted"
>title="削除されたレコード"
>abstract="選択したデータセットに関して、選択した時間間隔で接続から削除されたレコード（行）の数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_lastadded"
>title="前回追加した日時"
>abstract="接続に転送された任意のデータセットからの最新のバッチのタイムスタンプ。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_enablerollingdatawindow"
>title="周期的なデータ期間を有効にする"
>abstract="データ保持を月数で周期的な期間として接続レベルで定義します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_averagenumberofdailyuses"
>title="毎日の使用の平均数"
>abstract="接続全体で想定される毎日のイベント数の範囲を選択します。"



接続の作成と編集ワークフローエクスペリエンスでは、すべてのデータセットと接続設定が、補助的なワークフローで画面の中央に表示されます。 詳細なデータセットの選択、設定、確認のエクスペリエンスを提供します。 また、データセットのタイプ、サイズ、スキーマ、データセット ID、バッチステータス、バックフィルステータス、ユーザー ID などの重要な情報を指定できるので、誤った接続設定のリスクを軽減できます。 機能の概要を以下に示します。

* 接続を作成する際に、周期的なデータ保持時間枠を有効にすることができます。
* 接続からデータセットを追加および削除できます （データセットを削除すると、接続からデータセットが削除され、関連付けられたすべてのデータビューおよび基になる Analysis Workspace プロジェクトに影響します）。
* データセットごとにバックフィルデータを有効にしたり、リクエストしたりできます。
* （例えば、別のバックフィルをリクエストするために）データセットを編集できます。
* データセットごとに既存のデータ読み込むことができます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [接続の作成と編集](https://video.tv.adobe.com/v/343044/?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## 前提条件

接続に追加できるデータセットの最大数は 100 に制限されています。 組み合わせは、会社が購入した Customer Journey Analytics パッケージに応じて異なります。

使用している Customer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。

| **選択**&#x200B;パッケージ | **基盤**&#x200B;パッケージ |
| --- | --- |
| イベント／プロファイル／ルックアップ／概要データセットの任意の組み合わせ（最大 100 個の追加） | 接続あたり 1 個のイベントデータセット |
|  | 接続あたり最大 99 個のプロファイル、ルックアップまたは概要データセット |

{style="table-layout:auto"}

## 接続の作成と設定 {#create-connection}

1. Customer Journey Analyticsで、必要に応じて ]**データ管理**[!UICONTROL  から「**[!UICONTROL 接続]**」を選択します。
1. 「**[!UICONTROL 新しい接続を作成]**」を選択します。

>[!BEGINTABS]

>[!TAB 標準 ]

![名称未設定の接続設定](assets/create-conn1.png)

>[!TAB B2B edition]

![名称未設定の接続設定](assets/create-conn1-b2b.png)

>[!ENDTABS]

**[!UICONTROL 接続]**/**[!UICONTROL 名称未設定の接続]** 画面で、次の手順を実行します。

1. 接続を設定します。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL 接続名]** | 接続の一意の名前を入力します。 |
   | **[!UICONTROL 接続の説明]** | この接続の目的を記述します。 |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL プライマリID ]** | 接続に適したプライマリ ID を選択します。 <ul><li>B2C シナリオの ![ ユーザー ](/help/assets/icons/User.svg) **[!UICONTROL ユーザー]**</li><li> B2B シナリオの ![ 構築 ](/help/assets/icons/Building.svg) **[!UICONTROL アカウント]**。</li></ul> |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  オプションコンテナ ]** | 追加のコンテナを選択します。<ul><li>**[!UICONTROL グローバルアカウント]**：接続内のグローバルアカウントの設定を有効にします。</li><li>**[!UICONTROL 商談]**：接続内の商談の設定を有効にします。</li><li>**[!UICONTROL 購買グループ]**：接続内の購買グループの設定を有効にします。</li><ul> |
   | **[!UICONTROL サンドボックス]** | 接続を作成するデータセットを含む Experience Platform のサンドボックスを選択します。<p>Adobe Experience Platform は、単一の Platform インスタンスを別々の仮想環境に分割して、デジタルエクスペリエンスアプリケーションの開発と発展を支援する仮想[サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)を提供します。 サンドボックスは、データセットを含む「データサイロ」と考えることができます。 サンドボックスは、データセットへのアクセスを制御するために使用します。<p>サンドボックスを選択すると、左側のパネルに、取り出し元となるサンドボックス内のすべてのデータセットが表示されます。 |
   | **[!UICONTROL 周期的なデータ時間枠を有効にする]** | このチェックボックスをオンにすると、Customer Journey Analytics データ保持を接続レベルでの月単位（1 か月、3 か月、6 か月など）の周期的な時間枠として定義できます。<p>データ保持は、イベントデータセットのタイムスタンプに基づいており、イベントデータセットにのみ適用されます。 適用可能なタイムスタンプがないので、プロファイルまたはルックアップデータセットには、周期的なデータ時間枠設定は存在しません。 ただし、接続に（1 つ以上のイベントデータセットに加えて）プロファイルまたはルックアップデータセットが含まれる場合、そのデータは、同じ期間だけ保持されます。<p> 主な利点は、該当する有用なデータのみを保存またはレポートして、有用でなくなった古いデータを削除できるという点です。 契約上の上限を超えないようにし、超過コストのリスクを軽減します。<p>デフォルト（オフ）のままにすると、Adobe Experience Platform のデータ保持設定によって保持期間が置き換えられます。 Experience Platform に 25 か月分のデータがある場合、Customer Journey Analytics はバックフィルを通じて 25 か月分のデータを取得します。 Platform でこのうち 10 か月を削除すると、Customer Journey Analytics は残りの 15 か月を保持します。 |
   | **[!UICONTROL データセットを追加]**（後述） | データセットテーブルにデータセットが表示されない場合は、データセットを追加します。 そうでない場合は、接続の作成の一環として既に追加したデータセットのリストが表示されます。 |


   設定したデータセットの場合、データセットのテーブルには次の列が表示されます。

   | 列 | 説明 |
   |---|---|
   | **[!UICONTROL データセット名]** | Customer Journey Analytics に取り込むデータセットを 1 つ以上選択して、「**[!UICONTROL 追加]**」を選択します。<p>（選択できるデータセットが多数ある場合は、データセットのリスト上部にある「データセットを検索」検索バーを使用して、適切なデータセットを検索できます）。 |
   | **[!UICONTROL 最終更新日]** | イベントデータセットの場合のみ、この設定は、Experience Platform のイベントベースのスキーマからデフォルトのタイムスタンプフィールドに自動的に設定されます。 「該当なし」は、このデータセットにデータが含まれていないことを意味します。 |
   | **[!UICONTROL レコード数]** | Experience Platform 内のデータセットの先月の合計レコード数。 |
   | **[!UICONTROL スキーマ]** | Adobe Experience Platform で作成されたデータセット基づく[スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition)。 |
   | **[!UICONTROL データセットタイプ]** | Customer Journey Analytics は、この接続に追加した各データセットに対して、受信するデータに基づいてデータセットタイプを自動的に設定します。 データセットには、イベントデータ、プロファイルデータおよびルックアップデータの 3 種類があります。 データセットのタイプについて詳しくは、次の表を参照してください。 |
   | **[!UICONTROL 精度]** | データセット内のデータの精度。概要データセットにのみ適用できます。 |
   | **[!UICONTROL データソースタイプ]** | データセットのデータソースタイプ。 概要データセットには適用できません。 |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  アカウント ID ]** | データセットのアカウントベースのレポートをサポートするために使用されるアカウント ID。 |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  グローバルアカウント ID ]** | グローバルアカウントデータの検索に使用するグローバルアカウント ID。 |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  購入グループ ID ]** | 購入グループデータを参照するために使用される購入グループ ID。 |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  オポチュニティ ID ]** | 商談データの参照に使用される商談 ID。 |
   | **[!UICONTROL ユーザー ID]** | データセットのユーザーベースのレポートをサポートするために使用されるユーザー ID。 |
   | **[!UICONTROL キー]** | データセットのルックアップのみ（as _id など）。 |
   | **[!UICONTROL 一致するキー]** | データセットのルックアップのみ（as _id など）。 |
   | **[!UICONTROL 新しいデータをインポート]** | オンまたはオフに設定します。 |
   | **[!UICONTROL データをバックフィル]** | データセット内のデータのバックフィルをリクエストできます。 例えば、過去 7 日間のデータのバックフィルをリクエストできます。 データセットを正しく設定し、接続をテストします。 問題がないようであれば、残りのすべてのデータを簡単にバックフィルできます。<p>また、データセット別に新しいデータの読み込みを有効にすることもできます。 |
   | **[!UICONTROL バックフィルのステータス]** | このステータスは、バックフィルデータが処理中かどうかを示します。 |

   ![ 検索 ](/help/assets/icons/Search.svg) フィールドを使用して、特定のデータセットを検索できます。


## データセットを追加 {#add-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_primaryid"
>title="プライマリ ID"
>abstract="接続に適したプライマリ ID を選択します（B2C シナリオの場合は「ユーザー」）。B2B シナリオのアカウント。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_optionalcontainers"
>title="オプションコンテナ"
>abstract="追加のコンテナを選択します。<br/><br/>**[!UICONTROL グローバルアカウント&#x200B;]**：接続内のグローバルアカウントの設定を有効にします。<br/>**[!UICONTROL 商談]**：接続内の商談の設定を有効にします。<br/>**[!UICONTROL 購買グループ&#x200B;]**：接続内の購買グループの設定を有効にします。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_personid"
>title="ユーザー ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID からユーザー ID を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountid"
>title="アカウント ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID からアカウント ID（アカウントの一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountfield"
>title="アカウントフィールド"
>abstract="アカウント ID（アカウントの一意の ID）を表すフィールドを選択します。"

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_globalaccountid"
>title="グローバルアカウント ID"
>abstract="Experience Platform のデータセットスキーマで定義されている、使用可能な ID からグローバルアカウント ID（グローバルアカウントの一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_opportunityid"
>title="商談 ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID から商談 ID（商談の一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_buyinggroupid"
>title="購買グループ ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID から購買グループ ID（購入グループの一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_matchingkey"
>title="一致するキー"
>abstract="結合方法を選択：一致するキーまたは一致するコンテナに基づきます。<br/><br/>**[!UICONTROL 一致するキー&#x200B;]**：いずれかのイベントデータセットで結合するフィールドを選択します。このリストが空の場合は、イベントデータセットを追加または設定していない可能性があります。<br/>**[!UICONTROL 一致するコンテナ]**：イベントデータセットの 1 つと結合するために使用するコンテナを選択します。このリストが空の場合は、1 つ以上のコンテナを設定していない可能性があります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="新しいデータの読み込み"
>abstract="Experience Platform データセットに追加される新しいバッチはすべて、この接続に自動的に追加され、分析に使用できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="データセットのバックフィル"
>abstract="このオプションを使用すると、接続内のこのデータセットについて、Experience Platform からの既存の（履歴）データがバックフィルされます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="データセットの変換"
>abstract="このオプションは、B2B シナリオで個人ベースのルックアップに使用できるようにデータセットを変換します。一度オンにすると、データセットの変換は元に戻せません。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_connectionmap"
>title="接続マップ"
>abstract="接続マップは、イベント、ユーザー、アカウントおよび関連するルックアップデータセット（商談、キャンペーンメンバーなど）間の関係を視覚化します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_primaryid"
>title="プライマリ ID"
>abstract="接続に適したプライマリ ID を選択します（B2C シナリオの場合は「ユーザー」）。B2B シナリオのアカウント。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_optionalcontainers"
>title="オプションコンテナ"
>abstract="追加のコンテナを選択します。<br/><br/>**[!UICONTROL グローバルアカウント&#x200B;]**：接続内のグローバルアカウントの設定を有効にします。<br/>**[!UICONTROL 商談]**：接続内の商談の設定を有効にします。<br/>**[!UICONTROL 購買グループ&#x200B;]**：接続内の購買グループの設定を有効にします。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_personid"
>title="ユーザー ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID からユーザー ID を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountid"
>title="アカウント ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID からアカウント ID（アカウントの一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountfield"
>title="アカウントフィールド"
>abstract="アカウント ID（アカウントの一意の ID）を表すフィールドを選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_globalaccountid"
>title="グローバルアカウント ID"
>abstract="Experience Platform のデータセットスキーマで定義されている、使用可能な ID からグローバルアカウント ID（グローバルアカウントの一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_opportunityid"
>title="商談 ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID から商談 ID（商談の一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_buyinggroupid"
>title="購買グループ ID"
>abstract="Experience Platform のデータセットスキーマで定義されている使用可能な ID から購買グループ ID（購入グループの一意の ID）を選択します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_matchingkey"
>title="一致するキー"
>abstract="結合方法を選択：一致するキーまたは一致するコンテナに基づきます。<br/><br/>**[!UICONTROL 一致するキー&#x200B;]**：いずれかのイベントデータセットで結合するフィールドを選択します。このリストが空の場合は、イベントデータセットを追加または設定していない可能性があります。<br/>**[!UICONTROL 一致するコンテナ]**：イベントデータセットの 1 つと結合するために使用するコンテナを選択します。このリストが空の場合は、1 つ以上のコンテナを設定していない可能性があります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_importnewdata"
>title="新しいデータの読み込み"
>abstract="Experience Platform データセットに追加される新しいバッチはすべて、この接続に自動的に追加され、分析に使用できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_datasetbackfill"
>title="データセットのバックフィル"
>abstract="このオプションを使用すると、接続内のこのデータセットについて、Experience Platform からの既存の（履歴）データがバックフィルされます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_transformdataset"
>title="データセットの変換"
>abstract="このオプションは、B2B シナリオで個人ベースのルックアップに使用できるようにデータセットを変換します。一度オンにすると、データセットの変換は元に戻せません。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_connectionmap"
>title="接続マップ"
>abstract="接続マップは、イベント、ユーザー、アカウントおよび関連するルックアップデータセット（商談、キャンペーンメンバーなど）間の関係を視覚化します。"



このワークフローを使用すると、接続を作成する際に、1 つ以上のExperience Platform データセットを追加できます。


1. 接続設定ダイアログで、「**[!UICONTROL データセットを追加]**」を選択します。

1. **[!UICONTROL データセット➊を選択]** 手順には、Experience Platform データセットのリストが表示されます。

   ![データセットの選択](assets/select-datasets.png)

   各データセットに対して、リストには次が表示されます。

   | 列 | 説明 |
   |---|---|
   | **[!UICONTROL データセット]** | データセットの名前。 名前を選択すると、Experience Platform のデータセットに移動します。 ![情報](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)を選択すると、データセットの詳細を含むポップアップが表示されます。 「**[!UICONTROL Platform で編集]**」を選択すると、Experience Platform でデータセットを直接編集できます。 |
   | **[!UICONTROL データセットタイプ]** | データセットのタイプ（イベント、プロファイル、ルックアップ、概要）。 |
   | **[!UICONTROL レコード数]** | Experience Platform 内のデータセットの先月の合計レコード数。 |
   | **[!UICONTROL スキーマ]** | データセットのスキーマ。 名前を選択すると、Experience Platform のスキーマに移動します。 |
   | **[!UICONTROL 前回のバッチ]** | Experience Platform で最後に取り込まれたバッチの状態。 詳しくは、[バッチの状態](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/batch/troubleshooting#batch-states)を参照してください。 |
   | **[!UICONTROL データセット ID]** | データセットの ID。 |
   | **[!UICONTROL 最終更新日]** | データセットの最終更新日タイムスタンプ。 |

   * データセットのリストに表示される列を変更するには、「![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」をクリックし、[!UICONTROL テーブルをカスタマイズ]ダイアログで表示する列を選択します。
   * 特定のデータセットを検索するには、「![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)」検索フィールドを使用します。
   * 選択したデータセットの表示や非表示を切り替えるには、「![選択](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg)」、「**[!UICONTROL 選択した項目を非表示]**」または「**[!UICONTROL 選択した項目を表示]**」の順に選択します。
   * 選択したデータセットのリストからデータセットを削除するには、「![閉じる](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg)」を使用します。 選択したすべてのデータセットを削除するには、「**[!UICONTROL すべてクリア]**」を選択します。


1. 1 つ以上のデータセットを選択して、「**[!UICONTROL 次へ]**」を選択します。 各データセットを [ 設定 ](#configure-datasets) します。 少なくとも 1 つのイベントデータセットを接続に含める必要があります。


## データセットの設定

**[!UICONTROL データセットを追加]** ダイアログの **[!UICONTROL データセット設定]** の➋手順で、選択した各データセットを 1 つずつ設定します。

>[!BEGINTABS]

>[!TAB 標準 ]

![データセットを追加](assets/add-dataset.png)

>[!TAB B2B edition]

![ データセット B2B を追加 ](assets/add-dataset-b2b.png)

>[!ENDTABS]

| 設定 | 説明 |
| --- | --- |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  アカウント ID ]** | イベントデータセットと、[ コンテナで一致 ](/help/getting-started/cja-b2b-concepts-features.md#match-by-container-or-field) するルックアップデータセットでのみ使用できます。 Experience Platform のデータセットスキーマで定義されている使用可能な ID からアカウント ID（アカウントの一意の ID）を選択します。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  オポチュニティ ID ]** | イベントデータセットでのみ使用できます。 Experience Platform のデータセットスキーマで定義されている使用可能な ID から商談 ID（商談の一意の ID）を選択します。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  購入グループ ID ]** | イベントデータセットでのみ使用できます。 Experience Platform のデータセットスキーマで定義されている使用可能な ID から購買グループ ID（購入グループの一意の ID）を選択します。 |
| **[!UICONTROL ユーザー ID]** | イベントデータセットとプロファイルデータセットでのみ使用できます。 使用可能な ID のドロップダウンリストからユーザー ID を選択します。 これらの ID は、Experience Platform 内のデータセットスキーマで定義されています。 ユーザー ID として ID マップを使用する方法については、次を参照してください。<p>選択するユーザー ID がない場合は、1 つ以上のユーザー ID がスキーマで定義されていないことを意味します。 詳しくは、[UI で ID フィールドを定義](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity)を参照してください。 <p>選択したユーザー ID の値は、大文字と小文字が区別されると見なされます。 例えば、`abc123` と `ABC123` は 2 つの異なる値です。 |
| **[!UICONTROL タイムスタンプ]** | イベントおよび概要データセットの場合のみ、この設定は、Experience Platform のイベントベースのスキーマからデフォルトのタイムスタンプフィールドに自動的に設定されます。 |
| **[!UICONTROL キー]** | ルックアップデータセットでのみ使用できます。 ルックアップデータセットに使用するキーです。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} **[!UICONTROL 一致するキータイプ]** | データセットの結合方法として、「**[!UICONTROL コンテナで一致]** または **[!UICONTROL コンテナで一致]** を選択します。 詳しくは [ フィールドのコンテナで一致 ](/help/getting-started/cja-b2b-concepts-features.md#match-by-container-or-field) を参照してください。 |
| **[!UICONTROL 一致するキー]** | 参照またはプロファイルデータセットでのみ使用できます。 いずれかのイベントデータセットで結合するための一致するキーです。 このリストが空の場合は、イベントデータセットを追加または設定していない可能性があります。 <br/><br/>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/> 選択した **[!UICONTROL 一致するキータイプ]** に基づいて、適切な値を選択します。<ul><li>**[!UICONTROL フィールドによる一致]**：いずれかのイベントデータセットと結合するフィールドを選択します。 このリストが空の場合は、イベントデータセットを追加または設定していない可能性があります。</li><li>**[!UICONTROL コンテナで一致]**：イベントデータセットの 1 つと結合するために使用するコンテナを選択します。 選択可能なコンテナは、接続の設定時に含めたコンテナによって決まります。 このリストが空の場合は、1 つ以上のコンテナを設定していない可能性があります。</li></ul> |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL  アカウントフィールド ]** | アカウントベースのレポートに使用するアカウント ID。 |
| **[!UICONTROL タイムゾーン]** | 概要データでのみ使用できます。 時系列の概要データに適したタイムゾーンを選択します。 |
| **[!UICONTROL データソースタイプ]** | データソースのタイプを選択します。 <br/>データソースのタイプを以下に示します。 <ul><li>[!UICONTROL Web データ]</li><li>[!UICONTROL モバイルアプリデータ]</li><li>[!UICONTROL POS データ]</li><li>[!UICONTROL CRM データ]</li><li>[!UICONTROL サーベイデータ]</li><li>[!UICONTROL コールセンターデータ]</li><li>[!UICONTROL 製品データ]</li><li> [!UICONTROL アカウントデータ]</li><li> [!UICONTROL トランザクションデータ]</li><li>[!UICONTROL 顧客フィードバックデータ]</li><li> [!UICONTROL その他]</li></ul>このフィールドは、使用中のデータソースのタイプを調査するために使用します。 |
| **[!UICONTROL 新しいデータをインポート]** | 継続的な接続を確立する場合は、このオプションを有効にします。 継続的な接続を行うと、データセットに追加された新しいデータバッチが Workspace で自動的に使用できます。 |
| **[!UICONTROL データセットのバックフィル]** | 既存のすべてのデータを確実にバックフィルするには、「**[!UICONTROL 既存のすべてのデータをバックフィル]**」を有効にします。<br/><br/>特定の期間の履歴データをバックフィルするには、「**[!UICONTROL バックフィルをリクエスト]**」を選択します。 データセットのバックフィル期間を最大 10 個定義できます。<ol><li>開始データと終了データを入力するか、![カレンダー](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) を使用して日付を選択して期間を定義します。</li><li>「**[!UICONTROL キューのバックフィル]**」を選択してバックフィルをリストに追加するか、「**[!UICONTROL キャンセル]**」を選択してキャンセルします。</li></ol>各エントリについて、期間を編集するには ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) を選択し、エントリを削除するには ![削除](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) を選択します。<br/><br/>バックフィルについて：<ul><li>各データセットを個別にバックフィルできます。</li><li>接続内のデータセットに追加された新しいデータが優先されるので、この新しいデータの待ち時間が最も短くなります。</li><li>バックフィル（履歴）データのインポートには時間がかかります。 履歴データの量は待ち時間に影響を与えます。</li><li>Analytics ソースコネクタは、実稼動用サンドボックスに（サイズに関係なく）最大 13 か月分のデータを読み込みます。 非実稼動用サンドボックスのバックフィルは、3 か月に制限されています。</li></ul> |
| **[!UICONTROL データセットを変換]** | 特定の B2B ルックアップデータセットでは、適切な B2B ユーザーベースのレポートシナリオに対応するデータセットの変換を有効にすることができます。 詳しくは、[B2B ルックアップ用にデータセットを変換](transform-datasets-b2b-lookups.md)を参照してください。 |
| **[!UICONTROL バッチステータス]** | 次に、使用可能なステータスインジケーターを示します。<ul><li>成功</li><li>X 個のバックフィルが処理中</li><li>オフ</li></ul> |
| **[!UICONTROL データセット ID]** | この ID は自動的に生成されます。 |
| **[!UICONTROL 説明]** | データセットの作成時にこのデータセットに付与される説明。 |
| **[!UICONTROL レコード数]** | データセットのサイズ。 |
| **[!UICONTROL スキーマ]** | Adobe Experience Platform で作成されたデータセットに基づくスキーマ。 |
| **[!UICONTROL データセット]** | データセットの名前。 |
| **[!UICONTROL プレビュー：*データセット名&#x200B;*]** | 最初の 10 行および最初の 10 列のデータセットをプレビューします。 |
| **[!UICONTROL 削除]** | 接続全体を削除しなくても、データセットを削除して、[!UICONTROL  ユーザー ID] または [!UICONTROL  アカウント ID] [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} を変更できます。 削除すると、データの取り込みに伴うコストと、接続全体および関連するデータビューを再作成する煩雑なプロセスが削減されます。 |

{style="table-layout:auto"}

## 接続プレビュー {#preview}

作成した接続をプレビューするには、接続設定ダイアログで「![PageSearch](/help/assets/icons/PageSearch.svg)**[!UICONTROL 接続プレビュー]**」を選択します。

![接続プレビュー](assets/create-conn4.png)

このプレビューには、接続設定の一覧を示す列がいくつか含まれています。 表示される列タイプは、個々のデータセットによって異なります。


## 接続マップ

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}

接続に含まれるデータセット間の関係のマップを表示するには、接続設定ダイアログで ![GraphPathing](/help/assets/icons/GraphPathing.svg)**[!UICONTROL Connection map]** を選択します。

![ 接続マップ ](assets/connectionmap.png)

このマップは、接続を定義した方法をより深く理解し、識別子を使用してイベント、プロファイル、ルックアップデータセット間の関係を設定するのに役立ちます。

## データセットタイプ {#dataset-types}

[!UICONTROL Customer Journey Analytics] は、この接続に追加した各データセットに対して、受信するデータに基づいてデータセットタイプを自動的に設定します。

>[!IMPORTANT]
>
>少なくとも 1 つのイベントまたは概要データセットを接続の一部として追加します。

データセットには、[!UICONTROL イベント]データ、[!UICONTROL プロファイル]データ、[!UICONTROL ルックアップ]データおよび[!UICONTROL 概要]データなど、様々なタイプがあります。

| データセットタイプ | 説明 | タイムスタンプ | スキーマ | 人物 ID <br/> アカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} |
|---|---|---|---|---|
| **[!UICONTROL イベント]** | イベントの時間を表すデータ。 例えば、web 訪問数、インタラクション、トランザクション、POS データ、サーベイデータ、広告インプレッションデータなどがあります。 このデータには、顧客 ID または cookie ID とタイムスタンプを含む一般的なクリックストリームデータを使用できます。 イベントデータを使用すると、ユーザー ID として使用する ID を柔軟に設定できます。 | [!UICONTROL Experience Platform] のイベントベースのスキーマからデフォルトのタイムスタンプフィールドへと自動的に設定されます。 | 「時系列」動作を持つ XDM クラスに基づいた組み込みスキーマまたはカスタムイベント。 例として、「XDM エクスペリエンスイベント」や「XDM 決定イベント」などがあります。 | 含めるユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} を選択できます。 Experience Platform で定義された各データセットスキーマは、1 つ以上の定義済み ID のセットを持つことができ、ID 名前空間に関連付けられます。 これらの ID のいずれかを人物 ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} として使用できます。 例としては、Cookie ID、スティッチされた ID、ユーザー ID、トラッキングコード、アカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} などがあります。 |
| **[!UICONTROL ルックアップ]** | すべてのデータセットタイプ（プロファイルデータセット、ルックアップデータセット、イベントデータセット）内のフィールドのルックアップとしてデータセットを追加できます（後者は常にサポートされていました）。 この追加機能により、B2B を含む複雑なデータモデルをサポートする Customer Journey Analytics の機能が拡張されます。 このデータは、イベント、プロファイルまたはルックアップデータにある値やキーを検索するために使用します。 最大 2 レベルのルックアップを追加できます。 （[派生フィールド](/help/data-views/derived-fields/derived-fields.md)は、接続内のルックアップに一致するキーとして使用できません）。例えば、イベントデータ内の数値 ID を製品名にマッピングするルックアップデータをアップロードできます。詳しくは、[B2B の例](/help/use-cases/b2b/example.md)を参照してください。 | 該当なし | 「XDM 個別プロファイル」クラスを除いて、「レコード」動作を持つ XDM クラスに基づいた、組み込みまたはカスタムのスキーマです。 | 該当なし |
| **[!UICONTROL プロファイル]** | [!UICONTROL  イベント ] データのアカウント、人物、ユーザーまたは顧客に適用されるデータ。 例えば、顧客に関する CRM データをアップロードできます。 | 該当なし | 「XDM 個別プロファイル」クラスに基づいた組み込みスキーマまたはカスタムイベント。 | 含めるユーザー ID / アカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} を選択できます。 [!DNL Experience Platform] で定義された各データセット（概要データセットを除く）には、1 つ以上のユーザー ID またはアカウント ID [!BADGE B2B edition} の独自のセットが定義されてい ]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} す。 例えば、Cookie ID、スティッチ ID、ユーザー ID、トラッキングコードアカウント ID などです。<br>![ユーザー ID ](assets/person-id.png)**メモ**：異なる ID のデータセットを含む接続を作成すると、レポートに反映されます。 データセットを結合するには、同じユーザー ID またはアカウント ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} を使用する必要があります。 |
| **概要** | 個々のユーザー ID に関連付けられていない時系列データ。 概要データは、キャンペーンなど、様々な集計レベルでの集計データを表します。 このデータを Customer Journey Analytics で使用して、様々なユースケースをサポートできます。 詳しくは、[概要データ](/help/data-views/summary-data.md)を参照してください。 | Experience Platform のイベントベースの概要指標スキーマからデフォルトのタイムスタンプフィールドへと自動的に設定されます。 時間単位または日単位の精度のみがサポートされます。 | 「XDM 概要指標」クラスに基づいた組み込みスキーマまたはカスタムスキーマ。 | 該当なし |

>[!MORELIKETHIS]
>
>ブログ：[Adobe Customer Journey Analyticsでイベント、ルックアップ、プロファイルのデータセットを活用する方法 ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-to-leverage-event-lookup-and-profile-datasets-in-adobe/ba-p/681478)

## ルックアップキーおよびルックアップ値としての数値フィールドの使用 {#numeric}

このルックアップ機能は、文字列ベースのキーフィールドに、コストやマージンなどの数値フィールドを追加する場合に便利です。 この機能を使用すると、キーまたは値として、数値をルックアップの一部にすることができます。 ルックアップスキーマでは、例えば、製品名、COGS、キャンペーンマーケティングコスト、マージンなどに数値を関連付けることができます。 次に、Adobe Experience Platform のルックアップスキーマの例を示します。

![ルックアップスキーマ](assets/schema.png)

これらの値を指標またはディメンションとして Customer Journey Analytics レポートに取り込むことができるようになりました。 接続を設定してルックアップデータセットを取り込む際に、データセットを編集して[!UICONTROL キー]と[!UICONTROL 一致するキー]を選択できます。

![データセットを編集](assets/lookup-dataset.png)

この接続に基づいてデータビューを設定すると、数値がコンポーネントとしてデータビューに追加されます。 このデータビューに基づくプロジェクトでは、これらの数値についてレポートできます。

## ユーザー ID としての ID マップの使用 {#id-map}

Customer Journey Analytics で、ユーザー ID に ID マップを使用する機能がサポートされます。 ID マップは、キーと値のペアをアップロードできるマップデータ構造です。 キーは ID 名前空間で、値は ID 値を保持する構造体です。 アップロードされた各行／イベントに ID マップが存在し、それに応じて各行に対して値が設定されます。

ID マップは、[ExperienceEvent XDM](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home) クラスに基づくスキーマを使用するデータセットで使用できます。 Customer Journey Analytics 接続に含めるデータセットを選択する場合、次のオプションを使用して、フィールドをプライマリ ID または ID マップとして選択できます。

![](assets/idmap1.png)

「ID マップ」を選択すると、次の 2 つの追加の設定オプションが表示されます。

| オプション | 説明 |
|---|---|
| **[!UICONTROL プライマリ ID 名前空間を使用]** | このオプションでは、Customer Journey Analytics に対し、`primary=true` 属性でマークされた ID マップ内の ID を検索し、その行のユーザー ID として使用します。 この ID は、Experience Platform でパーティション分割に使用するプライマリキーです。 また、この ID は、Customer Journey Analytics のユーザー ID として使用する主な候補でもあります（Customer Journey Analytics 接続でのデータセットの設定方法に応じて異なります）。 |
| **[!UICONTROL 名前空間]** | （このオプションは、プライマリ ID 名前空間を使用しない場合にのみ使用できます）。ID 名前空間は、[Experience Platform ID サービス](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)のコンポーネントです。名前空間は、ID が関連付けられているコンテキストを示します。 名前空間を指定すると、Customer Journey Analytics は各行の ID マップでこの名前空間キーを検索し、その名前空間の ID をその行のユーザー ID として使用します。 Customer Journey Analytics は、すべての行の完全なデータセットスキャンを実行して、存在する名前空間を判断することはできません。そのため、使用可能なすべての名前空間がドロップダウンリストに表示されます。 データ内で指定されている名前空間を把握します。これらの名前空間は自動検出されません。 |

{style="table-layout:auto"}

### ID マップのエッジケース {#id-map-edge}

次の表に、エッジケースが存在する場合の 2 つの設定オプションと、その処理方法を示します。

| オプション | ID マップに ID が存在しない | 複数の ID、プライマリに指定されているものはない | 複数の ID がプライマリとして指定されている | 単一の ID、プライマリか非プライマリか指定されている | ID がプライマリとして指定されている無効な名前空間 |
|---|---|---|---|---|---|
| 「**[!UICONTROL プライマリ ID 名前空間を使用]」がオンになっている** | Customer Journey Analytics によって行が削除されます。 | プライマリ ID が指定されていないので、Customer Journey Analytics によって行が削除されます。 | すべての名前空間の下で、プライマリと指定されたすべての ID がリストに抽出されます。 その後、アルファベット順に並べ替えられます。この新しい並べ替えでは、最初の ID を持つ最初の名前空間がユーザー ID として使用されます。 | 単一の ID がユーザー ID として使用されます。 | 名前空間が無効である（Adobe Experience Platform に存在しない）場合でも、Customer Journey Analytics は、その名前空間のプライマリ ID をユーザー ID として使用します。 |
| 「**[!UICONTROL 特定の ID マップ名前空間]」が選択されている** | Customer Journey Analytics によって行が削除されます。 | 選択した名前空間に属するすべての ID がリストに抽出され、最初の ID がユーザー ID として使用されます。 | 選択した名前空間に属するすべての ID がリストに抽出され、最初の ID がユーザー ID として使用されます。 | 選択した名前空間に属するすべての ID がリストに抽出され、最初の ID がユーザー ID として使用されます。 | 選択した名前空間に属するすべての ID がリストに抽出され、最初の ID がユーザー ID として使用されます。 （接続の作成時には有効な名前空間のみを選択できるので、無効な名前空間／ID をユーザー ID として使用することはできません）。 |

{style="table-layout:auto"}

## 毎日のイベントの平均数を計算する {#average-number}

この計算は、接続内のすべてのデータセットに対して実行されます。

1. [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home) に移動して、クエリを作成します。

   クエリは次のようになります：

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   この例では、「analytics_demo_data」がデータセットの名前です。

2. Adobe Experience Platform に存在するすべてのデータセットを表示するために、`Show Tables` クエリを実行します。


## 大規模なルックアップデータセットのアルゴリズムプルーニング

接続を作成する際に、ルックアップ用に大規模なデータセットを追加できます。 例えば、レポートやビジュアライゼーションを作成する際に、説明的な製品情報を検索できるように、製品カタログを表すデータセットを指定できます。 このような大規模なルックアップデータセットでは、現在ガードレールとして実装されている一意のルックアップの最大数が 1,000 万件を超え、追加のデータがスキップされる可能性があります。

大規模なルックアップデータセットのアルゴリズムによるプルーニングをリクエストできます。 このアルゴリズムによるプルーニングでは、イベントデータセット内のキーと一致するデータのみをルックアップデータセットに保持します。 これにより、プルーニングされていないルックアップデータセット全体を読み込む必要がなくなります。 使用頻度の低い古い項目は削除されます。その結果、レポートにわずかに影響を与える可能性がありますが、大きなメリットがもたらされます。 アルゴリズムは 90 日間遡り、毎週更新します。

詳細について、およびこの機能を有効にするには、担当のアドビサポートチームにお問い合わせください。
