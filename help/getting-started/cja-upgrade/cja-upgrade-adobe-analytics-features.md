---
title: Customer Journey Analyticsへのアップグレード時のAdobe Analytics機能のサポートについて
description: Customer Journey Analyticsへのアップグレード時のAdobe Analytics機能のサポートについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1460cbd05cce793b25d026c413744508ab951147
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 29%

---

# Customer Journey Analyticsへのアップグレード時のAdobe Analytics機能のサポートについて {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="コンポーネントとプロジェクト"
>abstract="Adobe Analyticsのコンポーネントには、プロジェクト（関連するフリーフォームテーブルおよびビジュアライゼーションを含む）、セグメント、計算指標が含まれます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity Map のオーバーレイとリンクトラッキング"
>abstract="サイト上にオーバーレイとしてリンクトラッキングデータを表示できるブラウザー拡張機能。"

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
>abstract="外部のツールやプロセスで使用するために、Adobe Analyticsから生データを書き出します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Adobe Analyticsから処理済みデータをスプレッドシート形式で書き出します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="ストリーミングメディアデータ"
>abstract="オーディオ、ビデオ、ストリーミングコンテンツなどのメディアのデータ収集を専門とするAdobe Analyticsのアドオンです。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics アップグレード チェックリスト ](https://gigazelle.github.io/cja-ttv/) の質問に答える際は、このページの情報を使用してください。

以下の一覧は、[Customer Journey Analyticsアップグレードチェックリスト ](https://gigazelle.github.io/cja-ttv/) に含まれる機能のみを示しています。 Customer Journey AnalyticsでサポートされているAdobe Analytics機能、一部サポートされている機能、サポートされていない機能の一覧については、[Customer Journey Analytics機能のサポート ](/help/getting-started/aa-vs-cja/cja-aa.md) を参照してください。

Customer Journey Analyticsにアップグレードする際に、引き続き使用するAdobe Analyticsの次の機能を検討してください。

| Adobe Analytics機能 | Customer Journey Analytics内の対応する機能 |
|---------|----------|
| [Adobe Analyticsのコンポーネントとプロジェクト ](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [ プロジェクトとその関連コンポーネントをCustomer Journey Analyticsに移行します ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。 |
| [Activity Map のオーバーレイとリンクトラッキング ](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | まだ利用できません |
| [ 分類データ ](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | ルックアップデータセットは、Customer Journey Analytics内のデータを分類する手段です。<p>[ 分類データを含む各ディメンションのルックアップデータセットを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。</p> |
| [マーケティングチャネル](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 派生フィールドは、データビュー内で作成されます。 <p>[ マーケティングチャネル派生フィールドを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)。</p> |
| [データフィード](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | データセットの第 1 世代のデータ書き出しは、[Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=ja) および [Experience Platform の宛先](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja)を通じて利用できます。これらのオプションを使用すると、Experience Platform データレイクに収集または取り込まれるすべてのデータをイベント／行レベルで書き出すことができます。Post 列はクエリ時に計算されるので、後処理データ列は使用できません。Post 列の書き出しは、レポートを通じて使用できます。 |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics の完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md)は、Adobe Analytics のデータウェアハウスレポートの進化版で、現在のデータウェアハウスでは利用できない、リクエストの多い新機能が多数追加されています。 |
| [ ストリーミングメディアデータ ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-overview) | ストリーミングメディアデータは、Workspace のメディア同時視聴者数パネルおよびメディア再生滞在時間パネルの一部として、Analytics ソースコネクタに使用できます。 |

