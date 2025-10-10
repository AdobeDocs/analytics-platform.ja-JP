---
description: 既存の書き出しの管理
keywords: Analysis Workspace
title: 書き出しの管理
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: 6f8a43acfba23d6faeff078873742315f1506699
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 7%

---

# 書き出しの管理

[Customer Journey Analytics レポートをクラウドに書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md) の説明に従って完全なテーブルを書き出すと、書き出しは [!UICONTROL &#x200B; 書き出し &#x200B;] ページの [!UICONTROL &#x200B; 書き出し &#x200B;] タブで使用できます。

自分が作成した書き出しのみを表示できます。

## 書き出しのフィルターと検索

必要な情報を見つけるには、書き出しのリストをフィルタリングするか、書き出しを検索します。

### 書き出しのリストのフィルタリング

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **書き出し**]」タブを選択します。

1. **フィルター** アイコンを選択します。

   <!--add screenshot -->

   次の条件でフィルタリングできます。

   | フィルター | 説明 |
   |---------|----------|
   | [!UICONTROL **アカウントタイプ**] | 書き出しが関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **ステータス**] | エクスポートのステータス。 次のステータスを表示できます。 <ul><li>[!UICONTROL **アクティブ**]：スケジュールされた書き出しがまだ期限切れになっていないか、1 回限りの書き出しがまだ完了していないことを示します。 </li><li>[!UICONTROL **完了**]：書き出しが正常に書き出されたことを示します。 スケジュールされた書き出しの場合は、スケジュールの有効期限が切れたことを示します。</li><li>[!UICONTROL **失敗**]<p>次の状況では、書き出しに失敗する場合があります。 [!UICONTROL **失敗**] ステータスの上にマウスポインターを置くと、失敗の詳細が表示されます。 <ul><li>スケジュールされた書き出しの有効期限</li><li>スケジュールされた書き出しの行制限に達しました </li></ul> </p></li></ul> |
   | [!UICONTROL **頻度**] | 書き出しの発生頻度。 次の頻度を使用できます。 <ul><li>[!UICONTROL **1 回**]</li><li>[!UICONTROL **毎日**]</li><li>[!UICONTROL **毎週**]</li><li>[!UICONTROL **毎月**]</li><li>[!UICONTROL **毎年**]</li></ul> |

   {style="table-layout:auto"}

### 書き出しの検索

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **書き出し**]」タブを選択します。

1. 検索フィールドに、検索する書き出しに関連する情報の入力を開始します。 テーブルで使用可能な任意の列からデータを検索できます。

## 書き出しの編集

書き出しのプロパティ、形式、スケジュール、および場所情報を編集できます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. [!UICONTROL **書き出し**] タブで、編集する書き出しの横にあるチェックボックスをオンにします。

   複数の書き出しを選択する場合、このオプションは使用できません。

1. 「[!UICONTROL **編集**]」を選択します。

   [!UICONTROL **完全なテーブルを書き出し**] ダイアログが表示されます。

1. 使用可能なオプションを更新します。 各オプションについて詳しくは、[Analysis Workspace レポートのクラウドへの書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) の [Customer Journey Analyticsからの完全なテーブルの書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md) を参照してください。

## 書き出しを複製

既存の書き出しを複製できます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. [!UICONTROL **書き出し**] タブで、複製する書き出しの横にあるチェックボックスをオンにします。

   複数の書き出しを選択する場合、このオプションは使用できません。

1. 「[!UICONTROL **複製**]」を選択します。

   書き出しの複製が作成されます。 新しい書き出しの名前は、元の書き出しの名前と一致し、ファイル名に _[!UICONTROL - コピー]_ が追加されます。

