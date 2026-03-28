---
description: 既存の書き出しのログの管理
keywords: Analysis Workspace
title: 書き出しログの管理
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: 50b82943d4c59f612240ffc8d83a8a08f09b8331
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 9%

---

# 書き出しログの管理

書き出しログでは、それぞれの書き出しに関する詳細が提供されます。Analysis Workspace データがクラウドに書き出されるたびに生成されます。 （データをクラウドにエクスポートする方法については、[Customer Journey Analytics レポートをクラウドにエクスポート &#x200B;](/help/analysis-workspace/export/export-cloud.md)を参照してください）。

スケジュールされた書き出しの場合、ログには、ログの送信時と同じ書き出し設定が反映されます。 ログを削除できません。

## 書き出しログを表示

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

   ![&#x200B; ログ タブを表示する書き出しウィンドウ &#x200B;](assets/export-logs-tab.png)

   各ログの詳細は、使用可能な列に表示されます。

1. 次のいずれかの操作を行います。

   * システム管理者は、すべてのユーザーに対して&#x200B;**[!UICONTROL ログを表示]**&#x200B;するオプションを有効にできます。 このオプションを有効にすると、書き出しを作成したユーザーに関係なく、すべてのログが表示されます。

   * [表示される列](#configure-columns)をカスタマイズします。

   * ログ名の横にある&#x200B;**情報アイコン** ![情報アイコン &#x200B;](assets/information-icon.png)を選択すると、ログに関連付けられている書き出しが表示されます。

   * ログ名の横にある&#x200B;**書き出し編集アイコン** ![書き出し編集アイコン &#x200B;](/help/assets/icons/Edit.svg)を選択して、ログに関連付けられている書き出しを編集します。

     書き出しの編集について詳しくは、[Customer Journey Analytics レポートのクラウドへの書き出し](/help/analysis-workspace/export/export-cloud.md)を参照してください。

## ログのフィルタリングと検索

必要な情報を見つけるには、ログのリストをフィルタリングするか、ログを検索します。

### ログのリストをフィルタリング

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. 「**フィルター**」アイコンを選択します。

   ![&#x200B; アカウントタイプ別のフィルターリストを表示するウィンドウをエクスポート &#x200B;](assets/export-log-filters.png)

   次の条件でフィルタリングできます。

   | フィルター | 説明 |
   |---------|----------|
   | [!UICONTROL **書き出しID**] | 表示する書き出しログの書き出しIDを指定します。 |
   | [!UICONTROL **アカウントタイプ**] | ログが関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **ステータス**] | 書き出しのステータス。 次のステータスを表示できます。 <ul><li>[!UICONTROL **保留中**]：書き出しの特定のインスタンスが開始されましたが、まだ完了していません。<p>ステータスが「保留中」の書き出しを再実行すると、書き出しプロセスが遅れます。</p></li><li>[!UICONTROL **完了**]：書き出しの特定のインスタンスの処理が完了し、書き出しアカウントで利用できるようになります。</li><li>[!UICONTROL **失敗**]<p>様々な状況で書き出しに失敗する可能性があります。 失敗ステータスにカーソルを合わせると、失敗の詳細が表示されます。</p><p>エラーの考えられる原因について詳しくは、[失敗した書き出しのトラブルシューティング &#x200B;](/help/components/exports/troubleshoot-exports.md)を参照してください。</p></li></ul> |

   {style="table-layout:auto"}

### ログの検索

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. 検索フィールドに、検索するログに関連付けられている情報を入力します。 テーブルで使用可能な任意の列からデータを検索できます。

<!-- 
removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. 
-->

<!-- 
1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. 
-->

## 書き出しの編集

特定のログに関連付けられている書き出しを編集できます。

このオプションは、複数のログを選択する場合は使用できません。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. 編集する書き出しに関連付けられているログを探します。

1. ログ名の横にある「**書き出しを編集**」アイコン「![書き出しログを編集」アイコン「](/help/assets/icons/Edit.svg)」を選択します。

   または

   ログの横にあるチェックボックスを選択し、[!UICONTROL **書き出しを編集**]&#x200B;を選択します。

## 完了または失敗した書き出しの再実行

特定の書き出しログに関連付けられた1つ以上の書き出しを再実行できます。 書き出しを再実行するには、書き出しログのステータスが「完了」または「失敗」で、7日以内である必要があります。

1. 再実行する1つ以上の書き出しジョブの横にあるチェックボックスをオンにします。

1. **[!UICONTROL 再実行]**&#x200B;を選択します。

## 列の設定

[!UICONTROL &#x200B; ログ &#x200B;] タブの列を追加または削除して、表示する情報を設定できます。

列ヘッダーを選択して、その列でログを並べ替えます。 デフォルトでは、ログは書き出しを開始した日時で並べ替えられます。

[!UICONTROL &#x200B; ログ &#x200B;] タブの列を設定するには：

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **ログ**]」タブを選択します。

1. **ログ** ページの右上にある![&#x200B; テーブルのカスタマイズ &#x200B;](assets/customize-table-icon.png) アイコン [!UICONTROL &#x200B; テーブルのカスタマイズ &#x200B;]を選択します。

   次の列を表示できます。

   | 使用可能な列 | 説明 |
   |---------|----------|
   | 書き出し名 | 書き出しの名前。 [Customer Journey Analytics レポートをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)の説明に従って、書き出し時に名前を付けます。 |
   | 書き出し ID | IDは、作成時に書き出しに自動的に割り当てられます。<!-- True? --> |
   | インスタンス ID | Customer Journey Analytics インスタンスのID。<!-- True? --> |
   | データビュー名 | 書き出しに関連付けられているデータビューの名前。 「[Customer Journey Analytics レポートをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)」の説明に従って、書き出しを作成するときにデータビューを選択できます。 |
   | ファイル数 | 書き出しに含まれるファイル数。 |
   | サイズ | 書き出しのサイズ。<p>ファイルサイズは基数1024で計算されます。基数はKiBやMiBのように表されることがあります。 クラウドプロバイダーが1000をベースにサイズを計算する場合、クラウドプロバイダーに表示されるサイズが、ここに表示されるサイズとわずかに異なる場合があります。</p> |
   | 場所 | データが書き出されたアカウント上の場所。 |
   | アカウント | データがエクスポートされたアカウント。 |
   | ステータス | 書き出しのステータス。 利用できるステータスは、[!UICONTROL 保留中]、[!UICONTROL 完了]、[!UICONTROL 失敗]です。 |
   | 配信日 | 書き出しが行われた日付。 |
   | 開始日 | 書き出しが開始された日付。 |
   | アカウントタイプ | データが書き出されたクラウドアカウントのタイプ。 利用できるアカウントタイプは、[!UICONTROL Amazon S3 Role ARN]、[!UICONTROL Google Cloud Platform]、[!UICONTROL Azure SAS]、[!UICONTROL Azure RBAC]、[!UICONTROL Snowflake]、および[!UICONTROL AEP Data Landing Zone]です。 |
   | 行数 | 書き出されたテーブルに含まれる行数。 |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。選択した列が[!UICONTROL &#x200B; ログ &#x200B;] ページに表示され、関連情報が表示されます。

## 監査ログの表示

テーブルの書き出しは、[Customer Journey Analytics監査ログ &#x200B;](/help/privacy/audit-log.md)でも追跡されます。<!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
