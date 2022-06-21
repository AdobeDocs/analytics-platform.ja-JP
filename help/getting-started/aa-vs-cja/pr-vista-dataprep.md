---
title: 処理ルール、VISTA および分類と Analytics Source Connector 用データ準備の比較
description: Data Prep の処理ルールと VISTA を使用したデータ変換と使用したデータ準備について説明します。
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# 処理ルール、VISTA および分類とデータ準備の比較

Adobe Analytics [処理ルールと VISTA ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) Adobe Analytics [データ収集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). これらの変換は、Adobeのデータ処理の一環として発生します。この変換は、Adobe Analyticsでのレポートおよび分析のためにデータが保存される前におこなわれます。

[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) は、 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). その後、データは CJA などのExperience Platformアプリケーションで利用可能になります。 データ準備は、多くの Platform と統合されています [ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en)と [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja). このコネクタを使用すると、レポートスイートデータをAdobe Analyticsから Platform に取り込むことができます。

## データ準備を使用したその他の変換 {#data-prep}

Adobe Analyticsで収集され、格納されたデータは、処理ルール、VISTA ルール、またはその両方で変換できます。 ただし、その後、Analytics ソースコネクタを介して Platform に転送されるレポートスイートは、Data Prep を使用して別の時間に変換される場合があります。 これは、様々な目的で使用すると望ましいと考えられます。

* **CJA や RTCDP で使用するレポートスイート間のスキーマの違いの解決**. 例えば、レポートスイート A が `eVar1` を「検索語句」として指定し、レポートスイート B が `eVar2` を「検索語句」として使用します。 データ準備を使用して、2 つの異なる eVar を、両方の eVar のデータを含む共通のフィールドにマッピングできます。 これにより、 [異なるスキーマでレポートスイートを組み合わせる](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) 内 [CJA 接続](/help/connections/overview.md) または [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=ja).
* **マッピング `eVars` 意味的に意味のある名前のフィールド**. `eVars` および `props` Analytics ソースコネクタを通じて読み込むと、次のようなフィールドにマッピングされます。 _\_experience.analytics.customDimensions.eVars.eVar1_. データ準備を使用してマッピングできます `eVar` および `prop` ユーザーにとってより意味のある名前を持つ新しいフィールドや、他のデータソースから取得した名前と一致するフィールド。 ( 他の方法 ( [CJA データビュー](/help/data-views/create-dataview.md).)
* **データの一般的な変換**. データ準備には、Analytics ソースコネクタを介したデータに基づいて新しいフィールドの計算と計算に使用できる、数百ものマッピング関数があります。 区切りフィールドは別々のフィールドに分割できます。 フィールドを組み合わせることができます。 文字列を操作できます。 正規表現などに基づいて、フィールドから情報を抽出できます。

## データ準備と分類 {#classifications}

Data Prep はとの重複があります [分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=ja) 場合によっては

たとえば、区切りフィールドでは、Data Prep を使用して、分類を使用せずに、そのフィールドを複数の個々のフィールドに分割できます。 一般に、分類は、受信する Analytics ヒットのストリーム外で提供される参照ファイルをアップロードすることで、フィールドにメタデータを追加する方法です。

例えば、SKU を「サイズ」、「ブランド」、「色」などにグループ化する分類ファイルをアップロードできます。 分類と Data Prep のもう 1 つの違いは、分類がデータに適用される点です _歴史的にも将来にも_. 一方、データ準備マッピングは適用されます _転送_ マッピングが作成された時点からのデータに対して。