1. （任意） [&#x200B; 新しい書き出しを編集 &#x200B;](#edit-an-export) します。ファイル名やその他の変更するプロパティも指定します。

## 手動によるエクスポートの開始

スケジュールされた書き出し、または以前に完了した 1 回限りの書き出しに対して、手動で書き出しを開始できます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. [!UICONTROL **書き出し**] タブで、実行する書き出しの横にあるチェックボックスをオンにします。

   複数の書き出しを選択する場合、このオプションは使用できません。

1. [!UICONTROL **今すぐ書き出す**] を選択します。

## エクスポートのタグ付け

タグを書き出しに適用すると、それらのタグを [!UICONTROL &#x200B; 書き出し &#x200B;] ページの [!UICONTROL &#x200B; タグ &#x200B;] 列で表示できます。 詳しくは、[&#x200B; 列の設定 &#x200B;](#configure-columns) を参照してください。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. [!UICONTROL **書き出し**] タブで、タグ付けする 1 つ以上の書き出しの横にあるチェックボックスを選択します。

1. [!UICONTROL **タグを編集**] を選択します。

1. [!UICONTROL **タグの書き出し**] ダイアログで、新しいタグを作成するためのタグの名前を入力するか、ドロップダウンメニューから既存のタグを選択します。

   選択した書き出し間に共通するタグが、タグダイアログに表示されます。<!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. 「[!UICONTROL **タグを適用**]」を選択します。

## 書き出しの削除

書き出しは、書き出しページから削除できます。 スケジュールされた書き出しのうち、削除されたものは送信されなくなります。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. [!UICONTROL **書き出し**] タブで、削除する 1 つ以上の書き出しの横にあるチェックボックスを選択します。

1. 確認メッセージが表示されたら、「[!UICONTROL **削除**]」を選択してから「[!UICONTROL **削除**]」を選択します。

## [!UICONTROL &#x200B; 書き出し &#x200B;] ページでの列の設定

「[!UICONTROL &#x200B; 書き出し &#x200B;]」タブの列を追加または削除して、表示する情報を設定できます。

列ヘッダーを選択して、その列で書き出しを並べ替えます。 デフォルトでは、書き出しは、書き出しが最後に変更された日時で並べ替えられます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**] を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、**書き出し** ページの右上にある「![&#x200B; テーブルをカスタマイズ &#x200B;](assets/customize-table-icon.png) アイコン [!UICONTROL &#x200B; テーブルをカスタマイズ &#x200B;] を選択します。

   次の列を表示できます。

   | 使用可能な列 | 説明 |
   |---------|----------|
   | 名前 | エクスポートの名前。 [Customer Journey Analytics レポートをクラウドに書き出す &#x200B;](/help/analysis-workspace/export/export-cloud.md) で説明されているように、ユーザーは作成時に名前を付けます。 |
   | ID | エクスポートの作成時にエクスポートに自動的に割り当てられた ID。<!-- True? --> |
   | データビュー名 | エクスポートに関連付けられたデータビューの名前。 [Customer Journey Analytics レポートのクラウドへの書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md) に示すように、書き出し時にデータビューを選択できます。 |
   | ステータス | エクスポートのステータス。 使用可能なステータスは [!UICONTROL &#x200B; アクティブ &#x200B;]、[!UICONTROL &#x200B; 完了 &#x200B;]、[!UICONTROL &#x200B; 失敗 &#x200B;] です。<p> **注意：** 失敗した書き出しのトラブルシューティングについて詳しくは、[&#x200B; 失敗した書き出しのトラブルシューティング &#x200B;](/help/components/exports/troubleshoot-exports.md) を参照してください。</p> |
   | タグ | 書き出しに適用されているタグを表示します。 書き出しにタグを適用する方法について詳しくは、「[&#x200B; 書き出しにタグ付け &#x200B;](#tag-an-export) を参照してください。 |
   | テーブルサイズ (前回の送信) | 最後に送信された際のエクスポートのサイズ。 |
   | 作成者 | 書き出しを作成したユーザー。 |
   | 作成日 | エクスポートが作成された日時。<!-- true? --> |
   | 場所 | データが書き出されたアカウント上の場所。 |
   | アカウント | データが書き出されたアカウント。 |
   | 頻度 | 書き出しが送信される頻度。 使用できるオプションは、[!UICONTROL 1 回 &#x200B;]、[!UICONTROL &#x200B; 毎日 &#x200B;]、[!UICONTROL &#x200B; 毎週 &#x200B;]、[!UICONTROL &#x200B; 毎月 &#x200B;] 曜日、[!UICONTROL &#x200B; 毎月 &#x200B;]、[!UICONTROL &#x200B; 毎年 &#x200B;]、および [!UICONTROL &#x200B; 毎年の特定の日付 &#x200B;] です。 |
   | 送信時間 | エクスポートが送信された時刻。 |
   | 最後の送信 | エクスポートが最後に送信された時刻。 |
   | 最終変更日 | 最後にエクスポートが変更された時刻。 書き出しページの項目は、デフォルトではこの列で並べ替えられます。 |
   | アカウントタイプ | データが書き出されたクラウドアカウントのタイプ。 使用可能なアカウントタイプは、[!UICONTROL Amazon S3 Role ARN]、[!UICONTROL Google Cloud Platform]、[!UICONTROL Azure SAS]、[!UICONTROL Azure RBAC]、[!UICONTROL Snowflake]、[!UICONTROL Adobe Experience Platform] です。 |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。選択した列は書き出しページに表示され、関連情報が表示されます。
