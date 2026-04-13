---
description: Analysis Workspaceのリアルタイムレポートの使用方法を説明します。
title: リアルタイムのレポートを利用して
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: 0e5a64e78e5a471f8b7c9fc32fdbae2b2e70230a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 12%

---

# リアルタイムレポートの使用 {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="リアルタイム更新"
>abstract="このパネルのデータとビジュアライゼーションのリアルタイム更新を有効にします。"

リアルタイムレポートを使用するには、Workspace プロジェクトの次のいずれかのパネルで&#x200B;**[!UICONTROL リアルタイム更新]**&#x200B;切り替えスイッチを有効にします。

* [空のパネル](/help/analysis-workspace/c-panels/blank-panel.md)
* [フリーフォーム](/help/analysis-workspace/c-panels/freeform-panel.md)
* [アトリビューション](/help/analysis-workspace/c-panels/attribution.md)
* [次または前の項目](/help/analysis-workspace/c-panels/next-previous.md)

データの最新の更新のタイムスタンプを含むメッセージが表示されます。 例：[!UICONTROL  *最終更新日：07:55 pm*]。

ドロップダウンメニューからレポートするリアルタイム期間を選択します。 利用可能なオプションは次のとおりです。

* [!UICONTROL 最後15分]
* [!UICONTROL 過去30分]
* [!UICONTROL 過去1時間]
* [!UICONTROL 過去8時間]
* [!UICONTROL 過去24時間]

パネル内のすべてのビジュアライゼーションは、リアルタイム更新が有効になっているパネルを含むブラウザータブがアクティブになっている間、最大30分間毎分更新されるようになりました。

例として、時間が&#x200B;**[!UICONTROL 06]**&#x200B;から&#x200B;**[!UICONTROL 06]**&#x200B;午後&#x200B;**[!UICONTROL に移動すると、]**&#x200B;総収益/時間&#x200B;**[!UICONTROL *の可視化と:26pm*]**&#x200B;総収益/時間&#x200B;**[!UICONTROL *のフリーフォームテーブルを更新する:27 リアルタイムレポートパネル&#x200B;*]**のスナップショットを以下に示します。

![ リアルタイム更新](assets/real-time-refresh.gif)

30分後、またはブラウザータブが非アクティブになるとすぐに、**[!UICONTROL リアルタイム更新]**&#x200B;切り替えが自動的に無効になり、リアルタイム更新が停止されます。

リアルタイム更新トグルを無効にすると、パネル（および内のすべてのビジュアライゼーション）が[に戻り、Customer Journey Analyticsの標準レポートデータと機能を使用します](real-time.md#how-it-works)。
