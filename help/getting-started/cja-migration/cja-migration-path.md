---
title: Customer Journey Analyticsの移行パスを選択
description: Customer Journey Analyticsへの移行時に考えられる移行パスの長所と短所を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 1c789264a9867279f58a3ad139207fec8db29c1b
workflow-type: tm+mt
source-wordcount: '2422'
ht-degree: 0%

---

# 手順 2：移行パスの選択

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認してください。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている、移行の手順 2 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| <span class="preview">**手順 2：移行パスの選択**</span> | <span class="preview">Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。</span> |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択した移行パスによって異なります。 |
| **手順 4: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | Customer Journey Analyticsプロセスのこの時点では、移行に使用する準備が整う前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからの移行と、新しいCustomer Journey Analytics実装に当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Customer Journey Analyticsへの移行を決定した後、組織に最適な移行パスを決定する必要があります。

Adobe AnalyticsからCustomer Journey Analyticsへの移行に使用するパスは、次の要因によって決まります。

* 既存のAdobe Analyticsの実装

* 将来の目標

このページの情報を使用して、組織の現在の実装と将来の目標に最適なCustomer Journey Analytics移行パスを判断します。

組織に最適な移行パスを決定するには、次の節を順番に読む必要があります。

1. まず、 [使用可能な移行パスについて](#understand-migration-methods).

1. その後、 [使用可能な移行パスの評価](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. 最後に、 [各移行パスのメリットとデメリットを比較検討する](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## 移行パスについて

Adobe AnalyticsからCustomer Journey Analyticsへの移行には、様々な移行パスがあります。

一般に、各移行パスは、移行の実行に必要な労力のレベルや、移行完了後に達成される長期的な実行可能性が異なります。

次の表に、各移行パス、その作業レベルおよび長期的な実行可能性を示します。

| 移行パス | 作業レベル | 長期的な生存率 |
|---------|----------|---------|
| **Experience PlatformWeb SDK の新しい実装**</br>&#x200B;これは技術的にはExperience Platformではありませんが、移行 Web SDK の新しい実装を行うことで、Customer Journey Analyticsの使用を開始できます。 これにより、Adobe Experience Platform Edge NetworkおよびCustomer Journey Analyticsへのデータ送信を開始できます。 <p>Web SDK をまだ使用していない組織の場合、この移行パスは必要な手順が最も少ないため、データをEdge Networkに取り込む際に最も簡単です。ただし、すべての作業が事前に行われる（XDM スキーマの作成など）ので、より大きな初期作業が必要です。</p><p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマを作成します。</li><li>Web SDK の実装</li><li>Platform にデータを送信します。</li></ol> | 高 | 高 |
| **Web SDK を使用するようにAdobe Analytics実装を移行する**</br> Adobe Analytics実装がAppMeasurementまたは Analytics 拡張機能の場合は、Adobe Experience Platform Web SDK を使用してEdge NetworkおよびAdobe Analyticsへのデータ送信を開始してから、Customer Journey Analyticsに送信するように移行できます。<p>まだ Web SDK を使用していない組織にとって、これはデータをEdge Networkに取得する最も簡単でスムーズな方法です。より多くの手順が必要ですが、Adobe AnalyticsからCustomer Journey Analyticsへの体系的な移行を提供し、明確なマイルストーンを実現します。</p><p>基本的な手順は次のとおりです。</p><ol><li>既存のAdobe Analytics実装を Web SDK に移行し、Adobe Analyticsですべてが機能していることを検証します。</li><li>時間の経過に応じて、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li><li>Platform にデータを送信します。</li></ol> | 中等 | 高 |
| **既存のAdobe Analytics Web SDK 実装の設定**</br> Adobe Analytics実装で既にAdobe Experience Platform Web SDK を使用している場合は、最小限の労力でCustomer Journey Analyticsへのデータ送信を開始できます。<p>データを Platform に送信する前に、組織や使用するその他のCustomer Journey Analyticsアプリケーションの特定のニーズに合わせてAdobe Analytics スキーマを更新することを検討してください。</p><p>基本的な手順は次のとおりです。</p><ol><li>Customer Journey Analyticsへのデータ送信を開始します。<!-- What's involved here? Just point it at CJA? --></li><li>（オプション）時間に応じて、組織の XDM スキーマを作成します。</li><li>（条件付き） XDM スキーマを作成した場合、データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li></ol> | 低 | 高 |
| **Analytics ソースコネクタの使用**</br> Adobe Analyticsの実装がAppMeasurementまたは Analytics 拡張機能の場合、Customer Journey Analyticsでデータビューへのデータ送信を開始できます。<p>これは、データをCustomer Journey Analyticsに取得する最も簡単な方法ですが、長期的には最も実行可能でない方法です。</p> | 低 | 低 |

{style="table-layout:auto"}

次の図を使用して、各移行パスが作業レベルと長期的な実行可能性の観点でどの程度の割合になるかを視覚化します。

![cja 移行パス](assets/cja-migration-methods.png)

## 現在のAdobe Analyticsの実装に基づいて、使用可能な移行パスを評価する

Adobe Analyticsの実装の種類ごとに、すべての移行パスを使用できるわけではありません。

以下の情報を使用して、組織に最も適した移行パスを理解します。

より具体的なアドバイス、ガイダンス、サポートが必要な場合は、Adobe担当者にお問い合わせください。

| 既存のAdobe Analyticsの実装 | 使用可能な移行パス |
|---------|----------|
| AppMeasurement | <ul><li>Experience PlatformWeb SDK の新しい実装</li><li>Adobe Analyticsの Web SDK への移行</li><li>Analytics ソースコネクタ</li></ul> |
| Adobe Analytics 拡張機能 | <ul><li>Experience PlatformWeb SDK の新しい実装</li><li>Adobe Analyticsの Web SDK への移行</li><li>Analytics ソースコネクタ</li></ul> |
| Web SDK | <ul><li>データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を実装を設定します。</li></ul> |

{style="table-layout:auto"}

## 使用可能な移行パスのメリットとデメリットを比較検討する

特定の移行パスのメリットとデメリットは、既存のAdobe Analytics実装によって異なります。

以下の情報を使用してどの移行パスが適切かを判断する前に、の情報を確認してください [移行パスについて](#understand-migration-methods) まだの場合は、

### を使用したAdobe Analytics実装の場合：AppMeasurementおよびAdobe Analytics拡張機能

以下は、AppMeasurementまたはAdobe Analytics拡張機能を使用してAdobe Analyticsを実装している組織で使用できる移行パスです。 各セクションを展開して、各移行パスのメリットとデメリットを確認します。

#### 移行パス

+++Experience PlatformWeb SDK の新しい実装

| メリット | デメリット |
|----------|---------|
| <ul><li>**エクスペリエンスEdge Networkでデータをホストする利点をすべて提供します**: <p>その利点は次のとおりです。</p><ul><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>他のExperience Cloud製品（AJO、RTCDP など）間でAdobe Experience Cloud データ収集の実装を統合します</li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li></ul></li><li>**将来にわたって有効な**：今後の実装アップデートが容易になります。</li></ul> | <ul><li>**新規の実装が必要です**：新しい実装をゼロから行う必要があるということは、次のような欠点を意味します。 </li><ul><li>**時間がかかる**：これは、新しい実装からやり直す必要があるため、最も時間がかかり、要求の厳しい移行パスです。</li><li>**XDM で完全なスキーマを再作成する必要があります**:Web SDK の実装を開始する前に、XDM で完全なスキーマを再作成する必要があります。</li><li>**ルールとデータ要素を再作成する必要があります**:Web SDK の実装を開始する前に、ルール条件とデータ要素をAdobe Analyticsの実装から再作成する必要があります。</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Adobe AnalyticsをExperience PlatformWeb SDK に移行する

| メリット | デメリット |
|----------|---------|
| <ul><li>**エクスペリエンスEdge Networkでデータをホストする利点をすべて提供します**: <p>その利点は次のとおりです。</p><ul><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>他のExperience Cloud製品（AJO、RTCDP など）間でAdobe Experience Cloud データ収集の実装を統合します</li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li></ul><li>**既存の実装を使用**：このアプローチでは、いくつかの実装変更が必要ですが、ゼロから完全に新しい実装を行う必要はありません。 既存のAdobe Analytics レポートに影響を与えることなく、実装ロジックに対する最小限の変更で既存のデータレイヤーとコードを使用できます。</li><li>**組織の XDM スキーマを後で作成する柔軟性を提供します**：既存のAdobe Analytics実装を移行して Web SDK を使用し、Adobe Analyticsですべてが機能していることを検証してから、XDM スキーマを作成できます。 この柔軟性により、より体系的で思慮深い移行が可能になります。</li></ul> | <ul><li>**Platform にデータを送信するには、マッピングが必要です**:Customer Journey Analyticsを使用する準備が整ったら、Adobe Experience Platformのデータセットにデータを送信する必要があります。 このアクションでは、データオブジェクト内のすべてのフィールドが、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリである必要があります。 マッピングは、このワークフローに対して 1 回だけ行う必要があります。実装の変更は必要ありません。 ただし、XDM オブジェクトでデータを送信する場合に必要ない追加の手順です。</li><li>**技術的債務**：このアプローチは、既存の実装を修正した形式を使用するので、実装ロジックを追跡し、必要に応じて将来変更を実行するのが難しい場合があります。 </li></ul> |

{style="table-layout:auto"}

+++

+++Analytics ソースコネクタの使用

| メリット | デメリット |
|----------|---------|
| <ul><li>最も時間がかかり、要求の厳しい移行パス。 <p>最小限の投資でデータを迅速にCustomer Journey Analyticsに移行</p></li></ul> | <ul><li>**データがEdge Networkに送信されない**: <p>その結果、次のようなデメリットが生じます。</p><ul><li>最高レベルの [待ち時間](/help/admin/guardrails.md#latencies) （すべての移行パスにわたるレポート作成）。リアルタイムパーソナライゼーションのユースケース向けに最適化されていない。</li><li>データを他のAdobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analyticsのみに制限されます</li><li>Adobe Analyticsの命名法（prop、eVar、イベントなど）に依存する</li></ul><li>**今後 Web SDK に移行するのは困難です**: </li><li>**スキーマ内で Analytics エクスペリエンスイベントフィールドグループを使用します**：このフィールドグループには、Customer Journey Analyticsスキーマに必要のない多くのAdobe Analytics イベントが追加されます。  これにより、Customer Journey Analyticsに必要なスキーマよりも、より雑然とした複雑なスキーマが生じる可能性があります。</li></ul> |

{style="table-layout:auto"}

+++

### Web SDK を使用したAdobe Analytics実装の場合：

Experience PlatformWeb SDK を使用してAdobe Analyticsを実装している組織では、次の移行パスを使用できます。

この移行パスを選択する際は、スキーマも選択する必要があります。

#### 移行パス

+++データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を実装を設定します

| メリット | デメリット |
|----------|---------|
| Adobe Analytics実装で既に Web SDK を使用している場合は、この移行パスをお勧めします。<ul><li>**エクスペリエンスEdge Networkでデータをホストする利点をすべて提供します**: <p>その利点は次のとおりです。</p><ul><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>他のExperience Cloud製品（AJO、RTCDP など）間でAdobe Experience Cloud データ収集の実装を統合します</li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li></ul><li>**既存の実装を使用**：このアプローチでは、いくつかの実装変更が必要ですが、ゼロから完全に新しい実装を行う必要はありません。 既存のAdobe Analytics レポートに影響を与えることなく、実装ロジックに対する最小限の変更で既存のデータレイヤーとコードを使用できます。</li><li>**XDM スキーマを使用するためのオプションを提供します**：既存のAdobe Analytics スキーマを使用するか、XDM スキーマを作成し、データオブジェクトのフィールドを XDM スキーマにマッピングするかを選択できます。 [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、必要なフィールドを定義し、関連するフィールドのみを定義する柔軟なスキーマです。 <p>独自の XDM スキーマを使用する利点について詳しくは、以下の「独自の XDM スキーマの使用」を参照してください。</p></li><li>**ルールとデータ要素を保持**：新しいルールアクションが必要になりますが、最小限の変更で既存のデータ要素とルール条件を再利用できます。</li><li>**将来にわたって有効な**：独自の XDM スキーマを使用する場合は、後で実装を更新する方が簡単です。</li></ul> | なし |

{style="table-layout:auto"}

+++

#### スキーマを選択

データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を設定できる移行パスを選択した場合は、使用するスキーマを選択できます。

既存のAdobe Analytics スキーマを使用するか、または独自の XDM スキーマに更新して、他の Platform サービスを使用し始める際に組織のニーズに合わせることができます。

+++Adobe Analytics Web SDK 実装でAdobe Analytics スキーマを使用する

| メリット | デメリット |
|----------|---------|
| <p>Adobe Analytics スキーマを使用する場合の利点は次のとおりです。</p><ul><li>容易な移行<p>Adobe Experience Platform Web SDK を使用して既にAdobe Analyticsにデータを送信している場合は、データストリームにサービスを追加して、Adobe Experience Platformにデータを送信できます（Customer Journey Analytics設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用するデメリットには、次のものがあります。</p><ul><li>Adobe Analytics スキーマの使用は、他の Platform アプリケーションとの使用方法に関して制限を受けませんが、結果的にスキーマは、そうでない場合よりも複雑になります。 これは、Adobe Analytics スキーマには、Adobe Analyticsに固有で組織で使用される可能性の低いオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるには、何千もの未使用のフィールドをふるいにかける必要があります。</p></li></ul> |

+++

+++Adobe Analytics Web SDK 実装で独自の XDM スキーマを使用する

| メリット | デメリット |
|----------|---------|
| <ul><p>独自の XDM スキーマに更新する利点は次のとおりです。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマ。</li><p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるために、何千もの未使用フィールドを調べる必要はありません。</p></ul> | <p>独自の XDM スキーマに更新するデメリットには、次のものがあります。</p><ul><li>スキーマの更新は時間がかかるプロセスであり、Customer Journey Analyticsへのデータの送信を開始する前に行う必要があります。</li></ul> |

+++

## 次に、Adobe Experience Platformにデータを送信します

上記の情報を使用して移行パスを選択したら、次の方法を学習します [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 選択した移行パスによって異なります。
