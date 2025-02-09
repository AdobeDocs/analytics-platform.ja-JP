---
title: Adobe Analyticsの実装と、Customer Journey Analyticsへのアップグレードに与える影響について説明します
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 11%

---

# Adobe Analyticsの実装と、Customer Journey Analyticsへのアップグレードに与える影響について説明します {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement（手動 JS ファイル）"
>abstract="AppMeasurement.js をページに読み込み、s オブジェクトを使用してデータをAdobeeVarに送信するJavaScript実装（例：s.data1）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics拡張機能（タグ）"
>abstract="Adobe Experience Platform Data Collection （旧称 Launch）を読み込むタグ実装。 タグにはAdobe Analytics拡張機能がインストールされています。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK（alloy.js）"
>abstract="Web SDK ライブラリ（alloy.js）をページに読み込み、JSON ペイロードを使用してデータをAdobeに送信するJavaScript実装。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK拡張機能（タグ）"
>abstract="Adobe Experience Platform Data Collection （旧称 Launch）を読み込むタグ実装。 タグには Web SDK拡張機能がインストールされています。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="データ挿入 API"
>abstract="データ挿入 API または一括データ挿入 API を使用する実装。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="Adobe Experience Platform Mobile SDKを使用する実装。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="不明な実装"
>abstract="実装を管理していない場合は、このオプションを一時的に選択できます。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics アップグレード チェックリスト ](https://gigazelle.github.io/cja-ttv/) の質問に答える際は、このページの情報を使用してください。

Adobe Analyticsの実装方法は様々です。 Customer Journey Analyticsにアップグレードする場合、すべてのAdobe Analytics実装ですべてのアップグレードパスを使用できるわけではありません。 ただし、組織でのAdobe Analyticsの実装方法に関係なく、推奨されるアップグレードパスを利用できます。

以下の情報を使用して、現在のAdobe Analyticsの実装と、組織で使用可能なアップグレードパスを確認します。

具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

| 既存の Adobe Analytics の実装 | 説明 | 使用可能なアップグレードパス |
|---------|----------|----------|
| AppMeasurement | これまで、JavaScriptのAppMeasurementは、Adobe Analyticsを実装する一般的な方法でした。<p>この実装タイプについて詳しくは、[JavaScriptのAppMeasurementを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Web SDK への Adobe Analytics の移行</li><li>[Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics拡張機能（タグ） | <p>Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。</p><p>この実装タイプについて詳しくは、[Analytics 拡張機能を使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Web SDK への Adobe Analytics の移行</li><li>[Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK（alloy.js） | Experience Platform web SDKは、Adobeが現在Adobe Analyticsを実装する際に推奨している方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Edge Networkを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| Experience Platform Web SDK拡張機能（タグ） | Experience Platform Web SDKは、Adobeが現在、web データにAdobe Analyticsを実装する際にお勧めする方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Web SDKを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md)</li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| Experience Platform Mobile SDK | Experience Platform モバイルSDKは、モバイルデータ用にAdobe Analyticsを実装するAdobeが現在推奨する方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。<p>Adobe Experience Platform Mobile SDKは、モバイルアプリにおけるAdobeのExperience Cloudソリューションおよびサービスを強化するのに役立ちます。 </p><p>この実装タイプについて詳しくは、[Adobe Experience Platform Mobile SDKを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| 一括データ挿入 API | Bulk Data Insertion API （BDIA）は、Adobe Analyticsの機能で、AppMeasurementなどのクライアントサイドライブラリを使用する代わりに、多数のファイルからなるサーバーコールデータをアップロードできるものです。 </p><p>この実装タイプについて詳しくは、[Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Networkサーバーの API とEdge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
