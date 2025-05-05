---
title: データセットの書き出しCustomer Journey Analytics
description: データセットの書き出しを使用してデータをバックアップする方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 6%

---

# データセットの書き出し

この記事では、[!DNL Customer Journey Analytics Export datasets] を使用して次の [ データ書き出しのユースケース ](overview.md) を実装する方法について説明します。

- データバックアップ

## はじめに

[!DNL Experience Platform Export datasets] を使用したデータの書き出しを使用すると、クラウドデータビューから任意のCustomer Journey Analyticsストレージの宛先にデータを書き出すことができます。

![BI 拡張機能 ](../assets/export-datasets.svg)

## 詳細情報

Experience Platformのデータレイクからクラウドストレージの宛先に、未加工データセットを書き出すことができます。 この書き出しは、データセット書き出し宛先と呼ばれるExperience Platformー宛先の用語で使用されます。 詳しくは、[ クラウドストレージの宛先へのデータセットの書き出し ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets) を参照してください。

次のクラウドストレージの宛先がサポートされています。

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### EXPERIENCE PLATFORMUI

Experience PlatformUI を使用して、データセットの書き出しをスケジュールできます。 この節では、関連する手順について説明します。

#### 宛先を選択

データセットの書き出し先となるクラウドストレージの宛先を決定したら、[ 宛先を選択 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination) します。 優先クラウドストレージの宛先をまだ設定していない場合は、[ 新しい宛先接続を作成する ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/connect-destination) 必要があります。

宛先の設定の一環として、次の項目を定義できます。

- ファイルタイプ（JSON または Parquet）
- 結果のファイルが圧縮されるかどうか、および
- マニフェストファイルを含めるかどうか。


#### データセットを選択

宛先を選択したら、次の **[!UICONTROL データセットを選択]** 手順で、データセットのリストからデータセットを選択する必要があります。 複数のスケジュール済みクエリを作成し、データセットを同じクラウドストレージ宛先に送信する場合、対応するデータセットを選択できます。 詳しくは [ データセットの選択 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) を参照してください。

#### データセット書き出しのスケジュール設定

最後に、**[!UICONTROL スケジュール設定]** 手順の一部としてデータセットの書き出しをスケジュールします。 その手順では、スケジュールと、データセットの書き出しを増分で行うかどうかを定義できます。 詳しくは [ データセットの書き出しをスケジュール ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) を参照してください。


#### 最終手順

[ 確認 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets#review) 選択し、正しければ、クラウドストレージの宛先へのデータセットの書き出しを開始します。

まず、データの書き出しが正常に行われたことを [ 検証 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets#verify) する必要があります。 データセットを書き出す際、Experience Platformは、書き出し先に定義されたストレージの場所に 1 つまたは複数の `.json` ファイルまたは `.parquet` ファイルを作成します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM` のパターンに従って、書き出しのたびに新しいフォルダーが作成されます。 デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

### フローサービス API

または、API を使用してデータセットの書き出しを書き出し、スケジュールすることもできます。 含まれる手順は、[Flow Service API を使用したデータセットの書き出し ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets) に記載されています。

#### 基本を学ぶ

データセットを書き出すには、[ 必要な権限 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#permissions) があることを確認します。 また、データセットの送信先がデータセットの書き出しをサポートしていることを確認します。 次に、API 呼び出しで使用する [ 必須ヘッダーとオプションヘッダーの値を収集する ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) 必要があります。 また、データセットを書き出す [ 宛先の接続仕様 ID とフロー仕様 ID](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) を識別する必要もあります。

#### 適格なデータセットの取得

書き出し用に [ 適格なデータセットのリストを取得 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) し、データセットが [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API を使用してそのリストに含まれているかどうかを確認できます。


#### ソース接続を作成

次に、クラウドストレージの宛先に書き出す、一意の ID を使用したデータセットの [ ソース接続を作成 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#create-source-connection) する必要があります。 [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API を使用します。

#### 宛先に対する認証（ベース接続の作成）

[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API を使用して認証を行い、クラウドストレージの宛先に資格情報を安全に保存するには、[ ベース接続を作成 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#create-base-connection) する必要があります。


#### エクスポートパラメーターの指定

次に、[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API を使用してデータセットの [ 書き出しパラメーターを保存する追加のターゲット接続の作成 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#create-target-connection) を行う必要があります。 これらの書き出しパラメーターには、場所、ファイル形式、圧縮などが含まれます。

#### データフローの設定

最後に、[ データフローの設定 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#create-dataflow) を行い、[`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API を使用してデータセットがクラウドストレージの宛先に書き出されるようにします。 この手順では、`scheduleParams` パラメーターを使用して、書き出しのスケジュールを定義できます。

#### データフローの検証

[ データフローの正常な実行を確認 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs) するには、[`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API を使用して、データフロー ID をクエリパラメーターとして指定します。 このデータフロー ID は、データフローを設定したときに返される識別子です。

[ 検証 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets#verify) 成功したデータ書き出し。 データセットを書き出す際、Experience Platformは、書き出し先に定義されたストレージの場所に 1 つまたは複数の `.json` ファイルまたは `.parquet` ファイルを作成します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM` のパターンに従って、書き出しのたびに新しいフォルダーが作成されます。 デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。
