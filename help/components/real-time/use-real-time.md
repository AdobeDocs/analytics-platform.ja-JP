---
description: Analysis Workspaceでのリアルタイムレポートの使用方法を説明します。
title: リアルタイムレポートの使用
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: d8ff5191ea96b8871f6aaba1fc28211c22a13e0d
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 12%

---

# リアルタイムレポートの使用 {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="リアルタイム更新"
>abstract="このパネルのデータとビジュアライゼーションのリアルタイム更新を有効にします。"

{{release-limited-testing}}

リアルタイムレポートを使用するには、Workspace プロジェクトの次のパネルのいずれかを有効にする **[!UICONTROL リアルタイム更新]** を有効にします。

* [空のパネル](/help/analysis-workspace/c-panels/blank-panel.md)
* [フリーフォーム](/help/analysis-workspace/c-panels/freeform-panel.md)
* [アトリビューション](/help/analysis-workspace/c-panels/attribution.md)
* [次または前の項目](/help/analysis-workspace/c-panels/next-previous.md)

データの最新の更新のタイムスタンプを含むメッセージが表示されます。 例：[!UICONTROL *最終更新は午後 7 時 :55 です*]。

レポートするリアルタイム期間をドロップダウンメニューから選択します。 利用可能なオプションは次のとおりです。

* [!UICONTROL  過去 15 分 ]
* [!UICONTROL  過去 30 分 ]
* [!UICONTROL  過去 1 時間 ]
* [!UICONTROL  過去 8 時間 ]
* [!UICONTROL  過去 24 時間 ]

リアルタイム更新が有効になっているパネルを含むブラウザータブがアクティブになっている間、パネル内のすべてのビジュアライゼーションが最大 30 分間、1 分ごとに更新されるようになりました。

例として、時間が **[!UICONTROL 06]** から **[!UICONTROL 06]** pm **[!UICONTROL に移動するのに応じて]** 合計売上高/時間 **[!UICONTROL *バービジュアライゼーションおよび:26pm*]** 合計売上高/時間 **[!UICONTROL *フリーフォームテーブルを更新する :27 リアルタイムレポートパネル&#x200B;*]**のスナップショットを以下に示します。

![ リアルタイム更新 ](assets/real-time-refresh.gif)

30 分後、またはブラウザータブが非アクティブになるとすぐに、「**[!UICONTROL リアルタイム更新]**」トグルが自動的に無効になり、リアルタイムの更新が停止します。

「リアルタイム更新」切替スイッチが無効になると、パネル（および内のすべてのビジュアライゼーション）は [Customer Journey Analyticsの標準レポートデータと機能を使用 ](real-time.md#how-it-works) に戻ります。
