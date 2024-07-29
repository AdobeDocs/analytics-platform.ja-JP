---
description: Customer Journey Analyticsデータを送信できるクラウドの書き出し場所の設定
keywords: Analysis Workspace
title: クラウドの書き出し場所の設定
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: ec8f6c3c8cc1c0b12821e3b61fbef9f5fe875258
workflow-type: tm+mt
source-wordcount: '1888'
ht-degree: 20%

---

# クラウドの書き出し場所の設定

[ クラウドへのCustomer Journey Analyticsレポートの書き出し ](/help/analysis-workspace/export/export-cloud.md) の説明に従ってクラウドの宛先にCustomer Journey Analyticsレポートを書き出す前に、データを送信する場所を追加および設定する必要があります。

このプロセスでは、[ クラウドの書き出しアカウントの設定 ](/help/components/exports/cloud-export-accounts.md) の説明に従ってアカウント（Amazon S3、Google Cloud Platform など）を追加および設定し、次に、この記事の説明に従って、そのアカウント内の場所（アカウント内のフォルダーなど）を追加および設定します。

場所の表示、編集、削除など、既存の場所を管理する方法について詳しくは、[ クラウドの書き出し場所とアカウントの管理 ](/help/components/exports/manage-export-locations.md) を参照してください。

## クラウドの書き出し場所の作成を開始

1. 場所を追加するには、アカウントを追加する必要があります。 アカウントをまだ追加していない場合は、[ クラウド書き出しアカウントの設定 ](/help/components/exports/cloud-export-accounts.md) の説明に従ってアカウントを追加します。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **場所**]」タブを選択し、「[!UICONTROL **場所を追加**]」を選択します。

   ![ 「場所を追加」ボタンがハイライト表示された「場所」タブが選択されたエクスポートウィンドウ ](assets/location-add.png)

   または

   「[!UICONTROL **場所アカウント**]」タブを選択し、場所を追加する既存のアカウント上にある 3 ドットアイコンを選択して、「[!UICONTROL **場所を追加**]」を選択します。

   ![GCP アカウントと「場所を追加」が選択されていることを示す省略記号ドロップダウンメニュー ](assets/add-location-existing-account.png)

   場所ダイアログが表示されます。

1. 次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **名前**] | 場所の名前。 |
   | [!UICONTROL **説明**] | アカウントの他の場所との区別に役立つ、場所の短い説明を入力します。 |
   | [!UICONTROL **組織内のすべてのユーザーが場所を利用できるようにする**] | 組織内の他のユーザーが場所を使用できるようにするには、このオプションを有効にします。 <p>場所を共有する際は、次の点に注意してください。</p><ul><li>共有する場所の共有を解除することはできません。</li><li>共有場所は、その場所の所有者のみが編集できます。</li><li>場所を共有できるのは、その場所が関連付けられているアカウントも共有されている場合のみです。</li></ul> |
   | [!UICONTROL **場所アカウント**] | 場所を作成するアカウントを選択します。 アカウントの作成方法について詳しくは、[ クラウド書き出しアカウントの設定 ](/help/components/exports/cloud-export-accounts.md) を参照してください。 |

