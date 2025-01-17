---
title: Customer Journey Analytics用スキーマの作成
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 41965bcd5ae8252fbf2ceda0d2b633ec6dc0e9a3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 23%

---

# Customer Journey Analyticsで使用するデータストリームを作成する

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

データストリームは、Adobe Experience Platform Web および Mobile SDK を実装する際のサーバーサイド設定を表します。Adobe Experience Platform SDK を使用してデータを収集する際、データはAdobe Experience Platform Edge Network に送信されます。データの転送先となるサービスを決定するデータストリームです。

設定では、収集したデータをAdobe Experience Platformのデータセットに送信するようにデータストリームを設定します。

>[!NOTE]
>
>次の手順は、Analytics またはAdobe AnalyticsAppMeasurement（タグ）を使用する Analytics 実装にのみ必要です。
>
>Adobe Analyticsの実装で Web SDKまたは Web SDK拡張機能を使用している場合、データストリームはAdobe Analytics環境に既に存在します。

データストリームを設定するには：

1. Adobe Experience Platformで、左パネルの **[!UICONTROL データ収集]** から [!UICONTROL  データストリーム ] を選択します。

1. **[!UICONTROL 新しいデータストリーム]**&#x200B;を選択します。

1. データストリームに名前を付けて説明します。[!UICONTROL イベントスキーマ]リストからスキーマを選択します。

   ![新規データストリーム](assets/new-datastream.png)

1. 「**[!UICONTROL 保存]**」を選択します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
