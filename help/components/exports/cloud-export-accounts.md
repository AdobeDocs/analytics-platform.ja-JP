---
description: Customer Journey Analyticsデータの送信先となるクラウドエクスポートアカウントを設定する
keywords: Analysis Workspace
title: クラウドエクスポートアカウントの設定
feature: Components
hide: true
hidefromtoc: true
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
source-git-commit: b0ddfbb4d018e6d563bef639a31f31e09700fbc2
workflow-type: tm+mt
source-wordcount: '1543'
ht-degree: 5%

---

# クラウドエクスポートアカウントの設定

Customer Journey Analyticsレポートをクラウドの宛先に書き出す前に、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md)に値を入力する場合は、データの送信先を追加して設定する必要があります。

このプロセスは、この記事で説明するアカウント (Amazon S3、Google Cloud Platform など ) の追加と設定の後、アカウント内の場所（アカウント内のフォルダーなど）の追加と設定で構成されます。詳しくは、 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

アカウントの表示、編集、削除など、既存のアカウントの管理方法について詳しくは、 [クラウドの書き出し場所とアカウントを管理](/help/components/exports/manage-export-locations.md).

## クラウドエクスポートアカウントの作成を開始します

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].
1. 次の日： [!UICONTROL エクスポート] ページで、 [!UICONTROL **場所のアカウント**] タブをクリックします。
1. 選択 [!UICONTROL **アカウントを追加**].

   ![アカウントを追加](assets/account-add.png)

   アカウントを追加ダイアログが表示されます。

1. Adobe Analytics の [!UICONTROL **場所のアカウント名**] 「 」フィールドで、場所アカウントの名前を指定します。 この名前は、ロケーションを作成する際に表示されます。

1. Adobe Analytics の [!UICONTROL **場所アカウントの説明**] 「 」フィールドに、同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。

1. Adobe Analytics の [!UICONTROL **アカウントタイプ**] 「 」フィールドで、エクスポート先のクラウドアカウントのタイプを選択します。 使用可能なアカウントの種類は、Amazon S3 ロール ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake、AEP データランディングゾーンです。

