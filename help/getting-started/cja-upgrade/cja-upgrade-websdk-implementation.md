---
title: Customer Journey Analytics にアップグレードする際の Web SDK 実装オプションについて
description: Customer Journey Analyticsへのアップグレード時の Web SDK実装オプションについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 54%

---

# Customer Journey Analytics にアップグレードする際の Web SDK 実装オプションについて {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript ライブラリ（alloy.js）"
>abstract="サイトの各ページに Web SDK ライブラリ（alloy.js）を含めます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK タグ拡張機能"
>abstract="（推奨）タグをまだ使用していない場合は、サイトにタグローダーをインストールします。既にタグを使用している場合は、タグプロパティに Web SDK 拡張機能を追加できます。このオプションには、Adobe Experience Platform データ収集内のタグとサードパーティのタグ管理システムを使用した実装が含まれます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM パッケージ"
>abstract="Data Collection API を使用して、データをデータストリームに直接送信します。非認証（クライアントからサーバー）と認証（サーバーからサーバー）の両方のタイプがサポートされています。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="指定したプロパティの Web SDK の実装"
>abstract="アップグレードガイドで目的の実装タイプを選択して、手順の詳細を確認します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="サードパーティの Tag Management システムへの Web SDK ライブラリの追加"
>abstract="Tag Management システムの管理者と協力して、Web SDK ライブラリをサイトに追加します。<br><br>このタスクの完了時間は、Tag Management システムの担当者の応答性に大きく依存します。Web SDK ライブラリを追加すると、関連する実装ロジックとバンドルされ、組織の標準リリースサイクル中にデプロイされる可能性があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードには、Experience Platform Web SDKの新規実装を使用することをお勧めします。これは、Customer Journey Analyticsで推奨されるデータ収集方法です。

Adobe Experience Platform Web SDKの使用方法として、次の 3 つがサポートされています。

* [Web SDK タグ拡張機能 ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension):Adobeでは、この方法を使用することをお勧めします。 サイトにタグローダーをインストールし、Adobe Experience Platform Data Collection UI を使用して実装を設定します。

* [Web SDK JavaScript ライブラリ ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library):CDN でホストされるライブラリファイルを参照するか、独自のインフラストラクチャを使用してライブラリファイルをホストします。 サイトのコード内でライブラリに対して呼び出しを行います。

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm):NPM パッケージマネージャーを使用して、サイトに web SDKをインストールします。

詳しくは、『Experience Platform Web SDK ガイド』の [Web SDKのインストールの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) を参照してください。
