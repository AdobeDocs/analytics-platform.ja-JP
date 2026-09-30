---
title: Analytics ソースコネクタ用の処理ルール、VISTA、分類と Data Prep の比較
description: 処理ルールおよび VISTA を使用した場合とデータ準備を使用した場合を比較し、データ変換について学ぶ
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
role: User
TQID: 'https://experienceleague.adobe.com/MuJbtTwSbGbKBifnyWz6SNybYX9JsMpIL9QwVJv031Y'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 92%
---
# 処理ルール、VISTA、分類と Data Prep の比較

Adobe Analytics の[処理ルールと VISTA ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=ja)は、Adobe Analytics [データ収集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=ja)に渡されるデータを変換して操作する手段を提供します。 これらの変換は、Adobe Analytics でレポートや分析目的でデータが保存される前に、アドビのデータ処理の一部として行われます。

[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)は、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja) に取り込まれたデータに対して、行ベースのマッピングや変換を適用できるツールです。 これにより、Customer Journey Analytics などを含む Experience Platform アプリケーションでデータを利用できるようになります。 データ準備は、多くの Platform [ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)および [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)と統合されています。 このコネクタは、Adobe Analytics からプラットフォームにレポートスイートデータを取り込むための手段を提供します。

## Data Prep を使用したさらなる変換 {#data-prep}

Adobe Analytics で収集され、保存されたデータは、処理ルール、VISTA ルールまたはその両方で変換できます。 ただし、Analytics ソースコネクタを介してプラットフォームに転送されるレポートスイートは、Data Prep を使用してさらにもう一度変換することができます。 これは、いくつかの目的で有用です。

* **Customer Journey Analytics や RTCDP で使用するための、レポートスイート間のスキーマの違いの解決**。 例えば、レポートスイート A は `eVar1` を「検索語」として定義し、レポートスイート B では `eVar2` を「検索語」として定義します。 Data Prep を使用して、2 つの異なる eVar を、両方の eVar のデータを含む共通のフィールドにマッピングできます。 これにより、[Customer Journey Analytics 接続](/help/connections/overview.md)や [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=ja) で使用するために、[レポートスイートを様々なスキーマと組み合わせる](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=ja)ことが可能になります。
* **`eVars` フィールドを意味論的に意味のある名前にマッピングする**。 Analytics ソースコネクタを使用して取得した `eVars` と `props` は、_\_ experience.analytics.customDimensions.eVars.eVar1_ などのフィールドにマッピングされます。 データ準備は、`eVar` および `prop` フィールドを、ユーザーにとってより意味のある名前、または他のデータソースから取得する名前と一致する新しいフィールドにマッピングするために使用できます。 （これは、[Customer Journey Analytics データビュー](/help/data-views/create-dataview.md)でフィールド名を変更するなど、他の手段でも実現できます）。
* **データの一般的な変換**。 Data Prep には何百ものマッピング関数があり、Analytics ソースコネクタ経由で流入するデータに基づいて新しいフィールドを計算するために使用できます。 区切り文字で分割されたフィールドを別々のフィールドに分割できます。 フィールドを組み合わせることができます。 文字列を操作できます。 正規表現などに基づいて、フィールドから情報を抽出できます。

## データ準備と分類 {#classifications}

データ準備は、状況によっては、[分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=ja)と被ります。

例えば、区切られたフィールドでは、分類を使用せずにデータ準備を使用して、そのフィールドを複数の個別のフィールドに分割できます。 通常、分類は、受信する Analytics のイベントのストリーム外で提供されるルックアップファイルをアップロードして、フィールドにメタデータを追加するための手段です。

例えば、SKUを「サイズ」、「ブランド」、「カラー」などにグループ化する分類ファイルをアップロードできます。分類とデータ準備のもう1つの違いは、分類がデータ _に適用されるのは、過去と今後の両方です_。 一方、データ準備のマッピングは、マッピングが作成された時点から&#x200B;_先_&#x200B;のデータに適用されます。
