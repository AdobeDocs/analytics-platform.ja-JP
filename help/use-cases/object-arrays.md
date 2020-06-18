---
title: オブジェクトの配列でCJAを使用する
description: データ階層に関するCJAのレポート方法を理解します。
translation-type: tm+mt
source-git-commit: b7cd74f3fe2f0222e78452f58a7c387f6e0c86d2
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# オブジェクトの配列でCJAを使用する

一部のプラットフォームスキーマはオブジェクト配列を持つことができます。 最も一般的な例の1つは、複数の製品が入った買い物かごです。 各製品には、名前、SKU、カテゴリ、価格、数量など、追跡する必要のあるディメンションがあります。 これらのファセットはすべて別々の要件を持ちますが、すべて同じヒットに適合する必要があります。

以前のバージョンのAdobeAnalyticsでは、この機能は `products` 変数を使用して実行されました。 製品のファセットはセミコロン(`;`)で区切られた連結文字列で、製品のファセットはコンマ(`,`)で区切られました。 これは、「オブジェクト配列」のサポートを制限した唯一の変数です。 リスト変数などの複数値の変数は、配列と同等の配列をサポートすることはできますが、「オブジェクト配列」をサポートすることはできません。 CJAは、アドビAnalyticsの以前のバージョンでは利用できない機能である、1行のデータ内で任意に深い階層をサポートすることで、この概念を拡張しています。

## 同じヒットの例

次のヒットは、洗濯機と乾燥機で作られた顧客の購入を表すJSONオブジェクトです。

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

データ表示を作成する場合、スキーマに基づいて、次のディメンションと指標を使用できます。

* **ディメンション:**
   * ID
   * product: SKU
   * product: name
   * product: order_id
   * product: 保証： 範囲
   * prodcut : 保証： length
   * product: 保証： name
   * product: 保証： type
* **指標:**
   * product: 注文数
   * product: 単位
   * product: 売上高
   * product: 保証
   * product: 保証： 売上高

### 同じヒットの例(レポートの動作)

上記のヒットのみを使用して、次の表に、ワークスペースレポートにいくつかのディメンションと指標の組み合わせを示します。

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJAは、テーブルに基づいて、オブジェクトのディメンションと指標を選択的に調べます。

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

保証による売上高のみをレポートしたい場合、プロジェクトは次のようになります。

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJAは、ヒットの次の部分を調べてレポートを生成します。

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

ドライヤーには保証が付いていないので、テーブルには入っていません。

任意のディメンションを任意の指標と組み合わせることができるので、次の表に、未指定のディメンション値を持つデータの処理方法を示します。

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

製品注文には保証名が関連付けられていないため、分析コード値の属性は「未指定」になっています。 同じ状況が製品の保証注文にも当てはまります。

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```
