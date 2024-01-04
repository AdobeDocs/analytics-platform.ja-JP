---
description: 既存のエクスポートを管理
keywords: Analysis Workspace
title: エクスポートを管理
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 4%

---

# エクスポートを管理

表全体をエクスポートした後、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md)を使用する場合、エクスポートは [!UICONTROL エクスポート] タブ [!UICONTROL エクスポート] ページに貼り付けます。

作成した書き出しのみが表示されます。

## エクスポートのフィルターと検索

必要な情報を見つけるには、エクスポートのリストをフィルタリングするか、エクスポートを検索します。

### エクスポートのリストをフィルター

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **エクスポート**] タブをクリックします。

1. を選択します。 **フィルター** アイコン。

   <!--add screenshot -->

   次の条件でフィルタリングできます。

   | フィルター | 説明 |
   |---------|----------|
   | [!UICONTROL **アカウントタイプ**] | エクスポートが関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP データランディングゾーン**]</li><li>[!UICONTROL **Amazon S3 ロール ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **ステータス**] | エクスポートのステータス。 次のステータスを使用できます。 <ul><li>[!UICONTROL **アクティブ**]：スケジュールされた書き出しがまだ期限切れでない、または 1 回限りの書き出しがまだ完了していないことを示します。 </li><li>[!UICONTROL **完了**]：書き出しが正常に書き出されたことを示します。 スケジュールされたエクスポートの場合は、スケジュールの有効期限が切れていることを示します。</li><li>[!UICONTROL **失敗**]<p>次の状況では、エクスポートが失敗する場合があります。 次の項目にカーソルを合わせます。 [!UICONTROL **失敗**] ステータスを使用して、失敗に関する詳細を確認します。 <ul><li>予定されている書き出しの有効期限</li><li>スケジュールされたエクスポートの行の上限に達しました </li></ul> </p></li></ul> |
   | [!UICONTROL **頻度**] | エクスポートが発生する頻度。 次の頻度を使用できます。 <ul><li>[!UICONTROL **1 回**]</li><li>[!UICONTROL **毎日**]</li><li>[!UICONTROL **毎週**]</li><li>[!UICONTROL **毎月**]</li><li>[!UICONTROL **毎年**]</li></ul> |

   {style="table-layout:auto"}

### エクスポートを検索

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. を選択します。 [!UICONTROL **エクスポート**] タブをクリックします。

1. 検索フィールドに、検索するエクスポートに関連する情報を入力します。 テーブル内の任意の列からデータを検索できます。

## エクスポートの編集

書き出しのプロパティ、形式、スケジュール、場所の情報を編集できます。

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. 次の日： [!UICONTROL **エクスポート**] 「 」タブで、編集するエクスポートの横にあるチェックボックスを選択します。

   複数の書き出しを選択する場合は、このオプションを使用できません。

1. 「[!UICONTROL **編集**]」を選択します。

   The [!UICONTROL **完全なテーブルをエクスポート**] ダイアログが表示されます。

1. 使用可能なオプションを更新します。 各オプションについて詳しくは、 [Analysis Workspaceからの完全なテーブルのエクスポート](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) in [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md).

## エクスポートの複製

既存のエクスポートを複製できます。

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. 次の日： [!UICONTROL **エクスポート**] 「 」タブで、複製するエクスポートの横にあるチェックボックスを選択します。

   複数の書き出しを選択する場合は、このオプションを使用できません。

1. 「[!UICONTROL **複製**]」を選択します。

   エクスポートの複製が作成されます。 新しいエクスポートの名前は、元のエクスポートの名前と一致し、 _[!UICONTROL — コピー]_ ファイル名に追加されました。

