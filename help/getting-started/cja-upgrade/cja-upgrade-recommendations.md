---
title: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時にお勧めのパス
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 8%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードプロセスを開始する前に、まず推奨されるアップグレード手順を理解します。

>[!NOTE]
>
>この節で説明するアップグレード手順は、Adobe AnalyticsからCustomer Journey Analyticsに正常にアップグレードするために組織で使用できる推奨アップグレード手順です。
>
>ただし、タイムラインやリソースの制約などのいくつかの要因によっては、推奨されるアップグレード手順が組織にとって実用的でない場合があります。 その場合は、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) を使用して、組織固有の状況に合わせたアップグレード手順を動的に生成します。

## 大部分の組織で推奨されるアップグレード手順

Adobe AnalyticsからCustomer Journey Analyticsにアップグレードする際の推奨手順は、Customer Journey Analyticsで推奨されるデータ収集方法であるExperience Platform Web SDK の新しい実装です。 Adobeでは、Web SDK と組み合わせて、Analytics ソースコネクタを使用して、Adobe Analyticsの履歴データを保持し、並列データ比較を実行することをお勧めします。

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

次の手順は、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードにお勧めのプロセスを示しています。

組織の固有の環境と要件によっては、これらの推奨手順が組織に適さない場合があります。 その場合は、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) を使用して、組織固有の状況に合わせたアップグレード手順を動的に生成します。

1. [XDM スキーマアーキテクチャの計画 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [Adobe Experience Platformで目的のカスタムスキーマを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

1. [Adobe Experience Platformでデータセットを作成する ](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. 現在のAdobe Analytics実装を説明するセクションを展開し、関連する手順を実行します。

   +++AppMeasurementを使用したAdobe Analytics実装の場合

   1. [Adobe Experience Platformでデータストリームを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++Analytics 拡張機能を使用したAdobe Analytics実装の場合（タグ）

   1. [Adobe Experience Platformでデータストリームを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ Web SDK を使用したAdobe Analytics実装の場合

   追加の手順は必要ありません。

+++

1. [ データストリームにAdobe Experience Platformをサービスとして追加します ](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. 次の表を使用して、Customer Journey Analyticsで引き続き使用するAdobe Analytics機能を特定し、提供された情報を使用してCustomer Journey Analyticsへのアップグレードの一環としてそれらの機能を設定する方法を学習します。

   | Adobe Analytics機能 | Customer Journey Analyticsの実装要件 | 追加情報 |
   |---------|----------|---------|
   | 分類データ | 分類データを含む各ディメンションのルックアップデータセットを作成します。 |  |
   | マーケティングチャネル | マーケティングチャネル派生フィールドを作成します。 |  |
   | Activity Map のオーバーレイとリンクトラッキング | 該当なし | Adobeは現在、Customer Journey AnalyticsのActivity Mapオーバーレイのサポートに取り組んでいます。 |
   | データフィード | 実装時の設定は不要です。<br/>[Customer Journey Analyticsの様々な書き出しオプションについて説明します ](/help/analysis-workspace/export/export-project-overview.md)。 | データフィードに代わる直接的な機能はまだCustomer Journey Analyticsでは利用できませんが、サードパーティのツールで使用したり、外部データと組み合わせたりするためにAnalysis WorkspaceからCustomer Journey Analyticsレポートを書き出すことができます。 |
   | Data Warehouse | 実装時の設定は不要です。<br/>[Customer Journey Analyticsでの完全なテーブル書き出しについて説明します ](/help/analysis-workspace/export/export-cloud.md)。 | Customer Journey Analyticsの完全なテーブルの書き出しは、Adobe AnalyticsのData Warehouseレポートが進化したものです。現在、Data Warehouseでは利用できない、頻繁にリクエストされる多くの新機能を備えています。 |
   | ストリーミングメディアデータ |  |  |

1. （任意） Analytics ソースコネクタを使用して、Adobe Analyticsから履歴データを取り込みます。

   詳しくは、[ ソースコネクタを使用したデータの取り込みと使用 ](/help/data-ingestion/sources.md#use-a-source-connector) の [ ソースコネクタの使用 ](/help/data-ingestion/sources.md) を参照してください。

1. 次の表を使用して必要なCustomer Journey Analytics機能を特定し、Customer Journey Analyticsへのアップグレードの一環としてそれらの機能を設定する方法について説明します。

   | 必要なCustomer Journey Analytics機能 | Customer Journey Analyticsの実装要件 | 追加情報 |
   |---------|----------|---------|
   | コールセンターデータなど、他のチャネルのデータと web データを結び付ける | 接続を作成したら（後の手順で説明するように）、Customer Journey Analyticsの接続にデータセットを追加します。 |  |
   | RTCDP との統合 | スキーマ内でプロファイルを有効にし、RTCDP で使用するためのプロファイルデータセットを作成します | これは、XDM スキーマの作成時に行う必要があります。 |
   | Adobe Journey Optimizerとの統合 | Adobe Journey Optimizerで使用するための実装でのパーソナライゼーションオブジェクトの使用 |  |

1. 目的のCustomer Journey Analytics実装を説明するセクションを展開し、関連する手順を実行します。

   +++手動実装（JS ファイル）

   1. [alloy.js をサイトに追加 ](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22) します。

+++

   +++タグ

   1. [Adobe Experience Platform Data Collection でタグプロパティを作成します ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property)。

+++

+++ API

   1. Edge NetworkAPI を使用して、目的のデータストリームにデータを送信します。

+++

1. [Customer Journey Analyticsで接続を作成します ](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)。

1. [Customer Journey Analyticsでデータビューを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

1. [ データがCustomer Journey Analyticsに送られていることを検証します ](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)。

1. [ プロジェクトとコンポーネントを移行する ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

1. 古い実装のデータと新しい実装のデータを比較し、違いとその理由を理解していることを確認します。

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









