---
title: データフィードのサブイベントとオブジェクト配列について
description: Customer Journey Analytics データフィードがスキーマ配列からサブイベントを書き出し、Workspaceのように階層を統合するのではなく階層を保持する方法について説明します。
hide: true
feature: Components
source-git-commit: afc1b55eb54b5f3342800489d0a7f63508ee8b10
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# データフィードのサブイベント

{{release-limited-testing}}

XDM スキーマでは、配列（文字列またはオブジェクト）であるすべてはサブイベントです。 Customer Journey Analyticsのサブイベントは、データフィードの書き出しにその階層で表されます。

Adobe Analyticsでは、サブイベントは1つの列として表されます。

次の情報を使用して、Customer Journey Analytics データフィードでサブイベントを操作する方法を理解します。

## XDM スキーマ、Workspace、データフィードのサブイベント

XDM スキーマでは、サブイベントを文字列配列またはオブジェクト配列として定義します。

これらのサブイベントは、Analysis Workspaceで表示するか、データフィードで表示するかによって異なります。

| 場所 | サブイベントの表現方法 |
| --- | --- |
| **Analysis Workspace** | オブジェクトの配列内の個々のオブジェクトは、表示されている階層とは別に、個々のコンポーネントとして選択できます。 |
| **データフィード** | オブジェクトの配列内のオブジェクトは、階層を維持したままグループとして表されます。 |

## データフィードへのサブイベントデータの追加

データフィードの構築中にサブイベントである列を追加しようとすると、すべてのピアサブイベントを追加できるダイアログが表示されます。 これらのイベントはすべて、データフィード出力の1列に表示されます。

## データフィード出力でのサブイベントデータの表示

サブイベントデータ（1つのイベントに複数の商品がある場合など）は、Adobe Analytics データフィードとCustomer Journey Analytics データフィードで表示が異なります。 次の表は、各製品がサブイベントデータをどのように表しているかを比較したものです。

| 製品 | データフィードでのサブイベントデータの表示方法 | 例：製品リスト |
| --- | --- | --- |
| **Adobe Analytics** | 1列の区切り文字列にフラット化されます。 | 製品リストには、複数の製品が1つの文字列でグループ化されています。<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | サブイベントは、XDM スキーマで定義された階層を保持します。 親イベントや兄弟サブイベントと一緒に、同じ列にグループ化されたままになります。 | 製品リストは、XDM スキーマで配列として定義されている階層を維持します。<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## データフィード出力のサブイベントデータのクエリ

サブイベントデータ [はCustomer Journey Analytics データフィード ](#customer-journey-analytics-vs-adobe-analytics)で異なって表示されるため、Adobe Analytics データフィードで使用するクエリと使用するクエリは異なります。

次の例は、特定の製品を含むイベントを検索する方法を示しています。 この例では、Google BigQuery構文を使用します。 SnowflakeやDatabricksなどの他のデータウェアハウスも、構文の違いが少なくても同じアプローチをサポートしています。

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






