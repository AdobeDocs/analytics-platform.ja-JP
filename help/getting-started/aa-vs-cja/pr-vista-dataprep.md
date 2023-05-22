---
title: 処理ルール、VISTA および分類と Analytics ソースコネクタのデータ準備の比較
description: 処理ルールおよび VISTA を使用した場合とデータ準備を使用した場合を比較し、データ変換について説明します
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 95%

---

# 処理ルール、VISTA および分類とデータ準備の比較

Adobe Analytics の[処理ルールと VISTA ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=ja)は、Adobe Analytics [データ収集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=ja)に渡されるデータを変換して操作する手段を提供します。これらの変換は、Adobe Analytics でレポートや分析目的でデータが保存される前に、アドビのデータ処理の一部として行われます。

[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)は、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja) に取り込まれたデータに対して、行ベースのマッピングや変換を適用できるツールです。これにより、CJA などを含む Experience Platform アプリケーションでデータを利用できるようになります。データ準備は、多くの Platform [ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)および [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)と統合されています。このコネクタは、Adobe Analytics から Platform にレポートスイートデータを取り込むための手段を提供します。

## データ準備を使用したさらなる変換 {#data-prep}

Adobe Analytics で収集され、保存されたデータは、処理ルール、VISTA ルールまたはその両方で変換できます。しかし、Analytics ソースコネクタを介して Platform に転送されるレポートスイートは、データ準備を使用してさらにもう一度変換できます。これは、様々な目的のために望ましいといえます。

* **CJA や RTCDP で使用するための、レポートスイート間のスキーマの違いの解決**。例えば、レポートスイート A が `eVar1` を「検索語句」として定義し、レポートスイート B が `eVar2` を「検索語句」として定義しているとします。データ準備を使用して、2 つの異なる eVar を、両方の eVar のデータを含む共通のフィールドにマッピングできます。これにより、[CJA 接続](/help/connections/overview.md)や [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=ja) で使用するために、[レポートスイートを様々なスキーマと組み合わせる](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=ja)ことが可能になります。
* **`eVars` フィールドを意味論的に意味のある名前にマッピングする**。Analytics ソースコネクタを使用して取得した `eVars` と `props` は、_\_experience.analytics.customDimensions.eVars.eVar1_ などのフィールドにマッピングされます。データ準備は、`eVar` および `prop` フィールドを、ユーザーにとってより意味のある名前、または他のデータソースから取得する名前と一致する新しいフィールドにマッピングするために使用できます（これは、[CJA データビュー](/help/data-views/create-dataview.md)でフィールド名を変更するなど、他の手段でも実現できます）。
* **データの一般的な変換**。データ準備には、何百ものマッピング関数があり、Analytics ソースコネクタを使用して取得するデータに基づいて新しいフィールドを計算するのに使用できます。区切られたフィールドを別のフィールドに分割できます。フィールドを組み合わせることができます。文字列を操作できます。正規表現に基づいてフィールドから情報を抽出できます。他にも、様々なことができます。

## データ準備と分類 {#classifications}

データ準備は、状況によっては、[分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=ja)と被ります。

例えば、区切られたフィールドでは、分類を使用せずにデータ準備を使用して、そのフィールドを複数の個別のフィールドに分割できます。一般に、分類は、受信する Analytics イベントのストリーム外で提供される参照ファイルをアップロードすることで、フィールドにメタデータを追加する方法です。

例えば、SKU を「サイズ」、「ブランド」、「色」などにグループ化した分類ファイルをアップロードできます。分類とデータ準備のもう 1 つの違いとして、分類は、_履歴と将来の両方_&#x200B;のデータに適用されるということがあります。一方、データ準備のマッピングは、マッピングが作成された時点から&#x200B;_先_&#x200B;のデータに適用されます。
