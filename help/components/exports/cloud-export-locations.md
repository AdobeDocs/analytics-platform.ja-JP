---
description: Customer Journey Analyticsデータを送信できるクラウドの書き出し場所を設定する
keywords: Analysis Workspace
title: クラウドの書き出し場所の設定
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 6%

---

# クラウドの書き出し場所の設定

{{select-package}}

クラウドの宛先にCustomer Journey Analyticsデータを書き出す前に、 [Customer Journey Analyticsデータをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)に値を入力する場合は、データを送信する場所を追加して設定する必要があります。

このプロセスは、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md)をクリックし、この記事で説明するように、そのアカウント内の場所（アカウント内のフォルダーなど）を追加して設定します。

場所の表示、編集、削除など、既存の場所の管理方法について詳しくは、 [クラウドの書き出し場所とアカウントを管理](/help/components/exports/manage-export-locations.md).

クラウドの書き出し先を設定するには：

1. 場所を追加する前に、アカウントを追加する必要があります。 まだアカウントを追加していない場合は、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md).
1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].
1. 次の日： [!UICONTROL エクスポート] ページで、 [!UICONTROL **場所**] タブをクリックします。
1. 選択 [!UICONTROL **場所を追加**].

   ![場所を追加ボタン](assets/location-add.png)

   [ ロケーション ] ダイアログが表示されます。

1. 次の情報を指定します。 |フィールド |関数 | |—|—| | [!UICONTROL **名前**] |場所の名前。  | | [!UICONTROL **説明**] |同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 | | [!UICONTROL **場所アカウント**] |で作成したロケーションアカウントを選択します。 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md). |

1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] 「 」セクションで、ロケーションアカウントのアカウントタイプに固有の情報を指定します。

   設定手順については、 [!UICONTROL **場所のアカウント**] フィールドに入力します。

   +++Amazon S3 Role ARN

   Amazon S3 の役割の ARN の場所を設定するには、次の情報を指定します。

   <!-- still need to update; can't create S3 role ARN account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **グループ**] | Adobe Analyticsデータを送信するAmazon S3 アカウント内のバケット。 Adobeから提供されたユーザー ARN が、このバケットにファイルをアップロードするためのアクセス権を持っていることを確認します。 |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Google Cloud Platform の場所を設定するには、次の情報を指定します。

   <!-- still need to update; can't create GCP account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **グループ**] | Customer Journey Analyticsデータを送信する GCP アカウント内のバケット。 ファイルをこのバケットにアップロードするための権限が、Adobeから提供されるプリンシパルに対して付与されていることを確認します。 ( 本人は、次の場合に定める。 [Google Cloud Platform アカウントの設定](/help/components/exports/cloud-export-accounts.md).) 権限の付与について詳しくは、 [プリンシパルをバケットレベルのポリシーに追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) ( Google Cloud ドキュメント ) を参照してください。 |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Azure SAS の場所を構成するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ名**] | アカウントデータの送信先として指定したCustomer Journey Analytics内のコンテナです。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Azure RBAC の場所を設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ**] | Adobe Analyticsデータを送信するアカウント内のコンテナです。 前に作成した Azure アプリケーションにファイルをアップロードする権限を付与してください。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |
   | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |

   {style="table-layout:auto"}

+++

   +++Snowflake

   次の情報を指定して、Snowflakeの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **DB**] | 接続時に使用するデフォルトのデータベース、または空の文字列を指定します。 指定したデフォルトの役割が権限を持つ既存のデータベースを指定します。 <p>詳しくは、 [「JDBC Driver Connection Parameter Reference」ページ (Snowflake・ドキュメント内 )](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **スキーマ**] | 接続後に指定したデータベースに対して使用するデフォルトのスキーマ、または空の文字列を指定します。 指定したスキーマは、指定したデフォルトの役割が権限を持つ既存のスキーマである必要があります。 <p>詳しくは、 [「JDBC Driver Connection Parameter Reference」ページ (Snowflake・ドキュメント内 )](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **ステージ名**] | データファイルが保存される場所の名前。Snowflake。 <p>詳しくは、 [ローカルファイルの内部ステージの選択ページ (Snowflakeドキュメント )](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **ステージパス**] | データファイルが保存されている場所のSnowflake。 <p>詳しくは、 [ローカルファイルの内部ステージの選択ページ (Snowflakeドキュメント )](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

   +++Adobe Experience Platform

   Adobe Experience Platformの場所を設定するには、次の情報を指定します。

   <!-- still need to update; can't create AEP account -->

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **IMS 組織 ID**] | IMS Org ID は、Adobeが提供します。 の横にあるコピーアイコンをクリックします。 [!UICONTROL **IMS Org ID**] フィールドを使用してフィールドの内容をコピーし、Experience Platform アカウントで ID をAdobeします。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

+++

1. 「[!UICONTROL **保存**]」を選択します。

1. これで、Analysis Workspaceから設定したアカウントと場所にデータを書き出せるようになりました。 クラウドにデータを書き出す方法について詳しくは、 [クラウドへのプロジェクトデータの書き出し](/help/analysis-workspace/export/export-cloud.md).