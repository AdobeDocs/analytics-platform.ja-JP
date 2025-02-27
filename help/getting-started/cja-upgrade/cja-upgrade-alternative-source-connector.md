---
title: Analytics ソースコネクタを、Customer Journey Analyticsへのアップグレードにのみ使用します
description: Analytics ソースコネクタを作成しフィールドをマッピングする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 23%

---

# 代替アップグレード：Analytics ソースコネクタを使用して、Customer Journey Analyticsにのみアップグレードします {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Analytics ソースコネクタのみを使用する"
>abstract="（非推奨）Customer Journey Analytics ソースコネクタを、Analytics の唯一の実装パスとして使用できます。 <br><br> このオプションを使用すると、データをCustomer Journey Analyticsにすばやく送信できるので、実装時間を節約できます。 ただし、待ち時間の増加や今後のAdobe Analyticsからの移行の困難さなど、様々な欠点があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

お勧めはしませんが、Customer Journey Analytics ソースコネクタを、Analytics の唯一の実装パスとして使用することはできます。 ただし、このタイプのアップグレードには不利な点があることから、Adobeでは、Analytics ソースコネクタをExperience Platform Web SDKの新規実装と組み合わせて使用することをお勧めします。 この推奨アップグレードパスについて詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパス ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) を参照してください。

以下の表に示す情報を使用して、Customer Journey Analyticsへのアップグレード時にのみソースコネクタを使用する場合のメリットとデメリットを理解します。

Analytics ソースコネクタをCustomer Journey Analyticsの唯一の実装パスとして使用する場合は、[ ソースコネクタを使用したデータの取り込みと使用 ](/help/data-ingestion/sources.md) に記載されている実装手順に従ってください。

| メリット | デメリット |
|----------|---------|
| <ul><li>アップグレード・パスの所要時間と要件が最も短い。 <p>データはCustomer Journey Analyticsにすばやく簡単に移行されます。</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>すべてのアップグレードパスにわたるレポートで最高レベルの [ 待ち時間 ](/help/technotes/guardrails.md#latencies)。リアルタイムパーソナライゼーションのユースケース用に最適化されていません。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**今後 Web SDKに移行するのは難しい**：最終的には、Experience Platform Web SDKが提供するメリットを利用したいと考えるようになります。 Experience Platform Web SDKの使用を開始するには、新しい実装を行う必要があります。</li><li>**スキーマで Analytics Experience Event フィールド グループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li><li>**Adobe AnalyticsとCustomer Journey Analyticsの両方のライセンスが必要**:Analytics ソースコネクタを使用するには、Adobe AnalyticsとCustomer Journey Analyticsの両方の料金を支払う必要があります。</li></ul> |

{style="table-layout:auto"}
