---
description: Customer Journey Analyticsデータを送信できるクラウドの書き出し場所の設定
keywords: Analysis Workspace
title: クラウドの書き出し場所の設定
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 067a9e3d5319a33bb5ae894d76f3445e2d968d0e
workflow-type: tm+mt
source-wordcount: '1789'
ht-degree: 19%

---

# クラウドの書き出し場所の設定

の説明に従って、Customer Journey Analyticsレポートをクラウドの宛先に書き出す前に [クラウドへのCustomer Journey Analyticsレポートの書き出し](/help/analysis-workspace/export/export-cloud.md)を作成する場合は、データを送信する場所を追加および設定する必要があります。

このプロセスでは、に示すように、アカウント（Amazon S3、Google Cloud Platform など）を追加し、設定します。 [クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)その後、この記事で説明しているように、そのアカウント内の場所（アカウント内のフォルダーなど）を追加して設定します。

ロケーションの表示、編集、削除など、既存のロケーションの管理方法については、を参照してください。 [クラウドの書き出し場所とアカウントの管理](/help/components/exports/manage-export-locations.md).

## クラウドの書き出し場所の作成を開始

1. 場所を追加するには、アカウントを追加する必要があります。 アカウントをまだ追加していない場合は、の説明に従ってアカウントを追加します。 [クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md).

1. Customer Journey Analyticsで、を選択します。 [!UICONTROL **Components**] > [!UICONTROL **エクスポート**].

1. 「」を選択します [!UICONTROL **場所**] tab キーを押してから、 [!UICONTROL **場所を追加**].

   ![「場所を追加」ボタンをハイライト表示した「場所」タブが選択されたエクスポートウィンドウ](assets/location-add.png)

   または

   「」を選択します [!UICONTROL **場所アカウント**] タブで、場所を追加する既存のアカウント上の「。..」アイコンを選択し、以下を選択します [!UICONTROL **場所を追加**].

   ![「場所を追加」が選択されていることを示す GCP アカウントと省略記号ドロップダウンメニュー](assets/add-location-existing-account.png)

   場所ダイアログが表示されます。

1. 次の情報を指定します。 |フィールド |関数 | |---------|----------| | [!UICONTROL **名前**] |場所の名前。  | | [!UICONTROL **説明**] | アカウント上の他の場所との区別に役立つ、場所の短い説明を入力します。 | | [!UICONTROL **場所アカウント**] |場所を作成するアカウントを選択します。 アカウントの作成方法については、を参照してください [クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md). |

