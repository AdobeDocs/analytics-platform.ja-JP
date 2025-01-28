---
title: サードパーティの分析ソリューションからCustomer Journey Analyticsへのアップグレード
description: サードパーティの分析ソリューションからCustomer Journey Analyticsにアップグレードする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 12%

---

# サードパーティの分析ソリューションからCustomer Journey Analyticsへのアップグレード {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="サードパーティの分析製品"
>abstract="Google Analyticsなどのサードパーティの分析製品のデータを収集する実装。 このオプションを選択すると、アンケートの一部のオプションが無効になり、サードパーティの Analytics 製品からCustomer Journey Analyticsにアップグレードする際には適用されません。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics アップグレード チェックリスト ](https://gigazelle.github.io/cja-ttv/) の質問に答える際は、このページの情報を使用してください。

サードパーティの分析ソリューションからCustomer Journey Analyticsにアップグレードする場合は、Experience Platform Web SDKの新しい実装を使用することをお勧めします。これは、Customer Journey Analyticsで推奨されるデータ収集方法です。 Adobeでは、Web SDKと併せて、履歴データをサードパーティの分析ソリューションからAdobe Experience Platformに取り込むこともお勧めします。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

サードパーティの分析ソリューション（Google Analyticsなど）からCustomer Journey Analyticsに移行する場合は、次の手順を実行します。

1. ：


具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

| 既存の分析ソリューション | 説明 | 使用可能なアップグレードパス |
|---------|----------|----------|
| AppMeasurement | これまで、JavaScriptのAppMeasurementは、Adobe Analyticsを実装する一般的な方法でした。<p>この実装タイプについて詳しくは、[JavaScriptのAppMeasurementを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Web SDK への Adobe Analytics の移行</li><li>[Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics拡張機能（タグ） | <p>Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。</p><p>この実装タイプについて詳しくは、[Analytics 拡張機能を使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Web SDK への Adobe Analytics の移行</li><li>[Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK（alloy.js） | Experience Platform web SDKは、Adobeが現在Adobe Analyticsを実装する際に推奨している方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Edge Networkを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| Experience Platform Web SDK拡張機能（タグ） | Experience Platform Web SDKは、Adobeが現在、web データにAdobe Analyticsを実装する際にお勧めする方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Web SDKを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md)</li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| Experience Platform Mobile SDK | Experience Platform モバイルSDKは、モバイルデータ用にAdobe Analyticsを実装するAdobeが現在推奨する方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。<p>Adobe Experience Platform Mobile SDKは、モバイルアプリにおけるAdobeのExperience Cloudソリューションおよびサービスを強化するのに役立ちます。 </p><p>この実装タイプについて詳しくは、[Adobe Experience Platform Mobile SDKを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| 一括データ挿入 API | Bulk Data Insertion API （BDIA）は、Adobe Analyticsの機能で、AppMeasurementなどのクライアントサイドライブラリを使用する代わりに、多数のファイルからなるサーバーコールデータをアップロードできるものです。 </p><p>この実装タイプについて詳しくは、[Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Networkサーバーの API とEdge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}