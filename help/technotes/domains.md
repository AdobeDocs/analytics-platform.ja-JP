---
title: Customer Journey Analyticsが使用するドメイン
description: 組織のファイアウォールで、アドビから派生する IP アドレスがブロックされている場合は、このリストを使用してファイアウォール設定を更新してください。
role: Admin
source-git-commit: 43bda939a5464c5f65b0a050ccfdb5ba17f7d34b
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Customer Journey Analyticsが使用するドメイン

一部のファイアウォール設定では、Customer Journey Analyticsが製品インターフェイスに使用するドメインがブロックされます。 このドメインのリストを使用して組織のネットワーク設定を変更し、組織内からの製品アクセスを許可できます。 Adobeは、最適なエクスペリエンスを得るために、組織のファイアウォールを通じてこれらのドメインを許可することをお勧めします。

| 技術 | ドメイン |
| --- | --- |
| Customer Journey Analyticsドメイン | `adobe.com`、`adobe.net`、`adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud ドメイン

上記のドメインに加えて、Adobe Experience Cloudでは、データ収集とレポートの書き出しに複数のドメインを使用します。 参照： [Adobe Experience Cloudが使用するドメイン](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) （ドメインのこのリスト）。

>[!MORELIKETHIS]
>
>[Customer Journey Analyticsが使用する IP アドレス](ip-addresses.md)
>
>[Adobe Experience Cloudが使用するドメイン](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)