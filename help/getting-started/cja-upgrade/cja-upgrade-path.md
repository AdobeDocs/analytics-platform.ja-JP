---
title: Customer Journey Analyticsアップグレードパスを選択
description: Customer Journey Analyticsへのアップグレード時に考えられるアップグレードパスの長所と短所を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '2420'
ht-degree: 0%

---

# 手順 2：アップグレードパスの選択

+++このセクションを展開すると、このページの情報が大きなアップグレードプロセスのどこに適合するかを確認できます。 以前のアップグレード手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のアップグレードタスクがすべて完了していることを確認してください。

このページの情報では、次の表で強調表示されている、アップグレードプロセスの手順 2 について説明します。

| アップグレードタスク | 詳細 |
|---------|----------|
| **手順 1: [アップグレードの概要](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analyticsへのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。 |
| <span class="preview">**手順 2：アップグレードパスの選択**</span> | <span class="preview">Customer Journey Analyticsへのアップグレードには様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。</span> |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| **手順 4: [履歴データを保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからのアップグレードや、新しいCustomer Journey Analyticsの実装にも当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Customer Journey Analyticsへのアップグレードを決定した後、組織に最適なアップグレードパスを決定する必要があります。

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに使用するパスは、次の要因によって変わります。

* 既存のAdobe Analyticsの実装

* 将来の目標

このページの情報を使用して、組織の現在の実装と将来の目標に最適なCustomer Journey Analyticsアップグレードパスを判断します。

組織に最適なアップグレードパスを決定するには、次の節を順番に参照する必要があります。

1. まず、 [使用可能なアップグレードパスについて](#understand-migration-methods).

1. その後、 [使用可能なアップグレードパスの評価](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. 最後に、 [各アップグレードパスのメリットとデメリットを比較検討する](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## アップグレードパスについて

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードには、様々なアップグレードパスがあります。

一般に、各アップグレードパスは、アップグレードの実行に必要な労力のレベルや、アップグレード完了後に達成される長期的な生存率が異なります。

次の表に、各アップグレードパス、その作業レベル、長期的な実行可能性を示します。

| アップグレードパス | 作業レベル | 長期的な生存率 |
|---------|----------|---------|
| **Experience PlatformWeb SDK の新しい実装**</br> Experience Platform Web SDK の新しい実装を行うことで、Customer Journey Analyticsの使用を開始できます。 これにより、Adobe Experience Platform Edge NetworkおよびCustomer Journey Analyticsへのデータ送信を開始できます。 <p>Web SDK をまだ使用していない組織の場合、このアップグレードパスは必要な手順が最も少ないため、データをEdge Networkに送信する際に最も簡単です。ただし、すべての作業が事前に行われる（XDM スキーマの作成など）ので、より大きな初期作業が必要です。</p><p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマを作成します。</li><li>Web SDK の実装</li><li>Platform にデータを送信します。</li></ol> | 高 | 高 |
| **Web SDK を使用するようにAdobe Analyticsの実装をアップグレードする**</br> Adobe Analytics実装がAppMeasurementまたは Analytics 拡張機能の場合は、Adobe Experience Platform Web SDK を使用してEdge NetworkおよびAdobe Analyticsへのデータ送信を開始してから、Customer Journey Analyticsに送信するように移行できます。<p>まだ Web SDK を使用していない組織にとって、これはデータをEdge Networkに取得する最も簡単でスムーズな方法です。より多くの手順が必要ですが、Adobe AnalyticsからCustomer Journey Analyticsへの体系的な移行を提供し、明確なマイルストーンを実現します。</p><p>基本的な手順は次のとおりです。</p><ol><li>既存のAdobe Analytics実装を Web SDK に移行し、Adobe Analyticsですべてが機能していることを検証します。</li><li>時間の経過に応じて、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li><li>Platform にデータを送信します。</li></ol> | 中等 | 高 |
| **既存のAdobe Analytics Web SDK 実装の設定**</br> Adobe Analytics実装で既にAdobe Experience Platform Web SDK を使用している場合は、最小限の労力でCustomer Journey Analyticsへのデータ送信を開始できます。<p>データを Platform に送信する前に、組織や使用するその他のCustomer Journey Analyticsアプリケーションの特定のニーズに合わせてAdobe Analytics スキーマを更新することを検討してください。</p><p>基本的な手順は次のとおりです。</p><ol><li>Customer Journey Analyticsへのデータ送信を開始します。<!-- What's involved here? Just point it at CJA? --></li><li>（オプション）時間に応じて、組織の XDM スキーマを作成します。</li><li>（条件付き） XDM スキーマを作成した場合、データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li></ol> | 低 | 高 |
| **Analytics ソースコネクタの使用**</br> Adobe Analyticsの実装がAppMeasurementまたは Analytics 拡張機能の場合、Customer Journey Analyticsでデータビューへのデータ送信を開始できます。<p>これは、データをCustomer Journey Analyticsに取得する最も簡単な方法ですが、長期的には最も実行可能でない方法です。</p> | 低 | 低 |

{style="table-layout:auto"}

次の図は、各アップグレードパスが労力レベルと長期実行可能性の観点でどの程度の割合になるかを視覚化するのに役立ちます。

![cja アップグレードパス](assets/cja-upgrade-path-chart.png)

## 現在のAdobe Analyticsの実装に基づいて、使用可能なアップグレードパスを評価する

Adobe Analyticsの実装の種類ごとに、すべてのアップグレードパスを使用できるわけではありません。

以下の情報を使用すると、組織に最も適したアップグレードパスを理解できます。

より具体的なアドバイス、ガイダンス、サポートが必要な場合は、Adobe担当者にお問い合わせください。

| 既存のAdobe Analyticsの実装 | 使用可能なアップグレードパス |
|---------|----------|
| AppMeasurement | <ul><li>Experience PlatformWeb SDK の新しい実装</li><li>Adobe Analyticsの Web SDK への移行</li><li>Analytics ソースコネクタ</li></ul> |
| Adobe Analytics 拡張機能 | <ul><li>Experience PlatformWeb SDK の新しい実装</li><li>Adobe Analyticsの Web SDK への移行</li><li>Analytics ソースコネクタ</li></ul> |
| Web SDK | <ul><li>データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を実装を設定します。</li></ul> |

{style="table-layout:auto"}

## 使用可能なアップグレードパスのメリットとデメリットを比較検討する

特定のアップグレードパスのメリットとデメリットは、既存のAdobe Analytics実装によって異なります。

以下の情報を使用してどのアップグレードパスが適切かを判断する前に、の情報を確認してください [アップグレードパスについて](#understand-migration-methods) まだの場合は、

### を使用したAdobe Analytics実装の場合：AppMeasurementおよびAdobe Analytics拡張機能

以下は、AppMeasurementまたはAdobe Analytics拡張機能を使用してAdobe Analyticsを実装している組織で使用できるアップグレードパスです。 各セクションを展開して、各アップグレードパスのメリットとデメリットを確認します。

#### アップグレードパス

+++Experience PlatformWeb SDK の新しい実装

| メリット | デメリット |
|----------|---------|
| <ul><li>**エクスペリエンスEdge Networkでデータをホストする利点をすべて提供します**: <p>その利点は次のとおりです。</p><ul><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>他のExperience Cloud製品（AJO、RTCDP など）間でAdobe Experience Cloud データ収集の実装を統合します</li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li></ul></li><li>**将来にわたって有効な**：今後の実装アップデートが容易になります。</li></ul> | <ul><li>**新規の実装が必要です**：新しい実装をゼロから行う必要があるということは、次のような欠点を意味します。 </li><ul><li>**時間がかかる**：これは、新しい実装からやり直す必要があるため、最も時間がかかり、要求の厳しいアップグレードパスです。</li><li>**XDM で完全なスキーマを再作成する必要があります**:Web SDK の実装を開始する前に、XDM で完全なスキーマを再作成する必要があります。</li><li>**ルールとデータ要素を再作成する必要があります**:Web SDK の実装を開始する前に、ルール条件とデータ要素をAdobe Analyticsの実装から再作成する必要があります。</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Adobe AnalyticsをExperience PlatformWeb SDK に移行する

| メリット | デメリット |
|----------|---------|
| <ul><li>**エクスペリエンスEdge Networkでデータをホストする利点をすべて提供します**: <p>その利点は次のとおりです。</p><ul><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>他のExperience Cloud製品（AJO、RTCDP など）間でAdobe Experience Cloud データ収集の実装を統合します</li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li></ul><li>**既存の実装を使用**：このアプローチでは、いくつかの実装変更が必要ですが、ゼロから完全に新しい実装を行う必要はありません。 既存のAdobe Analytics レポートに影響を与えることなく、実装ロジックに対する最小限の変更で既存のデータレイヤーとコードを使用できます。</li><li>**組織の XDM スキーマを後で作成する柔軟性を提供します**：既存のAdobe Analytics実装を移行して Web SDK を使用し、Adobe Analyticsですべてが機能していることを検証してから、XDM スキーマを作成できます。 この柔軟性により、Customer Journey Analyticsに対するより体系的で思慮深いアップグレードが可能になります。</li></ul> | <ul><li>**Platform にデータを送信するには、マッピングが必要です**:Customer Journey Analyticsを使用する準備が整ったら、Adobe Experience Platformのデータセットにデータを送信する必要があります。 このアクションでは、データオブジェクト内のすべてのフィールドが、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリである必要があります。 マッピングは、このワークフローに対して 1 回だけ行う必要があります。実装の変更は必要ありません。 ただし、XDM オブジェクトでデータを送信する場合に必要ない追加の手順です。</li><li>**技術的債務**：このアプローチは、既存の実装を修正した形式を使用するので、実装ロジックを追跡し、必要に応じて将来変更を実行するのが難しい場合があります。 </li></ul> |

{style="table-layout:auto"}

+++

+++Analytics ソースコネクタの使用

| メリット | デメリット |
|----------|---------|
| <ul><li>アップグレード・パスの所要時間と要件が最も短い。 <p>最小限の投資でデータを迅速にCustomer Journey Analyticsに移行</p></li></ul> | <ul><li>**データがEdge Networkに送信されない**: <p>その結果、次のようなデメリットが生じます。</p><ul><li>最高レベルの [待ち時間](/help/technotes/guardrails.md#latencies) （すべてのアップグレードパスにわたるレポートで、リアルタイムパーソナライゼーションのユースケース向けに最適化されていない）。</li><li>データを他のAdobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analyticsのみに制限されます</li><li>Adobe Analyticsの命名法（prop、eVar、イベントなど）に依存する</li></ul><li>**今後 Web SDK に移行するのは困難です**: </li><li>**スキーマ内で Analytics エクスペリエンスイベントフィールドグループを使用します**：このフィールドグループには、Customer Journey Analyticsスキーマに必要のない多くのAdobe Analytics イベントが追加されます。  これにより、Customer Journey Analyticsに必要なスキーマよりも、より雑然とした複雑なスキーマが生じる可能性があります。</li></ul> |

{style="table-layout:auto"}

+++

### Web SDK を使用したAdobe Analytics実装の場合：

Experience Platform Web SDK を使用してAdobe Analyticsを実装している組織は、次のアップグレードパスを利用できます。

このアップグレードパスを選択する場合は、スキーマも選択する必要があります。

#### アップグレードパス

+++データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を実装を設定します

| メリット | デメリット |
|----------|---------|
| Adobe Analytics実装で既に Web SDK を使用している場合は、このアップグレードパスをお勧めします。<ul><li>**エクスペリエンスEdge Networkでデータをホストする利点をすべて提供します**: <p>その利点は次のとおりです。</p><ul><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>他のExperience Cloud製品（AJO、RTCDP など）間でAdobe Experience Cloud データ収集の実装を統合します</li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li></ul><li>**既存の実装を使用**：このアプローチでは、いくつかの実装変更が必要ですが、ゼロから完全に新しい実装を行う必要はありません。 既存のAdobe Analytics レポートに影響を与えることなく、実装ロジックに対する最小限の変更で既存のデータレイヤーとコードを使用できます。</li><li>**XDM スキーマを使用するためのオプションを提供します**：既存のAdobe Analytics スキーマを使用するか、XDM スキーマを作成し、データオブジェクトのフィールドを XDM スキーマにマッピングするかを選択できます。 [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、必要なフィールドを定義し、関連するフィールドのみを定義する柔軟なスキーマです。 <p>独自の XDM スキーマを使用する利点について詳しくは、以下の「独自の XDM スキーマの使用」を参照してください。</p></li><li>**ルールとデータ要素を保持**：新しいルールアクションが必要になりますが、最小限の変更で既存のデータ要素とルール条件を再利用できます。</li><li>**将来にわたって有効な**：独自の XDM スキーマを使用する場合は、後で実装を更新する方が簡単です。</li></ul> | なし |

{style="table-layout:auto"}

+++

#### スキーマを選択

データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK 実装を設定できるアップグレードパスを選択した場合は、使用するスキーマを選択できます。

既存のAdobe Analytics スキーマを使用するか、または独自の XDM スキーマに更新して、他の Platform サービスを使用し始める際に組織のニーズに合わせることができます。

+++Adobe Analytics Web SDK 実装でAdobe Analytics スキーマを使用する

| メリット | デメリット |
|----------|---------|
| <p>Adobe Analytics スキーマを使用する場合の利点は次のとおりです。</p><ul><li>アップグレードが容易<p>Adobe Experience Platform Web SDK を使用して既にAdobe Analyticsにデータを送信している場合は、データストリームにサービスを追加して、Adobe Experience Platformにデータを送信できます（Customer Journey Analytics設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用するデメリットには、次のものがあります。</p><ul><li>Adobe Analytics スキーマの使用は、他の Platform アプリケーションとの使用方法に関して制限を受けませんが、結果的にスキーマは、そうでない場合よりも複雑になります。 これは、Adobe Analytics スキーマには、Adobe Analyticsに固有で組織で使用される可能性の低いオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるには、何千もの未使用のフィールドをふるいにかける必要があります。</p></li></ul> |

+++

+++Adobe Analytics Web SDK 実装で独自の XDM スキーマを使用する

| メリット | デメリット |
|----------|---------|
| <ul><p>独自の XDM スキーマに更新する利点は次のとおりです。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマ。</li><p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるために、何千もの未使用フィールドを調べる必要はありません。</p></ul> | <p>独自の XDM スキーマに更新するデメリットには、次のものがあります。</p><ul><li>スキーマの更新は時間がかかるプロセスであり、Customer Journey Analyticsへのデータの送信を開始する前に行う必要があります。</li></ul> |

+++

## 次に、Adobe Experience Platformにデータを送信します

上記の情報を使用してアップグレードパスを選択した後、次の方法を学習します [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md) 選択したアップグレードパスによって異なります。
