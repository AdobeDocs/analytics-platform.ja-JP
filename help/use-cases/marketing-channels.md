---
title: Adobe Experience Platformでのマーケティングチャネルディメンションの使用
description: Analytics Data Connectorを使用して、マーケティングチャネルの処理ルールをAdobe Experience Platformに取り込みます。
translation-type: tm+mt
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 3%

---


# Adobe Experience Platformでのマーケティングチャネルディメンションの使用

組織で[Analytics Data Connector](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/analytics.html)を使用してレポートスイートデータをCJAに送信する場合、CJAでチャネルを設定して、マーケティング接続のディメンションに関するレポートを作成できます。

## 前提条件

* [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html)を使用して、レポートスイートのデータを既にAdobe Experience Platformにインポートしておく必要があります。 他のデータソースはサポートされません。マーケティングチャネルは、Analyticsレポートスイートの処理ルールに依存しています。
* マーケティングチャネルの処理ルールは、既に設定されている必要があります。 従来のAnalyticsコンポーネントガイドの[マーケティングチャネルの処理ルール](https://docs.adobe.com/content/help/ja-JP/analytics/components/marketing-channels/c-rules.html)を参照してください。

## マーケティングチャネルスキーマ要素

目的のレポートスイートにAnalytics Data Connectorを確立すると、XDMスキーマが作成されます。 このスキーマには、すべてのAnalyticsディメンションおよび指標が生データとして含まれます。 この生データには、アトリビューションや永続性は含まれません。 代わりに、各イベントはマーケティングチャネルの処理ルールを使用して、最初に一致したルールを記録します。 アトリビューションと永続性は、CJAでデータ表示を作成する際に指定します。

1. [Analytics Data Connectorに基づくデータセットを含む](/help/connections/create-connection.md) 接続を作成します。
2. [次のディメンションを含むデータ](/help/data-views/create-dataview.md) ビューを作成します。
   * **`channel.typeAtSource`**: [Marketing ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) channeldimensionと同じです。
   * **`channel._id`**:マー [ケティングチャネルの詳細と同じ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. 各ディメンションに、目的のアトリビューションモデルと持続性を指定します。 ファーストタッチディメンションとラストタッチディメンションの両方が必要な場合は、各マーケティングチャネルディメンションをコンポーネント領域に複数回ドラッグします。 各ディメンションに、目的のアトリビューションモデルと持続性を指定します。 Adobeでは、Workspaceで使いやすくするために、各ディメンションに表示名を付けることもお勧めします。
4. データ表示を作成します。

マーケティングチャネルのディメンションがAnalysis Workspaceで使用できるようになりました。

## 処理とアーキテクチャの違い

>[!IMPORTANT]
>
>レポートスイートデータとプラットフォームデータには、いくつかの基本的なデータの違いがあります。 Adobeでは、Platformでの適切なデータ収集を容易にするために、レポートスイートのマーケティングチャネルの処理ルールを調整することを強くお勧めします。

マーケティングチャネルの設定の動作は、プラットフォームデータとレポートスイートデータで異なります。 CJA用のマーケティングチャネルを設定する際は、次の点を考慮してください。

* **は訪問の最初のページ**:このルール条件は、複数のデフォルトのマーケティングチャネル定義で共通です。この条件を含む処理ルールは、プラットフォームでは無視されます（同じルール内の他の条件も引き続き適用されます）。 セッションは、データ収集時ではなく、データクエリ時に決定されるので、プラットフォームはこの特定のルール条件を使用できません。 Adobeでは、各マーケティングチャネル処理ルールから「訪問の最初のページ」条件を削除することを推奨します。

   ![訪問の最初のページ](assets/first-page-of-visit.png)

* **ラストタッチチャネルを上書き**:マーケティングチャネルマネージャーのこの設定は、通常、特定のチャネルがラストタッチチャネルのクレジットを受け取るのを防ぎます。プラットフォームはこの設定を無視し、「直接」や「内部」などの幅広いチャネルを指標に対して好ましくない結果にすることができます。 Adobeでは、「ラストタッチチャネルを上書き」をオフにしているチャネルを削除することをお勧めします。
   * マーケティングチャネルマネージャーで「ダイレクト」マーケティングチャネルを削除して、そのチャネルにCJAの「値なし」ディメンション項目を使用できます。 また、データ表示を設定する際に、このディメンション項目の名前を「直接」に変更したり、ディメンション項目を完全に除外したりすることもできます。
   * また、マーケティングチャネルの分類を作成し、CJAから除外するチャネルを除き、各値をそれ自体に分類することもできます。 その後、データ表示を作成する際に、`channel.typeAtSource`の代わりにこの分類ディメンションを使用できます。

   ![ラストタッチチャネルの上書き](assets/override-last-touch-channel.png)

* **マーケティングチャネルの有効期限**:このエンゲージメント期間の設定により、訪問者がレポートスイートデータの新しいファーストタッチチャネルを取得するまでの無操作時間を決定します。プラットフォームは独自のアトリビューション設定を使用するので、この設定はCJAでは完全に無視されます。

   ![マーケティングチャネルの有効期限](assets/marketing-channel-expiration.png)

## CJAと従来のAnalyticsのデータの比較

Adobe Experience Platformのアーキテクチャは、従来のAnalyticsレポートスイートとは異なるので、結果が一致するとは保証されません。 ただし、次のヒントを参考にして比較を簡単にすることができます。

* 上記のアーキテクチャの違いが比較に影響しないことを確認します。 これには、ラストタッチチャネルを上書きしないチャネルの削除や、訪問（セッション）の最初のヒットであるルール条件の削除が含まれます。
* 重複が、従来のAnalyticsと同じレポートスイートを使用していることを確認します。 CJA接続に、独自のマーケティングチャネル処理ルールを持つ複数のレポートスイートが含まれる場合、従来のAnalyticsと比較するのは簡単ではありません。 データを比較するために、各レポートスイートに対して個別の接続を作成する必要があります。
* 同じ日付範囲を比較し、データ表示のタイムゾーン設定がレポートスイートのタイムゾーンと同じであることを確認してください。
* レポートスイートデータを表示する場合は、カスタムアトリビューションモデルを使用します。 例えば、[マーケティングチャネル](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html)ディメンションは、デフォルト以外のアトリビューションモデルを使用する指標で使用します。 デフォルトのディメンション[ファーストタッチチャネル](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html)または[ラストタッチチャネル](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html)を比較する場合、Adobeは、レポートスイートで収集されるアトリビューションに依存するので、これらのディメンションを比較することをお勧めします。 CJAは、レポートスイートのアトリビューションデータに依存しません。代わりに、CJAレポートを実行したときに計算されます。
* レポートスイートデータとプラットフォームデータの間でアーキテクチャの違いがあるので、一部の指標は妥当な比較を行いません。 訪問回数/セッション、訪問者数/人、回数/イベントなどが例です。
