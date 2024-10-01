---
title: 日付範囲の概要
description: 日付範囲の詳細と、レポートでの使用方法について説明します。
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 21%

---

# 日付範囲の概要

Workspace プロジェクトでは、通常、パネル内の [ カレンダー ](/help/analysis-workspace/c-panels/panels.md#calendar) を使用して、そのパネルのビジュアライゼーションの日付範囲を指定します。

日付範囲コンポーネントを使用すると、パネルのカレンダー設定を定義および上書きできます。

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## 日付範囲の使用

日付範囲コンポーネントを使用して、パネルのカレンダーを再定義できます。

または、フリーフォームテーブルの日付範囲を指標またはディメンションとして使用できます。

![ 日付範囲の使用 ](/help/components/date-ranges/assets/date-ranges-usage.png)

- **指標**。 例えば、特定の指標について 2 つの異なる月のディメンションを比較する場合です。
- **Dimension**。 日付範囲ディメンションについて、様々なディメンション項目の指標を比較します。

>[!NOTE]
>
>フリーフォームテーブルで日付範囲を使用すると、そのフリーフォームテーブルが属するパネルに指定されたカレンダーが日付範囲によって上書きされます。
>

日付範囲は、（任意のコンポーネントを使用 [ と同様に使用し ](/help/components/overview.md#analysis-workspace-components) す。 ![ カレンダー ](/help/assets/icons/Calendar.svg) **[!UICONTROL 日付範囲]** コンポーネントパネルから日付範囲をドラッグして、コンポーネントを次の場所にドロップします。

- **[!UICONTROL カレンダー]**：現在のカレンダー設定を日付範囲で ![ 切り替え ](/help/assets/icons/Switch.svg) **[!UICONTROL 置換]** します。
- **指標列ヘッダー**：指標を ![ 切り替え ](/help/assets/icons/Switch.svg) **[!UICONTROL 置換]**、指標を ![ 追加 ](/help/assets/icons/Add.svg)**[!UICONTROL  追加 ]**、日付範囲を指標として、または指標を ![ フィルター ](/help/assets/icons/Filter.svg)**[!UICONTROL  フィルター ]**できます。
- **Dimension列ヘッダー**：現在のディメンションを ![ 切り替え ](/help/assets/icons/Switch.svg) **[!UICONTROL 置換]** します。 新しいディメンションは **[!UICONTROL 日付範囲]** になりました。 ディメンションが日付範囲になると、追加の日付範囲をディメンション項目として ![ 追加 ](/help/assets/icons/Add.svg)**[!UICONTROL  追加 ]**できます。
- **Dimension項目**：日付範囲ごとの特定のディメンション項目を ![ 分類 ](/help/assets/icons/Breakdown.svg) **[!UICONTROL 分類]** しました。

また、フリーフォームテーブルのビジュアライゼーションで、日付範囲列を直接追加することもできます。

1. 指標列で、コンテキストメニューから次の項目を選択します。

   - **[!UICONTROL 期間列を追加]**. 現在のカレンダーに基づいて候補として挙げられたオプションを選択することも、[ カスタムの日付範囲 ](#custom-date-ranges) を作成することもできます。
   - **[!UICONTROL 期間を比較]**. 現在のカレンダーに基づく候補オプションを選択するか、[ カスタムの日付範囲 ](#custom-date-ranges) を作成できます。

1. 選択した内容に応じて、追加の日付範囲列がフリーフォームテーブルに追加されます。

## デフォルトの日付範囲

Analysis Workspaceには、多数のデフォルトの日付範囲が用意されています。


| 日 | 週 | 月 | 四半期 | 年 |
|---|---|---|---|---|
| Today | 今週 | 今月 | 今四半期 | 今年 |
| 昨日 | 今週 (今日を除く) | 今月 (今日を除く) | 今四半期 (今日を除く) | 今年 (今日を除く) |
| 2 日前 | 2 週間前 | 2 か月前 |   |  |
| 3 日前 | 3 週間前 | 3 か月前 |  | |
| 過去 7 日間 | 先週 | 先月 | 前四半期 | 昨年 |
| 過去 14 日間 | 過去 2 週間 | 過去 2 ヶ月 | 過去 4 四半期 | |
| 過去 30 日間 | 過去 3 週間 | 過去 3 ヶ月間 | | |
| 過去 60 日間 | 過去 4 週間 | 過去 6 ヶ月 | | |
| 過去 90 日間 | 過去 12 週間 | 過去 12 ヶ月間 | | |
| 過去 7 日間 | 過去 52 週間 | 過去 13 ヶ月間 | | |
| 過去 14 日間 | | | | |
| 過去 30 日間 | | | | |
| 過去 90 日間 | | | | |

<table style="table-layout:fixed">

## カスタム日付範囲

独自のカスタム日付範囲を作成できます。 日付範囲の作成に使用できる様々なオプションについては、[ 日付範囲の作成 ](/help/components/date-ranges/create.md) を参照してください。 その後、[ 日付範囲ビルダー ](create.md#date-range-builder) で日付範囲を作成、変更および保存します。

日付範囲を管理するには、[ 日付範囲マネージャー ](manage.md) を使用します。
