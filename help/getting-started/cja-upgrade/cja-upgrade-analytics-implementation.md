---
title: Adobe Analytics の実装と、Customer Journey Analytics へのアップグレードに与える影響について
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパスについて説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '939'
ht-degree: 100%

---

# Adobe Analytics の実装と、Customer Journey Analytics へのアップグレードに与える影響について {#implementation-affects-upgrade}

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
>id="cja-upgrade-appmeasurement-third-party"
>title="サードパーティの Tag Management ツールを使用する AppMeasurement"
>abstract="サードパーティの Tag Management ツールを使用する実装。"

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
>title="既存の実装タイプの決定"
>abstract="組織内で作業して、Adobe Analytics へのデータ送信に現在使用している実装のタイプを決定します。Customer Journey Analytics にアップグレードする際は、この情報を把握している個人またはチームと協力します。<br><br>組織が使用する実装のタイプを決定したら、Customer Journey Analytics アップグレードガイドの回答を変更します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics は様々な方法で実装できます。Customer Journey Analytics にアップグレードする際、すべてのアップグレードパスがすべての Adobe Analytics 実装で使用できるわけではありません。 ただし、組織での Adobe Analytics の実装方法に関係なく、推奨されるアップグレードパスは使用できます。

以下の情報を使用して、現在の Adobe Analytics 実装と、組織に対して使用可能なアップグレードパスを確認してください。

具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

| 既存の Adobe Analytics の実装 | 説明 | 利用可能なアップグレードパス |
|---------|----------|----------|
| AppMeasurement | JavaScript 版 AppMeasurement は、これまで Adobe Analytics を実装する一般的な方法でした。<p>この実装タイプについて詳しくは、[JavaScript 版 AppMeasurement を使用した Adobe Analytics の実装](https://experienceleague.adobe.com/ja/docs/analytics/implementation/js/overview)を参照してください。</p> | <ul><li>[（推奨）継続的なデータ収集用の Experience Platform Web SDK の新しい実装。履歴データ用の Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK の新しい実装](/help/data-ingestion/aepwebsdk.md) </li><li>[Web SDK への Adobe Analytics の移行](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics 拡張機能（タグ） | <p>Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。</p><p>この実装タイプについて詳しくは、[Analytics 拡張機能を使用した Adobe Analytics の実装](https://experienceleague.adobe.com/ja/docs/analytics/implementation/launch/overview)を参照してください。</p> | <ul><li>[（推奨）継続的なデータ収集用の Experience Platform Web SDK の新しい実装。履歴データ用の Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK の新しい実装](/help/data-ingestion/aepwebsdk.md) </li><li>[Web SDK への Adobe Analytics の移行](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK（alloy.js） | Adobe Analytics の実装方法としてアドビが現在推奨しているのは、Experience Platform Web SDK です。Adobe Experience Platform Edge Network を使用すると、複数の製品宛てのデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Edge Network を使用した Adobe Analyticsの実装](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/overview)を参照してください。</p> | <ul><li>[（推奨）継続的なデータ収集用の Experience Platform Web SDK の新しい実装。履歴データ用の Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK の新しい実装](/help/data-ingestion/aepwebsdk.md) </li><li>[Platform にデータを送信する Adobe Analytics Web SDK 実装の設定](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Web SDK 拡張機能（タグ） | web データ用の Adobe Analytics の実装方法としてアドビが現在推奨しているのは、Experience Platform Web SDK です。Adobe Experience Platform Edge Network を使用すると、複数の製品宛てのデータを一元的な場所に送信できます。 <p>この実装タイプについて詳しくは、[Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/web-sdk/overview)を参照してください。</p> | <ul><li>[（推奨）継続的なデータ収集用の Experience Platform Web SDK の新しい実装。履歴データ用の Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK の新しい実装](/help/data-ingestion/aepwebsdk.md)</li><li>[Platform にデータを送信する Adobe Analytics Web SDK 実装の設定](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK は、モバイルデータに Adobe Analytics を実装するためのアドビの現在のお勧めの方法です。Adobe Experience Platform Edge Network を使用すると、複数の製品宛てのデータを一元的な場所に送信できます。<p>Adobe Experience Platform Mobile SDK は、モバイルアプリでの Adobe Experience Cloud のソリューションとサービスを強化するのに役立ちます。 </p><p>この実装タイプについて詳しくは、[Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/mobile-sdk/overview)を参照してください。</p> | <ul><li>[（推奨）継続的なデータ収集用の Experience Platform Web SDK の新しい実装、履歴データ用の Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK の新しい実装](/help/data-ingestion/aepwebsdk.md) </li><li>[Platform にデータを送信する Adobe Analytics Web SDK 実装の設定](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| 一括データ挿入 API | 一括データ挿入 API（BDIA）は Adobe Analytics の機能で、AppMeasurement などのクライアントサイドライブラリを使用する代わりに、多数のファイルからなるサーバーコールデータをアップロードできるものです。 </p><p>この実装タイプについて詳しくは、[一括データ挿入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) を参照してください。</p> | <ul><li>[（推奨）継続的なデータ収集用の Experience Platform Web SDK の新しい実装、履歴データ用の Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK の新しい実装](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API と Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


