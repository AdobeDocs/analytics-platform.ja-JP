---
title: Adobe Analytics との比較
description: Customer Journey Analytics と Adobe Analytics の比較の概要。
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 99%

---

# Adobe Analytics との比較

ドキュメントのこの節では、Adobe Customer Journey Analytics と Adobe Analytics の違いを比較して理解する方法について説明します。

この 2 つのソリューションの基本的な違いは、レポートや分析を作成する際に考慮できる幅広いデータです。

Customer Journey Analytics では、*あらゆる*&#x200B;データソースを、レポートや分析に使用するデータの一部にすることができます。Adobe Analytics は主に、web サイトやモバイルアプリから収集されたオンラインデータを対象としています。Adobe Analytics には他のソースからデータを読み込む機能が用意されていますが、この機能の主な目的は、前述のオンラインデータに関するより多くのコンテキストを提供することです。

## データ収集

Customer Journey Analytics は、Adobe Experience Platform データセットに保存されているデータに依存しています。Experience Platform でこれらのデータセットからデータを収集して取り込むには、いくつかのオプションがあります。[データ取り込みの概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html)で、これらのオプションについて詳しく説明しています。

Adobe Analytics は、最終的に、ソリューション自体内のデータを収集します。この場合も、データを収集するオプションがいくつかあります。詳しくは、[Adobe Analytics 実装ガイド](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja)を参照してください。

Adobe Analytics のレポートスイートデータを Customer Journey Analytics で使用するには、[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を使用します。このコネクタでは、Adobe Analytics で収集されたデータを Experience Platform に取り込みます。その後、Customer Journey Analytics でこのデータセットへの接続を作成できます。詳しくは、[Customer Journey Analytics での Adobe Analytics レポートスイートデータの使用](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html)を参照してください。


## データ処理

データに関するレポートを作成する前に、多くの場合、そのデータを処理して、レポートでデータを適切に使用できることを確認する必要があります。データ処理は、収集時とレポート時に発生する可能性があります。

一般に、Customer Journey Analytics は、レポート時に Experience Platform データセットに収集および保存されたデータを操作するように設計されています。Customer Journey Analytics は、データをレポートや分析に使用できるようにする、強力なレポート時間処理機能を備えています。Experience Platform に取り込む前にデータのマッピング、変換、検証を行う必要がある場合は、Experience Platform の[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)機能を使用できます。

Adobe Analytics では、データの処理のほとんどは、データの収集直後に行われます。

詳しくは、[Adobe Analytics と Customer Journey Analytics でのデータ処理の比較](data-processing-comparisons.md)および[処理ルール、VISTA および分類とデータ準備の比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html)を参照してください。


## 用語

Customer Journey Analytics は、基になるエクスペリエンスデータモデル（XDM）ベースのスキーマが提供する柔軟性によって、ディメンションと指標の定義方法に柔軟性をもたらします。例えば、Adobe Analytics では訪問者、訪問数、ヒット数を使用しますが、Customer Journey Analytics ではユーザー、セッション、イベントを同等の概念として使用します（必要に応じて名前を変更できます）。

用語の違いについて詳しくは、[Analytics ソースコネクタを介して渡された Analytics データの用語の比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html)を参照してください。


## 仮想レポート環境とサンドボックス

Adobe Analytics には仮想レポートスイートの概念があり、収集したデータをセグメント化し、そのセグメント化されたデータへのアクセスを制御できます。

Customer Journey Analytics には、「データビュー」という似た概念があります。データビューは、接続からのデータを解釈する方法を決定できるコンテナです。これにより、レポートや分析に備えて、ディメンションと指標を指定および設定する上で究極の柔軟性が提供されます。

Experience Platform は、特定の環境のデータやアプリケーションを保持するコンテナと考えることができる、サンドボックスを提供します。サンドボックスの機能は、Adobe Analytics 仮想レポートスイートまたは Customer Journey Analytics データビューとは無関係です。Adobe Analytics 自体には、Experience Platform サンドボックスとの依存関係や関係はまったくありません。Customer Journey Analytics は Experience Platform サンドボックスをサポートしていますが、いくつかの重要な考慮事項があります。

詳しくは、[仮想レポートスイート、データビュー、Adobe Experience Platform サンドボックスおよび Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html)を参照してください。


## ID

Customer Journey Analytics は、データを含むデータセットが準拠するスキーマの一部として定義する ID をサポートします。したがって、ID は Experience Platform の基本概念で、Customer Journey Analytics は「[接続](../../connections/overview.md)」を設定する際（各データセットのユーザー ID を定義）およびクロスチャネル分析の「[ステッチ](../../stitching/overview.md)」を適用する際に使用します。Experience Platform SDK および API で使用される重要な ID は、Experience Cloud ID（ECID）です。

Adobe Analytics は、Adobe Analytics ID（AAID）など、より明確な ID フィールドのセットを使用します。Analytics ソースコネクタを使用する場合、これらの Adobe Analytics 識別フィールドは特別に処理されます。詳しくは、[AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=ja)を参照してください。


## サポートされる機能

Adobe Analytics の機能の概要と、これらの機能が Customer Journey Analytics でどのようにサポートされるかについては、[Customer Journey Analytics 機能のサポート](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html)を参照してください。
