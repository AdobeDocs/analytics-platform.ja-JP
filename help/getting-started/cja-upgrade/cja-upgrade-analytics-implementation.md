---
title: Adobe Analyticsの実装と、Customer Journey Analyticsへのアップグレードに与える影響について説明します
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 19%

---

# Adobe Analyticsの実装と、Customer Journey Analyticsへのアップグレードに与える影響について説明します

>[!NOTE]
> 
>[Customer Journey Analytics アップグレード チェックリスト ](https://gigazelle.github.io/cja-ttv/) の質問に答える際は、このページの情報を使用してください。

Adobe Analyticsの実装方法は様々です。 Customer Journey Analyticsにアップグレードする場合、すべてのAdobe Analytics実装ですべてのアップグレードパスを使用できるわけではありません。 ただし、組織でのAdobe Analyticsの実装方法に関係なく、推奨されるアップグレードパスを利用できます。

以下の情報を使用して、現在のAdobe Analyticsの実装と、組織で使用可能なアップグレードパスを確認します。

具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

| 既存の Adobe Analytics の実装 | 説明 | 使用可能なアップグレードパス |
|---------|----------|----------|
| AppMeasurement | これまで、JavaScriptのAppMeasurementは、Adobe Analyticsを実装する一般的な方法でした。<p>この実装タイプについて詳しくは、[JavaScriptのAppMeasurementを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview) を参照してください。</p> | <ul><li>（推奨） Analytics Source Connector を使用したExperience PlatformWeb SDK の新規実装</li><li>Experience Platform Web SDK の新しい実装</li><li>Web SDK への Adobe Analytics の移行</li><li>Analytics ソースコネクタ</li></ul> |
| Adobe Analytics拡張機能（タグ） | <p>Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。</p><p>この実装タイプについて詳しくは、[Analytics 拡張機能を使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview) を参照してください。</p> | <ul><li>（推奨） Analytics Source Connector を使用したExperience PlatformWeb SDK の新規実装</li><li>Experience Platform Web SDK の新しい実装</li><li>Web SDK への Adobe Analytics の移行</li><li>Analytics ソースコネクタ</li></ul> |
| Experience PlatformWeb SDK （alloy.js） | Experience Platform Web SDK は、Adobeが現在Adobe Analyticsを実装する際に推奨している方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Edge Networkを使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview) を参照してください</p> | <ul><li>（推奨） Analytics Source Connector を使用したExperience PlatformWeb SDK の新規実装</li><li>Platform にデータを送信するようにAdobe Analytics Web SDK を実装します。</li></ul> |
| Experience Platform Web SDK 拡張機能（タグ） | Experience Platform Web SDK は、Adobeで現在、web データ用にAdobe Analyticsを実装するために推奨されている方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Web SDK を使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview) を参照してください</p> | <ul><li>（推奨） Analytics Source Connector を使用したExperience PlatformWeb SDK の新規実装</li><li>Platform にデータを送信するようにAdobe Analytics Web SDK を実装します。</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK は、モバイルデータ用のAdobe Analyticsを実装するためにAdobeが現在推奨している方法です。 Adobe Experience Platform Edge Networkを使用すると、複数の製品用のデータを一元的な場所に送信できます。<p>Adobe Experience Platform Mobile SDK は、モバイルアプリでのAdobeのExperience Cloudソリューションおよびサービスを強化するのに役立ちます。 </p><p>この実装タイプについて詳しくは、[Adobe Experience Platform Mobile SDK を使用したAdobe Analyticsの実装 ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview) を参照してください。</p> | <ul><li>（推奨） Analytics Source Connector を使用したExperience PlatformWeb SDK の新規実装</li><li>Platform にデータを送信するようにAdobe Analytics Web SDK を実装します。</li></ul> |

{style="table-layout:auto"}
