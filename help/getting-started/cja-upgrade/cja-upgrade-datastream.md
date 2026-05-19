---
title: Customer Journey Analytics のスキーマの作成
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパスについて説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
autotag-review: '2026-05-19T08:13:03.106Z'
TQID: 'https://experienceleague.adobe.com/vzavQGq0OyhXTpSkqe3nnXQEW0Nax9RXt4SwTRwa4UU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 100%

---

# Customer Journey Analytics で使用するデータストリームの作成 {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Adobe Experience Platform でデータストリームを作成"
>abstract="データストリームは、設定済みのすべてのサービスにデータを渡す中間の場所です。 Adobe Experience Platform でこの場所を作成します。<br><br>Platform インターフェイスでのデータストリームの初期作成は、わずか数分で完了します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

データストリームは、Adobe Experience Platform Web および Mobile SDK を実装する際のサーバーサイド設定を表します。 Adobe Experience Platform SDK を使用してデータを収集する際、データはAdobe Experience Platform Edge Network に送信されます。 これは、データの転送先となるサービスを決定するデータストリームです。

設定では、収集したデータを Adobe Experience Platform のデータセットに送信するようにデータストリームを設定する必要があります。

>[!NOTE]
>
>次の手順は、AppMeasurement または Analytics 拡張機能（タグ）を使用した Adobe Analytics 実装の場合にのみ必要です。
>
>Adobe Analytics 実装で Web SDK または Web SDK 拡張機能を使用する場合、データストリームは Adobe Analytics 環境に既に存在します。

データストリームを設定するには：

1. Adobe Experience Platform で、左側のパネルにある[!UICONTROL データ収集]から「**[!UICONTROL データストリーム]**」を選択します。

1. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。

1. データストリームに名前を付けて説明します。 [!UICONTROL イベントスキーマ]リストからスキーマを選択します。

   ![新規データストリーム](assets/new-datastream.png)

1. 「**[!UICONTROL 保存]**」を選択します。

{{upgrade-final-step}}
