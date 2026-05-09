---
title: Customer Journey Analyticsにアップグレードする際の代替方法
description: Customer Journey Analyticsにアップグレードする際の代替方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: ba9ae0e5084aaf1b14cff0ac89abd9b9f3569cc0
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 56%

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

このメソッドは、Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)でAppMeasurement データ収集ロジックを使用する[と相互に排他的です。両方のメソッドで同じタスクが実行されます。

次に、このアップグレードの代替手段を使用する利点と欠点を示します。

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**現在のデータ層ロジックを使用**：このメソッドでは、従来のWeb SDKの実装の代わりに、現在のデータ層ロジックを使用します。 このアプローチでは、ある程度の設定が必要ですが、まったく新しい実装をゼロから実装する必要はなく、データ要素やタグルールを入力する必要もありません。 これにより、XDM オブジェクトをゼロから入力するのではなく、データ レイヤーからXDMにデータをマッピングできます。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。 <p>このオプションを使用すると、クライアントサイドのデータレイヤー全体をデータオブジェクトに配置してAdobeに送信できるため、Adobeでは容易に解釈できない大量のデータが生成されます。 Adobeでデータを解釈できるようにするには、データストリームマッピングを使用して、個々のフィールドを目的のXDM フィールドにマッピングする必要があります。</p></li><li>**厳格な実装**：実装は、ヒットが送信されるときにデータレイヤーが提供するものに制限されます。 これは、基本的なデータが必要な企業にとっては受け入れられるかもしれませんが、多くの企業では、データ要素の収集を可能にする、より柔軟な実装を優先して、この種の厳格な実装を避けるべきです。</li><li>**今後の変更は実装がより困難です**：今後後でデータに追加するフィールドは、データストリームのXDMにマッピングする必要があります。</li></ul> |

{style="table-layout:auto"}

## 基本手順

データレイヤー全体をCustomer Journey Analyticsに送信するための基本的な手順は次のとおりです。

1. 目的の時間にアドビにデータを送信する実装を設定し、JSON ペイロードを設定して、全体にデータレイヤーを指定します。

1. すべてのデータレイヤー要素を目的の XDM フィールドにマッピングします。

   アドビではそのデータの保存場所や保存方法がわからないので、XDM フィールドにマッピングされていないデータレイヤー要素は、完全にドロップされます。
