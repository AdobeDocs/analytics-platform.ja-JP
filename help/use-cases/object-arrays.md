---
title: オブジェクトの配列の使用
description: Customer Journey Analyticsによるデータ階層に関するレポート方法を説明します。
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 61%

---

# オブジェクトの配列の使用

一部のプラットフォームスキーマでは、オブジェクト配列を使用できます。Adobe Customer Journey Analyticsは、イベント、ルックアップ、プロファイルデータ内のオブジェクト配列の取り込みとレポートをサポートしています。 最も一般的な例の 1 つに、複数の製品が入った買い物かごがあります。各製品には、名前、SKU、カテゴリ、価格、数量、および追跡したいその他のディメンションがあります。これらのファセットにはそれぞれ個別の要件がありますが、すべて同じヒットに適合する必要があります。

以前のバージョンの Adobe Analytics では、この機能は `products` 変数を使用して実行されていました。この連結文字列では、セミコロン（`;`）で製品のファセットを区切り、製品の区切りにはコンマ（`,`）を使用します。これは、「オブジェクト配列」のサポートが制限される唯一の変数です。複数値の変数（リスト変数など）は、同等の配列をサポートできますが、「オブジェクト配列」をサポートすることはできません。Customer Journey Analyticsでは、この概念をさらに拡張し、以前のバージョンのAdobe Analyticsでは使用できない、1 行のデータ内の任意の深層階層をサポートします。

## 同じイベントの例

次のイベントは、洗濯機と乾燥機で作られた顧客の購入を表す JSON オブジェクトです。

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

### 同じイベントの例（レポート動作）

上記のイベントのみを使用し、次の表は、いくつかのディメンションと指標の組み合わせを使用したWorkspace レポートを示しています。

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analyticsは、テーブルに基づいてオブジェクトのディメンションと指標を選択的に調べます。

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

Customer Journey Analyticsでは、イベントの次の部分を調べてレポートを生成します。

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

異なるオブジェクトレベルにある場合、Customer Journey Analyticsは同じような名前の指標をネイティブに組み合わせません。

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



## 制限事項

制限は、スキーマで使用され、Experience PlatformのCustomer Journey Analyticsの一部としてモデル化されるデータ内の配列に適用されます。 [ リアルタイム顧客プロファイルデータおよびセグメント化のデフォルトガードレール [ の [](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-size-limits) データモデルの制限 ](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-model-limits) および ](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails) データサイズの制限）を参照してください。

