---
title: Analytics ソースコネクタを通じて渡された Analytics データに関する用語を比較
description: いくつかの用語の違い
solution: Customer Journey Analytics
exl-id: f0f9aa1e-f9d2-4dcb-bbe9-7960412c094b
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/nGTgotKQlT8vjh1BBS4TOOAbcsSRUy25O-nWIl-BkcM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 844
ht-degree: 90%

---

# Analytics ソースコネクタを通じて渡された Analytics データに関する用語を比較

Adobe Analytics、データフィード、Analytics ソースコネクタ／データレイクおよび Customer Journey Analytics には、いくつかの用語が異なります。 このトピックでは、その違いを強調し、明確にすることを目的としています。

| 関連する用語 | Adobe Analytics | Adobe Analytics データフィード | Analytics ソースコネクタ／データレイク | Customer Journey Analytics | メモ |
|---|---|---|---|---|---|
| <ul><li>[!UICONTROL ヒット数]</li><li>[!UICONTROL 発生件数]</li><li>[!UICONTROL レコード]</li><li>[!UICONTROL イベント]</li></ul> | **[!UICONTROL 発生件数]**&#x200B;指標<br><br>について詳しくは、以下を参照してください。<ul><li>[Adobe Analytics で使用されている用語](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=ja)</li><li>[発生件数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)</li></ul> | データフィードファイルの行（レコード）の数 | データセット内の行（レコード）の数<br><br>詳しくは、以下を参照してください。<ul><li>[Adobe Analytics データと Customer Journey Analytics データの比較](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=ja)</li></ul> | **[!UICONTROL イベント]**&#x200B;指標 | <ul><li>Adobe Analytics では、「ヒット数」と「発生件数」は同義です。</li><li>以下の&#x200B;_カスタムイベント_&#x200B;を参照してください。</li><li>特定のデータは、Analytics ソースコネクタを介して Adobe Experience Platform に渡される際にフィルタリングされます。 [Adobe Analytics データと Customer Journey Analytics データの比較](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=ja)を参照してください |
| <ul><li>[!UICONTROL ユニーク訪問者]</li><li>[!UICONTROL 一意のデバイス]</li><li>[!UICONTROL 一意の Cookie]</li></ul> | **[!UICONTROL ユニーク訪問者]**&#x200B;指標<br><br>詳しくは、以下を参照してください。<ul><li>[Adobe Analytics で使用されている用語](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=ja)</li><li>[ユニーク訪問者](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=ja)</li></ul> | **post\_visid\_highとpost\_visid\_low**&#x200B;の異なる値が連結されています。<br><br>参照：<ul><li>[データフィードを使用した一般的な指標の計算](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=ja)</li></ul> | **endUserIDs.\_experience.aaid.id**&#x200B;の個別のカウント | **endUserIDs.\_experience.aaid.id**&#x200B;が人物IDとして選択されている場合、**人物**&#x200B;指標。 | <ul><li>Adobe Analytics の「ユーザー」は、通常、cookie などの「デバイス識別子」に関連付けられています。 AAID は、ECID ではなく、Adobe Analytics のプライマリデバイス識別子です。 [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=ja)も参照してください。</li><li>「訪問者」は Customer Journey Analytics の標準の指標ではありません。 ただし、**endUserIDs.\_experience.aaid.id**&#x200B;を人物IDとして選択した場合、Customer Journey Analyticsの人物指標は、Adobe Analyticsの一意の訪問者とほぼ同じです。</li></ul> |
| <ul><li>[!UICONTROL 人物]</li></ul> | **人物**&#x200B;指標<br><br>以下を参照してください。<ul><li>[人物](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=ja)</li></ul> | 使用不可 | **_\&lt;path\>_.stitchedId**&#x200B;の個別カウント（ステッチされたデータセットでのみ使用可能） | **人物**&#x200B;指標 | <ul><li>Customer Journey Analytics の人物指標は、ユーザー ID の個別カウントです。 Customer Journey Analytics 接続でユーザー ID として選択した内容に応じて、人物指標が持つ意味が異なる場合があります。</ul></li> |
| <ul><li>[!UICONTROL 訪問回数]</li><li>[!UICONTROL セッション]</li></ul> | **[!UICONTROL 訪問回数]**&#x200B;指標<br><br>以下を参照してください。<ul><li>[Adobe Analytics で使用されている用語](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=ja)</li><li>[訪問回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ja)</li><li>[レポート期間処理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)</ul></li> | **post\_visid\_high、post\_visid\_low、visit\_numおよびvisit\_start\_time\_gmt**&#x200B;の個別の値が連結されています。<br><br>参照：<ul><li>[データフィードを使用した一般的な指標の計算](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=ja)</li></ul> | 使用不可 | **セッション数**&#x200B;指標 | <ul><li>Adobe Analytics 仮想レポートスイートと Customer Journey Analytics データビューでのレポート時の処理を使用すると、訪問（セッション）の概念を設定できます。 その結果、適用される定義に応じて、訪問（セッション）の数が環境間で異なる場合があります。 [Adobe Analytics と Customer Journey Analytics のレポート機能間でのデータ処理の比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=ja)および[仮想レポートスイート、データビュー、Adobe Experience Platform サンドボックスおよび Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=ja)も参照してください。 |
| <ul><li>カスタムイベント</li><li>成功イベント</li></ul> | カスタムイベント 1～1000 | **post\_events\_list**<br><br>&#x200B;以下を参照してください。<ul><li>[データフィードを使用した一般的な指標の計算](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=ja) | **\_experience.analytics.<ul>event1to100.event1 &#x200B;**～<br>**&#x200B; event901to1000.event1000 &#x200B;**</ul> | **\_experience.analytics.<ul>event1to100.event1 &#x200B;**～<br>**&#x200B; event901to1000.event1000 &#x200B;**</ul> | <ul><li>Adobe Analytics の「イベント」とは、Adobe Analytics イメージリクエスト（データ収集サーバー呼び出し）に設定された[成功イベント](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=ja)（カスタムイベント）です。</ul> |
| <ul><li>イベントの重複排除</li><li>指標の重複排除</ul></li> | 以下を参照してください。<ul><li>[イベント ID のシリアル化](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=ja)</li></ul> | **post_events_list** 列には、重複排除されたイベント指標が含まれます。<br><br>以下を参照してください。 <ul><li>[データ列リファレンス](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja). </ul></li> | 使用不可 | 以下を参照してください。<ul><li>[指標の重複排除コンポーネントの設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=ja) | <ul><li>Adobe Analytics でのイベント／指標の重複排除は、Customer Journey Analytics とは少し異なります。 Adobe Analytics では、データ処理時に重複排除が行われます。 Customer Journey Analytics では、重複排除はレポートの実行時に行われるので、柔軟性が向上します。 重複排除された指標は、Adobe Analytics と Customer Journey Analytics では少し異なる場合があります。</li></ul> |
| <ul><li>[!UICONTROL インスタンス]指標</li></ul> | 以下を参照してください。<ul><li>[インスタンス](https://experienceleague.adobe.com/docs/analytics/components/metrics/instances.html?lang=ja) | 「pre」変数が null でない回数（例：eVar1）。 | 「mid」変数がnullでない回数（例：**\_experience.analytics.<br>customDimensions.eVars.eVar1&#x200B;**）。 | [eVar フィールドから作成](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ja)して、**&#x200B;インスタンス**&#x200B;指標を作成できます。 | <ul><li>[!UICONTROL インスタンス]は、通常、変数の設定回数を判断する手段として、prop 列と eVar 列に関連付けられています。 |

{style="table-layout:auto"}
