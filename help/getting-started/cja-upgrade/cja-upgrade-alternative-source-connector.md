---
title: アップグレードの代替案：Customer Journey Analytics へのアップグレードに、Analytics ソースコネクタのみを使用する
description: Analytics ソースコネクタをCustomer Journey Analyticsの唯一の実装パスとして使用する利点と欠点を理解します。これは、Adobeでは推奨されないアプローチです。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
autotag-review: '2026-05-19T08:09:45.448Z'
TQID: 'https://experienceleague.adobe.com/KF-XUA12iIq0wGcSc4P-vGXQV56H5j-jKEgRsxLoUrI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 614a234f8db9783dacaf9d2f3c21a5afd5ea02ef
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 88%
---
# アップグレードの代替案：Customer Journey Analytics へのアップグレードに、Analytics ソースコネクタのみを使用する {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Analytics ソースコネクタのみを使用する"
>abstract="（非推奨）Analytics ソースコネクタを、Customer Journey Analytics の唯一の実装パスとして使用できます。 <br><br>このオプションを使用すると、Customer Journey Analytics にデータをすばやく送信できるので、実装時間が節約されます。 ただし、待ち時間が長い、今後 Adobe Analytics から移行するのが難しいなど、様々な欠点があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

推奨されませんが、Analytics ソースコネクタを Customer Journey Analytics の唯一の実装パスとして使用できます。 ただし、このタイプのアップグレードには固有のデメリットがあるので、アドビでは、Analytics ソースコネクタを Experience Platform Web SDK の新しい実装と組み合わせて使用することをお勧めします。 お勧めのアップグレードパスについて詳しくは、[Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパス](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)を参照してください。

## メリットとデメリット

Customer Journey Analyticsにアップグレードする際にのみソースコネクタを使用する利点と欠点を理解するには、次の表の情報を使用します。

| メリット | デメリット |
|----------|---------|
| <ul><li>最も時間と手間がかからないアップグレードパス。 <p>データはすばやく簡単に Customer Journey Analytics に移行されます。</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>すべてのアップグレードパスにわたるレポートの[待ち時間](/help/technotes/guardrails.md#latencies)が最高レベル。 リアルタイムパーソナライゼーションのユースケースには最適化されていません。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**今後 Web SDKに移行するのは難しい**：最終的には、Experience Platform Web SDK が提供するメリットを利用したいと考えるようになります。 Experience Platform Web SDK の使用を開始するには、新しい実装を行う必要があります。</li><li>**スキーマで Analytics エクスペリエンスイベントのフィールドグループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。  これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li><li>**Adobe Analytics と Customer Journey Analytics の両方のライセンスが必要**：Analytics ソースコネクタを使用するには、Adobe Analytics と Customer Journey Analytics の両方のライセンスに対して支払う必要があります。</li></ul> |

{style="table-layout:auto"}

## 基本手順

Analytics ソースコネクタを Customer Journey Analytics の唯一の実装パスとして使用する場合は、[ソースコネクタを使用したデータの取り込みと使用](/help/data-ingestion/sources.md)で説明されている実装手順に従ってください。

