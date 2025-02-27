---
title: Customer Journey Analytics用の Streaming Media Collection の設定
description: Customer Journey Analytics用の Streaming Media Collection の設定方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Customer Journey Analytics用の Streaming Media Collection の設定 {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Media Edgeのセットアップと実装"
>abstract="Adobe Streaming Media Collection を設定して、Experience Platform Edgeを使用することにより、Customer Journey Analyticsでデータを利用できるようになります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Streaming Media Collection をAdobe Analyticsに実装する手順は、Customer Journey Analyticsで現在 Streaming Media Collection を実装している環境によって異なります。

Streaming Media Collection は、次のいずれかの方法でAdobe Analyticsに実装できます。

* [ストリーミングメディアコレクション用のEdge Network実装](#edge-network-implementations)

+++ インフォグラフィックを表示

  ![Streaming Media on Edgeの実装 ](assets/streaming-media-edge.png)

+++

* [ストリーミングメディアコレクション用のAdobe Analytics専用の実装](#adobe-analytics-only-implementations)

+++ インフォグラフィックを表示

  ![Analytics のみの実装 ](assets/analytics-implementation.png)

+++

これらの実装方法の違いについて詳しくは、『ストリーミングメディアコレクションガイド』の [ ストリーミングメディアコレクションの実装 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) を参照してください。

## ストリーミングメディアコレクション用のEdge Network実装

Streaming Media Collection が [Adobe Analyticsの実装でEdge Networkを使用して実装 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods) されている場合、Streaming Media Collection をCustomer Journey Analyticsにアップグレードするために必要ないくつかの手順は、Adobe Analyticsの実装に既に含まれています。 完了した手順は次のとおりです。

* [Adobe Experience Platformでのスキーマの設定 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Adobe Experience Platformでのデータセットの作成 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Adobe Experience Platformでのデータストリームの設定 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

Customer Journey Analyticsへのアップグレードの一環として、次の追加手順を完了する必要があります。

>[!NOTE]
>
>Customer Journey Analyticsのアップグレード手順を完了したら、Adobe Analyticsでストリーミングメディアコレクション実装のスキーマ、データセット、データストリームを使用していることを確認してください。

* [Customer Journey Analytics で接続を作成する](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Customer Journey Analytics でデータビューを作成](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## ストリーミングメディアコレクション用のAdobe Analytics専用の実装

Streaming Media Collection が [Adobe Analytics環境でAdobe Analyticsのみの実装を使用して実装 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods) されている場合、Streaming Media データがまだEdge Networkに送信されていないことを意味します。

Adobe AnalyticsからCustomer Journey Analyticsにアップグレードする際に、スキーマ、データセット、データストリーム、接続、データビューを作成する際に、ストリーミングメディアコレクションデータを考慮して次の選択を行います。

* Customer Journey Analyticsのスキーマを作成する場合は、`MediaAnalytics Interaction Details` フィールドグループを含めます。

  このフィールドグループの追加について詳しくは、ストリーミングメディアコレクションガイドの [Adobe Experience Platformでのスキーマの設定 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) を参照してください。

  スキーマの作成について詳しくは、[Customer Journey Analyticsで使用するカスタムスキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) を参照してください。

* Media Analytics 用にデータストリームを設定する際に、Customer Journey Analyticsを有効にします。

  このオプションを有効にする方法については、ストリーミングメディアコレクションガイドの [Adobe Experience Platformでのデータストリームの設定 ](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) を参照してください。

  データストリームの作成について詳しくは、[Customer Journey Analyticsで使用するデータストリームの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md) を参照してください。

* Customer Journey Analyticsのデータビューを作成する際に、ストリーミングメディアコレクションの必須スキーマフィールドを含めます。

  これらのスキーマフィールドを XDM オブジェクトの正しい値に必ずマッピングしてください。

  必須フィールドについて詳しくは、ストリーミングメディアコレクションガイドの [Customer Journey Analyticsでのデータビューの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) を参照してください。

  データビューの作成について詳しくは、[Customer Journey Analyticsでのデータビューの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) を参照してください。


