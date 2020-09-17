---
title: Customer Journey Analytics のデータ取り込みオプション
description: Customer Journey Analytics にデータを取り込む様々な方法について
translation-type: ht
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: ht
source-wordcount: '487'
ht-degree: 100%

---


# Customer Journey Analytics のデータ取り込みオプション

Customer Journey Analytics へのデータの取り込みには、様々なオプションがあります。従来の Adobe Analytics データを移動することを想定しているものもあれば、Adobe Experience Platform から直接データを取り込むことを想定しているものもあります。このリファレンスでは、従うべき手順の概要と、より詳細な情報へのリンクを示します。

## 従来の Adobe Analytics からのデータの取り込み

このワークフローでは、Adobe Analytics データコネクタを使用し、タグマネージャーとして DTM を使用するか、Launch を使用するかによって異なります。

### Dynamic Tag Management（DTM）

1. [データレイヤーの作成](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/prepare/data-layer.html)をまだおこなっていない場合は、おこないます。データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [DTM](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/other/dtm/dtm-implementation-overview.html) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。Dynamic Tag Management では、単一のデータ層で複数のソースのデータをプッシュできます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)を作成します。このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。

### Launch を使用

1. [データレイヤーの作成](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/prepare/data-layer.html)をまだおこなっていない場合は、おこないます。データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。
1. [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/launch/overview.html) を使用して、データ収集用のコードをサイトに導入します（まだ導入していない場合）。Launch は、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。Launch は他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。
1. Adobe Experience Platform で [Adobe Analytics ソースコネクタ](https://docs.adobe.com/content/help/ja-JP/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)を作成します。このソースコネクタは、[エクスペリエンスデータモデル（XDM）システム](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)と呼ばれる、標準化されたフレームワーク内で Experience Platform に Analytics データを取り込みます。
1. [Customer Journey Analytics](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-overview/cja-getting-started.html) を使用して、クロスチャネルレポートのための 1 つ以上の接続とデータ表示を作成します。
