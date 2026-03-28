---
description: Customer Journey Analytics データを送信できるクラウド書き出し場所の設定
keywords: Analysis Workspace
title: クラウドの書き出し場所の設定
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '3136'
ht-degree: 20%

---

# クラウドの書き出し場所の設定 {#configure-cloud-export-locations}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-prefix"
>title="接頭辞"
>abstract="データを配置するコンテナ内のルートフォルダー。静的なフォルダー名を指定してから、名前の後にスラッシュを追加してフォルダーを作成します。例：`folder_name/`"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-name"
>title="ファイル名とパス"
>abstract="この場所に送信される自動書き出しに使用する動的なカスタムファイル名を指定します。 ファイル名の前に動的なカスタムファイルパスを付けることもできます。<br/> ファイル名とパスで変数を使用して、動的にします。 <br/>例えば、`${yyyy}/${MM}/${dd}/my-report-${instance_id}-${idx}`を指定した場合、2026年1月15日にこの宛先に自動的に送信される書き出しには、次のファイルパスと名前が含まれます。`[prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv` <br/>使用可能な変数のリストについては、以下のリンクをクリックしてください。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics レポートをクラウドの宛先（[Analysis Workspace](/help/analysis-workspace/export/export-cloud.md)または[Report Builder](/help/report-builder/report-builder-export.md)から）に書き出す前に、データを送信する場所を追加して設定する必要があります。 このプロセスは次の要素で構成されます。

