---
title: マーケティングチャネルディメンションの使用
description: Analytics ソースコネクタを使用して、マーケティングチャネルの処理ルールをAdobe Experience Platformに取り込む方法を説明します。
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 49%

---

# マーケティングチャネルディメンションの使用

[Analytics ソースコネクタ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/analytics) を使用してレポートスイートデータをCustomer Journey Analyticsに送信する場合は、Customer Journey Analyticsの接続を設定して、マーケティングチャネルディメンションに関するレポートを作成できます。

>[!IMPORTANT]
>
>マーケティングチャネルディメンションに関するレポートのネイティブ製品機能については、[&#x200B; 派生フィールド – マーケティングチャネルのテンプレート &#x200B;](/help/data-views/derived-fields/derived-fields.md#marketing-channels) を参照してください。
>


## 前提条件

* [Analytics ソースコネクタ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/analytics) を使用して、事前にレポートスイートデータをAdobe Experience Platformに読み込んでおく必要があります。 他のデータソースはサポートされません。これは、マーケティングチャネルが Analytics レポートスイートの処理ルールに依存しているためです。
* マーケティングチャネルの処理ルールは、事前に設定しておく必要があります。Adobe Analytics コンポーネントガイドの [&#x200B; マーケティングチャネルの処理ルール &#x200B;](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules) を参照してください。

## マーケティングチャネルのスキーマ要素

目的のレポートスイートに Analytics ソースコネクタを確立すると、XDM スキーマが作成されます。 このスキーマには、すべての Analytics ディメンションと指標が生データとして含まれています。この生データには、アトリビューションや永続性は含まれていません。代わりに、各イベントはマーケティングチャネルの処理ルールを確認し、最初に一致したルールを記録します。Customer Journey Analyticsでデータビューを作成する際に、アトリビューションと永続性を指定します。

1. Analytics ソースコネクタに基づいたデータセットを含む [&#x200B; 接続を作成 &#x200B;](/help/connections/create-connection.md)。
2. 次のディメンションを含む[データビューを作成](/help/data-views/create-dataview.md)します。
   * **`channel.typeAtSource`**：[マーケティングチャネル](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/marketing-channel)に相当します。
   * **`channel._id`**：[マーケティングチャネルの詳細](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/marketing-detail)に相当します。
3. 各ディメンションに、目的のアトリビューションモデルと永続性を指定します。ファーストタッチディメンションとラストタッチディメンションの両方が必要な場合は、各マーケティングチャネルのディメンションをコンポーネント領域に複数回ドラッグします。各ディメンションに、目的のアトリビューションモデルと永続性を指定します。ワークスペースで使いやすくするために、各ディメンションに表示名を付けることもお勧めします。
4. データビューを作成します。

これで、マーケティングチャネルのディメンションを Analysis Workspace で使用できるようになります。

>[!NOTE]
>
> Analytics ソースコネクタでは、`channel.typeAtSource` （マーケティングチャネル）と `channel._id` （マーケティングチャネルの詳細）の両方が入力されている必要があります。 それ以外の場合は、どちらも XDM ExperienceEvent に引き継がれません。 ソースレポートスイートでマーケティングチャネルの空白の詳細が表示されると、`channel._id` が空白になり、Analytics ソースコネクタ `channel.typeAtSource` も空白になります。 これらの空白により、Adobe AnalyticsとCustomer Journey Analyticsの間でレポートの違いが生じる可能性があります。

## 処理とアーキテクチャの違い

>[!IMPORTANT]
>
>基本的に、レポートスイートデータと Platform データにはいくつかの違いがあります。Adobeでは、Experience Platformでの適切なデータ収集を容易にするために、レポートスイートのマーケティングチャネル処理ルールを調整することを強くお勧めします。

>[!NOTE]
>
>アトリビューションとCustomer Journey Analyticsに対するマーケティングチャネルの効果を最大限に高めるために、[&#x200B; 改訂されたベストプラクティス &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics/components/marketing-channels/mchannel-best-practices) を使用できます。

マーケティングチャネルの設定の動作は、Platform データとレポートスイートデータで異なります。Customer Journey Analytics用のマーケティングチャネルを設定する際は、次の違いを考慮してください。

* **訪問の最初のページです**：このルール条件は、複数のデフォルトのマーケティングチャネル定義で共通です。 この条件を含む処理ルールは、Platform では無視されます（同じルール内の他の条件は引き続き適用されます）。セッションは、データ収集時ではなくデータクエリ時に決定されます。このため、Platform でこの特定のルール条件の使用を回避できます。アドビでは、「訪問の最初のページ」条件を含むマーケティングチャネル処理ルールを再評価して、目標を達成する別のアプローチを選択することをお勧めします。

  ![訪問の最初のページ](../assets/first-page-of-visit.png)

* **ラストタッチチャネルの上書き**：マーケティングチャネルマネージャでこのオプションを設定すると、通常は、特定のチャネルがラストタッチチャネルのクレジットを受け取るのを回避できます。Platform ではこの設定が無視されるため、「ダイレクト」や「内部」などの幅広いチャネルが、潜在的に好ましくない方法で指標の影響を受けます。「ラストタッチチャネルの上書き」をオフにしているチャネルを削除することをお勧めします。
   * マーケティングチャネルマネージャーで「ダイレクト」マーケティングチャネルを削除し、そのチャネルのCustomer Journey Analyticsの「値なし」ディメンション項目を利用できます。 また、データビューを設定する際に、このディメンション項目の名前を「ダイレクト」に変更したり、ディメンション項目を完全に除外したりすることもできます。
   * または、Customer Journey Analyticsで除外するチャネルを除く各値をそれ自体に分類して、マーケティングチャネルの分類を作成できます。 その後、データビューを作成する際に、`channel.typeAtSource` の代わりに、この分類ディメンションを使用できます。

  ![ラストタッチチャネルの上書き](../assets/override-last-touch-channel.png)

* **マーケティングチャネルの有効期限**：このエンゲージメント期間設定では、レポートスイートデータでユーザーが新しいファーストタッチチャネルを取得するまでの非アクティブ期間を決定します。 Platform は独自のアトリビューション設定を使用するので、この設定はCustomer Journey Analyticsで完全に無視されます。

  ![マーケティングチャネルの有効期限](../assets/marketing-channel-expiration.png)

## Customer Journey AnalyticsとAdobe Analytics間のデータの比較

Adobe Experience PlatformのアーキテクチャはAdobe Analytics レポートスイートとは異なるので、結果の一致は保証されません。 ただし、次のヒントを参考にすると、データの比較が容易になります。

* 上記のアーキテクチャの違いが比較に影響しないことを確認します。これらの違いには、ラストタッチチャネルを上書きしないチャネルの削除や、訪問（セッション）の最初のヒットであるルール条件の削除などが含まれます。
* 接続でAdobe Analyticsと同じレポートスイートが使用されていることを再確認します。 Customer Journey Analytics接続に、独自のマーケティングチャネル処理ルールを持つ複数のレポートスイートが含まれている場合、Adobe Analyticsと比較する簡単な方法はありません。 データを比較するには、各レポートスイートに対して個別に接続を作成する必要があります。
* 同じ日付範囲を比較すること、およびデータビューのタイムゾーン設定がレポートスイートのタイムゾーンと同じであることを確認してください。
* レポートスイートデータを表示する際には、カスタムアトリビューションモデルを使用します。例えば、デフォルト以外のアトリビューションモデルを使用する指標を含む[マーケティングチャネル](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/marketing-channel)ディメンションを使用します。デフォルトのディメンションである[ファーストタッチチャネル](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/first-touch-channel)または[ラストタッチチャネル](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/last-touch-channel)に対する比較は行わないことをお勧めします。これは、これらがレポートスイートで収集されるアトリビューションに依存しているためです。Customer Journey Analyticsは、レポートスイートのアトリビューションデータに依存しません。代わりに、Customer Journey Analytics レポートの実行時に計算されます。
* レポートスイートデータと Platform データのアーキテクチャの違いにより、一部の指標は適切に比較されません。例としては、訪問/セッション、人物/人物、発生件数/イベントがあります。
