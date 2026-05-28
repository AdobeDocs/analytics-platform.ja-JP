---
title: 共有デバイス
description: ステッチやその他の手法を使用して共有デバイスを処理する方法の説明。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
autotag-review: '2026-05-19T09:47:24.777Z'
TQID: 'https://experienceleague.adobe.com/8Xq8mUchtogMLiEuPVv-DWpkWtD5ubJGSQm2SRaZmps'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 726
ht-degree: 16%

---

# 共有デバイス

この記事では、共有デバイスに関するコンテキストと、[&#x200B; ステッチ &#x200B;](/help/stitching/overview.md)を使用して共有デバイスからのデータを処理および軽減する方法、およびクエリサービスを使用してデータ内の共有デバイスの露出を把握する方法について説明します。

## 共有デバイスとは？

共有デバイスは、複数のユーザーが使用するデバイスです。 一般的なシナリオは、タブレットなどのデバイス、キオスクで使用されるデバイス、コールセンターの担当者が共有するコンピューター機器などです。

2人が同じデバイスを使用し、両方で認証済みの購入をおこなう場合、サンプルイベントデータは次のようになります。

| イベント | タイムスタンプ | ページ名 | デバイス ID | 電子メール |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | ホームページ | `1234` | |
| 2 | 2023-05-12 12:02 | 製品ページ | `1234` | |
| 3 | 2023-05-12 12:03 | 注文の成功 | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | 製品ページ | `1234` | |
| 5 | 2023-05-12 12:08 | 注文の成功 | `1234` | `cassidy@a.com` |

この表から分かるように、イベント 3と5で認証が行われると、デバイス IDと人物IDの間にリンクが形成され始めます。 マーケティング活動が個人レベルで与える影響を把握するには、これらの未認証のイベントを適切な人物に起因させる必要があります。

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## 人物中心の分析を改善

このステッチプロセスでは、選択した人物識別子（データの例では電子メール）を、その識別子が存在しないイベントに追加することで、このアトリビューションの問題に対処します。 接続では、デバイス IDと人物IDのマッピングを利用して、認証済みトラフィックと未認証トラフィックの両方を分析で使用できるようにし、人物を中心に据えます。 詳しくは、[&#x200B; ステッチ &#x200B;](/help/stitching/overview.md)を参照してください。

ステッチでは、last-auth アトリビューションまたはdevice-split アトリビューションを使用して、共有デバイスデータにアトリビューションを付けることができます。 未認証のイベントを既知のユーザーに結びつけるあらゆる試みは、決定論的ではありません。


### Last-auth attribution

Last-authは、共有デバイスのすべての不明なアクティビティを、最後に認証されたユーザーに属性します。 Experience Platform Identity Serviceは、last-auth アトリビューションに基づいてグラフベースを構築するため、グラフベースの合成に使用されます。 詳細については、[ID グラフ リンク ルール &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details)を参照してください。

ステッチでlast-auth アトリビューションを使用する場合、ステッチ IDは次の表のように解決されます。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール | ステッチ ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | 製品ページ | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | 注文の成功 | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | 製品ページ | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | 注文の成功 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | ホームページ | `1234` | | `cassidy@a.com` |


### Device-split

デバイス分割では、共有デバイスの匿名アクティビティを、過去に閲覧した最新の既知のユーザーに割り当てます。 デバイス分割は現在、フィールドベースのステッチで使用されています。

デバイス分割アトリビューションをステッチで使用する場合、ステッチ IDは次の表に示すように解決されます。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール | ステッチ ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | 製品ページ | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | 注文の成功 | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | 製品ページ | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | 注文の成功 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | ホームページ | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`|
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` |
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` |
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## 共有デバイス露出

共有デバイスが組織内でどの程度普及しているかを正しく把握するために、いくつかの要因を検討してください。 さらに、共有デバイスからのイベントの全体的な貢献度を把握すると、分析に使用されたイベントデータ全体への影響を把握できます。

共有デバイスの露出を把握するには、次のクエリを実行することを考えます。

1. **共有デバイスの特定**

   共有されているデバイスの数を把握するには、2つ以上の人物IDが関連付けられているデバイス IDをカウントするクエリを実行します。 これにより、複数のユーザーが使用しているデバイスを特定できます。

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **共有デバイスに対するイベントの属性**

   特定された共有デバイスについて、合計のうち、これらのデバイスに起因するイベントの数を決定します。 このアトリビューションにより、insightでは、共有デバイスがデータに与える影響と、分析に対する影響を把握できます。

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **共有デバイス上の匿名イベントを識別**

   共有デバイスに起因するイベントの中から、匿名のイベントを示すユーザーIDが欠落しているイベントの数を特定します。 データ品質を向上させるために選択したアルゴリズム（last-auth、device-split、ECID-resetなど）は、これらの匿名イベントに影響します。

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **イベントの誤分類からの露出の計算**

   最後に、イベントの誤分類によって各顧客が直面する可能性のある露出を評価します。 共有デバイスごとにイベントの合計に対する匿名イベントの割合を計算します。 これは、顧客データの正確性に与える可能性のある影響を把握するのに役立ちます。

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
