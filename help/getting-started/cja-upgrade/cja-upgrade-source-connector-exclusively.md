---
title: Analytics ソースコネクタを、Customer Journey Analyticsへのアップグレードにのみ使用してください
description: Analytics ソースコネクタを作成しフィールドをマッピングする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 07570641949e17d30b7f9f5b38eb95c29c5176c0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 27%

---

# Analytics ソースコネクタを、Customer Journey Analyticsへのアップグレードにのみ使用してください

>[!NOTE]
> 
>[Customer Journey Analytics アップグレード チェックリスト ](https://gigazelle.github.io/cja-ttv/) の質問に答える際は、このページの情報を使用してください。

お勧めはしませんが、Customer Journey Analytics用の唯一の実装パスとして Analytics ソースコネクタを使用できます。 ただし、このタイプのアップグレードには固有の欠点があるため、Adobeでは、Analytics ソースコネクタをExperience Platform Web SDK の新規実装と組み合わせて使用することをお勧めします。 この推奨アップグレードパスについて詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパス ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) を参照してください。

ソースコネクタのみを使用する場合のメリットとデメリットを理解するには、次の情報を使用します。

| メリット | デメリット |
|----------|---------|
| <ul><li>アップグレード・パスの所要時間と要件が最も短い。 <p>データは迅速かつ容易にCustomer Journey Analyticsに移行されます。</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>すべてのアップグレードパスにわたるレポートで最高レベルの [ 待ち時間 ](/help/technotes/guardrails.md#latencies)。リアルタイムパーソナライゼーションのユースケース用に最適化されていません。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**今後、Web SDK に移行するのは難しい**：最終的には、Experience Platform Web SDK が提供する利点にアクセスする必要が生じる可能性があります。 Experience PlatformWeb SDK の使用を開始するには、新しい実装を行う必要があります。</li><li>**スキーマで Analytics Experience Event フィールド グループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li><li>**Adobe AnalyticsとCustomer Journey Analyticsの両方のライセンスが必要**:Analytics ソースコネクタを使用するには、Adobe AnalyticsとCustomer Journey Analyticsの両方の費用を支払う必要があります。</li></ul> |

{style="table-layout:auto"}

