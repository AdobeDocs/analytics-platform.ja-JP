---
title: Customer Journey Analytics にアップグレードする際の Adobe Analytics 機能のサポートについて
description: Customer Journey Analyticsへのアップグレード時のAdobe Analytics機能のサポートについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 4f6b5531578fbc4ae0eef5dc4fb46c3c1b548417
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 50%

---

# Customer Journey Analytics にアップグレードする際の Adobe Analytics 機能のサポートについて {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="コンポーネントとプロジェクト"
>abstract="Adobe Analytics のコンポーネントには、プロジェクト（関連付けられたフリーフォームテーブルとビジュアライゼーションを含む）、セグメント、計算指標が含まれます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity Map のオーバーレイとリンクトラッキング"
>abstract="リンクトラッキングデータをサイト上のオーバーレイとして表示できるブラウザー拡張機能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="Activity Map のオーバーレイは、まだサポートされていません"
>abstract="Activity Mapのオーバーレイは、Customer Journey Analyticsではまだサポートされていません。 今後利用可能になる予定です。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="分類データ"
>abstract="データを個別のディメンションとしてグループ化または分類します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="マーケティングチャネル"
>abstract="顧客がサイトに到達する方法を分類するルールを作成します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="データフィード"
>abstract="外部のツールやプロセスで使用するために、Adobe Analytics から生データを書き出します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Adobe Analytics から処理済みデータをスプレッドシート形式で書き出します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="ストリーミングメディアデータ"
>abstract="オーディオ、ビデオ、ストリーミングコンテンツなどのメディアのデータ収集を専門とするAdobe AnalyticsおよびCustomer Journey Analyticsのアドオンです。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="プロジェクトとコンポーネントを移行する"
>abstract="Adobe Analytics プロジェクトとそれに関連するコンポーネントをCustomer Journey Analyticsに取り込みます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

以下のリストは、Customer Journey Analyticsへのアップグレードプロセスで考慮する必要があるAdobe Analytics機能のみを示しています。 Customer Journey Analyticsで完全にサポートされているAdobe Analytics機能、部分的にサポートされている機能、サポートされていない機能を示す包括的なリストについては、[Customer Journey Analytics機能のサポート ](/help/getting-started/aa-vs-cja/cja-aa.md) を参照してください。

Customer Journey Analyticsにアップグレードする際に、引き続き使用するAdobe Analyticsの次の機能を検討してください。

| Adobe Analytics機能 | Customer Journey Analyticsの対応する機能 |
|---------|----------|
| [Adobe Analyticsのコンポーネントとプロジェクト ](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [ プロジェクトとその関連コンポーネントをCustomer Journey Analyticsに移行します ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。 |
| [Activity Map のオーバーレイとリンクトラッキング ](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | まだ利用できません |
| [ 分類データ ](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | ルックアップデータセットは、Customer Journey Analyticsでのデータの分類に使用されます。<p>[ 分類データを含む各ディメンションのルックアップデータセットを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。</p> |
| [マーケティングチャネル](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 派生フィールドは、データビュー内で作成されます。 <p>[ マーケティングチャネル派生フィールドを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)。</p> |
| [データフィード](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | データセットの第 1 世代のデータ書き出しは、[Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=ja) および [Experience Platform の宛先](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja)を通じて利用できます。これらのオプションを使用すると、Experience Platform データレイクに収集または取り込まれるすべてのデータをイベント／行レベルで書き出すことができます。Post 列はクエリ時に計算されるので、後処理データ列は使用できません。Post 列の書き出しは、レポートを通じて使用できます。 |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics の完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md)は、Adobe Analytics のデータウェアハウスレポートの進化版で、現在のデータウェアハウスでは利用できない、リクエストの多い新機能が多数追加されています。 |
| [ ストリーミングメディアデータ ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-overview) | ストリーミングメディアデータは、Workspace のメディア同時視聴者数パネルおよびメディア再生滞在時間パネルの一部として、Analytics ソースコネクタに使用できます。 |