1. に対応する以下のセクションに進みます。 [!UICONTROL **アカウントタイプ**] を選択しました。

   * [Adobe Experience Platform Data Landing Zone](#adobe-experience-platform)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### AEP データランディングゾーン

>[!IMPORTANT]
>
>Customer Journey AnalyticsレポートをAdobe Experience Platform Data Landing Zone に書き出す場合は、7 日以内にデータをダウンロードしてから、AEP Data Landing Zone から削除してください。 7 日後に、データは AEP データランディングゾーンから自動的に削除されます。

1. [クラウドエクスポートアカウントの作成を開始します](#begin-creating-a-cloud-export-account)（前述のように）

1. 「[!UICONTROL **保存**]」を選択します。

   The [!UICONTROL **作成されたエクスポートアカウント**] ダイアログが表示されます。

   <!-- add screen shot -->

1. の内容をコピーします。 [!UICONTROL **SAS**] フィールドをクリップボードに追加します。 この SAS トークンを使用して、AEP ランディングゾーンからAnalysis Workspaceから書き出されたデータにアクセスします。

1. 選択 [!UICONTROL **OK**].

1. 次で続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. [クラウドエクスポートアカウントの作成を開始します](#begin-creating-a-cloud-export-account)（前述のように）

1. Adobe Analytics の [!UICONTROL **アカウントのプロパティ**] のセクション [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **役割 ARN**] | AdobeがAmazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN(Amazon Resource Name) を指定する必要があります。 これを行うには、ソースアカウントの IAM アクセス許可ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントのロールを作成します。 詳しくは、 [このAWSドキュメント](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   The [!UICONTROL **作成されたエクスポートアカウント**] ダイアログが表示されます。

   <!-- add screen shot -->

1. の内容をコピーします。 [!UICONTROL **ユーザー ARN**] フィールドをクリップボードに追加します。 ユーザー ARN(Amazon Resource Name) は、Adobeが提供します。 このユーザーは、Amazon S3 の役割 ARN で作成したポリシーに関連付ける必要があります。

1. 選択 [!UICONTROL **OK**].

1. 次で続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. [クラウドエクスポートアカウントの作成を開始します](#begin-creating-a-cloud-export-account)（前述のように）

1. Adobe Analytics の [!UICONTROL **アカウントのプロパティ**] のセクション [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **プロジェクト ID**] | Google Cloud アカウントからコピーするGoogle Cloud プロジェクト ID です。 詳しくは、 [プロジェクト ID の取得に関するGoogle Cloud ドキュメント](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   The [!UICONTROL **作成されたエクスポートアカウント**] ダイアログが表示されます。

   <!-- add screen shot -->

1. の内容をコピーします。 [!UICONTROL **プリンシパル**] フィールドをクリップボードに追加して、Google Cloud Platform のこのバケットにファイルをアップロードする権限をプリンシパルに付与していることを確認します。 <!-- add link to Google Cloud docs on how to do this -->

1. 選択 [!UICONTROL **OK**].

1. 次で続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. [クラウドエクスポートアカウントの作成を開始します](#begin-creating-a-cloud-export-account)（前述のように）

1. Adobe Analytics の [!UICONTROL **アカウントのプロパティ**] のセクション [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault の SAS トークンへのパス。  Azure SAS を構成するには、Azure Key Vault を使用して SAS トークンを秘密鍵として保存する必要があります。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>キー Vault URI を作成したら、作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。 詳しくは、 [Key Vault アクセスポリシーの割り当て方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Key Vault シークレットの名前**] | Azure Key Vault に秘密鍵を追加する際に作成した秘密鍵の名前。 Microsoft Azure では、この情報は、次の場所で作成した Key Vault 内の **Key Vault** 設定ページ。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **場所アカウントの秘密鍵**] <!-- nothing for us to have them do on the second screen. Just need to permission the container if they haven't --> | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   The [!UICONTROL **作成されたエクスポートアカウント**] ダイアログが表示されます。

   <!-- add screen shot -->

1. まだの場合、Azure SAS のバケットに対する権限を付与していることを確認してください。 <!-- add link to Google Cloud docs on how to do this -->

1. 選択 [!UICONTROL **OK**].

1. 次で続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. [クラウドエクスポートアカウントの作成を開始します](#begin-creating-a-cloud-export-account)（前述のように）

1. Adobe Analytics の [!UICONTROL **アカウントのプロパティ**] のセクション [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   The [!UICONTROL **作成されたエクスポートアカウント**] ダイアログが表示されます。

   <!-- add screen shot -->

1. まだの場合、Azure RBAC でバケットに対する権限を付与していることを確認してください。 <!-- add link to Google Cloud docs on how to do this -->

1. 選択 [!UICONTROL **OK**].

1. 次で続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. [クラウドエクスポートアカウントの作成を開始します](#begin-creating-a-cloud-export-account)（前述のように）

1. Adobe Analytics の [!UICONTROL **アカウントのプロパティ**] のセクション [!UICONTROL **アカウントを追加**] ダイアログボックスで、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アカウント識別子**] | 組織内のSnowflakeアカウント、およびSnowflakeがサポートするクラウドプラットフォームとクラウド地域のグローバルネットワーク全体を通じて一意に識別します。 <p>ご使用のアカウントのアカウント ID を取得し、Snowflakeをここに貼り付ける必要があります。</p><p>この情報の入手方法については、 [アカウント識別子ページ (Snowflakeドキュメント )](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **ユーザー**] | 接続に使用するユーザーのログイン名。 特にAdobe用に使用する新しいユーザーを作成することをお勧めします。 ここで名前を指定し、Snowflake内に同じ名前のユーザーを作成します。 ユーザーをSnowflakeで作成するには、 `CREATE USER` コマンドを使用します。  <p>詳しくは、 [ユーザー、役割、権限に関するコマンド](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **役割**] | ユーザーに割り当てられる役割。 特にAdobe用に使用する新しい役割を作成することをお勧めします。 ここで役割を指定し、同じ名前のSnowflakeで役割を作成し、その役割をユーザーに付与します。 を使用して、Snowflake内にロールを作成できます。 `CREATE ROLE` コマンドを使用します。 <p>詳しくは、 [ユーザー、役割、権限に関するコマンド](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   The [!UICONTROL **作成されたエクスポートアカウント**] ダイアログが表示されます。

   <!-- add screen shot -->

1. の内容をコピーします。 [!UICONTROL **公開鍵**] フィールドをクリップボードに追加します。 公開鍵はAdobeが提供します。

   公開鍵をSnowflakeで使用して、Snowflakeアカウントに接続します。 作成したユーザーをこの公開鍵に関連付ける必要があります。

   例えば、「Snowflake」で、次のコマンドを指定します。

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   詳しくは、 [キーペア認証とキーペアのローテーションページ (Snowflakeドキュメント内 )](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. 選択 [!UICONTROL **OK**].

1. 次で続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).
