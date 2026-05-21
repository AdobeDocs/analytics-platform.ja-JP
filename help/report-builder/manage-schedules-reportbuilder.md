---
title: Report Builderでのスケジュールされたワークブックの管理
description: Report Builderでスケジュールされたワークブックを管理する方法について説明します。
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 0a0427d9-223e-410b-a8ef-8601390d88aa
TQID: https://experienceleague.adobe.com/HcKyD-v3I1hsxWwiDZJwgvO9pH9ifBVOjBapARdYQVQ
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 6%

---

# スケジュールされたワークブックの管理

次の記事の説明に従って、電子メールまたはクラウド宛先への書き出しを通じて共有するワークブックをスケジュールできます。

* [電子メールを通じて共有してワークブックをスケジュールする](/help/report-builder/schedule-reportbuilder.md)

* [クラウド宛先への書き出し用ワークブックのスケジュール](/help/report-builder/report-builder-export.md)

次の節では、ワークブックをスケジュール後に管理する方法について説明します。

## スケジュールされたワークブックの表示と管理

スケジュールされたすべてのワークブックは、**[!UICONTROL ワークブック]** タブで表示および管理できます。

1. Report Builder ハブで「**[!UICONTROL スケジュール]**」を選択します

1. 「**[!UICONTROL ワークブック]**」タブを選択します。 スケジュールされたすべてのワークブックのリストが表示されます。 （または、「**[!UICONTROL レガシー]**」タブを選択して、新しいレポートビルダーに移行する必要があるレガシーワークブックのリストを表示することもできます）。

   ![ スケジュール済みワークブック ](assets/scheduled-workbooks.png){zoomable="yes"}

1. 次のいずれかの操作を行います。

   * アイコンにカーソルを合わせると、スケジュールされたワークブックのステータスが表示されます。

   * 検索フィールド ![検索](/help/assets/icons/Search.svg)で、特定のスケジュール済みワークブックを検索します。

   * 列アイコン ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)を選択して、表示する列を定義します。

   * フィルターアイコン ![ フィルターアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)を選択し、[!UICONTROL **すべてを表示**]&#x200B;を選択して、特定の組織のすべてのスケジュール済みワークブックを表示します。

1. 1つ以上のワークブックを選択します。

   ![選択したワークブックのスケジュール ](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   次のオプションがあります。

   | オプション | 説明 |
   |---|---|
   | ![編集](/help/assets/icons/Edit.svg) | 選択したワークブックのスケジュールを編集します。 |
   | ![履歴](/help/assets/icons/History.svg) | 選択したワークブックの履歴を表示します。 |
   | ![一時停止](/help/assets/icons/Pause.svg) | 選択したワークブックのスケジュールを一時停止します。 |
   | ![ プレイ ](/help/assets/icons/Play.svg) | 選択したワークブックのスケジュールを再開します。 |
   | ![ダウンロード](/help/assets/icons/Download.svg) | 選択したワークブックを新しいワークブックにダウンロードします。 |
   | ![削除](/help/assets/icons/Delete.svg) | 選択したワークブックのスケジュールを削除します。 |


## スケジュールされたワークブックの履歴とステータス

スケジュールされたワークブックの履歴とステータスは、**[!UICONTROL 履歴]** タブで確認できます。

1. Report Builder ハブで「**[!UICONTROL スケジュール]**」を選択します。

1. 「**[!UICONTROL 履歴]**」タブを選択します。 スケジュールされたすべてのワークブックのリストが表示されます。

   ![ スケジュール履歴](assets/scheduled-workbooks-history.png){zoomable="yes"}

   リスト内の特定のワークブックを検索するには、![検索](/help/assets/icons/Search.svg)を使用します。
![ColumnSetting](/help/assets/icons/ColumnSetting.svg)を使用して、表示する列を定義します。

   「**[!UICONTROL 履歴]**」タブでは、スケジュールされた各タスクのステータスを確認できます。 スケジュールされた各タスクのステータスの変更を、別の行に文書化します。

   * ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)は、ワークブックが正常に送信されたことを示します。
   * ![AlertRed](/help/assets/icons/AlertRed.svg)は、エラーが発生したことを示します。

または、「**[!UICONTROL ワークブック]**」タブで、選択した1つ以上のワークブックに対して「![履歴](/help/assets/icons/History.svg)」を選択することもできます。 このアクションは、選択範囲でフィルタリングされたリストを含む「**[!UICONTROL 履歴]**」タブを表示します。 フィルターを削除するには、![CrossSize75](/help/assets/icons/CrossSize75.svg)を選択します。
