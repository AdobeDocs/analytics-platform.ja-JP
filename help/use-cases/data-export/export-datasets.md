---
title: データセットの書き出しCustomer Journey Analytics
description: データセットの書き出しを使用してデータをバックアップする方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 6%

---


# データセットを書き出し

この記事では、その方法を説明します [!DNL Customer Journey Analytics Export datasets] を使用して、以下を実装できます [データ書き出しのユースケース](overview.md):

- データバックアップ

## はじめに

を使用したデータのエクスポート [!DNL Experience Platform Export datasets] では、クラウドデータビューから任意のCustomer Journey Analyticsストレージの宛先にデータを書き出すことができます。

![BI 拡張機能](../assets/export-datasets.svg)

## 詳細情報

Experience Platformのデータレイクからクラウドストレージの宛先に、未加工データセットを書き出すことができます。 この書き出しは、データセット書き出し宛先と呼ばれるExperience Platformー宛先の用語で使用されます。 参照： [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) を参照してください。

次のクラウドストレージの宛先がサポートされています。

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### EXPERIENCE PLATFORMUI

Experience PlatformUI を使用して、データセットの書き出しをスケジュールできます。 この節では、関連する手順について説明します。

#### 宛先を選択

データセットの書き出し先となるクラウドストレージの宛先を決定したら、 [宛先を選択](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). 優先クラウドストレージの宛先をまだ設定していない場合は、次の操作を行う必要があります [新しい宛先接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

宛先の設定の一環として、次の項目を定義できます。

- ファイルタイプ（JSON または Parquet）
- 結果のファイルが圧縮されるかどうか、および
- マニフェストファイルを含めるかどうか。


#### データセットを選択

宛先を選択した場合、次の **[!UICONTROL データセットを選択]** 手順データセットのリストからデータセットを選択する必要があります。 複数のスケジュール済みクエリを作成し、データセットを同じクラウドストレージ宛先に送信する場合、対応するデータセットを選択できます。 参照： [データセットを選択](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) を参照してください。

#### データセット書き出しのスケジュール設定

最後に、の一部としてデータセットの書き出しをスケジュールします **[!UICONTROL スケジュール]** ステップ。 その手順では、スケジュールと、データセットの書き出しを増分で行うかどうかを定義できます。 参照： [データセットの書き出しをスケジュール](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) を参照してください。


#### 最終手順

[レビュー](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) 選択した内容が正しければ、クラウドストレージの宛先へのデータセットの書き出しを開始します。

まず、以下を行う必要があります [検証](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) データの書き出しが成功した。 データセットを書き出す際に、Experience Platformが 1 つ以上のデータセットを作成する `.json` または `.parquet` 宛先で定義されたストレージの場所にあるファイル。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出しのたびに、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

### フローサービス API

または、API を使用してデータセットの書き出しを書き出し、スケジュールすることもできます。 関連する手順は、に記載されています。 [Flow Service API を使用したデータセットの書き出し](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### 基本を学ぶ

データセットを書き出すには、次があることを確認します [必要な権限](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). また、データセットの送信先がデータセットの書き出しをサポートしていることを確認します。 次に、以下を行う必要があります [必須ヘッダーおよびオプションヘッダーの値の収集](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) api 呼び出しで使用する。 また、次の操作も必要です [宛先の接続仕様およびフロー仕様 ID の特定](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) データセットをに書き出そうとしています。

#### 適格なデータセットの取得

次のことができます [適格なデータセットのリストの取得](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) エクスポートの場合は、を使用して、データセットがそのリストに含まれているかどうかを確認します。 [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API です。


#### ソース接続を作成

次に、以下を行う必要があります [ソース接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) 一意の ID を使用する、クラウドストレージの宛先に書き出すデータセットの場合。 を使用します [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API です。

#### 宛先に対する認証（ベース接続の作成）

次に、以下を行う必要があります [ベース接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) を使用して、資格情報を認証し、クラウドストレージの宛先に安全に保存するには [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API です。


#### エクスポートパラメーターの指定

次に、以下を行う必要があります [エクスポートパラメーターを格納する追加のターゲット接続の作成](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) を使用したデータセットの場合、もう一度 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API です。 これらの書き出しパラメーターには、場所、ファイル形式、圧縮などが含まれます。

#### データフローの設定

最後に、あなたは [データフローの設定](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) を使用して、データセットがクラウドストレージの宛先に書き出されることを確認します。 [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API です。 この手順では、を使用して書き出しのスケジュールを定義できます `scheduleParams` パラメーター。

#### データフローの検証

終了 [データフローの正常な実行の確認](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)、を使用します [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API。データフロー ID をクエリパラメーターとして指定します。 このデータフロー ID は、データフローを設定したときに返される識別子です。

[検証](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) データの書き出しが成功した。 データセットを書き出す際に、Experience Platformが 1 つ以上のデータセットを作成する `.json` または `.parquet` 宛先で定義されたストレージの場所にあるファイル。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されます。 Experience Platformは、選択された出力先の一部として指定されたストレージの場所にフォルダー構造を作成し、書き出されたファイルを格納します。 書き出しのたびに、次のパターンに従って新しいフォルダーが作成されます。 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。
