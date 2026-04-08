---
title: ステッチを有効にする
description: Customer Journey Analyticsでイベントデータセットのステッチを有効にします。 接続UIで、永続的ID、ユーザーID、再生ウィンドウを設定します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: d42f0eb658f26d16bd21bb6ca47d5dd7c228e614
workflow-type: tm+mt
source-wordcount: '1717'
ht-degree: 4%

---

# ステッチを有効にする

接続の一部として設定した1つ以上のイベントデータセットでステッチを有効にできます。 ライセンスを取得したCustomer Journey Analytics パッケージによって、ステッチに使用できるイベントデータセットの数が決まります。

接続[を](/help/connections/create-connection.md#dataset-settings)作成する場合、または[接続を編集する場合](/help/connections/create-connection.md)は、イベントデータセットの[&#x200B; データセット設定](/help/connections/manage-connections.md#edit-a-connection)の一部としてステッチを有効にします。

## 前提条件

指定したステッチ方法の前提条件を確認して満たす必要があります。[&#x200B; フィールドベースのステッチ &#x200B;](fbs.md#prerequisites)または[&#x200B; グラフベースのステッチ &#x200B;](gbs.md#prerequisites)。

## プリフライトチェック

前提条件を満たしている場合は、ID合成を有効にする前に、イベントデータセットのデータに対してプリフライトチェックを実行することをお勧めします。

* 永続的なIDまたは人物IDに[Experience Data Model （XDM）スキーマ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home) フィールドを使用する場合は、イベントデータセットのスキーマでIDが適切にマークされていることを確認してください。 [ID名前空間の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)を参照してください。
* 永続的IDと個人IDの両方のID カバレッジを確認します。

   * **[!UICONTROL 永続的ID]**

     永続的ID フィールドがnullではない7日間のデータをクエリし、データセット内のすべてのイベントの7日間のデータのクエリで割ります。 この割合は95%以上である必要があります。

     検証に使用できるクエリの例：

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     ここで：

      * `{PERSISTENT_ID_FIELD}`は永続IDのフィールドです。 例：`identityMap.ecid[0]`。
      * `{DATASET_TABLE_NAME}`は、イベントデータセットのテーブル名です。
      * `{FORMAT_STRING}`は、タイムスタンプフィールドの書式文字列です。 例：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE}`は開始日です。 例：`2024-01-01 00:00:00`。
      * `{END_DATE}`は標準形式の終了日です。 例：`2024-01-08 00:00:00`。


   * **[!UICONTROL ユーザー ID]**
      * グラフベースの合成の場合、ID グラフに、選択した永続的ID名前空間と人物ID名前空間のID値をリンクするフラグメントが含まれていることを確認します。 [Experience Platform ID グラフビューア &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"}に移動してテストを実行し、サンプルの永続的ID値を使用してグラフをクエリできます。 これらの永続的ID値がグラフ内の人物ID値にリンクされているかどうかを確認します。
      * フィールドベースのステッチの場合は、個人ID フィールドがnullでない7日間のデータをクエリし、データセット内のすべてのイベントの7日間のデータのクエリで割ります。 この割合は、理想的には5%を超えるはずです。

        検証に使用できるクエリの例：

        ```sql
        SELECT
          COUNT(*) AS total_events,
          COUNT({PERSON_ID_FIELD}) AS events_with_personid,
          ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
        FROM 
          {DATASET_TABLE_NAME}
        WHERE
          TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
          AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
        ```

        ここで：

         * `{PERSON_ID_FIELD}`は人物IDのフィールドです。 例：`identityMap.crmId[0]`。
         * `{DATASET_TABLE_NAME}`は、イベントデータセットのテーブル名です。
         * `{FORMAT_STRING}`は、タイムスタンプフィールドの書式文字列です。 例：`MM/DD/YY HH12:MI AM`。
         * `{START_DATE}`は開始日です。 例：`2024-01-01 00:00:00`。
         * `{END_DATE}`は標準形式の終了日です。 例：`2024-01-08 00:00:00`。



## ID ステッチを有効にする {#enable-identity-stitching}

個人ベースの接続でイベントデータセットを[追加](/help/connections/create-connection.md#add-datasets)または[編集](/help/connections/create-connection.md#edit-a-dataset)すると、IDの合成を有効にできます。 IDの合成は、アカウントベースの接続では使用できません。

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="ID グラフへの変更"
>abstract="ステッチに ID グラフを使用する前に、ID グラフの設定が完了していることを確認します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/stitching/gbs" text="グラフベースのステッチ"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="ユーザー ID"
>abstract="使用可能な ID からユーザー ID （ユーザーの一意の ID）を選択します。 ライセンスにグラフベースのステッチが含まれており、そのステッチ方法を使用する場合は、**[!UICONTROL ID グラフ]**&#x200B;を選択します。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics"
>title="指標をつなぎ合わせる"
>abstract="ステッチ指標は、過去7日間のイベントタイムスタンプを含むデータのサンプルセットを使用して計算されます。<br>このデータのサンプルセットは、通常、**[!UICONTROL Preview]** テーブルで使用されるサンプルデータとは異なります。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_gbs_personidcoverage"
>title="人物ID カバレッジ"
>abstract="ステッチプロセス（ライブおよびリプレイ）中に識別に使用される、選択した人物IDのカバー範囲。<br/>最適なステッチ結果を得るには、各永続的IDのID グラフに（永続的ID、人物ID）関係を含める必要があります。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_fbs_personidcoverage"
>title="人物ID カバレッジ"
>abstract="ステッチプロセス（ライブおよびリプレイ）中に識別に使用される、選択した人物IDのカバー範囲。<br/>最適なステッチ結果を得るには、永続ID （デバイス情報）ごとに少なくとも1つのイベントで人物ID （ユーザー情報）を送信する必要があります。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_persistentidcoverage"
>title="永続的なID カバレッジ"
>abstract="この値は、個人ID値を検出できない場合に備えて、ステッチプロセス（ライブおよびリプレイ）中の識別に使用されます。 <br/>永続的なIDがなく、ユーザーIDのないイベントがデータから削除されます。 最適なステッチ結果を得るには、すべてのイベントに永続的なIDが存在する必要があります。"


>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_badids"
>title="不正 ID"
>abstract="不正なIDは、レポートデータに深刻な影響を与えるID値です。"
>additional-url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/technotes/badids" text="不正 ID"


### データセット設定

結合を有効にするには、**[!UICONTROL データセットを追加]**&#x200B;または&#x200B;**[!UICONTROL データセットを編集]** ダイアログの「**[!UICONTROL データセット設定]**」セクションで行います。

![機能を有効にする際のID ステッチ オプション &#x200B;](assets/identity-stitching-ui.png)

1. 「**[!UICONTROL ID ステッチを有効にする]**」を選択します。

   接続で保存されたイベントデータセットのステッチを有効または無効にすると、**[!UICONTROL 人物IDの変更]** ダイアログに、人物IDの変更の影響が表示されます。 続行するには、**[!UICONTROL 続行]**&#x200B;を選択してください。

   **[!UICONTROL IDの結合を有効にする]** ダイアログでは、IDの結合の結果が要約されます。 続行するには、**[!UICONTROL 続行]**&#x200B;を選択してください。

1. 「**[!UICONTROL 永続ID]**」ドロップダウンメニューから永続IDを選択します。

   永続的IDに&#x200B;**[!UICONTROL ID マップ]**&#x200B;を選択する場合は、名前空間を選択します。 選択肢は次の2つです。

   * 「**[!UICONTROL プライマリ ID名前空間を使用]**」を選択して、プライマリ ID名前空間を使用します。
   * **[!UICONTROL 名前空間]** ドロップダウンメニューから名前空間を選択します。

1. 「**[!UICONTROL 人物ID]**」ドロップダウンメニューから人物IDを選択します。

   ユーザーIDに「**[!UICONTROL ID マップ]**」を選択した場合は、名前空間を選択します。 選択肢は次の2つです。

   * 「**[!UICONTROL プライマリ ID名前空間を使用]**」を選択して、プライマリ ID名前空間を使用します。
   * **[!UICONTROL 名前空間]** ドロップダウンメニューから名前空間を選択します。

   人物IDに「**[!UICONTROL ID グラフ]**」を選択した場合（[&#x200B; グラフベースのステッチ &#x200B;](/help/stitching/gbs.md)）は、名前空間を選択する必要があります。

   >[!NOTE]
   >
   >ID グラフを使用する権利を有していることを確認します。
   >

   その前に、データセットのID グラフの設定が完了したことを確認するために、**[!UICONTROL ID グラフへの変更]** ダイアログが表示されます。 この設定は、[&#x200B; グラフベースの前提条件](/help/stitching/gbs.md#prerequisites)の一部であり、ID グラフをステッチに使用できます。 続行するには、**[!UICONTROL 続行]**&#x200B;を選択してください。

   * **[!UICONTROL 名前空間]** ドロップダウンメニューから名前空間を選択します。

1. **[!UICONTROL 再生ウィンドウ]** ドロップダウンメニューから再生ウィンドウを選択します。 使用可能なオプションは、使用権限のあるCustomer Journey Analytics パッケージによって異なります。

1. **[!UICONTROL 次へ]**&#x200B;を選択すると、ステッチの対象となるイベントデータセットのプレビューが表示されます。


### データセットのプレビュー

標準の&#x200B;**[!UICONTROL データセットのプレビュー]** インターフェイスに加えて、個人ベースの接続で[追加](/help/connections/create-connection.md#add-datasets)または[編集](/help/connections/create-connection.md#edit-a-dataset) データセットを追加すると、2つの追加情報パネルが使用できます。

![機能を有効にする際のID ステッチ オプション &#x200B;](assets/identity-stitching-ui-preview.png)

#### 指標をつなぎ合わせる

>[!AVAILABILITY]
>
>ステッチ指標は、グラフベースのステッチでは使用できません。
>

**[!UICONTROL ステッチ指標]**&#x200B;は、過去7日間のイベントタイムスタンプを含むデータのサンプルセットを使用して計算されます。 このデータのサンプルセットは、通常、**[!UICONTROL Preview]** テーブルで使用されるサンプルデータとは異なります。 指標を結合すると、次の項目の詳細が表示されます。

* **[!UICONTROL 人物ID カバレッジ]**：ステッチプロセス（ライブおよびリプレイ）中に識別に使用される、選択した人物IDのカバレッジ。
   * フィールドベースのステッチングを最適に行うには、永続ID （デバイス情報）ごとに少なくとも1つのイベントで個人ID （ユーザー情報）を送信する必要があります。
   * 最適なグラフベースのステッチ結果を得るには、各永続的IDのID グラフに（永続的ID、人物ID）リレーションを存在させる必要があります。

  個人IDのカバレッジはパーセントで表示され、安定した開発または実稼動設定で推奨されるものと比較されます。 このカバレッジ値が高いほど、選択した人物IDでより良いステッチ結果が得られます。

* **[!UICONTROL 永続的ID カバレッジ]**：この値は、人物ID値を検出できない場合に、ステッチ プロセス（ライブおよびリプレイ）中に識別するために使用されます。 永続的なIDとユーザーIDがないイベントは、データから削除されます。 最適なステッチ結果を得るには、すべてのイベントに永続的なIDが存在する必要があります。

  永続的なID カバレッジは、パーセントで表示され、安定した開発または実稼動設定で推奨される最小値と比較されます。

#### 不正 ID

>[!AVAILABILITY]
>
>無効なIDは、グラフベースのステッチングでは使用できません。
>

>[!INFO]
>
>Customer Journey Analyticsのインターフェイスでは、不正なIDはBAVIDとも呼ばれます。
> 

Customer Journey Analyticsでは、不正なIDは次のIDです。

* ステッチが有効なデータセットの永続的IDまたは個人ID フィールドから取得した特定のID値を持つ&#x200B;**および**
* 1か月以内に接続データ内の100万以上（1,000,000）のイベントに存在します。

ID値が不正IDとしてマークされている場合、そのID値を含む将来のイベントは接続データから破棄され、レポートには表示されません。

不正なIDの使用例：

* ユーザーID フィールドにカスタムまたはプレースホルダー値があります（例：`undefined`）。 このような値は、[&#x200B; データ品質のステッチとレポートにも影響する可能性があります](/help/stitching/faq.md#undefined-person-id-values)。
* フィールドベースのステッチ設定で、複数のユーザーがデバイスを共有し、ユーザー間のトランジションの合計数が50,000を超える場合。 このシナリオでは、ステッチプロセスは停止して、そのデバイスの個人ID情報を使用し、代わりに永続的ID情報のみを使用します。 その結果、そのデバイスからのすべてのデータセットイベントは、永続的なID ID IDを持つ接続データに送信され、不正なIDの状況が発生する可能性が高くなります。


>[!NOTE]
>**[!UICONTROL 不正ID]**&#x200B;を含む&#x200B;**[!UICONTROL 結合指標]**&#x200B;は、限られたデータセットに基づいて計算されます。 結合に使用するデータセットの不正なIDの存在を特定するには、[不正なIDのテクニカルノート &#x200B;](/help/technotes/badids.md)を参照してください。
>


### 保存

接続を保存すると、これらのデータセットのデータの取り込みが開始するとすぐに、有効なデータセットをステッチするためのステッチプロセスが開始されます。

>[!CAUTION]
>
>接続インターフェイスでステッチが有効になっているデータセットの場合、バックフィルのステータスは、完了したバックフィルの数に対して![Status green](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _backfills completed]**&#x200B;と直ちに誤って報告されます。 他の方法を使用して、ステッチされたデータセットのデータがバックフィルされているかどうかを確認します。
>


## 制限事項

[&#x200B; フィールドベースのステッチ制限](/help/stitching/fbs.md#limitations)と[&#x200B; グラフベースのステッチ制限](/help/stitching/gbs.md#limitations)に加えて、接続インターフェイスでステッチを有効にすると、次の制限が適用されます。

* イベントデータセットは、1つの接続の一部として1回のみ結合できます。 同じイベントデータセットを複数回定義し、各インスタンスに個別のステッチ設定を使用することはできません。 同じデータセットに異なるステッチ設定を適用する場合は、設定ごとに個別の接続を使用します。


## 移行

接続インターフェイスでステッチを有効にすると、リクエストベースのステッチで問題なく共存できます。

例えば、以前または現在のステッチリクエストの結果として、web ベースのステッチされたデータセットがデータレイクにあります。 接続インターフェイスを使用して、コールセンターのデータセットからステッチされたデータを追加し、そのデータをweb ベースのデータと組み合わせることができます。

最終的に、Adobeは、リクエストベースのステッチされたデータセットを、新しいステッチの接続エクスペリエンスに移行します。
