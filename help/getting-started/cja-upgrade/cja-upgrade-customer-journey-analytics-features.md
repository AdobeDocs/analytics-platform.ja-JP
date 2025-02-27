---
title: Customer Journey Analyticsに特有の機能について
description: Customer Journey Analytics固有の機能について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 19%

---

# Customer Journey Analyticsに特有の機能について {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="様々なソースのデータを結合"
>abstract="（推奨）他のチャネルからの分析データを組み合わせる機能は、Customer Journey Analyticsの主なユースケースです。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="複数のデータセットからのヒットをステッチ"
>abstract="データセットのいずれかがプライマリ識別情報（Experience Cloud ID など）を共有しない場合でも、ログインユーザー名やメールアドレスなど、別のディメンションを使用して、そのデータを結び付けることができます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="ステッチされたデータセットを生成するには、Adobe カスタマーケアにお問い合わせください"
>abstract="複数のデータセットに存在するがプライマリ識別子ではない識別子を含むフィールドがある場合、それを使用して、一貫性のある識別子で新しいデータセットを生成できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Real-time CDP との統合"
>abstract="複数のソースのプロファイルデータを組み合わせて、ユーザー特性に基づいてオーディエンスとセグメントを生成します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="一時的にAdobe Targetと統合する"
>abstract="Adobeでは、パーソナライゼーションのユースケースに対してAdobe Journey Optimizerとの統合を推奨します。 Adobe Targetとの統合は可能ですが、一時的な解決策です。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Journey Optimizerとの統合"
>abstract="顧客とのつながり、コンテキスト、パーソナライズされたエクスペリエンスを提供します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Adobe Audience Manager と一時的に統合する"
>abstract="Adobeでは、オーディエンスベースのユースケースに対して、Adobe Real-time CDP との統合を推奨します。 Audience Managerとの統合は可能ですが、一時的な解決策です。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

次のリストは、アップグレードプロセス中に考慮する必要があるCustomer Journey Analytics機能のみを示しています。 Customer Journey Analyticsで完全にサポートされているAdobe Analytics機能、部分的にサポートされている機能、サポートされていない機能を示す包括的なリストについては、[Customer Journey Analytics機能のサポート ](/help/getting-started/aa-vs-cja/cja-aa.md) を参照してください。

Customer Journey Analyticsにアップグレードする際には、次のどのCustomer Journey Analytics機能を採用するかを考慮します。

| Customer Journey Analytics機能 | 関数 |
|---------|----------|
| [Web データを、コールセンターデータなどの他のチャネルのデータと結び付ける ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics は、あらゆる種類のデータスキーマとタイプを保持する Experience Platform の機能と組み合わされています。[エクスペリエンスデータモデル（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用すると、データを均等に表現および整理して、組み合わせや探索にすぐに使用できます。Adobe Analytics は、主に web およびモバイル分析データに焦点を当てており、[データを読み込む](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=ja)機能もいくつかあります。 |
| [ カスタムディメンションを使用して他のデータセットからのヒットをステッチする ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics を使用すると、Adobe Analytics の単一のレポートスイートであるかのように、複数のレポートスイートの[データを組み合わせる](/help/connections/combined-dataset.md)ことができます。 |
| [Adobe Real-time CDP との統合 ](/help/components/audiences/audiences-overview.md) | Customer Journey Analyticsで検出されたオーディエンスを [ 作成して公開 ](/help/components/audiences/audiences-overview.md) し、Adobe Experience Platformのリアルタイム顧客プロファイルに公開して、顧客のターゲティングやパーソナライゼーションに使用できます。 |
| [Adobe Target（A4T）との一時的な統合 ](/help/integrations/at.md) | Customer Journey Analyticsの Target レポートを使用すると、Adobe Target アクティビティを [ 測定およびレポート ](/help/integrations/at.md)Customer Journey Analyticsで直接行えます。 |
| [Adobe Journey Optimizerとの統合 ](/help/integrations/ajo.md) | Journey Optimizerで生成されたデータを設定 [Customer Journey Analyticsでアドバンス分析を実行 ](/help/integrations/ajo.md) できます。 |
| Adobe Audience Manager と一時的に統合する |  |
