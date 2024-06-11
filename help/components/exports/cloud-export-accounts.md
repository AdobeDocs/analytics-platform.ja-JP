---
description: Customer Journey Analyticsデータを送信できる Cloud Export アカウントの設定
keywords: Analysis Workspace
title: クラウド書き出しアカウントの設定
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: 9a0e6ed66a20eac1fa5f94efd378842a579826c0
workflow-type: tm+mt
source-wordcount: '2009'
ht-degree: 29%

---

# クラウド書き出しアカウントの設定

の説明に従って、Customer Journey Analyticsレポートをクラウドの宛先に書き出す前に [クラウドへのCustomer Journey Analyticsレポートの書き出し](/help/analysis-workspace/export/export-cloud.md)の場合、データを送信する宛先を追加して設定する必要があります。

このプロセスでは、この記事に従ってアカウント（Amazon S3、Google Cloud Platform など）を追加および設定し、次に説明に従って、そのアカウント内の場所（アカウント内のフォルダーなど）を追加および設定します [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

アカウントの表示、編集、削除など、既存アカウントの管理方法については、を参照してください。 [クラウドの書き出し場所とアカウントの管理](/help/components/exports/manage-export-locations.md).

## クラウド書き出しアカウントの作成を開始

1. 必ずを満たすようにしてください。 [最小要件](/help/analysis-workspace/export/export-cloud.md#minimum-requirements) クラウドにレポートを書き出す場合。
1. Customer Journey Analyticsで、を選択します。 [!UICONTROL **Components**] > [!UICONTROL **エクスポート**].
1. 日 [!UICONTROL エクスポート] ページで、 [!UICONTROL **場所アカウント**] タブ。

   ![「別のアカウントを追加」を示すページオプションを書き出します。](assets/account-add.png)

1. を選択 [!UICONTROL **アカウントを追加**].

   アカウントを追加ダイアログが表示されます。

1. が含まれる [!UICONTROL **場所アカウント名**] フィールドで、場所アカウントの名前を指定します。 この名前は、場所を作成する際に表示されます。

1. が含まれる [!UICONTROL **場所アカウントの説明**] フィールドに、アカウントの簡単な説明を入力します。同じアカウントタイプを持つ他のアカウントとの区別に役立ちます。

1. このオプションを有効にすると、 [!UICONTROL **組織内のすべてのユーザーがアカウントを使用できるようにする**] 組織内の他のユーザーがアカウントを使用できるようにする場合。

   アカウントを共有する際は、次の点に注意してください。

   * 共有しているアカウントの共有を解除することはできません。

   * 共有アカウントは、そのアカウントの所有者のみが編集できます。

   * 共有アカウントの場所は誰でも作成できます。

   **注意：** この機能は、リリースの限定的テスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 機能が一般に利用できるようになったら、このメモは削除されます。Analytics リリースプロセスについて詳しくは、[Customer Journey Analytics 機能リリース](/help/release-notes/releases.md)を参照してください。

1. が含まれる [!UICONTROL **アカウントタイプ**] フィールドで、書き出し先のクラウドアカウントのタイプを選択します。 使用可能なアカウントタイプは、Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake、AEP Data Landing Zone です。

1. 以下の、に対応するセクションを続行します [!UICONTROL **アカウントタイプ**] が選択されました。

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

1. 次のいずれかの方法で、クラウド書き出しアカウントの作成を開始します。

   * 前述の「」の書き出しページから [クラウド書き出しアカウントの作成を開始](#begin-creating-a-cloud-export-account)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 「[!UICONTROL **保存**]」を選択します。

   この [!UICONTROL **書き出しアカウントが作成されました**] ダイアログが表示されます。

   ![アカウントの書き出しダイアログ AEP データランディングゾーン](assets/export-account-aep.png)

1. の内容をコピーします [!UICONTROL **SAS URI**] フィールドをクリップボードに追加します。 この SAS URI を使用して、AEP データランディングゾーンからAnalysis Workspaceから書き出されたデータにアクセスします。

   このフィールドが空の場合、Adobe Experience Platformへのアクセス権を付与されている必要があります。

1. Adobe Experience Platformで、コピーした SAS URI を使用するようにデータランディングゾーンコンテナを設定します。

   >[!NOTE]
   >
   >AEP データランディングゾーンのアカウントは Azure に基づいているので、AEP データランディングゾーンに書き出したレポートにアクセスする最も簡単な方法は、Azure ストレージエクスプローラーを使用することです。 次の手順では、この方法を使用します。

   1. まだダウンロードしていない場合は、 [Microsoft Azure ストレージエクスプローラー](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Adobe Experience Platform ドキュメントでは、で説明されている手順に従います [データランディングゾーンコンテナの Azure ストレージエクスプローラーへの接続](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#connect-your-data-landing-zone-container-to-azure-storage-explorer).

      セクションで説明したタスクはスキップできます [データランディングゾーンの資格情報の取得](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#retrieve-dlz-credentials) および [データランディングゾーン資格情報の更新](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#update-dlz-credentials)コピーした URI にはこれらの資格情報が含まれているので、

   1. Adobe Experience Platformのドキュメントに従い、次の手順を実行します [!UICONTROL **Blob コンテナ SAS URL**] フィールドに、手順 3 でコピーした SAS URI を貼り付けます。

      >[!NOTE]
      >
      >SAS URI は作成後 7 日で期限切れになるので、このアクションは 7 日ごとに実行する必要があります。 このプロセスを自動化するスクリプトを作成できます。


      ![SAS URL フィールドを表示する接続情報を入力ウィンドウ](assets/blob-container-sas-uri.png)

   1. を選択 [!UICONTROL **次**] > [!UICONTROL **接続**].

1. Customer Journey Analyticsで、次の場所にある [!UICONTROL **書き出しアカウントが作成されました**] ダイアログ、選択 [!UICONTROL **OK**].

   ![アカウントの書き出しダイアログ AEP データランディングゾーン](assets/export-account-aep.png)

1. 続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. 次のいずれかの方法で、クラウド書き出しアカウントの作成を開始します。

   * 前述の「」の書き出しページから [クラウド書き出しアカウントの作成を開始](#begin-creating-a-cloud-export-account)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **アカウントのプロパティ**] の節 [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 機能 |
   |---------|----------|
   | [!UICONTROL **役割 ARN**] | アドビが Amazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN（Amazon リソースネーム）を指定する必要があります。これを行うには、ソースアカウントの IAM 権限ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントの役割を作成します。詳しくは、[この AWS ドキュメント](https://repost.aws/ja/knowledge-center/cross-account-access-iam)を参照してください。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   この [!UICONTROL **書き出しアカウントが作成されました**] ダイアログが表示されます。

   ![アカウント作成ダイアログの書き出しAmazon S3 Role ARN](assets/export-account-amazons3.png)

1. の内容をコピーします [!UICONTROL **ユーザー ARN**] フィールドをクリップボードに追加します。 ユーザー ARN（Amazon リソースネーム）は、アドビが指定します。このユーザーをAmazon S3 Role ARN で作成したポリシーに関連付ける必要があります。

1. を選択 [!UICONTROL **OK**].

1. 続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. 次のいずれかの方法で、クラウド書き出しアカウントの作成を開始します。

   * 前述の「」の書き出しページから [クラウド書き出しアカウントの作成を開始](#begin-creating-a-cloud-export-account)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **アカウントのプロパティ**] の節 [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **プロジェクト ID**] | Google Cloud アカウントからコピーするGoogle Cloud プロジェクト ID。 [プロジェクト ID の取得に関する Google Cloud ドキュメント](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=ja#identifying_projects)を参照してください。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   この [!UICONTROL **書き出しアカウントが作成されました**] ダイアログが表示されます。

   ![書き出しアカウントが作成されましたダイアログ](assets/export-account-gcp.png)

1. の内容をコピーします [!UICONTROL **元本**] フィールドをクリップボードに追加し、このバケットにGoogle Cloud Platform でファイルをアップロードする権限をプリンシパルに付与していることを確認します。 <!-- add link to Google Cloud docs on how to do this -->

1. を選択 [!UICONTROL **OK**].

1. 続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. 次のいずれかの方法で、クラウド書き出しアカウントの作成を開始します。

   * 前述の「」の書き出しページから [クラウド書き出しアカウントの作成を開始](#begin-creating-a-cloud-export-account)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **アカウントのプロパティ**] の節 [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
   | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault 内の SAS URI へのパス。Azure SAS を設定するには、Azure Key Vault を使用して SAS URI を秘密鍵として保存する必要があります。詳しくは、[Azure Key Vault で秘密鍵を設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。</p><p>Key Vault URI の作成後：<ul><li>作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。</li><li>Key Vault URI にアクセスするには、アプリケーション ID に `Key Vault Certificate User` 組み込みの役割が付与されていることを確認してください。</br><p>詳しくは、[Azure の組み込みの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p></li></ul><p>詳しくは、[Key Vault アクセスポリシーの割り当て方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/general/assign-access-policy?tabs=azure-portal)を参照してください。</p> |
   | [!UICONTROL **Key Vault シークレット名**] | Azure Key Vault にシークレットを追加する際に作成したシークレット名。Microsoft Azure では、この情報は、作成した Key Vault の **Key Vault** 設定ページにあります。詳しくは、[Azure Key Vault からシークレットを設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。 |
   | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、 [Microsoft ID プラットフォームへのアプリケーションの登録方法に関するMicrosoft Azure のドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   この [!UICONTROL **書き出しアカウントが作成されました**] ダイアログが表示されます。

   ![書き出しアカウントが作成されましたダイアログ](assets/export-account-azure.png)

1. まだ付与していない場合は、Azure SAS のバケットに権限を付与していることを確認します。 <!-- add link to Google Cloud docs on how to do this -->

1. を選択 [!UICONTROL **OK**].

1. 続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. 次のいずれかの方法で、クラウド書き出しアカウントの作成を開始します。

   * 前述の「」の書き出しページから [クラウド書き出しアカウントの作成を開始](#begin-creating-a-cloud-export-account)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **アカウントのプロパティ**] の節 [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
   | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーション登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   この [!UICONTROL **書き出しアカウントが作成されました**] ダイアログが表示されます。

   ![書き出しアカウントが作成されましたダイアログ](assets/export-account-azure.png)

1. まだ付与していない場合は、Azure RBAC のバケットに権限を付与していることを確認します。 <!-- add link to Google Cloud docs on how to do this -->

1. を選択 [!UICONTROL **OK**].

1. 続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. 次のいずれかの方法で、クラウド書き出しアカウントの作成を開始します。

   * 前述の「」の書き出しページから [クラウド書き出しアカウントの作成を開始](#begin-creating-a-cloud-export-account)

   * 条件 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. が含まれる [!UICONTROL **アカウントのプロパティ**] の節 [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アカウント識別子**] | 社内だけでなく、Snowflakeがサポートするクラウドプラットフォームとクラウドリージョンのグローバルネットワーク全体で、Snowflakeアカウントを一意に特定します。 <p>Snowflakeアカウントからアカウント ID を取得し、ここにペーストする必要があります。</p><p>この情報の取得先については、を参照してください [Snowflakeドキュメントのアカウント識別子ページ](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **ユーザー**] | 接続に使用されるユーザーのログイン名。 特にAdobeに使用する新しいユーザーを作成することをお勧めします。 ここに名前を指定して、Snowflakeに同じ名前のユーザーを作成してください。 Snowflakeでユーザーを作成するには、 `CREATE USER` コマンド。  <p>詳しくは、 [ユーザー、役割、権限のコマンド](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **役割**] | ユーザーに割り当てられる役割。 特にAdobeに使用される新しいロールを作成することをお勧めします。 ここでロールを指定し、Snowflakeで同じ名前のロールを作成してロールを付与します。 Snowflakeでロールを作成するには、 `CREATE ROLE` コマンド。 <p>詳しくは、 [ユーザー、役割、権限のコマンド](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   この [!UICONTROL **書き出しアカウントが作成されました**] ダイアログが表示されます。

   ![書き出しアカウントが作成されましたダイアログ](assets/export-account-snowflake.png)

1. の内容をコピーします [!UICONTROL **公開鍵**] フィールドをクリップボードに追加します。 公開鍵はAdobeが指定します。

   Snowflakeの公開鍵を使用して、Snowflakeアカウントに接続します。 作成したユーザーをこの公開鍵に関連付ける必要があります。

   例えば、Snowflakeで、次のコマンドを指定します。

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   詳しくは、 [Snowflakeドキュメントのキーペア認証とキーペアローテーション ページ](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. を選択 [!UICONTROL **OK**].

1. 続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).
