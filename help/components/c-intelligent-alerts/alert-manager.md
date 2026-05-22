---
description: アラートの管理方法。
title: アラートの管理
feature: Workspace Basics
role: User, Admin
exl-id: 174c3ebd-a77b-4403-ae9a-bb0cff4bcca6
TQID: https://experienceleague.adobe.com/oKewVodxYwDlnsuqGclK6ZYEmN-pXNqbc5ud6OkIUK4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: de8f8e06f074fdcb0219ce7286785d870c2093b4
workflow-type: tm+mt
source-wordcount: 589
ht-degree: 22%

---

# アラートの管理


中央の[!UICONTROL  アラート ]管理インターフェイスから、アラートのフィルタリング、タグ付け、削除、名前の変更、コピー、有効化、更新の無効化、エクスポートを行うことができます。 アラートを管理するには：

* メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL アラート]**」を選択します。

アラートマネージャーは、[ セグメントマネージャー](/help/components/segments/seg-manage.md)と[計算指標マネージャー](/help/components/calc-metrics/cm-workflow/cm-manager.md)のような構造になっています。


## アラートマネージャー

アラートマネージャーには、次のインターフェイス要素があります。

![フィルターインターフェイス](assets/alerts-manager.png)

### アラートリスト

アラート リスト ➊には、作成したアラートが表示されます。 管理者の場合は、すべてのアラートが表示されます。

リストには、次の列があります。

| 列 | 説明 |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | ![Star](/help/assets/icons/Star.svg)を優先するか、![StarOutline](/help/assets/icons/StarOutline.svg)をアラートから除外するかを選択します。 |
| **[!UICONTROL タイトルと説明]** | アラートを編集するには、タイトルリンクを選択します。これにより、[ アラートビルダー](alert-builder.md#alert-builder)が開きます。 |
| **[!UICONTROL タイプ]** | このアラートがCustomer Journey Analytics データ アラートかServer Call usage アラートかを示します。 |
| **[!UICONTROL 有効]** | アラートが有効か無効かを示します。 |
| **[!UICONTROL データビュー]** | このアラートが適用されるデータビュー。 |
| **[!UICONTROL 所有者]** | アラートの所有者。 管理者以外の場合は、自分が所有するアラートのみが表示されます。 管理者はすべてのアラートを確認できます。 |
| **[!UICONTROL タグ]** | このアラートのタグ。 |
| **[!UICONTROL 有効期限]** | アラートの有効期限が切れるように設定されている日時。 |
| **[!UICONTROL 変更日時]** | アラートが最後に変更された日時。 |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

アクション バー➋を使用して、アラートに対してアクションを実行できます。 アクションバーには、次のアクションが含まれます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 追加]** | [ アラートビルダー](alert-builder.md#alert-builder)を使用して、別のアラートを追加します。 |
| ![検索](/help/assets/icons/Search.svg) | [!UICONTROL *タイトルで検索*] | リストでアラートが選択されていない場合は、この検索フィールドを使用してアラートを検索します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 選択したアラートにタグを付けます。 **[!UICONTROL タグのアラート]** ダイアログで、選択したアラートのタグを選択または選択解除します。 選択したアラートのタグを保存するには、**[!UICONTROL 保存]**&#x200B;を選択します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択したアラートを削除します。 確認メッセージが表示されます。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | 選択した1つのアラートの名前を変更します。 選択すると、アラートの名前をインラインで変更できます。 |
| ![コピー](/help/assets/icons/Copy.svg) | **[!UICONTROL コピー]** | 選択したアラートをコピーします。 新しいアラートが、同じ名前とサフィックス `(Copy)`で作成されます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 有効]**&#x200B;または&#x200B;**[!UICONTROL 無効]** | 選択したアラートを有効または無効にします。 |
| ![更新](/help/assets/icons/Refresh.svg) | **[!UICONTROL 更新]** | アラートの有効期限日を更新します。 有効期限は、元の有効期限に関係なく、このオプションを選択した日から1年間延長されます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV に書き出し]** | アラートを`Alerts List.csv` ファイルにエクスポートします。 |


### アクティブなフィルターバー

フィルターバー➌には、フィルターパネルからアラートのリスト（存在する場合）に適用されたアクティブなフィルターが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。 複数のフィルターを指定した場合は、「**[!UICONTROL すべて削除]**」を使用すると、すべてのフィルターを削除できます。


### フィルターパネル

![ フィルター](/help/assets/icons/Filter.svg) **[!UICONTROL フィルター]**&#x200B;左側のパネル ➍を使用して、アラートのリストをフィルターできます。 フィルターパネルには、フィルターのタイプと、特定のフィルターを適用するアラートの数が表示されます。


1. 「![フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターパネルを開きます。 アラートリストの空き容量が必要な場合は、![ フィルター](/help/assets/icons/Filter.svg)をもう一度選択してパネルを閉じることができます。
1. 使用可能なフィルターセクションからフィルターを選択します。


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



## アラートを編集

アラートは

* [[!UICONTROL  アラート ] リスト ](#alerts-list)で、アラートのタイトルを選択します。

[ アラートビルダー](alert-builder.md#alert-builder)を使用して、アラートを編集します。

## アラートのトラブルシューティング

アラートに関する問題のトラブルシューティングを行う場合は、JID （Job Instance ID）番号をAdobe サポートに提供します。 JID番号は、受信したアラートメール通知の下部にあります。

![アラートメール](assets/alerts-email.PNG)
