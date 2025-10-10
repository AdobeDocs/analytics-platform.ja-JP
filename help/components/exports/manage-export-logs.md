---
description: 既存の書き出しのログの管理
keywords: Analysis Workspace
title: 書き出しログの管理
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 10%

---

# 書き出しログの管理

エクスポートログは、各エクスポートの詳細を提供し、Analysis Workspace データがクラウドに書き出されるたびに生成されます。 （データをクラウドに書き出す方法について詳しくは、[Customer Journey Analytics レポートのクラウドへの書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md) を参照してください。

スケジュールされた書き出しの場合、ログには、ログが送信されたときの書き出し設定が反映されます。 ログは削除できません。

## 書き出しログを表示

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

   ![&#x200B; 「ログ」タブを表示する「書き出し」ウィンドウ &#x200B;](assets/export-logs-tab.png)

   各ログの詳細は、使用可能な列に表示されます。

1. 次のいずれかの操作を行います。

   * 表示される [&#x200B; 列をカスタマイズ &#x200B;](#configure-columns) します。

   * ログ名の横にある **情報アイコン**![&#x200B; 情報アイコン &#x200B;](assets/information-icon.png) を選択して、ログに関連付けられているエクスポートを表示します。

   * ログ名の横にある **書き出しを編集アイコン**![&#x200B; 情報アイコン &#x200B;](assets/edit-export-icon.png) を選択して、ログに関連付けられている書き出しを編集します。

     書き出しの編集について詳しくは、[Customer Journey Analytics レポートのクラウドへの書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md) を参照してください。

## ログのフィルタリングと検索

必要な情報を見つけるには、ログのリストをフィルタリングするか、ログを検索します。

### ログのリストのフィルタリング

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. **フィルター** アイコンを選択します。

   ![&#x200B; アカウントタイプ別のフィルターリストを表示する書き出しウィンドウ &#x200B;](assets/export-log-filters.png)

   次の条件でフィルタリングできます。

   | フィルター | 説明 |
   |---------|----------|
   | [!UICONTROL **書き出し ID**] | 表示するエクスポートログのエクスポート ID を指定します。 |
   | [!UICONTROL **アカウントタイプ**] | ログが関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **ステータス**] | エクスポートのステータス。 次のステータスを表示できます。 <ul><li>[!UICONTROL **保留中**]：書き出しの特定のインスタンスが開始されましたが、まだ完了していません。<p>ステータスが保留中のエクスポートを再実行すると、エクスポートプロセスが遅延します。</p></li><li>[!UICONTROL **完了**]：書き出しの特定のインスタンスの処理が完了し、書き出しアカウントで使用できるようになりました。</li><li>[!UICONTROL **失敗**]<p>様々な状況で、書き出しが失敗する場合があります。 失敗ステータスの上にマウスポインターを置くと、失敗の詳細が表示されます。<p>失敗の考えられる理由について詳しくは、[&#x200B; 失敗した書き出しのトラブルシューティング &#x200B;](/help/components/exports/troubleshoot-exports.md) を参照してください。</p> |

   {style="table-layout:auto"}

### ログを検索

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. 検索フィールドに、検索するログに関連付けられている情報の入力を開始します。 テーブルで使用可能な任意の列からデータを検索できます。

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## 書き出しの編集

特定のログに関連付けられている書き出しを編集できます。

このオプションは、複数のログを選択している場合は使用できません。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. 編集するエクスポートに関連付けられているログを見つけます。

1. ログ名の横にある **エクスポートを編集** アイコン ![&#x200B; エクスポートログアイコン &#x200B;](assets/export-icon.png) を選択します。

   または

   ログの横にあるチェックボックスをオンにし、「[!UICONTROL **書き出しを編集**]」を選択します。

## 列の設定

「[!UICONTROL &#x200B; ログ &#x200B;]」タブの列を追加または削除して、表示する情報を設定できます。

列ヘッダーを選択して、その列でログを並べ替えます。 デフォルトでは、ログは書き出しが開始された日時で並べ替えられます。

「[!UICONTROL &#x200B; ログ &#x200B;] タブの列を設定するには：

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. **ログ** ページの右上にある「![&#x200B; テーブルをカスタマイズ &#x200B;](assets/customize-table-icon.png)」アイコン [!UICONTROL &#x200B; テーブルをカスタマイズ &#x200B;] を選択します。

   次の列を表示できます。

   | 使用可能な列 | 説明 |
   |---------|----------|
   | 書き出し名 | エクスポートの名前。 [Customer Journey Analytics レポートをクラウドに書き出す &#x200B;](/help/analysis-workspace/export/export-cloud.md) で説明されているように、ユーザーは作成時に名前を付けます。 |
   | 書き出し ID | エクスポートの作成時にエクスポートに自動的に割り当てられた ID。<!-- True? --> |
   | インスタンス ID | Customer Journey Analytics インスタンスの ID。<!-- True? --> |
   | データビュー名 | エクスポートに関連付けられたデータビューの名前。 [Customer Journey Analytics レポートのクラウドへの書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md) に示すように、書き出し時にデータビューを選択できます。 |
   | ファイル数 | エクスポートに含まれるファイルの数。 |
   | サイズ | 書き出しのサイズ。<p>ファイルサイズは 1024 を基準に計算されます。これは KIB および MIB として表されることがあります。 クラウドプロバイダーがベース 1000 を使用してサイズを計算すると、クラウドプロバイダーに表示されるサイズが、ここに表示されるサイズとは少し異なる場合があります。</p> |
   | 場所 | データが書き出されたアカウント上の場所。 |
   | アカウント | データが書き出されたアカウント。 |
   | ステータス | エクスポートのステータス。 使用可能なステータスは、[!UICONTROL &#x200B; 保留中 &#x200B;]、[!UICONTROL &#x200B; 配信済み &#x200B;]、[!UICONTROL &#x200B; 失敗 &#x200B;] です。 |
   | 配信日 | エクスポートが行われた日付。 |
   | アカウントタイプ | データが書き出されたクラウドアカウントのタイプ。 使用可能なアカウントタイプは、[!UICONTROL Amazon S3 Role ARN]、[!UICONTROL Google Cloud Platform]、[!UICONTROL Azure SAS]、[!UICONTROL Azure RBAC]、[!UICONTROL Snowflake]、[!UICONTROL Adobe Experience Platform] です。 |
   | 行数 | エクスポートされたテーブルに含まれる行数。 |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。選択した列は [!UICONTROL &#x200B; ログ &#x200B;] ページに表示され、関連情報が表示されます。

## 監査ログの表示

完全テーブルの書き出しは、[Customer Journey Analytics監査ログ &#x200B;](/help/privacy/audit-log.md) でも追跡されます。<!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
