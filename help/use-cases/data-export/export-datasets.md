---
title: Customer Journey Analytics データセットの書き出し
description: データセットの書き出しを使用してデータをバックアップする方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
autotag-review: '2026-05-19T09:38:40.111Z'
TQID: 'https://experienceleague.adobe.com/az0B0Gzzu0pbb0TbpiZjW0Y-GysEptIETtg2bBFl-Uw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases, Use cases (CJA)
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 6%
---
# データセットの書き出し

この記事では、[!DNL Customer Journey Analytics Export datasets]を使用して次の[ データ書き出しの使用例](overview.md)を実装する方法について説明します。

- データバックアップ

## はじめに

[!DNL Experience Platform Export datasets]を使用してデータをエクスポートすると、Customer Journey Analytics データビューから任意のクラウドストレージの宛先にデータをエクスポートできます。

他の書き出し方法とは異なり、書き出しデータセットには固定の行制限はありません。 クラウドストレージの宛先の容量によって書き出しサイズが制限されるため、データの完全で未加工のコピーが必要な場合は、この機能が適しています。

![BI拡張機能](../assets/export-datasets.png)

## 詳細情報

Experience Platformのデータレイクから生データセットを書き出すには、クラウドストレージの宛先を使用します。 この書き出しは、Experience Platform Destinationsの用語では、データセット書き出し先と呼ばれます。 概要については、[ データセットをクラウドストレージの宛先に書き出し](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets)を参照してください。

次のクラウドストレージの宛先がサポートされています。

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Data Landing Zone](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google Cloud Storage](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure BLOB](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### EXPERIENCE PLATFORM UI

Experience Platform UIを使用して、データセットの書き出しをスケジュールできます。 この節では、関連する手順について説明します。

#### 宛先を選択

データセットを書き出すクラウドストレージの宛先を決定したら、[宛先](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination)を選択します。 優先クラウドストレージの宛先をまだ設定していない場合は、[新しい宛先接続を作成する必要があります](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination)。

宛先の設定の一環として、次の項目を定義できます。

- ファイルタイプ（JSONまたはParquet）、
- 生成されるファイルを圧縮するかどうか、および
- マニフェストファイルを含めるかどうかを指定します。


#### データセットを選択

宛先を選択した場合、次の&#x200B;**[!UICONTROL データセットを選択]** ステップで、データセットのリストからデータセットを選択する必要があります。 複数のスケジュール済みクエリを作成し、データセットを同じクラウドストレージの宛先に送信する場合は、対応するデータセットを選択できます。 詳しくは、[ データセットの選択](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets)を参照してください。

#### データセット書き出しのスケジュール設定

最後に、**[!UICONTROL スケジューリング]**&#x200B;手順の一環として、データセットの書き出しをスケジュールします。 この手順では、スケジュールと、データセットの書き出しが増分かどうかを定義します。 詳しくは、[ データセットの書き出しをスケジュール ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling)を参照してください。


#### 最終手順

[選択内容を確認](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review)し、正しい場合は、データセットをクラウドストレージの宛先に書き出します。

最初に、[ データの書き出しを正常に実行するには、](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)検証する必要があります。 データセットを書き出す場合、Experience Platformは、宛先の保存場所に1つまたは複数の`.json`または`.parquet`個のファイルを作成します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されることを期待します。 Experience Platformは、選択した保存先の一部として指定した保存場所にフォルダー構造を作成し、書き出されたファイルを保存します。 書き出し時間ごとに、パターン `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`に従って新しいフォルダーが作成されます。 デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。

### Flow Service API

または、APIを使用して、データセットの書き出しを書き出し、スケジュールすることもできます。 関連する手順については、[Flow Service APIを使用したデータセットの書き出し](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets)を参照してください。

#### 基本を学ぶ

データセットを書き出すには、[必要な権限](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions)があることを確認してください。 宛先がデータセットの書き出しをサポートしていることを確認します。 データセットをこの宛先に送信できます。 次に、[API呼び出しで使用する必須ヘッダーとオプション ヘッダー](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers)の値を収集する必要があります。 また、データセットを書き出す宛先](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec)の接続仕様とフロー仕様IDを[特定する必要があります。

#### 適格なデータセットの取得

[書き出しの対象となるデータセット ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets)のリストを取得し、[`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getDatasets) APIを使用して、データセットがそのリストに含まれているかどうかを確認できます。


#### ソース接続の作成

次に、クラウドストレージの宛先に書き出すデータセットの一意のIDを使用して、[ ソース接続](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection)を作成する必要があります。 [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postSourceConnection) APIを使用しています。

#### 宛先への認証（ベース接続の作成）

クラウドストレージの宛先に資格情報を認証して安全に保存するには、[[`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection) APIを使用してベース接続](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection)を作成します。


#### 書き出しパラメーターを指定

次に、[`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection) APIを使用して、データセットの書き出しパラメーター](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection)を格納する追加のターゲット接続を[作成する必要があります。 これらのエクスポートパラメーターには、場所、ファイル形式、圧縮などが含まれます。

#### データフローの設定

データセットがクラウドストレージの宛先に確実にエクスポートされるようにするには、[[`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postFlow) APIを使用してデータフロー](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow)を設定します。 この手順では、`scheduleParams` パラメーターを使用して、書き出しのスケジュールを定義できます。

#### データフローの検証

データフロー](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)の正常な実行を[確認するには、[`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getFlowRuns) APIを使用して、データフローIDをクエリパラメーターとして指定します。 このデータフローIDは、データフローの設定時に返される識別子です。

[ データの書き出しが成功したことを](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)確認します。 データセットを書き出す場合、Experience Platformは、宛先の保存場所に1つまたは複数の`.json`または`.parquet`個のファイルを作成します。 設定した書き出しスケジュールに従って、新しいファイルがストレージの場所に格納されることを期待します。 Experience Platformは、選択した保存先の一部として指定した保存場所にフォルダー構造を作成し、書き出されたファイルを保存します。 書き出し時間ごとに、パターン `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`に従って新しいフォルダーが作成されます。 デフォルトのファイル名はランダムに生成され、書き出されたファイルの名前は必ず一意になります。
