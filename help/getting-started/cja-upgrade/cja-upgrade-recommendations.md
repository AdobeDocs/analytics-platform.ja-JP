---
title: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時にお勧めのパス
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 4%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードプロセスを開始する前に、まず推奨されるアップグレード手順を理解します。

タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織に適さない場合があります。 推奨されるアップグレード手順を理解したら、アンケートに回答して、組織固有の状況に合わせたアップグレード手順を動的に生成します。

## 1.推奨されるアップグレード手順を理解する

>[!NOTE]
>
>この節で説明するアップグレード手順は、Adobe AnalyticsからCustomer Journey Analyticsに正常にアップグレードするために組織で使用できる推奨アップグレード手順です。
>
>ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。 推奨されるアップグレード手順を理解したら、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケートに回答して ](https://gigazelle.github.io/cja-ttv/) 組織固有の状況に合わせたアップグレード手順を動的に生成します。

Adobe AnalyticsからCustomer Journey Analyticsにアップグレードする際の推奨手順は、Customer Journey Analyticsで推奨されるデータ収集方法であるExperience Platform Web SDK の新しい実装です。 Adobeでは、Web SDK と組み合わせて、Analytics ソースコネクタを使用して、Adobe Analyticsの履歴データを保持し、並列データ比較を実行することをお勧めします。

Customer Journey Analyticsへの完全な移行が完了したら、Analytics ソースコネクタをオフにして、Experience Platform Web SDK のみを使用できます。

1. **Experience PlatformWeb SDK の実装**

   Customer Journey Analytics用のデータを収集する方法として最適なのは、Experience PlatformWeb SDK の新しい実装です。 Customer Journey Analyticsを最大限に活用するための最適な基盤を提供します。これは、Customer Journey Analyticsを実装するための最もパフォーマンスが高く、簡単で、将来性の高い方法であるためです。

   * Adobe Experience Platformはリアルタイムパーソナライゼーションのユースケースを強化するように構築されているので、高性能のレポートとデータの可用性を実現します

   * 他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する

   * Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない

1. **Adobe Analytics ソースコネクタの設定**

   Adobeでは、Customer Journey AnalyticsでExperience Platform Web SDK を使用する方法へスムーズに移行できるように、Adobe Analytics ソースコネクタを使用することをお勧めします。 これにより、履歴データを保持し、既存のAdobe Analytics実装のデータを、新しいExperience Platform Web SDK 実装のデータと並べてCustomer Journey Analyticsで表示できます。

   Analytics ソースコネクタを使用すると、次のことができます。

   * Adobe Analyticsの履歴レポートスイートデータをAdobe Experience PlatformとCustomer Journey Analyticsに取り込みます。

     Adobe Analyticsの履歴データを保持する必要がある限り、Analytics ソースコネクタを実行し続けることができます。

   * Customer Journey Analytics内で、元のAdobe Analytics実装（Analytics 拡張機能、Analytics 拡張機能、Web SDKAppMeasurementのいずれか）で収集したデータを表示します。 このデータを新しい Web SDK 実装と並べて比較できます。

     違いに慣れて慣れるまで、Analytics ソースコネクタを動作し続けることができます。<!--elaborate on what those differences are? -->

   Analytics ソースコネクタをスタンドアロンCustomer Journey Analyticsとして使用することは、長期的に実装を使用する方法にはお勧めしません。 これは、待ち時間が長く、スキーマが散乱し複雑であり、Adobe Analyticsの命名法（prop、eVarなど）に依存しており、最終的にソースコネクタから推奨される Web SDK 実装に移行するのが難しいためです。

## 2.組織のアップグレード手順の動的な生成

タイムラインやリソースの制約などのいくつかの要因によっては、「[ 推奨されるアップグレード手順について ](#1-understand-the-recommended-upgrade-steps) で説明されている推奨アップグレード手順が組織にとって実用的でない場合があります。

組織固有の状況に合わせて動的に生成されたアップグレード手順を表示するには：

1. [Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) に回答してください。

   このアンケートに回答すると、組織に固有の最適なアップグレード手順の概要が段階的に説明されます。 これらは、既存のAdobe Analytics環境およびCustomer Journey Analyticsの目標に最も適したアップグレード手順です。

1. 生成されたステップバイステップの手順に従って、Customer Journey Analyticsにアップグレードします。

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









