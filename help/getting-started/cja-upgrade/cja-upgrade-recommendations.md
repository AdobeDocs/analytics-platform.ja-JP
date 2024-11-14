---
title: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時にお勧めのパス
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dbeb3cabeaa7586e8a024a46e7ae42984e9c1c09
workflow-type: tm+mt
source-wordcount: '1499'
ht-degree: 7%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード

Adobe AnalyticsからCustomer Journey Analyticsにアップグレードする場合は、[ ほとんどのAdobeの推奨アップグレード手順 ](#recommended-upgrade-steps-for-most-organizations) に示すように、Experience PlatformWeb SDK と Analytics ソースコネクタの新規実装をお勧めします。

タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織に適さない場合があります。 その場合は、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) を使用して、組織固有の状況に合わせたアップグレード手順を動的に生成します。

## 大部分の組織で推奨されるアップグレード手順

>[!NOTE]
>
>この節で説明するアップグレード手順は、Adobe AnalyticsからCustomer Journey Analyticsに正常にアップグレードするために組織で使用できる推奨アップグレード手順です。
>
>ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。 その場合は、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) を使用して、組織固有の状況に合わせたアップグレード手順を動的に生成します。

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードには、Experience Platform Web SDK の新しい実装を使用することをお勧めします。これは、Customer Journey Analyticsに推奨されるデータ収集方法です。 Adobeでは Web SDK と組み合わせて、Analytics ソースコネクタをCustomer Journey Analyticsへの移行に役立てることもお勧めします。 Analytics ソースコネクタを使用して、Adobe Analyticsの履歴データを保持し、横に並べてデータを比較します。

Customer Journey Analyticsへの完全な移行が完了したら、Analytics ソースコネクタをオフにして、Experience Platform Web SDK のみを使用できます。

### 推奨アップグレードプロセスの概要

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

### 推奨されるアップグレード手順の詳細

次の手順では、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるプロセスの概要を説明します。

各手順では、より詳細なプロセスの概要を説明します。 各手順のリンクに従って、関連するタスクを完了してから、このページに戻ってプロセスの次の手順に進みます。

