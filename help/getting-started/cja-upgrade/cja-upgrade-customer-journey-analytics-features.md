---
title: Customer Journey Analytics 固有の機能について
description: Customer Journey Analytics 固有の機能について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 78%

---

# Customer Journey Analytics 固有の機能について {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="様々なソースのデータを結合"
>abstract="（推奨）様々な web、モバイル、オフラインのプロパティのデータを結び付けて、顧客行動の単一の統合ビューを作成します。他のチャネルからの分析データを組み合わせるこの機能は、Customer Journey Analytics の主なユースケースです。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="複数のデータセットからのヒットをステッチ"
>abstract="データセットのいずれかがプライマリ識別子（Experience Cloud ID など）を共有しない場合でも、ログインユーザー名やメールアドレスなど、別のディメンションを使用して、そのデータを結び付けることができます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="ステッチされたデータセットを生成するには、アドビカスタマーケアにお問い合わせください"
>abstract="複数のデータセットに存在するがプライマリ識別子ではない識別子を含むフィールドがある場合は、これを使用して一貫性のある識別子で新しいデータセットを生成できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Real-Time CDP との統合"
>abstract="複数のソースからのプロファイルデータを組み合わせて、ユーザー特性に基づいてオーディエンスとセグメントを生成します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Adobe Target との一時的な統合"
>abstract="アドビでは、パーソナライゼーションのユースケースに対して Adobe Journey Optimizer との統合をお勧めします。Adobe Target との統合は可能ですが、短期的な解決策です。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Journey Optimizer との統合"
>abstract="顧客とのつながり、コンテキスト、パーソナライズされたエクスペリエンスを配信します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Adobe Audience Manager との一時的な統合"
>abstract="アドビでは、オーディエンスベースのユースケースに対して Adobe Real-Time CDP との統合をお勧めします。Audience Manager との統合は可能ですが、短期的な解決策です。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

次のリストは、アップグレードプロセス中に考慮する必要がある Customer Journey Analytics 機能のみを示しています。Customer Journey Analytics で完全にサポートされている、部分的にサポートされている、またはサポートされていない Adobe Analytics 機能を示す包括的なリストについては、[Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を参照してください。

Customer Journey Analytics にアップグレードする際には、次のどの Customer Journey Analytics 機能を採用するかを考慮します。

| Customer Journey Analytics 機能 | 関数 |
|---------|----------|
| [Web データをコールセンターデータなどの他のチャネルのデータと結び付ける](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics は、あらゆる種類のデータスキーマとタイプを保持する Experience Platform の機能と組み合わされています。[エクスペリエンスデータモデル（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用すると、データを均等に表現および整理して、組み合わせや探索にすぐに使用できます。Adobe Analytics は、主に web およびモバイル分析データに焦点を当てており、[データを読み込む](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=ja)機能もいくつかあります。 |
| [カスタムディメンションを使用して他のデータセットからのヒットをステッチする](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics を使用すると、Adobe Analytics の単一のレポートスイートであるかのように、複数のレポートスイートの[データを組み合わせる](/help/connections/combined-dataset.md)ことができます。 |
| [Adobe Real-time CDP との統合 ](/help/components/audiences/audiences-overview.md) | Customer Journey Analyticsで検出されたオーディエンスを [ 作成して公開 ](/help/components/audiences/audiences-overview.md) し、Adobe Experience Platformのリアルタイム顧客プロファイルに公開して、顧客のターゲティングやパーソナライゼーションに使用できます。 |
| [Adobe Target（A4T）との統合 ](/help/integrations/at.md) | Customer Journey Analyticsの Target レポートを使用すると、Adobe Target アクティビティを [ 測定およびレポート ](/help/integrations/at.md)Customer Journey Analyticsで直接行えます。 ただし、Adobeでは、パーソナライゼーションのユースケースにはAdobe Journey Optimizerとの統合を推奨しています。 |
| [Adobe Journey Optimizer と統合する](/help/integrations/ajo.md) | Journey Optimizerで生成されたデータを設定 [Customer Journey Analyticsでアドバンス分析を実行 ](/help/integrations/ajo.md) できます。 |
| [Adobe Audience Managerとの統合 ](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | [Audience Managerの特性とセグメントをAdobe Experience Platformと共有する ](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) ことができます。 ただし、Adobeでは、オーディエンスベースのユースケースに対して、Adobe Real-time CDP との統合を推奨します。 |
