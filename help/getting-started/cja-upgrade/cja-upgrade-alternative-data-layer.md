---
title: Customer Journey Analyticsにアップグレードする際の代替方法
description: Customer Journey Analyticsにアップグレードする際の代替方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
autotag-review: '2026-05-19T08:09:26.880Z'
TQID: 'https://experienceleague.adobe.com/IsYrCVRcY1cd2xSYV7A-iJ2jx8Ku-oZ-BtHu8If-55Y'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 54%
---
# Customer Journey Analytics へのデータレイヤー送信というアップグレードの代替案 {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="アドビへのデータレイヤーの送信"
>abstract="XDM オブジェクトを通じてデータを送信する代わりに、データオブジェクトを通じてデータレイヤー全体をアドビに送信できます。<br><br>このオプションを使用すると、XDM オブジェクトをゼロから入力するのではなく、データレイヤーを XDM にマッピングできるので、実装時間が節約されます。 ただし、アドビではすぐに解釈できないデータが大量に存在するので、このマッピングは膨大な作業となります。 また、このオプションでは、今後データに追加するフィールドはデータストリームの XDM にマッピングする必要があるので、時間の経過と共に複雑さが増します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="アドビへのデータレイヤーの送信"
>abstract="実装を設定して、目的のタイミングでアドビにデータを送信し、JSON ペイロード全体がデータレイヤーになるように設定します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="各データレイヤー要素を XDM に割り当てる"
>abstract="すべてのデータレイヤー要素を目的の XDM フィールドにマッピングします。 アドビではそのデータをどこにどのように格納すべきかがわからないため、XDM フィールドにマッピングされていないデータレイヤーの要素は恒久的に破棄されます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Customer Journey Analytics にアップグレードする場合は、[Experience Platform Web SDK の新しい実装をお勧め](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)します。 ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。

XDM オブジェクトでデータを収集する代わりに、データレイヤー全体をCustomer Journey Analyticsに送信できます。 しかし、この代替案は、時間の経過とともにさらなる複雑さを引き起こします。

## メリットとデメリット

このメソッドは、Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)でAppMeasurement データ収集ロジックを使用する[と相互に排他的です。両方のメソッドで同じタスクが実行されます。

次に、このアップグレードの代替手段を使用する利点と欠点を示します。

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>Adobe CX Enterpriseのデータ収集に関して、ほかのCX Enterprise製品（AJO、RTCDPなど）と連携して導入します</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**現在のデータ層ロジックを使用**：このメソッドでは、従来のWeb SDKの実装の代わりに、現在のデータ層ロジックを使用します。 このアプローチでは、ある程度の設定が必要ですが、まったく新しい実装をゼロから実装する必要はなく、データ要素やタグルールを入力する必要もありません。 これにより、XDM オブジェクトをゼロから入力するのではなく、データ レイヤーからXDMにデータをマッピングできます。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。 <p>このオプションを使用すると、クライアントサイドのデータレイヤー全体をデータオブジェクトに配置してAdobeに送信できるため、Adobeでは容易に解釈できない大量のデータが生成されます。 Adobeでデータを解釈できるようにするには、データストリームマッピングを使用して、個々のフィールドを目的のXDM フィールドにマッピングする必要があります。</p></li><li>**厳格な実装**：実装は、ヒットが送信されるときにデータレイヤーが提供するものに制限されます。 これは、基本的なデータが必要な企業にとっては受け入れられるかもしれませんが、多くの企業では、データ要素の収集を可能にする、より柔軟な実装を優先して、この種の厳格な実装を避けるべきです。</li><li>**今後の変更は実装がより困難です**：今後後でデータに追加するフィールドは、データストリームのXDMにマッピングする必要があります。</li></ul> |

{style="table-layout:auto"}

## 基本手順

データレイヤー全体をCustomer Journey Analyticsに送信するための基本的な手順は次のとおりです。

1. 実装を設定して、目的のタイミングでアドビにデータを送信し、JSON ペイロード全体がデータレイヤーになるように設定します。

1. すべてのデータレイヤーの要素を、目的の XDM フィールドにマッピングします。

   アドビではそのデータをどこにどのように格納すべきかがわからないため、XDM フィールドにマッピングされていないデータレイヤーの要素は恒久的に破棄されます。
