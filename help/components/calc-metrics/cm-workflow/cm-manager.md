---
description: 計算指標マネージャーを使用すると、共有、フィルター、タグ付け、承認、コピー、削除およびお気に入りとしてマークできます。
title: 計算指標マネージャー
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: e07197325e992cd85b852899c2f7cef60637f532
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 5%

---

# 計算指標の管理

一元化された [!UICONTROL  計算指標 ] 管理インターフェイスから、計算指標の共有、フィルタリング、タグ付け、承認、名前変更、コピー、削除、書き出し、計算指標をお気に入りとしてマークできます。 計算指標を管理するには：


* メインインターフェイスで **[!UICONTROL コンポーネント]** を選択し、次に **[!UICONTROL 計算指標]** を選択します。


## 計算指標マネージャー

計算指標マネージャーには、次のインターフェイス要素があります。


![ フィルターインターフェイス ](assets/calculated-metrics-manager.png)

### フィルターリスト

フィルターリストには➊、所有している計算指標または共有されているすべての計算指標が表示されます。 リストには次の列があります。

<!-- I think this table incorrectly talks about quick calculated metrics -->

| 列 | 説明 |
| --- | --- | 
| ![ 星の輪郭 ](/help/assets/icons/StarOutline.svg) | 計算指標である ![Star](/help/assets/icons/Star.svg) を優先するか、または ![StarOutline](/help/assets/icons/StarOutline.svg) を優先しないかを選択します。 [ 計算指標をお気に入りとしてマーク ](/help/components/filters/filters-favorite.md) を参照してください。 |
| **[!UICONTROL タイトルと説明]** | 計算指標を編集するには、タイトルリンクを選択して [ 計算指標ビルダー ](cm-build-metrics.md) を開きます。 共有計算指標は、「![ 共有 ](/help/assets/icons/ShareLight.svg) と表示されます。 |
| **[!UICONTROL データビュー]** | この計算指標が適用されるデータビュー。 |
| **[!UICONTROL 所有者]** | 計算指標の所有者。 ユーザーには、自分が所有する注釈または自分と共有されている注釈のみが表示されます。 |
| **[!UICONTROL タグ]** | この計算指標のタグをリストします。 |
| **[!UICONTROL 共有先]** | 計算指標を共有した個人またはグループの数をリストします。 選択して **[!UICONTROL 計算指標を共有]** ダイアログを開きます。 詳しくは、[ 計算指標の共有 ](cm-sharing.md) を参照してください。 |
| **[!UICONTROL 変更日]** | 計算指標が最後に変更された日時。 |
| **[!UICONTROL 使用場所]** | 計算指標が現在使用されている場所と、各領域で使用されている回数を表示します。 <p>例えば、計算指標が 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は [!UICONTROL **42 components**] と表示されます。 <p>この列の値を選択して、計算指標が使用されている場所（例：[!UICONTROL **プロジェクト （40）**]、[!UICONTROL **モバイルスコアカード （2）**]）の分類を確認します。 さらに、計算指標が使用されている項目のリストを表示できます。 例えば、使用されているプロジェクトのリストを表示するには、「[!UICONTROL **プロジェクト （40）**]」リンクを選択します。</p><p>次の各領域には、その領域で使用されている計算指標のインスタンス数が表示されます。</p> <ul><li>[!UICONTROL **プロジェクト**]<p>[ 計算指標ビルダーで作成 ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) された計算指標が含まれ、すべてのプロジェクトで使用できます。</p></li><li>[!UICONTROL **アドホックコンポーネント**]<p>[ クイック計算指標として作成 ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) された計算指標が含まれ、1 つのプロジェクト内でのみ使用できます。</p></li><li>[!UICONTROL **スケジュールされたプロジェクト**]</li><li>[!UICONTROL **モバイルスコアカード**]</li><li>[!UICONTROL **注釈**]</li><li>[!UICONTROL **Report Builder**]<p>このオプションを選択すると、次のデータ列を含む CSV ファイルがダウンロードされます。</p><ul><li>Report Builder名</li><li>最終アクセス日</li><li>最終アクセス日の IMS ユーザー ID</li><li>最終アクセス日のユーザー名</li></ul></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって価値があるかどうか、コンポーネントが使用されている場所、コンポーネントを削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報は、システム管理者のみが使用できます。</li><li>[!UICONTROL **使用**] 列はデフォルトでは表示されません。 この列の表示を構成するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。</li><li>この情報には、API またはData Warehouseからの使用は含まれません。</li><li>この列に特定のコンポーネントに関するデータがないが、そのデータに [!UICONTROL **前回の使用**] 日付が含まれている場合、そのコンポーネントは保存されずに分析で使用された可能性があります。</li><li>使用状況に関する情報は、2023年9月より提供されます。</li></ul><p>この情報と共に [ データ要素 ](/help/components/data-dictionary/data-dictionary-overview.md) を使用すると、組織でコンポーネントがどのように使用されているかを追跡し、よりよく理解できます。</p> |
| **[!UICONTROL 前回の使用]** | 計算指標が最後に使用された日時。 |

