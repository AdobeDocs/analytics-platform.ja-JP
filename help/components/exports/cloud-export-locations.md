---
description: Customer Journey Analyticsデータを送信できるクラウドの書き出し場所を設定する
keywords: Analysis Workspace
title: クラウドの書き出し場所の設定
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 3d4017ba36ac4b0c9ccb10a3e3127c6ea386fb1e
workflow-type: tm+mt
source-wordcount: '1415'
ht-degree: 4%

---

# クラウドの書き出し場所の設定

Customer Journey Analyticsレポートをクラウドの宛先に書き出す前に、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md)に値を入力する場合は、データを送信する場所を追加して設定する必要があります。

このプロセスは、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md)をクリックし、この記事で説明するように、そのアカウント内の場所（アカウント内のフォルダーなど）を追加して設定します。

場所の表示、編集、削除など、既存の場所の管理方法について詳しくは、 [クラウドの書き出し場所とアカウントを管理](/help/components/exports/manage-export-locations.md).

## クラウドの書き出し場所の作成を開始します

1. 場所を追加する前に、アカウントを追加する必要があります。 まだアカウントを追加していない場合は、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md).

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **場所**] 「 」タブで、「 [!UICONTROL **場所を追加**].

   ![場所を追加ボタン](assets/location-add.png)

   または

   を選択します。 [!UICONTROL **場所のアカウント**] タブで、場所を追加する既存のアカウントの 3 ドットアイコンを選択し、「 [!UICONTROL **場所を追加**].

   ![既存のアカウントに場所を追加](assets/add-location-existing-account.png)

   [ ロケーション ] ダイアログが表示されます。

1. 次の情報を指定します。 |フィールド |関数 | |—|—| | [!UICONTROL **名前**] |場所の名前。  | | [!UICONTROL **説明**] |同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 | | [!UICONTROL **場所アカウント**] |ロケーションを作成するアカウントを選択します。 アカウントの作成方法について詳しくは、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md). |

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] 「 」セクションで、ロケーションアカウントのアカウントタイプに固有の情報を指定します。

   で選択したアカウントタイプに対応する以下のセクションに進みます。 [!UICONTROL **場所アカウント**] フィールドに入力します。

### AEP データランディングゾーン

>[!IMPORTANT]
>
>Customer Journey AnalyticsレポートをAdobe Experience Platform Data Landing Zone に書き出す場合は、7 日以内にデータをダウンロードしてから、AEP Data Landing Zone から削除してください。 7 日後に、データは AEP データランディングゾーンから自動的に削除されます。

1. [クラウドの書き出し場所の作成を開始します](#begin-creating-a-cloud-export-location)（前述のように）

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] のセクション [!UICONTROL **場所を追加**] ダイアログボックスで、Adobe Experience Platform Data Landing Zone の場所を設定する次の情報を指定します。

   <!-- still need to update; can't create AEP account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **IMS 組織 ID**] | IMS Org ID は、Adobeが提供します。 の横にあるコピーアイコンをクリックします。 [!UICONTROL **IMS Org ID**] フィールドを使用してフィールドの内容をコピーし、Experience Platform アカウントで ID をAdobeします。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. これで、Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法について詳しくは、 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Amazon S3 Role ARN

1. [クラウドの書き出し場所の作成を開始します](#begin-creating-a-cloud-export-location)（前述のように）

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] のセクション [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定して、Amazon S3 の役割の ARN の場所を設定します。

   <!-- still need to update; can't create S3 role ARN account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **グループ**] | Adobe Analyticsデータを送信するAmazon S3 アカウント内のバケット。 Adobeから提供されたユーザー ARN が、このバケットにファイルをアップロードするためのアクセス権を持っていることを確認します。 |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. これで、Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法について詳しくは、 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. [クラウドの書き出し場所の作成を開始します](#begin-creating-a-cloud-export-location)（前述のように）

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] のセクション [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定してGoogle Cloud Platform の場所を設定します。

   <!-- still need to update; can't create GCP account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **グループ**] | Customer Journey Analyticsデータを送信する GCP アカウント内のバケット。 ファイルをこのバケットにアップロードするための権限が、Adobeから提供されるプリンシパルに対して付与されていることを確認します。 ( 本人は、次の場合に定める。 [Google Cloud Platform アカウントの設定](/help/components/exports/cloud-export-accounts.md).) 権限の付与について詳しくは、 [プリンシパルをバケットレベルのポリシーに追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) ( Google Cloud ドキュメント ) を参照してください。 |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. これで、Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法について詳しくは、 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. [クラウドの書き出し場所の作成を開始します](#begin-creating-a-cloud-export-location)（前述のように）

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] のセクション [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定して Azure SAS の場所を構成します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ名**] | アカウントデータの送信先として指定したCustomer Journey Analytics内のコンテナです。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. これで、Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法について詳しくは、 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. [クラウドの書き出し場所の作成を開始します](#begin-creating-a-cloud-export-location)（前述のように）

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] のセクション [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定して Azure RBAC の場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ**] | Adobe Analyticsデータを送信するアカウント内のコンテナです。 前に作成した Azure アプリケーションにファイルをアップロードする権限を付与してください。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |
   | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. これで、Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法について詳しくは、 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. [クラウドの書き出し場所の作成を開始します](#begin-creating-a-cloud-export-location)（前述のように）

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] のセクション [!UICONTROL **場所を追加**] ダイアログボックスで、次の情報を指定してSnowflakeの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **DB**] | 指定したデータベースは既存のデータベースである必要があります。 作成した役割には、このデータベースにアクセスする権限が必要です。<p>ステージ名に関連付けられているデータベースです。</p><p>次のコマンドを使用して、Snowflake内のデータベースにこのロール権限を付与できます。 `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>詳しくは、 [データベース、スキーマ、共有コマンドのページ (Snowflake・ドキュメント内 )](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **スキーマ**] | 指定されたスキーマは既存のスキーマである必要があります。 作成した役割には、このスキーマにアクセスする権限が必要です。<p>これは、ステージ名に関連付けられたスキーマです。<p>次のコマンドを使用して、作成したロールをSnowflake内のスキーマに付与できます。 `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>詳しくは、 [データベース、スキーマ、共有コマンドのページ (Snowflake・ドキュメント内 )](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **ステージ名**] | データファイルがSnowflakeに保存される内部ステージの名前。<p>アカウントで指定した役割が、このステージ名に対する読み取りおよび書き込みアクセス権を持っていることを確認します。 ( 読み取りと書き込みのアクセス権を付与するので、Adobeのみで使用するステージを使用することをお勧めします )。<p>次のコマンドを使用して、Snowflake内のステージ名に対して読み取りと書き込みのアクセス権を付与できます。 `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>ロールへの権限の付与について詳しくは、 [権限の付与については、Snowflakeドキュメントを参照してください](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>ステージ名について詳しくは、 [ローカルファイルの内部ステージの選択ページ (Snowflakeドキュメント )](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **ステージパス**] | データファイルが保存されている場所のSnowflake。 <p>詳しくは、 [ローカルファイルの内部ステージの選択ページ (Snowflakeドキュメント )](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. これで、Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法について詳しくは、 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).
