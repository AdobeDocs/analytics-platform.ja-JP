---
description: Customer Journey Analyticsデータの送信先となるクラウドエクスポートアカウントを設定する
keywords: Analysis Workspace
title: クラウドエクスポートアカウントの設定
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 5%

---

# クラウドエクスポートアカウントの設定

{{select-package}}

クラウドの宛先にCustomer Journey Analyticsデータを書き出す前に、 [Customer Journey Analyticsデータをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)に値を入力する場合は、データを送信する場所を追加して設定する必要があります。

このプロセスは、この記事で説明するアカウント (Amazon S3、Google Cloud Platform など ) の追加と設定の後、アカウント内の場所（アカウント内のフォルダーなど）の追加と設定で構成されます。詳しくは、 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

アカウントの表示、編集、削除など、既存のアカウントの管理方法について詳しくは、 [クラウドの書き出し場所とアカウントを管理](/help/components/exports/manage-export-locations.md).

クラウドの宛先アカウントにアクセスするために必要な情報をCustomer Journey Analyticsに設定する必要があります。

クラウドエクスポートアカウントを設定するには：

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].
1. 次の日： [!UICONTROL エクスポート] ページで、 [!UICONTROL **場所のアカウント**] タブをクリックします。
1. 選択 [!UICONTROL **アカウントを追加**].

   ![アカウントを追加](assets/account-add.png)

   アカウントを追加ダイアログが表示されます。
1. 次の情報を指定します。 |フィールド |関数 | |—|—| | [!UICONTROL **場所のアカウント名**] |ロケーションアカウントの名前。 この名前は、ロケーションを作成する際に表示されます | | [!UICONTROL **場所アカウントの説明**] |同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 | | [!UICONTROL **アカウントタイプ**] |書き出し先のクラウドアカウントのタイプを選択します。 使用可能なアカウントのタイプは、Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake、Adobe Experience Platformです。 |
1. Adobe Analytics の [!UICONTROL **アカウントのプロパティ**] 「 」セクションで、選択したアカウントタイプに固有の情報を指定します。

   設定手順については、 [!UICONTROL **アカウントタイプ**] を選択します。

   +++Amazon S3 Role ARN

   Amazon S3 Role ARN アカウントを設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **役割 ARN**] | AdobeがAmazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN(Amazon Resource Name) を指定する必要があります。 これを行うには、ソースアカウントの IAM アクセス許可ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントのロールを作成します。 詳しくは、 [このAWSドキュメント](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **ユーザーARN**] | ユーザー ARN(Amazon Resource Name) は、Adobeが提供します。 作成したポリシーにこのユーザーを添付する必要があります。 |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Google Cloud Platform アカウントを設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **プロジェクト ID**] | Google Cloud アカウントからコピーするGoogle Cloud プロジェクト ID です。 詳しくは、 [プロジェクト ID の取得に関するGoogle Cloud ドキュメント](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **プリンシパル**] | プリンシパルはAdobeで提供されます。 次をクリック： [!UICONTROL **コピー**] 横のアイコン [!UICONTROL **プリンシパル**] 「 」フィールドを使用してフィールドの内容をコピーし、Google Cloud Platform のこのバケットにファイルをアップロードする権限をプリンシパルに付与する必要があります。 <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Azure SAS アカウントを構成するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault の SAS トークンへのパス。  Azure SAS を構成するには、Azure Key Vault を使用して SAS トークンを秘密鍵として保存する必要があります。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>キー Vault URI を作成したら、作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。 詳しくは、 [Key Vault アクセスポリシーの割り当て方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Key Vault シークレットの名前**] | Azure Key Vault に秘密鍵を追加する際に作成した秘密鍵の名前。 Microsoft Azure では、この情報は、次の場所で作成した Key Vault 内の **Key Vault** 設定ページ。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Azure RBAC アカウントを設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   次の情報を指定して、Snowflakeアカウントを設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アカウント識別子**] | 組織内のSnowflakeアカウント、およびSnowflakeがサポートするクラウドプラットフォームとクラウド地域のグローバルネットワーク全体を通じて一意に識別します。 <p>詳しくは、 [アカウント識別子ページ (Snowflakeドキュメント )](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **ユーザー**] | 接続に使用するユーザーのログイン名を指定します。 これは、特にAdobeに使用されるユーザーです。 ここでユーザー名を指定した後、Snowflakeでユーザーを作成できます。 <p>詳しくは、 [「JDBC Driver Connection Parameter Reference」ページ (Snowflake・ドキュメント内 )](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **役割**] | ドライバが開始したSnowflakeセッションで使用する既定のアクセス制御の役割です。 読み取りおよび書き込みアクセス権を持つAdobe専用のロールを作成する必要があります。<p>詳しくは、 [「JDBC Driver Connection Parameter Reference」ページ (Snowflake・ドキュメント内 )](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **公開鍵**] | 公開鍵はAdobeが提供します。 の横にあるコピーアイコンを選択します。 [!UICONTROL **公開鍵**] 「 」フィールドを使用してフィールドの内容をコピーし、Snowflakeアカウントで公開鍵を使用します。 詳しくは、 [キーペア認証とキーペアのローテーションページ (Snowflakeドキュメント内 )](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   すべてのAdobe Experience Platformのお客様は、AEP ランディングゾーンにデータを書き出すことができます。

   Adobe Experience Platformアカウントを設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **IMS 組織 ID**] | IMS Org ID は、Adobeが提供します。 の横にあるコピーアイコンをクリックします。 [!UICONTROL **IMS Org ID**] フィールドを使用してフィールドの内容をコピーし、Experience Platform アカウントで ID をAdobeします。 |

+++

1. 「[!UICONTROL **保存**]」を選択します。

1. 次で続行 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

