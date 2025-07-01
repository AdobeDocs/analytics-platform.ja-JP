---
description: Analysis Workspace プロジェクトをクラウドの場所に書き出す方法について説明します。
keywords: Analysis Workspace
title: Customer Journey Analytics レポートのクラウドへの書き出し
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: c91ee21a3d4e20e3bdaeb75f2011ede6eee6cba0
workflow-type: tm+mt
source-wordcount: '2360'
ht-degree: 95%

---

# Customer Journey Analytics レポートのクラウドへの書き出し {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Data Warehouse と同様の完全なテーブルの書き出しを作成"
>abstract="完全なテーブルの書き出しは、Analysis Workspaceにデータが表示されたらすぐに使用できます。必要に応じて、完全なテーブルの書き出しを作成またはスケジュールできます。<br><br>書き出しに含めるデータが既にわかっている場合、完全なテーブルの書き出しを作成するのに数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics から Workspace の完全なテーブルを書き出し、指定したクラウドの宛先に書き出しを送信できます。

[書き出しの概要](/help/analysis-workspace/export/export-project-overview.md)の説明に従って、Customer Journey Analytics レポートを書き出す他の方法も使用できます。

## 完全なテーブルの書き出しについて

Analysis Workspace から完全なテーブルを Google、Azure、Amazon、Adobe などのクラウドプロバイダーに書き出すことができます。

