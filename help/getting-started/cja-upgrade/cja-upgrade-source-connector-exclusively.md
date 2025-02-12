---
title: Analytics ソースコネクタを、Customer Journey Analyticsへのアップグレードにのみ使用します
description: Analytics ソースコネクタを作成しフィールドをマッピングする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 23%

---

# Analytics ソースコネクタを、Customer Journey Analyticsへのアップグレードにのみ使用します {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Analytics ソースコネクタのみを使用する"
>abstract="（推奨しません）他のAdobe Experience Platform サービスと統合したり、Analytics ソースコネクタを使用してAdobe Analyticsから移動したりすることはできません。 他のソースからデータを結び付けるには、ステッチが必要になる可能性があります。 このオプションを選択するには、アンケートの要件をすべて満たしている必要があります。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analyticsのアップグレードチェックリスト ](https://gigazelle.github.io/cja-ttv/) に関する質問に答える際は、このページの情報を使用してください。

お勧めはしませんが、Customer Journey Analytics ソースコネクタを、Analytics の唯一の実装パスとして使用することはできます。 ただし、このタイプのアップグレードには不利な点があることから、Adobeでは、Analytics ソースコネクタをExperience Platform Web SDKの新規実装と組み合わせて使用することをお勧めします。 この推奨アップグレードパスについて詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパス ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) を参照してください。

次の表の情報を使用して、ソースコネクタのみを使用する場合のメリットとデメリットを理解します。

Analytics ソースコネクタをCustomer Journey Analyticsの唯一の実装パスとして使用する場合は、[ ソースコネクタを使用したデータの取り込みと使用 ](/help/data-ingestion/sources.md) に記載されている実装手順に従ってください。

| メリット | デメリット |
|----------|---------|
| <ul><li>アップグレード・パスの所要時間と要件が最も短い。 <p>データはCustomer Journey Analyticsにすばやく簡単に移行されます。</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>すべてのアップグレードパスにわたるレポートで最高レベルの [ 待ち時間 ](/help/technotes/guardrails.md#latencies)。リアルタイムパーソナライゼーションのユースケース用に最適化されていません。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**今後 Web SDKに移行するのは難しい**：最終的には、Experience Platform Web SDKが提供するメリットを利用したいと考えるようになります。 Experience Platform Web SDKの使用を開始するには、新しい実装を行う必要があります。</li><li>**スキーマで Analytics Experience Event フィールド グループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li><li>**Adobe AnalyticsとCustomer Journey Analyticsの両方のライセンスが必要**:Analytics ソースコネクタを使用するには、Adobe AnalyticsとCustomer Journey Analyticsの両方の料金を支払う必要があります。</li></ul> |

{style="table-layout:auto"}
