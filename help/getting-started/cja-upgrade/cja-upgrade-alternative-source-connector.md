---
title: Customer Journey Analytics へのアップグレードに対する Analytics ソースコネクタのみの使用
description: Analytics ソースコネクタを作成しフィールドをマッピングする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 41%

---

# アップグレードの代替案：Customer Journey Analytics へのアップグレードに対する Analytics ソースコネクタのみの使用 {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Analytics ソースコネクタのみの使用"
>abstract="（非推奨）Analytics ソースコネクタを、Customer Journey Analytics の唯一の実装パスとして使用できます。<br><br>このオプションを使用すると、Customer Journey Analytics にデータをすばやく送信できるので、実装時間が節約されます。ただし、待ち時間が長い、今後 Adobe Analytics から移行するのが難しいなど、様々な欠点があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

お勧めはしませんが、Customer Journey Analytics ソースコネクタを、Analytics の唯一の実装パスとして使用することはできます。 ただし、このタイプのアップグレードには不利な点があることから、Adobeでは、Analytics ソースコネクタをExperience Platform Web SDKの新規実装と組み合わせて使用することをお勧めします。 この推奨アップグレードパスについて詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパス ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) を参照してください。

## メリットとデメリット

以下の表に示す情報を使用して、Customer Journey Analyticsへのアップグレード時にのみソースコネクタを使用する場合のメリットとデメリットを理解します。

| メリット | デメリット |
|----------|---------|
| <ul><li>アップグレード・パスの所要時間と要件が最も短い。 <p>データはCustomer Journey Analyticsにすばやく簡単に移行されます。</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>すべてのアップグレードパスにわたるレポートで最高レベルの [ 待ち時間 ](/help/technotes/guardrails.md#latencies)。リアルタイムパーソナライゼーションのユースケース用に最適化されていません。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**今後 Web SDKに移行するのは難しい**：最終的には、Experience Platform Web SDKが提供するメリットを利用したいと考えるようになります。 Experience Platform Web SDKの使用を開始するには、新しい実装を行う必要があります。</li><li>**スキーマで Analytics Experience Event フィールド グループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li><li>**Adobe AnalyticsとCustomer Journey Analyticsの両方のライセンスが必要**:Analytics ソースコネクタを使用するには、Adobe AnalyticsとCustomer Journey Analyticsの両方の料金を支払う必要があります。</li></ul> |

{style="table-layout:auto"}

## 基本手順

Analytics ソースコネクタをCustomer Journey Analyticsの唯一の実装パスとして使用する場合は、[ ソースコネクタを使用したデータの取り込みと使用 ](/help/data-ingestion/sources.md) に記載されている実装手順に従ってください。