[完全なテーブルをクラウドに書き出すメリット](#advantages-of-exporting-to-the-cloud)には、数百万行を書き出す機能、計算指標を含める機能、連結された値でデータ出力を構造化する機能などがあります。

完全なテーブルを書き出す場合は、次の点を考慮します。

* クラウドに書き出す前に、テーブル、環境、権限が[書き出し要件](#export-requirements)を満たしていることを確認します。

* 完全なテーブルをクラウドに書き出す際、一部の[機能](#unsupported-features)と[コンポーネント](#unsupported-components)はサポートされません。

完全なテーブルをクラウドに書き出す際は、次のプロセスを使用します。

1. [クラウドアカウントを設定](/help/components/exports/cloud-export-accounts.md)

1. [アカウントの場所を設定](/help/components/exports/cloud-export-locations.md)

1. [Workspace から完全なテーブルを書き出し](#export-full-tables-from-analysis-workspace)

1. [クラウドのデータにアクセス](#view-exported-data-and-manifest-file)および[アドビで書き出しを管理](/help/components/exports/manage-exports.md)

![手順 1～4 で説明する完全なテーブル書き出しプロセス。](assets/export-full-table-process.png)

## Analysis Workspace からの完全なテーブルの書き出し {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="マニフェストファイル"
>abstract="有効にすると、成功した書き出し配信にマニフェストファイルが含まれます。マニフェストファイルを使用すると、すべてのファイルが正常に配信されたことを確認できます。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>この節の説明に従ってデータを書き出す前に、完全なテーブルの書き出しについて詳しくは、上記の[完全なテーブルの書き出しについて](#understand-full-table-export)の節を参照してください。

Analysis Workspace から完全なテーブルを書き出すには：

1. まだ行っていない場合は、[クラウドの書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)の説明に従って、書き出しのアカウントと場所を設定します。

1. Analysis Workspace で、書き出すデータが含まれているフリーフォームテーブルを右クリックします。

1. 「[!UICONTROL **完全なテーブルを書き出し**]」を選択します。

   ![「完全なテーブルを書き出し」をハイライト表示するフリーフォームテーブルドロップダウンメニュー](assets/export-full-table.png)

1. [!UICONTROL **新しい完全なテーブルの書き出し**]&#x200B;ダイアログボックスで、次の情報を指定します。

   | フィールド名 | 関数 |
   |---------|----------|
   | 名前 | 書き出しの名前を指定します。この名前は、書き出しのリストに表示されます。 |
   | タグ | 既存のタグを書き出しに適用することも、新しいタグを作成および適用することもできます。 <p>既存のタグを書き出しに適用するには、ドロップダウンメニューから任意のタグを選択します。会社の任意のタグを適用できます<!-- double-check this -->。</p> <p>新しいタグを作成するには、新しいタグの名前を入力して、Enter キーを押します。</p><p>書き出しにタグを適用する際は、次の点を考慮します。 <ul><li>適用したタグは、書き出しテーブルでフィルタリングまたは検索できます。</li> <li>プロジェクトに適用したタグは、[書き出しの管理](/help/components/exports/manage-exports.md)の「書き出しページでの列の設定」で説明されているように、完全なテーブルを書き出す際には自動的に適用されません（または、[書き出し用に完全なプロジェクトをスケジュール](/help/analysis-workspace/export/t-schedule-report.md)する際、プロジェクトに適用されたタグが自動的に書き出しに適用されます）。<!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 説明 | 書き出しに説明を追加します。書き出しを表示する際に、説明を[書き出しページ](/help/components/exports/manage-exports.md)の列として表示することを選択できます。 |
   | データビュー | 書き出しに含めるコンポーネントが含まれているデータビューを選択します。データビュードロップダウンメニューは、ダイアログの左上隅にあり、データビューアイコン ![データビューアイコン](assets/data-view-icon.png) で識別できます。  <p>**メモ：**&#x200B;データテーブルに既に含まれているコンポーネントが欠落しているデータビューを選択した場合は、データテーブルをクリアし、選択したデータビューに含まれているコンポーネントを使用して再作成するプロンプトが表示されます。 </p> |
   | ルックバックウィンドウ | 各書き出しファイルに含めるレポート時間枠を選択します。オプションには、「[!UICONTROL **今日**]」、「[!UICONTROL **昨日**]」、「[!UICONTROL **過去 7 日間**]」、「[!UICONTROL **過去 30 日間**]」、「[!UICONTROL **今週**]」、「[!UICONTROL **今月**]」が含まれます。 <p>[!UICONTROL **書き出し頻度**]&#x200B;を&#x200B;[!UICONTROL **今すぐ送信（1 回限り）**]&#x200B;に設定した際、このオプションは表示されません。 |
   | データテーブル | 書き出すフリーフォームテーブルを表示します。左側のパネルからテーブルにコンポーネントをドラッグして、データテーブルを変更できます。コンポーネントをキャンバスに追加すると、テーブルは動的に更新されます。  <p>プロジェクトの完全なテーブルに適用したセグメントは、テーブルの個々の各列の上部に表示されます。</p> |
   | クリア | データテーブルの内容をクリアします。 これにより、新しい完全なテーブルの書き出しダイアログ内で新しいテーブルの作成を直接開始できます。 |
   | 書き出し頻度 | 書き出しを実行する頻度のスケジュールを設定します。 <p>「[!UICONTROL **今すぐ送信（1 回限り）**]」を選択すると、書き出しを 1 回のみ送信できます。このオプションを選択すると、書き出しがすぐに開始されます。<p>または、定義済みのスケジュールに従って、書き出しを送信することを選択できます。スケジュールに従って送信する場合、オプションには、[!UICONTROL **毎日**]、[!UICONTROL **毎週**]、[!UICONTROL **毎月曜日別**]、[!UICONTROL **毎月日付別**]、[!UICONTROL **毎年月日付別**]、[!UICONTROL **毎年指定日別**]&#x200B;が含まれます。 </p><p>書き出し頻度を選択する際は、次の点を考慮します。</p><ul><li>「[!UICONTROL **ルックバックウィンドウ**]」フィールドのオプションは、ここで選択した内容に応じて変更されます。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>選択したオプションに応じて、追加の設定フィールドが表示されます。</li></ul> |
   | 開始日時 | スケジュールされた書き出しを開始する日時。 <p>このオプションは、スケジュールされた書き出し頻度を選択する場合にのみ使用できます。</p> |
   | 終了日時 | スケジュールされた書き出しが期限切れになる日時。スケジュールされた書き出しは、設定した日時以降は実行されなくなります。 <p>このオプションは、スケジュールされた書き出し頻度を選択する場合にのみ使用できます。</p> |
   | ファイル形式 | 書き出すデータを .csv 形式にするか .json 形式にするかを選択します。 |
   | マニフェストファイルを含める | 有効にすると、成功した書き出し配信にマニフェストファイルが含まれます。マニフェストファイルを使用すると、すべてのファイルが正常に配信されたことを確認できます。これには、次の情報が含まれます。<ul><li>配信されたすべてのファイルのリスト</li><li>各ファイルの MD5 チェックサム</li></ul><p>書き出したデータは、[クラウドの書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)および[クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md)の説明に従って、設定したクラウドの宛先で圧縮ファイルとして使用できます。</p><p>圧縮ファイルのファイル名は、ファイル形式として CSV または JSON のどちらを選択したかに応じて、次のようになります。</p><ul><li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li></ul><p>上記の「[!UICONTROL **ファイル形式**]」フィールドでファイル形式を選択します。</p> |
   | アカウント | データを送信するクラウド書き出しアカウントを選択します。 <p>または、使用するクラウドアカウントをまだ設定していない場合は、新しいアカウントを設定できます。<ol><li>「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。<ul><li>[!UICONTROL **場所アカウント名**]：場所アカウントの名前を指定します。この名前は、場所を作成する際に表示されます。 </li><li>[!UICONTROL **場所アカウントの説明**]：同じアカウントタイプの他のアカウントと区別できるように、アカウントの簡単な説明を入力します。</li><li>[!UICONTROL **アカウントタイプ**]：書き出し先のクラウドアカウントのタイプを選択します。使用可能なアカウントタイプは、Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake、AEP Data Landing Zone です。</li></ul><li>アカウントの設定を完了するには、選択した&#x200B;[!UICONTROL **アカウントタイプ**]&#x200B;に対応する以下のリンクに進みます。<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 場所 | 書き出しデータを送信するアカウント上の場所を選択します。<p>または、選択したアカウントで使用する場所をまだ設定していない場合は、新しい場所を設定できます。<ol><li>「[!UICONTROL **場所を追加**]」を選択し、次の情報を指定します。 <ul><li>[!UICONTROL **名前**]：場所の名前。</li><li>[!UICONTROL **説明**]：アカウント上の他の場所と区別できるように、場所の簡単な説明を入力します。</li><li>[!UICONTROL **場所アカウント**]：場所を作成するアカウントを選択します。</li></ul><li>場所の設定を完了するには、「[!UICONTROL **場所アカウント**]」フィールドで選択したアカウントタイプに対応する以下のリンクに進みます。<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択して書き出しを保存します。

   データは、指定した頻度で指定したクラウドアカウントに送信されます。

1. （オプション）書き出しを作成したら、今すぐ送信するか、定義済みスケジュールで送信するかに関係なく、[書き出しページ](/help/components/exports/manage-exports.md)で表示および管理し、[書き出しログ](/help/components/exports/manage-export-logs.md)で表示できます。</p>

## 書き出しの管理

Analysis Workspace からデータを書き出したら、[書き出しの管理](/help/components/exports/manage-exports.md)の説明に従って、既存の書き出しを編集、再書き出し、複製、タグ付けまたは削除できます。

## クラウドへの書き出しのメリット {#advantages}

Customer Journey Analytics データをクラウドに書き出すと、次の操作を実行できます。

* Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflake などの共有の場所に書き出す。

* 大量の履歴データを保存する。

  このタイプのデータを使用すると、ビジネスインテリジェンスを獲得するために長期的なトレンドを検出し、最終的により良いビジネス上の意思決定につながります。

* 数千または数百万の行（ライセンスタイプに応じて、300 万行、3,000 万行、1 億 5,000 万行、または 3 億行）を含む完全なテーブルを書き出す。その他の書き出し方法では、最大 50,000 行まで書き出すことができます。

* 書き出された Customer Journey Analytics データに計算指標を含める。

* 連結された値としてデータ出力を構造化する。

* 1 回限りで書き出すか、スケジュールに従って書き出す（[その他の書き出しオプション](/help/analysis-workspace/export/export-project-overview.md)でも使用可能）。

* ファイルを CSV 形式または JSON 形式で書き出す（[その他の書き出しオプション](/help/analysis-workspace/export/export-project-overview.md)でも使用可能）。

* 複数のディメンションを含むテーブルを書き出す。

## 要件とサポートされていない機能 {#export-requirements}

この節では、データを書き出す際に考慮する必要がある最小要件とサポートされていない機能について説明します。

### 最小要件

テーブル、環境、権限が次の要件を満たしていることを確認します。

* **テーブル：**&#x200B;完全なテーブルの書き出しをサポートするために、すべてのテーブルには行に 1 つ以上のディメンション、各列に 1 つ以上の指標を含める必要があります。

* **環境：** Customer Journey Analytics で使用される [IP アドレス](/help/technotes/ip-addresses.md)と[ドメイン](/help/technotes/domains.md)が組織のファイアウォールを通過できることを確認します。

* **権限：** Adobe Admin Console では、完全なテーブルを書き出すに、ユーザーに&#x200B;[!UICONTROL **完全なテーブルの書き出し**]&#x200B;権限が割り当てられた製品プロファイルを割り当てる必要があります。Admin Console での製品プロファイルへの権限の割り当てについて詳しくは、[Admin Console のCustomer Journey Analytics 権限](/help/technotes/access-control.md)を参照してください。

  >[!NOTE]
  >
  >  [製品管理者の役割](/help/technotes/access-control.md#product-admin-role)が割り当てられているユーザーには、常に完全なテーブルを書き出すアクセス権があります。これらのユーザーには、[!UICONTROL **完全なテーブルの書き出し**]&#x200B;権限を割り当てる必要はありません。


### サポートされていない機能

次の機能はサポートされていないので、完全なテーブルの書き出しから自動的に削除されます。

* 割合
* 合計
* 検索フィルタリング
* 静的行
* 日付の整列
* 概要データセットからの指標
* 動的ディメンション項目

  動的ディメンション項目は、フリーフォームテーブルの列ヘッダーにディメンションをドロップすると作成され、その列は上位 5 つのディメンション項目によって動的にフィルタリングされます。 Analysis Workspaceでは、これらの上位 5 つのディメンション項目は、プロジェクトを読み込むたびに更新されます。 フルテーブルのエクスポートでは、これらのディメンション項目は静的になります。 詳しくは、[フリーフォームテーブルの動的ディメンション項目と静的ディメンション項目](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)を参照してください。
* 最初の分類のディメンションは変換され、書き出したテーブルの行にセカンダリディメンションとして追加されます。他の分類は、テーブルに含まれません。
* ほとんどのデータセットでは、並べ替えはサポートされていません。小さいデータセットでは、データが並べ替えられる可能性があります。

### サポートされていないコンポーネント

次のコンポーネントはサポートされていないので、Analysis Workspace では、完全なテーブルの書き出しを実行する際に、テーブルから削除するプロンプトが表示されます。

* 指標定義で基本関数または高度な関数を使用する計算指標（詳しくは、[基本関数](/help/components/calc-metrics/cm-functions.md)と[高度な関数](/help/components/calc-metrics/cm-adv-functions.md)を参照してください）
* 管理者によって書き出しを制限されているコンポーネント（詳しくは、*ラベルとポリシー [ の* データビューのデータガバナンスポリシーに関するセグメント ](/help/data-views/data-governance.md) の節を参照）
* 次のすべての条件を満たす任意のディメンション。
   * [オブジェクトの配列](/help/use-cases/object-arrays.md)の一部であるフィールドから作成された（Adobe Analytics の複数値変数に類似）
   * [永続性が有効](/help/data-views/component-settings/persistence.md)になっている
   * [バインディングディメンション](/help/use-cases/data-views/binding-dimensions-metrics.md)を使用していない
* 異なる[オブジェクトの配列](/help/use-cases/object-arrays.md)を参照するフィールドからの複数のディメンション（同じオブジェクトの配列を参照する複数のディメンションが許可されます）。
* レポートあたり 10 つ以上のディメンションと 10 つの指標（最大 10 つのディメンションと 10 つの指標がサポートされます）
* テーブル列の場合：
   * 日付範囲
   * ディメンション
* テーブル行の場合：
   * 計算指標
   * 指標
   * 日付範囲
   * セグメント

### アトリビューションの動作

完全なテーブルの書き出しでは、デフォルト以外のアトリビューションモデルを使用する計算指標がサポートされます（[列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)の&#x200B;*デフォルト以外のアトリビューションモデルの使用*&#x200B;の節で説明）。

レポートでデフォルト以外のアトリビューションモデルを使用している場合、レポートに単一のディメンションがあるか、複数のディメンションがあるかに応じて、レポートで使用している配分モデルは無視または保持されます。

* **単一のディメンションに指標アトリビューションが含まれるレポートの場合：**&#x200B;指標アトリビューションを使用する際に通常行われるように、[指標アトリビューション](/help/data-views/component-settings/attribution.md)は[配分モデル](/help/data-views/component-settings/persistence.md)を上書きします。

  例えば、「ファーストタッチ」指標アトリビューションは、「最新」ディメンション配分を上書きします。

* **複数のディメンションに指標アトリビューションが同時に含まれるレポートの場合：**&#x200B;ディメンション[配分モデル](/help/data-views/component-settings/persistence.md)に加えて[指標アトリビューション](/help/data-views/component-settings/attribution.md)が適用されます。

  例えば、「最新」ディメンション配分に加えて、「ファーストタッチ」指標アトリビューションが適用されます。さらに、指標アトリビューションは、フリーフォームテーブルで通常行われるように、各ディメンション項目に独立して適用されるのではなく、単一のディメンション項目であるかのように、割り当て後のディメンション項目のペアに適用されます。

  >[!NOTE]
  >
  >この記事で説明されているように、複数ディメンションのレポートは、データをクラウドに書き出す場合にのみサポートされます。

## 完全なテーブルの書き出し（Customer Journey Analytics）と Data Warehouse（Adobe Analytics）の比較 {#comparison}

以前に Data Warehouse を使用して Adobe Analytics データを書き出したことがある場合は、次の表が、Customer Journey Analytics で完全なテーブルを書き出す場合と、Adobe Analytics で Data Warehouse を使用してデータを書き出す場合の違いを理解するのに役立ちます。


| 機能 | Customer Journey Analytics での完全なテーブルの書き出し | Adobe Analytics の Data Warehouse |
|---------|----------|---------|
| カスタムレポートを作成 | はい | はい |
| 計算指標 | はい | いいえ |
| セグメント | ○ | 制限あり |
| ディメンション | 制限は 10 | 制限なし |
| 指標 | 制限は 10 | 制限なし |
| レポート行 | 階層に応じて、300 万行、3,000 万行、1 億 5,000 万行、3 億行の制限 | 制限なし |
| レポート数 | 制限なし | 制限なし |
| アドホック（1 回限り）配信 | はい | はい |
| 繰り返し配信をスケジュール | はい | はい |
| メール配信 | いいえ | はい |
| FTP／SFTP | × | レガシーサポート |
| Azure | はい | はい |
| Amazon S3 | はい | はい |
| Google Cloud Platform | はい | はい |
| Snowflake | はい | いいえ |
| 配信頻度 | 毎日 | 1 時間ごと |
