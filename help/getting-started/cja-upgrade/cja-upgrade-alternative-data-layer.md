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
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 54%

---

# アップグレードの代替案：Customer Journey Analytics へのデータレイヤーの送信 {#data-collection-data-layer}

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
>abstract="目的の時間にアドビにデータを送信する実装を設定し、JSON ペイロードを設定して、全体にデータレイヤーを指定します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="XDM への各データレイヤー要素の割り当て"
>abstract="すべてのデータレイヤー要素を目的の XDM フィールドにマッピングします。 アドビではそのデータの保存場所や保存方法がわからないので、XDM フィールドにマッピングされていないデータレイヤー要素は、完全にドロップされます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Customer Journey Analytics にアップグレードする場合は、[Experience Platform Web SDK の新しい実装をお勧め](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)します。 ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。

XDM オブジェクトでデータを収集する代わりに、データレイヤー全体をCustomer Journey Analyticsに送信できます。 しかし、この代替案は、時間の経過とともにさらなる複雑さを引き起こします。

## メリットとデメリット

このメソッドは、Customer Journey Analytics[&#128279;](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)でAppMeasurement データ収集ロジックを使用すると相互に排他的です。両方のメソッドで同じタスクが実行されます。

次に、このアップグレードの代替手段を使用する利点と欠点を示します。

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>Adobe CX Enterpriseのデータ収集の実装を、他のCX Enterprise製品（AJO、RTCDPなど）と統合します</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**現在のデータ層ロジックを使用**：このメソッドでは、従来のWeb SDKの実装の代わりに、現在のデータ層ロジックを使用します。 このアプローチでは、ある程度の設定が必要ですが、まったく新しい実装をゼロから実装する必要はなく、データ要素やタグルールを入力する必要もありません。 これにより、XDM オブジェクトをゼロから入力するのではなく、データ レイヤーからXDMにデータをマッピングできます。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。 <p>このオプションを使用すると、クライアントサイドのデータレイヤー全体をデータオブジェクトに配置してAdobeに送信できるため、Adobeでは容易に解釈できない大量のデータが生成されます。 Adobeでデータを解釈できるようにするには、データストリームマッピングを使用して、個々のフィールドを目的のXDM フィールドにマッピングする必要があります。</p></li><li>**厳格な実装**：実装は、ヒットが送信されるときにデータレイヤーが提供するものに制限されます。 これは、基本的なデータが必要な企業にとっては受け入れられるかもしれませんが、多くの企業では、データ要素の収集を可能にする、より柔軟な実装を優先して、この種の厳格な実装を避けるべきです。</li><li>**今後の変更は実装がより困難です**：今後後でデータに追加するフィールドは、データストリームのXDMにマッピングする必要があります。</li></ul> |

{style="table-layout:auto"}

## 基本手順

データレイヤー全体をCustomer Journey Analyticsに送信するための基本的な手順は次のとおりです。

1. 目的の時間にアドビにデータを送信する実装を設定し、JSON ペイロードを設定して、全体にデータレイヤーを指定します。

1. すべてのデータレイヤー要素を目的の XDM フィールドにマッピングします。

   アドビではそのデータの保存場所や保存方法がわからないので、XDM フィールドにマッピングされていないデータレイヤー要素は、完全にドロップされます。
