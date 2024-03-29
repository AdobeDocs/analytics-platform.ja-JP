---
title: Adobe Analytics データと Customer Journey Analytics データの比較
description: Adobe Analytics データを Customer Journey Analytics のデータと比較する方法を学ぶ
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: クエリサービス；クエリサービス；SQL 構文
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 64%

---

# Adobe Analytics データと Customer Journey Analytics データの比較

組織でCustomer Journey Analyticsを採用しているので、Adobe AnalyticsとCustomer Journey Analyticsの間でデータにいくつかの違いが生じる場合があります。 これは正常なことで、いくつかの理由で発生する場合があります。Customer Journey Analyticsは、AA のデータに関する制限の一部を改善できるように設計されています。 ただし、予期しない不一致や意図しない不一致が発生する場合があります。 この記事は、データの整合性に関する懸念事項によって妨げられないCustomer Journey Analyticsを、ユーザーとチームが使用できるように、違いの診断と解決に役立つように設計されています。

Adobe AnalyticsデータをAdobe Experience Platformに取り込んだとします ( [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を作成し、このデータセットを使用してCustomer Journey Analytics接続を作成しました。

![CJA 接続を使用した、Adobe Analyticsから Data Connector 経由でAdobe Experience Platformに、および Customer Analytics に送られるデータフロー。](assets/compare.png)

次に、データビューを作成し、その後、Customer Journey Analyticsに関するこのデータをレポートする際に、Adobe Analyticsのレポート結果との相違に気がつきました。

ここでは、元の Adobe Analytics データと現在 Customer Journey Analytics にある Adobe Analytics のデータを比較するための手順を示します。

## 前提条件 

* 調査中の日付範囲のデータがAdobe Experience Platformの Analytics データセットに含まれていることを確認します。

* Analytics で選択したレポートスイートが、Adobe Experience Platform に取り込まれたレポートスイートと一致していることを確認します。

## 手順 1：Adobe Analytics で発生件数指標を実行する

[発生件数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)指標は、特定のディメンションが設定または持続されたヒット数を示します。

1. Analytics／[!UICONTROL ワークスペース]で、ディメンションとしてレポートする日付範囲を[!UICONTROL フリーフォーム]テーブルにドラッグします。

1. この [!UICONTROL 発生件数]指標が自動的にその日付範囲に適用されます。

1. このプロジェクトを保存して、比較で使用できるようにします。

## 手順 2：結果の比較 [!UICONTROL タイムスタンプ別の合計レコード数] Customer Journey Analytics

ここで、Analytics の[!UICONTROL 発生件数]と Customer Journey Analytics のタイムスタンプ別合計レコード数を比較します。

Analytics ソースコネクタがドロップしたレコードがない場合、タイムスタンプ別の合計レコード数は、発生件数と一致する必要があります（次の節を参照）。

>[!NOTE]
>
>これは、( [ステッチ](/help/stitching/overview.md)) をクリックします。 比較を行う際には、Customer Journey Analyticsで使用されるユーザー ID のアカウンティングが重要であることに注意してください。 これは、特にステッチがオンになっている場合に、Adobe Analyticsでレプリケートするのが常に容易ではない場合があります。

1. Adobe Experience Platform [クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=ja)で、次の[!UICONTROL タイムスタンプ別の合計レコード数]クエリを実行します。

   ```sql
   SELECT
       Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
       Count(_id) AS Records 
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
       AND timestamp < from_utc_timestamp('{toDate}','UTC')
       AND timestamp IS NOT NULL
       AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day; 
   ```

1. [Analytics データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja)で、生データから、Analytics ソースコネクタからによって一部の行が除外された可能性があるかどうかを確認します。

   [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)では、XDM スキーマへの変換中に行がフィルタリングされる可能性があります。行全体が変換に適さない理由は複数考えられます。次の Analytics フィールドのいずれかにこれらの値がある場合、行全体が削除されます。

   | Analytics フィールド | 行が削除される原因となる値 |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | 0 ではない |
   | Exclude_hit | 0 ではない |
   | Bot_id | 0 ではない |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   hit\_source について詳しくは、[データ列リファレンス](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja)を参照してください。page\_event について詳しくは、[ページイベント検索](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html)を参照してください。

1. コネクタによって行がフィルタリングされた場合は、[!UICONTROL 発生件数]指標からそれらの行を減算します。結果の数は、Adobe Experience Platform データセットのイベント数と一致する必要があります。

## Adobe Experience Platformからの取り込み中にレコードがフィルターまたはスキップされる可能性がある理由

Customer Journey Analytics [接続](/help/connections/create-connection.md) を使用すると、データセット全体で共通の個人 ID に基づいて複数のデータセットを取り込み、結合できます。 バックエンドでは、重複排除（タイムスタンプに基づくイベントデータセットの完全な外部結合または和集合、そしてユーザー ID に基づくプロファイルとルックアップデータセットの内部結合）を適用します。

Adobe Experience Platformからデータを取り込む際にレコードがスキップされる可能性がある理由を以下に示します。

* **タイムスタンプがありません** - イベントデータセットにタイムスタンプがない場合、取り込み中、それらのレコードは完全に無視またはスキップされます。

* **ユーザー ID がありません** -（イベントデータセットからおよび／またはプロファイル／ルックアップデータセットから）ユーザー ID が見つからない場合、これらのレコードは無視またはスキップされます。これは、レコードを結合するための共通の ID や一致するキーがないためです。

* **無効または大きなユーザー ID** - 無効な ID を使用した場合、システムは結合するデータセット内で有効な共通 ID を見つけることができません。場合によっては、「未定義」や「00000000」など、ユーザー ID 列に無効なユーザー ID が含まれることがあります。月に 100 万回以上イベントに表示されるユーザー ID（数字と文字の組み合わせは任意）は、特定のユーザーに関連付けることはできません。無効と分類されます。これらのレコードはシステムに取り込むことができないので、取り込みやレポートの際にエラーが発生しやすくなります。
