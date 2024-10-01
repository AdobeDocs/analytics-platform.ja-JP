---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: 指標
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 25%

---

# スケジュールされたプロジェクト

スケジュールされたAnalysis Workspace プロジェクトは、**[!UICONTROL コンポーネント]**/**[!UICONTROL スケジュールされたプロジェクト]** を使用してCustomer Journey Analyticsで管理できます。

スケジュ **[!UICONTROL ルされたプロジェクト]** では、繰り返しプロジェクトスケジュールを編集および削除できます。 ![ 検索 ](/help/assets/icons/Search.svg) 検索フィールドを使用してスケジュールを検索します。 または、左側のパネルの ![ フィルター ](/help/assets/icons/Filter.svg) フィルターオプションを使用します。 **[!UICONTROL タグ]**、**[!UICONTROL 所有者]**、**[!UICONTROL その他のフィルター]** でフィルタリングできます。

「スケジュール済みプロジェクト」リストには、次の列が表示されます。

| フィールド | 説明 |
| --- | --- |
| ![ 星 ](/help/assets/icons/Star.svg) | 「![ 星 ](/help/assets/icons/Star.svg)」を選択すると、このスケジュールがお気に入りになります。 |
| **[!UICONTROL スケジュール ID]** | 主にデバッグ目的で使用される ID。 |
| [!UICONTROL 名前] | このプロジェクトの名前。<br/>![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、スケジュールされたプロジェクトの詳細が表示されます。<br/> 詳細 ![ を選択して ](/help/assets/icons/More.svg) コンテキストメニューを開きます。 このメニューから、次の操作を実行できます。<ul><li>![ 削除 ](/help/assets/icons/Delete.svg)**[!UICONTROL 削除]** スケジュールされたプロジェクト。</li><li>![ ラベル ](/help/assets/icons/Labels.svg)**[!UICONTROL タグ付け]** スケジュールされたプロジェクト。</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)**[!UICONTROL Approve]** スケジュールされたプロジェクト。</li><li>![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL Export CSV]**：スケジュールされたプロジェクトを CSV ファイルに書き出します。</li></ul> |
| **[!UICONTROL 所有者]** | プロジェクトを作成し所有しているユーザー。 |
| **[!UICONTROL タグ]** | （任意）タグ付けは、プロジェクトを整理するのに適した方法です。すべてのユーザーがタグを作成し、1 つ以上のタグをプロジェクトに適用できます。ただし、タグを表示できるのは、自分が所有しているプロジェクトか、自分と共有されているプロジェクトに限られます。 |
| **[!UICONTROL 配信先]** | スケジュールされたプロジェクトの受信者。 |
| **[!UICONTROL 有効期限]** | スケジュールの頻度に関係なく、有効期限を最大 1 年まで設定できます。 |
| **[!UICONTROL 頻度]** | このスケジュールプロジェクトを 1 人または複数の受信者に送信する頻度。 |
| **[!UICONTROL 実行時間]** | このスケジュールされたプロジェクトが送信される時刻。 |
| **[!UICONTROL クエリ数]** | このプロジェクトに対するクエリの数。 |
| **[!UICONTROL 最長の日付範囲]** | スケジュールされたプロジェクトに定義されている最長の日付範囲。 この値は、パフォーマンスの問題の調査に関連する可能性があります。 詳しくは、[ レポートアクティビティマネージャー ](/help/reporting-activity-manager/reporting-activity-overview.md) を参照してください。 |
| **[!UICONTROL クエリ数]** | スケジュールされたプロジェクトで実行されたクエリの数。 この値は、パフォーマンスの問題の調査に関連する可能性があります。 詳しくは、[ レポートアクティビティマネージャー ](/help/reporting-activity-manager/reporting-activity-overview.md) を参照してください。 |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を構成できます。

スケジュールされたプロジェクトには、特定のユーザーが作成した項目が表示されます。 アプリケーションでユーザーアカウントが無効になっている場合、スケジュールされたすべての配信が停止します。



## アクション

スケジュール済みプロジェクトマネージャーで一般的なアクションは次のとおりです。 コンテキストメニューから、または複数のスケジュールされたプロジェクトを選択する際の青いアクションバーから、アクションを選択できます。

| アクション | 説明 |
|---|---|
| **[!UICONTROL 承認]** | スケジュールされたプロジェクトを承認します。 |
| **[!UICONTROL 編集]** | スケジュールのタイトルをクリックして、配信設定を更新します。 |
| **[!UICONTROL 削除]** | プロジェクトに対して選択したスケジュールを削除します。プロジェクト自体は削除されません。 |
| **[!UICONTROL タグ]** | スケジュールされたプロジェクトにタグを付けて、プロジェクトを見つけやすくします。 |

![ フィルター ](/help/assets/icons/Filter.svg) フィルターを使用すると、次の操作も実行できます。

| アクション | 説明 |
|---|---|
| **[!UICONTROL 失敗スケジュールを表示]** | **[!UICONTROL その他のフィルター]** に移動し、「**[!UICONTROL 失敗]** を選択して、失敗したスケジュールを表示します。 |
| **[!UICONTROL 期限切れスケジュールを表示]** | **[!UICONTROL その他のフィルター]** に移動し、「**[!UICONTROL 期限切れ]**」を選択して、期限切れのスケジュールを表示します。 スケジュールのタイトルをクリックして、新しい配信スケジュールを設定します。 |

