---
title: Adobe AnalyticsからCustomer Journey Analyticsへの移行
description: Adobe AnalyticsからCustomer Journey Analyticsへの移行手順
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2a330a430b48eb753d269e1165e95b61cb5fb483
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 6%

---

# Adobe AnalyticsからCustomer Journey Analyticsへの移行の準備

Adobe AnalyticsからCustomer Journey Analyticsにデータを移行する前に、以下の考慮事項を検討して、データを準備し、2 つのテクノロジー間の重要な違いを認識しておきます。

## データの準備

Customer Journey Analyticsにシームレスに移行するためにAdobe Analyticsデータを準備することは、データの整合性とレポートの整合性を保つ上で重要です。

### 1. ID の収集

おそらく、カスタマージャーニーを理解する上で最も重要な要素は、各ステップで顧客が誰であるかを把握することです。 Customer Journey Analyticsの場合、すべてのチャネルと対応するデータに存在する識別子を持つことで、CJA 内で複数のソースを結び付けることができます。
ID の例としては、顧客 ID、アカウント ID、電子メール ID などがあります。 ID（および複数の ID が存在する場合）に関係なく、各 ID に対して次の点を必ず考慮してください。

* ID が存在するか、CJA に取り込むすべてのデータソースに追加できます。
* ID はデータの各行に対して設定されます
* ID に PII が含まれていません。 機密性が高い可能性のあるすべての要素にハッシュを適用します。
* ID は、すべてのソース（同じ長さ、同じハッシュメソッドなど）で同じ形式を使用し、

Adobe Analyticsなどのデータセットでは、データのすべての行に ID が存在するわけではなく、セカンダリ ID が存在する場合があります。 この場合、クロスチャネル分析（以前の「フィールドベースのステッチ」）は、顧客が ECID でのみ識別される場合と、ID が収集される場合（例えば、顧客の認証時）との間のギャップを埋めるために使用できます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ja)

### 2.変数を揃えます。

Adobe AnalyticsのデータをCustomer Journey Analyticsに簡単に移行するには、 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja). このコネクタは、Adobe Analytics変数を AEP の XDM スキーマとデータセットに直接マッピングし、AEP では CJA に簡単に接続できます。

完全なグローバルレポートスイートは、実装が可能とは限らない場合があります。 複数のレポートスイートをCustomer Journey Analyticsに取り込む場合は、これらのレポートスイート間で変数を整合させる計画を立てる必要があります。

例えば、レポートスイート 1 の eVar1 が [!UICONTROL ページ] を指し、レポートスイート 2 では、eVar1 は [!UICONTROL 内部キャンペーン]. CJA に取り込むと、これらの変数が 1 つのeVar1 ディメンションに混在し、混乱の原因となり、不正確なレポートになる可能性があります。

の問題が原因でグローバルレポートスイートへの移行を避けた場合 [!UICONTROL ユニークが超過しました] または [!UICONTROL 低トラフィック]、CJA に [ディメンションの基数の制限](/help/components/dimensions/high-cardinality.md). これにより、任意の一意の値を表示してカウントできます。

### 3. （再）マーケティングチャネルの設定

従来のAdobe Analyticsマーケティングチャネルの設定は、CJA では同じように実行されません。 これは、次の 2 つの理由に基づいています。

* Adobe Experience Platformに取り込まれるAdobe Analyticsデータの処理レベル。

* Customer Journey Analyticsのレポート時間の特性

Adobeが公開されました [マーケティングチャネルの実装に関するベストプラクティスの更新](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). これらの更新された推奨事項は、Attribution IQを使用して既にAdobe Analyticsにある機能を最大限に活用するのに役立ちます。 また、Customer Journey Analyticsへの移行時に、成功に向けた設定もおこなわれます。

### 4. Analytics ソースコネクタとExperience PlatformSDK の使用を決定する

形式 [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) データ収集の進化に伴い、次のいずれかに移行する可能性があります。 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) または [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=en) とAdobe Experience Platform Edge Network の連携が可能です。 SDK の一般的な実装ではAdobe Analyticsにデータを送信しますが、新しいオポチュニティが自らAdobe Experience Platformに直接データを送信する機会を提供します。 その後、Adobe Analyticsに送信するデータを維持しながら、Customer Journey Analyticsに取り込むことができます。

この方法により、次のようなデータ収集の可能性が大幅に広がります。フィールドの数や、Analytics などの prop、eVar およびイベントにデータ要素をマッピングする必要性に制限はなくなりました。 CJA を使用すると、様々なタイプの無制限のスキーマ要素を使用し、複数の方法でそれらを表すことができます [データビュー](/help/data-views/data-views.md). Adobe Analyticsを介したデータ処理の時間がなくなると、Adobe Experience Platformに直接送信するとデータ可用性の速度が向上します。

**Experience PlatformSDK を使用する利点**

* 必要なフィールドを定義する柔軟なスキーマ
* Adobe Analyticsの命名 (prop、eVar、イベントなど ) に依存しない
* 文字制限に関する問題はありません（prop の場合は 100 文字）
* Adobe Experience Platformでのデータの可用性の向上

**Experience PlatformSDK を使用する際の欠点**

次のAdobe Analyticsコンポーネントはサポートされていません。

* マーケティングチャネル
* ボットフィルタリング
* 地域、ドメイン、デバイスの参照
* Analytics for Target（A4T）

## 重要な違いに対する準備

### レポート時間処理に慣れる

Adobe Analyticsのレポートは、eVar で確認できる永続性などの結果を生み出すために、大量のデータの前処理に依存しています。 Customer Journey Analyticsは、レポートの実行時にこれらの計算を実行します。

レポート時間処理を使用すると、遡及的な設定を適用し、基になるデータの収集方法を変更することなく、変数永続性の複数のバージョンを作成できます。

この変更により、特に有効期限が長い変数について、データのレポート方法に多少の違いが生じます。 まず、 [仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### 重要なセグメントと計算指標の特定

Adobe Analyticsのセグメント（CJA ではフィルターと呼ばれます）と計算指標は、Customer Journey Analyticsとは互換性がありません。 多くの場合、CJA では、使用可能な新しいスキーマとデータを使用して、これらのコンポーネントを再構築できます。

ユーザーがシステム間を移行する際に、移行をできるだけスムーズにおこなうには、次の手順で計画します。

1. これらのコンポーネントの最も重要な要素の特定

1. 定義のドキュメント化、および

1. CJA でレプリケートするためにデータに必要なフィールドの識別 [フィルター](/help/components/filters/filters-overview.md) および [計算指標](/help/components/calc-metrics/calc-metr-overview.md).

以下に、ユーザーを導くビデオをいくつか示します。

* [Adobe AnalyticsセグメントのCustomer Journey Analyticsへの移動](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [Adobe Analytics から Customer Journey Analytics への計算指標の移行](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)
