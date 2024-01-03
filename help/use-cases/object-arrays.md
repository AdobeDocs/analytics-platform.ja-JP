---
title: オブジェクトの配列の使用
description: データ階層に関するCustomer Journey Analyticsのレポート方法を説明します。
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 66%

---

# オブジェクトの配列の使用

一部のプラットフォームスキーマでは、オブジェクト配列を使用できます。Adobe Customer Journey Analyticsは、イベント、ルックアップ、プロファイルデータ内のオブジェクト配列の取り込みとレポートをサポートします。 最も一般的な例の 1 つに、複数の製品が入った買い物かごがあります。各製品には、名前、SKU、カテゴリ、価格、数量、および追跡したいその他のディメンションがあります。これらのファセットにはそれぞれ個別の要件がありますが、すべて同じヒットに適合する必要があります。

以前のバージョンの Adobe Analytics では、この機能は `products` 変数を使用して実行されていました。この連結文字列では、セミコロン（`;`）で製品のファセットを区切り、製品の区切りにはコンマ（`,`）を使用します。これは、「オブジェクト配列」のサポートが制限される唯一の変数です。複数値の変数（リスト変数など）は、同等の配列をサポートできますが、「オブジェクト配列」をサポートすることはできません。Customer Journey Analyticsは、Adobe Analyticsの以前のバージョンでは利用できない機能である、1 行のデータ内で任意の深い階層をサポートすることで、この概念を拡張しています。

## 同じイベントの例

次のイベントは、洗濯機と乾燥機で構成される顧客の購入を表す JSON オブジェクトです。

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

データビューを作成する場合、（スキーマに基づいて）次のディメンションと指標を使用できます。

* **ディメンション：**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : warranty : coverage
   * prodcut : warranty : length
   * product : warranty : name
   * product : warranty : type
* **指標：**
   * product : orders
   * product : units
   * product : revenue
   * product : warranty
   * product : warranty : revenue

### 同じイベントの例（レポートの動作）

上記のイベントのみを使用し、次の表に、いくつかのディメンションと指標の組み合わせを使用した Workspace レポートを示します。

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analyticsは、テーブルに基づいて、オブジェクトのディメンションと指標を選択的に確認します。

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

保証売上高のみを報告したい場合、プロジェクトは次のようになります。

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

Customer Journey Analyticsは、イベントの次の部分を調べてレポートを生成します。

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

乾燥機には保証が付いていないので、テーブルには含まれていません。

任意のディメンションを任意の指標と組み合わせることができるので、次の表では、ディメンション項目が指定されていないデータの処理方法を示します。

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

製品注文には保証名が関連付けられていないのでディメンション項目は「未指定」に属しています。同じ状況が、製品の保証注文にも当てはまります。

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
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

名前が関連付けされていない注文をメモしておきます。これらは、「未指定」ディメンション項目に属する注文です。

### 指標の組み合わせ

Customer Journey Analyticsは、異なるオブジェクトレベルにある場合、同じ名前の指標をネイティブで結合しません。

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

ただし、必要な指標を組み合わせた計算指標を作成できます。

計算指標「合計売上高」：`[product : revenue] + [product : warranty : revenue]`

この計算指標を適用すると、望ましい結果が表示されます。

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |
