---
title: 顧客の遍歴分析 — はじめに
description: 顧客の遍歴分析の概要を参照してください。
translation-type: tm+mt
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# 顧客の遍歴分析 — はじめに

顧客の遍歴分析を導入するには、このワークフローに従う必要があります。 一部の初期タスクはAdobe Experience Platformで実行され、一部はCustomer Jeurney Analyticsで実行されます。

| タスク | 実行場所 | 詳細 |
|---|---|---|
| **手順1:データをAdobe Experience Platformに取り込む** | Adobe Experience Platform | APIやデータアップロード用のグラフィカルインターフェイスなど、ストリーミングとバッチの両方でデータを取り込む方法はいくつかあります。 エクスペリエンスプラットフォームは、次のようなデータを取り込むことができます。<ul><li>S3ストレージ</li><li>Azure Blob ストレージ</li><li>カフカ川</li><li>SFTP転送</li><li>CSVファイルのアップロード</li><li>JSONファイルのアップロード</li></ul> |
| **手順2:データの準備スキーマ** | Adobe Experience Platform | Adobe Experience Data Model( [XDM)を使用して](https://www.adobe.io/apis/experienceplatform/home/xdm.html) 、顧客エクスペリエンスデータを標準化し、顧客エクスペリエンス管理のスキーマを定義します。 |
| **手順3:データセットの作成スキーマ** | Adobe Experience Platform | プラットフォームのデータは、電子メールデータセット、CRMデータセット、POSデータセット、Adobe Analyticsデータセットなどのデータセットで構成されます。 各データセットは、1つのデータとスキーマのバッチで構成されます。 Experience Platformでデータセットを作 [成できます](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)。<br>Customer Jeurney Analyticsにインポートできるデータセットのスキーマは柔軟性が高いですが、いくつかの基本ルールに従う必要があります。 データをプラットフォームにアップロードする前に、データがこれらの要件を満たしていることを確認することをお勧めします。 (スキーマには指標とディメンションの両方が含まれます)。<br>Customer Jeurney Analyticsと互換性のあるデータには、次の3種類があります。<ul><li>**イベント**:イベントを時間で表すデータ(例：Web訪問、インタラクション、トランザクション、POSデータ、調査データ、広告インプレッションデータなど)。 これは、顧客IDまたはcookie IDとタイムスタンプを持つ一般的なクリックストリームデータです。 イベントデータを使用すると、任意のIDを使用できます。</li><li>**参照データ**:このデータは、イベントまたはデータ内の値やキーを参照するために使用されます。 例えば、製品データ内の数値IDを製品名にマップする参照イベントをアップロードできます。</li><li>**プロファイル**:ユーザーデータ内の訪問者、ユーザーまたは顧客に適用されるイベント。 例えば、顧客に関するCRMデータをアップロードできます。</li></ul> |
| **手順4：プラットフォームデータセットとCustomer Jeurney Analytics間の接続を作成する** | カスタマージャーニー分析 | See [Create a connection](/help/connections/create-connection.md). |
| **手順5:データの作成表示** | カスタマージャーニー分析 | See [Create a data view](/help/data-views/create-dataview.md). |
| **手順6:Workspaceでのクロスチャネルデータのレポート** | カスタマージャーニー分析 | 基本分析 [の実行および詳細](/help/projects/perform-basic-analysis.md) 分析 [の実行を参照してくださ](/help/projects/perform-adv-analysis.md)い。 |

## 前提条件

顧客の遍歴分析は、

* Adobe Analyticsのお客様は [Select、Prime](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) 、Ultimateのいずれですか。
* Adobe Experience Platform用にプロビジョニ [ングされ](https://www.adobe.com/experience-platform.html)、
* 顧客の遍歴分析SKUを購入済み

## データの準備スキーマ

[スキーマエディターを使用したスキーマの作成](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 手順1:データをAdobe Experience Platformに取り込む

CJAでエクスペリエンスプラットフォームのデータを活用する前に、そのデータをプラットフォームに取り込む必要があります。 これを行う方法はいくつかあります。

* 既存のAdobe Analyticsデータを取り込む場合は、Adobe Analytics Platform Connectorを使用します。
* 他のデータを取り込むには、次のような形式を使用します。S3ストレージ、Azure Blobストレージ、Kafka Streams、SFTP転送、CSVファイルのアップロード、JSONファイルのアップロード

### 手順1a:既存のAnalyticsデータをAdobe Experience Platformに取り込む

標準搭載のAdobe Analytics Platform Connectorを使用して、従来のAdobe Analyticsデータをプラットフォームに取り込みます。 レポートスイートごとに1つのソース接続を作成できます。 Adobe Experience Platform [ドキュメントの「Adobe Analyticsを使用したソース接続の作成](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) 」を参照してください。

接続が作成されると、ターゲットスキーマとデータセットが自動的に作成され、受信データが格納されます。 さらに、データのバックフィルが行われ、最大13か月の履歴データが取り込まれます。 最初のインジェストが完了したら、次に、このAnalyticsデ `Step 4` ータセットとCustomer Jareny Analyticsとの接続を作成します。

### 手順1b:他のデータ型の取り込み

[バッチ取り込みを使用すると](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) 、データをバッチファイルとしてエクスペリエンスプラットフォームに取り込むことができます。 バッチとは、単一の単位として取り込まれる1つ以上のファイルで構成されるデータの単位です。 取り込まれたバッチは、正常に取り込まれたレコードの数、失敗したレコードおよび関連するエラーメッセージを示すメタデータを提供します。 フラットな.CSVファイル(XDMスキーマにマッピング)やParqetaframesなど、手動でアップロードしたデータファイルは、この方法を使用して取り込む必要があります。

[ストリーミング取り込み](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) ：クライアントおよびサーバー側のデバイスからExperience Platformにデータをリアルタイムで送信できます。

[その他のソースコネクタを使用すると](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) 、外部ソースからデータを取り込みながら、プラットフォームサービスを使用して、受信データの構造化、ラベル付け、拡張を行うことができます。 アドビアプリケーション(Adobe Analytics、オーディエンスマネージャー、Experience Platform Launch、ターゲット)、クラウドベースのストレージ(Azure Blob、Amazon S3、FTP/SFTP、Google Cloudストレージ)、サードパーティソフトウェア、CRM(Microsoft Dynamics 365、Force)など、様々なソースからデータを取り込むことができます。

## 手順2:データの準備スキーマ

bnbnbnbn
