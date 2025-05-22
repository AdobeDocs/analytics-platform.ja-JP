---
title: Customer Journey Analytics アップグレードパスの選択
description: Customer Journey Analytics にアップグレードする際に考えられるアップグレードパスのメリットとデメリットを説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '2981'
ht-degree: 100%

---

# 手順 2：アップグレードパスの選択

+++このセクションを展開すると、このページの情報がアップグレードプロセス全体のどこに当てはまるかがわかります。これまでのアップグレード手順がすべて完了していることを確認してください。

この節に進む前に、以前のアップグレードタスクがすべて完了していることを確認してください。

このページの情報では、次の表でハイライト表示されているアップグレードプロセスの手順 2 について説明します。

| アップグレードタスク | 詳細 |
|---------|----------|
| **手順 1：[アップグレードの概要](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analytics へのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。 |
| <span class="preview">**手順 2：アップグレードパスの選択**</span> | <span class="preview">Customer Journey Analytics へのアップグレードには様々な方法があります。組織の現在の Adobe Analytics 環境と長期的な目標に応じて、組織に最適な方法を選択します。</span> |
| **手順 3：[データを Adobe Experience Platform に送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platform にデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| **手順 4：[履歴データの保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | ほとんどの組織では、Adobe Analytics の履歴データを一定期間保持する必要があります。これを実現するために様々なオプションが利用できます。 |
| **手順 5：[追加の実装タスクを実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics 環境が使用可能になる前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analytics からのアップグレードと新しい Customer Journey Analytics の実装に適用されます。</p><p>これらのタスクには次のものが含まれます。</p><ul><li>他のデータを Experience Platform に取り込む</li><li>手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとデータウェアハウスの考慮</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーオンボーディングの計画</li></ul> <p>詳しくは、[Customer Journey Analytics の概要](/help/getting-started/cja-getting-started.md)を参照してください。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>このページの情報は、次のより包括的なアップグレード情報に置き換えられます。 <ul><li>**推奨されるアップグレード手順**<p>詳しくは、[Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパス](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)を参照してください。</p></li><li>**Customer Journey Analytics アップグレードガイド**<p>組織と一意の状況に合わせて調整されたアップグレード手順を動的に生成する新しいアップグレードガイドが使用できます。</p><p>Customer Journey Analytics からガイドにアクセスするには、「**[!UICONTROL Workspace]**」タブを選択し、左側のパネルで「**[!UICONTROL Customer Journey Analytics にアップグレード]**」を選択します。画面の指示に従います。</p></li></ul>


Customer Journey Analytics へのアップグレードを決定したら、組織にとって最適なアップグレードパスを決定する必要があります。

Adobe Analytics から Customer Journey Analytics へのアップグレードに選択するパスは、次の要因によって異なります。

* 既存の Adobe Analytics の実装

* 将来の目標

このページの情報を使用して、組織の現在の実装と将来の目標に最も適した Customer Journey Analytics アップグレードパスを決定します。

組織に最適なアップグレードパスを決定するには、次の節を順番にお読みください。

1. まず、[利用可能なアップグレードパスを理解する](#understand-upgrade-paths)。

1. 次に、[利用可能なアップグレードパスを評価する](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation)。

1. 最後に、[各アップグレードパスのメリットとデメリットを比較検討する](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you)。

## アップグレードパスについて

Adobe Analytics から Customer Journey Analytics へのアップグレードには、様々なアップグレードパスが存在します。

一般に、アップグレードパスごとに、アップグレードの実行に必要な労力のレベルや、アップグレード完了後に実現される長期的な実行可能性が異なります。

次の表に、各アップグレードパス、その労力レベル、および長期的な実行可能性を示します。

| アップグレードパス | 労力のレベル | 長期的な実行可能性 |
|---------|----------|---------|
| **Analytics ソースコネクタを使用した Experience Platform Web SDK の新しい実装**</br> Experience Platform Web SDK を新たに実装すれば、Customer Journey Analytics の使用を開始できます。これにより、Adobe Experience Platform Edge Network および Customer Journey Analytics へのデータの送信を開始できます。さらに、Analytics ソースコネクタを使用すると、履歴データを Customer Journey Analytics に取り込むことができます。<p>まだ Web SDK を使用していない組織の場合、このアップグレードパスは、必要な手順数が最も少ないので、おそらく Edge Network にデータを取得する最も簡単な方法です。ただし、すべての作業（XDM スキーマの作成など）を最初に行うので、初期作業がより多く必要になります。</p><p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマを作成します。</li><li>Web SDKを実装します。</li><li>Platform にデータを送信します。</li><li>Analytics ソースコネクタを設定します。</br>Analytics ソースコネクタを使用すると、Adobe Analytics の履歴データを Customer Journey Analytics に取り込むことができます。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | 高 | 高 |
| **Experience Platform Web SDK の新しい実装**</br> Experience Platform Web SDK を新たに実装すれば、Customer Journey Analytics の使用を開始できます。これにより、Adobe Experience Platform Edge Network および Customer Journey Analytics へのデータの送信を開始できます。 <p>まだ Web SDK を使用していない組織の場合、このアップグレードパスは、必要な手順数が最も少ないので、おそらく Edge Network にデータを取得する最も簡単な方法です。ただし、すべての作業（XDM スキーマの作成など）を最初に行うので、初期作業がより多く必要になります。</p><p>基本的な手順は次のとおりです。</p><ol><li>組織の XDM スキーマを作成します。</li><li>Web SDKを実装します。</li><li>Platform にデータを送信します。</li></ol> | 高 | 高 |
| **Web SDK を使用するための Adobe Analytics の実装の移行**</br> Adobe Analytics の実装が AppMeasurement または Analytics 拡張機能である場合は、Customer Journey Analytics にデータを送信する前に、Adobe Experience Platform Web SDK を使用するように実装を移行すると、Edge Network と Adobe Analytics へのデータの送信を開始できます。<p>まだ Web SDK を使用していない組織の場合、これは Edge Network にデータを取得する最も簡単かつスムーズな方法です。多くの手順が必要になりますが、Adobe Analytics から Customer Journey Analytics へのより体系的な移行が可能になり、具体的なマイルストーンが得られます。</p><p>基本的な手順は次のとおりです。</p><ol><li>既存の Adobe Analytics の実装を Web SDK に移行し、Adobe Analytics ですべてが機能していることを検証します。</li><li>時間があれば、組織の XDM スキーマを作成します。</li><li>データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li><li>Platform にデータを送信します。</li></ol> | 中 | 高 |
| **既存の Adobe Analytics Web SDK 実装の設定**</br> Adobe Analytics の実装で既に Adobe Experience Platform Web SDK を使用している場合は、データストリームを設定することで Platform へのデータの送信を開始できます。または、既に Platform にデータを送信している場合は、Platform データセットと Customer Journey Analytics の間の接続を作成するだけで済みます。<p>Customer Journey Analytics で使用するデータを Platform に送信する前に、組織や使用するその他の Platform アプリケーションの特定のニーズに合わせて Adobe Analytics スキーマを更新することを検討します。</p><p>基本的な手順は次のとおりです。</p><ol><li>Platform へのデータ送信を開始します。<p>Adobe Analytics の実装で既にプラットフォームにデータを送信している場合、この手順は必要ありません。このプロセスで後ほど説明するように、プラットフォームデータセットと Customer Journey Analytics の間で接続を作成するだけで済みます。</p></li><li>（オプション）時間があれば、組織の XDM スキーマを作成します。</li><li>（条件付き）XDM スキーマを作成した場合は、データストリームマッピングを使用して、データオブジェクト内のすべてのフィールドを XDM スキーマにマッピングします。</li></ol> | 低 | 高 |
| **Analytics ソースコネクタの使用**</br> Adobe Analytics の実装が AppMeasurement または Analytics 拡張機能である場合は、Customer Journey Analytics のデータビューへのデータの送信を開始できます。<p>これは、Customer Journey Analytics にデータを取得する最も簡単な方法ですが、長期的には最も実行可能性が低い方法です。</p> <p>**メモ：**&#x200B;このアップグレードパスは独立して使用できます。ただし、より良い結果を得るには、このアップグレードパスを Experience Platform WebSDK の新しい実装と組み合わせて使用することをお勧めします。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | 低 | 低 |

{style="table-layout:auto"}

次の図を使用すると、労力のレベルと長期的な実行可能性の観点から、各アップグレードパスがスペクトルのどこに位置するかを視覚化するのに役立ちます。

![CJA アップグレードパス](assets/cja-upgrade-path-chart.png)

## 現在の Adobe Analytics の実装に基づいた利用可能なアップグレードパスの評価

Adobe Analytics 実装の各タイプで、すべてのアップグレードパスが利用できるわけではありません。

以下の情報を使用すると、組織に最適なアップグレードパスを理解するのに役立ちます。

具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

| 既存の Adobe Analytics の実装 | 利用可能なアップグレードパス |
|---------|----------|
| AppMeasurement | <ul><li>Experience Platform Web SDK の新しい実装</li><li>Web SDK への Adobe Analytics の移行</li><li>Analytics ソースコネクタ</li><li>（推奨）Analytics ソースコネクタを使用した Experience Platform Web SDK の新しい実装</li></ul> |
| Adobe Analytics 拡張機能 | <ul><li>Experience Platform Web SDK の新しい実装</li><li>Web SDK への Adobe Analytics の移行</li><li>Analytics ソースコネクタ</li><li>（推奨）Analytics ソースコネクタを使用した Experience Platform Web SDK の新しい実装</li></ul> |
| Web SDK | <ul><li>Platform にデータを送信する Adobe Analytics Web SDK 実装の設定</li><li>（推奨）Analytics ソースコネクタを使用した Experience Platform Web SDK の新しい実装</li></ul> |

{style="table-layout:auto"}

## 利用可能なアップグレードパスのメリットとデメリットの比較検討

特定のアップグレードパスのメリットとデメリットは、既存の Adobe Analytics の実装によって異なります。

以下の情報を使用して適切なアップグレードパスを判断する前に、[アップグレードパスについて](#understand-migration-methods)の情報をまだ確認していない場合は確認してください。

>[!NOTE]
>
>次の節で説明する各アップグレードパスは独立して使用できますが、アドビでは、Adobe Analytics から Customer Journey Analytics にアップグレードする際は、現在の Adobe Analytics 実装に関係なく、**Adobe Analytics ソースコネクタ**&#x200B;と **Experience Platform WebSDK の新しい実装**&#x200B;の 2 方向のアップグレードアプローチをお勧めします。
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### AppMeasurement と Adobe Analytics 拡張機能を使用した Adobe Analytics 実装の場合

AppMeasurement または Adobe Analytics 拡張機能を使用して Adobe Analytics を実装している組織が利用できるアップグレードパスは次のとおりです。各節を展開すると、各アップグレードパスのメリットとデメリットが表示されます。

#### アップグレードパス

+++Experience Platform Web SDK の新しい実装

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul></li><li>**将来性を確保**：将来の実装の更新が簡単になります。</li></ul> | <ul><li>**ゼロから新しい実装が必要**：ゼロから新しい実装を行う必要があるということは、つまり、次のようなデメリットがあります。 </li><ul><li>**時間がかかる**：これは、新しい実装をやり直す必要があるので、最も時間がかかり、要求が厳しいアップグレードパスです。</li><li>**XDM での完全なスキーマの再作成が必要**：Web SDK の実装を開始する前に、XDM で完全なスキーマを再作成する必要があります。</li><li>**ルールとデータ要素の再作成が必要**：Web SDK の実装を開始する前に、Adobe Analytics 実装からルール条件とデータ要素を再作成する必要があります。</li></ul><li>**履歴データの保持が考慮されない：**&#x200B;アドビでは、Customer Journey Analytics にアップグレードした後に履歴データを保持するために、Analytics ソースコネクタを Experience Platform Web SDK の新しい実装と組み合わせて使用することをお勧めします。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**元の実装のデータと新しい実装のデータの比較が考慮されない：**&#x200B;アドビでは、Customer Journey Analytics にアップグレードした後にデータを比較するには、Analytics ソースコネクタを Experience Platform Web SDK の新しい実装と組み合わせて使用することをお勧めします。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++Adobe Analytics を Experience Platform Web SDK に移行

| メリット | デメリット |
|----------|---------|
| <ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**後で組織の XDM スキーマを作成できる柔軟性を提供**：既存の Adobe Analytics 実装を Web SDK を使用するように移行し、Adobe Analytics ですべてが機能していることを検証してから、XDM スキーマを作成できます。この柔軟性により、Customer Journey Analytics に対する、より系統的かつ慎重なアップグレードが可能になります。</li></ul> | <ul><li>**Platform にデータを送信するにはマッピングが必要**：組織で Customer Journey Analytics を使用する準備が整ったら、Adobe Experience Platform のデータセットにデータを送信する必要があります。このアクションでは、データオブジェクトのすべてのフィールドを、XDM スキーマフィールドに割り当てるデータストリームマッピングツールのエントリにする必要があります。このワークフローではマッピングを 1 回行うだけで済み、実装を変更する必要ありません。ただし、これは、XDM オブジェクトでデータを送信する際には必要ない追加の手順です。</li><li>**技術的負債**：このアプローチでは、既存の実装の修正された形式が使用されるので、実装ロジックを追跡し、今後必要に応じて変更を実行することが難しくなる可能性があります。 </li></ul> |

{style="table-layout:auto"}

+++

+++Analytics ソースコネクタを使用

| メリット | デメリット |
|----------|---------|
| <ul><li>最も時間がかかり、要求が厳しいアップグレードパス。 <p>最小限の投資で迅速に Customer Journey Analytics へとデータを移行する</p></li></ul> | <ul><li>**データが Edge Network に送信されない**： <p>その結果、次のようなデメリットが生じます。</p><ul><li>すべてのアップグレードパスにわたるレポートの[待ち時間](/help/technotes/guardrails.md#latencies)が最高レベル。 リアルタイムパーソナライゼーションのユースケースには最適化されていません。</li><li>データを他の Adobe Experience Platform アプリケーションと共有することはできません。Customer Journey Analytics にのみ制限されます</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存します</li></ul><li>**今後 Web SDKに移行するのは難しい**：最終的には、Experience Platform Web SDK が提供するメリットを利用したいと考えるようになります。Experience Platform Web SDK の使用を開始するには、新しい実装を行う必要があります。</li><li>**スキーマで Analytics Experience Event フィールド グループを使用**：このフィールドグループは、Customer Journey Analytics スキーマでは必要のない多くの Adobe Analytics イベントを追加します。これにより、Customer Journey Analytics に必要なスキーマよりも雑然とした複雑なスキーマが作成される可能性があります。</li></ul><p>これらのデメリットにより、アドビでは、Analytics ソースコネクタを Experience Platform Web SDK の新しい実装と組み合わせて使用することをお勧めします。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### Web SDK を使用した Adobe Analytics 実装の場合

Experience Platform Web SDK を使用して Adobe Analytics を実装している組織では、次のアップグレードパスを利用できます。

このアップグレードパスを選択する際は、スキーマも選択する必要があります。

#### アップグレードパス

+++Platform にデータを送信する Adobe Analytics Web SDK 実装の設定

| メリット | デメリット |
|----------|---------|
| Adobe Analytics の実装で既に Web SDK を使用している場合、これが推奨されるアップグレードパスです。<ul><li>**Experience Edge Network でデータをホストするすべてのメリットを提供**： <p>次のようなメリットがあります。</p><ul><li>Adobe Experience Platform は、[リアルタイムパーソナライゼーションのユースケース](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ja)を強化するように作成されているので、高パフォーマンスのレポートとデータの可用性が実現する</li><li>他の Experience Cloud 製品（AJO、RTCDP など）の間で Adobe Experience Cloud データ収集の実装を統合する</li><li>Adobe Analytics の用語（prop、eVar、イベントなど）に依存しない</li></ul><li>**既存の実装を使用**：このアプローチには実装の変更が必要ですが、完全に新しい実装をゼロから行う必要はありません。実装ロジックに最小限の変更を行うだけで、既存の Adobe Analytics レポートに影響を与えることなく、既存のデータレイヤーとコードを使用できます。</li><li>**XDM スキーマを使用するオプションを提供**：既存の Adobe Analytics スキーマを使用するか、XDM スキーマを作成してデータオブジェクトのフィールドを XDM スキーマにマッピングするかを選択できます。[XDM スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home#xdm-schemas)は、必要なフィールドを定義し、関連するフィールドのみを定義できる柔軟なスキーマです。 <p>独自の XDM スキーマを使用するメリットについて詳しくは、以下の「独自の XDM スキーマを使用」を参照してください。</p></li><li>**ルールとデータ要素を保持**：新しいルールアクションが必要ですが、最小限の変更で既存のデータ要素とルール条件を再利用できます。</li><li>**将来性を確保**：独自の XDM スキーマを使用することを選択した場合、将来の実装の更新が簡単になります。</li></ul> | なし |

{style="table-layout:auto"}

+++

#### スキーマの選択

Platform にデータを送信するように Adobe Analytics Web SDK 実装を設定できるアップグレードパスを選択した場合は、使用するスキーマを選択できます。

既存の Adobe Analytics スキーマを使用するか、他の Platform サービスの使用を開始する際に組織のニーズに合わせて独自の XDM スキーマに更新するかを選択できます。

+++Adobe Analytics Web SDK 実装で Adobe Analytics スキーマを使用

| メリット | デメリット |
|----------|---------|
| <p>Adobe Analytics スキーマを使用すると、次のようなメリットがあります。</p><ul><li>アップグレードのしやすさ<p>既にAdobe Experience Platform Web SDK を使用して Adobe Analytics にデータを送信している場合は、データストリームに追加サービスを追加して、Adobe Experience Platform にデータを送信できます（これは Customer Journey Analytics 設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用すると、次のようなデメリットがあります。</p><ul><li>Adobe Analytics スキーマを使用しても、他の Platform アプリケーションでの使用方法が制限されることはありませんが、スキーマは他の方法よりも複雑になります。これは、Adobe Analytics スキーマには、組織で使用される可能性が低い Adobe Analytics に固有のオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要があります。</p></li></ul> |

+++

+++Adobe Analytics Web SDK 実装で独自の XDM スキーマを使用

| メリット | デメリット |
|----------|---------|
| <ul><p>独自の XDM スキーマに更新すると、次のようなメリットがあります。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマ。</li><p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。</p></ul> | <p>独自の XDM スキーマに更新すると、次のようなデメリットがあります。</p><ul><li>スキーマの更新は、Platform へのデータの送信を開始する前に必要な時間のかかるプロセスです。</li></ul> |

+++

## 次に、Adobe Experience Platform にデータを送信します

上記の情報を使用してアップグレードパスを選択したら、選択したアップグレードパスに応じて [Adobe Experience Platform にデータを送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)する方法を学んでください。
