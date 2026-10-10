---
title: データフィードの配列とマップからのサブコンテナコンポーネント
description: Customer Journey Analytics データフィードが配列とマップフィールドからサブコンテナコンポーネントを書き出す方法と、データウェアハウスでそれらをクエリする方法について説明します。
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
source-git-commit: 93107a7cf46e5d71bcb5c588eb7395fd1b88d150
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%
---
# データフィードのサブコンテナコンポーネント

{{release-limited-testing}}

サブコンテナコンポーネントは、XDM スキーマの配列内またはマップ内のフィールドに基づくディメンションと指標です。 これにより、購入時の個々の商品など、イベントレベルよりも詳細なレベルでデータを分析できます。 セグメントでのデータの使用について詳しくは、[&#x200B; サブイベント &#x200B;](/help/components/segments/sub-event.md)を参照してください。

次の情報を使用して、配列およびマップフィールドのサブコンテナコンポーネントがCustomer Journey Analytics データフィードでどのように表示されるかを理解します。

## サブコンテナコンポーネントについて

### XDM スキーマのサブコンテナコンポーネント

XDM スキーマでは、配列の各要素（文字列配列またはオブジェクト配列）はサブコンテナです。 マップフィールドの各エントリは、[&#x200B; データフィードのマップフィールド &#x200B;](#map-fields-in-data-feeds)で説明されているように、サブコンテナでもあります。 サブコンテナ内のフィールドに基づくディメンションと指標は、サブコンテナコンポーネントです。

Adobe Experience PlatformのXDM スキーマ内のサブコンテナを表示するには、[!UICONTROL **Schemas**]&#x200B;を選択し、サブコンテナを含むイベントを展開します。

次の例では、`Product list items`は、様々なサブコンテナコンポーネントを含むオブジェクト配列です。

オブジェクト配列とサブコンテナコンポーネントを含む![XDM スキーマ &#x200B;](assets/df-sub-event-schema.png)

### Analysis Workspaceとデータフィードのサブコンテナの違い

サブコンテナコンポーネントは、Customer Journey AnalyticsのAnalysis Workspaceとデータフィードで異なって表示されます。

| 場所 | サブコンテナコンポーネントの表現方法 |
| --- | --- |
| **Analysis Workspace（Customer Journey Analytics内）** | 表示されている階層とは別に、個々のコンポーネントとして選択できます。 |
| **データフィード （Customer Journey Analytics内）** | グループとして表され、階層は維持されます。 |

### Adobe AnalyticsとCustomer Journey Analyticsのサブコンテナの違い

サブコンテナデータ（1回の購入イベントで複数の商品の詳細など）は、Adobe Analytics データフィードとはCustomer Journey Analytics データフィードで異なります。 次の表は、各製品がサブコンテナデータをどのように表しているかを比較したものです。

| 製品 | データフィードでのサブコンテナデータの表示方法 | 例：製品リスト |
| --- | --- | --- |
| **Adobe Analytics** | 1列の区切り文字列にフラット化されます。 | 製品リストには、複数の製品が1つの文字列でグループ化されています。<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | サブコンテナコンポーネントは、XDM スキーマで定義された階層を保持します。 同じ列にグループ化されている間、親イベントと兄弟サブコンテナに関係する階層が表示されます。 | 製品リストは、XDM スキーマで配列として定義されている階層を維持します。<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### サブコンテナの例：購入イベント内の製品

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

このイベントには、2つのサブコンテナが含まれており、`productListItems`配列内の各オブジェクトに1つずつ含まれます。 次の表は、イベントに属するフィールドと、そのサブコンテナに属するフィールドを示しています。

| レベル | フィールド | フィールドの内容 |
| --- | --- | --- |
| **イベント** | `eventType`, `timestamp`, `commerce.purchases.value` | 購入全体です。 各フィールドには、イベントの1つの値があります。 **注文数**&#x200B;指標は、このイベントに含まれる製品数に関係なく`1`をカウントします。 |
| **サブコンテナ** | 各`productListItems` オブジェクトの`SKU`、`name`、`quantity`、`priceTotal` | 購入時の個別商品。 各フィールドには、製品ごとに1つの値があります。 例えば、`quantity`はコードレスドリルの場合は`1`、ドリルバッテリーパックの場合は`2`です。 |

{style="table-layout:auto"}

>[!NOTE]
>
>サブコンテナには、イベントと共に送信されるデータのみが含まれます。 Customer Journey Analyticsでは、買い物かごの追加やチェックアウトなど、以前のイベントから買い物かごの内容を再構築することはありません。 製品を購入イベントのサブコンテナとして表示するには、実装でその購入イベントの`productListItems`に製品を含める必要があります。

## データフィードへのサブコンテナコンポーネントの追加

サブコンテナコンポーネントをデータフィードに追加すると、同じサブコンテナから他のコンポーネントを追加するように求めるダイアログが表示されます。

![関連するサブコンテナコンポーネントの追加を求めるダイアログ &#x200B;](assets/data-feeds-add-subevent.png)

同じサブコンテナのフィールドは、フラットアイテムではなく、折りたたみ可能なネストされたグループとしてキャンバスに表示されます。

![&#x200B; サブコンテナグループ &#x200B;](assets/data-feeds-subevent-added.png)

このグループは、基礎となるデータ構造を反映しています。

データフィード出力では、これらのコンポーネントはすべて、ネストされた配列として1列に表示されます。

サブコンテナコンポーネントを含むコンポーネントをデータフィードに追加する方法について詳しくは、[&#x200B; データフィードの作成](/help/components/exports/cja-data-feeds/create-feed.md)を参照してください。

## データフィード出力のサブコンテナデータのクエリ

サブコンテナデータ [はCustomer Journey Analytics データフィード &#x200B;](#sub-container-differences-between-adobe-analytics-and-customer-journey-analytics)で異なって表示されるため、Adobe Analytics データフィードで使用するクエリと使用するクエリは異なります。

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

## データフィードでのマップフィールドの使用

XDM スキーマストアのフィールドにキーと値のペアをマッピングします。 データフィードは、他の[&#x200B; サブコンテナデータ &#x200B;](#query-sub-container-data-in-data-feed-output)と同じように、各マップをオブジェクトの配列として書き出します。 各オブジェクトには、マップキーとその値が個別のフィールドとして含まれます。

出力のフィールド名は、データフィード用に設定したコンポーネント IDに由来し、`key`や`value`などの固定名ではありません。 この節の例では、サンプルコンポーネント IDを使用します。

<!-- Confirm with Nate before publishing: how the outer array column is named in the output (for example, `survey_responses`). -->

### シンプルなマップ

シンプルなマップは、独自のスキーマで作成できるマップタイプです。 各キーは文字列で、各値は文字列または整数です。

たとえば、調査マップでは、各質問がキーとして、回答が値として格納されます。

```json
{
  "_yourtenant": {
    "surveyResponses": {
      "How did you hear about us?": "Search engine",
      "How likely are you to recommend us?": 9
    }
  }
}
```

データフィード出力では、`survey_question`と`survey_answer`はキーと値のコンポーネント IDです。

```json
{
  "survey_responses": [
    { "survey_question": "How did you hear about us?", "survey_answer": "Search engine" },
    { "survey_question": "How likely are you to recommend us?", "survey_answer": 9 }
  ]
}
```

### ID マップ

[`identityMap`](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/profile/identitymap) フィールドの各IDは、1つのオブジェクトとして書き出されます。 オブジェクトには、ID名前空間（キー）、識別子、認証状態、プライマリフラグが含まれます。 名前空間は、その名前空間内の各IDに対して繰り返されます。

データビューにディメンションとして存在し、データフィードに追加したID マップ属性のみが書き出されます。

```json
{
  "identity_map": [
    { "identity_namespace": "ECID", "identity_id": "83290187457380573620940587193016478103", "authenticated_state": "ambiguous", "is_primary": true },
    { "identity_namespace": "CRMID", "identity_id": "C-1048576", "authenticated_state": "authenticated", "is_primary": false }
  ]
}
```

### ネストされたマップ

`segmentMembership`などのAdobe定義フィールドの中には、マップのマップです。 データフィードは、これらを単一の配列に統合し、1番目のレベルのキーと2番目のレベルのキーを各オブジェクトの個別のフィールドとして使用します。 第1 レベルのキーは、適用される各オブジェクトで繰り返されるため、データや関係が失われることはありません。

例えば、`segment_namespace`と`segment_id`は、第1 レベルのキーと第2 レベルのキーのコンポーネント IDです。

```json
{
  "segment_membership": [
    { "segment_namespace": "ups", "segment_id": "04a81716-43d6-4e7a-a49c-f1d8b3129ba9", "status": "realized" },
    { "segment_namespace": "ups", "segment_id": "53cba6b2-a23b-454a-8069-fc41308f1c0f", "status": "exited" }
  ]
}
```








