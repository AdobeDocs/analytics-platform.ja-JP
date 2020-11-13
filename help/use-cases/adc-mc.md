---
title: Analytics Data Connectorを使用したCJAへのマーケティングチャネルのインポート
description: 正しいAnalytics Data Connector設定を使用して、マーケティングチャネルの処理ルールをAdobe Experience Platformに取り込みます。
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# Analytics Data Connectorを使用したCJAへのマーケティングチャネルのインポート

組織で[Analytics Data Connector](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/connectors/adobe-applications/analytics.html)を使用してレポートスイートデータをCJAに送信する場合、CJAでチャネルを設定して、マーケティング接続のディメンションに関するレポートを作成できます。

## 前提条件

* [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html)を使用して、レポートスイートのデータを既にAdobe Experience Platformにインポートしておく必要があります。
* マーケティングチャネルの処理ルールは、既に設定されている必要があります。 従来のAnalyticsコンポーネントガイドの[マーケティングチャネルの処理ルール](https://docs.adobe.com/content/help/ja-JP/analytics/components/marketing-channels/c-rules.html)を参照してください。

## マーケティングチャネルスキーマ要素

目的のレポートスイートでAnalytics Data Connectorを使用すると、XDMスキーマが作成されます。 このスキーマには、すべてのAnalyticsディメンションおよび指標が生のデータとして含まれます。 この生データには、アトリビューションや永続性は含まれません。 代わりに、各ヒットはマーケティングチャネルの処理ルールを使用して実行され、最初に一致したルールを記録します。 アトリビューションと永続性は、CJAでデータ表示を作成する際に指定します。

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


ファーストタッチディメンションとラストタッチチャネルディメンションは、基本的には同じディメンションで異なるアトリビューションモデルを持つので、[データ表示](/help/data-views/create-dataview.md)を作成する際に、同じディメンションを再作成できます。 同じスキーマエレメントに基づいて複数のディメンションを作成し、様々なアトリビューションモデルと持続性を提供できます。

## AとBの違い