1. Adobe Analytics の「[!UICONTROL **場所のプロパティ**]」セクションで、場所アカウントのアカウントタイプに固有の情報を指定します。

   「[!UICONTROL **場所アカウント**]」フィールドで選択したアカウントタイプに対応する、以下の節を続行します。

   * [AEP データランディングゾーン](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP データランディングゾーン

>[!IMPORTANT]
>
>Customer Journey AnalyticsレポートをAdobe Experience Platform データランディングゾーンに書き出す場合は、7 日以内にデータをダウンロードし、AEP データランディングゾーンから削除してください。 7 日後、データは AEP データランディングゾーンから自動的に削除されます。

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述した書き出しページの [ クラウドの書き出し場所の作成を開始 ](#begin-creating-a-cloud-export-location)

   * [Analysis Workspaceからの完全なテーブルの書き出し ](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) の場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの [!UICONTROL **場所のプロパティ**] セクションで、次の情報を指定してAdobe Experience Platform Data Landing Zone の場所を設定します。

   <!-- still need to update; can't create AEP account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法については、[ クラウドへのプロジェクトデータの書き出し ](/help/analysis-workspace/export/export-cloud.md) を参照してください。

1. AEP Data Landing Zone のデータにアクセスする最も簡単な方法は、Microsoft Azure ストレージエクスプローラーを使用することです。 これは、[AEP データランディングゾーンアカウント ](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone) を設定する手順で使用するツールと同じです。

   1. [Microsoft Azure ストレージエクスプローラー ](https://azure.microsoft.com/en-us/products/storage/storage-explorer/) を開きます。

   1. [!UICONTROL **ストレージアカウント**]/[!UICONTROL **（添付コンテナ）**]/[!UICONTROL **BLOB コンテナ**]/**[!UICONTROL cjaexport-_number_]**/*** your_container_name ***に移動します。

      >[!NOTE]
      >
      >Azure ストレージエクスプローラーから提供されるデフォルトの名前はフォルダー名 **[!UICONTROL cjaexport-_number_]**です。 SAS URI に関連付けられている接続が 1 つのみ（通常）の場合、このフォルダーの名前は&#x200B;**[!UICONTROL cjaexport-1]**になります。


      ![Azure ストレージエクスプローラー内のファイルへのアクセス ](assets/azure-storage-explorer-access.png)

   1. ダウンロードするエクスポートを選択してから、「[!UICONTROL **ダウンロード**]」を選択してダウンロードします。

### Amazon S3 Role ARN

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述した書き出しページの [ クラウドの書き出し場所の作成を開始 ](#begin-creating-a-cloud-export-location)

   * [Analysis Workspaceからの完全なテーブルの書き出し ](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) の場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの [!UICONTROL **場所のプロパティ**] セクションで、次の情報を指定してAmazon S3 Role ARN の場所を設定します。

   <!-- still need to update; can't create S3 role ARN account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Customer Journey Analyticsデータを送信するAmazon S3 アカウント内のバケット。 <p>Adobeから提供されたユーザー ARN に、このバケットにファイルをアップロードするための `S3:PutObject` 権限があることを確認します。 </p><p>バケット名は、特定の命名規則を満たす必要があります。例えば、3〜63 文字までの長さで、小文字、数字、ドット（.）、ハイフン（-）のみで構成でき、先頭と末尾は文字または数字にする必要があります。[命名規則の完全なリストについて詳しくは、AWS ドキュメントを参照してください](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/userguide/bucketnamingrules.html)。 </p> |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法については、[ クラウドへのプロジェクトデータの書き出し ](/help/analysis-workspace/export/export-cloud.md) を参照してください。

### Google Cloud Platform

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述した書き出しページの [ クラウドの書き出し場所の作成を開始 ](#begin-creating-a-cloud-export-location)

   * [Analysis Workspaceからの完全なテーブルの書き出し ](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) の場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの [!UICONTROL **場所のプロパティ**] セクションで、次の情報を指定してGoogle Cloud Platform の場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Customer Journey Analyticsデータを送信する GCP アカウント内のバケット。 <p>Adobeから提供されたプリンシパルに `roles/storage.objectCreator` 権限を付与していることを確認してください。 （プリンシパルは、[Google Cloud Platform アカウントの設定 ](/help/components/exports/cloud-export-accounts.md) 時に提供されます。 <p>権限の付与について詳しくは、Google Cloud ドキュメントの[バケットレベルのポリシーにプリンシパルを追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=ja#bucket-add)を参照してください。</p><p>組織が[組織ポリシーの制約](https://cloud.google.com/storage/docs/org-policy-constraints)を使用して許可リスト内の Google Cloud Platform アカウントのみを許可している場合は、次のアドビ所有の Google Cloud Platform 組織 ID が必要です。 <ul><li>`DISPLAY_NAME`：`adobe.com`</li><li>`ID`：`178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`：`C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法については、[ クラウドへのプロジェクトデータの書き出し ](/help/analysis-workspace/export/export-cloud.md) を参照してください。

### Azure SAS

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述した書き出しページの [ クラウドの書き出し場所の作成を開始 ](#begin-creating-a-cloud-export-location)

   * [Analysis Workspaceからの完全なテーブルの書き出し ](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) の場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの [!UICONTROL **場所のプロパティ**] セクションで、次の情報を指定して Azure SAS の場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ名**] | Customer Journey Analyticsデータの送信先として指定したアカウント内のコンテナ。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：`folder_name/`<p>Azure SAS アカウントを設定する際に、Key Vault 秘密鍵名フィールドに指定した SAS トークンストアに `Write` 権限があることを確認します。これにより、SAS トークンで Azure コンテナにファイルを作成できます。 <p>SAS トークンでファイルも上書きする場合は、SAS トークンストアに `Delete` 権限があることを確認します。</p><p>詳しくは、Azure Blob Storage ドキュメントの [Blob Storage のリソース](https://learn.microsoft.com/ja-jp/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)を参照してください。</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法については、[ クラウドへのプロジェクトデータの書き出し ](/help/analysis-workspace/export/export-cloud.md) を参照してください。

### Azure RBAC

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述した書き出しページの [ クラウドの書き出し場所の作成を開始 ](#begin-creating-a-cloud-export-location)

   * [Analysis Workspaceからの完全なテーブルの書き出し ](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) の場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの [!UICONTROL **場所のプロパティ**] セクションで、次の情報を指定して Azure RBAC の場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ**] | Customer Journey Analyticsデータの送信先として指定したアカウント内のコンテナ。 以前に作成した Azure アプリケーションにファイルをアップロードする権限を付与します。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：`folder_name/`<p>Azure RBAC アカウントの設定時に指定したアプリケーション ID に、コンテナ（フォルダー）にアクセスするための `Storage Blob Data Contributor` の役割が付与されていることを確認します。</p> <p>詳しくは、[Azure の組み込みの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p> |
   | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法については、[ クラウドへのプロジェクトデータの書き出し ](/help/analysis-workspace/export/export-cloud.md) を参照してください。

### Snowflake

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述した書き出しページの [ クラウドの書き出し場所の作成を開始 ](#begin-creating-a-cloud-export-location)

   * [Analysis Workspaceからの完全なテーブルの書き出し ](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) の場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの [!UICONTROL **場所のプロパティ**] セクションで、次の情報を指定してSnowflakeの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **DB**] | 既存のデータベースを指定してください。 作成した役割には、このデータベースにアクセスするための権限が必要です。<p>これは、ステージ名に関連付けられたデータベースです。</p><p>次のコマンドを使用して、このロール権限をSnowflake内のデータベースに付与できます。`GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>詳しくは、[Snowflakeドキュメントのデータベース、スキーマ、および共有コマンドのページ ](https://docs.snowflake.com/en/sql-reference/commands-database) を参照してください。</p> |
   | [!UICONTROL **スキーマ**] | 既存のスキーマを指定する必要があります。 作成した役割には、このスキーマにアクセスするための権限が必要です。<p>これは、ステージ名に関連付けられたスキーマです。<p>次のコマンドを使用して、作成したロールにSnowflakeのスキーマに権限を付与できます。`GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>詳しくは、[Snowflakeドキュメントのデータベース、スキーマ、および共有コマンドのページ ](https://docs.snowflake.com/en/sql-reference/commands-database) を参照してください。</p> |
   | [!UICONTROL **ステージ名**] | データファイルがSnowflakeに保存される内部ステージの名前。<p>アカウントで指定した役割に、このステージ名への読み取りおよび書き込みアクセス権があることを確認してください。 （読み取りおよび書き込みアクセス権を付与するので、Adobeでのみ使用するステージを使用することをお勧めします。）<p>次のコマンドを使用して、Snowflakeのステージ名に読み取りおよび書き込みアクセス権を付与できます：`GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>ロールへの権限の付与について詳しくは、[Snowflakeドキュメントでの権限の付与 ](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege) を参照してください。 <p>ステージ名の詳細については、Snowflakeドキュメントの [ ローカルファイルの内部ステージの選択 ](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage) を参照してください。</p> |
   | [!UICONTROL **ステージパス**] | データファイルがSnowflakeに格納されている場所のパス。 <p>詳しくは、Snowflakeドキュメントの [ ローカルファイルの内部ステージの選択 ](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage) を参照してください。</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法については、[ クラウドへのプロジェクトデータの書き出し ](/help/analysis-workspace/export/export-cloud.md) を参照してください。
