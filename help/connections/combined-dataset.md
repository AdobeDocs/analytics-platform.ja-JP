---
title: 組み合わされたデータセット
description: CJAがデータセットを組み合わせて接続を作成する方法を説明します。
translation-type: tm+mt
source-git-commit: fa354af31237c4963ba0affa89652bfdeae45ea0
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 5%

---


# 組み合わされたデータセット

接続を作成すると、CJAはすべてのスキーマとデータセットを1つのデータセットに結合します。 この「組み合わせデータセット」は、CJAがレポートに使用するものです。 複数のスキーマまたはデータセットを接続に含める場合：

* スキーマは結合されます。 重複スキーマフィールドが結合されます。
* 各データセットの「Person ID」列は、名前に関係なく1つの列に結合されます。 この列は、CJAでの個別訪問者の識別の基礎です。
* 行はタイムスタンプに基づいて処理されます。

## 例

次の例を考えてみましょう。 2つのデータセットがあり、それぞれ異なるフィールドに異なるデータが含まれています。

>[!NOTE] 通常、Adobe Experience PlatformはタイムスタンプをUnixミリ秒で格納します。 この例では、読みやすくするために、日付と時刻が使用されます。

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

これら2つのデータセットを使用して接続を作成する場合、次の表がレポートに使用されます。

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

この組み合わせデータセットは、レポートで使用されるデータセットです。 どのデータセットから行が取得されたかは関係ありません。 CJAは、すべてのデータを同じデータセット内にあるかのように扱います。 一致するPerson IDが両方のデータセットに表示される場合、それらは同じ一意の訪問者と見なされます。 30分以内のタイムスタンプを持つ両方のデータセットに、一致するPerson IDが含まれる場合、それらは同じセッションの一部と見なされます。

この概念はアトリビューションにも当てはまります。 どのデータセットから行が取得されたかは関係ありません。 アトリビューションは、すべてのイベントが単一のデータセットから来たものであるかのように正確に機能します。 上記の表を例として使用します。

接続に最初の表のみが含まれ、2番目の表は含まれない場合、ラストタッチ属性を使用してディメンション `string_color` と `metric_a` 指標を使用してレポートを取り込むと、次のように表示されます。

| string_color | metric_a |
| --- | --- |
| 未指定 | 6 |
| 青 | 3 |
| 赤 | 2 |

ただし、両方のテーブルを接続に含めた場合、属性は両方のデータセット `user_847` にあるので変更されます。 2つ目のデータセット属性 `metric_a` から「Yellow」（以前は未指定）までの行

| string_color | metric_a |
| --- | --- |
| 黄色 | 6 |
| 青 | 3 |
| 赤 | 2 |
