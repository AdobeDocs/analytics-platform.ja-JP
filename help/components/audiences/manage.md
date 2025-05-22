---
title: Adobe Customer Journey Analytics で作成したオーディエンスの管理方法について説明します
description: Customer Journey Analytics でのオーディエンスの管理方法を学ぶ
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 95%

---

# オーディエンスの管理

Adobe Customer Journey Analytics でオーディエンスを管理するには、**[!UICONTROL コンポーネント]**／**[!UICONTROL オーディエンス]**&#x200B;を使用します。

## Audience management タスクについて

以前に作成したオーディエンスを管理すると、次のことを行えます。

* オーディエンスの自動更新／アップデートを&#x200B;**スケジュール設定またはスケジュール解除**&#x200B;できます。スケジュールの最大有効期限は 1 年です。
* 有効期限が近づいたら&#x200B;**オーディエンスの更新スケジュールを更新**&#x200B;します。有効期限が近づいたオーディエンスは、予定レポートの有効期限が近づいた場合と同様に扱われます。管理者は、スケジュールの期限が切れる 1 か月前にメールを受け取ります。
* **更新間隔**&#x200B;と&#x200B;**オーディエンスが最後に更新された時間**&#x200B;を表示します。
* **オーディエンスの作成に要した時間**&#x200B;に関するインサイトを Adobe Customer Journey Analytics から取得します。さらに、オーディエンスがアクティベーション目的で Real-time Customer Platform に表示されるまでに要した時間。
* Adobe Customer Journey Analytics のオーディエンスが **Real-time Customer Platform でアクティブに使用されている**&#x200B;かどうかを確認します。または（理想的には）Adobe Customer Journey Analytics で作成されたオーディエンスを使用する任意の Experience Platform アプリケーション。