1. （オプション） [新しいエクスポートを編集](#edit-an-export)（ファイル名および変更するその他のプロパティを含む）

## エクスポートの手動開始

スケジュール済みのエクスポートまたは以前に完了した 1 回限りのエクスポートのいずれかに対して、エクスポートを手動で開始できます。

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. 次の日： [!UICONTROL **エクスポート**] 「 」タブで、実行するエクスポートの横にあるチェックボックスを選択します。

   複数の書き出しを選択する場合は、このオプションを使用できません。

1. 選択 [!UICONTROL **今すぐ書き出し**].

## エクスポートのタグ付け

書き出しにタグを適用すると、それらのタグは [!UICONTROL タグ] 列 [!UICONTROL エクスポート] ページに貼り付けます。 詳しくは、 [列の設定](#configure-columns) を参照してください。

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. 次の日： [!UICONTROL **エクスポート**] タブで、タグを付ける 1 つ以上の書き出しの横にあるチェックボックスを選択します。

1. 選択 [!UICONTROL **タグを編集**].

1. Adobe Analytics の [!UICONTROL **タグの書き出し**] ダイアログで、新しいタグを作成するタグの名前を入力するか、ドロップダウンメニューから既存のタグを選択します。

   選択した書き出しの間の共通タグが、タグダイアログに表示されます。 <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. 選択 [!UICONTROL **タグの適用**].

## エクスポートの削除

エクスポートページからエクスポートを削除できます。 削除されたスケジュール済みのエクスポートは、送信されなくなります。

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. 次の日： [!UICONTROL **エクスポート**] 「 」タブで、削除する 1 つ以上のエクスポートの横にあるチェックボックスを選択します。

1. 選択 [!UICONTROL **削除**]&#x200B;を選択し、「 [!UICONTROL **削除**] 確認メッセージが表示されたら、

## 上の列を設定する [!UICONTROL エクスポート] ページ

列を追加または削除するには、 [!UICONTROL エクスポート] タブをクリックして、表示する情報を設定します。

列ヘッダーを選択して、その列でエクスポートを並べ替えます。 デフォルトでは、エクスポートは、エクスポートが最後に変更された日時で並べ替えられます。

1. 「Customer Journey Analytics」で、「 [!UICONTROL **コンポーネント**] > [!UICONTROL **エクスポート**].

1. 次の日： [!UICONTROL **エクスポート**] タブで、 **テーブルをカスタマイズ** アイコン ![テーブルをカスタマイズ](assets/customize-table-icon.png) の右上に [!UICONTROL エクスポート] ページに貼り付けます。

   以下の列を表示できます。

   | 使用可能な列 | 説明 |
   |---------|----------|
   | 名前 | エクスポートの名前。 ユーザーは、作成時にエクスポートに名前を付けます。詳しくは、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md). |
   | ID | エクスポートの作成時に、エクスポートに自動的に割り当てられる ID です。 <!-- True? --> |
   | データビュー名 | エクスポートに関連付けられたデータビューの名前。 ユーザーは、エクスポートの作成時にデータビューを選択できます。詳しくは、 [Customer Journey Analyticsレポートをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md). |
   | ステータス | エクスポートのステータス。 利用可能なステータスは次のとおりです。 [!UICONTROL アクティブ], [!UICONTROL 完了]、および [!UICONTROL 失敗].<p> **注意：** 失敗したエクスポートのトラブルシューティングについて詳しくは、 [失敗した書き出しのトラブルシューティング](/help/components/exports/troubleshoot-exports.md).</p> |
   | タグ | 書き出しに適用されているタグが表示されます。 書き出しにタグを適用する方法について詳しくは、 [エクスポートのタグ付け](#tag-an-export). |
   | テーブルサイズ (前回の送信) | 最後に送信されたエクスポートのサイズ。 |
   | 作成者 | エクスポートを作成したユーザー。 |
   | 作成日 | エクスポートが作成された日時。 <!-- true? --> |
   | 場所 | データが書き出されたアカウント上の場所。 |
   | アカウント | データが書き出されたアカウント。 |
   | 頻度 | エクスポートが送信される頻度。 次のオプションを使用できます。 [!UICONTROL 1 回], [!UICONTROL 毎日], [!UICONTROL 毎週], [!UICONTROL 毎月（曜日別）], [!UICONTROL 毎月（日別）], [!UICONTROL 毎年 — 月の日別]、および [!UICONTROL 毎年 — 特定の日別]. |
   | 送信時間 | エクスポートが送信された時刻。 |
   | 最後の送信 | エクスポートが最後に送信された時刻。 |
   | 最終変更日 | エクスポートが最後に変更された日時。 エクスポートページ上の項目は、デフォルトではこの列で並べ替えられます。 |
   | アカウントタイプ | データが書き出されたクラウドアカウントのタイプ。 利用可能なアカウントのタイプは次のとおりです [!UICONTROL Amazon S3 ロール ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake]、および [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。 選択した列がエクスポートページに表示され、関連情報が表示されます。
