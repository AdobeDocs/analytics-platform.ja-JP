---
title: AAID、ECID、AACUSTOMID および Analytics ソースコネクタ
description: Analytics ソースコネクタでのAdobe Analytics ID フィールドの扱い方を説明します。
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
source-git-commit: 89fb87653355ffe174d9ad7e19eb5979dd78eaaf
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 9%

---

# AAID、ECID、AACUSTOMID および Analytics ソースコネクタ

Adobe Analyticsデータには複数の id フィールドが含まれています。 3 つの重要な ID フィールドは、 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja):AAID、ECID、AACUSTOMID です。

## AAID

Adobe Analytics ID(AAID) は、Adobe Analyticsの主なデバイス識別子で、Analytics ソースコネクタを介して渡されるすべてのイベントに必ず存在します。 AAID は「レガシー Analytics ID」とも呼ばれます。 `s_vi` cookie id. ただし、AAID は、 `s_vi` cookie が存在しません。 AAID は、 `post_visid_high/post_visid_low` 列 [Adobe Analyticsデータフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja#columns%2C-descriptions%2C-and-data-types).

Analytics ソースコネクタで、AAID は `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. 特定のイベントの AAID フィールドには、単一の ID が含まれます。この ID は、 [Analytics ID の操作の順序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (AAID には、レポートスイート全体で、複数のイベントにわたる複数のタイプが混在している場合があります。 各ヒットのタイプは、 `post_visid_type` 」列を参照してください )。 関連項目： [データ列リファレンス](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja).

## ECID

ECID(Experience CloudID)(MCID(Marketing CloudID) とも呼ばれます ) は、Adobe Analyticsの個別のデバイス識別子フィールドで、Analytics が [Experience CloudID サービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=ja). ECID は、 `mcvisid` Adobe Analyticsデータフィードの列。

イベントに ECID が存在する場合、AAID は、Analytics が [猶予期間](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=ja) が設定されている。 関連項目： [Analytics およびExperience CloudID のリクエスト](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID は、 `s.VisitorID` 変数を使用して、Analytics の実装で使用できます。 AACUSTOMID は、 `cust_visid` Adobe Analyticsデータフィードの列。 AACUSTOMID が存在する場合、AAID は AACUSTOMID に基づきます。 （AACUSTOMID は、上記の操作の順序で定義された他のすべての識別子を切り捨てます。）

## Analytics Source コネクタによるこれらの ID の処理方法

Analytics Source Connector は、これらの ID を次のように XDM 形式でAdobe Experience Platformに渡します。

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

これらのフィールドは ID としてマークされません。 代わりに、同じ ID が XDM の **_identityMap_** をキーと値のペアとして使用します。

* `{ “key”: “AAID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “<identity>”, “primary”: false } ] }`

括弧内の項目

identityMap 内：

* ECID が存在する場合は、イベントのプライマリ ID としてマークされます。 この場合、AAID は上記の説明に従った ECID に基づく場合があります。
それ以外の場合、AAID はイベントのプライマリ ID としてマークされます。
* AACUSTOMID はイベントのプライマリID とはしません。 ただし、AACUSTOMID が存在する場合、AAID は上記の説明に従って AACUSTOMID に基づきます。

CJA に関しては、プライマリID の定義は、エンドユーザーがプライマリID をユーザー ID として使用する場合にのみ重要です。 ただし、これは必須ではありません。 ユーザーは、別の ID 列をユーザー ID として選択できます。
