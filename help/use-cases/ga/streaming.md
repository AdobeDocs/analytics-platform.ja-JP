---
title: Adobe Experience Platform への Google Analytics データのストリーミング設定
description: Google データレイヤーを Adobe Experience Platform に送信するための実装の設定方法について説明します
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

---

# Adobe Experience Platform への Google Analytics データのストリーミング設定

このページでは、ライブ Google Analytics のデータを Adobe Experience Platform に取り込み、Customer Journey Analytics 内のデータビューでそのデータセットを参照する方法について重点的に説明します。このページの手順を、履歴データを含むデータセットの生成方法を説明した [Google Analytics 履歴データの Adobe Experience Platform への取り込み](backfill.md)ページと組み合わせることができます。ストリーミングデータセットとバックフィルデータセットを組み合わせて、過去のデータと現在のデータをシームレスにCustomer Journey Analytics に表示して確認できます。

データ収集を設定するには、次の手順を実行します。

1. [Adobe Experience Platform のタグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)を実装する。基本的な実装環境のインストールおよび導入について詳しくは、[クイックスタートガイド](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=ja)を参照してください。
1. [Google データレイヤー拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=ja)をインストールする。この拡張機能は、Web SDK 拡張機能をインストールした環境の代替となるもので、Google データレイヤーに特化しています。
1. Adobe Experience Platform データ収集に[データストリームを作成](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja)する。データを Adobe Experience Platform に送信するようデータストリームを設定します。現時点では、ここで各 Google データレイヤーオブジェクトを該当する XDM フィールドにマッピングする必要があります。アドビでは今後、このマッピングワークフローを簡略化する予定です。

サイトに目的のタグを実装して公開したら、[接続を作成](/help/connections/create-connection.md)手順、さらに[データビューを作成](/help/data-views/create-dataview.md)手順に進むことができます。
