---
title: Customer Journey Analytics 接続の概要
description: Customer Journey Analytics での接続について説明します。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: e4ddb98b800457e407bb414ed4929c5d5018cf30
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 10%

---

# 接続の概要

接続を使用すると、Customer Journey Analytics製品管理者は、イベント、ルックアップ、プロファイル、概要データセットなど、様々な [!DNL Adobe Experience Platform] データソースとの接続を確立できます。 これらの接続により、接続から派生データビューへのデータの統合が可能になります。 接続はCustomer Journey Analyticsの基盤であり、ソースデータセットから作成 [!DNL Experience Platform] れます。

>[!IMPORTANT]
>
>複数の [!DNL Experience Platform] データセットを 1 つの接続に組み合わせることができます。


## 接続ワークフロー

![ 接続ワークフロー ](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

接続ワークフローの概要レベルでは、次の操作を行うことができます。

| インターフェイス | 説明 |
|:---:|---|
| ➊ | 接続マネージャーから、Customer Journey Analyticsの [ 接続と全体的な使用状況の管理 ](manage-connections.md) を行います。 |
| ➋ | [ 取り込まれた、スキップされた、削除されたデータセットレコードなど ](manage-connections.md#connection-details) 接続の詳細を調べる」。 |
| ➌ | [ 周期的なデータウィンドウや、接続に含まれるデータセットなど ](create-connection.md#create-or-edit-a-connection) 接続の設定の作成または編集。 |
| ➍ | [ 接続へのデータセットの追加 ](create-connection.md#add-datasets)。 接続には少なくとも 1 つのイベントまたは概要データセットが必要ですが、様々なイベント、プロファイル、ルックアップ、概要データセットを含めることができます。 |
| ➎ | 追加するデータセットの [ 設定を指定 ](create-connection.md#dataset-settings) します。 そのため、共通のユーザーベースまたは [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"} アカウントベースの識別子に基づいて、様々なデータセットをどのようにリンクするかを決定できます。 |
| ➏ | [ 既存のデータセットの設定の編集 ](create-connection.md#edit-a-dataset)。 後の段階で、データセット設定を常に再検討できます。 |



## アクセス制御

接続管理へのアクセスは、コア管理グループに制限する必要があります。 接続設定には、Customer Journey Analyticsに取り込まれるデータのボリューム割り当てに関する契約上の影響があります。

>[!MORELIKETHIS]
>
>[ アクセス制御 ](/help/technotes/access-control.md)。

