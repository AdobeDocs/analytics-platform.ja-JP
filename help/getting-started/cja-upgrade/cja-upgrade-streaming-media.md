---
title: Customer Journey Analytics 用ストリーミングメディアコレクションの設定
description: Customer Journey Analytics用の Streaming Media Collection の設定方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 20%

---

# Customer Journey Analytics 用ストリーミングメディアコレクションの設定 {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Media Edge の設定と実装"
>abstract="ストリーミングメディアコレクションを Customer Journey Analytics と共に使用する予定の場合は、アップグレードプロセスの特定の手順で特定の選択を行う必要があります。例えば、スキーマに MediaAnalytics インタラクションの詳細フィールドグループを追加したり、データストリームで Media Analytics を有効にしたりする必要があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Analyticsと同様に、ストリーミングメディアコレクションを使用して、Customer Journey Analyticsで使用するストリーミングメディアデータを収集できます。 Streaming Media Collection をAdobe Analyticsで使用する場合は、Customer Journey Analyticsへのアップグレード計画に含める必要があります。

Adobe AnalyticsからCustomer Journey Analyticsにアップグレードする手順を実行する際に、ストリーミングメディアコレクションのデータを考慮して、次の選択をおこないます。

* Customer Journey Analyticsのスキーマを作成する場合は、`MediaAnalytics Interaction Details` フィールドグループを含めます。

  このフィールドグループの追加について詳しくは、ストリーミングメディアコレクションガイドの [Adobe Experience Platformでのスキーマの設定 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) を参照してください。

  スキーマの作成について詳しくは、[Customer Journey Analyticsで使用するカスタムスキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) を参照してください。

* Media Analytics 用にデータストリームを設定する際に、Customer Journey Analyticsを有効にします。

  このオプションを有効にする方法については、ストリーミングメディアコレクションガイドの [Adobe Experience Platformでのデータストリームの設定 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) を参照してください。

  データストリームの作成について詳しくは、[Customer Journey Analyticsで使用するデータストリームの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md) を参照してください。

  >[!NOTE]
  >
  >Adobe Analytics実装で既にExperience Platform Web SDKを使用している場合、この手順は必要ありません。

* Customer Journey Analyticsのデータビューを作成する際に、ストリーミングメディアコレクションの必須スキーマフィールドを含めます。

  これらのスキーマフィールドを XDM オブジェクトの正しい値に必ずマッピングしてください。

  必須フィールドについて詳しくは、ストリーミングメディアコレクションガイドの [Customer Journey Analyticsでのデータビューの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) を参照してください。

  データビューの作成について詳しくは、[Customer Journey Analyticsでのデータビューの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) を参照してください。

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
