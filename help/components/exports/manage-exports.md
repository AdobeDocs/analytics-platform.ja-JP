---
description: 既存の書き出しの管理
keywords: Analysis Workspace
title: 書き出しの管理
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
TQID: https://experienceleague.adobe.com/a63XlsGElfxDW1-EqB2l1iMdTtMlk7OaVBuLvS8QH7E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 1281
ht-degree: 6%

---

# 書き出しの管理

「[Customer Journey Analytics レポートをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)」の説明に従ってテーブル全体を書き出した後、書き出しは、[!UICONTROL 書き出し] ページの「[!UICONTROL 書き出し]」タブで利用できます。

作成した書き出しのみが表示されます。 管理者は、「**[!UICONTROL すべてのユーザーの書き出しを表示]**」オプションを有効にすることで、すべての書き出しを表示できます。

## 書き出しのフィルターと検索

必要な情報を検索するには、書き出しのリストをフィルタリングするか、書き出しを検索します。

### 書き出しのリストをフィルタリング

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブを選択します。

   ![書き出しページの管理](assets/exports-manage.png)

1. **フィルター** アイコン ![&#x200B; フィルターアイコン &#x200B;](/help/assets/icons/Filter.svg)を選択します。

   次の条件でフィルタリングできます。

   | フィルター | 説明 |
   |---------|----------|
   | [!UICONTROL **アカウントタイプ**] | 書き出しが関連付けられているアカウントタイプ。 次のアカウントタイプを使用できます。 <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **ステータス**] | 書き出しのステータス。 次のステータスを表示できます。 <ul><li>[!UICONTROL **アクティブ**]：スケジュールされた書き出しがまだ期限切れになっていないか、1回限りの書き出しがまだ完了していないことを示します。 </li><li>[!UICONTROL **完了**]：書き出しが正常に書き出されたことを示します。 スケジュールされた書き出しの場合、スケジュールが期限切れであることを示します。</li><li>[!UICONTROL **失敗**]<p>次の状況では、書き出しに失敗する可能性があります。 失敗の詳細を表示するには、[!UICONTROL **失敗**] ステータスにカーソルを合わせます。 <ul><li>スケジュールされた書き出しの有効期限</li><li>スケジュールされた書き出しの行数の上限に達しました </li></ul><li>[!UICONTROL **期限切れ**]：書き出しの有効期限が切れていることを示します。</li></ul> |
   | [!UICONTROL **作成者**] | エクスポートを作成したユーザー。<p>このオプションは、**[!UICONTROL すべてのユーザーの書き出しを表示]** オプションが有効になっている場合にのみ、管理者が使用できます。 |
   | [!UICONTROL **頻度**] | 書き出しの頻度。 次の周波数を使用できます。 <ul><li>[!UICONTROL **1回**]</li><li>[!UICONTROL **毎日**]</li><li>[!UICONTROL **毎週**]</li><li>[!UICONTROL **毎月**]</li><li>[!UICONTROL **年**]</li></ul> |

   {style="table-layout:auto"}

### 書き出しを検索

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブを選択します。

   ![書き出しページの管理](assets/exports-manage.png)

1. 検索フィールドで、検索中の書き出しに関連付けられている情報を入力します。 テーブルで使用可能な任意の列からデータを検索できます。

## 書き出しの編集

書き出しのプロパティ、形式、スケジュール、位置情報を編集できます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、編集する書き出しの横にあるチェックボックスを選択します。

   複数の書き出しを選択する場合、このオプションは使用できません。

1. 「[!UICONTROL **編集**]」を選択します。

   [!UICONTROL **テーブル全体を書き出し**] ダイアログが表示されます。

