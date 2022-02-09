---
title: CJA でのバインディングディメンションと指標の使用
description: 複雑な永続性分析のために、ディメンションをオブジェクト配列に対して属性化します。
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 38c10e395b816d812d30f0698dc821ee0ea5c9b1
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 75%

---

# CJA でのバインディングディメンションと指標の使用

Customer Journey Analytics には、設定されたヒットの後でディメンション値を保持する方法がいくつか用意されています。 アドビが提供する永続性メソッドの 1 つにバインディングがあります。 以前のバージョンの Adobe Analyticsでは、この概念はマーチャンダイジングと呼ばれていました。

バインディングディメンションはトップレベルのイベントデータで使用できますが、この概念は[オブジェクトの配列](object-arrays.md)を操作する際に最も適しています。特定のイベント内のすべての属性にディメンションを適用することなく、ディメンションをオブジェクト配列の 1 つの部分に属性付けできます。 例えば、検索語句をイベント全体にバインドしなくても、買い物かごオブジェクト配列内の 1 つの製品に、検索語句を関連付けることができます。

## 例 1:バインディングディメンションを使用して、追加の製品属性を購入に関連付けます

オブジェクト配列内のディメンション項目を別のディメンションに連結できます。 連結されたディメンション項目が表示されると、CJA は連結されたディメンションを呼び出し、イベントに含めます。 次のカスタマージャーニーについて考えてみましょう。

1. 訪問者が洗濯機で製品ページを閲覧します。

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. 訪問者は乾燥機で製品ページを表示します。

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. 最終的に彼らは購入を行う。 各製品の色が購入イベントに含まれませんでした。

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

バインディングディメンションを持たない色で売上高を確認する場合は、ディメンション `product.color` 乾燥機の色のクレジットを保持し、誤って属性設定します。

| product.color | 売上高 |
| --- | --- |
| ネオンオレンジ | 2099 |

データ表示マネージャを開き、製品の色を製品名にバインドできます。

![バインディングディメンション](assets/binding-dimension.png)

この永続性モデルを設定すると、Adobeは製品の色が設定されるたびに製品名をメモします。 この訪問者に対する後続のイベントで同じ製品名が認識されると、製品の色も引き継がれます。 製品の色を製品名にバインドする場合、同じデータは次のようになります。

| product.color | 売上高 |
| --- | --- |
| 白 | 1600 |
| ネオンオレンジ | 499 |

## 例 2:バインディング指標を使用して検索語句を製品購入に結び付ける

Adobe Analytics で最も一般的なマーチャンダイジング方法の 1 つは、検索語句を製品に結び付けて、適切な製品に対するクレジットが各検索語句に割り当てられるようにすることです。 次のカスタマージャーニーについて考えてみましょう。

1. ある訪問者がサイトを訪問して「ボクシング手袋」を検索します。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. 気に入った手袋を見つけて、買い物かごに追加します。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. 次に、訪問者は「テニスラケット」を検索します。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. 気に入ったラケットを見つけて、それを買い物かごに追加します。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. 3 回目は「靴」を検索します。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 気に入った靴を見つけて買い物かごに追加します。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 訪問者はチェックアウトプロセスを経て、これら 3 つのアイテムを購入します。

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

検索語句を使用した従来の配分モデルを使用する場合、3 つの製品すべてで、売上高が 1 つの検索語句のみに関連付けられます。 例えば、検索語句ディメンションで最初の配分を使用した場合は次のようになります。

| search_term | 売上高 |
| --- | --- |
| ボクシング手袋 | $204.97 |

検索語句ディメンションで最後の配分を使用した場合、3 つの製品すべてで売上高が 1 つの検索語句に関連付けられます。

| search_term | 売上高 |
| --- | --- |
| 靴 | $204.97 |

この例には 1 人の訪問者のみが含まれますが、多くの訪問者が異なるものを検索すると、検索用語を誤って異なる製品に関連付けてしまう可能性があるので、実際に最適な検索結果を見極めるのが困難になります。

バインディングディメンションの場合、アドビでは、連結先のディメンション項目をメモします。 後続のイベントで同じバインディング値が表示された場合、ディメンション項目が引き継がれ、目的の指標をその項目に関連付けることができます。 この例では、search_term のバインディングディメンションを product name に設定できます。 このディメンションをデータビューマネージャで設定する場合、バインディングディメンションはオブジェクト配列にあるので、バインディング指標も設定する必要があります。 バインディング指標は、バインディングディメンションのトリガーとして機能するので、バインディング指標が存在するイベントに対してのみバインドされます。 この例の実装では、検索結果ページには常に検索語句ディメンションと検索指標が含まれます。 検索指標が存在する場合は必ず、検索語句を製品名にバインドできます。

![バインディング指標](assets/binding-metric.png)

検索語句ディメンションをこの永続性モデルに設定すると、次のロジックが実行されます。

* search_term がイベント内にある場合は、製品名が存在するかどうかを確認します。
* 製品名がない場合は、何もしません。
* 製品名がある場合は、検索指標が存在するかどうかを確認します。
* 検索指標がない場合は、何もしません。
* 検索指標がある場合は、検索語句をすべての製品名にバインドします。 そのイベントの製品名と同じレベルであるかのように動作します。 この例では、product.search_term として処理します。
* 後続のイベントで同じ製品名が表示された場合は、バインドされた検索語句もそこに存在します。

Analysis Workspace では、結果のレポートは次のようになります。

| search_term | 売上高 |
| --- | --- |
| ボクシング手袋 | $89.99 |
| テニスラケット | $34.99 |
| 靴 | $79.99 |
