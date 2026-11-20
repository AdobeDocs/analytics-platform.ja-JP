---
title: Adobe Analytics との比較
description: Customer Journey Analytics と Adobe Analytics の比較の概要。
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# Adobe Analytics との比較

ドキュメントのこの節では、Adobe Customer Journey Analytics と Adobe Analytics の違いを比較して理解する方法について説明します。

この 2 つのソリューションの基本的な違いは、レポートや分析を作成する際に考慮できる幅広いデータです。

Customer Journey Analytics では、*あらゆる*&#x200B;データソースを、レポートや分析に使用するデータの一部にすることができます。 Adobe Analyticsは、主にweb サイトやモバイルアプリから収集されたオンラインデータを収集することを目的としています。 Adobe Analyticsでは、他のソースからデータをインポートする機能を提供していますが、この機能の主な目的は、前述のオンラインデータに関するより多くのコンテキストを提供することです。

## データ収集

Customer Journey Analytics は、Adobe Experience Platform データセットに保存されているデータに依存しています。 Experience Platform でこれらのデータセットからデータを収集して取り込むには、いくつかのオプションがあります。 これらのオプションについて詳しくは、[&#x200B; データ取り込みの概要](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/data-ingestion)を参照してください。

Adobe Analytics は、最終的に、ソリューション自体内のデータを収集します。 繰り返しますが、そのデータを収集する方法はいくつかあります。詳しくは、[Adobe Analytics実装ガイド &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics/implementation/home)を参照してください。

Adobe Analytics のレポートスイートデータを Customer Journey Analytics で使用するには、[Analytics ソースコネクタ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)を使用します。 このコネクタでは、Adobe Analytics で収集されたデータを Experience Platform に取り込みます。 その後、Customer Journey Analytics でこのデータセットへの接続を作成できます。 詳しくは、[Customer Journey Analytics での Adobe Analytics レポートスイートデータの使用](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja)を参照してください。

Adobe Analytics レポートスイートのデータは、Customer Journey Analytics接続を構成するAdobe Experience Platform データセットに保存されているデータとは独立しています。 そのため、Adobeでは、両方の基盤に同じ値が反映されることを想定するのではなく、それぞれの基盤のデータを別々に評価することをお勧めします。

## データ処理

データに関するレポートを作成する前に、多くの場合、そのデータを処理して、レポートでデータを適切に使用できることを確認する必要があります。 データ処理は、収集時とレポート時に発生する可能性があります。

一般的に、Customer Journey Analyticsは、レポート時にExperience Platform データセットに収集および保存されたデータを使用するように設計されています。 Customer Journey Analytics には、データをレポートや分析に利用できる状態にするための、強力なレポート時の処理機能が用意されています。 [派生フィールド &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/derived-fields)と[&#x200B; コンポーネント設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview)は、過去のデータに過去にさかのぼって変更および適用できます。 データをExperience Platformに取り込む前に、データをマッピング、変換、検証する必要がある場合は、Experience Platformの[&#x200B; データ準備機能](https://experienceleague.adobe.com/ja/docs/experience-platform/data-prep/home)を使用できます。

Adobe Analytics では、データの処理のほとんどは、データの収集直後に行われます。 マーケティングチャネルルール、処理ルール、eVarの永続性およびその他の後処理ロジックは、現時点で適用され、レポートスイートに永続的です。 これらの設定に加えられた変更は、その時点から新しく受信するデータにのみ影響します。

詳しくは、[Adobe Analytics と Customer Journey Analytics でのデータ処理の比較](data-processing-comparisons.md)および[処理ルール、VISTA および分類とデータ準備の比較](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep)を参照してください。


## 用語

Customer Journey Analytics は、基になるエクスペリエンスデータモデル（XDM）ベースのスキーマが提供する柔軟性によって、ディメンションと指標の定義方法に柔軟性をもたらします。 例えば、Adobe Analyticsが訪問者、訪問、ヒットを使用する場合、Customer Journey Analyticsは人物、セッション、イベントを使用します（名前は必要に応じて変更できます）。

用語の違いについて詳しくは、[Analytics ソースコネクタを介して渡された Analytics データの用語の比較](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology)を参照してください。


## 仮想レポート環境とサンドボックス

Adobe Analytics には仮想レポートスイートの概念があり、収集したデータをセグメント化し、そのセグメント化されたデータへのアクセスを制御できます。

Customer Journey Analytics には、「データビュー」という似た概念があります。 データビューは、接続からのデータを解釈する方法を決定できるコンテナです。 これにより、レポートや分析に備えて、ディメンションと指標を指定および設定する上で究極の柔軟性が提供されます。

Experience Platformでは、特定の環境のデータとアプリケーションを保持するコンテナとして機能するサンドボックスを提供しています。 サンドボックスの機能は、Adobe Analytics 仮想レポートスイートまたは Customer Journey Analytics データビューとは無関係です。 Adobe Analytics自体には、Experience Platform サンドボックスに対する依存関係も関係もありません。 Customer Journey Analytics は Experience Platform サンドボックスをサポートしていますが、いくつか重要な考慮すべき点があります。

詳しくは、[仮想レポートスイート、データビュー、Adobe Experience Platform サンドボックスおよび Analytics ソースコネクタ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc)を参照してください。


## ID

Customer Journey Analytics は、データを含むデータセットが準拠するスキーマの一部として定義する ID をサポートします。 したがって、ID は Experience Platform の基本概念で、Customer Journey Analytics は「[接続](../../connections/overview.md)」を設定する際（各データセットのユーザー ID を定義）およびクロスチャネル分析の「[ステッチ](../../stitching/overview.md)」を適用する際に使用します。 Experience Platform SDKとAPIで使用される重要なIDは、ECIDです。

Adobe Analytics は、Adobe Analytics ID（AAID）など、より明確な ID フィールドのセットを使用します。 Analytics ソースコネクタを使用する場合、これらのAdobe Analytics ID フィールドは特別な扱いを受けます。 詳しくは、[AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc)を参照してください。


## 基数の高いディメンション

Customer Journey Analyticsはディメンション全体の値を保存します。ディメンションの一意の値の数に制限はありません。 一方、Adobe Analyticsでは、レポートとストレージを最適化するために、32 ビットハッシュを使用してディメンション値をマッピングします。 この動作により、レポートで[&#x200B; ハッシュ衝突](https://experienceleague.adobe.com/en/docs/analytics/implementation/validate/hash-collisions)が発生する可能性があります。 Adobe Analyticsは、一意の制限しきい値に達すると、値を[Low-Traffic](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic)行項目にバケット化します。 これらのディメンションを使用するセグメントでは、Adobe AnalyticsレポートとCustomer Journey Analyticsレポートの間に不一致が表示される場合があります。

## サポートされる機能

Adobe Analytics機能の概要と、Customer Journey Analyticsがそれらをサポートする方法については、[Customer Journey Analytics機能サポート &#x200B;](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa)を参照してください。
