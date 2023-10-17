---
description: 既存のエクスポートのログを管理
keywords: Analysis Workspace
title: 書き出しログを管理
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
source-git-commit: 05cc65f3a463bc71db85d85292a172784c3d7c75
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 7%

---

# 書き出しログを管理

書き出しログは、各書き出しに関する詳細を提供し、Analysis Workspaceデータがクラウドに書き出されるたびに生成されます。 ( データをクラウドに書き出す方法について詳しくは、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md).)

スケジュールされたエクスポートの場合、ログには、ログの送信時と同じエクスポート設定が反映されます。 ログは削除できません。

## ログのフィルターと検索

必要な情報を見つけるには、ログのリストをフィルターするか、ログを検索します。

### ログのリストをフィルター

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **ログ**] タブをクリックします。

1. を選択します。 **フィルター** アイコン。

   ![情報をフィルター](assets/export-log-filters.png)

   次の条件でフィルタリングできます。

   | フィルター | 説明 |
   |---------|----------|
   | [!UICONTROL **書き出し ID**] | 表示するエクスポートログのエクスポート ID を指定します。 |
   | [!UICONTROL **アカウントタイプ**] | ログが関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP データランディングゾーン**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **ステータス**] | エクスポートのステータス。 次のステータスを使用できます。 <ul><li>[!UICONTROL **保留中**]：書き出しの特定のインスタンスは開始されましたが、まだ完了していません。<p>ステータスが「保留」のエクスポートを再実行すると、エクスポート処理が遅れます。</p></li><li>[!UICONTROL **完了**]：エクスポートの特定のインスタンスの処理が終了し、エクスポートアカウントで使用できるようになりました。</li><li>[!UICONTROL **失敗**]<p>様々な状況で、エクスポートが失敗する場合があります。 失敗ステータスの上にマウスポインターを置くと、失敗に関する詳細が表示されます。<p>エラーの考えられる理由について詳しくは、 [失敗した書き出しのトラブルシューティング](/help/components/exports/troubleshoot-exports.md).</p> |

   {style="table-layout:auto"}

### ログを検索

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **ログ**] タブをクリックします。

1. 検索フィールドに、検索するログに関連する情報を入力します。 テーブル内の任意の列からデータを検索できます。

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## エクスポートの編集

特定のログに関連付けられたエクスポートを編集できます。

複数のログを選択する場合は、このオプションを使用できません。

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **ログ**] タブをクリックします。

1. 編集するエクスポートに関連付けられているログを探します。

1. を選択します。 **エクスポートを編集** アイコン ![ログを書き出しアイコン](assets/export-icon.png) ログ名の横に表示されます。

   または

   ログの横にあるチェックボックスを選択し、「 」を選択します。 [!UICONTROL **エクスポートを編集**].

## 列の設定

列を追加または削除するには、 [!UICONTROL ログ] タブをクリックして、表示する情報を設定します。

列ヘッダーを選択して、その列でログを並べ替えます。 デフォルトでは、ログはエクスポートが開始された日時で並べ替えられます。

上の列を設定するには [!UICONTROL ログ] タブ：

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **ログ**] タブをクリックします。

1. を選択します。 **テーブルをカスタマイズ** アイコン ![テーブルをカスタマイズ](assets/customize-table-icon.png) の右上に [!UICONTROL ログ] ページに貼り付けます。

   以下の列を表示できます。

   | 使用可能な列 | 説明 |
   |---------|----------|
   | 書き出し名 | エクスポートの名前。 ユーザーは、作成時にエクスポートに名前を付けます。詳しくは、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md). |
   | 書き出し ID | エクスポートの作成時に、エクスポートに自動的に割り当てられる ID です。 <!-- True? --> |
   | インスタンス ID | Customer Journey Analyticsインスタンスの ID。 <!-- True? --> |
   | データビュー名 | エクスポートに関連付けられたデータビューの名前。 ユーザーは、エクスポートの作成時にデータビューを選択できます。詳しくは、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md). |
   | ファイル数 | エクスポートに含まれるファイルの数。 |
   | サイズ | 書き出しのサイズ。<p>ファイルサイズは 1024 の底を使用して計算され、KIB および MIB と表される場合があります。 クラウドプロバイダーが基数 1,000 のサイズを計算した場合、クラウドプロバイダーに表示されるサイズがここに表示されるサイズと少し異なる場合があります。</p> |
   | 場所 | データが書き出されたアカウント上の場所。 |
   | アカウント | データが書き出されたアカウント。 |
   | ステータス | エクスポートのステータス。 利用可能なステータスは次のとおりです。 [!UICONTROL 保留中], [!UICONTROL 配信済み]、および [!UICONTROL 失敗]. |
   | 配信日 | エクスポートがおこなわれた日付。 |
   | アカウントタイプ | データが書き出されたクラウドアカウントのタイプ。 利用可能なアカウントのタイプは次のとおりです [!UICONTROL Amazon S3 ロール ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake]、および [!UICONTROL Adobe Experience Platform]. |
   | 行数 | エクスポートするテーブルに含まれる行の数。 |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。 選択した列は、 [!UICONTROL ログ] ページを開き、関連情報を表示します。

## 監査ログの表示

また、 [Customer Journey Analytics監査ログ](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
