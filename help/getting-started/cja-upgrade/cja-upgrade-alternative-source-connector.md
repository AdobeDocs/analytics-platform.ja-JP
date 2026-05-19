---
title: Analytics ソースコネクタのみを使用した Customer Journey Analyticsへのアップグレード
description: Analytics ソースコネクタの作成とフィールドのマッピング方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
autotag-review: '2026-05-19T08:09:45.448Z'
TQID: 'https://experienceleague.adobe.com/KF-XUA12iIq0wGcSc4P-vGXQV56H5j-jKEgRsxLoUrI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 94%

---

# アップグレードの代替案：Customer Journey Analytics へのアップグレードに対する Analytics ソースコネクタのみの使用 {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Analytics ソースコネクタのみを使用する"
>abstract="（非推奨）Analytics ソースコネクタを、Customer Journey Analytics の唯一の実装パスとして使用できます。 <br><br>このオプションを使用すると、Customer Journey Analytics にデータをすばやく送信できるので、実装時間が節約されます。 ただし、待ち時間が長い、今後 Adobe Analytics から移行するのが難しいなど、様々な欠点があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

お勧めしませんが、Analytics ソースコネクタを Customer Journey Analytics の唯一の実装パスとして使用できます。 ただし、このタイプのアップグレードには固有のデメリットがあるので、アドビでは、Analytics ソースコネクタを Experience Platform Web SDK の新しい実装と組み合わせて使用することをお勧めします。 お勧めのアップグレードパスについて詳しくは、[Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパス](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)を参照してください。

## メリットとデメリット

Customer Journey Analyticsにアップグレードする際にのみソースコネクタを使用する利点と欠点を理解するには、次の表の情報を使用します。

| メリット | デメリット |
|----------|---------|
| <ul><li>最も時間がかかり、要求が厳しいアップグレードパス。 <p>すばやく簡単に Customer Journey Analytics へとデータを移行する。</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>すべてのアップグレードパスにわたるレポートの[待ち時間](/help/technotes/guardrails.md#latencies)が最高レベル。 リアルタイムパーソナライゼーションのユースケースには最適化されていません。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**今後 Web SDKに移行するのは難しい**：最終的には、Experience Platform Web SDK が提供するメリットを利用したいと考えるようになります。 Experience Platform Web SDK の使用を開始するには、新しい実装を行う必要があります。</li><li>**スキーマで Analytics エクスペリエンスイベントのフィールドグループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。  これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li><li>**Adobe Analytics と Customer Journey Analytics の両方のライセンスが必要**：Analytics ソースコネクタを使用するには、Adobe Analytics と Customer Journey Analytics の両方のライセンスに対して支払う必要があります。</li></ul> |

{style="table-layout:auto"}

## 基本手順

Analytics ソースコネクタを Customer Journey Analytics の唯一の実装パスとして使用する場合は、[ソースコネクタを使用したデータの取り込みと使用](/help/data-ingestion/sources.md)で説明されている実装手順に従ってください。

