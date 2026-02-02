---
title: Report Builder ハブ
description: Report Builder ハブについて説明します。
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
source-git-commit: 1e19e0c79617d27c7039b695c70ca5026fcaf357
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 25%

---

# Report Builder ハブ

Report Builder ハブは、Excel のリボン バーから ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** を選択すると、Excel ブック内に表示される右側のウィンドウです。

Report Builder ハブを使用して、データブロックの作成、更新、管理を行います。

Report Builder ハブには、![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Create]**、![TableManage](/help/assets/icons/TableManage.svg)**[!UICONTROL Manage]**、![Calendar](/help/assets/icons/Calendar.svg)**[!UICONTROL Schedule]** ボタン、**[!UICONTROL Commands]** パネル、**[!UICONTROL Quick Edit]** パネルが含まれています。

![Report Builder ハブ &#x200B;](assets/hub51.png){zoomable="yes"}


選択

* ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Create]** して [&#x200B; 新しいデータブロックを作成 &#x200B;](create-a-data-block.md) します。
* ![TableManage](/help/assets/icons/TableManage.svg)**[!UICONTROL Manage]** 既存のデータブロックを [&#x200B; 管理 &#x200B;](manage-reportbuilder.md) します。
* ![&#x200B; カレンダー &#x200B;](/help/assets/icons/Calendar.svg) **[!UICONTROL スケジュール]**&#x200B;[&#x200B; ワークブックをメールで送信するスケジュールを管理 &#x200B;](schedule-reportbuilder.md) します。

## コマンドパネル

**[!UICONTROL コマンド]** パネルを使用して、選択したセルまたは以前のアクションと互換性のあるコマンドにアクセスします。

| コマンド | 使用条件... | 目的 |
|------|------------------|--------|
| ![&#x200B; 編集 &#x200B;](/help/assets/icons/Edit.svg)**[!UICONTROL データブロックを編集]** | 選択したセル範囲が、1 つのデータブロックのみの一部である。 | データブロックの編集に使用します。 |
| ![&#x200B; 更新 &#x200B;](/help/assets/icons/Refresh.svg) **[!UICONTROL データブロックを更新]** | 選択範囲に少なくとも 1 つのデータブロックが含まれている。コマンドは、選択範囲内のデータブロックのみを更新します。 | を使用して、1 つ以上のデータブロックを更新します。 |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg)**[!UICONTROL すべてのデータブロックを更新]** | ワークブックには、1 つ以上のデータブロックが含まれています。 | ワークブック内のすべてのデータブロックを更新するために使用します |
| ![&#x200B; ワークブックを送信 &#x200B;](/help/assets/icons/Send.svg)**[!UICONTROL 送信]** | ワークブックには、1 つ以上のデータブロックが含まれています。 | を使用して [&#x200B; ワークブックをファイルとして電子メールで送信 &#x200B;](schedule-reportbuilder.md) します。 |
| ![&#x200B; コピー &#x200B;](/help/assets/icons/Copy.svg)**[!UICONTROL データブロックをコピー]** | 選択したセルまたはセル範囲は、1 つ以上のデータブロックの一部です。 | データブロックのコピーに使用します。 |
| ![&#x200B; 切り取り &#x200B;](/help/assets/icons/Cut.svg)**[!UICONTROL データブロックを切り取り]** | 選択したセルまたはセル範囲は、1 つ以上のデータブロックの一部です。 | データブロックの切り取りに使用します。 |
| ![&#x200B; 削除 &#x200B;](/help/assets/icons/Delete.svg)**[!UICONTROL データブロックを削除]** | 選択したセル範囲が、1 つのデータブロックのみの一部である。 | データブロックの削除に使用 |

## クイック編集パネル

スプレッドシートで 1 つ以上のデータブロックを選択すると、Report Builderに **[!UICONTROL クイック編集]** パネルが表示されます。 **[!UICONTROL クイック編集]** パネルを使用して、1 つ以上のデータブロックのパラメーターを同時に変更できます。

「**[!UICONTROL クイック編集]**」セクションを使用して行った変更は、選択したすべてのデータブロックに適用されます。

### データビュー

データブロックは、選択したデータビューからデータを取り込みます。 ワークシートで複数のデータブロックが選択されていて、それらが同じデータビューからデータを取り込まない場合、「**データビュー**」リンクに「**[!UICONTROL _複数_]**」と表示されます。

データビューを変更すると、選択範囲内のすべてのデータブロックに新しいデータビューが採用されます。データブロック内のコンポーネントは、ID に基づいて新しいデータビューと照合されます。 コンポーネントがデータブロック内に見つからない場合、そのコンポーネントは削除され、**[!UICONTROL 無効な値]** または特定のコンポーネントに対して ![AlertRed](/help/assets/icons/AlertRed.svg) が表示されます。

データビューを変更するには、**[!UICONTROL データビュー]** ドロップダウンメニューから新しいデータビューを選択します。


### 日付範囲

**日付範囲**&#x200B;は、選択したデータブロックの日付範囲を表示します。複数の日付範囲を持つ複数のデータブロックが選択されている場合、「**[!UICONTROL 日付範囲]**」リンクに「**[!UICONTROL _複数_]**」と表示されます。

### セグメント

**セグメント** リンクには、選択したデータブロックで使用されているセグメントの概要リストが表示されます。 複数のセグメントが適用された状態で複数のデータブロックが選択されている場合、「**セグメント**」リンクに **[!UICONTROL _複数_]** と表示されます。

>[!MORELIKETHIS]
>
>[&#x200B; データビューの選択 &#x200B;](select-data-view.md)
>[日付範囲を選択 &#x200B;](select-date-range.md)
>[フィルターの操作 &#x200B;](work-with-filters.md)
>
