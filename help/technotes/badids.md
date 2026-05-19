---
title: Customer Journey Analyticsの不正なID
description: Customer Journey Analyticsの不正なID （BAVIDs）を理解する。 データ内の不正なIDを特定する方法、レポートに影響を与える理由、接続の不正なIDの露出を調査して解決する方法について説明します。
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 4f71fbf2-290b-4076-b2ad-b086c2b854d9
autotag-review: '2026-05-19T06:53:00.572Z'
TQID: 'https://experienceleague.adobe.com/6vut30l-BSIxhTK96Tt3BG01q-rjHagcmer0WZ2GL-c'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 632
ht-degree: 2%

---

# 不正な ID

この記事では、クエリサービスを使用して、無効なIDに関するコンテキストと、データ内での存在または発生のリスクを検出する方法について説明します。


>[!INFO]
>
>無効なIDは、Customer Journey Analytics インターフェイスではBAVIDとも呼ばれます（[Analytics BAVID](https://experienceleague.adobe.com/ja/docs/experience-cloud-kcs/kbarticles/ka-16444)から取得）。
>

## 定義

Customer Journey Analyticsでは、コネクションで定義されるすべてのデータの一部として、不正なIDは識別子です。

* 電子メールの送信元となる特定のID値を
   * ユーザーID フィールド （ステッチされていないデータセット）、**または**&#x200B;から
   * 永続的IDまたは個人ID フィールド（ステッチ可能なデータセット）から，

  **および**
* 1か月以内に、接続データ内の100万以上（1,000,000）のイベント（接続内のすべてのデータセットに対してカウント）に対して発生します。

ID値が不正IDとしてマークされている場合、そのID値を含む将来のイベントは接続データから破棄され、レポートには表示されません。

### 例

不正なID シナリオの例として、ユーザーID フィールドにカスタム値またはプレースホルダー値が含まれていることが挙げられます（匿名トラフィックの場合は`undefined`など）。 ステッチが有効なデータセットの場合、ステッチ品質が影響を受ける可能性が最も高いため、この状況はレポートデータにさらに大きな影響を与える可能性があります。 これを解決するには、接続のデータセットの履歴データの削除など、ステッチ設定をクリアして再度有効にする必要がある場合があります。


## 指標

Customer Journey Analytics Connection インターフェイスでは、インターフェイス内の複数の場所で&#x200B;**[!UICONTROL 不正なID]**&#x200B;の指標に関する情報が提供されます。

* **[!UICONTROL 無効なID]** （または&#x200B;**[!UICONTROL BAVIDs]**）は、**[!UICONTROL スキップされた詳細を確認]** ダイアログでレコードをスキップする理由として表示されます。 **[[!UICONTROL 以下の**&#x200B;[!UICONTROL &#x200B;詳細を確認&#x200B;]&#x200B;**（使用可能な場合）を使用すると、接続]](/help/connections/create-connection.md)の[詳細画面で]**&#x200B;をスキップしたレコードが表示されます。
* ステッチが有効なデータセットの場合、[**[!UICONTROL &#x200B; データセットのプレビュー]**](/help/stitching/use-stitching-ui.md#bad-ids)には、**[!UICONTROL ステッチ指標]**&#x200B;の一部として&#x200B;**[!UICONTROL 不正なID]**&#x200B;が表示されます。 この指標は、不正なID ケースが発生する可能性を特定するのに役立ちます。 ただし、この指標は、限られたデータセットにもとづいて計算されます。

接続内で使用するデータセットに対する不正なIDの存在を特定する方法については、[不正なIDの露出](#bad-ids-exposure)を参照してください（ステッチが有効かどうかに関係なく）。


## 露光量

特定のデータセットフィールドに対する不正なIDの露出を調査するには、Experience Platform クエリサービスで次のクエリを実行することを検討してください。 上位の返されたID値を確認して、不正なIDの候補があるかどうかを確認します。 [不正なID定義](#definition)は、接続内のすべてのデータセットを考慮することに注意してください。


### フィールド内の不正なIDを特定（リスクの高い）

Experience Platform Queryを使用すると、フィールド内の不正なIDの潜在的なリスクを特定できます。

以下のクエリは、フィールドから最初の20個のID値を返します。 イベントの合計数を降順で表示します。 そして、各値が特定の間隔（例えば過去30日以内）内に検出される場所。

分析する特定のユーザーID フィールドに対して、このクエリを実行します。 ステッチが必要なデータセットの場合は、永続的ID フィールドに対してクエリを実行することもできます。

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

クエリで、不正なIDについて調査するフィールドのタイプに応じて`INSERT FIELD HERE`を置き換えます。

* `full.field.path.from.XDM.schema` （XDM スキーマで定義された文字列フィールド用）
* `identityMap['namespace_value'][0].id` （`identityMap`の`namespace_value`で定義されたフィールドの場合）

結果を確認して、問題のあるID値があるかどうかを確認します。 カスタム値やプレースホルダー値、発生率が高い値など、接続データレベルで1か月以内に100万個に近づく、または近づく可能性があります。
実装がまだ開発段階にある場合でも、セットアップが安定し、本番準備が整ったら、Bad IDが存在するリスクを評価する必要があります。
