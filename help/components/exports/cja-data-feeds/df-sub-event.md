---
title: データフィードのサブイベントとオブジェクト配列について
description: Customer Journey Analytics データフィードがスキーマ配列からサブイベントを書き出し、Workspaceのように階層を統合するのではなく階層を保持する方法について説明します。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# データフィードのサブイベント

{{release-limited-testing}}

Customer Journey Analyticsの[&#x200B; サブイベント &#x200B;](/help/components/segments/sub-event.md)を使用すると、イベントレベルよりも詳細なレベルでイベントデータを分析できます。

次の情報を使用して、Customer Journey Analytics データフィードでサブイベントを操作する方法を理解します。

## サブイベントについて

### XDM スキーマのサブイベント

XDM スキーマでは、配列の各要素（文字列配列またはオブジェクト配列）はサブイベントです。

Adobe Experience PlatformのXDM スキーマ内のサブイベントを含むイベントを表示するには、[!UICONTROL **スキーマ**]&#x200B;を選択し、サブイベントを含むイベントを展開します。

次の例では、`Product list items`は様々なサブイベントを含むオブジェクト配列です。

オブジェクト配列とサブイベントを含む![XDM スキーマ &#x200B;](assets/df-sub-event-schema.png)

### サブイベントの例：購入イベント内の製品

顧客は、コードレスドリル 1個とドリルバッテリーパック 2個の2つの製品を1つの注文で購入します。 実装では、両方の製品を`productListItems` オブジェクト配列に含む単一の購入イベントを送信します。

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

このイベントには、2つのサブイベントが含まれており、`productListItems`配列内の各オブジェクトに1つずつ含まれます。 次の表は、イベントに属するフィールドと、そのサブイベントに属するフィールドを示しています。

| レベル | フィールド | フィールドの内容 |
| --- | --- | --- |
| **イベント** | `eventType`, `timestamp`, `commerce.purchases.value` | 購入全体です。 各フィールドには、イベントの1つの値があります。 **注文数**&#x200B;指標は、このイベントに含まれる製品数に関係なく`1`をカウントします。 |
| **サブイベント** | 各`productListItems` オブジェクトの`SKU`、`name`、`quantity`、`priceTotal` | 購入時の個別商品。 各フィールドには、製品ごとに1つの値があります。 例えば、`quantity`はコードレスドリルの場合は`1`、ドリルバッテリーパックの場合は`2`です。 |

{style="table-layout:auto"}

>[!NOTE]
>
>サブイベントには、イベントと共に送信されるデータのみが含まれます。 Customer Journey Analyticsでは、買い物かごの追加やチェックアウトなど、以前のイベントから買い物かごの内容を再構築することはありません。 製品を購入イベントのサブイベントとして表示するには、実装でその購入イベントの`productListItems`に製品を含める必要があります。

## データフィードへのサブイベントデータの追加

データフィードの構築中にサブイベントである列を追加しようとすると、ダイアログが表示され、ピアサブイベントのいずれかを追加するよう求められます。 データフィード出力では、これらのイベントはすべて1列に表示されます。

## データフィード出力でのサブイベントデータの表示

### Analysis Workspaceとデータフィードのサブイベントの違い

サブイベントは、Customer Journey AnalyticsのAnalysis Workspaceとデータフィードで異なって表示されます。

| 場所 | サブイベントの表現方法 |
| --- | --- |
| **Analysis Workspace（Customer Journey Analytics内）** | 表示されている階層とは別に、個々のコンポーネントとして選択できます。 |
| **データフィード （Customer Journey Analytics内）** | グループとして表され、階層は維持されます。 |

### Adobe AnalyticsとCustomer Journey Analyticsのサブイベントの違い

サブイベントデータ（1回の購入イベントで複数の商品の詳細など）は、Adobe Analytics データフィードとは異なり、Customer Journey Analytics データフィードに表示されます。 次の表は、各製品がサブイベントデータをどのように表しているかを比較したものです。

| 製品 | データフィードでのサブイベントデータの表示方法 | 例：製品リスト |
| --- | --- | --- |
| **Adobe Analytics** | 1列の区切り文字列にフラット化されます。 | 製品リストには、複数の製品が1つの文字列でグループ化されています。<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | サブイベントは、XDM スキーマで定義された階層を保持します。 同じ列にグループ化されている間、親イベントと兄弟サブイベントに関係する階層が表示されます。 | 製品リストは、XDM スキーマで配列として定義されている階層を維持します。<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Adobe Analyticsとの違い

### Adobe AnalyticsとCustomer Journey Analyticsのデータフィードの出力の違い

サブイベントデータ（1回の購入イベントで複数の商品の詳細など）は、Adobe Analytics データフィードとは異なり、Customer Journey Analytics データフィードに表示されます。 次の表は、各製品がサブイベントデータをどのように表しているかを比較したものです。

| 製品 | データフィードでのサブイベントデータの表示方法 | 例：製品リスト |
| --- | --- | --- |
| **Adobe Analytics** | 1列の区切り文字列にフラット化されます。 | 製品リストには、複数の製品が1つの文字列でグループ化されています。<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | サブイベントは、XDM スキーマで定義された階層を保持します。 同じ列にグループ化されている間、親イベントと兄弟サブイベントに関係する階層が表示されます。 | 製品リストは、XDM スキーマで配列として定義されている階層を維持します。<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Analysis Workspaceとデータフィード出力のサブイベントの違い

サブイベントは、Customer Journey AnalyticsのAnalysis Workspaceとデータフィードで異なって表示されます。

| 場所 | サブイベントの表現方法 |
| --- | --- |
| **Analysis Workspace** | 表示されている階層とは別に、個々のコンポーネントとして選択できます。 |
| **データフィード** | グループとして表され、階層は維持されます。 |


## データフィード出力でのサブイベントデータの表示

サブイベントデータ（1回の購入イベントで複数の商品の詳細など）は、Adobe Analytics データフィードとは異なり、Customer Journey Analytics データフィードに表示されます。 次の表は、各製品がサブイベントデータをどのように表しているかを比較したものです。

| 製品 | データフィードでのサブイベントデータの表示方法 | 例：製品リスト |
| --- | --- | --- |
| **Adobe Analytics** | 1列の区切り文字列にフラット化されます。 | 製品リストには、複数の製品が1つの文字列でグループ化されています。<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | サブイベントは、XDM スキーマで定義された階層を保持します。 同じ列にグループ化されている間、親イベントと兄弟サブイベントに関係する階層が表示されます。 | 製品リストは、XDM スキーマで配列として定義されている階層を維持します。<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## データフィード出力のサブイベントデータのクエリ

サブイベントデータ [はCustomer Journey Analytics データフィード &#x200B;](#view-sub-event-data-in-data-feed-output)で異なって表示されるため、Adobe Analytics データフィードで使用するクエリと使用するクエリは異なります。

次の例は、特定の製品を含むイベントを検索する方法を示しています。 この例では、Google BigQuery構文を使用します。 SnowflakeやDatabricksなどの他のデータウェアハウスも、構文の違いが少なくても同じアプローチをサポートしています。

+++ Customer Journey Analytics データフィードの商品データのクエリ

Customer Journey Analytics データフィードでは、同じ2つの商品が`product_list_items`列のオブジェクトの配列として表示されます。 区切り文字の解析は必要ありません。

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

クエリの書き方は、イベントごとに1行にするか、一致する製品ごとに1行にするかによって異なります。

**イベントごとに1行を返す**

行数を変更せずにイベントをフィルタリングするには、`EXISTS` サブクエリ内で`UNNEST`を使用します。

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

このクエリは、一致するイベントごとに1行を返します。配列の中で一致する製品数に関係なく、完全な`product_list_items`配列はそのまま保持されます。

**一致する製品ごとに1行を返します**

一致する製品ごとに1行を返すには、`UNNEST`を外部`FROM`句に移動します。

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

複数の一致する製品を持つイベントが複数の行として表示され、`row_id`などのイベントの列が各行で繰り返されます。 この方法は、製品レベルの詳細が必要な場合にのみ使用してください。 結果のイベントをカウントするには、行をカウントする代わりに`COUNT(DISTINCT row_id)`を使用します。

このアプローチは、製品だけでなく、XDM スキーマ内のあらゆる配列フィールドに適用されます。

+++

+++ Adobe Analytics データフィードの商品データのクエリ

Adobe Analytics データフィードでは、2つの商品が一緒に購入されたイベントが、`product_list`列に1つの区切り文字列として表示されます。

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

コードレスドリルを含むイベントを見つけるには、この文字列を正規表現で解析します。

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++






