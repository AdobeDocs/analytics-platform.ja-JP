---
description: Analysis Workspaceでのリアルタイムレポートの使用方法を説明します。
title: リアルタイムレポートの使用
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="ベータ版"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: 82aefce30834d6400d338896dc1968e37596393e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 9%

---

# リアルタイムレポートの使用

{{release-limited-testing}}

リアルタイムレポートを使用するには、Workspace プロジェクトの次のパネルのいずれかを有効にする **[!UICONTROL リアルタイム更新]** を有効にします。



* [空のパネル](/help/analysis-workspace/c-panels/blank-panel.md)
* [フリーフォーム](/help/analysis-workspace/c-panels/freeform-panel.md)
* [アトリビューション](/help/analysis-workspace/c-panels/attribution.md)
* [次または前の項目](/help/analysis-workspace/c-panels/next-previous.md)
* [クイックインサイト](/help/analysis-workspace/c-panels/quickinsight.md)

データの最新の更新のタイムスタンプを含むメッセージが表示されます。 例：[!UICONTROL *最終更新午後 7 時 55 分*]。

レポートするリアルタイム期間をドロップダウンメニューから選択します。 利用可能なオプションは次のとおりです。

* [!UICONTROL &#x200B; 過去 15 分 &#x200B;]
* [!UICONTROL &#x200B; 過去 30 分 &#x200B;]
* [!UICONTROL &#x200B; 過去 1 時間 &#x200B;]
* [!UICONTROL &#x200B; 過去 8 時間 &#x200B;]
* [!UICONTROL &#x200B; 過去 24 時間 &#x200B;]

リアルタイム更新が有効になっているパネルを含むブラウザータブがアクティブになっている間、パネル内のすべてのビジュアライゼーションが最大 30 分間、1 分ごとに更新されるようになりました。

![ リアルタイム更新 ](assets/real-time-refresh.gif)

30 分後、またはブラウザータブが非アクティブになるとすぐに、「**[!UICONTROL リアルタイム更新]**」トグルが自動的に無効になり、リアルタイムの更新が停止します。
