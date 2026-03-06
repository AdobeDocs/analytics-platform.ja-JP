---
title: Customer Journey Analyticsの無効な ID
description: Customer Journey Analyticsの無効な ID （BAVID）について説明します。 データ内の不正な ID を特定する方法、それがレポートに影響を与える理由、接続での不正な ID の漏洩を調査して解決する方法について説明します。
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---


# 不正 ID

この記事では、無効な ID に関するコンテキストと、クエリサービスを使用してデータ内の不正な ID の存在または発生リスクを検出する方法について説明します。


>[!INFO]
>
>不正な ID は、Customer Journey Analytics インターフェイスでは BAVID とも呼ばれます（[Analytics BAVID](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16444) に由来）。
>

## 定義

Customer Journey Analyticsでは、接続で定義されるすべてのデータの一部として、無効な ID は識別子です。

* 特定の ID 値がを生成する
   * ユーザー ID フィールド（ステッチされていないデータセット）から **または**
   * 永続 ID または人物 ID フィールド（ステッチが有効なデータセット）から、

  **および**
* は、1 か月以内に接続データの 100 万（1,000,000）個を超えるイベントに発生しています（接続内のすべてのデータセットについてカウントされます）。

ID 値が無効な ID としてマークされた場合、その ID 値を含む今後のイベントは接続データから破棄され、レポートには表示されません。

### 例

悪質な ID シナリオの例として、人物 ID フィールドにカスタムまたはプレースホルダーの値がある場合が挙げられます（例：匿名トラフィックの場合 `undefined`。 ステッチが有効なデータセットの場合、ステッチの品質に影響が及ぶ可能性が最も高いので、この状況はレポートデータにさらに大きな影響を与える可能性があります。 これを解決するには、ステッチ設定（接続内のデータセットの履歴データの削除など）をクリアして再度有効にする必要がある場合があります。


## 指標

Customer Journey Analytics Connection インターフェイスでは、インターフェイスの複数の場所に **[!UICONTROL 無効な ID]** 指標情報が表示されます。

* **[!UICONTROL スキップされた詳細を確認]** ダイアログでレコードをスキップした理由として、**[!UICONTROL 無効な ID]** （または **[!UICONTROL BAVID]**）が考えられます。 **[!UICONTROL 接続の詳細画面]** で、**[!UICONTROL スキップされたレコード]** の下の [ 詳細を確認 ](/help/connections/create-connection.md) （使用可能な場合）を使用します。
* ステッチが有効なデータセットの場合、[**[!UICONTROL  データセットプレビュー ]**](/help/stitching/use-stitching-ui.md#bad-ids) には **[!UICONTROL 指標のステッチ]** の一部として **[!UICONTROL 無効な ID]** が表示されます。 この指標は、不正な ID ケースの可能性を特定するのに役立ちます。 ただし、この指標は、限られたデータセットに基づいて計算されることに注意してください。

（ステッチが有効になっているかどうかに関係なく）接続内で使用する予定のデータセットに不正な ID が存在するかどうかを特定する際には、[ 不正な ID の漏洩 ](#bad-ids-exposure) を参照してください。


## 照射線量

特定のデータセットフィールドの不正な ID 漏洩を調査するには、Experience Platform クエリサービスで次のクエリを実行することを検討してください。 上位の返された ID 値を確認して、無効な ID の候補があるかどうかを確認します。 [ 無効な ID 定義 ](#definition) は、接続内のすべてのデータセットを考慮します。


### フィールド内の不正な ID の特定（リスク）

Experience Platform Query to Service を使用して、フィールド内の不正な ID の潜在的なリスクを特定できます。

以下のクエリは、フィールドの最初の 20 個の ID 値を返します。 合計イベント数の降順。 また、各値が特定の期間内（例えば、過去 30 日以内）に検出された場合。

分析する特定のユーザー ID フィールドに対してこのクエリを実行します。 ステッチが必要なデータセットの場合、永続 ID フィールドのクエリを実行することもできます。

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

クエリで、不正な ID について調査したフィールドのタイプに応じて、`INSERT FIELD HERE` を置き換えます。

* `full.field.path.from.XDM.schema` （XDM スキーマで定義された文字列フィールド用）
* `identityMap['namespace_value'][0].id` （`namespace_value` で `identityMap` を使用して定義されたフィールド用）

結果をチェックして、問題のある ID 値があるかどうかを確認します。 カスタム値やプレースホルダー値や、接続データレベルで 1 か月以内に 100 万近く取得される（または取得される可能性がある）オカレンスの高い値と同様です。
実装がまだ開発段階の場合でも、設定が安定し、実稼動の準備が整ったら、不正な ID が存在するリスクを評価する必要があります。