1. 使用可能なオプションのいずれかを更新します。 各オプションについて詳しくは、[Customer Journey Analytics レポートをAnalysis Workspace](/help/analysis-workspace/export/export-cloud.md)に書き出しの[&#128279;](/help/analysis-workspace/export/export-cloud.md#export-full-tables)から完全なテーブルを書き出すを参照してください。

## 書き出しの更新

スケジュールされた1つ以上の書き出しは、期限が切れる前または後に更新できます。 書き出しは、更新した日付から1年間更新されます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、更新する1つ以上の書き出しの横にあるチェックボックスを選択します。

1. 「[!UICONTROL **更新**]」を選択します。

   [!UICONTROL **テーブル全体を書き出し**] ダイアログが表示されます。<!--check process from here. -->

1. 使用可能なオプションのいずれかを更新します。 各オプションについて詳しくは、[Customer Journey Analytics レポートをAnalysis Workspace](/help/analysis-workspace/export/export-cloud.md)に書き出しの[&#128279;](/help/analysis-workspace/export/export-cloud.md#export-full-tables)から完全なテーブルを書き出すを参照してください。

## 書き出しの複製

既存の書き出しを複製できます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、複製する書き出しの横にあるチェックボックスを選択します。

   複数の書き出しを選択する場合、このオプションは使用できません。

1. 「[!UICONTROL **複製**]」を選択します。

   書き出しの複製が作成されます。 新しい書き出しの名前は、元の書き出しの名前と一致し、ファイル名に&#x200B;_[!UICONTROL - Copy]_&#x200B;が追加されます。

1. （オプション） [変更するファイル名やその他のプロパティを含む、新しい書き出し](#edit-an-export)を編集します。

## 書き出しを手動で開始する

スケジュールされた書き出しまたは以前に完了した1回限りの書き出しのいずれかで、書き出しを手動で開始できます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、実行する書き出しの横にあるチェックボックスを選択します。

   複数の書き出しを選択する場合、このオプションは使用できません。

1. 「[!UICONTROL **今すぐ書き出し**]」を選択します。

## タグ付けと書き出し

タグを書き出しに適用すると、[!UICONTROL 書き出し] ページの[!UICONTROL &#x200B; タグ &#x200B;]列でこれらのタグを表示できます。 詳しくは、[列の設定](#configure-columns-on-the-exports-page)を参照してください。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、タグ付けする1つ以上の書き出しの横にあるチェックボックスを選択します。

1. 「[!UICONTROL **タグを編集**]」を選択します。

1. [!UICONTROL **タグ書き出し**] ダイアログで、新しいタグを作成するタグの名前を入力するか、ドロップダウンメニューから既存のタグを選択します。

   選択した書き出しの間に共通するタグがタグダイアログに表示されます。

1. 「[!UICONTROL **タグを適用**]」を選択します。


## 書き出しの削除

書き出しは、「書き出し」ページから削除できます。 書き出しを削除すると、書き出しページから削除されます。 削除されたスケジュール済み書き出しはキャンセルされ、送信されなくなります。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、削除する1つ以上の書き出しの横にあるチェックボックスを選択します。

1. [!UICONTROL **削除**]&#x200B;を選択し、確認メッセージが表示されたら&#x200B;[!UICONTROL **削除**]&#x200B;を選択します。

## [!UICONTROL 書き出し] ページの列を設定

[!UICONTROL 書き出し] タブの列を追加または削除して、表示する情報を設定できます。

列ヘッダーを選択して、その列で書き出しを並べ替えます。 デフォルトでは、書き出しは、書き出しが最後に変更された日時で並べ替えられます。

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、[!UICONTROL 書き出し] ページの右上にある「**テーブルをカスタマイズ**」アイコン「![&#x200B; テーブルをカスタマイズ &#x200B;](assets/customize-table-icon.png)」を選択します。

   次の列を表示できます。

   | 使用可能な列 | 説明 |
   |---------|----------|
   | 名前 | 書き出しの名前。 [Customer Journey Analytics レポートをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)の説明に従って、書き出し時に名前を付けます。 |
   | ID | IDは、作成時に書き出しに自動的に割り当てられます。<!-- True? --> |
   | データビュー名 | 書き出しに関連付けられているデータビューの名前。 「[Customer Journey Analytics レポートをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)」の説明に従って、書き出しを作成するときにデータビューを選択できます。 |
   | ステータス | 書き出しのステータス。 利用できるステータスは、[!UICONTROL &#x200B; アクティブ &#x200B;]、[!UICONTROL 完了]、[!UICONTROL 失敗]です。<p> **メモ：**&#x200B;失敗した書き出しのトラブルシューティングについて詳しくは、[失敗した書き出しのトラブルシューティング &#x200B;](/help/components/exports/troubleshoot-exports.md)を参照してください。</p> |
   | タグ | 書き出しに適用されているタグが表示されます。 書き出しにタグを適用する方法について詳しくは、[書き出しのタグ付け](#tag-an-export)を参照してください。 |
   | テーブルサイズ (前回の送信) | 前回の送信時の書き出しのサイズ。 |
   | 作成者 | エクスポートを作成したユーザー。 |
   | 作成日 | 書き出しが作成された日時。<!-- true? --> |
   | 場所 | データが書き出されたアカウント上の場所。 |
   | アカウント | データがエクスポートされたアカウント。 |
   | 頻度 | 書き出しが送信される頻度。 利用できるオプションは、[!UICONTROL 1回限り]、[!UICONTROL 日単位]、[!UICONTROL 週単位]、[!UICONTROL 月単位の曜日]、[!UICONTROL 月単位の日単位]、[!UICONTROL 年単位の月単位]、および[!UICONTROL 年単位の特定の日単位]です。 |
   | 送信時間 | エクスポートが送信された時間。 |
   | 前回の送信 | 前回エクスポートが送信された時刻。 |
   | 最終変更日 | 最後に書き出しが変更された時刻。 書き出しページの項目は、デフォルトでこの列で並べ替えられます。 |
   | アカウントタイプ | データが書き出されたクラウドアカウントのタイプ。 利用できるアカウントタイプは、[!UICONTROL Amazon S3 Role ARN]、[!UICONTROL Google Cloud Platform]、[!UICONTROL Azure SAS]、[!UICONTROL Azure RBAC]、[!UICONTROL Snowflake]、および[!UICONTROL AEP Data Landing Zone]です。 |

   {style="table-layout:auto"}

1. 表示する列が選択されていることを確認します。 選択した列が書き出しページに表示され、関連情報が表示されます。

## 書き出しページからの書き出しの作成

書き出しは、[完全テーブルをAnalysis Workspaceに書き出す](/help/analysis-workspace/export/export-cloud.md)の説明に従って、または書き出しページから作成できます（この節の説明を参照）。

書き出しページから書き出しの作成を開始するには：

1. Customer Journey Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **書き出し**]&#x200B;を選択します。

1. 「[!UICONTROL **書き出し**]」タブで、「**[!UICONTROL 書き出しを追加]**」を選択します。

1. 書き出しを作成するために、使用可能なフィールドに入力します。 各フィールドの詳細、およびコンポーネント、計算指標の関数、サポートされているその他の機能については、[完全なテーブルをクラウドに書き出し](/help/analysis-workspace/export/export-cloud.md)を参照してください。


