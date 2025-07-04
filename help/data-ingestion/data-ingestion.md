---
title: データ取り込みの概要
description: Customer Journey Analytics にデータを取り込む様々な方法について
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: 8071e8d5e1ab7e9cfc5037d710361a4d10285704
workflow-type: ht
source-wordcount: '957'
ht-degree: 100%

---

# データ取り込みの概要

Customer Journey Analytics にデータを取り込むには、いくつかのオプションがあります。従来の Adobe Analytics データを移動することを想定しているものもあれば、Adobe Experience Platform に取り込んだデータを使用することを想定しているものもあります。

>[!IMPORTANT]
>
>すべてのシナリオにおいて、Customer Journey Analytics で&#x200B;_使用_&#x200B;するデータは、実際には Adobe Experience Platform で&#x200B;_取り込んだ_&#x200B;データになります。

[概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja)で前述の、大まかな Customer Journey Analytics アーキテクチャを参照してください。

![この節で説明する Customer Journey Analytics アーキテクチャ](./assets/cja-architecture.png)

上記のアーキテクチャのデータセットのソースには、次のようにさまざまなものがあります。

- バッチデータ

- ストリーミングデータ

- 現在の Adobe Analytics デプロイメントのデータ

- Adobe Experience Platform Web／Mobile SDK を使用した web サイトやモバイルアプリのトラッキングデータ

- Adobe Experience Platform Edge Network Server API を使用したデスクトップアプリケーション、コンソールゲーム、セットトップボックス、IoT デバイスのトラッキングデータ

- アドビがソースコネクタを提供するサードパーティのデータプロバイダーからのデータ

また、これらのデータセットを多数持つことができます。

ドキュメントのこの節では、様々なシナリオに関するクイックスタートガイドを提供します。

## 取り込みの優先順位と待ち時間

イベントデータが 24 時間、48 時間、7 日前のいずれかであるかに関係なく、データを 90 分以内（SLT）に Customer Journey Analytics に取り込むことができます。

この機能は、会社が購入した SKU パッケージによって異なります。

- 優先取り込み基本：24 時間前のデータを 90 分以内に SLT 処理（**CJA Foundation** および **CJA Select** で使用可能）

- 優先取り込み中級：72 時間前のデータを 90 分以内に SLT 処理（**CJA Prime** で使用可能）

- 優先取り込み上級：1 週間前のデータを 90 分以内に SLT 処理（**CJA Ultimate** で使用可能）

## 従来の Adobe Analytics からのデータの取り込みと使用

既に Adobe Analytics をデプロイしており、このデータを Adobe Experience Platform で取り込み、Customer Journey Analytics で使用したり、他のチャネルやデータソースからのデータと組み合わせて分析したりします。

詳しくは、[従来の Adobe Analytics からのデータの取り込みと使用](./analytics.md)を参照してください。


## Edge Network を介したデータの取り込みと使用

### Adobe Experience Platform Web SDK の使用

アドビのテクノロジーを使用して web サイトを分析し、別のソリューションから移行するか、ユーザーの行動をトラッキングします。実装に関するアドビのベストプラクティス（Adobe Experience Platform SDK と Edge ネットワークを使用）に従い、データを取り込みます。次に、取り込んだデータを、Customer Journey Analytics 内の他のチャネルやデータソースからのデータと使用し、組み合わせて、分析できます。

詳しくは、[Adobe Experience Platform Web SDK を介したデータの取り込みと使用](./aepwebsdk.md)を参照してください。

### Adobe Experience Platform Mobile SDK の使用

アドビのテクノロジーを使用してモバイルアプリを分析し、別のソリューションから移行するか、アプリの使用開始時からユーザーの行動をトラッキングします。実装に関するアドビのベストプラクティス（Adobe Experience Platform SDK と Edge ネットワークを使用）に従い、データを取り込みます。次に、取り込んだデータを、Customer Journey Analytics 内の他のチャネルやデータソースからのデータと使用し、組み合わせて、分析できます。

詳しくは、[Adobe Experience Platform Mobile SDK を介したデータの取り込みと使用](./aepmobilesdk.md)を参照してください。

### Adobe Experience Platform Edge Network Server API の使用

アドビのテクノロジーを使用して、デスクトップアプリケーション、ゲームコンソールでプレイしたゲーム、セットトップボックスでのビデオストリーミングアプリケーションの使用状況、または IoT デバイスを分析します。別のソリューションから移行するか、これらのデバイスの使用開始時からユーザーの行動をトラッキングします。実装に関するアドビのベストプラクティス（Adobe Experience Platform Edge Network Server API と Edge Network を使用）に従い、データを取り込みます。次に、取り込んだデータを、Customer Journey Analytics 内の他のチャネルやデータソースからのデータと使用し、組み合わせて、分析できます。

詳しくは、[Adobe Experience Platform Edge Network Server API を介したデータの取り込みと使用](./serverapi.md)を参照してください。

## バッチデータの取り込みと使用

顧客の行動をより深く理解し、顧客のインタラクションを分析するのに役立つ詳細を提供する、関連するバッチデータを使用できます。このようなバッチデータの例としては、CRM システム、ロイヤルティアプリケーション、またはアドビが現在ソースコネクタを提供していないその他のソリューションからの、CSV、JSON、Parquet 形式のフラットファイルがあります。このバッチデータを Adobe Experience Platform に取り込むと、Customer Journey Analytics で他のチャネルやデータソースのデータを使用し、組み合わせて、分析できます。

詳しくは、[バッチデータの取り込みと使用](./batch.md)を参照してください。

## ストリーミングデータの取り込みと使用

CRM システム、ERP システム、またはその他のソースなど、顧客の行動をより深く理解し、顧客とのやり取りを分析するのに役立つ詳細を提供する関連データソースがあります。このデータソースは、アドビが現在ソースコネクタを提供していない、HTTP またはパブリッククラウドのストリーミングインフラストラクチャ経由で通信できます。このストリーミングデータをリアルタイムで Adobe Experience Platform に取り込むと、Customer Journey Analytics で他のチャネルやデータソースのデータを使用し、組み合わせて、分析できます。

詳しくは、[ストリーミングデータの取り込みと使用](./streaming.md)を参照してください。

## ソースコネクタを使用したデータの取り込みと使用

ソースコネクタでサポートされているソースからデータを取得できます。ソースコネクタは、アドビ、ファーストパーティおよびサードパーティのアプリケーションから Adobe Experience Platform にデータを取り込むための設定が可能です。詳しくは、[ソースコネクタの概要](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)を参照してください。ソースコネクタを使用すると、ソースから Adobe Experience Platform へと簡単にデータを取り込み、Customer Journey Analytics で使用したり、他のチャネルやデータソースのデータと組み合わせて分析したりできます。

詳しくは、[ソースコネクタを使用したデータの取り込みと使用](./sources.md)を参照してください。

>[!MORELIKETHIS]
>
>ブログ：[Adobe Customer Journey Analytics でのデータ処理と取り込みについて詳しく見る](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091?profile.language=ja)

