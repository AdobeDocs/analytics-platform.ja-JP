---
description: Analysis Workspaceのリアルタイムレポートの使用方法を説明します。
title: リアルタイムのレポートを利用して
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d1779026-aeed-458e-a1c7-839d4acac922
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 239
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

データの最新の更新のタイムスタンプを含むメッセージが表示されます。 例：[!UICONTROL &#x200B; *最終更新日：07:55 pm*]。

ドロップダウンメニューからレポートするリアルタイム期間を選択します。 利用可能なオプションは次のとおりです。

* [!UICONTROL 最後15分]
* [!UICONTROL 過去30分]
* [!UICONTROL 過去1時間]
* [!UICONTROL 過去8時間]
* [!UICONTROL 過去24時間]

パネル内のすべてのビジュアライゼーションは、リアルタイム更新が有効になっているパネルを含むブラウザータブがアクティブになっている間、最大30分間毎分更新されるようになりました。

例として、時間が&#x200B;**[!UICONTROL *06:26pm*]**&#x200B;から&#x200B;**[!UICONTROL *06:27午後&#x200B;*]**&#x200B;に移動すると、**[!UICONTROL &#x200B;総収益/時間&#x200B;]**&#x200B;の可視化と&#x200B;**[!UICONTROL &#x200B;総収益/時間&#x200B;]**&#x200B;のフリーフォームテーブルを更新する&#x200B;**[!UICONTROL &#x200B; リアルタイムレポートパネル &#x200B;]**&#x200B;のスナップショットを以下に示します。

![&#x200B; リアルタイム更新](assets/real-time-refresh.gif)

30分後、またはブラウザータブが非アクティブになるとすぐに、**[!UICONTROL リアルタイム更新]**&#x200B;切り替えが自動的に無効になり、リアルタイム更新が停止されます。

リアルタイム更新トグルを無効にすると、パネル（および内のすべてのビジュアライゼーション）が[に戻り、Customer Journey Analyticsの標準レポートデータと機能を使用します](real-time.md#how-it-works)。