1. [&#x200B; クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md)の説明に従って、アカウント（Amazon S3、Google Cloud Platformなど）を追加および設定する

1. この記事で説明されているように、そのアカウント内の場所（アカウント内のフォルダーなど）を追加および設定します。

場所の表示、編集、削除など、既存の場所を管理する方法について詳しくは、[&#x200B; クラウド書き出し場所とアカウントの管理](/help/components/exports/manage-export-locations.md)を参照してください。

## クラウド書き出し場所の作成を開始

1. 場所を追加する前に、アカウントを追加する必要があります。 まだアカウントを追加していない場合は、[&#x200B; クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)の説明に従ってアカウントを追加します。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **場所**]」タブを選択し、「[!UICONTROL **場所を追加**]」を選択します。

   ![場所を追加ボタンを強調表示する「場所」タブが選択された状態でウィンドウを書き出す](assets/location-add.png)

   または

   「[!UICONTROL **場所アカウント**]」タブを選択し、場所を追加する既存のアカウントの3点アイコンを選択してから、[!UICONTROL **場所を追加**]&#x200B;を選択します。

   ![GCP アカウントと省略記号ドロップダウンメニューに「場所を追加」が選択されている](assets/add-location-existing-account.png)

   場所ダイアログが表示されます。

1. 次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **名前**] | 場所の名前。 |
   | [!UICONTROL **説明**] | アカウント上の他の場所と区別するために、場所の簡単な説明を提供します。 |
   | [!UICONTROL **組織内のすべてのユーザーが場所を利用できるようにします**] | このオプションを有効にすると、組織内の他のユーザーがこの場所を使用できるようになります。 <p>場所を共有する場合は、次の点を考慮してください。</p><ul><li>共有している場所は共有を解除できません。</li><li>共有場所は、場所の所有者のみが編集できます。</li><li>場所を共有できるのは、場所が関連付けられているアカウントも共有されている場合のみです。</li></ul> |
   | [!UICONTROL **場所アカウント**] | 場所を作成するアカウントを選択します。 アカウントの作成方法について詳しくは、[&#x200B; クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)を参照してください。 |

1. Adobe Analytics の「[!UICONTROL **場所のプロパティ**]」セクションで、場所アカウントのアカウントタイプに固有の情報を指定します。

   [!UICONTROL **場所アカウント**] フィールドで選択したアカウントタイプに対応する以下のセクションに進みます。

   * [AEP データランディングゾーン](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP データランディングゾーン

>[!IMPORTANT]
>
>Customer Journey Analytics レポートをAdobe Experience Platform Data Landing Zoneに書き出す場合は、7日以内にデータをダウンロードしてから、AEP Data Landing Zoneから削除してください。 7日後、データはAEP Data Landing Zoneから自動的に削除されます。

1. 次のいずれかの方法で、クラウド書き出し場所の作成を開始します。

   * 上記の書き出しページから、[&#x200B; クラウド書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)します

   * Analysis Workspace[から完全なテーブルを](/help/analysis-workspace/export/export-cloud.md#export-full-tables)書き出す場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの&#x200B;[!UICONTROL **場所プロパティ**] セクションで、次の情報を指定してAdobe Experience Platform データランディングゾーンの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **接頭辞**] | データを配置するコンテナ内のフォルダー。静的なフォルダー名を指定してから、名前の後にスラッシュを追加してフォルダーを作成します。例：`folder_name/` |
   | [!UICONTROL **ファイル名とパス**] | この場所に送信される自動書き出しに使用する動的なカスタムファイル名を指定します。 ファイル名の前に動的カスタムファイルパスを付けることもできます。 <p>このオプションを使用すると、ファイル名の作成とフォルダーの配置を自動化できるため、ファイル名は予測可能であり、フォルダーに論理的に整理されます。 例えば、ファイル名は配達日に応じて名前を付け、各月に対応するフォルダーに配置することができます。</p><p>ファイル名とパスで次のいずれかの変数を使用して、動的にします。</p><ul><li>**{yyyy}**: 4桁の暦年（大文字と小文字を区別）</li><li>**{yy}**: 2桁の暦年（大文字と小文字を区別）</li><li>**{MM}**: 2桁の月（大文字と小文字を区別）</li><li>**{dd}**: 2桁の日（大文字と小文字を区別）</li><li>**{HH}**: 2桁の時間（大文字と小文字を区別）</li><li>**{mm}**: 2桁の分（大文字と小文字を区別）</li><li>**{ss}**: 2桁の秒（大文字と小文字を区別）</li><li>**{fff}**: 3桁のナノ秒（大文字と小文字を区別）</li><li>**{instance_id}**: リクエスト （インスタンス） UUID</li><li>**{export_id}**：書き出し（スケジュール） UUID</li><li>**{idx}**: インデックスは0から始まります（各ファイルごとに増分）</li><li>**{total}**：転送ジョブ全体の合計ファイル番号</li><li>**{completion_millis}**：転送時間（ミリ秒単位）</li></ul></p><p>例えば、`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`を指定した場合、2026年1月15日にこの宛先に自動的に送信される書き出しには、次のファイルパスと名前が含まれます。[prefix_folder_name]/2026/01/15/my-report-[UID]-1.csv</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから、設定したアカウントと場所にデータを書き出せるようになりました。 データをクラウドにエクスポートする方法について詳しくは、[&#x200B; プロジェクトデータをクラウドにエクスポート &#x200B;](/help/analysis-workspace/export/export-cloud.md)を参照してください。

1. AEP Data Landing Zoneのデータにアクセスする最も簡単な方法は、Microsoft Azure Storage Explorerを使用することです。 Storage Explorerは、[AEP Data Landing Zone アカウント &#x200B;](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)の設定手順で使用されるものと同じツールです。

   1. [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/)を開きます。

   1. [!UICONTROL **ストレージアカウント**] > [!UICONTROL **（添付コンテナ）**] > [!UICONTROL **Blob Containers**] > **[!UICONTROL cjaexport-_number_]**>*** your_container_name &#x200B;***に移動します。

      >[!NOTE]
      >
      >フォルダー名&#x200B;**[!UICONTROL cjaexport-_number_]**&#x200B;は、Azure Storage Explorerが提供するデフォルトの名前です。 SAS URIに関連付けられた接続が1つしかない場合（通常の場合）、このフォルダーの名前は&#x200B;**[!UICONTROL cjaexport-1]**&#x200B;になります。


      ![Azure ストレージエクスプローラーのファイルにアクセス &#x200B;](assets/azure-storage-explorer-access.png)

   1. ダウンロードする書き出しを選択し、[!UICONTROL **ダウンロード**]&#x200B;を選択してダウンロードします。

### Amazon S3 Role ARN

1. 次のいずれかの方法で、クラウド書き出し場所の作成を開始します。

   * 上記の書き出しページから、[&#x200B; クラウド書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)します

   * Analysis Workspace[から完全なテーブルを](/help/analysis-workspace/export/export-cloud.md#export-full-tables)書き出す場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの&#x200B;[!UICONTROL **場所プロパティ**] セクションで、次の情報を指定してAmazon S3 ロール ARNの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Customer Journey Analytics データを送信するAmazon S3 アカウント内のバケット。 <p>このバケットにファイルをアップロードするには、Adobeから提供されたユーザーARNに`S3:PutObject`権限があることを確認してください。 </p><p>バケット名は、特定の命名規則を満たす必要があります。例えば、3〜63 文字までの長さで、小文字、数字、ドット（.）、ハイフン（-）のみで構成でき、先頭と末尾は文字または数字にする必要があります。[命名規則の完全なリストについては、AWSのドキュメント &#x200B;](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/userguide/bucketnamingrules.html)を参照してください。 </p> |
   | [!UICONTROL **接頭辞**] | データを配置するバケット内のフォルダー。静的なフォルダー名を指定してから、名前の後にスラッシュを追加してフォルダーを作成します。例：folder_name/ |
   | [!UICONTROL **ファイル名とパス**] | この場所に送信される自動書き出しに使用する動的なカスタムファイル名を指定します。 ファイル名の前に動的カスタムファイルパスを付けることもできます。 <p>このオプションを使用すると、ファイル名の作成とフォルダーの配置を自動化できるため、ファイル名は予測可能であり、フォルダーに論理的に整理されます。 例えば、ファイル名は配達日に応じて名前を付け、各月に対応するフォルダーに配置することができます。</p><p>ファイル名とパスで次のいずれかの変数を使用して、動的にします。</p><ul><li>**{yyyy}**: 4桁の暦年（大文字と小文字を区別）</li><li>**{yy}**: 2桁の暦年（大文字と小文字を区別）</li><li>**{MM}**: 2桁の月（大文字と小文字を区別）</li><li>**{dd}**: 2桁の日（大文字と小文字を区別）</li><li>**{HH}**: 2桁の時間（大文字と小文字を区別）</li><li>**{mm}**: 2桁の分（大文字と小文字を区別）</li><li>**{ss}**: 2桁の秒（大文字と小文字を区別）</li><li>**{fff}**: 3桁のナノ秒（大文字と小文字を区別）</li><li>**{instance_id}**: リクエスト （インスタンス） UUID</li><li>**{export_id}**：書き出し（スケジュール） UUID</li><li>**{idx}**: インデックスは0から始まります（各ファイルごとに増分）</li><li>**{total}**：転送ジョブ全体の合計ファイル番号</li><li>**{completion_millis}**：転送時間（ミリ秒単位）</li></ul></p><p>例えば、`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`を指定した場合、2026年1月15日にこの宛先に自動的に送信される書き出しには、次のファイルパスと名前が含まれます。[prefix_folder_name]/2026/01/15/my-report-[UID]-1.csv</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから、設定したアカウントと場所にデータを書き出せるようになりました。 データをクラウドにエクスポートする方法について詳しくは、[&#x200B; プロジェクトデータをクラウドにエクスポート &#x200B;](/help/analysis-workspace/export/export-cloud.md)を参照してください。

### Google Cloud Platform

1. 次のいずれかの方法で、クラウド書き出し場所の作成を開始します。

   * 上記の書き出しページから、[&#x200B; クラウド書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)します

   * Analysis Workspace[から完全なテーブルを](/help/analysis-workspace/export/export-cloud.md#export-full-tables)書き出す場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの&#x200B;[!UICONTROL **場所プロパティ**] セクションで、次の情報を指定してGoogle Cloud Platformの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Customer Journey Analytics データを送信するGCP アカウント内のバケット。 <p>Adobeが提供するプリンシパルに`roles/storage.objectCreator`権限を付与していることを確認してください。 （プリンシパルは、[Google Cloud Platform アカウントの設定時](/help/components/exports/cloud-export-accounts.md)に提供されます）。 <p>権限の付与について詳しくは、Google Cloud ドキュメントの[バケットレベルのポリシーにプリンシパルを追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=ja#bucket-add)を参照してください。</p><p>組織が[組織ポリシーの制約](https://cloud.google.com/storage/docs/org-policy-constraints)を使用して許可リスト内の Google Cloud Platform アカウントのみを許可している場合は、次のアドビ所有の Google Cloud Platform 組織 ID が必要です。 <ul><li>`DISPLAY_NAME`：`adobe.com`</li><li>`ID`：`178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`：`C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **接頭辞**] | データを配置するバケット内のフォルダー。静的なフォルダー名を指定してから、名前の後にスラッシュを追加してフォルダーを作成します。例：folder_name/ |
   | [!UICONTROL **ファイル名とパス**] | この場所に送信される自動書き出しに使用する動的なカスタムファイル名を指定します。 ファイル名の前に動的カスタムファイルパスを付けることもできます。 <p>このオプションを使用すると、ファイル名の作成とフォルダーの配置を自動化できるため、ファイル名は予測可能であり、フォルダーに論理的に整理されます。 例えば、ファイル名は配達日に応じて名前を付け、各月に対応するフォルダーに配置することができます。</p><p>ファイル名とパスで次のいずれかの変数を使用して、動的にします。</p><ul><li>**{yyyy}**: 4桁の暦年（大文字と小文字を区別）</li><li>**{yy}**: 2桁の暦年（大文字と小文字を区別）</li><li>**{MM}**: 2桁の月（大文字と小文字を区別）</li><li>**{dd}**: 2桁の日（大文字と小文字を区別）</li><li>**{HH}**: 2桁の時間（大文字と小文字を区別）</li><li>**{mm}**: 2桁の分（大文字と小文字を区別）</li><li>**{ss}**: 2桁の秒（大文字と小文字を区別）</li><li>**{fff}**: 3桁のナノ秒（大文字と小文字を区別）</li><li>**{instance_id}**: リクエスト （インスタンス） UUID</li><li>**{export_id}**：書き出し（スケジュール） UUID</li><li>**{idx}**: インデックスは0から始まります（各ファイルごとに増分）</li><li>**{total}**：転送ジョブ全体の合計ファイル番号</li><li>**{completion_millis}**：転送時間（ミリ秒単位）</li></ul></p><p>例えば、`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`を指定した場合、2026年1月15日にこの宛先に自動的に送信される書き出しには、次のファイルパスと名前が含まれます。[prefix_folder_name]/2026/01/15/my-report-[UID]-1.csv</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから、設定したアカウントと場所にデータを書き出せるようになりました。 データをクラウドにエクスポートする方法について詳しくは、[&#x200B; プロジェクトデータをクラウドにエクスポート &#x200B;](/help/analysis-workspace/export/export-cloud.md)を参照してください。

### Azure SAS

1. 次のいずれかの方法で、クラウド書き出し場所の作成を開始します。

   * 上記の書き出しページから、[&#x200B; クラウド書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)します

   * Analysis Workspace[から完全なテーブルを](/help/analysis-workspace/export/export-cloud.md#export-full-tables)書き出す場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの&#x200B;[!UICONTROL **場所プロパティ**] セクションで、次の情報を指定してAzure SASの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ名**] | Customer Journey Analytics データを送信する場所を指定したアカウント内のコンテナ。 |
   | [!UICONTROL **接頭辞**] | データを配置するコンテナ内のフォルダー。静的なフォルダー名を指定してから、名前の後にスラッシュを追加してフォルダーを作成します。例：`folder_name/`<p>Azure SAS アカウントを設定する際に、Key Vault 秘密鍵名フィールドに指定した SAS トークンストアに `Write` 権限があることを確認します。これにより、SAS トークンで Azure コンテナにファイルを作成できます。 <p>SAS トークンでファイルも上書きする場合は、SAS トークンストアに `Delete` 権限があることを確認します。</p><p>詳しくは、Azure Blob Storage ドキュメントの [Blob Storage のリソース](https://learn.microsoft.com/ja-jp/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)を参照してください。</p> |
   | [!UICONTROL **ファイル名とパス**] | この場所に送信される自動書き出しに使用する動的なカスタムファイル名を指定します。 ファイル名の前に動的カスタムファイルパスを付けることもできます。 <p>このオプションを使用すると、ファイル名の作成とフォルダーの配置を自動化できるため、ファイル名は予測可能であり、フォルダーに論理的に整理されます。 例えば、ファイル名は配達日に応じて名前を付け、各月に対応するフォルダーに配置することができます。</p><p>ファイル名とパスで次のいずれかの変数を使用して、動的にします。</p><ul><li>**{yyyy}**: 4桁の暦年（大文字と小文字を区別）</li><li>**{yy}**: 2桁の暦年（大文字と小文字を区別）</li><li>**{MM}**: 2桁の月（大文字と小文字を区別）</li><li>**{dd}**: 2桁の日（大文字と小文字を区別）</li><li>**{HH}**: 2桁の時間（大文字と小文字を区別）</li><li>**{mm}**: 2桁の分（大文字と小文字を区別）</li><li>**{ss}**: 2桁の秒（大文字と小文字を区別）</li><li>**{fff}**: 3桁のナノ秒（大文字と小文字を区別）</li><li>**{instance_id}**: リクエスト （インスタンス） UUID</li><li>**{export_id}**：書き出し（スケジュール） UUID</li><li>**{idx}**: インデックスは0から始まります（各ファイルごとに増分）</li><li>**{total}**：転送ジョブ全体の合計ファイル番号</li><li>**{completion_millis}**：転送時間（ミリ秒単位）</li></ul></p><p>例えば、`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`を指定した場合、2026年1月15日にこの宛先に自動的に送信される書き出しには、次のファイルパスと名前が含まれます。[prefix_folder_name]/2026/01/15/my-report-[UID]-1.csv</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから、設定したアカウントと場所にデータを書き出せるようになりました。 データをクラウドにエクスポートする方法について詳しくは、[&#x200B; プロジェクトデータをクラウドにエクスポート &#x200B;](/help/analysis-workspace/export/export-cloud.md)を参照してください。

### Azure RBAC

1. 次のいずれかの方法で、クラウド書き出し場所の作成を開始します。

   * 上記の書き出しページから、[&#x200B; クラウド書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)します

   * Analysis Workspace[から完全なテーブルを](/help/analysis-workspace/export/export-cloud.md#export-full-tables)書き出す場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの&#x200B;[!UICONTROL **場所プロパティ**] セクションで、次の情報を指定してAzure RBACの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ**] | Customer Journey Analytics データを送信する場所を指定したアカウント内のコンテナ。 以前に作成した Azure アプリケーションにファイルをアップロードする権限を付与します。 |
   | [!UICONTROL **接頭辞**] | データを配置するコンテナ内のフォルダー。静的なフォルダー名を指定してから、名前の後にスラッシュを追加してフォルダーを作成します。例：`folder_name/`<p>Azure RBAC アカウントの設定時に指定したアプリケーション ID に、コンテナ（フォルダー）にアクセスするための `Storage Blob Data Contributor` の役割が付与されていることを確認します。</p> <p>詳しくは、[Azure のビルトインの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p> |
   | [!UICONTROL **ファイル名とパス**] | この場所に送信される自動書き出しに使用する動的なカスタムファイル名を指定します。 ファイル名の前に動的カスタムファイルパスを付けることもできます。 <p>このオプションを使用すると、ファイル名の作成とフォルダーの配置を自動化できるため、ファイル名は予測可能であり、フォルダーに論理的に整理されます。 例えば、ファイル名は配達日に応じて名前を付け、各月に対応するフォルダーに配置することができます。</p> <p>ファイル名とパスで次のいずれかの変数を使用して、動的にします。</p><ul><li>**{yyyy}**: 4桁の暦年（大文字と小文字を区別）</li><li>**{yy}**: 2桁の暦年（大文字と小文字を区別）</li><li>**{MM}**: 2桁の月（大文字と小文字を区別）</li><li>**{dd}**: 2桁の日（大文字と小文字を区別）</li><li>**{HH}**: 2桁の時間（大文字と小文字を区別）</li><li>**{mm}**: 2桁の分（大文字と小文字を区別）</li><li>**{ss}**: 2桁の秒（大文字と小文字を区別）</li><li>**{fff}**: 3桁のナノ秒（大文字と小文字を区別）</li><li>**{instance_id}**: リクエスト （インスタンス） UUID</li><li>**{export_id}**：書き出し（スケジュール） UUID</li><li>**{idx}**: インデックスは0から始まります（各ファイルごとに増分）</li><li>**{total}**：転送ジョブ全体の合計ファイル番号</li><li>**{completion_millis}**：転送時間（ミリ秒単位）</li></ul></p><p>例えば、`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`を指定した場合、2026年1月15日にこの宛先に自動的に送信される書き出しには、次のファイルパスと名前が含まれます。[prefix_folder_name]/2026/01/15/my-report-[UID]-1.csv</p> |
   | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから、設定したアカウントと場所にデータを書き出せるようになりました。 データをクラウドにエクスポートする方法について詳しくは、[&#x200B; プロジェクトデータをクラウドにエクスポート &#x200B;](/help/analysis-workspace/export/export-cloud.md)を参照してください。

### Snowflake

1. 次のいずれかの方法で、クラウド書き出し場所の作成を開始します。

   * 上記の書き出しページから、[&#x200B; クラウド書き出し場所の作成を開始](#begin-creating-a-cloud-export-location)します

   * Analysis Workspace[から完全なテーブルを](/help/analysis-workspace/export/export-cloud.md#export-full-tables)書き出す場合

1. [!UICONTROL **場所を追加**] ダイアログボックスの&#x200B;[!UICONTROL **場所プロパティ**] セクションで、次の情報を指定してSnowflakeの場所を設定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **DB**] | 指定されたデータベースは、既存のデータベースである必要があります。 作成した役割には、このデータベースにアクセスするための権限が必要です。<p>これは、ステージ名に関連付けられたデータベースです。</p><p>次のコマンドを使用して、Snowflakeのデータベースにこのロール権限を付与できます：`GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>詳しくは、Snowflake ドキュメント [の「](https://docs.snowflake.com/en/sql-reference/commands-database)Database, Schema, and Share Commands」ページを参照してください。</p> |
   | [!UICONTROL **スキーマ**] | 指定されたスキーマは既存のスキーマである必要があります。 作成した役割には、このスキーマにアクセスするための権限が必要です。<p>これは、ステージ名に関連付けられたスキーマです。</p><p>次のコマンドを使用して、Snowflakeのスキーマに権限を作成したロールを付与できます：`GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>詳しくは、Snowflake ドキュメント [の「](https://docs.snowflake.com/en/sql-reference/commands-database)Database, Schema, and Share Commands」ページを参照してください。</p> |
   | [!UICONTROL **ステージ名**] | データファイルがSnowflakeに保存される内部ステージの名前。<p>アカウントで指定した役割に、このステージ名への読み取りおよび書き込みアクセス権があることを確認します。 （読み取りと書き込みのアクセス権を付与しているので、Adobeでのみ使用されるステージを使用することをお勧めします）。</p><p>次のコマンドを使用して、Snowflakeのステージ名に読み取りアクセス権と書き込みアクセス権を付与できます：`GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>ロールに権限を付与する方法について詳しくは、[Snowflake ドキュメントの権限の付与](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege)を参照してください。</p> <p>ステージ名について詳しくは、Snowflake ドキュメント [の「](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage) ローカルファイルの内部ステージの選択」ページを参照してください。</p> |
   | [!UICONTROL **ステージパス**] | Snowflakeに保存されているデータファイルの場所へのパス。 <p>詳しくは、Snowflake ドキュメント [の「](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage) ローカルファイルの内部ステージの選択」ページを参照してください。</p> |
   | [!UICONTROL **ファイル名とパス**] | この場所に送信される自動書き出しに使用する動的なカスタムファイル名を指定します。 ファイル名の前に動的カスタムファイルパスを付けることもできます。 <p>このオプションを使用すると、ファイル名の作成とフォルダーの配置を自動化できるため、ファイル名は予測可能であり、フォルダーに論理的に整理されます。 例えば、ファイル名は配達日に応じて名前を付け、各月に対応するフォルダーに配置することができます。</p><p>ファイル名とパスで次のいずれかの変数を使用して、動的にします。</p><ul><li>**{yyyy}**: 4桁の暦年（大文字と小文字を区別）</li><li>**{yy}**: 2桁の暦年（大文字と小文字を区別）</li><li>**{MM}**: 2桁の月（大文字と小文字を区別）</li><li>**{dd}**: 2桁の日（大文字と小文字を区別）</li><li>**{HH}**: 2桁の時間（大文字と小文字を区別）</li><li>**{mm}**: 2桁の分（大文字と小文字を区別）</li><li>**{ss}**: 2桁の秒（大文字と小文字を区別）</li><li>**{fff}**: 3桁のナノ秒（大文字と小文字を区別）</li><li>**{instance_id}**: リクエスト （インスタンス） UUID</li><li>**{export_id}**：書き出し（スケジュール） UUID</li><li>**{idx}**: インデックスは0から始まります（各ファイルごとに増分）</li><li>**{total}**：転送ジョブ全体の合計ファイル番号</li><li>**{completion_millis}**：転送時間（ミリ秒単位）</li></ul></p><p>例えば、`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`を指定した場合、2026年1月15日にこの宛先に自動的に送信される書き出しには、次のファイルパスと名前が含まれます。[prefix_folder_name]/2026/01/15/my-report-[UID]-1.csv</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

1. Analysis Workspaceから、設定したアカウントと場所にデータを書き出せるようになりました。 データをクラウドにエクスポートする方法について詳しくは、[&#x200B; プロジェクトデータをクラウドにエクスポート &#x200B;](/help/analysis-workspace/export/export-cloud.md)を参照してください。
