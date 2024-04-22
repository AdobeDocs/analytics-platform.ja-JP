---
title: Customer Journey Analyticsの移行方法を選択
description: Customer Journey Analyticsへの移行時に考えられる移行方法のメリットとデメリットを説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 5%

---

# 手順 2:Customer Journey Analytics移行方法の選択

+++このページの情報は、大規模な移行プロセスの一部です。 このセクションを展開すると、移行プロセス内でこの情報が収まる場所を確認できます。 </br></br>このページの情報を続行する前に、以前の移行手順をすべて完了する必要があります。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている手順 2 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| <span class="preview">**手順 2: [移行方法の選択](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。</span> |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 1 で選択した移行方法によって異なります。 |
| **手順 4: [XDM スキーマへのデータマッピングを計画します](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、Adobe Experience Platformで使用され、一貫した再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。<p>ほとんどの移行方法では、新しい XDM スキーマを作成するか、データストリームマッピングを使用して既存のAdobe Analytics スキーマを XDM にマッピングする必要があります。</p> |
| **手順 5: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 6: [ユーザーのオンボーディングの計画](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。 |
| **手順 7: [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| **手順 8: [データフィードとData Warehouseの置き換え](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analyticsで使用していたデータフィードとData Warehouse機能を置き換えるために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。 |
| **手順 9: [プロジェクトとコンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。 |

{style="table-layout:auto"}

+++

Customer Journey Analyticsへの移行を決定した後、組織に最適な移行方法を決定する必要があります。

Adobe AnalyticsからCustomer Journey Analyticsへの移行方法は、次の要因によって決まります。

* 既存のAdobe Analyticsの実装

* 将来の目標

次の節では、組織の現在の実装と将来の目標に最適なCustomer Journey Analyticsの移行方法を判断します。

## 移行方法について

Adobe AnalyticsからCustomer Journey Analyticsへの移行には、様々な移行方法があります。

一般に、各移行方法は、移行の実行に必要な労力のレベルや、移行完了後に達成される長期的な実行可能性が異なります。

次の表に、各移行方法、作業レベルおよび長期的な実行可能性を示します。

| 移行方法 | 作業レベル | 長期的な生存率 |
|---------|----------|---------|
| **Web SDK の新しい実装**</br>&#x200B;新しいAdobe Experience Platform Web SDK 実装を実行して、Adobe Experience Platform Edge Networkへのデータ送信を開始できます <!-- what is the correct branding -->. <p>Web SDK をまだ使用していない組織の場合、この移行方法は、おそらくデータをEdge Networkに取り込む際に最も簡単です（必要な手順の数が最も少ない）。ただし、XDM スキーマの作成など、すべての作業は事前に行われます。</p><p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマの作成</li><li>Web SDK の実装</li><li>Platform にデータを送信</li></ol> | 高 | 高 |
| **Web SDK を使用するようにAdobe Analytics実装を移行する**</br> Adobe Analytics実装がAppMeasurementまたは Analytics 拡張機能の場合は、Adobe Experience Platform Web SDK を使用してCustomer Journey Analyticsに送信する前にEdge Networkへの送信を開始するように移行できます。 <!-- what else? --><p>これは、データをEdge Networkに取り込むための最も簡単でスムーズな方法です。より多くの手順が必要になりますが、より具体的なマイルストーンを持つより体系的なトランジションを提供します。</p><p>基本的な手順は次のとおりです。</p><ol><li>既存のAdobe Analytics実装を Web SDK に移行し、すべてがそこで機能していることを検証します。</li><li>時間の経過に応じて、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li><li>Platform にデータを送信</li></ol> | 中等 | 高 |
| **既存のAdobe Analytics Web SDK 実装を設定し、データをCustomer Journey Analyticsに送信します**</br> Adobe Analyticsの実装で既に Web SDK を使用している場合は、Customer Journey Analyticsへのデータ送信を開始できます。<p>データを Platform に送信する前に、Customer Journey Analyticsおよび使用するその他のAdobe Analytics アプリケーションの具体的なニーズに合わせて Platform スキーマを更新することを検討してください。</p><p>基本的な手順は次のとおりです。</p><ol><li>Customer Journey Analyticsへのデータ送信を開始します。<!-- What's involved here? Just point it at CJA? --></li><li>（オプション）時間に応じて、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li></ol> | 低 | 高 |
| **Analytics ソースコネクタ**</br> Adobe Analyticsの実装がAppMeasurementまたは Analytics 拡張機能の場合、Customer Journey Analyticsでデータビューへのデータ送信を開始できます。<p>これは、データをCustomer Journey Analyticsに取得する最も簡単な方法ですが、長期的には最も実行可能でない方法です。</p> | 低 | 低 |

{style="table-layout:auto"}

次の図を使用して、各移行方法が作業レベルの観点からどの程度の範囲に該当するか、およびそれぞれが達成する長期的な実行可能性を視覚化します。

![cja 移行方法](assets/cja-migration-methods.png)

## 現在のAdobe Analyticsの実装に基づいて、使用可能な移行方法を評価する

Adobe Analyticsの実装の種類ごとに、すべての移行方法を利用できるわけではありません。

以下の情報を一般的なガイドラインとして使用すると、組織に最も適した移行方法を理解するのに役立ちます。

より具体的なアドバイス、ガイダンス、サポートが必要な場合は、Adobe担当者にお問い合わせください。

| Adobe Analytics実装 | 使用可能な移行方法 |
|---------|----------|
| AppMeasurement | <ul><li>Web SDK の新しい実装</li><li>Adobe Analyticsの Web SDK への移行</li><li>Analytics ソースコネクタ</li></ul> |
| Adobe Analytics 拡張機能 | <ul><li>Web SDK の新しい実装</li><li>Adobe Analyticsの Web SDK への移行</li><li>Analytics ソースコネクタ</li></ul> |
| Web SDK | <ul><li>データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を実装を設定します。</li></ul> |

{style="table-layout:auto"}

## 使用可能な移行方法のメリットとデメリットを比較検討する

どの移行方法の長所と短所かは、既存のAdobe Analytics実装によって異なります。

以下の情報を使用してどの移行方法が適切かを判断する前に、の情報を確認してください [移行方法について](#understand-migration-methods) まだの場合は、

### AppMeasurementとAdobe Analytics拡張機能

次の表に、AppMeasurementまたはAdobe Analytics拡張機能を使用してAdobe Analyticsを実装している組織で使用できる移行方法を示します。

| 移行方法 | メリット | デメリット |
|---------|----------|---------|
| **Web SDK の新しい実装** | <ul><li>XDM スキーマ（柔軟なスキーマ）を使用して必要なフィールドを定義する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しません</li><li>文字制限に関する問題がありません（prop の場合は 100 文字）</li><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>将来の拡張にも対応（最新の機能をすべて搭載）</li><li>Adobe Experience Cloud データ収集のタグを他のExperience Cloud製品（AJO、RTCDP など）間で統合します。</li><li>[ファーストパーティのデバイス ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=ja) で訪問者識別の精度を高めます</li></ul> | <ul><li>最も時間がかかり要求の厳しい移行方法<p>Web SDK の実装を開始するには、XDM で完全なスキーマを再作成する必要があります</p></li></ul> |
| **Adobe Analyticsの Web SDK への移行** | <ul><li>Adobe Analyticsの実装で既に設定されているルールとデータ要素を保持します。</li><li>既存のAdobe Analyticsのレポートに影響を与えることなく、Web SDK に移行できます。</li><li>組織の XDM スキーマを後で作成する柔軟性を提供します。</br>Customer Journey AnalyticsにAdobe Analytics エクスペリエンスイベントフィールドグループは必要ありません。 <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しません</li><li>文字制限に関する問題がありません（prop の場合は 100 文字）</li><li>Adobe Experience Platformは強力に設計されているので、レポートとデータの可用性が高いパフォーマンスを発揮します。 [リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)</li><li>将来の拡張にも対応（最新の機能をすべて搭載）</li><li>Adobe Experience Cloud データ収集のタグを他のExperience Cloud製品（AJO、RTCDP など）間で統合します。</li><li>[ファーストパーティのデバイス ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=ja) で訪問者識別の精度を高めます</li></ul> | <ul><li>は、データストリームマッピングを使用して、将来のある時点で XDM スキーマに準拠する必要があります。</li><li>多少の技術的負債が生じる。 例えば、従来のAppMeasurementや Analytics 拡張機能コードは残すことができます。 </li></ul> |
| **Analytics ソースコネクタ** | <ul><li>最も時間がかかり、要求の厳しい移行方法。 <p>最小限の投資でデータを迅速にCustomer Journey Analyticsに移行</p></li></ul> | <ul><li>データは、Edge Networkに送信されず、他のAdobe Experience Platform アプリケーションと共有できません。Customer Journey Analyticsのみに制限されます<li>今後 Web SDK に移行するのは困難です</li><li>スキーマで Analytics エクスペリエンスイベントフィールドグループを使用します。</br>このフィールドグループは、Customer Journey Analyticsスキーマに不要な多くのAdobe Analytics イベントを追加します。  これにより、Customer Journey Analyticsに必要なスキーマよりも、より雑然とした複雑なスキーマが生じる可能性があります。</li><li>最高レベルの [待ち時間](/help/admin/guardrails.md#latencies) すべての実装方法で</li></ul> |

{style="table-layout:auto"}

### Web SDK

次の表に、Web SDK を使用してAdobe Analyticsを実装している組織で使用できる移行方法を示します。

| 移行方法 | メリット | デメリット |
|---------|----------|---------|
| **データをCustomer Journey Analyticsに送信するようにAdobe Analytics Web SDK を実装を設定します。** | Adobe Analytics実装で既に Web SDK を使用している場合は、この移行方法をお勧めします。 <p>この実装方法を使用する場合、既存のAdobe Analytics スキーマを使用するか、他の Platform アプリケーションを使用し始める際に組織のニーズに合わせて XDM スキーマを更新するかを選択できます。</p><p>**Adobe Analytics スキーマの使用**</p><p>Adobe Analytics スキーマを使用する場合の利点は次のとおりです。</p><ul><li>容易な移行<p>Adobe Experience Platform Web SDK を使用して既にAdobe Analyticsにデータを送信している場合は、データストリームにサービスを追加して、Adobe Experience Platformにデータを送信できます（Customer Journey Analytics設定で使用できます）。</p></li></ul><p>Adobe Analytics スキーマを使用するデメリットには、次のものがあります。</p><ul><li>Adobe Analytics スキーマの使用は、他の Platform アプリケーションとの使用方法に関して制限を受けませんが、結果的にスキーマは、そうでない場合よりも複雑になります。 これは、Adobe Analytics スキーマには、Adobe Analyticsに固有で、組織で使用されない可能性の高いオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるには、何千もの未使用のフィールドをふるいにかける必要があります。</p></li></ul><p>**XDM スキーマの使用**</p><p>XDM スキーマを更新する利点は次のとおりです。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマ。</li><p>スキーマの変更が必要な場合、更新が必要なフィールドを見つけるために、何千もの未使用フィールドを調べる必要はありません。</p></ul><p>XDM スキーマを更新するデメリットには、次のものがあります。</p><ul><li>スキーマの更新は時間がかかるプロセスであり、Customer Journey Analyticsへのデータの送信を開始する前に行う必要があります。</li></ul> | なし |

{style="table-layout:auto"}

## 次に、Adobe Experience Platformにデータを送信します

上記の情報を使用して移行方法を選択したら、次の方法を学習します [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 選択した移行方法によって異なります。