1. [XDM スキーマアーキテクチャの計画 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [Adobe Experience Platformで目的のカスタムスキーマを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   スキーマを作成する際は、次のオプションを考慮してください。

   * Customer Journey Analyticsを RTCDP と統合する場合は、[Customer Journey Analyticsで使用する XDM スキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) に記載されているように、スキーマで **[!UICONTROL プロファイル]** オプションを有効にする必要があります。 このオプションを有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータがリアルタイム顧客プロファイルと結合されます。

   * ストリーミングメディアデータを含める場合は、[ ストリーミングデータを取り込んで使用するようにスキーマを設定する ](/help/data-ingestion/streaming.md) 必要があります。

1. [Adobe Experience Platformでデータセットを作成する ](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. （任意）Adobe Analyticsの分類データを使用する場合、Customer Journey Analyticsのデータセットに分類データを追加できます。

   これを行うには、[ 分類データを含んだ各ディメンションのルックアップデータセットを作成する ](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) を参照してください。

1. AppMeasurementまたはAdobe Analytics拡張機能（タグ）を使用した Analytics 実装の場合は、[Adobe Experience Platformでデータストリームを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Web SDK を使用したAdobe Analytics実装の場合、データストリームは既に存在しています。

1. [ データストリームにAdobe Experience Platformをサービスとして追加します ](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. （オプション）パーソナライゼーションをAdobe Journey Optimizerと統合する場合は、Adobe Journey Optimizerで使用するCustomer Journey Analytics内のパーソナライゼーションオブジェクトを使用します。

1. （任意） Analytics ソースコネクタを使用して、Adobe Analyticsから履歴データを取り込みます。

   1. [Analytics ソースコネクタのスキーマを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   1. [Analytics ソースコネクタの作成とフィールドのマッピング ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   1. [ 接続への Analytics ソースコネクタデータセットの追加 ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. Customer Journey Analytics実装用のExperience Platform Web SDK の実装方法を説明するセクションを展開し、関連する手順を実行します。

   +++手動実装（JS ファイル）

   1. [alloy.js をサイトに追加 ](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22) します。

   1. XDM オブジェクトにデータを入力し、データストリームに送信します。

+++

   +++タグ

   1. [ サイトにローダータグを実装します ](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)。

   1. [ タグプロパティを作成して、Adobe Experience Platform Web SDK 拡張機能を追加します ](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)。

   1. [ タグに XDM データ収集ロジックを追加します ](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)。

+++

+++ API

   1. Edge NetworkAPI を使用して、目的のデータストリームにデータを送信します。

+++

1. Web SDK 実装がデータセットにデータを送信していることを検証します。

1. [Customer Journey Analyticsで接続を作成します ](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)。

1. （任意） web データを、コールセンターデータなどの他のチャネルのデータと結び付けます。

   これを行うには、Customer Journey Analytics接続にデータセットを追加します。

1. [Customer Journey Analyticsでデータビューを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

1. [ データがCustomer Journey Analyticsに送られていることを検証します ](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)。

1. [ プロジェクトとコンポーネントを移行する ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

1. （任意）Adobe Analyticsでマーケティングチャネルを使用する場合は、[Customer Journey Analyticsでマーケティングチャネル派生フィールドを作成 ](/help/data-views/derived-fields/derived-fields.md#marketing-channels) できます。

   派生フィールドは、Customer Journey Analyticsにおけるリアルタイムレポートの重要な側面になります。 派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。

   派生フィールドの使用方法の 1 つは、1 つ以上の条件（URL パラメーター、ページ URL、ページ名など）に基づいて適切なマーケティングチャネルを決定する派生マーケティングチャネルフィールドを定義することです。

   派生フィールドで [ マーケティングチャネル機能テンプレート ](/help/data-views/derived-fields/derived-fields.md#marketing-channels) を使用して、マーケティングチャネルの派生フィールドをすばやく作成します。

1. 古い実装のデータと新しい実装のデータを比較し、違いとその理由を理解していることを確認します。

1. [Customer Journey Analyticsでの機能サポート ](/help/getting-started/aa-vs-cja/cja-aa.md) について説明します。 Adobe Analyticsのほとんどの機能はCustomer Journey Analyticsでサポートされており、その他の多くの機能はCustomer Journey Analyticsで利用できます。

1. ユーザーのオンボーディングを計画します。

   Adobe Analytics と同様、Analysis Workspace は Customer Journey Analytics の主なユーザー向けツールです。ただし、Customer Journey Analytics で Analysis Workspace を使用する際は、ユーザーが認識しておく必要がある主な違いがいくつかあります。

   Customer Journey Analytics の Analysis Workspace の主な違いを理解できるよう、十分な時間（3～6 か月）をユーザーに与える必要があります。

   Adobe Analytics と Customer Journey Analytics の主な違いについて詳しくは、[Adobe Analytics ユーザー向けユーザーガイド](/help/getting-started/aa-to-cja-user.md)を参照してください。

1. AppMeasurementデータ収集を無効にします。

1. Analytics ソースコネクタを無効にします。

   Experience Platform Web SDK の実装では、Analytics ソースコネクタは、Adobe Analyticsの履歴データに対してのみ必要であり、元の実装のデータを新しい実装のデータと比較するために必要です。

   新しい実装から十分な履歴データを入手し、Customer Journey Analyticsのレポートの違いに精通したら、Analytics ソースコネクタをオフにする必要があります。

## 組織に合わせたアップグレード手順の動的な生成

タイムラインやリソースの制約などのいくつかの要因によっては、「[ 推奨されるアップグレード手順について ](#1-understand-the-recommended-upgrade-steps) で説明されている推奨アップグレード手順が組織にとって実用的でない場合があります。

組織固有の状況に合わせてアップグレード手順を動的に生成するには：

1. [Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) に回答してください。

   このアンケートに回答すると、組織の要件に固有の最適なアップグレード手順の概要が段階的に説明されます。 これらは、既存のAdobe Analytics環境およびCustomer Journey Analyticsの目標に最も適したアップグレード手順です。

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
