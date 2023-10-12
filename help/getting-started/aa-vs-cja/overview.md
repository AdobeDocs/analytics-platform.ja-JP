---
title: Adobe Analytics との比較
description: Customer Journey AnalyticsとAdobe Analyticsの比較方法の概要。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 4cbf01d397e7f89e67ae20702790129478d45cce
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 7%

---

# Adobe Analytics との比較

ドキュメントのこの節では、Adobe Customer Journey AnalyticsとAdobe Analyticsの違いを比較および理解する方法について説明します。

この 2 つのソリューションの基本的な違いは、レポートや分析を作成する際に検討できる幅広いデータです。

CUSTOMER JOURNEY ANALYTICS: *任意* データソースは、レポートや分析に使用するデータの一部にすることができます。 Adobe Analyticsは主に、Web サイトやモバイルアプリから収集されたオンラインデータを対象としています。 Adobe Analyticsには、他のソースからデータをインポートする機能が用意されていますが、この機能の主な目的は、前述のオンラインデータに関するより多くのコンテキストを提供することです。

## データ収集

Customer Journey Analyticsは、 Adobe Experience Platformデータセットに保存されたデータに依存します。 Experience Platformでこれらのデータセットのデータを収集および取り込む方法はいくつかあります。 これらのオプションの詳細については、 [データ取り込みの概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analyticsは、最終的に、ソリューション自体内のデータを収集します。 この場合も、データを収集するオプションがいくつかあります。詳しくは、 [Adobe Analytics実装ガイド](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja).

Adobe AnalyticsのレポートスイートデータをCustomer Journey Analyticsで使用するには、 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja). このコネクタは、Adobe Analyticsで収集されたデータをExperience Platformに取り込みます。 その後、このデータセットへの接続をCustomer Journey Analyticsで作成できます。 詳しくは、 [Customer Journey AnalyticsでのAdobe Analyticsレポートスイートデータの使用](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=ja) を参照してください。


## データ処理

データに関するレポートを作成する前に、多くの場合、そのデータを処理して、データがレポートに適切に使用できることを確認する必要があります。 データ処理は、収集時とレポート時に実行される場合があります。

一般に、Customer Journey Analyticsは、レポート時にExperience Platformデータセットで収集および格納されたデータを操作するように設計されています。 Customer Journey Analyticsは、データをレポートや分析に使用できるようにする、強力なレポート時間処理機能を備えています。 Experience Platformでデータを取り込む前に、データのマッピング、変換、検証を行う必要がある場合は、 [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) Experience Platformの機能。

Adobe Analyticsでは、データの処理のほとんどは、データの収集後すぐにおこなわれます。

詳しくは、 [Adobe AnalyticsとCustomer Journey Analyticsでのデータ処理の比較](data-processing-comparisons.md) および [処理ルール、VISTA、分類と Data Prep の比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=ja) を参照してください。


## 用語

Customer Journey Analyticsは、基になるエクスペリエンスデータモデル (XDM) ベースのスキーマの柔軟性によって、ディメンションと指標の定義方法を柔軟に指定できます。 例えば、Adobe Analyticsで訪問者、訪問およびヒットを使用する場合、Customer Journey Analyticsでは人物、セッションおよびイベントを同等の概念として使用します（適切に名前を変更できます）。

詳しくは、 [Analytics ソースコネクタを介して渡された Analytics データに関する用語の比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) 」を参照してください。


## 仮想レポート環境とサンドボックス

Adobe Analyticsには仮想レポートスイートの概念があり、収集したデータをセグメント化し、そのセグメント化されたデータへのアクセスを制御できます。

Customer Journey Analyticsには、データビューと呼ばれる似た概念があります。 データビューは、接続からのデータの解釈方法を決定できるコンテナです。 レポートや分析に備えて、ディメンションと指標を指定および設定できる究極の柔軟性を提供します。

Experience Platformは、特定の環境のデータやアプリケーションを保持するコンテナと考えられるサンドボックスを提供します。 サンドボックスの機能は、Adobe Analytics仮想レポートスイートまたはCustomer Journey Analyticsデータビューとは無関係です。 Adobe Analytics自体には、Experience Platformサンドボックスとの依存関係や関係はまったくありません。 Customer Journey AnalyticsはExperience Platformサンドボックスをサポートしていますが、いくつかの重要な考慮事項があります。

詳しくは、 [仮想レポートスイート、データビュー、Adobe Experience Platformサンドボックス、Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=ja) を参照してください。


## ID

Customer Journey Analyticsは、データを含むデータセットが準拠するスキーマの一部として定義する ID をサポートします。 したがって、ID はExperience Platformの基本概念で、Customer Journey Analyticsは [接続](../../connections/overview.md) （各データセットのユーザー ID を定義）および適用時に [ステッチ](../../stitching/overview.md) クロスチャネル分析用。 Experience PlatformSDK および API で使用される重要な ID は、Experience CloudID(ECID) です。

Adobe Analyticsは、Adobe Analytics ID(AAID) など、より確固たる ID フィールドセットを使用します。 Analytics ソースコネクタを使用する場合、これらのAdobe Analytics識別フィールドは特別に処理されます。 詳しくは、 [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) を参照してください。


## サポートされる機能

Adobe Analyticsの機能の概要と、これらの機能がCustomer Journey Analyticsでどのようにサポートされるかについては、 [Customer Journey Analytics機能のサポート](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





