---
title: ステッチの使用
description: ステッチの使用方法
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="ベータ版" type="Informative"
source-git-commit: c67225619153218e3dca1eacea204f2b033dfb14
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 3%

---

# ステッチの使用

接続の一部として設定した 1 つ以上のイベントデータセットに対して、ステッチを有効にすることができます。 ライセンスを取得しているCustomer Journey Analytics パッケージによって、ステッチで有効にできるイベントデータセットの数が決まります。

{{release-limited-testing}}

[&#x200B; 接続の作成 &#x200B;](/help/connections/create-connection.md#dataset-settings) または [&#x200B; 接続の編集 &#x200B;](/help/connections/create-connection.md) を行う際に、イベントデータセットの [&#x200B; データセット設定 &#x200B;](/help/connections/manage-connections.md#edit-a-connection) の一部としてステッチを有効にすることができます。

## 前提条件

接続 UI 内でイベントデータセットのステッチを有効にする手順は次のとおりです。

* データセットのベースとなるスキーマには、次が必要です。

   * id として設定され、永続 ID と人物 ID に異なる値を選択できる複数のフィールド。
   * 永続 ID または人物 ID に ID マップとプライマリ ID 名前空間を使用する場合に、関連する名前空間を持つプライマリ ID としてマークされた少なくとも 1 つのフィールド。

* グラフベースのステッチを使用し、（データセットには永続 ID の横に関連する人物 ID が含まれているので） ID グラフに貢献するイベントデータセットが予想される場合は、[ID サービスのデータセットを有効にする &#x200B;](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) 必要があります。

## プリフライトチェック

前提条件を満たしている場合は、ID ステッチを有効にする前に、イベントデータセット内のデータに対してプリフライトチェックを実行してください。

* イベントデータセットのスキーマで ID が適切にマークされていることを確認します。 [ID 名前空間の概要を参照 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)。
* 永続 ID とユーザー ID の両方で ID カバレッジを確認します。
   * 永続 ID：永続 ID フィールドが null でない場合は 7 日間のデータをクエリし、データセット内のすべてのイベントについて 7 日間のデータのクエリで割ります。 この割合は 95% を超える必要があります。

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

      * `{PERSISTENT_ID_FIELD}` は、永続 ID のフィールドです。 例：`identityMap.ecid[0]`。
      * `{DATASET_TABLE_NAME}` は、イベントデータセットのテーブル名です。
      * `{FORMAT_STRING}` は、タイムスタンプフィールドの書式指定文字列です。 例：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE} ` 開始日。 例：`2024-01-01 00:00:00`。
      * `{END_DATE}` は、標準形式の終了日です。 例：`2024-01-08 00:00:00`。


   * ユーザー ID - ユーザー ID フィールドが null でない場合は 7 日間のデータをクエリし、データセット内のすべてのイベントに対して 7 日間のデータのクエリで割ります。 この割合は 5% を超える必要があります。

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

      * `{PERSON_ID_FIELD}` は、人物 ID のフィールドです。 例：`identityMap.crmId[0]`。
      * `{DATASET_TABLE_NAME}` は、イベントデータセットのテーブル名です。
      * `{FORMAT_STRING}` は、タイムスタンプフィールドの書式指定文字列です。 例：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE}` は開始日です。 例：`2024-01-01 00:00:00`。
      * `{END_DATE}` は、標準形式の終了日です。 例：`2024-01-08 00:00:00`。



## ID ステッチを有効にする

>[!NOTE]
>
>接続インターフェイスで **[!UICONTROL ID ステッチを有効にする]** を使用できない場合は、データセットで [&#x200B; リクエスト手順を使用してステッチを有効にする &#x200B;](/help/stitching/use-stitching.md) を使用します。



ステッチを有効にするには、**[!UICONTROL データセットを追加]** または **[!UICONTROL データセットを編集]** ダイアログのイベントデータセット セクションで、次の手順を実行します。

![ID ステッチを有効にする場合の ID ステッチオプション &#x200B;](assets/identity-stitching-ui.png)

1. 「**[!UICONTROL ID ステッチを有効にする]**」を選択します。

   既存のイベントデータセットに対してステッチを有効にすると、**[!UICONTROL ユーザー ID を変更]** ダイアログに、ステッチを使用したことによるユーザー ID の変更の影響が表示されます。 「**[!UICONTROL 続行]**」を選択して続行します。

   **[!UICONTROL ID ステッチを有効にする]** ダイアログには、ID のステッチの結果の概要が表示されます。 「**[!UICONTROL 続行]**」を選択して続行します。

1. **[!UICONTROL 永続 ID]** ドロップダウンメニューから永続 ID を選択します。

   永続 ID に **[!UICONTROL ID マップ]** を選択する場合は、名前空間を選択する必要があります。 次の 2 つのオプションがあります。

   * **[!UICONTROL プライマリ ID 名前空間を使用]** を有効にして、プライマリ ID 名前空間を使用します。
   * **[!UICONTROL 名前空間]** ドロップダウンメニューから名前空間を選択します。

1. **[!UICONTROL ユーザー ID]** ドロップダウンメニューからユーザー ID を選択します。

   ユーザー ID に **[!UICONTROL ID マップ]** を選択した場合は、名前空間を選択する必要があります。 次の 2 つのオプションがあります。

   * **[!UICONTROL プライマリ ID 名前空間を使用]** を有効にして、プライマリ ID 名前空間を使用します。
   * **[!UICONTROL 名前空間]** ドロップダウンメニューから名前空間を選択します。


   ユーザー ID に **[!UICONTROL ID グラフ]** を選択した場合（[&#x200B; グラフベースのステッチ &#x200B;](/help/stitching/gbs.md) を使用する場合）、名前空間を選択する必要があります。

   >[!NOTE]
   >
   >ID グラフを使用する権限があることを確認します。
   >

   その前に、**[!UICONTROL ID グラフに変更]** ダイアログが表示され、ステッチ用の ID グラフを使用する前に、データセットの ID グラフの設定が [&#x200B; 完了 &#x200B;](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) したことを確認します。 「**[!UICONTROL 続行]**」を選択して続行します。

   * **[!UICONTROL 名前空間]** ドロップダウンメニューから名前空間を選択します。


1. **[!UICONTROL ルックバックウィンドウ]** ドロップダウンメニューからルックバックウィンドウを選択します。 使用できるオプションは、使用資格のあるCustomer Journey Analytics パッケージによって異なります。

接続を保存すると、ステッチが有効なデータセットのステッチプロセスは、これらのデータセットのデータの取り込みが開始されたときに開始されます

## 制限事項

[&#x200B; フィールドベースのステッチの制限 &#x200B;](/help/stitching/fbs.md#limitations) および [&#x200B; グラフベースのステッチの制限 &#x200B;](/help/stitching/gbs.md#limitations) に加えて、接続インターフェイスでステッチを有効にすると次の制限が適用されます。

* イベントデータセットは、1 つの接続の一部として 1 回だけステッチできます。 同じイベントデータセットを複数回定義し、インスタンスごとに別のステッチ設定を使用することはできません。 同じデータセットに異なるステッチ設定を適用する場合は、設定ごとに個別の接続を使用します。

