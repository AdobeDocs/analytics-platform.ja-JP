---
title: Customer Journey Analyticsの移行パスを選択
description: Customer Journey Analyticsへの移行時に考えられる移行パスのメリットとデメリットを説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 7d17ef31053bbf0d480bfa923fc961aeba4fc15e
workflow-type: tm+mt
source-wordcount: '1965'
ht-degree: 2%

---

# 手順 2：移行パスの選択

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

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
| **Experience PlatformWeb SDK の新しい実装**</br>&#x200B;これは技術的には移行ではありませんが、Experience Platform Web SDK の新しい実装を行い、Adobe Experience Platform Edge Networkへのデータ送信を開始することで、Customer Journey Analyticsの使用を開始できます。 <p>Web SDK をまだ使用していない組織の場合、この移行パスは必要な手順が最も少ないため、データをEdge Networkに取り込む際に最も簡単です。ただし、すべての作業が事前に行われる（XDM スキーマの作成など）ので、より大きな初期作業が必要です。</p><p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマを作成します。</li><li>Web SDK の実装</li><li>Platform にデータを送信します。</li></ol> | 高 | 高 |
| **Web SDK を使用するようにAdobe Analytics実装を移行する**</br> Adobe Analytics実装がAppMeasurementまたは Analytics 拡張機能の場合は、Adobe Experience Platform Web SDK を使用してEdge NetworkおよびAdobe Analyticsへのデータ送信を開始してから、Customer Journey Analyticsに送信するように移行できます。<p>これは、データをEdge Networkに取り込む最も簡単でスムーズな方法です。より多くの手順が必要ですが、Adobe AnalyticsからCustomer Journey Analyticsへのより計画的な移行が可能になり、明確なマイルストーンが得られます。</p><p>基本的な手順は次のとおりです。</p><ol><li>既存のAdobe Analytics実装を Web SDK に移行し、Adobe Analyticsですべてが機能していることを検証します。</li><li>時間の経過に応じて、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li><li>Platform にデータを送信します。</li></ol> | 中等 | 高 |
| **既存のAdobe Analytics Web SDK 実装の設定**</br> Adobe Analytics実装で既にAdobe Experience Platform Web SDK を使用している場合は、最小限の労力でCustomer Journey Analyticsへのデータ送信を開始できます。<p>データを Platform に送信する前に、Customer Journey Analyticsおよび使用するその他のAdobe Analytics アプリケーションの具体的なニーズに合わせて Platform スキーマを更新することを検討してください。</p><p>基本的な手順は次のとおりです。</p><ol><li>Customer Journey Analyticsへのデータ送信を開始します。<!-- What's involved here? Just point it at CJA? --></li><li>（オプション）時間に応じて、組織の XDM スキーマを作成します。</li><li>（条件付き） XDM スキーマを作成した場合、データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li></ol> | 低 | 高 |
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

**移行パス：**

+++Experience PlatformWeb SDK の新しい実装

| メリット | デメリット |
|----------|---------|
| <ul><li>XDM スキーマ、柔軟なスキーマを使用して必要なフィールドを定義し、関連するフィールドのみを定義します（Adobe Analytics Experience Event フィールドグループから離れることができます）</li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li><li>文字制限に関する問題がありません（prop の場合は 100 文字）</li><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>将来の拡張にも対応（最新の機能をすべて搭載）</li><li>Adobe Experience Cloud データ収集用のタグを他のExperience Cloud製品（AJO、RTCDP など）間で統合します</li><li>[ファーストパーティのデバイス ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=ja) で訪問者識別の精度を高めます</li></ul> | <ul><li>最も時間がかかり要求の厳しい移行パス<p>Web SDK の実装を開始するには、XDM で完全なスキーマを再作成する必要があります</p></li></ul> |

{style="table-layout:auto"}

+++

+++Adobe Analyticsの Web SDK への移行

