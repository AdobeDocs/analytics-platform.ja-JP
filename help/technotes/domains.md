---
title: Customer Journey Analyticsで使用されるドメイン
description: 組織のファイアウォールで、アドビから派生する IP アドレスがブロックされている場合は、このリストを使用してファイアウォール設定を更新してください。
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
TQID: https://experienceleague.adobe.com/d-nNfumskelDKrgCPQpyoZIagJrGcniXyQgACaHh5tA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

---

# Customer Journey Analyticsで使用されるドメイン

一部のファイアウォール設定では、Customer Journey Analyticsが製品インターフェイスに依存するドメインをブロックします。 このドメインのリストを使用して、組織のネットワーク設定を変更し、組織内から製品にアクセスできるようにすることができます。 Adobeでは、最適なエクスペリエンスを実現するために、組織のファイアウォールを通じてこれらのドメインを許可することをお勧めします。

| 技術 | ドメイン |
| --- | --- |
| Customer Journey Analytics ドメイン | `adobe.com`、`adobe.net`、`adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft®Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## CX Enterprise ドメイン

CX Enterpriseでは、上記のドメインに加えて、データの収集とレポートのエクスポートに複数のドメインを利用しています。 このドメインのリストについては、[CX Enterprise](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/domains)で使用されるドメインを参照してください。

>[!MORELIKETHIS]
>
>Customer Journey Analyticsで使用される[IP アドレス &#x200B;](ip-addresses.md)
>
>CX Enterpriseで使用されている[&#x200B; ドメイン &#x200B;](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/domains)
