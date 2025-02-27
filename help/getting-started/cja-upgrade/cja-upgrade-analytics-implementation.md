---
title: Adobe Analytics の実装と、Customer Journey Analyticsへのアップグレードに与える影響について
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 30%

---

# Adobe Analytics の実装と、Customer Journey Analyticsへのアップグレードに与える影響について {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement（手動 JS ファイル）"
>abstract="AppMeasurement.js をページに読み込み、s オブジェクト（例：s.eVar1）を使用して、データをアドビ に送信する JavaScript 実装。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics 拡張機能（タグ）"
>abstract="Adobe Experience Platform データ収集（旧称 Launch）を読み込むタグ実装。タグには Adobe Analytics 拡張機能がインストールされています。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK（alloy.js）"
>abstract="Web SDK ライブラリ（alloy.js）をページに読み込み、JSON ペイロードを使用してデータをアドビ に送信する JavaScript 実装。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK 拡張機能（タグ）"
>abstract="Adobe Experience Platform データ収集（旧称 Launch）を読み込むタグ実装。タグには Web SDK 拡張機能がインストールされています。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="データ挿入 API"
>abstract="Data Insertion API または Bulk Data Insertion API を使用する実装。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="Adobe Experience Platform Mobile SDK を使用する実装。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="不明な実装"
>abstract="実装を管理するユーザーでない場合は、このオプションを一時的に選択できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="既存の実装タイプを決定"
>abstract="組織内で内部的に作業して、Adobe Analyticsへのデータ送信に現在使用している実装のタイプを判断します。 Customer Journey Analyticsへの移行の準備が整った時点で、この情報を把握している個人またはチームと提携する可能性が高くなります。<br><br> 組織が使用する実装のタイプを決定したら、アンケートの回答を変更します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analyticsの実装方法は様々です。 Customer Journey Analyticsにアップグレードする場合、すべてのAdobe Analytics実装ですべてのアップグレードパスを使用できるわけではありません。 ただし、組織でのAdobe Analyticsの実装方法に関係なく、推奨されるアップグレードパスを利用できます。

以下の情報を使用して、現在のAdobe Analyticsの実装と、組織で使用可能なアップグレードパスを確認します。

具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

| 既存の Adobe Analytics の実装 | 説明 | 使用可能なアップグレードパス |
|---------|----------|----------|
| AppMeasurement | これまで、JavaScript用のAppMeasurementは、Adobe Analyticsを実装する一般的な方法でした。<p>この実装タイプについて詳しくは、[JavaScript用AppMeasurementでAdobe Analyticsを実装する ](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Web SDK への Adobe Analytics の移行</li><li>[Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics拡張機能（タグ） | <p>Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。</p><p>この実装タイプについて詳しくは、[Analytics 拡張機能を使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Web SDK への Adobe Analytics の移行</li><li>[Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK（alloy.js） | Experience Platform Web SDKは、Adobeが現在Adobe Analyticsを実装するために推奨している方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Edge NetworkでのAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| Experience Platform Web SDK拡張機能（タグ） | Experience Platform Web SDKは、Adobeで現在、web データにAdobe Analyticsを実装するために推奨されている方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Web SDKを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md)</li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDKは、Adobeで現在、モバイルデータにAdobe Analyticsを実装するために推奨されている方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。<p>Adobe Experience Platform Mobile SDKは、モバイルアプリでAdobeのExperience Cloud ソリューションとサービスを強化するのに役立ちます。 </p><p>この実装タイプについて詳しくは、[Adobe Experience Platform Mobile SDKを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md) </li><li>Platform にデータを送信するようにAdobe Analytics Web SDKを設定します。</li></ul> |
| 一括データ挿入 API | Bulk Data Insertion API （BDIA）は、Adobe Analyticsの機能で、AppMeasurementなどのクライアントサイドライブラリを使用する代わりに、多数のファイルからなるサーバーコールデータをアップロードできるものです。 </p><p>この実装タイプについて詳しくは、[Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) を参照してください。</p> | <ul><li>[ （推奨）継続的なデータ収集のためのExperience Platform Web SDKの新しい実装。履歴データのための Analytics Source コネクタ ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDKの新しい実装 ](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API およびEdge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
