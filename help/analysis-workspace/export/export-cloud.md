---
description: Analysis Workspace プロジェクトをクラウドの場所に書き出す方法を説明します。
keywords: Analysis Workspace
title: クラウドへのCustomer Journey Analyticsレポートの書き出し
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '2205'
ht-degree: 4%

---

# クラウドへのCustomer Journey Analyticsレポートの書き出し

クラウドからWorkspaceの完全なテーブルを書き出し、指定したCustomer Journey Analytics宛先に書き出しを送信できます。

[ 書き出しの概要 ](/help/analysis-workspace/export/export-project-overview.md) に記載されているように、Customer Journey Analyticsレポートを書き出すその他の方法も使用できます。

## 完全テーブル書き出しについて

Analysis WorkspaceからGoogle、Azure、Amazon、Adobeなどのクラウドプロバイダーに完全なテーブルを書き出すことができます。

[ 完全なテーブルをクラウドに書き出す利点 ](#advantages-of-exporting-to-the-cloud) 数百万行を書き出す機能、計算指標を含める機能、連結された値でデータ出力を構造化する機能など。

テーブル全体を書き出す場合は、次の点を考慮してください。

* クラウドに書き出す前に、テーブル、環境、権限が [ 書き出し要件 ](#export-requirements) を満たしていることを確認します。

* 一部の [features](#unsupported-features) および [components](#unsupported-components) は、完全なテーブルをクラウドに書き出す際にはサポートされません。

完全なテーブルをクラウドに書き出す場合は、次の手順を使用します。

1. [クラウドアカウントの設定](/help/components/exports/cloud-export-accounts.md)

1. [アカウントの場所の設定](/help/components/exports/cloud-export-locations.md)

1. [Workspaceからの完全なテーブルの書き出し](#export-full-tables-from-analysis-workspace)

1. [ クラウド内のデータへのアクセス ](#view-exported-data-and-manifest-file) および [Adobeでの書き出しの管理 ](/help/components/exports/manage-exports.md)

![ 手順 1 ～ 4 で説明した完全テーブルの書き出しプロセス。](assets/export-full-table-process.png)

## Analysis Workspaceからの完全なテーブルの書き出し

>[!NOTE]
>
>この節の説明に従ってデータを書き出す前に、上記の [ 完全なテーブルの書き出しについて ](#understand-full-table-export) の節で、完全なテーブルの書き出しについて詳しく説明します。

Analysis Workspaceから完全なテーブルを書き出すには：

1. [ クラウドの書き出しアカウントの設定 ](/help/components/exports/cloud-export-accounts.md) の説明に従って、書き出しアカウントと場所をまだ設定していない場合は、設定します。

1. Analysis Workspaceで、書き出すデータを含んだフリーフォームテーブルを右クリックします。

1. 「[!UICONTROL **完全テーブルを書き出し**]」を選択します。

   ![ 「完全なテーブルを書き出し」がハイライト表示されたフリーフォームテーブル ドロップダウンメニュー ](assets/export-full-table.png)

1. [!UICONTROL **新規フルテーブルの書き出し**] ダイアログボックスで、次の情報を指定します。

   | フィールド名 | 関数 |
   |---------|----------|
   | 名前 | 書き出しの名前を指定します。 この名前は、書き出しのリストに表示されます。 |
   | タグ | 既存のタグを書き出しに適用することも、新しいタグを作成して適用することもできます。 <p>既存のタグを書き出しに適用するには、ドロップダウンメニューから任意のタグを選択します。 会社内のすべてのタグを適用できます <!-- double-check this -->。</p> <p>新しいタグを作成するには、新しいタグの名前を入力し、Enter キーを押します。</p><p>書き出しにタグを適用する場合は、次の点を考慮してください。 <ul><li>適用したタグは、書き出しテーブルでフィルタリングまたは検索できます。</li> <li>[ 書き出しを管理 ](/help/components/exports/manage-exports.md) の「書き出しページでの列の設定」で説明されているように、プロジェクトに適用されるタグがテーブル全体を書き出す際に自動的に適用されない。 （または、[ 書き出し用にプロジェクト全体のスケジュールを設定 ](/help/analysis-workspace/export/t-schedule-report.md) する場合、プロジェクトに適用されるタグは自動的に書き出しに適用されます。） <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 説明 | エクスポートに説明を追加します。 書き出しを表示する際に、[ 書き出しページ ](/help/components/exports/manage-exports.md) で説明を列として表示するように選択できます。 |
   | データビュー | 書き出しに含めるコンポーネントを含んだデータビューを選択します。 データビュードロップダウンメニューは、ダイアログの左上隅にあり、データビューアイコン ![ データビューアイコン ](assets/data-view-icon.png) で識別できます。  <p>**注意：** データテーブルにすでに含まれているコンポーネントが欠落しているデータビューを選択すると、データテーブルを消去して、選択したデータビューに含まれているコンポーネントを使用してデータテーブルを再作成するように求められます。 </p> |
   | ルックバックウィンドウ | 各エクスポートファイルに含めるレポート期間を選択します。 オプションには、「[!UICONTROL **今日**]」、「[!UICONTROL **昨日**]」、「[!UICONTROL **過去 7 日間**]」、「[!UICONTROL **過去 30 日間**]」、「[!UICONTROL **今週**]」、「[!UICONTROL **今月**] があります。 <p>このオプションは、「[!UICONTROL **エクスポートの頻度**] が「[!UICONTROL **今すぐ送信（1 回限り）**]」に設定されている場合は表示されません。 |
   | データテーブル | 書き出すフリーフォームテーブルを表示します。 左側のパネルからコンポーネントをテーブルにドラッグして、データテーブルを変更できます。 キャンバスにコンポーネントを追加すると、テーブルが動的に更新されます。  <p>プロジェクト内のテーブル全体に適用されたセグメントは、テーブルの個々の列の上部に表示されます。</p> |
   | クリア | データ テーブルの内容をクリアします。 これにより、新しい完全なテーブルの書き出しダイアログ内で直接新しいテーブルの作成を開始できます。 |
   | 書き出し頻度 | 書き出しの実行頻度のスケジュールを設定します。 <p>[!UICONTROL **今すぐ（1 回限り）送信**] を選択すると、書き出しは 1 回だけ送信されます。 このオプションを選択すると、書き出しが直ちに開始されます。<p>または、定義したスケジュールで書き出しを送信するように選択できます。 スケジュールに従って送信する場合、オプションには [!UICONTROL **毎日**]、[!UICONTROL **毎週**]、[!UICONTROL **月別、日別**]、[!UICONTROL **月別、日別**]、[!UICONTROL **年別**] および [!UICONTROL **特定日別**] があります。 </p><p>書き出し頻度を選択する際は、次の点を考慮してください。</p><ul><li>[!UICONTROL **ルックバックウィンドウ**] フィールドのオプションは、ここで選択した内容に応じて変わります。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>選択したオプションに応じて、追加の設定フィールドが表示されます。</li></ul> |
   | 開始日 | スケジュールされたエクスポートを開始する日時。 <p>このオプションは、スケジュールされた書き出し頻度を選択する場合にのみ使用できます。</p> |
   | 終了日 | スケジュールされた書き出しが期限切れになる日時。 スケジュールされた書き出しは、設定した日時以降は実行されなくなります。 <p>このオプションは、スケジュールされた書き出し頻度を選択する場合にのみ使用できます。</p> |
   | ファイル形式 | 書き出すデータを.csv 形式と.json 形式のどちらにするかを選択します。 |
   | アカウント | データを送信するクラウド書き出しアカウントを選択します。 <p>または、使用するクラウドアカウントをまだ設定していない場合は、新しいアカウントを設定できます。<ol><li>「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。<ul><li>[!UICONTROL **場所アカウント名**]：場所アカウントの名前を指定します。 この名前は、場所の作成時に表示されます </li><li>[!UICONTROL **場所アカウントの説明**]：アカウントの簡単な説明を入力して、同じアカウントタイプを持つ他のアカウントとの区別に役立てます。</li><li>[!UICONTROL **アカウントタイプ**]：書き出し先のクラウドアカウントのタイプを選択します。 使用可能なアカウントタイプは、Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake、AEP Data Landing Zone です。</li></ul><li>アカウントの設定を完了するには、選択した [!UICONTROL **アカウントタイプ**] に対応する以下のリンクを続行します。<ul><li>[AEP データランディングゾーン ](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 ロール ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google クラウドプラットフォーム ](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 場所名 | 書き出しデータを送信するアカウント上の場所を選択します。<p>または、選択したアカウントで使用する場所をまだ設定していない場合は、新しい場所を設定できます。<ol><li>「[!UICONTROL **場所を追加**]」を選択して、次の情報を指定します。 <ul><li>[!UICONTROL **名前**]：場所の名前。</li><li>[!UICONTROL **説明**]：アカウント上の他の場所との区別に役立つ、場所の短い説明を提供します。</li><li>[!UICONTROL **場所アカウント**]：場所を作成するアカウントを選択します。</li></ul><li>場所の設定を完了するには、「[!UICONTROL **場所アカウント**]」フィールドで選択したアカウントタイプに対応する、以下のリンクを続行します。<ul><li>[AEP データランディングゾーン ](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3 ロール ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google クラウドプラットフォーム ](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択して、書き出しを保存します。

   データは、指定した頻度で指定したクラウドアカウントに送信されます。

1. （オプション）書き出しを作成したら、すぐに送信するか、定義済みのスケジュールで送信するかを問わず、[ 書き出しページ ](/help/components/exports/manage-exports.md) で表示と管理を行ったり、[ 書き出しログ ](/help/components/exports/manage-export-logs.md) で表示したりできます。</p>

## 書き出しの管理

Analysis Workspaceからデータを書き出した後は、[ 書き出しの管理 ](/help/components/exports/manage-exports.md) に記載されているように、既存の書き出しの編集、再書き出し、複製、タグ付け、削除を行うことができます。

## 書き出されたデータとマニフェスト ファイルの表示

### 書き出したデータ

書き出されたデータは、[ クラウド書き出しアカウントの設定 ](/help/components/exports/cloud-export-accounts.md) および [ クラウド書き出し場所の設定 ](/help/components/exports/cloud-export-locations.md) で説明しているように、設定したクラウドの宛先で圧縮ファイルとして使用できます。

圧縮ファイルのファイル名は、ファイル形式として CSV と JSON のどちらを選択したかに応じて、次のようになります。

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>テーブルを書き出す際に、ファイル形式を「[!UICONTROL **ファイル形式**]」フィールドで指定します。詳しくは、[Analysis Workspaceからのすべてのテーブルの書き出し ](#export-full-tables-from-analysis-workspace) を参照してください。

### マニフェストファイル

ファイル名が `cja-export-{reportInstanceId}-{idx}.json.gz` のマニフェストファイルは、少なくとも 1 つのファイルを含む正常なエクスポート配信に含まれます。 マニフェストファイルを使用すると、すべてのファイルが正常に配信されたことを確認できます。 これには以下の情報が含まれます。

* 配信されたすべてのファイルのリスト

* 各ファイルの MD5 チェックサム

<!-- add in  what the file name, structure, and file format will be -->

## クラウドに書き出すメリット

Customer Journey Analyticsデータをクラウドに書き出すと、次の操作を実行できます。

* Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflakeなどの共有の場所に書き出します。

* 大量の履歴データを保存する。

  このタイプのデータを使用すると、ビジネスインテリジェンスを得るために長期的なトレンドを検出し、最終的にビジネスの意思決定を向上させることができます。

* 数千行または数百万行（ライセンスタイプに応じて、300 万行、3,000 万行、1 億 5,000 万行、3 億行）を含む完全なテーブルを書き出します。 その他の書き出し方法では、最大 50,000 行まで書き出すことができます。

* エクスポートされたCustomer Journey Analyticsデータに計算指標を含めます。

* 連結された値として出力される構造データ。

* 1 回限りのエクスポート、またはスケジュールに従ったエクスポート。 （[ その他の書き出しオプション ](/help/analysis-workspace/export/export-project-overview.md) でも使用可能）。

* ファイルを CSV 形式または JSON 形式で書き出します。 （[ その他の書き出しオプション ](/help/analysis-workspace/export/export-project-overview.md) でも使用可能）。

* 複数のディメンションが含まれるテーブルをエクスポートします。

## 書き出し要件 {#export-requirements}

### 最小要件

テーブル、環境、権限が次の要件を満たしていることを確認します。

* **テーブル：** すべてのテーブルが、テーブル全体の書き出しでサポートされるためには、行に少なくとも 1 つのディメンションと、各列に 1 つの指標を含める必要があります。

* **環境：** Customer Journey Analyticsで使用される [IP アドレス ](/help/technotes/ip-addresses.md) および [ ドメイン ](/help/technotes/domains.md) が、組織のファイアウォールを通過できることを確認します。

* **権限：** Adobe Admin Consoleでは、すべてのテーブルを書き出すには、[!UICONTROL **フルテーブルの書き出し**] 権限が割り当てられている製品プロファイルが割り当てられている必要があります。 Admin Consoleの製品プロファイルにアクセス権を割り当てる方法については、[Admin ConsoleのCustomer Journey Analyticsアクセス権 ](/help/technotes/access-control.md) を参照してください。

  >[!NOTE]
  >
  >  [ 製品管理者の役割 ](/help/technotes/access-control.md#product-admin-role) を割り当てられたユーザーは、常にすべてのテーブルを書き出すアクセス権を持ちます。これらのユーザーには [!UICONTROL **フルテーブルの書き出し**] 権限を割り当てる必要はありません。


### サポートされていない機能

次の機能はサポートされておらず、フルテーブル書き出しから自動的に削除されます。

* 割合（％）
* 合計
* 検索フィルター
* 静的行
* 日付の整列
* 動的ディメンション

  詳しくは、[ フリーフォームテーブルの動的ディメンション項目と静的ディメンション項目 ](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) を参照してください。
* 最初の分類のDimensionは変換され、エクスポートされたテーブルの行にセカンダリディメンションとして追加されます。その他の分類はテーブルに含まれません
* 並べ替えは、ほとんどのデータセットでサポートされていません。小さなデータセットでは、データが並べ替えられる場合があります

### サポートされていないコンポーネント

以下のコンポーネントはサポートされておらず、テーブル全体に書き出す場合に、テーブルからコンポーネントを削除するようにAnalysis Workspaceから求められます。

* 指標定義で基本的な関数または高度な関数を使用する計算指標（詳しくは [ 基本的な関数 ](/help/components/calc-metrics/cm-functions.md) および [ 高度な関数 ](/help/components/calc-metrics/cm-adv-functions.md) を参照）
* 管理者によって書き出しを制限されているコンポーネント（詳しくは、*ラベルとポリシー [ の* データビューのデータガバナンスポリシーに対するフィルター ](/help/data-views/data-governance.md) の節を参照）
* 次のすべての条件を満たすディメンション。
   * [ オブジェクトの配列 ](/help/use-cases/object-arrays.md) の一部であるフィールドから作成されました（Adobe Analyticsの複数値変数と同様）
   * [ 永続性が有効 ](/help/data-views/component-settings/persistence.md) になっている
   * [ バインディングディメンション ](/help/use-cases/data-views/binding-dimensions-metrics.md) を使用していない
* 1 つのレポートにつき 5 つを超えるディメンションと 5 つの指標（最大 5 つのディメンションと 5 つの指標がサポートされます）
* テーブルの列：
   * 日付範囲
   * ディメンション
* テーブルの行：
   * 計算指標
   * 指標
   * 日付範囲
   * フィルター

### 属性動作

完全テーブルの書き出しでは、デフォルト以外のアトリビューションモデルを使用する計算指標をサポートしています（*列設定* の「デフォルト以外のアトリビューションモデルの使用 [ 節で説明 ](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) ています）。

デフォルト以外のアトリビューションモデルがレポートで使用されている場合、レポートで使用されている配分モデルは、レポートに単一のディメンションがあるかまたは複数のディメンションがあるかどうかに応じて、無視されるか保持されます。

* **単一のディメンションに指標アトリビューションを含むレポートの場合：** [ 指標アトリビューション ](/help/data-views/component-settings/attribution.md) は、通常が指標アトリビューションを使用する場合と同様に [ 配分モデル ](/help/data-views/component-settings/persistence.md) を上書きします。

  例えば、「ファーストタッチ」指標アトリビューションは「最新」のディメンション配分を上書きします。

* **複数のディメンションに対する指標アトリビューションを同時に含むレポートの場合：** [ 指標アトリビューション ](/help/data-views/component-settings/attribution.md) が、ディメンション [ 配分モデル ](/help/data-views/component-settings/persistence.md) に加えて適用されます。

  例えば、「最新」のディメンション配分に加えて、「ファーストタッチ」指標アトリビューションが適用されます。 さらに、指標アトリビューションは、通常フリーフォームテーブルで行われるように、各ディメンション項目に個別に適用されるのではなく、割り当て後のディメンション項目のペアに対して、単一のディメンション項目であるかのように適用されます。

  >[!NOTE]
  >
  >多次元レポートは、この記事で説明しているように、データをクラウドに書き出す場合にのみサポートされます。

## Data Warehouseに対する完全テーブル書き出し（Customer Journey Analytics）の比較（Adobe Analytics）

以前にData Warehouseを使用してAdobe Analytics データを書き出した場合、完全なテーブルをData Warehouseで書き出す場合と、データをCustomer Journey Analyticsで書き出す場合をAdobe Analyticsで書き出す場合の違いを理解するのに、次の表が役立ちます。


| 機能 | Customer Journey Analyticsでのテーブル全体の書き出し | Adobe AnalyticsのData Warehouse |
|---------|----------|---------|
| カスタムレポートの作成 | ○ | ○ |
| 計算指標 | ○ | × |
| セグメント | ○ | 制限あり |
| ディメンション | 上限は 5 です | 制限なし |
| 指標 | 上限は 5 です | 制限なし |
| レポート行 | 階層に応じて、300 万、3,000 万、1 億 5,000 万、3 億の上限 | 制限なし |
| レポート数 | 制限なし | 制限なし |
| アドホック（1 回限りの）配信 | ○ | ○ |
| 繰り返し配信をスケジュール | ○ | ○ |
| メール配信 | × | ○ |
| FTP/SFTP | × | レガシーサポート |
| Azure | ○ | ○ |
| Amazon S3 | ○ | ○ |
| Google Cloud Platform | ○ | ○ |
| Snowflake | ○ | × |
| 配信頻度 | 毎日 | 1 時間ごと |
