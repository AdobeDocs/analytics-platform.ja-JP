---
title: Customer Journey Analyticsへのアップグレード時の Web SDK実装オプションについて
description: Customer Journey Analyticsへのアップグレード時の Web SDK実装オプションについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Customer Journey Analyticsへのアップグレード時の Web SDK実装オプションについて {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScriptライブラリ（alloy.js）"
>abstract="サイトの各ページに web SDK ライブラリ（alloy.js）を含めます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK タグ拡張機能"
>abstract="（推奨）タグをまだ使用していない場合は、サイトにタグローダーをインストールします。 既にタグを使用している場合は、タグプロパティに web SDK拡張機能を追加できます。 このオプションには、Adobe Experience Platform Data Collection およびサードパーティの Tag Management システム内のタグを使用した実装が含まれます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM パッケージ"
>abstract="データ収集 API を使用して、データストリームに直接データを送信します。 認証されていない（クライアントからサーバー）タイプと、認証されている（サーバーからサーバー）タイプの両方がサポートされています。"

<!-- markdownlint-enable MD034 -->

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードにお勧めのプロセスは、Experience Platform Web SDKの新しい実装です。これは、Customer Journey Analyticsに推奨されるデータ収集方法です。

Adobe Experience Platform Web SDKの使用方法として、次の 3 つがサポートされています。

* [Web SDK タグ拡張機能 ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension):Adobeでは、この方法を使用することをお勧めします。 サイトにタグローダーをインストールし、Adobe Experience Platform Data Collection UI を使用して実装を設定します。

* [Web SDK JavaScript ライブラリ ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library):CDN でホストされるライブラリファイルを参照するか、独自のインフラストラクチャを使用してライブラリファイルをホストします。 サイトのコード内でライブラリに対して呼び出しを行います。

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm):NPM パッケージマネージャーを使用して、サイトに web SDKをインストールします。

詳しくは、Experience PlatformWeb SDKガイドの [Web SDKのインストールの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) を参照してください。