| メリット | デメリット |
|----------|---------|
| <ul><li>既存のAdobe Analyticsのレポートに影響を与えることなく、Web SDK に移行できます。</li><li>Analytics 実装で既に設定されているルールとデータ要素を保持します（Adobe Analytics拡張機能を使用する組織用）。</li><li>組織の XDM スキーマを後で作成する柔軟性を提供：必要なフィールドと、関連するフィールドのみを定義する柔軟なスキーマ。</br>Adobe Experience PlatformのAdobe Analytics エクスペリエンスイベントフィールドグループは必要ありません。 <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Adobe Analyticsの用語（prop、eVar、イベントなど）に依存しません</li><li>文字制限に関する問題がありません（prop の場合は 100 文字）</li><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>将来の拡張にも対応（最新の機能をすべて搭載）</li><li>Adobe Experience Cloud データ収集用のタグを他のExperience Cloud製品（AJO、RTCDP など）間で統合します</li><li>[ファーストパーティのデバイス ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=ja) で訪問者識別の精度を高めます</li></ul> | <ul><li>は、データストリームマッピングを使用して、将来のある時点で XDM スキーマに準拠する必要があります。</li><li>多少の技術的負債が生じる。 例えば、従来のAppMeasurementや Analytics 拡張機能コードは残すことができます。 </li></ul> |

{style="table-layout:auto"}

+++

+++Analytics ソースコネクタの使用

| メリット | デメリット |
|----------|---------|
| <ul><li>最も時間がかかり、要求の厳しい移行パス。 <p>最小限の投資でデータを迅速にCustomer Journey Analyticsに移行</p></li></ul> | <ul><li>データは、Edge Networkに送信されず、他のAdobe Experience Platform アプリケーションと共有できません。Customer Journey Analyticsのみに制限されます<li>今後 Web SDK に移行するのは困難です</li><li>スキーマで Analytics エクスペリエンスイベントフィールドグループを使用します。</br>このフィールドグループは、Customer Journey Analyticsスキーマに不要な多くのAdobe Analytics イベントを追加します。  これにより、Customer Journey Analyticsに必要なスキーマよりも、より雑然とした複雑なスキーマが生じる可能性があります。</li><li>最高レベルの [待ち時間](/help/admin/guardrails.md#latencies) すべての実装方法で</li></ul> |

{style="table-layout:auto"}

+++

### Web SDK を使用したAdobe Analytics実装の場合：

Experience PlatformWeb SDK を使用してAdobe Analyticsを実装している組織では、次の移行パスを使用できます。

**移行パス：**

+++データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を実装を設定します

| メリット | デメリット |
|----------|---------|
| Adobe Analytics実装で既に Web SDK を使用している場合は、この移行パスをお勧めします。 <p>この実装方法を使用する場合、既存のAdobe Analytics スキーマを使用するか、他の Platform アプリケーションを使用し始める際に組織のニーズに合わせて XDM スキーマを更新するかを選択できます。</p><p>**Adobe Analytics スキーマの使用**</p><p>Adobe Analytics スキーマを使用する場合の利点は次のとおりです。</p><ul><li>容易な移行<p>Adobe Experience Platform Web SDK を使用して既にAdobe Analyticsにデータを送信している場合は、データストリームにサービスを追加して、Adobe Experience Platformにデータを送信できます（Customer Journey Analytics設定で使用できます）。</p></li></ul><p>Adobe Analytics スキーマを使用するデメリットには、次のものがあります。</p><ul><li>Adobe Analytics スキーマの使用は、他の Platform アプリケーションとの使用方法に関して制限を受けませんが、結果的にスキーマは、そうでない場合よりも複雑になります。 これは、Adobe Analytics スキーマには、Adobe Analyticsに固有で、組織で使用されない可能性の高いオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるには、何千もの未使用のフィールドをふるいにかける必要があります。</p></li></ul><p>**XDM スキーマの使用**</p><p>XDM スキーマを更新する利点は次のとおりです。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマ。</li><p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるために、何千もの未使用フィールドを調べる必要はありません。</p></ul><p>XDM スキーマを更新するデメリットには、次のものがあります。</p><ul><li>スキーマの更新は時間がかかるプロセスであり、Customer Journey Analyticsへのデータの送信を開始する前に行う必要があります。</li></ul> | なし |

{style="table-layout:auto"}

+++

## 次に、Adobe Experience Platformにデータを送信します

上記の情報を使用して移行パスを選択したら、次の方法を学習します [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 選択した移行パスによって異なります。
