---
title: Adobe Experience PlatformへのストリーミングGoogle Analyticsデータの設定
description: GoogleデータレイヤーをAdobe Experience Platformに送信するための実装の設定方法について説明します
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Adobe Experience PlatformへのストリーミングGoogle Analyticsデータの設定

このページでは、ライブGoogle AnalyticsのデータをAdobe Experience Platformに取り込み、Customer Journey Analytics内のデータビューでそのデータセットを参照する方法について説明します。 このページの手順を [Google Analyticsの履歴データをAdobe Experience Platformに取り込む](backfill.md)：履歴データを含むデータセットを生成します。 ストリーミングデータセットとバックフィルデータセットを組み合わせて、過去のデータと現在のデータをシームレスにCustomer Journey Analytics表示できます。

データ収集を設定するには、次の手順を実行します。

1. 実装方法 [Adobe Experience Platformのタグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja). 詳しくは、 [クイックスタートガイド](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) をクリックして、基本的な実装を実行します。
1. のインストール [Google Data Layer 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). この拡張機能は、Googleデータレイヤーに特に対応した Web SDK 拡張機能のインストールの代わりに使用されます。
1. [データストリームの作成](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) (Adobe Experience Platform Data Collection) を参照してください。 データをAdobe Experience Platformに送信するように Datastream を設定します。 現在、ここで各Googleデータレイヤーオブジェクトを適用可能な XDM フィールドにマッピングする必要があります。 Adobeは、今後、このマッピングワークフローを簡略化する予定です。

サイトに目的のタグを実装して公開したら、次に進みます。 [接続の作成](/help/connections/create-connection.md)を、 [データビューの作成](/help/data-views/create-dataview.md).
