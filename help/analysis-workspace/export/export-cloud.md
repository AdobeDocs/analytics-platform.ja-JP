---
description: クラウドの場所にAnalysis Workspaceプロジェクトを書き出します。
keywords: Analysis Workspace
title: Customer Journey Analyticsレポートをクラウドにエクスポート
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: b984241de42b2db2992e18c17cd60ca14cc725c7
workflow-type: tm+mt
source-wordcount: '1853'
ht-degree: 4%

---

# Customer Journey Analyticsレポートをクラウドにエクスポート

Workspace の完全なテーブルをCustomer Journey Analyticsから書き出し、書き出しを指定されたクラウドの宛先に送信できます。

また、Customer Journey Analyticsレポートを書き出すその他の方法も使用できます。詳しくは、 [エクスポートの概要](/help/analysis-workspace/export/export-project-overview.md).

## 完全なテーブルの書き出しについて

Analysis Workspaceから、Google、Azure、Amazon、Adobeなどのクラウドプロバイダーに、完全なテーブルを書き出すことができます。

[完全なテーブルをクラウドにエクスポートする利点](#advantages-of-exporting-to-the-cloud) には、何百万もの行をエクスポートする機能、計算指標を含める機能、連結された値での構造データ出力などが含まれます。

完全なテーブルをエクスポートする場合は、次の点に注意してください。

* クラウドにエクスポートする前に、テーブル、環境、権限が [輸出要件](#export-requirements).

* 一部 [機能](#unsupported-features) および [コンポーネント](#unsupported-components) 完全なテーブルをクラウドにエクスポートする場合、はサポートされません。

完全なテーブルをクラウドにエクスポートする場合は、次のプロセスを使用します。

1. [クラウドアカウントの設定](/help/components/exports/cloud-export-accounts.md)

1. [アカウント上の場所の設定](/help/components/exports/cloud-export-locations.md)

1. [Workspace からの完全なテーブルのエクスポート](#export-full-tables-from-analysis-workspace)

1. [クラウド内のデータにアクセスする](#view-exported-data-and-manifest-file) および [エクスポートをAdobeで管理](/help/components/exports/manage-exports.md)

![完全なテーブルの書き出しプロセス](assets/export-full-table-process.png)

## Analysis Workspaceからの完全なテーブルのエクスポート

>[!NOTE]
>
>この節で説明するようにデータをエクスポートする前に、 [完全なテーブルの書き出しについて](#understand-full-table-export) 」の節を参照してください。

Analysis Workspaceから完全なテーブルをエクスポートするには：

1. まだエクスポートアカウントを設定していない場合は、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md).

1. Analysis Workspaceで、エクスポートするデータを含むフリーフォームテーブルを右クリックします。

1. 選択 [!UICONTROL **完全なテーブルをエクスポート**].

   ![フルテーブルをエクスポート](assets/export-full-table.png)

1. Adobe Analytics の [!UICONTROL **新しいフルテーブルエクスポート**] ダイアログボックスで、次の情報を指定します。

   | フィールド名 | 関数 |
   |---------|----------|
   | 名前 | エクスポートの名前を指定します。 この名前は、エクスポートのリストに表示されます。 |
   | タグ | 既存のタグをエクスポートに適用することも、新しいタグを作成して適用することもできます。 <p>既存のタグをエクスポートに適用するには、ドロップダウンメニューから任意のタグを選択します。 会社内のタグを適用できます<!-- double-check this -->.</p> <p>新しいタグを作成するには、新しいタグの名前を入力し、Enter キーを押します。</p><p>書き出しにタグを適用する際は、次の点を考慮してください。 <ul><li>適用したタグは、エクスポートテーブルでフィルタリングしたり、検索したりできます。</li> <li>表全体をエクスポートする際に、プロジェクトに適用されたタグは自動的には適用されません。詳しくは、 [エクスポートを管理](/help/components/exports/manage-exports.md). ( または、 [完全なプロジェクトの書き出しをスケジュールする](/help/analysis-workspace/export/t-schedule-report.md)に設定すると、プロジェクトに適用されたタグが自動的に書き出しに適用されます )。  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 説明 | エクスポートに説明を追加します。 説明を列として [書き出しページ](/help/components/exports/manage-exports.md) （エクスポートを表示する場合） |
   | データビュー | エクスポートに含めるコンポーネントを含むデータビューを選択します。 データビュードロップダウンメニューは、ダイアログの左上隅にあり、データビューアイコンで識別できます![データ表示アイコン](assets/data-view-icon.png).  <p>**注意：** データテーブルに既に含まれているコンポーネントが見つからないデータビューを選択すると、データテーブルをクリアし、選択したデータビューに含まれるコンポーネントを使用して再作成するよう求められます。 </p> |
   | ルックバックウィンドウ | 各エクスポートファイルに含めるレポート期間を選択します。 次のオプションがあります [!UICONTROL **今日**], [!UICONTROL **昨日**], [!UICONTROL **過去 7 日間**], [!UICONTROL **過去 30 日間**], [!UICONTROL **今週**]、および [!UICONTROL **今月**]. |
   | クリア | データテーブルの内容をクリアします。 これにより、新しいフルテーブルの書き出しダイアログ内で、新しいテーブルの作成を直接開始できます。 |
   | 書き出し頻度 | エクスポートを実行する頻度のスケジュールを設定します。 <p>次を選択できます。 [!UICONTROL **今すぐ送信（1 回）**] を 1 回だけ送信する必要があります。 このオプションを選択すると、エクスポートが直ちに開始されます。<p>または、定義したスケジュールに従ってエクスポートを送信することもできます。 スケジュールに従って送信する場合、次のオプションがあります。 [!UICONTROL **毎日**], [!UICONTROL **毎週**], [!UICONTROL **毎月（曜日別）**], [!UICONTROL **毎月（日別）**], [!UICONTROL **毎年 — 月の日別**]、および [!UICONTROL **毎年 — 特定の日別**]. </p><p>書き出し頻度を選択する際は、次の点に注意してください。</p><ul><li>Adobe Analytics の [!UICONTROL **ルックバックウィンドウ**] フィールドは、ここで選択した内容に応じて変わります。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>選択したオプションに応じて、追加の設定フィールドが表示されます。</li></ul> |
   | 開始日 :  | スケジュールされたエクスポートを開始する日時。 <p>このオプションは、スケジュールされた書き出し頻度を選択した場合にのみ使用できます。</p> |
   | 終了日 | スケジュールされたエクスポートの有効期限が切れる日時。 設定した日時以降、スケジュールされたエクスポートは実行されなくなります。 <p>このオプションは、スケジュールされた書き出し頻度を選択した場合にのみ使用できます。</p> |
   | ファイル形式 | 書き出したデータを.csv 形式と.json 形式のどちらにするかを選択します。 |
   | アカウント | データを送信するクラウドエクスポートアカウントを選択します。 <p>詳しくは、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md).</p> |
   | 場所名 | エクスポートデータを送信するアカウント上の場所を選択します。 <p>詳しくは、 [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).</p><p>次の項目を選択できます。 [!UICONTROL **新しい場所を追加**] ボタンをクリックして、既存のエクスポートアカウントの新しい場所を作成します。 |

   {style="table-layout:auto"}

1. 選択 [!UICONTROL **保存**] エクスポートを保存します。

   指定した頻度で指定したクラウドアカウントにデータが送信されます。

1. （オプション）エクスポートを作成した後、今すぐ送信するか、定義したスケジュールに従って送信するかを選択した場合は、 [書き出しページ](/help/components/exports/manage-exports.md) をクリックし、 [ログの書き出し](/help/components/exports/manage-export-logs.md).</p>

## エクスポートを管理

Analysis Workspaceからデータを書き出した後、既存の書き出しを編集、再書き出し、複製、タグ付け、削除できます。詳しくは、 [エクスポートを管理](/help/components/exports/manage-exports.md).

## 書き出されたデータとマニフェストファイルを表示

### 書き出したデータ

書き出されたデータは、設定したクラウドの宛先で圧縮ファイルとして使用できます。詳しくは、 [クラウドエクスポートアカウントの設定](/help/components/exports/cloud-export-accounts.md) および [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md).

圧縮ファイルのファイル名は、ファイル形式として CSV と JSON のどちらを選択したかに応じて、次のようになります。

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>ファイル形式は、 [!UICONTROL **ファイル形式**] フィールド（テーブルのエクスポート時） [Analysis Workspaceからの完全なテーブルのエクスポート](#export-full-tables-from-analysis-workspace).

### マニフェストファイル

ファイル名がのマニフェストファイル `cja-export-{reportInstanceId}-{idx}.json.gz` は、少なくとも 1 つのファイルを含む、成功した書き出し配信に含まれます。 マニフェストファイルを使用すると、すべてのファイルが正常に配信されたことを確認できます。 次の情報が含まれます。

* 配信されたすべてのファイルのリスト

* 各ファイルのサイズ

* 各ファイルのタイムスタンプ

<!-- add in  what the file name, structure, and file format will be -->

## クラウドに書き出す利点

Customer Journey Analyticsデータをクラウドに書き出すと、次のことができます。

* Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflakeなどの共有場所にエクスポートします。

* 大量の履歴データを保存する。

  このタイプのデータは、ビジネスインテリジェンスを獲得し、最終的により良いビジネス意思決定を引き起こすために、長期的な傾向を検出するために使用できます。

* 数千または数百万の行（ライセンスのタイプに応じて 300 万、3000 万、1 億 5000 万の行）を含む完全なテーブルをエクスポートします。 その他の書き出し方法では、最大 50,000 行まで書き出すことができます。

* エクスポートされた指標データに計算Customer Journey Analyticsを含めます。

* 連結された値としての構造データ出力。

* アドホックまたはスケジュールに従ってエクスポートします。 ( また、 [その他の書き出しオプション](/help/analysis-workspace/export/export-project-overview.md).)

* CSV 形式または JSON 形式でファイルを書き出します。 ( また、 [その他の書き出しオプション](/help/analysis-workspace/export/export-project-overview.md).)

* 複数のディメンションを含むテーブルをエクスポートします。

## エクスポート要件 {#export-requirements}

### 最小要件

テーブル、環境、権限が次の要件を満たしていることを確認します。

* **テーブル：** フルテーブルエクスポートでサポートされるように、すべてのテーブルで、行に少なくとも 1 つのディメンションと各列に 1 つの指標を含める必要があります。

* **環境：** 管理者は、 [Customer Journey Analyticsで使用する IP アドレス](/help/admin/ip-addresses.md) は、ファイアウォールの許可リストに加えるに含まれます。

* **権限：** Adobe Admin Consoleでは、ユーザーに、 [!UICONTROL **フルテーブルエクスポート**] 完全なテーブルをエクスポートするために割り当てられた権限。 Admin Consoleでの製品プロファイルへの権限の割り当てについて詳しくは、 [Customer Journey AnalyticsのAdmin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analyticsアクセス制御](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

### サポートされない機能

次の機能はサポートされておらず、フルテーブル書き出しから自動的に削除されます。

* 割合（％）
* 合計
* 検索フィルター
* 静的な行
* 日付の整列
* 動的ディメンション

  詳しくは、 [フリーフォームテーブルの動的ディメンション項目と静的ディメンション項目](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* 最初の分類のDimensionは変換されて、エクスポートされたテーブルの行にセカンダリディメンションとして追加されます。その他の分類は、テーブルに含まれません。
* ほとんどのデータセットでは並べ替えがサポートされていません。小さいデータセットではデータを並べ替えることができます

### サポートされていないコンポーネント

次のコンポーネントはサポートされていません。フルテーブルエクスポートの実行時に、Analysis Workspaceからコンポーネントを削除するよう求められます。

* 指標定義で基本関数または高度な関数を使用する計算指標 ( [基本関数](/help/components/calc-metrics/cm-functions.md) および [高度な関数](/help/components/calc-metrics/cm-adv-functions.md) （詳細情報）
* 管理者によって制限されたコンポーネントのエクスポート ( *データビューのデータガバナンスポリシーに対するフィルタリング* のセクション [ラベルとポリシー](/help/data-views/data-governance.md) （詳細情報）
* 1 レポートにつき 5 つ以上のディメンションと 5 つの指標（最大 5 つのディメンションと 5 つの指標がサポートされます）
* テーブルの列：
   * 日付範囲
   * ディメンション
* テーブルの行：
   * 計算指標
   * 指標
   * 日付範囲
   * フィルター

### アトリビューション動作

フルテーブルでの書き出しでは、デフォルト以外のアトリビューションモデル ( *デフォルト以外のアトリビューションモデルを使用* のセクション [列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)) をクリックします。

デフォルト以外のアトリビューションモデルがレポートで使用されている場合、レポートに単一のディメンションが使用されているか複数のディメンションが使用されているかに応じて、レポートで使用される配分モデルは無視または保持されます。

* **単一のディメンションに指標アトリビューションを含むレポートの場合：** [指標アトリビューション](/help/data-views/component-settings/attribution.md) 上書きする [配分モデル](/help/data-views/component-settings/persistence.md) は、通常、指標アトリビューションを使用する際におこなわれます。

  例えば、「ファーストタッチ」指標アトリビューションは、「最新」のディメンション配分を上書きします。

* **複数のディメンションに同時に指標アトリビューションを含むレポートの場合：** [指標アトリビューション](/help/data-views/component-settings/attribution.md) は、ディメンションに加えて適用されます。 [配分モデル](/help/data-views/component-settings/persistence.md).

  例えば、「最新」のディメンション配分に加えて、「ファーストタッチ」指標アトリビューションが適用されます。 さらに、指標アトリビューションは、フリーフォームテーブルで通常おこなわれるように、各ディメンション項目に個別にではなく、単一のディメンション項目であるかのように、後で割り当てられたディメンション項目のペアに適用されます。

  >[!NOTE]
  >
  >複数次元レポートは、この記事で説明するように、データをクラウドにエクスポートする場合にのみサポートされます。

## フルテーブルエクスポート (Customer Journey Analytics) とData Warehouse(Adobe Analytics) の比較

以前にData Warehouseを使用してAdobe Analyticsデータをエクスポートした場合、次の表は、Customer Journey AnalyticsでのフルテーブルのエクスポートとAdobe AnalyticsでのData Warehouseを使用したデータのエクスポートの違いを理解するのに役立ちます。


| 機能 | フルテーブルエクスポートCustomer Journey Analytics | Adobe AnalyticsでのData Warehouse |
|---------|----------|---------|
| カスタムレポートの作成 | ○ | ○ |
| 計算指標 | ○ | × |
| セグメント | ○ | 制限あり |
| ディメンション | 5 の制限 | 制限なし |
| 指標 | 5 の制限 | 制限なし |
| レポート行 | 制限は、階層に応じて 300 万、3000 万、1 億 5000 万、3 億 | 制限なし |
| レポート数 | 制限なし | 制限なし |
| アドホック配信 | ○ | ○ |
| 定期的な配信のスケジュール設定 | ○ | ○ |
| E メール配信 | × | ○ |
| FTP/SFTP | × | レガシーサポート |
| Azure | ○ | ○ |
| Amazon S3 | ○ | ○ |
| Google Cloud Platform | ○ | ○ |
| Snowflake | ○ | × |
| 配信頻度 | 毎日 | 1 時間ごと |
