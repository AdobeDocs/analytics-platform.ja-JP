---
description: アラートの管理方法について説明します。
title: アラートの管理
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 22%

---

# アラートの管理


一元的な [!UICONTROL &#x200B; アラート &#x200B;] 管理インターフェイスから、アラートのフィルタリング、タグ付け、削除、名前変更、コピー、有効化、更新の無効化および書き出しを行うことができます。 アラートを管理するには、以下の手順に従います。

* メインインターフェイスで **[!UICONTROL コンポーネント]** を選択し、「**[!UICONTROL アラート]**」を選択します。

アラートマネージャーは、[ セグメントマネージャー ](/help/components/segments/seg-manage.md) および [ 計算指標マネージャー ](/help/components/calc-metrics/cm-workflow/cm-manager.md) のような構造になっています。


## アラートマネージャー

アラートマネージャーには、次のインターフェイス要素があります。

![フィルターインターフェイス](assets/alerts-manager.png)

### アラートリスト

アラートリスト ➊ は、所有するすべてのアラート、すべてのプロジェクトを対象としたアラート、自分と共有されているアラートが表示されます。 リストには、次の列があります。

| 列 | 説明 |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | アラートを ![ 星 ](/help/assets/icons/Star.svg) または ![ 星アウトライン ](/help/assets/icons/StarOutline.svg) に優先するかどうかを選択します。 |
| **[!UICONTROL タイトルと説明]** | アラートを編集するには、タイトルリンクを選択して [ アラートビルダー ](alert-builder.md#alert-builder) を開きます。 |
| **[!UICONTROL タイプ]** | アラートがCustomer Journey Analytics データアラートであるか、サーバーコールの使用状況アラートであるかを示します。 |
| **[!UICONTROL 有効]** | アラートが有効か無効かを示します。 |
| **[!UICONTROL データビュー]** | このアラートが適用されるデータビュー。 |
| **[!UICONTROL 所有者]** | アラートの所有者。 管理者以外のユーザーには、自分が所有しているアラートまたは自分と共有されているアラートのみが表示されます。 |
| **[!UICONTROL タグ]** | このアラートのタグ。 |
| **[!UICONTROL 有効期限]** | アラートの有効期限が切れるように設定された日時。 |
| **[!UICONTROL 変更日時]** | アラートが最後に変更された日時。 |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

アクションバーの ➋ を使用して、アラートに対するアクションを実行できます。 アクションバーには、次のアクションが含まれます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 追加]** | [ アラートビルダー ](alert-builder.md#alert-builder) を使用して、別のアラートを追加します。 |
| ![検索](/help/assets/icons/Search.svg) | [!UICONTROL *タイトルで検索*] | リストでアラートが選択されていない場合は、この検索フィールドを使用してアラートを検索します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 選択したアラートにタグを付けます。 **[!UICONTROL タグアラート]** ダイアログで、選択したアラートのタグを選択または選択解除します。 「**[!UICONTROL 保存]**」を選択して、選択したアラートのタグを保存します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択したアラートを削除します。 確認メッセージが表示されます。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | 選択した 1 つのアラートの名前を変更します。 選択した場合、アラートの名前をインラインで変更できます。 |
| ![コピー](/help/assets/icons/Copy.svg) | **[!UICONTROL コピー]** | 選択したアラートをコピーします。 同じ名前とサフィックスの `(Copy)` を持つ新しいアラートが作成されます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Enable]** または **[!UICONTROL Disable]** | 選択したアラートを有効または無効にします。 |
| ![更新](/help/assets/icons/Refresh.svg) | **[!UICONTROL 更新]** | アラートの有効期限日を更新します。有効期限は、元の有効期限に関係なく、このオプションを選択した日から 1 年間延長されます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV に書き出し]** | アラートを `Alerts List.csv` ファイルに書き出します。 |


### アクティブなフィルターバー

フィルターバー ➌ は、フィルターパネルからアラートのリスト（ある場合）に適用されたアクティブなフィルターが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。複数のフィルターを指定した場合は、「**[!UICONTROL すべて削除]**」を使用すると、すべてのフィルターを削除できます。


### フィルターパネル

アラートのリストは、左のパネル ![ ージの ](/help/assets/icons/Filter.svg) フィルター **&#x200B;**&#x200B;フィルター ➍ を使用してフィルタリングできます。 フィルターパネルには、フィルターのタイプと、特定のフィルターに従うアラートの数が表示されます。


1. 「![フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターパネルを開きます。アラート リスト用にスペースが必要な場合は、もう一度 ![ フィルター ](/help/assets/icons/Filter.svg) を選択してパネルを閉じることができます。
1. 使用可能ないずれかのフィルターセクションからフィルターを選択します。


#### タグフィルターセクション

{{tagfiltersection}}


#### データビューのフィルターセクション

{{dataviewfiltersection}}


#### 所有者フィルターセクション

{{ownerfiltersection}}


#### 有効ステータスのフィルターセクション

{{enabledstatusfiltersection}}


#### タイプのフィルターセクション

{{typefiltersection}}


#### その他のフィルターのフィルターセクション

{{otherfiltersfiltersection}}



## アラートの編集

アラートを編集できます

* [[!UICONTROL &#x200B; アラート &#x200B;] リスト ](#alerts-list) で、アラートのタイトルを選択します。

アラートを編集するには、[ アラートビルダー ](alert-builder.md#alert-builder) を使用します。

## アラートのトラブルシューティング

アラートの問題をトラブルシューティングする際には、Adobe サポートに JID （ジョブインスタンス ID）番号を伝えます。 JID 番号は、受信するアラートメール通知の下部にあります。

![アラートメール](assets/alerts-email.PNG)
