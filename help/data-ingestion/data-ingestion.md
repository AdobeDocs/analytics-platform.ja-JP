---
title: データ取り込みの概要
description: Customer Journey Analytics にデータを取り込む様々な方法について
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 5de8c0daaa7eea0a9ab993d256e2b0a14f37301e
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 8%

---


# データ取り込みの概要

Customer Journey Analytics へのデータの取り込みには、様々なオプションがあります。従来のAdobe Analyticsデータを移動することを想定しているものもあれば、Adobe Experience Platformに直接取り込まれたデータを使用することを想定しているものもあります。

>[!IMPORTANT]
>
>すべてのシナリオで、 _use_ Customer Journey Analyticsは _取得済み_ Adobe Experience Platform


前述のCustomer Journey Analytics・アーキテクチャの概要を [概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja):

![Customer Journey Analytics](./assets/cja-architecture.png)

上記のアーキテクチャのデータセットは、次の様々なソースから作成できます。バッチデータ、ストリーミングデータ、現在のAdobe Analyticsデプロイメントからのデータ、Adobe Experience Platform Web/Mobile SDK を使用して web サイトやモバイルアプリを追跡したデータ、またはAdobeがソースコネクタを提供するサードパーティのデータプロバイダーからのデータ。 多くのデータセットを持つことができます

ドキュメントのこの節では、様々なシナリオに関するクイックスタートガイドを提供します。

## 従来のAdobe Analyticsからのデータの取り込みと使用

既にAdobe Analyticsがデプロイ済みで、このデータをAdobe Experience Platformで取り込んで使用し、Customer Journey Analyticsの他のチャネルやデータソースからのデータと組み合わせて分析します。

詳しくは、 [従来のAdobe Analyticsからのデータの取り込みと使用](./analytics.md) を参照してください。

## Adobe Experience Platform Web SDK と Edge Network を使用したデータの取得と使用

Adobeテクノロジーを使用して Web サイトを分析し、潜在的に別のソリューションから移行するか、訪問者の行動の追跡を開始したい。 Adobe Experience Platform SDK と Edge ネットワークを使用してAdobeを取り込む実装に関する、データのベストプラクティスに従う必要があります。 次に、取り込んだデータを、Customer Journey Analytics内の他のチャネルやデータソースからのデータと組み合わせて、分析できます。

詳しくは、 [Adobe Experience Platform Web SDK と Edge Network を使用したデータの取得と使用](./aepwebsdk.md) を参照してください。

## バッチデータの取り込みと使用

顧客の行動をより深く理解し、顧客のインタラクションを分析するのに役立つ詳細を提供する、関連するバッチデータを使用できます。 このようなバッチデータの例としては、CSV、JSON、Parquet 形式のフラットファイル (CRM システム、ロイヤリティーアプリケーション、その他のソリューションでは、Adobeが現在ソースコネクタを提供していません ) があります。 このバッチデータをAdobe Experience Platformに取り込むと、他のチャネルやデータソースのデータと組み合わせて、Customer Journey Analyticsで使用し、分析できます。

詳しくは、 [バッチデータの取り込みと使用](./batch.md) を参照してください。

## ストリーミングデータの取り込みと使用

CRM システム、ERP システム、またはその他のソースなど、顧客の行動をより深く理解し、顧客とのやり取りを分析するのに役立つ詳細を提供する関連データソースがあります。 このデータソースは、HTTP またはパブリッククラウドのストリーミングインフラストラクチャ経由で通信できますが、Adobeが現在ソースコネクタを提供していない場合に使用します。 このストリーミングデータをリアルタイムでAdobe Experience Platformに取り込むと、Customer Journey Analytics内の他のチャネルやデータソースからのデータを使用し、組み合わせて、分析できます。

詳しくは、 [ストリーミングデータの取り込みと使用](./streaming.md) を参照してください。

## ソースコネクタを使用したデータの取り込みと使用

ソースコネクタでサポートされているソースからデータを取得できます。 ソースコネクタは、Adobe、ファーストパーティおよびサードパーティのアプリケーションからAdobe Experience Platformにデータを取り込むための設定が可能です。 詳しくは、 [ソースコネクタの概要](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja) を参照してください。 ソースコネクタを使用すると、ソースからAdobe Experience Platformに簡単にデータを取り込み、を使用して、他のチャネルやCustomer Journey Analytics内のデータソースからのデータと組み合わせて分析できます。

詳しくは、 [ソースコネクタを使用したデータの取り込みと使用](./sources.md) を参照してください。

