---
title: 共有デバイス
description: ステッチなどの手法を用いた共有デバイスの取り扱いについて説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hide-from-toc: true
role: Admin
source-git-commit: 97fcb5f16962b85aa4f95bfbe2f16295d8bb3452
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 8%

---

# 共有デバイス

この記事では、共有デバイスに関するコンテキスト、ステッチを使用して共有デバイスのデータを処理および軽減する方法およびクエリサービスを使用してデータ内の共有デバイスの漏洩を理解する方法について説明します。

## 共有デバイスとは

共有デバイスとは、複数のユーザーが使用するデバイスです。 一般的なシナリオは、タブレット、キオスクで使用されるデバイス、コールセンターのエージェントが共有するコンピューター機器などのデバイスです。

2 人のユーザーが同じデバイスを使用し、両方のユーザーが購入を行う場合、サンプルイベントデータは次のようになります。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール |
|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | 1234 | |
| 2023-05-12 12:02 | 製品紹介ページ | 1234 | |
| 2023-05-12 12:03 | 注文の成功 | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | 製品紹介ページ | 1234 | |
| 2023-05-12 12:08 | 注文の成功 | 1234 | <cassidy@a.com> |

注文成功（購入）イベントは、データを正しいメールに正確に割り当てます。 この割り当てが分析に与える影響は、分析の実行方法によって異なります。

- デバイス中心アプローチ：デバイス ID を使用して実行される分析。 このアプローチでは、認証済みデータと未認証データの両方が分析に含まれます。 ただし、このアプローチでは、より多くの人物に基づいた分析はできません。
- ユーザー中心アプローチ：メールアドレスまたは他のユーザー識別子を使用して実行される分析。 このアプローチでは、認証済みイベントのみが分析に含まれます。 このアプローチでは、買収を含むカスタマージャーニーの全体像を示すことはできません

## ユーザー中心の分析の向上

共有デバイスのユーザー中心の分析を改善するには、ステッチを使用するか、ECID リセット機能を実装するという 2 つのオプションがあります。 両方のアプローチについて、以下の節で詳しく説明します。

### ステッチ

ステッチプロセスは、人物中心のアプローチの欠点に対処します。 ステッチは、選択したユーザー識別子（サンプルデータ内のメール）がその識別子に存在しないイベントに追加します。 ステッチでは、デバイス ID とユーザー ID のマッピングを活用して、認証済みトラフィックと未認証トラフィックの両方を分析で使用できるようにし、ユーザー中心を維持します。 詳しくは、[ ステッチ ](/help/stitching/overview.md) を参照してください。

ステッチでは、最終認証アトリビューションまたはデバイス分割アトリビューションのいずれかを使用して、共有デバイスデータの属性を設定できます。 ただし、ECID のリセットを介した実装の変更でも、共有デバイスに対処できます。


#### 最終認証アトリビューション

Last-auth は、共有デバイスから最後に認証を行ったユーザーに対して、すべての不明なアクティビティを属性にします。 Last-auth は、Audience Managerで使用され、リアルタイム顧客データプロファイルのユースケースで推奨されるアプローチです。 Experience PlatformID サービスは、last-auth アトリビューションに基づいてグラフを作成するため、グラフベースのステッチで使用されます。

ステッチで last-auth アトリビューションを使用する場合、次の表に示すように、ステッチ ID が解決されます。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール | ステッチ ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | 製品紹介ページ | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:03 | 注文の成功 | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | 製品紹介ページ | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 注文の成功 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | ホームページ | 1234 | | <cassidy@a.com> |


#### デバイス分割

デバイス分割は、共有デバイスからの匿名アクティビティを、その匿名アクティビティに最も近いユーザーに属性します。 デバイス分割は、最も近い既知の人物に、未認証と認証済みの両方のアクティビティのクレジットを与えるので、分析ユースケースには推奨されるアプローチです。 デバイス分割は、現在、フィールドベースのステッチで使用されています。

ステッチでデバイス分割アトリビューションを使用する場合、次の表に示すように、ステッチされた ID が解決されます。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール | ステッチ ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 製品紹介ページ | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 注文の成功 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 製品紹介ページ | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | 注文の成功 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | ホームページ | 1234 | | <cassidy@a.com> |


### ECID のリセット

名前が示すように、ECID のリセットは、ほとんどの場合、ログインまたはログアウトイベントで、事前に決められたトリガーに ECID をリセットする機能を実装します。 この実装では、所定のトリガーが起動するたびに、1 台のデバイスが新しい ECID を取得します。 基本的に、このリセットにより、データの観点からデバイスが何度も *新しいデバイス* になります。 ECID のリセットは、共有デバイスがデータに表示されるのを防ぐためにも役立ちます。 追加のアルゴリズムは必要ありませんが、Adobeデータ収集の一環として ECID リセットシグナルを実装する必要があります。


ECID リセットを使用する場合、ステッチ ID は、次の表に示すように解決されます。

| タイムスタンプ | ページ名 | デバイス ID | 電子メール | ステッチ ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | ホームページ | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 製品紹介ページ | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 注文の成功 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 製品紹介ページ | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 注文の成功 | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | ホームページ | 5678 | | <cassidy@a.com> |

## 共有医療機器曝露

組織における共有デバイスの普及状況を正しく理解するには、いくつかの要因を考慮します。 また、共有デバイスからのイベントの全体的な影響を把握することで、分析に使用される全体的なイベントデータへの影響を理解できます。

共有デバイスの公開を理解するには、次のクエリの実行を検討します。

1. 共有されるデバイスの数を理解します。 デバイス ID に関連付けられた複数のユーザー ID を持つデバイス ID をカウントするクエリを使用できます。 サンプルクエリは次のようになります。

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


2. 最初のクエリから生成された共有デバイスの場合、これらの共有デバイスに起因する可能性のある合計イベントのイベント数を理解する必要があります。 このアトリビューションにより、共有デバイスがデータに与える影響と、分析を実行した場合の影響をより深く把握できます。 サンプルクエリは次のようになります。

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

3. 共有デバイスに起因するイベント（2 番目のクエリの結果）の場合は、ユーザー ID を持たないイベントの数を把握する必要があります。 それ以外の場合は、共有デバイスイベントの数が匿名イベントになります。 最終的には、データ品質を向上させるために選択するアルゴリズム（last-auth、device-split、ECID-reset）が、これらの匿名共有デバイスイベントに影響を与えます。 サンプルクエリは次のようになります。

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

4. 最後に、イベントの分類ミスが原因で各顧客が被る危険性を理解する必要があります。 この影響を受けるには、共有デバイスごとに、イベントの合計数に対する匿名イベントの割合を計算する必要があります。 サンプルクエリは次のようになります。

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


