---
title: 会話インサイト設定の管理
description: 会話インサイト設定を管理する方法について説明します。
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
autotag-review: '2026-10-02T07:03:36.851Z'
TQID: 'https://experienceleague.adobe.com/D2nrhtN2SaHoAw0PU7yJtabvx-q0L5FHtBFu1sORfaI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: d7a261eb-f9ac-4dd6-bd60-1637efcd3d36
    internal-label: Conversation Insights
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: ebc2d1d9992150683fb642862e0ea29b7f70ddb0
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 6%
---
# 設定の管理

[会話インサイト設定](/help/conversation-insights/configure.md)を作成した後、これらの設定を表示、編集、または削除できます。

会話インサイト設定を管理できるのはシステム管理者のみです。

会話インサイトについて詳しくは、[会話インサイトの概要](/help/conversation-insights/overview.md)を参照してください。


## 既存の設定の表示とフィルター

既存の会話インサイト設定を表示するには：

1. Customer Journey Analyticsで、**[!UICONTROL Data Management]** > **[!UICONTROL Conversation Insights configuration]**&#x200B;を選択します。

   ![会話インサイト設定の概要](assets/conversation-insights-configurations.png)

   各設定について、次の情報の列を使用できます。

   * **[!UICONTROL 名前]**：会話インサイト設定の名前。
   * **[!UICONTROL 作成者]**：設定を作成したユーザー。

   * **[!UICONTROL サンドボックス]**：接続に追加したプロファイルデータセットを含むExperience Platform サンドボックス。

   * **[!UICONTROL 接続]**：設定に追加した接続。

   * **[!UICONTROL 作成日]**：設定が作成された日時。

   * **[!UICONTROL 最終変更日]**：設定が最後に変更された日付。

   * **[!UICONTROL ステータス]**：設定のステータス。 使用可能な値：
     ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**、![StatusBlue](/help/assets/icons/StatusBlue.svg) **[!UICONTROL 保留中]**、または![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 失敗]**。

   テーブルに表示する列を設定するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg)を選択します。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログで、表示する列を選択します。 次に、**[!UICONTROL 適用]**&#x200B;を選択します。

1. （オプション）設定のリストをフィルタリングするには、![&#x200B; フィルター](/help/assets/icons/Filter.svg)を選択し、次のいずれかの条件でフィルタリングします。

   * **[!UICONTROL 接続]**

   * **[!UICONTROL 作成者]**

   * **[!UICONTROL サンドボックス]**

   * **[!UICONTROL ステータス]**

## 設定の作成

新しい会話インサイト設定を作成するには：

1. 「**[!UICONTROL 設定を作成]**」を選択します。
1. [**[!UICONTROL 設定を作成]**](./configure.md) ダイアログを使用して、会話インサイトを設定します。

## 設定の編集

既存の会話インサイト設定を編集するには：

1. 次のいずれかの操作を行います。

   * 編集する設定の名前を選択します。
   * 編集する設定の横にあるチェックボックスを選択し、青いアクションバーから![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**&#x200B;を選択します。
   * 編集する設定の![詳細](/help/assets/icons/More.svg)を選択します。 コンテキストメニューから、![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**&#x200B;を選択します。

1. 会話インサイトを管理するには、[**[!UICONTROL 設定/_設定の名前_]**](./configure.md) ダイアログを使用します。

## 設定の削除

既存の会話インサイト設定を削除するには：

1. 次のいずれかの操作を行います。

   * 削除する設定の横にあるチェックボックスを選択し、青いアクションバーから「![削除](/help/assets/icons/Delete.svg) **[!UICONTROL 削除]**」を選択します。
   * 編集する設定の![詳細](/help/assets/icons/More.svg)を選択します。 コンテキストメニューから、![削除](/help/assets/icons/Delete.svg) **[!UICONTROL 削除]**&#x200B;を選択します。

1. **[!UICONTROL 設定を削除]** ダイアログで、**[!UICONTROL 削除]**&#x200B;を選択して設定を削除します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。
