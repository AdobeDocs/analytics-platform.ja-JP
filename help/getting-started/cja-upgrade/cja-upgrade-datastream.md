---
title: Customer Journey Analytics のスキーマの作成
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパスについて説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 100%

---

# Customer Journey Analytics で使用するデータストリームの作成 {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Adobe Experience Platform でデータストリームを作成"
>abstract="データストリームは、設定済みのすべてのサービスにデータを渡す中間の場所です。Adobe Experience Platform でこの場所を作成します。<br><br>Platform インターフェイスでのデータストリームの初期作成には、わずか数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

データストリームは、Adobe Experience Platform Web および Mobile SDK を実装する際のサーバーサイド設定を表します。Adobe Experience Platform SDK を使用してデータを収集する際、データはAdobe Experience Platform Edge Network に送信されます。これは、データの転送先となるサービスを決定するデータストリームです。

設定では、収集したデータを Adobe Experience Platform のデータセットに送信するようにデータストリームを設定する必要があります。

>[!NOTE]
>
>次の手順は、AppMeasurement または Analytics 拡張機能（タグ）を使用した Adobe Analytics 実装の場合にのみ必要です。
>
>Adobe Analytics 実装で Web SDK または Web SDK 拡張機能を使用する場合、データストリームは Adobe Analytics 環境に既に存在します。

データストリームを設定するには：

1. Adobe Experience Platform で、左側のパネルにある[!UICONTROL データ収集]から「**[!UICONTROL データストリーム]**」を選択します。

1. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。

1. データストリームに名前を付けて説明します。[!UICONTROL イベントスキーマ]リストからスキーマを選択します。

   ![新規データストリーム](assets/new-datastream.png)

1. 「**[!UICONTROL 保存]**」を選択します。

{{upgrade-final-step}}
