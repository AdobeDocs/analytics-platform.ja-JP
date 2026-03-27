---
description: Adobe AnalyticsからCustomer Journey Analyticsへのデータフィード列のマッピングの準備方法について説明します。
keywords: クリックストリーム;データフィード;データフィード;データフィード
title: Adobe Adobe AnalyticsからCustomer Journey Analyticsへのデータフィード列のマッピングの準備
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: 9403a4c6d0e0389de19aa4627d9d952f0c31f1a2
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 2%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのデータフィード列のマッピングの準備

Customer Journey Analyticsは、データフィードに含めることができる列を決定するために、Adobe Analyticsよりも柔軟なアーキテクチャを提供します。 多くの企業では、Adobe Analyticsから書き出すよりも、Customer Journey Analyticsから異なるデータフィード列を書き出す必要があります。 この違いの原因は次のとおりです。

* **[スキーマアーキテクチャ](#schema-architecture)**: Adobe Analytics データフィード列はAnalytics変数から派生し、Customer Journey Analytics データフィード列はデータビュースキーマから派生します。

* **[データ処理](#data-processing)**: Adobe AnalyticsとCustomer Journey Analyticsの間には、基本的なデータ処理の違いがあります。特に、多くのAdobe Analytics列に対して、前処理列と後処理列の両方が存在します。

* **[未使用の列](#unused-columns)**: Adobe Analyticsには1,100を超えるデータフィード列が含まれています。 ほとんどの組織では、書き出されるすべての列のデータを使用しません。

* **[クロスチャネル列](#cross-channel-columns)**: Customer Journey Analyticsは、Adobe Analyticsでは使用できないクロスチャネルデータ（コールセンターのデータなど）をサポートしています。

Adobe Analytics データフィード列とCustomer Journey Analytics データフィード列のマッピングを開始する前に、以下の節を確認して、マッピングに影響を与える主な要因をより深く理解してください。

この情報を確認したら、[&#x200B; データ列リファレンス &#x200B;](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)の説明に従って、Customer Journey Analyticsに保持する各Adobe Analytics データフィード列のマッピング手順に従います。

## スキーマアーキテクチャ

Customer Journey Analyticsは、データフィードに含めることができる列を決定するために、Adobe Analyticsよりも柔軟なアーキテクチャを提供します。

### Adobe Analytics アーキテクチャ

事前に定義された静的な変数リストを、データフィード列として含めることができます。

すべての列を含めるのは簡単ですが、それらの列に含まれるデータが組織全体で使用されていない場合でも、多くの顧客が含めることができます。

### Customer Journey Analytics アーキテクチャ

データビュースキーマに含まれているコンポーネントは、データフィード列として含めることができます。 潜在的なAdobe Analytics データフィード列についてのこのプロセスの詳細については、[&#x200B; データ列リファレンス &#x200B;](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)を参照してください。

コンポーネントは、次の表に示すいずれかの方法でデータビュースキーマに含まれます。

| データビュースキーマに含める方法 | 追加情報 |
|---------|----------|
| XDM スキーマフィールドは、データビューのコンポーネントとしてキュレーションされます | XDM スキーマに存在するフィールドは、データビューのコンポーネントとしてキュレートされた後、Customer Journey Analyticsのデータビュースキーマの一部になります。 <p>Customer Journey Analytics XDM スキーマでデフォルトで使用できるフィールドの数は、Customer Journey Analyticsの実装でデータを収集する方法によって異なります。次に示します。</p><ul><li>**新しいWeb SDKの実装**: Customer Journey Analytics実装でカスタムスキーマを使用している場合、Adobe Analytics データフィードに存在する多くの列がCustomer Journey Analyticsに存在しない可能性があります。 同様に、Customer Journey Analyticsには、Adobe Analytics データフィードに存在しないフィールドが含まれている場合があります。<p>可能であれば、組織のCustomer Journey Analytics実装用にXDM スキーマを設計したチームまたは個人を参照してください。 XDM スキーマが作成されたときに、Customer Journey Analyticsで必要なAdobe Analytics フィールドに関する多くの意思決定が行われました。 詳しくは、[Customer Journey Analytics で使用するスキーマの設計](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)を参照してください。</p></li><li>**Analytics Source コネクタの実装**:Analytics Source コネクタでは、XDM スキーマでAnalytics Experience Event フィールドグループが使用されるため、多数のデータフィード列に対してOne to One フィールドマッピングがデフォルトで存在します。 このフィールドグループのフィールドにマッピングするAdobe Analytics フィールドについて詳しくは、Experience Platform ドキュメントの[Analytics フィールドマッピング &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)を参照してください。</li></ul> |
| コンポーネントは、派生フィールドを使用してデータビュー内で作成されます | データビュー内で直接コンポーネントを作成できるため、XDM スキーマでは使用できないデータフィード列を作成できます。 |

## データ処理

Adobe AnalyticsとCustomer Journey Analyticsのデータ処理の違いは、次のように、書き出し可能なデータフィード列に影響します。

* **Adobe Analytics**：多くのデータフィード フィールドは、前処理データを含むものと後処理データを含むものという2つの別々の列として書き出されます。 （後処理データには、サーバーサイドのロジック、処理ルール、VISTA ルール、ディメンション永続性ルールなどが含まれます）。

  Adobe Analyticsは、一部のフィールドのデータを2つの別々の列（前処理済みデータ用と後処理済みデータ用の1つ）に書き出すため、Adobe AnalyticsにはCustomer Journey Analyticsよりも多くのデータフィード列が含まれます。 フィールドをマッピングするときは、この点に注意してください。

* **Customer Journey Analytics**: データビューでフィールドを作成した後、データフィードでフィールドを使用できます。 通常、Customer Journey Analytics データビューのフィールドには、後処理データのみが含まれます。 ただし、通常、Adobe Analyticsの事前処理されたフィールドのバージョンを近似するには、Customer Journey Analytics データビュー内でフィールドの2番目のバージョンを作成し、ヒット時に有効期限を設定します。

## 未使用の列

Adobe Analyticsでは、1,100以上のデータフィード列を書き出すことができます。 Customer Journey Analyticsのデータフィードでは、そのすべてが使用されるわけではありません。 この不一致は、Customer Journey Analytics データフィード列が不十分であることを示すものではありません。

組織が使用するAdobe Analytics データフィード列を特定します。 そうすることで、Customer Journey Analyticsのデータフィードに必要な列を把握できます。 使用する列を決定するには：

* **Adobe Analyticsにのみ適用されるフィールドを特定**: Adobe Analytics データフィードの一部の列は、Adobe Analyticsのデータ処理エンジンに固有であるため、Customer Journey Analyticsには適用されません。 このような列の例は`exclude_hit`と`hit_source`です。

* **組織に適用されるフィールドを特定**：すべてのAdobe Analyticsのお客様が使用可能な列をすべて書き出すわけではありませんが、多くのお客様は、実際に使用する以上のものを書き出します。

  Customer Journey Analyticsからのデータフィードの書き出しを開始する前に、まず、組織が現在使用しているAdobe Analytics データフィード列を特定し、それらのコンポーネントがCustomer Journey Analytics データビュースキーマに存在することを確認する必要があります。 この情報を収集するには、Adobe Analyticsのデータフィードのコンテンツを利用する組織全体のチームまたは個人にお問い合わせください。

## クロスチャネル列

Customer Journey Analyticsは、Adobe Analyticsでは使用できないクロスチャネルデータ（コールセンターのデータなど）をサポートしています。 これらのクロスチャネルフィールドは、Adobe AnalyticsではサポートされていないCustomer Journey Analytics データフィードに含めることができる新しい列の例です。

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
