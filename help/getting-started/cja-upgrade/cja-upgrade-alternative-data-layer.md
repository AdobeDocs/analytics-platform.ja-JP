---
title: Customer Journey Analyticsへのアップグレード時の代替方法
description: Customer Journey Analyticsへのアップグレード時の代替方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 44%

---

# アップグレードの代替案：Customer Journey Analytics へのデータレイヤーの送信 {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="アドビへのデータレイヤーの送信"
>abstract="XDM オブジェクトを通じてデータを送信する代わりに、データオブジェクトを通じてデータレイヤー全体をアドビに送信できます。<br><br>このオプションを使用すると、XDM オブジェクトをゼロから入力するのではなく、データレイヤーを XDM にマッピングできるので、実装時間が節約されます。ただし、アドビではすぐに解釈できないデータが大量に存在するので、このマッピングは膨大な作業となります。また、このオプションでは、今後データに追加するフィールドはデータストリームの XDM にマッピングする必要があるので、時間の経過と共に複雑さが増します。"

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
>abstract="すべてのデータレイヤー要素を目的の XDM フィールドにマッピングします。アドビではそのデータの保存場所や保存方法がわからないので、XDM フィールドにマッピングされていないデータレイヤー要素は、完全にドロップされます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Customer Journey Analyticsにアップグレードする場合、Adobeは [Experience Platform web SDKの新規実装を推奨 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) します。 ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。

XDM オブジェクトを使用してデータを収集する代わりに、データレイヤー全体をCustomer Journey Analyticsに送信できます。 ただし、この代替オプションを使用すると、時間の経過と共に複雑さが増します。

## メリットとデメリット

どちらの方法も同じタスクを実行するので、この方法は [Customer Journey AnalyticsでAppMeasurement データ収集ロジックを使用する ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md) と相互排他的です。

このアップグレードの代替手段を使用する場合のメリットとデメリットを次に示します。

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**現在のデータレイヤーロジックを使用**：この方法では、従来の Web SDK実装の代わりに現在のデータレイヤーロジックを使用します。 このアプローチには何らかの設定が必要ですが、ゼロからまったく新しい実装を行う必要はなく、データ要素やタグルールを入力する必要もありません。 これにより、XDM オブジェクトをゼロから入力するのではなく、データレイヤーから XDM にデータをマッピングできます。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織でAdobe Experience Platformを使用する準備が整ったら、Customer Journey Analyticsのデータセットにデータを送信する必要があります。 <p>このオプションを使用すると、クライアントサイドのデータレイヤー全体をデータオブジェクトに入れて、Adobeに送信できるので、Adobeでは簡単に解釈できない大量のデータが発生します。 Adobeがデータを解釈できるようにするには、データストリームマッピングを使用して、個々のフィールドを目的の XDM フィールドにマッピングする必要があります。</p></li><li>**厳密な実装**：実装は、ヒットが送信される際にデータレイヤーが提供する内容に制限されます。 これは、基本的なデータが必要な組織にとっては問題ありませんが、ほとんどの組織では、このタイプの厳密な実装は避け、データ要素を格納できるより柔軟な実装を優先する必要があります。</li><li>**今後の変更は実装がより難しくなります**：今後後でデータに追加するフィールドは、データストリームの XDM にマッピングする必要があります。</li></ul> |

{style="table-layout:auto"}

## 基本手順

データレイヤー全体をCustomer Journey Analyticsに送信するための基本的な手順は次のとおりです。

1. 目的の時間にアドビにデータを送信する実装を設定し、JSON ペイロードを設定して、全体にデータレイヤーを指定します。

1. すべてのデータレイヤー要素を目的の XDM フィールドにマッピングします。

   アドビではそのデータの保存場所や保存方法がわからないので、XDM フィールドにマッピングされていないデータレイヤー要素は、完全にドロップされます。
