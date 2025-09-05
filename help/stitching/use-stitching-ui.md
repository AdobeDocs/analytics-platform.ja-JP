---
title: ステッチの使用
description: ステッチの使用方法
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 3%

---

# ステッチの使用

接続の一部として設定した 1 つ以上のイベントデータセットに対して、ステッチを有効にすることができます。 ステッチに対して有効にできるイベントデータセットの数は、ライセンスを取得したCustomer Journey Analytics パッケージによって決まります。

[ 接続の作成 ](/help/connections/create-connection.md#dataset-settings) または [ 接続の編集 ](/help/connections/create-connection.md) を行う際に、イベントデータセットの [ データセット設定 ](/help/connections/manage-connections.md#edit-a-connection) の一部としてステッチを有効にすることができます。

ステッチを有効にするには、**[!UICONTROL データセットを追加]** または **[!UICONTROL データセットを編集]** ダイアログのイベントデータセット セクションで、次の手順を実行します。

![ID ステッチを有効にする場合の ID ステッチオプション ](assets/identity-stitching-ui.png)

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


   ユーザー ID に対して **[!UICONTROL ID グラフ]** を選択した場合は、名前空間を選択する必要があります。

   >[!NOTE]
   >
   >ID グラフを使用する権限が必要です。
   >

   その前に、**[!UICONTROL ID グラフに変更]** ダイアログが表示され、ステッチ用の ID グラフを使用する前に、データセットの ID グラフの設定が [ 完了 ](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) したことを確認します。 「**[!UICONTROL 続行]**」を選択して続行します。

   * **[!UICONTROL 名前空間]** ドロップダウンメニューから名前空間を選択します。


1. **[!UICONTROL ルックバックウィンドウ]** ドロップダウンメニューからルックバックウィンドウを選択します。 使用できるオプションは、使用資格のあるCustomer Journey Analytics パッケージによって異なります。

ID ステッチが有効なデータセットを含む接続を保存すると、各データセットのステッチプロセスは、そのデータセットのデータの取り込みが開始した時点で開始されます。