[オーディエンス表示](/help/technotes/access-control.md#user-level-access)のアクセス権がある場合は、オーディエンスを表示できます。[オーディエンス作成](/help/technotes/access-control.md#user-level-access)のアクセス権がある場合は、オーディエンスを編集および削除できます。

## オーディエンスリストでのオーディエンスの表示

オーディエンス リスト ➊ には、既存のオーディエンスが表示されます。

![Audience Manager](assets/audiences-manager.png)

オーディエンスリストを表示するには：

1. Customer Journey Analytics で、**[!UICONTROL コンポーネント]**／**[!UICONTROL オーディエンス]**&#x200B;を選択します。

1. （オプション）![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用すると、表示する列を設定できます。

1. （オプション）![検索](/help/assets/icons/Search.svg) を使用して、オーディエンスを検索します。

   各オーディエンスに関する情報では、次の列を使用できます。

   | 列 | 説明 |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | 1 つ以上のオーディエンスを選択すると、オーディエンスインターフェイスの下部に青いアクションバーが表示されます。詳しくは、[アクション](#actions)を参照してください。 |
   | **[!UICONTROL タイトルと説明]** | オーディエンスの作成時に入力したタイトルと説明。 |
   | **[!UICONTROL データビュー]** | このオーディエンスが作成されたデータビュー。 |
   | **[!UICONTROL オーディエンスサイズ]** | このオーディエンスのユーザーの合計数。 |
   | **[!UICONTROL 所有者]** | オーディエンスの所有者 - オーディエンスを作成した人。 |
   | **[!UICONTROL 更新頻度]** | オーディエンスの作成時に設定された更新間隔。 |
   | **[!UICONTROL タグ]** | このオーディエンスに適用されるタグ。 |
   | **[!UICONTROL 公開ステータス]** | ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 準備完了]**、![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 処理中]**、![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL エラー]** のいずれかを表示できます。 |
   | **[!UICONTROL 前回の更新]** | オーディエンスが前回更新された日時のタイムスタンプ。 |
   | **[!UICONTROL 最終変更日]** | オーディエンスが前回編集または変更された日時のタイムスタンプ。 |

## オーディエンスの編集

オーディエンスの設定はいつでも編集できます。オーディエンス（1 回限りのオーディエンスまたは繰り返しオーディエンス）を編集する際は、再公開が必須です。

オーディエンスを編集するには：

1. Customer Journey Analytics で、**[!UICONTROL コンポーネント]**／**[!UICONTROL オーディエンス]**&#x200B;を選択します。

   オーディエンスページが表示されます。

1. 編集するオーディエンスのタイトルを選択します。

   **[!UICONTROL オーディエンスを編集]**&#x200B;ダイアログが表示されます。

1. オーディエンスの使用可能なフィールドを更新できます。更新できるフィールドについて詳しくは、[オーディエンスの作成と公開](/help/components/audiences/publish.md)の記事の[オーディエンスビルダー](/help/components/audiences/publish.md#audience-builder)を参照してください。

1. 「**[!UICONTROL 再公開]**」を選択します。

## アクション

スケジュール済みプロジェクトマネージャーでの一般的な操作は次のとおりです。コンテキストメニューからアクションを選択できます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![ラベル](/help/assets/icons/Labels.svg) | **[!UICONTROL タグ]** | 選択したオーディエンスにタグを付けます。**[!UICONTROL タグを更新：*オーディエンス名&#x200B;*]**&#x200B;ダイアログで、ドロップダウンメニューからタグを選択するか、1 つ以上の新しいタグを入力します。 「**[!UICONTROL 保存&#x200B;]**」を選択して保存します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択したオーディエンスを削除します。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | 選択したオーディエンスの名前を変更します。**[!UICONTROL 名前を変更：*オーディエンス名&#x200B;*]**&#x200B;ダイアログを使用してオーディエンスの名前を変更して、「**[!UICONTROL 保存&#x200B;]**」を選択して保存します。 |

スケジュールされたプロジェクトを 1 つ以上選択すると、青色のアクションバーから次のアクションを実行できます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![閉じる](/help/assets/icons/Close.svg) | **[!UICONTROL *x *個を選択済み]** | 選択して、選択したオーディエンスを選択解除します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択したオーディエンスを削除します。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV に書き出し]** | 選択したオーディエンスを、`audiences.csv` という名前のファイルに書き出します。 |

## オーディエンスリストのフィルタリング

フィルターパネル ➋ ールを使用して、[ オーディエンス ](#audiences-list) リストをフィルタリングできます。 フィルターパネルを表示または非表示にするには、![フィルター](/help/assets/icons/Filter.svg) を使用します。

![Audience Manager](assets/audiences-manager.png)

フィルターパネルは、次のセクションで構成されています。

### データビュー

| データビュー | 説明 |
|---|---|
| ![所有者](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | 「**[!UICONTROL データビュー]**」セクションでは、データビューでフィルタリングできます。 <ul><li>フィルタリングに使用するデータビューを検索するには、![検索](/help/assets/icons/Search.svg) を使用します。</li><li>複数のデータビューを選択できます。</li></ul> |

### 所有者

| 所有者 | 説明 |
|---|---|
| ![所有者](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | 「**[!UICONTROL 所有者]**」セクションでは、所有者でフィルタリングできます。 <ul><li>フィルタリングに使用する所有者を検索するには、![検索](/help/assets/icons/Search.svg) を使用します。</li><li>複数の所有者を選択できます。 </li></ul> |

## 更新頻度

| 更新頻度 | 説明 |
|---|---|
| ![更新頻度](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | 「**[!UICONTROL 更新頻度]**」セクションでは、更新頻度でフィルタリングできます。 <ul><li>フィルタリングに使用する更新頻度を検索するには、![検索](/help/assets/icons/Search.svg) を使用します。</li><li>[オーディエンスリスト](#audiences-list)内のオーディエンス<br/>に対して定義された更新頻度のみが、使用可能なオプションとして表示されます。</li></ul> |


### タグ

| タグ | 説明 |
|---|---|
| ![タグ](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | 「**[!UICONTROL タグ]**」セクションでは、タグでフィルタリングできます。 <ul><li>フィルタリングに使用するタグを検索するには、![検索](/help/assets/icons/Search.svg) を使用します。 |
