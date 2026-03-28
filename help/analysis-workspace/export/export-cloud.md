---
description: クラウドの場所にテーブル全体を書き出す方法について説明します。
keywords: Analysis Workspace
title: 完全なテーブルをクラウドに書き出す
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '3234'
ht-degree: 56%

---

# 完全なテーブルのクラウドへの書き出し {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Data Warehouse と同様の完全なテーブルの書き出しを作成"
>abstract="完全なテーブルの書き出しは、Analysis Workspaceにデータが表示されたらすぐに使用できます。必要に応じて、テーブルの書き出しを作成またはスケジュールできます。<br><br>書き出しに含めるデータが既にわかっている場合は、数分でテーブルの書き出しを作成できます。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analyticsでは、Analysis Workspaceから指定されたクラウドの宛先にテーブル全体を書き出すことができます。

[書き出しの概要](/help/analysis-workspace/export/export-project-overview.md)の説明に従って、Customer Journey Analytics レポートを書き出す他の方法も使用できます。

## 完全なテーブルの書き出しについて

Analysis Workspace から完全なテーブルを Google、Azure、Amazon、Adobe などのクラウドプロバイダーに書き出すことができます。

[&#x200B; テーブルの書き出し](#advantages-of-full-table-export)の利点には、数百万行を書き出す機能、計算指標を含める機能、連結された値で構造化データを出力する機能などが含まれます。

完全なテーブルを書き出す場合は、次の点を考慮します。

* クラウドに書き出す前に、テーブル、環境、および権限が[最小書き出し要件](#minimum-requirements)を満たしていることを確認してください。

* 完全なテーブルをクラウドに書き出す際、一部の[機能](#unsupported-features)と[コンポーネント](#unsupported-components)はサポートされません。

完全なテーブルをクラウドに書き出す際は、次のプロセスを使用します。

1. [クラウドアカウントを設定](/help/components/exports/cloud-export-accounts.md)

1. [アカウントの場所を設定](/help/components/exports/cloud-export-locations.md)

1. [Workspace から完全なテーブルを書き出し](#export-full-tables)

1. クラウドアカウント内のクラウド内のデータにアクセスし、[Adobeでの書き出しを管理](/help/components/exports/manage-exports.md)

![手順 1～4 で説明する完全なテーブル書き出しプロセス。](assets/export-full-table-process.png)

## 完全なテーブルの書き出し  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-details"
>title="詳細"
>abstract="書き出しの名前を指定します。説明と任意のタグを追加することもできます。この情報は、書き出しテーブルおよびメール通知で書き出しを識別するのに役立ちます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-data-structure"
>title="データ構造"
>abstract="これは書き出すフリーフォームテーブルです。左側のパネルからテーブルにコンポーネントをドラッグして、データ構造を変更できます。フィルターを適用するには、コンポーネントをフィルター領域にドラッグします。コンポーネントをキャンバスに追加すると、テーブルは動的に更新されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="マニフェストファイルを含める"
>abstract="選択すると、成功した書き出し配信にマニフェストファイルが含まれます。 マニフェストファイルを使用すると、すべてのファイルが正常に配信されたことを確認できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-schedule"
>title="スケジュール"
>abstract="書き出しの発生頻度を選択します。すぐに書き出しを開始するには、「今すぐ送信」（1 回）を選択します。定期エクスポートは、指定した日時に開始されます。"

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-destination"
>title="宛先"
>abstract="データを送信するクラウドアカウントと場所を選択します。既存のアカウントと場所を選択するか、「新規追加」を選択して作成できます。書き出しの失敗または期限切れを通知するユーザーとグループを指定します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-format"
>title="ファイル形式"
>abstract="Parquet ファイル形式を選択すると、コンポーネント名に含まれる一部の特殊文字がアンダースコア（_）に置き換えられます。置き換えられる文字の完全なリストについて詳しくは、以下のリンクを参照してください。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-notifications"
>title="通知"
>abstract="この書き出しが失敗した場合、または期限切れになろうとしている場合に通知を受け取るユーザーとグループを追加します。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>この節の説明に従ってデータを書き出す前に、完全なテーブルの書き出しについて詳しくは、上記の[完全なテーブルの書き出しについて](#understand-full-table-export)の節を参照してください。

Analysis Workspace から完全なテーブルを書き出すには：

1. まだ設定していない場合は、[&#x200B; クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)および[書き出し場所の設定](/help/components/exports/cloud-export-locations.md)の説明に従って、書き出しアカウントと場所を設定します。

1. Analysis Workspaceで、フリーフォームテーブルの見出しを右クリックしてコンテキストメニューを表示し、「[!UICONTROL **テーブル全体を書き出し**]」を選択します。

   ![&#x200B; テーブル全体を書き出しがハイライト表示されたフリーフォームテーブルのコンテキストメニュー。](assets/export-full-table.png)

1. [!UICONTROL **新しい完全なテーブルの書き出し**]&#x200B;ダイアログボックスで、次の情報を指定します。

   | フィールド名 | 関数 |
   |---------|----------|
   | 名前 | 書き出しの名前を指定します。この名前は、書き出しのリストに表示されます。 |
   | タグ | 既存のタグを書き出しに適用することも、新しいタグを作成および適用することもできます。 <p>既存のタグを書き出しに適用するには、ドロップダウンメニューから任意のタグを選択します。あなたの会社のすべてのタグは適用できます。</p> <p>新しいタグを作成するには、新しいタグの名前を入力して、Enter キーを押します。</p><p>書き出しにタグを適用する際は、次の点を考慮します。 <ul><li>適用したタグは、書き出しテーブルでフィルタリングまたは検索できます。</li> <li>プロジェクトに適用したタグは、[書き出しの管理](/help/components/exports/manage-exports.md)の「書き出しページでの列の設定」で説明されているように、完全なテーブルを書き出す際には自動的に適用されません（または、[書き出し用の完全なプロジェクトのスケジュールを設定](/help/analysis-workspace/export/t-schedule-report.md)すると、プロジェクトに適用されたすべてのタグが書き出しに自動的に適用されます）。 </li></ul> |
   | 説明 | 書き出しに説明を追加します。書き出しを表示する際に、説明を[書き出しページ](/help/components/exports/manage-exports.md)の列として表示することを選択できます。 |
   | データビュー | 書き出しに含めるコンポーネントが含まれているデータビューを選択します。「![&#x200B; データ &#x200B;](/help/assets/icons/Data.svg) データ表示」ドロップダウンメニューは、ダイアログの左上隅にあります。  <p>**注意：** データテーブルに既に含まれているコンポーネントが欠落しているデータビューを選択した場合、選択したデータビューに含まれているコンポーネントを使用して、パネルをクリアして再作成するように求められます。 </p> |
   | データ構造 | 書き出すフリーフォームテーブルを表示します。左側のパネルからテーブルにコンポーネントをドラッグして、データ構造を変更できます。フィルターを適用するには、コンポーネントをフィルター領域にドラッグします。カンバスにコンポーネントを追加すると、テーブルが動的に更新されます。 最大10列まで含めることができます。<p>プロジェクトのテーブル全体に適用されたセグメントは、テーブルの上に表示されます。 セグメントまたはセグメントのグループを書き出しに適用できます。</p> |
   | レポートウィンドウ | 各書き出しファイルに含めるレポート時間枠を選択します。オプションには、「[!UICONTROL **今日**]」、「**[!UICONTROL 昨日]**」、「**[!UICONTROL 過去 7 日間]**」、「**[!UICONTROL 過去 30 日間]**」、「**[!UICONTROL 今週]**」、「**[!UICONTROL 今月]**」が含まれます。 <p>**[!UICONTROL 書き出し頻度]**&#x200B;を&#x200B;**[!UICONTROL 今すぐ送信（1 回限り）]**&#x200B;に設定した際、このオプションは表示されません。</p> |
   | すべてクリア | データテーブルの内容をクリアします。 これにより、新しい完全なテーブルの書き出しダイアログ内で新しいテーブルの作成を直接開始できます。 |
   | ファイル形式 | 書き出すデータを.csv、.jsonまたは.parquet形式にするかどうかを選択します。 <p>Parquet ファイル形式を選択すると、コンポーネント名に含まれる次の文字のいずれかがアンダースコア（_）に置き換えられます。 <ul><li>「」 - ASCII スペース</li><li>&#39;,&#39; - ASCII コンマ</li><li>&#39;;&#39; - ASCII コロン</li><li>&#39;{&#39;または&#39;}&#39; - ASCII開閉ブレース</li><li>&#39;（&#39;または&#39;）&#39; - ASCII括弧を開く/閉じる</li><li>&#39;\n&#39; - ASCII改行</li><li>&#39;\t&#39; - ASCII タブ</li><li>&#39;=&#39; - ASCIIが等しい</li></ul></p> |
   | マニフェストファイルを含める | 有効にすると、成功した書き出し配信にマニフェストファイルが含まれます。 <p>マニフェストファイルを使用すると、すべてのファイルが正常に配信されたことを確認できます。これには、次の情報が含まれます。</p> <ul><li>配信されたすべてのファイルのリスト</li><li>各ファイルの MD5 チェックサム</li></ul><p>書き出したデータは、[クラウドの書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)および[クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md)の説明に従って、設定したクラウドの宛先で圧縮ファイルとして使用できます。</p><p>ファイル形式として&#x200B;**[!UICONTROL csv]**、**[!UICONTROL json]**、**[!UICONTROL parquet]**&#x200B;のいずれかを選択したかどうかに応じて、圧縮ファイルのファイル名は次のようになります。</p><ul> <li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li><li>`cja-export-<instanceId>-<idx>.snappy.parquet`<p>parquet ファイルの各列は圧縮されます。</p></li></ul><p>上記の「**[!UICONTROL ファイル形式]**」フィールドでファイル形式を選択します。</p> |
   | 頻度 | 書き出しを実行する頻度のスケジュールを設定します。 <p>「[!UICONTROL **今すぐ送信（1 回限り）**]」を選択すると、書き出しを 1 回のみ送信できます。このオプションを選択すると、書き出しがすぐに開始されます。</p><p>または、定義済みのスケジュールに従って、書き出しを送信することを選択できます。スケジュールに従って送信する場合、オプションには、**[!UICONTROL 毎日]**、**[!UICONTROL 毎週]**、**[!UICONTROL 毎月曜日別]**、**[!UICONTROL 毎月日付別]**、**[!UICONTROL 毎年月日付別]**、**[!UICONTROL 毎年指定日別]**&#x200B;が含まれます。 </p> <p>書き出し頻度を選択する際は、次の点を考慮します。</p><ul><li>ここで選択した内容に応じて、**[!UICONTROL ルックバックウィンドウ]** フィールドのオプションが変更されます。</li><li>選択したオプションに応じて、追加の設定フィールドが表示されます。</li></ul> |
   | 開始日時 | 定期エクスポートを開始する日時。 <p>このオプションは、定期エクスポート頻度を選択する場合にのみ使用できます。</p> |
   | 終了日時 | 定期エクスポートが期限切れになる日時。定期エクスポートは、設定した日時以降は実行されなくなります。 <p>このオプションは、定期エクスポート頻度を選択する場合にのみ使用できます。</p> |
   | すべてのユーザーの宛先を表示 | システム管理者は、このオプションを選択して、作成者に関係なくすべてのアカウントと場所を表示できます。 |
   | アカウント | データを送信するクラウド書き出しアカウントを選択します。 <p>または、使用するクラウドアカウントをまだ設定していない場合は、新しいアカウントを設定できます。<ol><li>**[!UICONTROL アカウント]** ドロップダウンメニューで、**[!UICONTROL アカウントを追加]**&#x200B;を選択し、次の情報を指定します。<ul><li>**[!UICONTROL 場所アカウント名]**：場所アカウントの名前を指定します。この名前は、場所を作成する際に表示されます。 </li><li>**[!UICONTROL 場所アカウントの説明]**：同じアカウントタイプの他のアカウントと区別できるように、アカウントの簡単な説明を入力します。</li><li>**組織内のすべてのユーザーがアカウントを利用できるようにします**：組織内の他のユーザーがアカウントを使用できるようにするには、このオプションを選択します。</li><li>**[!UICONTROL アカウントタイプ]**：書き出し先のクラウドアカウントのタイプを選択します。使用可能なアカウントタイプは、Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake、AEP Data Landing Zone です。</li></ul><li>アカウントの設定を完了するには、選択した&#x200B;**[!UICONTROL アカウントタイプ]**&#x200B;に対応する以下のリンクに進みます。<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 場所 | 書き出しデータを送信するアカウント上の場所を選択します。<p>または、使用するクラウドアカウントをまだ設定していない場合は、新しいアカウントを設定できます。<ol><li>**[!UICONTROL 場所]** ドロップダウンメニューで、**[!UICONTROL 場所を追加]**&#x200B;を選択し、次の情報を指定します。<ul><li>**[!UICONTROL 名前]**：場所の名前。</li><li>**[!UICONTROL 説明]**：アカウント上の他の場所と区別できるように、場所の簡単な説明を入力します。</li><li>**組織内のすべてのユーザーが場所を利用できるようにします**：組織内の他のユーザーが場所を使用できるようにするには、このオプションを選択します。</li><li>**[!UICONTROL 場所アカウント]**：場所を作成するアカウントを選択します。</li></ul><li>場所の設定を完了するには、「**[!UICONTROL 場所アカウント]**」フィールドで選択したアカウントタイプに対応する以下のリンクに進みます。<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |
   | 通知 | この書き出しが失敗した場合、または期限切れになろうとしている場合に通知を受け取るユーザーとグループを追加します。 ユーザーの名前または電子メールアドレスを入力するか、グループ名の入力を開始してから、ドロップダウンリストに表示されたらグループ名を選択します。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択して書き出しを保存します。

   データは、指定した頻度で指定したクラウドアカウントに送信されます。

1. （オプション）書き出しを作成したら、今すぐ送信するか、定義済みスケジュールで送信するかに関係なく、[書き出しページ](/help/components/exports/manage-exports.md)で表示および管理し、[書き出しログ](/help/components/exports/manage-export-logs.md)で表示できます。

## 書き出しの管理

Analysis Workspace からデータを書き出したら、[書き出しの管理](/help/components/exports/manage-exports.md)の説明に従って、既存の書き出しを編集、再書き出し、複製、タグ付けまたは削除できます。

## テーブルの書き出しの利点 {#advantages}

Customer Journey Analytics データをクラウドに書き出すと、次の操作を実行できます。

* Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflake などの共有の場所に書き出す。

* 大量の履歴データを保存する。

  このタイプのデータは、ビジネスインテリジェンスを獲得するための長期的なトレンドを検出するために利用でき、最終的にはより優れたビジネス上の意思決定につながります。

* 数千または数百万の行（ライセンスタイプに応じて、300 万行、3,000 万行、1 億 5,000 万行、または 3 億行）を含む完全なテーブルを書き出す。その他の書き出し方法では、最大 50,000 行まで書き出すことができます。

* 書き出された Customer Journey Analytics データに計算指標を含める。

* 連結された値としてデータ出力を構造化する。

* 1 回限りで書き出すか、スケジュールに従って書き出す（[その他の書き出しオプション](/help/analysis-workspace/export/export-project-overview.md)でも使用可能）。

* CSV、JSONまたはParquet形式でファイルを書き出します。 （[その他の書き出しオプション](/help/analysis-workspace/export/export-project-overview.md)でも使用可能）。

* 複数のディメンションを含むテーブルを書き出す。

## 最小要件

テーブル、環境、権限が次の要件を満たしていることを確認します。

* **テーブル：**&#x200B;すべてのテーブルには、テーブルの書き出しでサポートする、行に少なくとも1つのディメンションと各列に1つの指標を含める必要があります。

* **環境：** Customer Journey Analytics で使用される [IP アドレス](/help/technotes/ip-addresses.md)と[ドメイン](/help/technotes/domains.md)が組織のファイアウォールを通過できることを確認します。

* **権限：** Adobe Admin Consoleでは、完全なテーブルを書き出すために、**[!UICONTROL テーブルの書き出し]**&#x200B;権限が割り当てられている製品プロファイルをユーザーに割り当てる必要があります。 Admin Console での製品プロファイルへの権限の割り当てについて詳しくは、[Admin Console のCustomer Journey Analytics 権限](/help/technotes/access-control.md)を参照してください。

  >[!NOTE]
  >
  >  [製品管理者の役割](/help/technotes/access-control.md#product-admin-role)が割り当てられているユーザーには、常に完全なテーブルを書き出すアクセス権があります。これらのユーザーには、**[!UICONTROL 完全なテーブルの書き出し]**&#x200B;権限を割り当てる必要はありません。


## サポートされていない機能

次の機能はサポートされていないので、完全なテーブルの書き出しから自動的に削除されます。

* 割合
* 合計
* 検索フィルタリング
* 静的行
* 日付の整列
* 概要データセットからの指標
* 動的ディメンション項目

  フリーフォームテーブルの列ヘッダーにディメンションをドロップすると、動的ディメンション項目が作成され、上位5つのディメンション項目によって列が動的にフィルタリングされます。 Analysis Workspaceでは、これらの上位5つのディメンション項目は、プロジェクトを読み込むたびに更新されます。 テーブルの書き出しでは、これらのディメンション項目は静的になります。 詳しくは、[フリーフォームテーブルの動的ディメンション項目と静的ディメンション項目](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)を参照してください。
* 最初の分類のディメンションは変換され、書き出されたテーブルの行のセカンダリディメンションとして追加されます。 その他の分類は表に含まれていません。
* 並べ替えはほとんどのデータセットではサポートされていません。データは小さなデータセット用に並べ替えられる場合があります。

## サポートされていないコンポーネント

次のコンポーネントはサポートされていないので、Analysis Workspace では、完全なテーブルの書き出しを実行する際に、テーブルから削除するプロンプトが表示されます。

* 指標の定義でサポートされていない関数を使用する計算指標（詳細については、[&#x200B; サポートされていない計算指標の関数](#unsupported-calculated-metric-functions)を参照）
* 管理者によってエクスポートが制限されているコンポーネント（詳細については、*ラベルとポリシー*&#x200B;の「[&#x200B; データガバナンスポリシーに関するセグメント データビュー](/help/data-views/data-governance.md)」セクションを参照）
* 次のすべての条件を満たす任意のディメンション。
   * は、[&#x200B; オブジェクトの配列](/help/use-cases/object-arrays.md)の一部であるフィールドから作成されます（Adobe Analyticsの複数値の変数と同様）。
   * [永続性が有効になっています](/help/data-views/component-settings/persistence.md)。
   * [&#x200B; バインディングディメンション &#x200B;](/help/use-cases/data-views/binding-dimensions-metrics.md)を使用していません。
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

## 計算指標関数のサポート

次の基本セクションと詳細セクションでは、テーブル全体を書き出す際にサポートされる計算指標関数を示します。

### 基本関数のサポート


| 基本関数 | サポート状況 |
|---------|----------|
| 絶対値 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 列の最大値 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 列の最小値 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 列の合計値 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| カウント | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 指数 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 平均 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 中央値 | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| モジュロ | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| パーセンタイル | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 累乗演算子 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 四分位数 | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 行数 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 行の最大値 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 行の最小値 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 行の合計 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 四捨五入 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 平方根 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 標準偏差 | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 平方偏差 | ![StatusBlue](/help/assets/icons/StatusBlue.svg)が予定されています |

### 高度な機能のサポート

#### 代数関数

| 詳細関数 | サポート状況 |
|---------|----------|
| ログベース 10 （指数代数） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 立方根（指数代数） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 自然対数（指数代数） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| Floor （Numeric Adjustment Algebra） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |

#### 論理関数

| 詳細関数 | サポート状況 |
|---------|----------|
| If （ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |

#### ブール関数

| 詳細関数 | サポート状況 |
|---------|----------|
| Not （ブール演算子ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| Or （ブール演算子ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| And （ブール演算子ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |

#### 比較関数

| 詳細関数 | サポート状況 |
|---------|----------|
| より小さい（比較ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 以下（比較ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 等しい（比較ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 以上（比較ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| より大きい（比較ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 等しくない（比較ロジック） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |


#### 三角関数

| 詳細関数 | サポート状況 |
|---------|----------|
| 円周率 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 正弦（標準） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| Cosine （Standard） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 正接（標準） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 円弧 – 正弦（標準） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 円弧コサイン （標準） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 逆正接（標準） | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |

#### 双曲線関数

| 詳細関数 | サポート状況 |
|---------|----------|
| 双曲線余弦 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 双曲線正弦 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |
| 双曲線正接 | ![StatusGreen](/help/assets/icons/StatusGreen.svg)がサポートされています |

#### WASKR関数

| 詳細関数 | サポート状況 |
|---------|----------|
| 信頼性（WASKR） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 信頼性（低）（WASKR） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 信頼性（アッパー）（WASKR） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |

#### 分布関数

| 詳細関数 | サポート状況 |
|---------|----------|
| T スコア（学生T分布） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| T テスト（学生T分布） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| CDF-T （学生T分布） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| Z スコア（正規分布） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| Z検定（正規分布） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| CDF-Z （正規分布） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |

#### 回帰関数

| 詳細関数 | サポート状況 |
|---------|----------|
| 相関係数（指数回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 切片（指数回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 予測Y （指数回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 勾配（指数回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 相関係数（線形回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| インターセプト（線形回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 予測Y （線形回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 傾き（線形回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 相関係数（ログ回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| インターセプト（ログ回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 予測Y （ログ回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 傾き（ログ回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 相関係数（電力回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| インターセプト（電力回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 予測Y （回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 傾き（電力回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 相関係数（二次回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| インターセプト（二次回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 予測Y （二次回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 勾配（二次回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 相関係数（逆回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| インターセプト（逆回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 予測Y （逆回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |
| 傾き（逆回帰） | ![StatusRed](/help/assets/icons/StatusRed.svg)はサポートされていません |

#### その他の高度な関数

| 詳細関数 | サポート状況 |
|---------|----------|
| 個別の概算カウント | ![StatusBlue](/help/assets/icons/StatusBlue.svg)が予定されています |
| 累積 | ![StatusBlue](/help/assets/icons/StatusBlue.svg)が予定されています |
| 累加平均 | ![StatusBlue](/help/assets/icons/StatusBlue.svg)が予定されています |
| 上昇率 | ![StatusBlue](/help/assets/icons/StatusBlue.svg)が予定されています |
| サンプル分散 | ![StatusBlue](/help/assets/icons/StatusBlue.svg)が予定されています |

## アトリビューションの動作

完全なテーブルの書き出しでは、デフォルト以外のアトリビューションモデルを使用する計算指標がサポートされます（[列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)の&#x200B;*デフォルト以外のアトリビューションモデルの使用*&#x200B;の節で説明）。

レポートでデフォルト以外のアトリビューションモデルを使用している場合、レポートに単一ディメンションまたは複数ディメンションがあるかどうかに応じて、レポートで使用されている配分モデルは無視されるか保持されます。

* **単一のディメンションに指標アトリビューションが含まれるレポートの場合：**&#x200B;指標アトリビューションを使用する際に通常行われるように、[指標アトリビューション](/help/data-views/component-settings/attribution.md)は[配分モデル](/help/data-views/component-settings/persistence.md)を上書きします。

  例えば、「ファーストタッチ」指標アトリビューションは、「最新」ディメンション配分を上書きします。

* **複数のディメンションに指標アトリビューションが同時に含まれるレポートの場合：**&#x200B;ディメンション[配分モデル](/help/data-views/component-settings/persistence.md)に加えて[指標アトリビューション](/help/data-views/component-settings/attribution.md)が適用されます。

  例えば、「最新」ディメンション配分に加えて、「ファーストタッチ」指標アトリビューションが適用されます。さらに、指標のアトリビューションは、通常フリーフォームテーブルで行われるように、各ディメンション項目に個別に適用するのではなく、割り当て後のディメンション項目のペアに、単一のディメンション項目であるかのように適用されます。

  >[!NOTE]
  >
  >この記事で説明されているように、複数ディメンションのレポートは、データをクラウドに書き出す場合にのみサポートされます。

## Data Warehouseとの比較

以前に Data Warehouse を使用して Adobe Analytics データを書き出したことがある場合は、次の表が、Customer Journey Analytics で完全なテーブルを書き出す場合と、Adobe Analytics で Data Warehouse を使用してデータを書き出す場合の違いを理解するのに役立ちます。

| 機能 | Customer Journey Analytics での完全なテーブルの書き出し | Adobe Analytics の Data Warehouse |
|---------|----------|---------|
| カスタムレポートを作成 | はい | はい |
| 計算指標 | はい | いいえ |
| セグメント | はい | 制限あり |
| ディメンション | 制限は 10 | 制限なし |
| 指標 | 制限は 10 | 制限なし |
| レポート行 | 階層に応じて、300 万行、3,000 万行、1 億 5,000 万行、3 億行の制限 | 制限なし |
| レポート数 | 制限なし | 制限なし |
| アドホック（1 回限り）配信 | はい | はい |
| 繰り返し配信をスケジュール | はい | はい |
| メール配信 | いいえ | はい |
| FTP／SFTP | いいえ | レガシーサポート |
| Azure | はい | はい |
| Amazon S3 | はい | はい |
| Google Cloud Platform | はい | はい |
| Snowflake | はい | いいえ |
| 配信頻度 | 毎日 | 1 時間ごと |
