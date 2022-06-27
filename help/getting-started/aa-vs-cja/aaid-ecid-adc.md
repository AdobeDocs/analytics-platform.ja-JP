---
source-git-commit: f97439676c61acf1b6ba8818ef1d06542402e675
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 10%

---
# AAID、ECID、AACUSTOMID および Analytics ソースコネクタ

Adobe Analyticsデータには複数の id フィールドが含まれています。 3 つの重要な ID フィールドは、 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja):

* **AAID** は、Adobe Analyticsの主なデバイス識別子で、Analytics ソースコネクタを介して渡されるすべてのイベントに必ず存在します。 AAID は「従来の Analytics ID」または「s\_vi cookie id」と呼ばれることがありますが、s\_vi cookie が存在しない場合でも AAID が作成されます。 AAID は、 **_post\_visid\_high/post\_visid\_low_** 列 [Adobe Analyticsデータフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja#columns%2C-descriptions%2C-and-data-types). Analytics ソースコネクタで、AAID は **HEX(post_visid_high) + &quot;-&quot; + HEX(host_visid_low)**. 特定のイベントの AAID フィールドには、単一の ID が含まれます。この ID は、 [Analytics ID の操作の順序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (AAID には、レポートスイート全体で、複数のイベントにわたる複数のタイプが混在している場合があります。 各ヒットのタイプは、 **_[post\_]visid\_type_** 」列を参照してください )。 関連項目： [データ列リファレンス](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja).
* **ECID** (Experience CloudID) は、MCID(Marketing CloudID) とも呼ばれ、Adobe Analyticsが [Experience CloudID サービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=ja). ECID は、 **_mcvisid_** Adobe Analyticsデータフィードの列。 イベントに ECID が存在する場合、AAID は、Analytics が [猶予期間](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=ja) が設定されている。 関連項目： [Analytics およびExperience CloudID のリクエスト](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).
* **AACUSTOMID** は、Analytics 実装での s.VisitorID 変数の使用に基づいてAdobe Analyticsに入力される、個別の識別子フィールドです。 AACUSTOMID は、 **_cust_visid_** Adobe Analyticsデータフィードの列。 AACUSTOMID が存在する場合、AAID は AACUSTOMID に基づきます。 （AACUSTOMID は、上記の操作の順序で定義された他のすべての識別子を切り捨てます。）

Analytics ソースコネクタは、これらの ID を次のように XDM 形式で AEP に渡します。

* endUserIDs.\_experience.aaid.id
* endUserIDs.\_experience.mcid.id
* endUserIDs.\_experience.aacustomid.id

これらのフィールドは ID としてマークされません。 代わりに、同じ ID が XDM の **_identityMap_** をキーと値のペアとして使用します。

* { &quot;key&quot;:&quot;AAID&quot;, &quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;, &quot;primary&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_**} ] }
* { &quot;key&quot;:&quot;ECID&quot;, &quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;, &quot;primary&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_** } ] }
* { &quot;key&quot;:&quot;AACUSTOMID&quot;, &quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;, &quot;primary&quot;: **false** } ] }

identityMap 内：

* ECID が存在する場合は、イベントのプライマリ ID としてマークされます。 この場合、AAID は上記の説明に従った ECID に基づく場合があります。
それ以外の場合、AAID はイベントのプライマリ ID としてマークされます。
* AACUSTOMID はイベントのプライマリID とはしません。 ただし、AACUSTOMID が存在する場合、AAID は上記の説明に従って AACUSTOMID に基づきます。

CJA に関しては、プライマリID の定義は、エンドユーザーがプライマリID をユーザー ID として使用する場合にのみ重要です。 ただし、これは必須ではありません。 ユーザーは、別の ID 列をユーザー ID として選択できます。

