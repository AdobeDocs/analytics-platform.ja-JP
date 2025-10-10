---
title: Adobe Analytics から Customer Journey Analytics へのアップグレード
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨される手順について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 105b235c1a4791fd59cf65ae7f543a5fc08fc55d
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 99%

---

# Adobe Analytics から Customer Journey Analytics へのアップグレード

Adobe Analytics から Customer Journey Analytics にアップグレードする際は、[推奨されるアップグレード手順](#recommended-upgrade-steps-for-most-organizations)に従ってください。または、組織の一意の状況に合わせて[アップグレード手順を動的に生成](#dynamically-generate-upgrade-steps-for-your-organization)することもできます。

## ほとんどの組織に推奨されるアップグレード手順 {#upgrade-process}

Adobe Analytics から Customer Journey Analytics へのアップグレードでは、Customer Journey Analytics の推奨データ収集方法である Experience Platform Web SDK を新しく実装することをお勧めします。アドビでは、Web SDK と組み合わせて、Customer Journey Analytics への移行に役立てるために Analytics ソースコネクタを使用することもお勧めします。Analytics ソースコネクタを使用して、Adobe Analytics の履歴データを保持し、データを並べて比較します。

Experience Platform Web SDK を使用して十分な履歴データを取得し、Customer Journey Analytics に完全に移行したら、Analytics ソースコネクタをオフにして、Web SDK のみを使用できます。

>[!NOTE]
>
>この節で説明するアップグレード手順が組織にとって実用的でない場合は、Customer Journey Analytics アップグレードガイドを使用して、組織の一意の状況に合わせて調整されたアップグレード手順を動的に生成します。（Customer Journey Analytics からガイドにアクセスするには、「**[!UICONTROL Workspace]**」タブを選択し、左側のパネルで「**[!UICONTROL Customer Journey Analytics にアップグレード]**」を選択します。画面の指示に従います。）

### 高レベルの推奨アップグレードプロセス {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Adobe Analytics からの履歴データ"
>abstract="Adobe Analytics レポートスイートの履歴データを Adobe Experience Platform および Customer Journey Analytics に取り込む。"

<!-- markdownlint-enable MD034 -->

1. **Experience Platform Web SDK を実装（継続的なデータ収集用）**

   Experience Platform Web SDK の新しい実装は、Customer Journey Analytics のデータを収集する最適な方法です。これは、Customer Journey Analytics を実装するための最高のパフォーマンスで、簡単で、将来性も備えた方法であるので、Customer Journey Analytics を最大限に活用するための最適な基盤を提供します。

   * Adobe Experience Platform は、リアルタイムパーソナライゼーションのユースケースを強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する

   * 他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する

   * Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない

1. **Adobe Analytics ソースコネクタを設定（履歴データの取り込み用）**

   Customer Journey Analytics での Experience Platform Web SDK の使用へのスムーズな移行に役立てるために、アドビでは Adobe Analytics ソースコネクタの使用もお勧めします。これにより、履歴データを保持し、Customer Journey Analytics の既存の Adobe Analytics 実装のデータを、新しい Experience Platform Web SDK 実装のデータと並べて表示できます。

   Analytics ソースコネクタを使用すると、次の操作を実行できます。

   * Adobe Analytics レポートスイートの履歴データを Adobe Experience Platform および Customer Journey Analytics に取り込む。

     Adobe Analytics の履歴データを保持する必要がある限り、Analytics ソースコネクタを引き続き実行できます。

   * Customer Journey Analytics 内で、元の Adobe Analytics 実装（AppMeasurement、Analytics 拡張機能または Web SDK 拡張機能のいずれか）で収集されたデータを表示する。このデータを新しい Web SDK 実装のデータと並べて比較できます。

     違いを理解して慣れるまで、Analytics ソースコネクタを引き続き実行できます。<!--elaborate on what those differences are? -->

   スタンドアロン実装としての Analytics ソースコネクタは、Customer Journey Analytics を長期的に使用するための推奨される方法ではありません。これは、待ち時間が長く、スキーマが乱雑で複雑であり、Adobe Analytics の命名法（prop、eVar など）に依存しており、最終的に Analytics ソースコネクタから推奨される Web SDK 実装に移行するのが難しいからです。

### 推奨されるアップグレード手順の詳細

次の手順では、Adobe Analytics から Customer Journey Analytics へのアップグレードに推奨されるプロセスの概要について説明します。

各手順では、より詳細なプロセスの概要について説明します。各手順のリンクに従って関連するタスクを完了してから、このページに戻り、プロセスの次の手順に進みます。

1. [XDM スキーマアーキテクチャを計画します](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}。

1. [Adobe Experience Platform で目的のカスタムスキーマを作成します](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}。

   スキーマを作成する際は、次のオプションを考慮してください。

   * Customer Journey Analytics を RTCDP と統合する場合は、[Customer Journey Analytics で使用する XDM スキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}の説明に従って、スキーマで「**[!UICONTROL プロファイル]**」オプションを有効にする必要があります。 このオプションを有効にすると、このスキーマに基づくデータセットにデータが取り込まれたときに、そのデータがリアルタイム顧客プロファイルと結合されます。

   * ストリーミングメディアデータを含める場合は、[ストリーミングデータを取り込んで使用するスキーマを設定](/help/data-ingestion/streaming.md){target="_blank"}する必要があります。

1. [Adobe Experience Platform でデータセットを作成します](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md){target="_blank"}。

1. （オプション）Adobe Analytics で分類データを使用する場合は、Customer Journey Analytics のデータセットに分類データを追加できます。

   これを行うには、[分類データを含む各ディメンションのルックアップデータセットを作成します](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md){target="_blank"}。

1. AppMeasurement または Analytics 拡張機能（タグ）を使用した Adobe Analytics 実装の場合は、[Adobe Experience Platform でデータストリームを作成します](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md){target="_blank"}。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Web SDK を使用した Adobe Analytics 実装の場合、データストリームは既に存在しています。詳しくは、[Platform にデータを送信する既存の Adobe Analytics Web SDK 実装の設定](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md){target="_blank"}を参照してください。

1. [Adobe Experience Platform をサービスとしてデータストリームに追加します](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md){target="_blank"}。

1. （オプション）Customer Journey Analytics を Adobe Journey Optimizer と統合する場合は、Adobe Journey Optimizer で使用する実装でパーソナライゼーションオブジェクトを使用します。

1. Customer Journey Analytics 実装に Experience Platform Web SDK を実装する方法を説明する節を展開し、関連する手順を完了します。

   +++手動実装（JS ファイル）

   1. [サイトに alloy.js を追加します](https://experienceleague.adobe.com/ja/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22){target="_blank"}。

   1. XDM オブジェクトを入力してデータストリームに送信します。

   +++

   +++タグ

   1. [タグプロパティを作成して、Adobe Experience Platform Web SDK 拡張機能を追加します](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md){target="_blank"}。

   1. [Adobe Experience Platform Web SDK拡張機能をタグプロパティに追加します &#x200B;](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md){target="_blank"}。

   1. [サイトにローダータグを実装します](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)。

   1. [タグに XDM データ収集ロジックを追加します](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md){target="_blank"}。

   +++

   +++ API

   1. Edge Network API を使用して、目的のデータストリームにデータを送信します。

   +++

1. [Web SDK 実装がデータセットにデータを送信していることを検証します](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md){target="_blank"}。

1. [Customer Journey Analytics で接続を作成します](/help/getting-started/cja-upgrade/cja-upgrade-connection.md){target="_blank"}。

1. （オプション）Web データをコールセンターデータなどの他のチャネルのデータと結び付けます。

   これを行うには、[コールセンターデータと web データの読み込み](/help/use-cases/cross-channel/call-center.md){target="_blank"}の説明に従って、Customer Journey Analytics 接続に追加のデータセットを追加します。

1. [Customer Journey Analytics でデータビューを作成します](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md){target="_blank"}。

1. [Customer Journey Analytics でデータビューへのデータのフローを検証します](/help/getting-started/cja-upgrade/cja-upgrade-validate.md){target="_blank"}。

1. Adobe Analytics 環境では、[Analytics インベントリを使用](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/analytics-inventory){target="_blank"}して、プロジェクトとコンポーネント、レポートスイート、ユーザーの数など、Adobe Analytics 環境の包括的な概要を確認します。

1. [プロジェクトとコンポーネントを移行します](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration){target="_blank"}。

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. （オプション）Adobe Analytics でマーケティングチャネルを使用する場合は、[Customer Journey Analytics でマーケティングチャネル派生フィールドを作成](/help/data-views/derived-fields/derived-fields.md#marketing-channels){target="_blank"}できます。

   派生フィールドは、Customer Journey Analytics のリアルタイムレポートの重要な側面です。派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。

   派生フィールドの 1 つの用途は、1 つ以上の条件（URL パラメーター、ページ URL、ページ名など）に基づいて適切なマーケティングチャネルを決定する派生マーケティングチャネルフィールドを定義することです。

   派生フィールドの[マーケティングチャネル機能テンプレート](/help/data-views/derived-fields/derived-fields.md#marketing-channels){target="_blank"}を使用して、マーケティングチャネルの派生フィールドをすばやく作成します。

1. 古い実装の Adobe Analytics のデータと新しい実装の Customer Journey Analytics のデータを比較し、違いとその理由を理解します。<!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Analytics ソースコネクタを使用して、Adobe Analytics から履歴データを取り込みます。

   >[!NOTE]
   >
   >以前に Analytics ソースコネクタを作成していない場合は、次の手順に従います。
   >
   >Customer Journey Analytics で Analytics ソースコネクタを既に使用している場合は、[Analytics ソースコネクタから Customer Journey Analytics の Web SDK への移行](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md){target="_blank"}の手順に従ってください。

   1. [Analytics ソースコネクタの XDM スキーマを作成します](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md){target="_blank"}。

   1. Analytics ソースコネクタがまだない場合は、[Analytics ソースコネクタを作成し、フィールドを XDM スキーマにマッピングします](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md){target="_blank"}。

      または

      Analytics ソースコネクタが既にある場合は、[ソースコネクタのフィールドを XDM スキーマにマッピングします](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md){target="_blank"}。

   1. [Analytics ソースコネクタデータセットを接続に追加します](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md){target="_blank"}。

1. ユーザーオンボーディングを計画します。

   Adobe Analytics と同様、Analysis Workspace は Customer Journey Analytics の主なユーザー向けツールです。ただし、Customer Journey Analytics で Analysis Workspace を使用する際は、ユーザーが認識しておく必要がある主な違いがいくつかあります。

   Customer Journey Analytics の Analysis Workspace の主な違いを理解できるよう、十分な時間（3～6 か月）をユーザーに与える必要があります。

   Adobe Analytics と Customer Journey Analytics の主な違いについて詳しくは、[Adobe Analytics ユーザー向けユーザーガイド](/help/getting-started/aa-to-cja-user.md){target="_blank"}を参照してください。

1. [Customer Journey Analytics の機能サポート](/help/getting-started/aa-vs-cja/cja-aa.md){target="_blank"}について学びます。Adobe Analytics のほとんどの機能は Customer Journey Analytics でサポートされており、多くの追加機能が Customer Journey Analytics で使用できます。

1. Customer Journey Analytics Web SDK の実装が完了し、収集するデータに問題がなければ、Adobe Analytics を無効にします。

   アドビでは、Customer Journey Analytics を実装した後、一定期間 Adobe Analytics 環境を実行したままにしておくことをお勧めします。

   アップグレード中およびアップグレード後の Adobe Analytics の使用方法と、Adobe Analytics を無効にする推奨されるタイミングについて詳しくは、[Customer Journey Analytics へのアップグレード後に Adobe Analytics が必要な期間の評価](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md){target="_blank"}を参照してください。

## 組織に合わせたアップグレード手順の動的な生成

タイムラインやリソースの制約などのいくつかの要因によっては、[推奨されるアップグレード手順について](#recommended-upgrade-steps-for-most-organizations)で説明されている推奨されるアップグレード手順が組織にとって実用的ではない可能性があります。この場合、組織の一意の状況に合わせてアップグレード手順を動的に生成できます。これらの手順を生成するプロセスは、既に Customer Journey Analytics へのアクセス権を持っているかどうかによって異なります。

### Customer Journey Analytics へのアクセス権を持っているお客様の場合

組織の一意の状況に合わせてアップグレード手順を動的に生成するには：

1. Customer Journey Analytics アップグレードガイドを完了します。

   Customer Journey Analytics で、「**[!UICONTROL Workspace]**」タブを選択し、左側のパネルで「**[!UICONTROL Customer Journey Analytics にアップグレード]**」を選択します。画面の指示に従います。

   このアップグレードガイドを完了すると、組織の要件に一意の最適なアップグレード手順の概要が段階的に説明されます。これらは、既存の Adobe Analytics 環境と Customer Journey Analytics の目標に最も適合するアップグレード手順です。アップグレード手順は、共有可能なリンクまたはダウンロード可能な .csv ファイルとして使用できます。

1. 生成された段階的な手順に従って、Customer Journey Analytics にアップグレードします。

### Customer Journey Analytics へのアクセス権をまだ持っていないお客様の場合

組織の一意の状況に合わせてアップグレード手順を動的に生成するには：

1. Customer Journey Analytics アップグレードガイドを完了するには、アドビのアカウントチームにお問い合わせください。

   アドビのアカウントチームがアップグレードガイドを案内し、質問、回答、組織に一意の動的に生成されたアップグレード手順を含む .csv ファイルを提供する場合があります。

   アドビのアカウントチームに問い合わせる前に、Customer Journey Analytics アップグレードガイドに含まれる質問をよく理解し、回答を決定しておいてください。Customer Journey Analytics アップグレードガイドには、次の質問と考えられる回答が含まれています。


   | 質問 | 使用可能な回答 | 追加情報 |
   |---------|----------|---------|
   | 現在の Adobe Analytics 実装を説明するオプションを選択します。この情報は、Customer Journey Analytics へのアップグレード時に利用できる、代替アップグレードオプションに影響する可能性があります。 | 1 つ選択してください： <ul><li>**AppMeasurement：**<br/> AppMeasurement.js をページに読み込み、s オブジェクト（例：s.eVar1）を使用して、データをアドビに送信する JavaScript 実装。</li><li>**Adobe Analytics 拡張機能（タグ）：**<br/>Adobe Experience Platform データ収集（旧称 Launch）を読み込むタグ実装。タグには Adobe Analytics 拡張機能がインストールされています。</li><li>**Experience Platform Web SDK 拡張機能（タグ）：**<br/> Adobe Experience Platform データ収集（旧称 Launch）を読み込むタグ実装。タグには Web SDK 拡張機能がインストールされています。</li><li>**Experience Platform Web SDK（alloy.js）：** Web SDK ライブラリ（alloy.js）をページに読み込み、JSON ペイロードを使用してデータをアドビに送信する JavaScript 実装。</li><li>**Bulk Data Insertion API：**<br/> Data Insertion API または Bulk Data Insertion API を使用する実装。</li><li>**Experience Platform Mobile SDK：**<br/> Adobe Experience Platform Mobile SDK を使用する実装。</li><li>**サードパーティのタグ管理ツールを使用する AppMeasurement：**<br/>&#x200B;サードパーティのタグ管理ツールを使用する実装。</li><li>**Adobe Analytics 以外の製品：**<br/> Google Analytics など、Adobe Analytics 以外の製品のデータを収集する実装。このオプションを選択すると、Adobe Analytics 以外の製品から Customer Journey Analytics にアップグレードする際に適用されない、アップグレードガイドのいくつかのオプションが無効になります。 </li><li>**わからない：**<br/>&#x200B;実装を管理するユーザーでない場合は、このオプションを一時的に選択できます。</li></ul><p>該当する場合は選択してください：<ul><li>**現在、実装では Analytics ソースコネクタを使用：**<br/> Analytics ソースコネクタを使用すると、Customer Journey Analytics から簡単に価値を得ることができますが、Adobe Analytics と Customer Journey Analytics の両方に対して料金を支払う必要があります。このガイドは、独立した Web SDK の実装に移行するのに役立ちます。</li></ul></p> | <ul><li>[Adobe Analytics の実装と、Customer Journey Analytics へのアップグレードに与える影響について](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Analytics ソースコネクタから Customer Journey Analytics 向け Web SDK への移行](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | Adobe Analytics のほとんどの機能は、Customer Journey Analytics ですぐに利用できます。ただし、次の機能はアップグレードプロセス中に考慮する必要があります。使用する予定の機能を選択してください。 | 該当項目をすべて選択：<ul><li>**Adobe Analytics の履歴データ：**</br> Adobe Analytics レポートスイートの履歴データを Adobe Experience Platform および Customer Journey Analytics に取り込む。</li><li>**Adobe Analytics のコンポーネントとプロジェクト：**</br> Adobe Analytics のコンポーネントには、プロジェクト（関連付けられたフリーフォームテーブルとビジュアライゼーションを含む）、セグメント、計算指標が含まれます。</li><li>**アクティビティマップのオーバーレイとリンクトラッキング：**</br>&#x200B;リンクトラッキングデータをサイト上のオーバーレイとして表示できるブラウザー拡張機能。</li><li>**分類データ：**</br>&#x200B;データを個別のディメンションとしてグループ化または分類します。</li><li>**マーケティングチャネル：**</br>&#x200B;顧客がサイトに到達する方法を分類するルールを作成します。</li><li>**Data Warehouse：**</br> Adobe Analytics から処理済みデータをスプレッドシート形式で書き出します。</li><li>**データフィード：**&#x200B;データフィードの完全な代替機能は、Customer Journey Analytics ではまだ利用できません。ただし、完全なテーブルの書き出し、Platform データセットの書き出し、BI ツールの統合、レポート API などの機能を使用すると、同様の機能を実現できます。</br></li><li>**ストリーミングメディアデータ：**</br>&#x200B;オーディオ、ビデオ、ストリーミングコンテンツなどのメディアのデータ収集を専門とする Adobe Analytics と Customer Journey Analytics のアドオンです。</li></ul> | <ul><li>[Customer Journey Analytics にアップグレードする際の Adobe Analytics 機能のサポートについて](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | ほとんどの新機能は、Customer Journey Analytics ですぐに利用できます。ただし、次の機能はアップグレードプロセス中に考慮する必要があります。使用する予定の機能を選択してください。 | 該当項目をすべて選択：<ul><li>**収集したデータを他のソースのデータ（コンタクトセンターのデータなど）と結び付ける：**</br>（推奨）様々な web、モバイル、オフラインのプロパティからのデータを結び付けて、顧客行動の 1 つの統合ビューを作成します。他のチャネルからの分析データを組み合わせる機能は、Customer Journey Analytics の主なユースケースです。</li><li>**カスタムディメンションを使用して他のデータセットからのヒットをステッチする：**<br/>&#x200B;データセットのいずれかがプライマリ識別子（Experience Cloud ID など）を共有しない場合でも、ログインユーザー名やメールアドレスなど、別のディメンションを使用して、そのデータを結び付けることができます。</li><li>**Adobe Journey Optimizer と統合する：**<br/>&#x200B;お客様に接続され、コンテキストに応じて、パーソナライズされたエクスペリエンスを提供します。</li><li>**Adobe Real-Time CDP と統合する：**<br/>&#x200B;複数のソースからのプロファイルデータを組み合わせて、ユーザー特性に基づいてオーディエンスとセグメントを生成します。</li><li>**Adobe Target（A4T）と統合する：**<br/>&#x200B;アドビでは、パーソナライゼーションのユースケースに対して Adobe Journey Optimizer との統合をお勧めします。Adobe Target との統合は可能ですが、短期的な解決策です。</li><li>**Adobe Audience Manager と統合する：**<br/>&#x200B;アドビでは、オーディエンスベースのユースケースに対して Adobe Real-time CDP との統合をお勧めします。Audience Manager との統合は可能ですが、短期的な解決策です。</li></ul> | [Customer Journey Analytics 固有の機能について](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Adobe Analytics と Customer Journey Analytics を最終的にどのように使用する予定かを選択します。 | 1 つ選択してください： <ul><li>**Adobe Analytics から Customer Journey Analytics に完全に移行するつもりです：**<br/>（推奨）アドビでは、Adobe Analytics から Customer Journey Analytics に完全に移行することをお勧めします。移行期間中は、データを横に並べて比較するために、Adobe Analytics を Customer Journey Analytics と共に実行するよう計画する必要があります。データに問題がなければ、Adobe Analytics を無効にできます。</li><li>**両方の Analytics 製品を維持するつもりです：**<br/>（非推奨）このオプションを選択する場合、アドビとの契約には Adobe Analytics と Adobe Customer Journey Analytics の両方が含まれるので、時がたつにつれて組織にとってよりコストが高くなる可能性があります。</li></ul> | [Customer Journey Analytics へのアップグレード後、Adobe Analytics を無効にするタイミングの評価](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Customer Journey Analytics スキーマを設定する方法を選択します。 | 1 つ選択してください： <ul><li>**組織に合わせたスキーマを使用したい：**</br>（推奨）スキーマをカスタマイズすると、組織は必要なもののみを追跡でき、乱雑で不要なフィールドに関連付けられたオーバーヘッドを回避できます。このオプションには、Web SDK によって追加されたフィールドグループと、組織にカスタムのフィールドグループが含まれます。</li><li>**デフォルトの Adobe Analytics スキーマを使用したい：**</br>（非推奨）Adobe Analytics スキーマには 1,000 を超えるフィールドが含まれており、スキーマが乱雑で複雑になる場合があります。組織は、Customer Journey Analytics では使用されていない従来の概念である prop と eVar の概念に引き続き従わざるを得なくなります。 他の Adobe Experience Platform サービスとの統合はより困難です。</li></ul> | [Customer Journey Analytics のスキーマを選択](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Customer Journey Analytics を実装する方法を選択します。 | <ul><li>**手動による実装（alloy.js）：**<br/>&#x200B;サイトの各ページに Web SDK ライブラリ（alloy.js）を含めます。</li><li>**タグ：**<br/>（推奨）タグをまだ使用していない場合は、サイトにタグローダーをインストールします。既にタグを使用している場合は、タグプロパティに web SDK 拡張機能を追加できます。このオプションには、Adobe Experience Platform Data Collection およびサードパーティのタグ管理システム内のタグを使用した実装が含まれます。</li><li>**API：**<br/> Data Collection API を使用して、データをデータストリームに直接送信します。認証されていない（クライアントからサーバー）タイプと、認証されている（サーバーからサーバー）タイプの両方がサポートされています。</li></ul> | [Customer Journey Analytics にアップグレードする際の Web SDK 実装オプションについて](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | （オプション）別のアップグレード方法を選択します。 | <ul><li>**Analytics ソースコネクタのみを使用する：**<br/>（非推奨）Analytics ソースコネクタを Customer Journey Analytics の唯一の実装パスとして使用できます。<p>このオプションを使用すると、Customer Journey Analytics にデータをすばやく送信できるので、実装時間が節約されます。ただし、待ち時間が長い、今後 Adobe Analytics から移行するのが難しいなど、様々な欠点があります。</p></li><li>**WebSDK で AppMeasurement ロジックを使用したい：**<br/> XDM オブジェクトを通じてデータを送信する代わりに、すべての変数を AppMeasurement 形式でデータオブジェクトを通じて送信します。<p>このオプションを使用すると、XDM オブジェクトをゼロから入力するのではなく、AppMeasurement ロジックを XDM にマッピングできるので、実装時間が節約されます。ただし、今後追加するフィールドはデータストリームの XDM にマッピングする必要があるので、時間の経過と共に複雑さが増します。</p></li><li>**追加の設定なしでアドビにデータレイヤーを送信したい：**<br/> XDM オブジェクトを通じてデータを送信する代わりに、データオブジェクトを通じてデータレイヤー全体をアドビに送信できます。<p>このオプションを使用すると、XDM オブジェクトをゼロから入力するのではなく、データレイヤーを XDM にマッピングできるので、実装時間が節約されます。ただし、アドビではすぐに解釈できないデータが大量に存在するので、このマッピングは膨大な作業となります。また、このオプションでは、今後データに追加するフィールドはデータストリームの XDM にマッピングする必要があるので、時間の経過と共に複雑さが増します。</p></li></ul> | <ul><li>[アップグレードの代替案：Analytics ソースコネクタのみを使用した Customer Journey Analytics へのアップグレード](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[アップグレードの代替案：Experience Platform Web SDK と Customer Journey Analytics での AppMeasurement データ収集の使用](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[アップグレードの代替案：Customer Journey Analytics へのデータレイヤーの送信](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   アドビのアカウントチームと共にこのアップグレードガイドを完了すると、質問、回答、既存の Adobe Analytics 環境と Customer Journey Analytics の目標に最適な、動的に生成されたアップグレード手順を含む .csv ファイルが提供されます。

1. .csv ファイルに生成された段階的な手順に従って、Customer Journey Analytics にアップグレードします。

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
