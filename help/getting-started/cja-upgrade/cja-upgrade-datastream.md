---
title: Customer Journey Analytics用のスキーマの作成
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 51%

---

# Customer Journey Analytics で使用するデータストリームの作成 {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Adobe Experience Platform でのデータストリームの作成"
>abstract="データストリームは、設定済みのすべてのサービスにデータを渡す中間の場所です。Adobe Experience Platform でこの場所を作成します。<br><br>Platform インターフェイスでのデータストリームの初期作成には、わずか数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

データストリームは、Adobe Experience Platform Web および Mobile SDK を実装する際のサーバーサイド設定を表します。Adobe Experience Platform SDK を使用してデータを収集する際、データはAdobe Experience Platform Edge Network に送信されます。データの転送先となるサービスを決定するデータストリームです。

設定では、収集したデータをAdobe Experience Platformのデータセットに送信するようにデータストリームを設定します。

>[!NOTE]
>
>次の手順は、AppMeasurementまたはAdobe Analytics拡張機能（タグ）を使用する Analytics 実装にのみ必要です。
>
>Adobe Analyticsの実装で Web SDKまたは Web SDK拡張機能を使用している場合、データストリームはAdobe Analytics環境に既に存在します。

データストリームを設定するには：

1. Adobe Experience Platformで、左パネルの **[!UICONTROL データ収集]** から [!UICONTROL  データストリーム ] を選択します。

1. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。

1. データストリームに名前を付けて説明します。[!UICONTROL イベントスキーマ]リストからスキーマを選択します。

   ![新規データストリーム](assets/new-datastream.png)

1. 「**[!UICONTROL 保存]**」を選択します。

{{upgrade-final-step}}
