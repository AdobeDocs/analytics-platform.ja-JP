---
title: Customer Journey Analyticsアップグレードパスを選択
description: Customer Journey Analyticsへのアップグレード時に考えられるアップグレードパスの長所と短所を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: f1e1fdd5ca8aa51a28de13cdb028bf585a0324e7
workflow-type: tm+mt
source-wordcount: '2475'
ht-degree: 61%

---

# 手順 2：アップグレードパスの選択

+++このセクションを展開すると、このページの情報が大きなアップグレードプロセスのどこに適合するかを確認できます。 以前のアップグレード手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のアップグレードタスクがすべて完了していることを確認してください。

このページの情報では、次の表で強調表示されている、アップグレードプロセスの手順 2 について説明します。

| アップグレードタスク | 詳細 |
|---------|----------|
| **手順 1: [アップグレードの概要](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analyticsへのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。 |
| <span class="preview">**手順 2：アップグレードパスの選択**</span> | <span class="preview">Customer Journey Analyticsへのアップグレードには様々な方法があります。 組織の現在の Adobe Analytics 環境と長期的な目標に応じて、組織に最適な方法を選択します。</span> |
| **手順 3：[データを Adobe Experience Platform に送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| **手順 4：[履歴データの保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | ほとんどの組織では、Adobe Analytics の履歴データを一定期間保持する必要があります。これを実現するために様々なオプションが利用できます。 |
| **手順 5：[追加の実装タスクを実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからのアップグレードや、新しいCustomer Journey Analyticsの実装にも当てはまります。</p><p>これらのタスクには次のものが含まれます。</p><ul><li>他のデータを Experience Platform に取り込む</li><li>手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとデータウェアハウスの考慮</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーオンボーディングの計画</li></ul> <p>詳しくは、[Customer Journey Analytics の概要](/help/getting-started/cja-getting-started.md)を参照してください。 |

{style="table-layout:auto"}

+++

Customer Journey Analyticsへのアップグレードを決定した後、組織に最適なアップグレードパスを決定する必要があります。

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに使用するパスは、次の要因によって変わります。

* 既存の Adobe Analytics の実装

* 将来の目標

このページの情報を使用して、組織の現在の実装と将来の目標に最適なCustomer Journey Analyticsアップグレードパスを判断します。

組織に最適なアップグレードパスを決定するには、次の節を順番に参照する必要があります。

1. まず、 [使用可能なアップグレードパスについて](#understand-upgrade-paths).

1. その後、 [使用可能なアップグレードパスの評価](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. 最後に、 [各アップグレードパスのメリットとデメリットを比較検討する](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you).

## アップグレードパスについて

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードには、様々なアップグレードパスがあります。

一般に、各アップグレードパスは、アップグレードの実行に必要な労力のレベルや、アップグレード完了後に達成される長期的な生存率が異なります。

次の表に、各アップグレードパス、その作業レベル、長期的な実行可能性を示します。

| アップグレードパス | 労力のレベル | 長期的な実行可能性 |
|---------|----------|---------|
| **Experience PlatformWeb SDK の新しい実装**</br> Experience Platform Web SDK の新しい実装を行うことで、Customer Journey Analyticsの使用を開始できます。 これにより、Adobe Experience Platform Edge Network および Customer Journey Analytics へのデータの送信を開始できます。 <p>Web SDK をまだ使用していない組織の場合、このアップグレードパスは必要な手順が最も少ないため、データをEdge Networkに送信する際に最も簡単です。ただし、すべての作業が事前に行われる（XDM スキーマの作成など）ので、より大きな初期作業が必要です。</p><p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマを作成します。</li><li>Web SDKを実装します。</li><li>Platform にデータを送信します。</li></ol> | 高 | 高 |
| **Web SDK を使用するための Adobe Analytics の実装の移行**</br> Adobe Analytics の実装が AppMeasurement または Analytics 拡張機能である場合は、Customer Journey Analytics にデータを送信する前に、Adobe Experience Platform Web SDK を使用するように実装を移行すると、Edge Network と Adobe Analytics へのデータの送信を開始できます。<p>まだ Web SDK を使用していない組織の場合、これは Edge Network にデータを取得する最も簡単かつスムーズな方法です。多くの手順が必要になりますが、Adobe Analytics から Customer Journey Analytics へのより体系的な移行が可能になり、具体的なマイルストーンが得られます。</p><p>基本的な手順は次のとおりです。</p><ol><li>既存の Adobe Analytics の実装を Web SDK に移行し、Adobe Analytics ですべてが機能していることを検証します。</li><li>時間があれば、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li><li>Platform にデータを送信します。</li></ol> | 中 | 高 |
| **既存のAdobe Analytics Web SDK 実装の設定**</br> Adobe Analytics実装で既にAdobe Experience Platform Web SDK を使用している場合は、データストリームを設定することで Platform へのデータ送信を開始できます。 または、既に Platform にデータを送信している場合は、Platform データセットとCustomer Journey Analyticsの間に接続を作成するだけで済みます。<p>Customer Journey Analyticsで使用するデータを Platform に送信する前に、組織や使用するその他の Platform アプリケーションの特定のニーズに合わせてAdobe Analytics スキーマを更新することを検討してください。</p><p>基本的な手順は次のとおりです。</p><ol><li>Platform へのデータ送信を開始します。<p>Adobe Analyticsの実装で既に Platform にデータを送信している場合、この手順は必要ありません。 このプロセスで後ほど説明するように、Platform データセットとCustomer Journey Analyticsの間で接続を作成するだけで済みます。</p></li><li>（オプション）時間があれば、組織の XDM スキーマを作成します。</li><li>（条件付き）XDM スキーマを作成した場合は、データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li></ol> | 低 | 高 |
| **Analytics ソースコネクタの使用**</br> Adobe Analytics の実装が AppMeasurement または Analytics 拡張機能である場合は、Customer Journey Analytics のデータビューへのデータの送信を開始できます。<p>これは、Customer Journey Analytics にデータを取得する最も簡単な方法ですが、長期的には最も実行可能性が低い方法です。</p> | 低 | 低 |

{style="table-layout:auto"}

次の図は、各アップグレードパスが労力レベルと長期実行可能性の観点でどの程度の割合になるかを視覚化するのに役立ちます。

![cja アップグレードパス](assets/cja-upgrade-path-chart.png)

## 現在のAdobe Analyticsの実装に基づいて、使用可能なアップグレードパスを評価する

Adobe Analyticsの実装の種類ごとに、すべてのアップグレードパスを使用できるわけではありません。

以下の情報を使用すると、組織に最も適したアップグレードパスを理解できます。

具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

| 既存の Adobe Analytics の実装 | 使用可能なアップグレードパス |
|---------|----------|
| AppMeasurement | <ul><li>Experience Platform Web SDK の新しい実装</li><li>Web SDK への Adobe Analytics の移行</li><li>Analytics ソースコネクタ</li></ul> |
| Adobe Analytics 拡張機能 | <ul><li>Experience Platform Web SDK の新しい実装</li><li>Web SDK への Adobe Analytics の移行</li><li>Analytics ソースコネクタ</li></ul> |
| Web SDK | <ul><li>Platform にデータを送信するようにAdobe Analytics Web SDK を実装します。</li></ul> |

{style="table-layout:auto"}

## 使用可能なアップグレードパスのメリットとデメリットを比較検討する

特定のアップグレードパスのメリットとデメリットは、既存のAdobe Analytics実装によって異なります。

以下の情報を使用してどのアップグレードパスが適切かを判断する前に、の情報を確認してください [アップグレードパスについて](#understand-migration-methods) まだの場合は、

### AppMeasurement と Adobe Analytics 拡張機能を使用した Adobe Analytics 実装の場合

以下は、AppMeasurementまたはAdobe Analytics拡張機能を使用してAdobe Analyticsを実装している組織で使用できるアップグレードパスです。 各セクションを展開して、各アップグレードパスのメリットとデメリットを確認します。

#### アップグレードパス

+++Experience Platform Web SDK の新しい実装

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul></li><li>**将来性を確保**：将来の実装の更新が簡単になります。</li></ul> | <ul><li>**ゼロから新しい実装が必要**：ゼロから新しい実装を行う必要があるということは、つまり、次のようなデメリットがあります。 </li><ul><li>**時間がかかる**：これは、新しい実装からやり直す必要があるため、最も時間がかかり、要求の厳しいアップグレードパスです。</li><li>**XDM での完全なスキーマの再作成が必要**：Web SDK の実装を開始する前に、XDM で完全なスキーマを再作成する必要があります。</li><li>**ルールとデータ要素の再作成が必要**：Web SDK の実装を開始する前に、Adobe Analytics 実装からルール条件とデータ要素を再作成する必要があります。</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Adobe Analytics を Experience Platform Web SDK に移行

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**後で組織の XDM スキーマを作成できる柔軟性を提供**：既存の Adobe Analytics 実装を Web SDK を使用するように移行し、Adobe Analytics ですべてが機能していることを検証してから、XDM スキーマを作成できます。この柔軟性により、Customer Journey Analyticsに対するより体系的で思慮深いアップグレードが可能になります。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。このアクションでは、データオブジェクトのすべてのフィールドを、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリにする必要があります。このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li><li>**技術的負債**：このアプローチでは、既存の実装の修正された形式が使用されるので、実装ロジックを追跡し、今後必要に応じて変更を実行することが難しくなる可能性があります。 </li></ul> |

{style="table-layout:auto"}

+++

+++Analytics ソースコネクタを使用

| メリット | デメリット |
|----------|---------|
| <ul><li>アップグレード・パスの所要時間と要件が最も短い。 <p>最小限の投資で迅速に Customer Journey Analytics へとデータを移行する</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>最高レベルの [待ち時間](/help/technotes/guardrails.md#latencies) （すべてのアップグレードパスにわたるレポートで、リアルタイムパーソナライゼーションのユースケース向けに最適化されていない）。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**将来的に Web SDK への移行は困難**： </li><li>**スキーマで Analytics Experience Event フィールド グループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li></ul> |

{style="table-layout:auto"}

+++

### Web SDK を使用した Adobe Analytics 実装の場合

Experience Platform Web SDK を使用してAdobe Analyticsを実装している組織は、次のアップグレードパスを利用できます。

このアップグレードパスを選択する場合は、スキーマも選択する必要があります。

#### アップグレードパス

+++Platform にデータを送信するようにAdobe Analytics Web SDK を実装します

| メリット | デメリット |
|----------|---------|
| Adobe Analytics実装で既に Web SDK を使用している場合は、このアップグレードパスをお勧めします。<ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**XDM スキーマを使用するオプションを提供**：既存の Adobe Analytics スキーマを使用するか、XDM スキーマを作成してデータオブジェクトのフィールドを XDM スキーマにマッピングするかを選択できます。[XDM スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home#xdm-schemas)は、必要なフィールドを定義し、関連するフィールドのみを定義できる柔軟なスキーマです。 <p>独自の XDM スキーマを使用するメリットについて詳しくは、以下の「独自の XDM スキーマを使用」を参照してください。</p></li><li>**ルールとデータ要素を保持**：新しいルールアクションが必要ですが、最小限の変更で既存のデータ要素とルール条件を再利用できます。</li><li>**将来性を確保**：独自の XDM スキーマを使用することを選択した場合、将来の実装の更新が簡単になります。</li></ul> | なし |

{style="table-layout:auto"}

+++

#### スキーマの選択

Platform にデータを送信するようにAdobe Analytics Web SDK 実装を設定できるアップグレードパスを選択した場合は、使用するスキーマを選択できます。

既存の Adobe Analytics スキーマを使用するか、他の Platform サービスの使用を開始する際に組織のニーズに合わせて独自の XDM スキーマに更新するかを選択できます。

+++Adobe Analytics Web SDK 実装で Adobe Analytics スキーマを使用

| メリット | デメリット |
|----------|---------|
| <p>Adobe Analytics スキーマを使用すると、次のようなメリットがあります。</p><ul><li>アップグレードが容易<p>既にAdobe Experience Platform Web SDK を使用して Adobe Analytics にデータを送信している場合は、データストリームに追加サービスを追加して、Adobe Experience Platform にデータを送信できます（これは Customer Journey Analytics 設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用すると、次のようなデメリットがあります。</p><ul><li>Adobe Analytics スキーマを使用しても、他の Platform アプリケーションでの使用方法が制限されることはありませんが、スキーマは他の方法よりも複雑になります。これは、Adobe Analytics スキーマには、組織で使用される可能性が低い Adobe Analytics に固有のオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要があります。</p></li></ul> |

+++

+++Adobe Analytics Web SDK 実装で独自の XDM スキーマを使用

| メリット | デメリット |
|----------|---------|
| <ul><p>独自の XDM スキーマに更新すると、次のようなメリットがあります。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマ。</li><p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。</p></ul> | <p>独自の XDM スキーマに更新すると、次のようなデメリットがあります。</p><ul><li>スキーマの更新は、Platform へのデータ送信を開始する前に必要な、時間がかかるプロセスです。</li></ul> |

+++

## 次に、Adobe Experience Platform にデータを送信します

上記の情報を使用してアップグレードパスを選択した後、次の方法を学習します [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md) 選択したアップグレードパスによって異なります。