{style="table-layout:auto"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

アクションバーの➋を使用して、フィルターに対してアクションを実行できます。 アクションバーには、次のアクションが含まれます。

| アクション | 説明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | [ 計算指標ビルダー ](cm-build-metrics.md) を使用して、別の計算指標を追加します。 |
| ![ 検索 ](/help/assets/icons/Search.svg)[!UICONTROL *タイトルで検索*] | リストで計算指標が選択されていない場合は、この検索フィールドを使用してフィルターを検索します。 |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | 選択した計算指標のタグ付け。 **[!UICONTROL 計算指標をタグ付け]** ダイアログで、選択した計算指標のタグを選択または選択解除します。 「**[!UICONTROL 保存]**」を選択して、選択した計算指標のタグを保存します。 詳しくは、[ 計算指標のタグ付け ](cm-tagging.md) を参照してください。 |
| ![Share](/help/assets/icons/ShareLight.svg) **[!UICONTROL Share]** | 選択した計算指標を共有します。 **[!UICONTROL 計算指標を共有]** ダイアログでは、![ 検索 ](/help/assets/icons/Search.svg)*個人またはグループを検索* または **[!UICONTROL 組織]** または **[!UICONTROL グループ]** を選択できます。 「**[!UICONTROL 保存]**」を選択して、選択した計算指標の共有の詳細を保存します。 詳しくは、[ 計算指標の共有 ](cm-sharing.md) を参照してください。 |
| ![Delete](/help/assets/icons/Delete.svg)**[!UICONTROL Delete]** | 選択した計算指標を削除します。 確認メッセージが表示されます。 |
| ![ 編集 ](/help/assets/icons/Edit.svg) 名前 **[!UICONTROL 変更]** | 選択した 1 つの計算指標の名前を変更します。 選択した場合、計算指標の名前をインラインで変更できます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | 選択した計算指標を承認します。 [ 計算指標の承認 ](cm-approving.md) を参照してください。 |
| ![ コピー ](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]** | 選択した計算指標をコピーします。 同じ名前とサフィックスの `(Copy)` を持つ新しい計算指標が作成されます |
| ![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL CSV への書き出し]** | 計算指標を `Calculated  metric List.csv` ファイルにエクスポートします。 |

### アクティブなフィルターバー

フィルターバー➌には、フィルターパネルから計算指標のリスト（ある場合）に適用されたアクティブなフィルターが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。 複数のフィルターを指定した場合は、「すべて削除 **[!UICONTROL を使用して、すべてのフィルターを削除でき]** す。

### フィルターパネル

左のパネル➍インの ![ フィルター ](/help/assets/icons/Filter.svg)**[!UICONTROL フィルター]** を使用して、計算指標のリストをフィルタリングできます。 フィルターパネルには、フィルターのタイプと、特定のフィルターに従う計算指標の数が表示されます。 ![ フィルター ](/help/assets/icons/Filter.svg) を選択して、フィルターパネルの表示を切り替えます。

詳しくは、[ 計算指標のリストのフィルタリング ](cm-filter.md) を参照してください。


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a filter), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->