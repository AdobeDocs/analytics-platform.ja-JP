---
title: 共有デバイス
description: ステッチなどの手法を用いた共有デバイスの取り扱いについて説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: f45a457d251767634e28984d7c75158dac6e51e8
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 8%

---

# 共有デバイス

この記事では、共有デバイスに関するコンテキスト、[ ステッチ ](/help/stitching/overview.md) を使用して共有デバイスのデータを処理および軽減する方法、クエリサービスを使用してデータにおける共有デバイスの漏洩を理解する方法について説明します。

## 共有デバイスとは

共有デバイスとは、複数のユーザーが使用するデバイスです。 一般的なシナリオは、タブレット、キオスクで使用されるデバイス、コールセンターのエージェントが共有するコンピューター機器などのデバイスです。

2 人のユーザーが同じデバイスを使用し、両方のユーザーが認証済みの購入を行った場合、サンプルイベントデータは次のようになります。

| イベント | タイムスタンプ | ページ名 | デバイス ID | 電子メール |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | ホームページ | `1234` | |
| 2 | 2023-05-12 12:02 | 製品紹介ページ | `1234` | |
| 3 | 2023-05-12 12:03 | 注文の成功 | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | 製品紹介ページ | `1234` | |
| 5 | 2023-05-12 12:08 | 注文の成功 | `1234` | `cassidy@a.com` |

この表からわかるように、イベント 3 と 5 で認証が行われると、デバイス ID とユーザー ID の間にリンクが形成され始めます。 マーケティング活動がユーザーレベルに与える影響を理解するには、これらの未認証イベントを適切なユーザーに関連付ける必要があります。

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## ユーザー中心の分析の向上

ステッチプロセスは、選択した人物識別子（サンプルデータ内のメール）を、その識別子が存在しないイベントに追加することで、このアトリビューション問題に対処します。 ステッチでは、デバイス ID とユーザー ID のマッピングを活用して、認証済みトラフィックと未認証トラフィックの両方を分析で使用できるようにし、ユーザー中心を維持します。 詳しくは、[ ステッチ ](/help/stitching/overview.md) を参照してください。

ステッチでは、最終認証アトリビューションまたはデバイス分割アトリビューションのいずれかを使用して、共有デバイスデータの属性を設定できます。 未認証のイベントを既知のユーザーに関連付けようとする試みはすべて、非決定的です。


### 最終認証アトリビューション

Last-auth は、共有デバイスから最後に認証を行ったユーザーに対して、すべての不明なアクティビティを属性にします。 Experience PlatformID サービスは、last-auth アトリビューションに基づいてグラフを作成するため、グラフベースのステッチで使用されます。 詳しくは、[ID グラフリンクルール ](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details) を参照してください。

ステッチで last-auth アトリビューションを使用すると、次の表に示すように、ステッチされた ID が解決されます。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール | ステッチ ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | 製品紹介ページ | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | 注文の成功 | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | 製品紹介ページ | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | 注文の成功 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | ホームページ | `1234` | | `cassidy@a.com` |


### デバイス分割

デバイス分割は、共有デバイスの匿名アクティビティを、過去の情報を最新の既知のユーザーに属性にします。 デバイス分割は、現在、フィールドベースのステッチで使用されています。

ステッチでデバイス分割アトリビューションを使用する場合、次の表に示すように、ステッチされた ID が解決されます。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール | ステッチ ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | 製品紹介ページ | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | 注文の成功 | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | 製品紹介ページ | `1234` | | `ryan@a.com` |
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

## 共有医療機器曝露

組織における共有デバイスの普及状況を正しく理解するには、いくつかの要因を考慮します。 また、共有デバイスからのイベントの全体的な影響を把握することで、分析に使用される全体的なイベントデータへの影響を理解できます。

共有デバイスの公開を理解するには、次のクエリの実行を検討します。

1. **共有デバイスの識別**

   共有されているデバイスの数を把握するには、複数のユーザー ID が関連付けられているデバイス ID をカウントするクエリを実行します。 これは、複数の個人が使用するデバイスを識別するのに役立ちます。

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


2. **共有デバイスに対するイベントの帰属**

   識別された共有デバイスについて、これらのデバイスに起因する可能性のあるイベントの数を合計から決定します。 このアトリビューションは、共有デバイスがデータに与える影響と分析に対する影響に関するインサイトを提供します。

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

3. **共有デバイス上の匿名イベントの識別**

   共有デバイスに起因するイベントの中で、ユーザー ID を持たないイベントの数を特定し、匿名イベントを示します。 データ品質を向上させるために選択するアルゴリズム（last-auth、device-split、ECID-reset など）は、これらの匿名イベントに影響を与えます。

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

4. **イベントの誤分類からエクスポージャーを計算**

   最後に、イベントの誤分類が原因で各顧客が直面する可能性があるリスクを評価します。 各共有デバイスの合計イベントに対する匿名イベントの割合を計算します。 これは、顧客データの精度に与える可能性のある影響を理解するのに役立ちます。

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
