---
title: AAID、ECID、AACUSTOMID および Analytics ソースコネクタ
description: Analytics ソースコネクタで Adobe Analytics ID フィールドを処理する方法を説明します。
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
role: User
source-git-commit: 5c5f276711f39abb1b3f3b955ad99e17cb0ac09c
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 100%

---

# AAID、ECID、AACUSTOMID および Analytics ソースコネクタ

Adobe Analytics データには、複数の ID フィールドが含まれています。[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)では、AAID、ECID、AACUSTOMID の 3 つの重要な ID フィールドに特別な処理を行います。

## AAID

Adobe Analytics ID（AAID）は、Adobe Analytics のプライマリデバイス識別子で、Analytics ソースコネクタを通じて渡されるすべてのイベントに存在することが保証されます。AAID は、「従来の Analytics ID」や `s_vi` cookie ID と呼ばれることもあります。ただし、AAID は、`s_vi` cookie が存在しなくても作成されます。AAID は、[Adobe Analytics データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja#columns%2C-descriptions%2C-and-data-types)の `post_visid_high/post_visid_low` 列で表されます。

Analytics ソースコネクタで、AAID は、`HEX(post_visid_high) + "-" + HEX(post_visid_low)` に変換されます。指定されたイベントの AAID フィールドには、[Analytics ID の操作の順序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=ja)に記載されているように、いくつかの異なるタイプのうちの 1 つである可能性がある単一の ID が含まれています（レポートスイート全体では、AAID にはイベント間でタイプが混在している可能性があります。各イベントのタイプは、Analytics データフィードの `post_visid_type` 列に示されます）。[データ列リファレンス](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja)も参照してください。

## ECID

ECID（Experience Cloud ID）は、MCID（Marketing Cloud ID）と呼ばれることもありますが、[Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=ja)を使用して Adobe Analytics が実装される際に Analytics に設定される個別のデバイス ID フィールドです。ECID は、Adobe Analytics データフィードの `mcvisid` 列で表されます。

ECID がイベントに存在する場合、AAID は、Analytics [猶予期間](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=ja)が設定されているかどうかに応じて、ECID に基づいている可能性があります。[Analytics と Experience Cloud ID のリクエスト](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=ja)も参照してください。

## AACUSTOMID

AACUSTOMID は、Analytics 実装の `s.VisitorID` 変数の使用に基づいて、Adobe Analytics で設定される個別の ID フィールドです。AACUSTOMID は、Adobe Analytics データフィードの `cust_visid` 列で表されます。AACUSTOMID が存在する場合、AAID は、AACUSTOMID に基づきます（AACUSTOMID は、前述の操作順序で定義されるように、他のすべての ID に優先されます）。

## Analytics ソースコネクタでこれらの ID を処理する方法

Analytics ソースコネクタは、次のように、これらの ID を XDM 形式で Adobe Experience Platform に渡します。

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

これらのフィールドは、ID としてマークされません。むしろ、次のように、同じ ID が XDM の **_identityMap_** にキーと値のペアとしてコピーされます。

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

&lt;> 角括弧内の項目は、実際の値が表示される場所を表します。

identityMap 内：

* ECID が存在する場合、イベントのプライマリ ID としてマークされます。この場合、AAID は、前述のように ECID に基づいている可能性があることに注意してください。それ以外の場合、AAID は、イベントのプライマリ ID としてマークされます。
* AACUSTOMID は、イベントのプライマリ ID としてマークされることはありません。ただし、AACUSTOMID が存在する場合、AAID は、前述のように、AACUSTOMID に基づきます。

ID が `identityMap` にコピーされると、`endUserIDs._experience.mcid.namespace.code` も同じイベントに設定されます。

* AAID が存在する場合、`endUserIDs._experience.aaid.namespace.code` は「AAID」に設定されています。
* ECID が存在する場合、`endUserIDs._experience.mcid.namespace.code` は「ECID」に設定されています。
* AACUSTOMID が存在する場合、`endUserIDs._experience.aacustomid.namespace.code` は「AACUSTOMID」に設定されています。

## Customer Journey Analytics とプライマリ ID

Customer Journey Analytics に関する限り、プライマリ ID の定義は、プライマリ ID をユーザー ID として使用することに決定している場合にのみ重要です。ただし、これは必須ではありません。一部の他の ID 列を人物 ID として選択することできます。