1. Adobe Analytics の「[!UICONTROL **場所のプロパティ**]」セクションで、場所アカウントのアカウントタイプに固有の情報を指定します。

   で選択したアカウントタイプに対応する、以下の節を続行します。 [!UICONTROL **場所アカウント**] フィールド。

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

   * 前述の「」の書き出しページから [クラウドの書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **場所のプロパティ**] の節 [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定してAdobe Experience Platform データランディングゾーンの場所を設定します。

   <!-- still need to update; can't create AEP account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータをエクスポートする方法については、を参照してください。 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

1. AEP Data Landing Zone のデータにアクセスする最も簡単な方法は、Microsoft Azure ストレージエクスプローラーを使用することです。 これは、の設定手順で使用するのと同じツールです。 [AEP Data Landing Zone アカウント](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. を開きます [Microsoft Azure ストレージエクスプローラー](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. に移動 [!UICONTROL **ストレージアカウント**] > [!UICONTROL **（附属容器）**] > [!UICONTROL **Blob コンテナ**] > **[!UICONTROL cjaexport-_数値_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >フォルダー名 **[!UICONTROL cjaexport-_数値_]**は、Azure ストレージエクスプローラーから提供されるデフォルトの名前です。 SAS URI に関連付けられている接続が 1 つのみ（通常）の場合、このフォルダーの名前はになります&#x200B;**[!UICONTROL cjaexport-1]**.


      ![Azure ストレージエクスプローラーでのファイルへのアクセス](assets/azure-storage-explorer-access.png)

   1. ダウンロードするエクスポートを選択し、次のいずれかを選択します [!UICONTROL **Download**] をダウンロードします。

### Amazon S3 Role ARN

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述の「」の書き出しページから [クラウドの書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **場所のプロパティ**] の節 [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定してAmazon S3 ロール ARN の場所を設定します。

   <!-- still need to update; can't create S3 role ARN account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Adobe Analytics データを送信する Amazon S3 アカウント内のバケット。 <p>Adobeから提供されたユーザー ARN に、次のものが含まれていることを確認します `S3:PutObject` このバケットにファイルをアップロードするための権限。 </p><p>バケット名は、特定の命名規則を満たす必要があります。 例えば、3 ～ 63 文字の長さにする必要があり、小文字、数字、ドット （.）、ハイフン （–）のみで構成でき、先頭と末尾は文字または数字にする必要があります。 [命名規則の完全なリストについては、AWS ドキュメントを参照してください](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータをエクスポートする方法については、を参照してください。 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述の「」の書き出しページから [クラウドの書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **場所のプロパティ**] の節 [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定してGoogle Cloud Platform の場所を設定します。

   <!-- still need to update; can't create GCP account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Adobe Analytics データを送信する GCP アカウント内のバケット。 <p>を付与したことを確認します `roles/storage.objectCreator` Adobeで提供されるプリンシパルへの許可。 （元本の確定時期 [Google Cloud Platform アカウントの設定](/help/components/exports/cloud-export-accounts.md).） <p>権限の付与について詳しくは、Google Cloud ドキュメントの[バケットレベルのポリシーにプリンシパルを追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=ja#bucket-add)を参照してください。</p> |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータをエクスポートする方法については、を参照してください。 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述の「」の書き出しページから [クラウドの書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **場所のプロパティ**] の節 [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定して Azure SAS の場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ名**] | Customer Journey Analyticsデータの送信先として指定したアカウント内のコンテナ。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：`folder_name/`<p>Azure SAS アカウントを設定する際に、Key Vault 秘密鍵名フィールドに指定した SAS トークンストアに `Write` 権限があることを確認します。これにより、SAS トークンで Azure コンテナにファイルを作成できます。 <p>SAS トークンでファイルも上書きする場合は、SAS トークンストアに `Delete` 権限があることを確認します。</p><p>詳しくは、Azure Blob Storage ドキュメントの [Blob Storage のリソース](https://learn.microsoft.com/ja-jp/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)を参照してください。</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータをエクスポートする方法については、を参照してください。 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述の「」の書き出しページから [クラウドの書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **場所のプロパティ**] の節 [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定して Azure RBAC の場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。以前に作成した Azure アプリケーションにファイルをアップロードする権限を付与します。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にスラッシュを追加してフォルダーを作成します。 例：`folder_name/`<p>Azure RBAC アカウントの設定時に指定したアプリケーション ID に、コンテナ（フォルダー）にアクセスするための `Storage Blob Data Contributor` の役割が付与されていることを確認します。</p> <p>詳しくは、[Azure の組み込みの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p> |
   | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータをエクスポートする方法については、を参照してください。 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. 次のいずれかの方法で、クラウドの書き出し場所の作成を開始します。

   * 前述の「」の書き出しページから [クラウドの書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **場所のプロパティ**] の節 [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定してSnowflakeの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **DB**] | 既存のデータベースを指定してください。 作成した役割には、このデータベースにアクセスするための権限が必要です。<p>これは、ステージ名に関連付けられたデータベースです。</p><p>このロール権限をSnowflake内のデータベースに付与するには、次のコマンドを使用します。 `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>詳しくは、 [Snowflakeドキュメントのデータベース、スキーマ、および共有コマンドページ](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **スキーマ**] | 既存のスキーマを指定する必要があります。 作成した役割には、このスキーマにアクセスするための権限が必要です。<p>これは、ステージ名に関連付けられたスキーマです。<p>作成したロールに、Snowflakeのスキーマに権限を付与するには、次のコマンドを使用します。 `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>詳しくは、 [Snowflakeドキュメントのデータベース、スキーマ、および共有コマンドページ](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **ステージ名**] | データファイルがSnowflakeに保存される内部ステージの名前。<p>アカウントで指定した役割に、このステージ名への読み取りおよび書き込みアクセス権があることを確認してください。 （読み取りおよび書き込みアクセス権を付与するので、Adobeでのみ使用するステージを使用することをお勧めします。）<p>次のコマンドを使用して、Snowflakeのステージ名に読み取りおよび書き込みアクセス権を付与できます。 `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>ロールに対する権限の付与については、次を参照してください [Snowflakeドキュメントでの権限の付与](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>ステージ名の詳細については、を参照してください [Snowflakeドキュメントのローカルファイルの内部ステージの選択](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **ステージパス**] | データファイルがSnowflakeに格納されている場所のパス。 <p>詳しくは、 [Snowflakeドキュメントのローカルファイルの内部ステージの選択](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータをエクスポートする方法については、を参照してください。 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).
