---
title: Report Builderでのデータブロックの管理
description: Report Builderでデータブロックを管理する方法について説明します。
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
TQID: https://experienceleague.adobe.com/75yD-0nmVz22sHzBOga0oH9AaSiKsaG282k5kf3R4og
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 18%

---

# データブロックの管理

[!UICONTROL &#x200B; データブロックマネージャー]を使用して、ブック内のすべてのデータブロックを表示および管理できます。 [!UICONTROL &#x200B; データブロックマネージャー]には、特定のデータブロックを検索できる検索、フィルター、並べ替え機能が用意されています。 1 つまたは複数のデータブロックを選択した後、選択したデータブロックを編集、削除、または更新できます。

## データブロックを表示

ブック内のすべてのデータブロックをリストするテーブルを表示するには、![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**&#x200B;を選択します。

![すべてのデータブロックのリストを表示する管理オプション。](./assets/image53.png){zoomable="yes"}

**[!UICONTROL データブロックマネージャー]**&#x200B;には、ワークブック内に存在するすべてのデータブロックを含むテーブルが表示されます。

![&#x200B; ブック内に存在するすべてのデータブロックのリスト。](./assets/image52.png){zoomable="yes"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)を使用して、表示する列を選択できます。

## データブロックの並べ替え

表示されている列でデータブロックテーブルをソートできます。 例えば、データビュー、セグメント、日付範囲などの変数ごとにデータブロックを並べ替えることができます。

データブロックテーブルを並べ替えるには、列見出しを選択します。 同じ列見出しを選択して、並べ替え順序を反転します。


## データブロックを検索

![検索](/help/assets/icons/Search.svg) **[!UICONTROL _検索_]** フィールドを使用して、データブロックテーブル内の任意の項目を検索します。 例えば、データブロックやデータビューに含まれる指標を検索できます。 また、日付範囲、変更日または最終実行日の列に表示される日付を検索することもできます。


## データブロックを編集

データブロックのデータビューと日付範囲を編集できます。 データブロックに適用されたセグメントがあります。

例えば、既存のセグメントを1つ以上のデータブロック内の新しいセグメントに置き換えることができます。

1. 更新するデータブロックを選択します。 最上位のチェックボックスを選択してすべてのデータブロックを選択するか、個々のデータブロックを選択できます。

   ![鉛筆の編集アイコン &#x200B;](./assets/image56.png){zoomable="yes"}

1. ![編集](/help/assets/icons/Edit.svg)を選択して、**[!UICONTROL クイック編集]** ウィンドウを表示します。

   ![&#x200B; クイック編集ウィンドウ &#x200B;](./assets/image58.png){zoomable="yes"}

1. データビュー、日付範囲、またはセグメントを更新するリンクを選択します。 **[!UICONTROL クイック編集]** - **[!UICONTROL セグメント]**&#x200B;では、選択したデータブロックのセグメントを追加、削除、または更新できます。

   ![&#x200B; クイック編集ウィンドウの「セグメントを追加」フィールド &#x200B;](./assets/image59.png){zoomable="yes"}

## データブロックを更新

「![更新](/help/assets/icons/Refresh.svg)」を選択して、データブロックテーブルを更新します。

データブロックが更新されているかどうかを確認するには、更新ステータスアイコンを表示します。

- データ ブロックが正常に更新されると、![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)が表示されます。

- 更新に失敗したデータブロックには、![AlertRed](/help/assets/icons/AlertRed.svg)が表示されます。


## データブロックを削除

1つ以上のデータブロックを削除するには：

1. 1つ以上のデータブロックを選択します。
1. 「![削除](/help/assets/icons/Delete.svg)」を選択します。
1. **[!UICONTROL データブロックを削除]** ダイアログで&#x200B;**[!UICONTROL 削除]**&#x200B;を選択するか、**[!UICONTROL キャンセル]**&#x200B;を選択して削除をキャンセルします。

## データブロックをグループ化

データブロックは、**[!UICONTROL 別にグループ化]** ドロップダウンメニューを使用してグループ化するか、列タイトルを選択できます。

列ごとにデータブロックを並べ替えるには、列タイトルを選択します。 データブロックをグループ別にグループ化するには、**[!UICONTROL グループ化の条件]**&#x200B;ドロップダウンメニューからグループ名を選択します。 例えば、以下のスクリーンショットは、データビュー別にグループ化されたデータブロックを示しています。

グループ化を使用すると、セグメントなどの共通エレメントを変更するデータブロックをすばやく選択できます。

![&#x200B; シート別グループ リストを表示するデータ ブロック マネージャー。](./assets/group-data-blocks.png){zoomable="yes"}

