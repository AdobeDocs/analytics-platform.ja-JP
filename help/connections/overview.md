---
title: Customer Journey Analytics Connectionsの概要
description: Customer Journey Analytics での接続について説明します。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
autotag-review: '2026-05-19T08:50:38.470Z'
TQID: 'https://experienceleague.adobe.com/bD6BGFGwJkHr3w4GYXoOCVH2l49csOvsaYLgqTAL41I'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: b3197353-f189-4932-8378-3f3bc40e6071id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 294
ht-degree: 88%

---

# 接続の概要

接続を使用すると、Customer Journey Analytics の製品管理者は、イベント、ルックアップ、プロファイルおよび概要データセットなど、取り込む [!DNL  Experience Platform] データソースを定義できます。 接続は Customer Journey Analytics の基盤であり、ディメンションまたは指標として[データビュー](/help/data-views/data-views.md)で定義できるデータ（フィールド）の可用性を決定します。

>[!IMPORTANT]
>
>複数の [!DNL Experience Platform] データセットを 1 つの接続に組み合わせることができます。


## 接続ワークフロー

![接続ワークフロー](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ データソースへの接続](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

接続ワークフローで行うことができる操作の概要は、以下のとおりです。

| インターフェイス | 説明 |
|:---:|---|
| ➊ | 接続マネージャーから、Customer Journey Analytics の[接続と全体的な使用状況を管理](manage-connections.md)します。 |
| ➋ | [接続の詳細を調べます](manage-connections.md#connection-details)（データセットレコードが取り込まれた、スキップされた、または削除されたなど）。 |
| ➌ | [接続の設定を作成または編集します](create-connection.md#create-or-edit-a-connection)（周期的なデータウィンドウ、使用するサンドボックス、接続に含まれるデータセットなど）。 |
| ➍ | [データセットを接続に追加します](create-connection.md#add-datasets)。 接続には少なくとも 1 つのイベントまたは概要データセットが必要ですが、様々なイベント、プロファイル、ルックアップ、概要データセットを含めることができます。 |
| ➎ | 追加するデータセットの[設定を指定](create-connection.md#dataset-settings)します。 ユーザーベースまたは [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} アカウントベースの共通の ID に基づいて、様々なデータセットをどのようにリンクするかを決定できます。 |
| ➏ | [既存のデータセットの設定を編集します](create-connection.md#edit-a-dataset)。 データセットの設定は、後でいつでも見直すことができます。 |



## アクセス制御

接続管理にアクセスできるのは、コア管理グループに制限する必要があります。 接続の設定は、Customer Journey Analytics に取り込まれるデータ量の割り当てに関する契約上の影響を受けます。

>[!MORELIKETHIS]
>
>[アクセス制御](/help/technotes/access-control.md)。

