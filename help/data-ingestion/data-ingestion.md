---
title: データ取り込みの概要
description: Customer Journey Analytics にデータを取り込む様々な方法について
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: dca1cc33058ba57815c3534ab21da86d5247531a
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 63%

---

# データ取り込みの概要

データをCustomer Journey Analyticsに取り込む場合は、いくつかの方法があります。 従来の Adobe Analytics データを移動することを想定しているものもあれば、Adobe Experience Platform に取り込んだデータを使用することを想定しているものもあります。

>[!IMPORTANT]
>
>すべてのシナリオにおいて、Customer Journey Analytics で&#x200B;_使用_&#x200B;するデータは、実際には Adobe Experience Platform で&#x200B;_取り込んだ_&#x200B;データになります。

[概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja)で前述の、大まかな Customer Journey Analytics アーキテクチャを参照してください。

![この節で説明するCustomer Journey Analyticsーアーキテクチャ](./assets/cja-architecture.png)

上記のアーキテクチャのデータセットのソースには、次のようにさまざまなものがあります。

- バッチデータ

- ストリーミングデータ

- 現在の Adobe Analytics デプロイメントのデータ

- Adobe Experience Platform Web/Mobile SDK を使用した web サイト/モバイルアプリのトラッキングからのデータ。

- Adobe Experience Platform Edge Networkサーバー API を使用したデスクトップアプリケーション、コンソールゲーム、セットトップボックス、IoT デバイスのトラッキングからのデータ

- アドビがソースコネクタを提供するサードパーティのデータプロバイダーからのデータ

また、これらのデータセットを多数持つことができます。

ドキュメントのこの節では、様々なシナリオに関するクイックスタートガイドを提供します。

## 取り込みの優先順位と待ち時間

イベントデータが 24 時間、48 時間、7 日前のいずれであっても、90 分以内（SLT）にCustomer Journey Analyticsからイベントデータを取り込むことができます。

この機能は、会社が購入した SKU パッケージによって異なることに注意してください。

- 優先度取り込み基本：90 分 SLT 処理で 24 時間経過したデータ（で利用可能） **CJA の基盤** および **CJA 選択**）

- 優先度取り込み中級：90 分 SLT 処理で 72 時間経過したデータ（で利用可能） **CJA プライム**）

- 優先度取り込みの詳細設定：90 分 SLT 処理で 1 週間の古いデータ（で利用可能） **CJA Ultimate**）

## 従来の Adobe Analytics からのデータの取り込みと使用

既に Adobe Analytics をデプロイしており、このデータを Adobe Experience Platform で取り込み、Customer Journey Analytics で使用したり、他のチャネルやデータソースからのデータと組み合わせて分析したりします。

詳しくは、[従来の Adobe Analytics からのデータの取り込みと使用](./analytics.md)を参照してください。


## Edge Networkを介したデータの取り込みと使用

### Adobe Experience Platform Web SDK の使用

Web サイトをAdobeテクノロジで分析し、潜在的に別のソリューションから移行するか、ユーザーの行動の追跡を開始します。 実装に関するアドビのベストプラクティス（Adobe Experience Platform SDK と Edge ネットワークを使用）に従い、データを取り込みます。次に、取り込んだデータを、Customer Journey Analytics 内の他のチャネルやデータソースからのデータと使用し、組み合わせて、分析できます。

参照： [Adobe Experience Platform Web SDK を介したデータの取り込みと使用](./aepwebsdk.md) を参照してください。

### Adobe Experience Platform Mobile SDK の使用

Adobeテクノロジーを使用してモバイルアプリを分析し、潜在的に別のソリューションから移行するか、アプリ内でのユーザーの行動のトラッキングを最初から開始する場合。 実装に関するアドビのベストプラクティス（Adobe Experience Platform SDK と Edge ネットワークを使用）に従い、データを取り込みます。次に、取り込んだデータを、Customer Journey Analytics 内の他のチャネルやデータソースからのデータと使用し、組み合わせて、分析できます。

参照： [Adobe Experience Platform Mobile SDK を介したデータの取り込みと使用](./aepmobilesdk.md) を参照してください。

### Adobe Experience Platform Edge Networkサーバー API の使用

デスクトップアプリケーション、ゲーム機でプレイしたゲーム、セットトップボックスでのビデオストリーミングアプリケーションの使用状況、またはAdobeテクノロジを使用した IoT デバイスを分析する場合。 潜在的に別のソリューションから移行するか、これらのデバイスでのユーザーの行動の追跡を最初から開始します。 実装に関するAdobeのベストプラクティス（Adobe Experience Platform Edge Networkサーバー API とEdge Networkを使用）に従い、データを取り込みます。 次に、取り込んだデータを、Customer Journey Analytics 内の他のチャネルやデータソースからのデータと使用し、組み合わせて、分析できます。

参照： [Adobe Experience Platform Edge Networkサーバー API を介したデータの取り込みと使用](./serverapi.md) を参照してください。

## バッチデータの取り込みと使用

顧客の行動をより深く理解し、顧客のインタラクションを分析するのに役立つ詳細を提供する、関連するバッチデータを使用できます。このようなバッチデータの例としては、CRM システム、ロイヤルティアプリケーション、またはアドビが現在ソースコネクタを提供していないその他のソリューションからの、CSV、JSON、Parquet 形式のフラットファイルがあります。このバッチデータを Adobe Experience Platform に取り込むと、Customer Journey Analytics で他のチャネルやデータソースのデータを使用し、組み合わせて、分析できます。

詳しくは、[バッチデータの取り込みと使用](./batch.md)を参照してください。

## ストリーミングデータの取り込みと使用

CRM システム、ERP システム、またはその他のソースなど、顧客の行動をより深く理解し、顧客とのやり取りを分析するのに役立つ詳細を提供する関連データソースがあります。このデータソースは、アドビが現在ソースコネクタを提供していない、HTTP またはパブリッククラウドのストリーミングインフラストラクチャ経由で通信できます。このストリーミングデータをリアルタイムで Adobe Experience Platform に取り込むと、Customer Journey Analytics で他のチャネルやデータソースのデータを使用し、組み合わせて、分析できます。

詳しくは、[ストリーミングデータの取り込みと使用](./streaming.md)を参照してください。

## ソースコネクタを使用したデータの取り込みと使用

ソースコネクタでサポートされているソースからデータを取得できます。ソースコネクタは、アドビ、ファーストパーティおよびサードパーティのアプリケーションから Adobe Experience Platform にデータを取り込むための設定が可能です。詳しくは、[ソースコネクタの概要](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)を参照してください。ソースコネクタを使用すると、ソースから Adobe Experience Platform へと簡単にデータを取り込み、Customer Journey Analytics で使用したり、他のチャネルやデータソースのデータと組み合わせて分析したりできます。

詳しくは、[ソースコネクタを使用したデータの取り込みと使用](./sources.md)を参照してください。
