---
title: Customer Journey Analytics接続の概要
description: Customer Journey Analytics での接続について説明します。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 97%

---

# 接続の概要

接続を使用すると、Customer Journey Analytics の製品管理者は、イベント、ルックアップ、プロファイルおよび概要データセットなど、取り込む [!DNL  Experience Platform] データソースを定義できます。接続は Customer Journey Analytics の基盤であり、ディメンションまたは指標として[データビュー](/help/data-views/data-views.md)で定義できるデータ（フィールド）の可用性を決定します。

>[!IMPORTANT]
>
>複数の [!DNL Experience Platform] データセットを 1 つの接続に組み合わせることができます。


## 接続ワークフロー

![接続ワークフロー](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

接続ワークフローで行うことができる操作の概要は、以下のとおりです。

| インターフェイス | 説明 |
|:---:|---|
| ➊ | 接続マネージャーから、Customer Journey Analytics の[接続と全体的な使用状況を管理](manage-connections.md)します。 |
| ➋ | [接続の詳細を調べます](manage-connections.md#connection-details)（データセットレコードが取り込まれた、スキップされた、または削除されたなど）。 |
| ➌ | [接続の設定を作成または編集します](create-connection.md#create-or-edit-a-connection)（周期的なデータウィンドウ、使用するサンドボックス、接続に含まれるデータセットなど）。 |
| ➍ | [データセットを接続に追加します](create-connection.md#add-datasets)。接続には少なくとも 1 つのイベントまたは概要データセットが必要ですが、様々なイベント、プロファイル、ルックアップ、概要データセットを含めることができます。 |
| ➎ | 追加するデータセットの[設定を指定](create-connection.md#dataset-settings)します。ユーザーベースまたは [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} アカウントベースの共通の ID に基づいて、様々なデータセットをどのようにリンクするかを決定できます。 |
| ➏ | [既存のデータセットの設定を編集します](create-connection.md#edit-a-dataset)。データセットの設定は、後でいつでも見直すことができます。 |



## アクセス制御

接続管理にアクセスできるのは、コア管理グループに制限する必要があります。接続の設定は、Customer Journey Analytics に取り込まれるデータ量の割り当てに関する契約上の影響を受けます。

>[!MORELIKETHIS]
>
>[アクセス制御](/help/technotes/access-control.md)。

