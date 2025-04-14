---
title: Customer Journey Analyticsで作成されたオーディエンスを管理する方法を学ぶ
description: Customer Journey Analytics でのオーディエンスの管理方法を学ぶ
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 65dcbf63d9e155cb7e04bf9a550151a37b8457e6
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 18%

---

# オーディエンス管理

オーディエンスは、**[!UICONTROL コンポーネント]**/**[!UICONTROL オーディエンス]** を使用して、Customer Journey Analyticsで管理できます。

## Audience Management タスクについて

以前に作成したオーディエンスを管理すると、次のことが可能です。

* オーディエンスの自動更新／アップデートを&#x200B;**スケジュール設定またはスケジュール解除**&#x200B;できます。スケジュールの最大有効期限は 1 年です。
* 有効期限が近づいたら&#x200B;**オーディエンスの更新スケジュールを更新**&#x200B;します。有効期限が近づいたオーディエンスは、予定レポートの有効期限が近づいた場合と同様に扱われます。管理者は、スケジュールの期限が切れる 1 か月前にメールを受け取ります。
* **更新間隔** と **オーディエンスが最後に更新された時刻** を表示します。
* Customer Journey Analyticsから **オーディエンスの作成に要した時間** にinsightを得ます。 オーディエンスがアクティベーション目的でリアルタイム顧客プラットフォームに表示されるまでに要した時間。
* Customer Journey Analyticsのオーディエンスが **Real-time Customer Platform でアクティブに使用されている** かどうかを確認します。 または（理想的に） Customer Journey Analyticsで作成されたオーディエンスを使用するExperience Platform アプリケーション。

[ オーディエンス表示 ](/help/technotes/access-control.md#user-level-access) アクセス権がある場合は、オーディエンスを表示できます。 [ オーディエンスの作成 ](/help/technotes/access-control.md#user-level-access) アクセス権を持っている場合は、オーディエンスを編集および削除できます。

## オーディエンス リストでオーディエンスを表示

オーディエンス リスト➊には、既存のオーディエンスが表示されます。

![Audiences マネージャー ](assets/audiences-manager.png)

オーディエンスリストを表示するには：

1. Customer Journey Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL オーディエンス]** を選択します。

1. （オプション） ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を設定します。

1. （任意） ![ 検索 ](/help/assets/icons/Search.svg) を使用してオーディエンスを検索します。

   各オーディエンスに関する情報では、次の列を使用できます。

   | 列 | 説明 |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | 1 つ以上のオーディエンスを選択すると、オーディエンス インターフェイスの下部に青いアクションバーが表示されます。 詳しくは、[ アクション ](#actions) を参照してください。 |
   | **[!UICONTROL タイトルと説明]** | オーディエンスの作成時に入力したタイトルと説明。 |
   | **[!UICONTROL データビュー]** | このオーディエンスが作成されたデータビュー。 |
   | **[!UICONTROL オーディエンスサイズ]** | このオーディエンスのユーザーの合計数。 |
   | **[!UICONTROL 所有者]** | オーディエンスの所有者 – オーディエンスを作成したユーザー。 |
   | **[!UICONTROL 更新頻度]** | オーディエンスの作成時に設定された更新間隔。 |
   | **[!UICONTROL タグ]** | このオーディエンスに適用されるタグ。 |
   | **[!UICONTROL 公開ステータス]** | ![StatusGreen](/help/assets/icons/StatusGreen.svg)**[!UICONTROL 準備完了]**、![StatusGray](/help/assets/icons/StatusGray.svg)**[!UICONTROL 処理中]**、または ![StatusRed](/help/assets/icons/StatusRed.svg)**[!UICONTROL エラー]** を表示できます。 |
   | **[!UICONTROL 前回の更新]** | オーディエンスが最後に更新された際のタイムスタンプ。 |
   | **[!UICONTROL 最終変更日]** | オーディエンスが最後に編集または変更された際のタイムスタンプ。 |

## オーディエンスを編集

オーディエンスの設定はいつでも編集できます。 オーディエンス（1 回限りのオーディエンスまたは繰り返しオーディエンス）を編集する場合は、再公開が必要です。

オーディエンスを編集するには：

1. Customer Journey Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL オーディエンス]** を選択します。

   オーディエンス ページが表示されます。

1. 編集するオーディエンスのタイトルを選択します。

   **[!UICONTROL オーディエンスを編集]** ダイアログが表示されます。

1. オーディエンスに使用可能な任意のフィールドを更新できます。 更新できるフィールドについては、記事 [ オーディエンスの作成と公開 ](/help/components/audiences/publish.md#audience-builder) の「[ オーディエンスビルダー ](/help/components/audiences/publish.md) を参照してください。

1. 「**[!UICONTROL 再公開]**」を選択します。

## アクション

スケジュール済みプロジェクトマネージャーで一般的なアクションは次のとおりです。 コンテキストメニューからアクションを選択できます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![ラベル](/help/assets/icons/Labels.svg) | **[!UICONTROL タグ]** | 選択したオーディエンスにタグ付け。 **[!UICONTROL タグを更新：*オーディエンス名&#x200B;*]**ダイアログで、ドロップダウンメニューからタグを選択するか、1 つ以上の新しいタグを入力します。 「**[!UICONTROL 保存&#x200B;]**」を選択して保存します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択したオーディエンスを削除します。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | 選択したオーディエンスの名前を変更します。 **[!UICONTROL 名前を変更：*オーディエンス名&#x200B;*]**ダイアログを使用してオーディエンスの名前を変更し、「**[!UICONTROL 保存&#x200B;]**を選択して保存します。 |

1 つ以上のスケジュールされたプロジェクトを選択する際に、青いアクションバーから次のアクションを使用できます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![閉じる](/help/assets/icons/Close.svg) | **[!UICONTROL *x *個選択済み]** | 「」を選択すると、選択したオーディエンスの選択を解除できます。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択したオーディエンスを削除します。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV に書き出し]** | 選択したオーディエンスを `audiences.csv` という名前のファイルに書き出します。 |

## オーディエンスリストのフィルタリング

フィルターパネル ➋を使用して、[ オーディエンス ](#audiences-list) リストをフィルタリングできます。 フィルターパネルを表示または非表示にするには、![ フィルター ](/help/assets/icons/Filter.svg) を使用します。

![Audiences マネージャー ](assets/audiences-manager.png)

フィルターパネルは、次のセクションで構成されます。

### データビュー

| データビュー | 説明 |
|---|---|
| ![ 所有者 ](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | 「**[!UICONTROL データ表示]**」セクションでは、データ表示をフィルタリングできます。 <ul><li>![ 検索 ](/help/assets/icons/Search.svg) を使用して、フィルタリングに使用するデータビューを検索します。</li><li>複数のデータビューを選択できます。</li></ul> |

### 所有者

| 所有者 | 説明 |
|---|---|
| ![ 所有者 ](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | **[!UICONTROL 所有者]** セクションでは、所有者をフィルタリングできます。 <ul><li>![ 検索 ](/help/assets/icons/Search.svg) を使用して、フィルタリングに使用する所有者を検索します。</li><li>複数の所有者を選択できます。 </li></ul> |

## 更新頻度

| 更新頻度 | 説明 |
|---|---|
| ![更新頻度](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | 「**[!UICONTROL 更新頻度]**」セクションでは、更新頻度に基づいてフィルタリングできます。 <ul><li>![ 検索 ](/help/assets/icons/Search.svg) を使用して、フィルタリングに使用する更新頻度を検索します。</li><li>[ オーディエンスリスト ](#audiences-list) でオーディエンスに対して定義された更新頻度のみ <br/> 使用可能なオプションとして表示されます。</li></ul> |


### タグ

| タグ | 説明 |
|---|---|
| ![タグ](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | 「**[!UICONTROL タグ]**」セクションでは、タグに対してフィルターを適用できます。 <ul><li>![ 検索 ](/help/assets/icons/Search.svg) を使用して、フィルタリングに使用するタグを検索します。 |
