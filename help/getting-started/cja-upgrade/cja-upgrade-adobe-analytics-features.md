---
title: Customer Journey Analytics にアップグレードする際の Adobe Analytics 機能のサポートについて
description: Customer Journey Analytics にアップグレードする際の Adobe Analytics 機能のサポートについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '464'
ht-degree: 100%

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
>title="Activity Map のオーバーレイのサポートはまだ利用できません"
>abstract="Activity Map のオーバーレイのサポートは、Customer Journey Analytics ではまだ利用できません。今後利用可能になる予定です。"

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
>abstract="オーディオ、ビデオ、ストリーミングコンテンツなどのメディアのデータ収集を専門とする Adobe Analytics と Customer Journey Analytics のアドオンです。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="プロジェクトとコンポーネントの移行"
>abstract="Adobe Analytics プロジェクトと関連コンポーネントを Customer Journey Analytics に取り込みます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

次のリストは、Customer Journey Analytics へのアップグレードプロセス中に考慮する必要がある Adobe Analytics 機能のみを示しています。Customer Journey Analytics で完全にサポートされている、部分的にサポートされている、またはサポートされていない Adobe Analytics 機能を示す包括的なリストについては、[Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を参照してください。

Customer Journey Analytics にアップグレードする際には、次のどの Adobe Analytics 機能を引き続き使用するかを考慮します。

| Adobe Analytics 機能 | Customer Journey Analytics の対応する機能 |
|---------|----------|
| [Adobe Analytics のコンポーネントとプロジェクト](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [プロジェクトとその関連コンポーネントを Customer Journey Analytics に移行します](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。 |
| [Activity Map オーバーレイとリンクトラッキング](https://experienceleague.adobe.com/ja/docs/analytics/analyze/activity-map/overview) | まだ使用できません |
| [分類データ](https://experienceleague.adobe.com/ja/docs/analytics/components/classifications/c-classifications) | ルックアップデータセットは、Customer Journey Analytics でデータを分類する方法です。<p>[分類データを含む各ディメンションのルックアップデータセットを作成します。](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [マーケティングチャネル](https://experienceleague.adobe.com/ja/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 派生フィールドは、データビュー内で作成されます。 <p>[マーケティングチャネル派生フィールドを作成します。](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [データフィード](https://experienceleague.adobe.com/ja/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform と Customer Journey Analytics には、単独または組み合わせて様々な書き出し要件を解決できる多数の機能が用意されています。これらの機能には、[Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=ja)、[Experience Platform の宛先](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja)、[Customer Journey Analytics の完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md)、[BI ツールの統合](/help/data-views/bi-extension.md)が含まれます。<p>書き出しオプションについて詳しくは、[データ書き出しのユースケース](/help/use-cases/data-export/overview.md)を参照してください。</p> |
| [Data Warehouse](https://experienceleague.adobe.com/ja/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics の完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md)は、Adobe Analytics のデータウェアハウスレポートの進化版で、現在のデータウェアハウスでは利用できない、リクエストの多い新機能が多数追加されています。 |
| [ストリーミングメディアデータ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-overview) | ストリーミングメディアデータは、Workspace のメディア同時視聴者数パネルおよびメディア再生滞在時間パネルの一部として、Analytics ソースコネクタに使用できます。 |
