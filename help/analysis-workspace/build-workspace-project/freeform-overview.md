---
description: Analysis Workspaceでプロジェクトを操作する方法を説明します。 プロジェクトマネージャーを使用して、プロジェクトの管理（作成、削除、移動、共有、承認、ピン留め、コピー、タグ付け）を行います。
keywords: Analysis Workspace
title: プロジェクトの概要
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 70daf2251576bc3b473e63b3bb7c48f2d16dbffe
workflow-type: tm+mt
source-wordcount: '1638'
ht-degree: 98%

---

# プロジェクトの概要

Workspace プロジェクトでは、パネル、ビジュアライゼーション、コンポーネントを組み合わせて、分析を作成し、組織内の任意のユーザーと共有できます。最初のプロジェクトを開始する前に、プロジェクトへのアクセス方法、プロジェクト間の移動方法、およびプロジェクトの管理方法について説明します。

Customer Journey Analytics のプロジェクトにアクセスするには、「**[!UICONTROL Workspace]**」を選択します。**[!UICONTROL プロジェクト]**&#x200B;マネージャーには、自分が所有するすべてのプロジェクトまたは共有されているプロジェクトが一覧表示されます。環境設定で特に指定しない限り、プロジェクトリストを持つプロジェクトマネージャーにも Customer Journey Analytics のデフォルトのランディングページが表示されます。

![プロジェクトリストを表示するプロジェクトランディングページ](assets/projects.png)


## タイトル領域

タイトル領域内 ➊ から、プロジェクトの作成、フォルダーの作成、環境設定の編集、追加タイルなどのパネルの表示／非表示を行うことができます。

* 左側のパネルの表示／非表示を切り替えて、**[!UICONTROL プロジェクト]**&#x200B;と&#x200B;**[!UICONTROL 学習]**&#x200B;から選択できるようにするには、「![パネル](/help/assets/icons/Rail.svg)」を選択します。
* タイトルにはプロジェクトが表示され、オプションで選択したフォルダーへのパスが追加されます。[!UICONTROL プロジェクト]／**[!UICONTROL 会社フォルダー]**&#x200B;などです。個々のサブフォルダー部分を選択すると、特定のフォルダーに直接移動することができます。
* [**[!UICONTROL 空のプロジェクト]**](create-projects.md)、[**[!UICONTROL 空のモバイルスコアカード]**](/help/mobile-app/create-scorecard.md)、[**[!UICONTROL ガイド付き分析]**](/help/guided-analysis/overview.md)、**[!UICONTROL ドキュメントを開く]**、**[!UICONTROL リリースノートを開く]**&#x200B;の各タイルを表示するには、![ChevronDown](/help/assets/icons/ChevronDown.svg)、**[!UICONTROL 詳細を表示]**&#x200B;の順に選択します。タイルで領域を非表示にするには、![ChevronDown](/help/assets/icons/ChevronDown.svg)、**[!UICONTROL 表示を減らす]**&#x200B;の順に選択します。
* 表示する内容に応じて、[表示セレクター](#show-selector)を使用して、環境設定を編集し、**[!UICONTROL プロジェクト]**&#x200B;に表示されている現在のフォルダーに対するアクションを実行できます。

  | アクション | 説明 |
  |---|---|
  | **[!UICONTROL プロジェクトの作成]** | [新しいプロジェクトを作成](create-projects.md)する場合に選択します。 |
  | **[!UICONTROL フォルダーを作成]** | [新しいフォルダーを作成](workspace-folders/create-folders.md)する場合に選択します。 |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg)、**[!UICONTROL 環境設定を編集]** | すべてのプロジェクトの[環境設定を編集](/help/analysis-workspace/user-preferences.md)します。パンくずリストのスペースが制限される場合、このアクションは![その他](/help/assets/icons/More.svg)サブメニューの一部になります。 |
  | **[!UICONTROL プロジェクトを追加]** | 現在のフォルダーに[プロジェクトを追加](workspace-folders/add-projects.md)する場合に選択します。パンくずリストのスペースが制限される場合、このアクションは![その他](/help/assets/icons/More.svg)サブメニューの一部になります。 |
  | **[!UICONTROL フォルダーの名前を変更]** | 現在のフォルダーの[名前を変更](workspace-folders/manage-folders.md#rename-folders)します。 |
  | **[!UICONTROL フォルダーを移動]** | 現在のフォルダーを[移動](workspace-folders/manage-folders.md#move-folders)します。 |
  | **[!UICONTROL フォルダーを削除]** | 現在のフォルダーを[削除](workspace-folders/manage-folders.md#delete-folders)します。 |




## プロジェクトリスト


プロジェクトリスト ➋ には、自分が所有しているすべてのプロジェクトと、共有されているプロジェクトが表示されます。リストには、次の列があります。

| 列 | 説明 |
| --- | --- | 
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 1 つ以上のプロジェクトを選択すると、プロジェクトインターフェイスの下部に青いアクションバーが表示されます。詳しくは、[アクション](#actions)を参照してください。 |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | プロジェクト「![星](/help/assets/icons/Star.svg)」を優先するか、「![StarOutline](/help/assets/icons/StarOutline.svg)」を優先しないかを選択します。 |
| **[!UICONTROL タイトルと説明]** | プロジェクトを編集するには、タイトルリンクを選択して、[Workspace プロジェクト](/help/analysis-workspace/home.md)を開きます。共有されているプロジェクトには、![共有](/help/assets/icons/ShareAlt.svg)と表示されます。![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、プロジェクトの詳細を含むポップアップメニューが表示されます。![その他](/help/assets/icons/More.svg) を選択すると、アクションを含むコンテキストメニューが開きます。詳しくは、[アクション](#actions)を参照してください。 |
| **[!UICONTROL タイプ]** | Workspace プロジェクト、![FolderUser](/help/assets/icons/FolderUser.svg) フォルダーまたは[モバイルスコアカード](/help/mobile-app/home.md)。 |
| **[!UICONTROL タグ]** | プロジェクトに適用されたタグ。 |
| **[!UICONTROL スケジュール済み]** | プロジェクトが受信者にメールで送信されるようにスケジュールされているかどうか。 オプションは、![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL オン]**&#x200B;または ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL オフ]**&#x200B;です。 [他のユーザーへのプロジェクトデータの送信](/help/analysis-workspace/curate-share/t-schedule-report.md)を参照してください。 |
| **[!UICONTROL 共有リンク（任意のユーザー）]** | Analysis Workspace へのアクセス権を持たない人物を含め、プロジェクトを任意のユーザーと共有するかどうか。オプションは、![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL アクティブ]**&#x200B;または ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 非アクティブ]**&#x200B;です。詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)の[任意のユーザーとのプロジェクトの共有（ログイン不要）](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)を参照してください。 |
| **[!UICONTROL プロジェクトの役割]** | プロジェクトでの自分の役割。オプションは、編集、複製、表示です。詳しくは、[プロジェクトの役割](/help/analysis-workspace/curate-share/curate.md)を参照してください。 |
| **[!UICONTROL データビュー]** | プロジェクトが関連付けられているデータビュー。 |
| **[!UICONTROL 所有者]** | このプロジェクトを作成したユーザー（ユーザー自身、またはユーザー自身とそのプロジェクトを共有した他のユーザー）。 |
| **[!UICONTROL 共有先]** | プロジェクトが共有されているユーザー。 |
| **[!UICONTROL 最終変更日時]** | プロジェクトが最後に変更された日付。 |
| **[!UICONTROL 前回開いた日時]** | プロジェクトが最後に開かれた日時。 |
| **[!UICONTROL プロジェクト ID]** | プロジェクトの ID。 |
| **[!UICONTROL 最長の日付範囲]** | プロジェクト内の任意のパネルまたはビジュアライゼーションの最長の日付範囲。 |
| **[!UICONTROL クエリ数]** | プロジェクトに含まれるクエリの合計数。 |
| **[!UICONTROL 場所]** | プロジェクトが存在するフォルダー。 |

任意の列ヘッダーにポインタを合わせて ![ChevronDown](/help/assets/icons/ChevronDown.svg) を表示し、コンテキストメニューから次の項目を選択します。

* **[!UICONTROL 昇順で並べ替え]**
* **[!UICONTROL 降順で並べ替え]**
* **[!UICONTROL 列をサイズ変更]**。列をサイズ変更するのに役立つ青色の線が表示されます。

### アクション

コンテキストメニューの ![その他](/help/assets/icons/More.svg) または青色のアクションバーを使用して、1 つ以上のプロジェクトに対してアクションを実行できます。

| アイコン | アクション | 説明 |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *個を選択済み]** | 選択したプロジェクトとフォルダーを選択解除し、青色のアクションバーを削除します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 1 つ以上のプロジェクトまたはフォルダーを削除します。確認メッセージが表示されます。 |
| ![共有](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共有]** | プロジェクトを共有します。詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)を参照してください。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | プロジェクトの名前を変更します。**[!UICONTROL 名前変更：*プロジェクト名ダイアログ&#x200B;*]**&#x200B;を開きます。新しい名前を入力し、「**[!UICONTROL 保存&#x200B;]**」を選択します。 |
| ![コピー](/help/assets/icons/Copy.svg) | **[!UICONTROL コピー]** | 1 つ以上のプロジェクトをコピーします。プロジェクトには同じ名前とサフィックスの `(Copy)` が付けられます。 |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL ピン留め]**&#x200B;または&#x200B;**[!UICONTROL ピン留め解除]** | 1 つ以上のプロジェクトまたはフォルダーをピン留めまたはピン留め解除します。ピン留めしたプロジェクトとフォルダーはリストの上部に表示され、指定した並べ替え順序は無視されます。 |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL 上へ移動]** | ピン留めしたプロジェクトまたはフォルダーをプロジェクトリスト内で上に移動します。 |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL 下へ移動]** | ピン留めしたプロジェクトまたはフォルダーをプロジェクトリスト内で下に移動します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 1 つ以上のプロジェクトまたはフォルダーにタグを付けます。1 つ以上のタグを選択するための&#x200B;**[!UICONTROL タグコンポーネント]**&#x200B;ダイアログが表示されます。「**[!UICONTROL 保存]**」を選択して、選択したプロジェクトまたはフォルダーのタグを保存します。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 承認]**&#x200B;または&#x200B;**[!UICONTROL 未承認]** | プロジェクトを承認または未承認にします。管理者のみがプロジェクトを承認できます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV を書き出し]** | 選択したプロジェクトを `Project List.csv` という名前の CSV ファイルに書き出します。 |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL プロジェクトを追加]** | 選択したフォルダーに 1 つ以上のプロジェクトを追加します。**[!UICONTROL プロジェクトを追加]**&#x200B;で、1 つ以上のプロジェクトを選択できます。「**[!UICONTROL 追加]**」を選択して、プロジェクトをフォルダーに追加します。詳しくは、[フォルダーへのプロジェクトの追加](workspace-folders/add-projects.md#from-inside-a-folder)を参照してください。 |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL 移動先]** | 選択した 1 つ以上のプロジェクトをフォルダーに移動します。**[!UICONTROL フォルダーを選択]**&#x200B;で、選択したプロジェクトを移動するフォルダーを選択し、「**[!UICONTROL 移動]**」を選択します。詳しくは、[フォルダーへのプロジェクトの追加](workspace-folders/add-projects.md#from-the-project-list)を参照してください。 |



## 表示セレクター

**[!UICONTROL 表示]**&#x200B;セレクター➌を使用して、プロジェクトインターフェイスのルックアンドフィールを切り替えることができます。**[!UICONTROL 表示]**&#x200B;セレクターでは、[タイトル領域](#title-area)で使用できるオプションと、[プロジェクトリスト](#project-list)に表示される列を定義します。

* [タイトル領域](#title-area)で使用可能なオプションを変更するには、「**[!UICONTROL すべてのプロジェクトを]**&#x200B;**[!UICONTROL 表示]**」または「**[!UICONTROL フォルダーとプロジェクトを]**&#x200B;**[!UICONTROL 表示]**」を選択します。

* [プロジェクトリスト](#project-list)に表示する列を定義するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を選択し、**[!UICONTROL テーブルをカスタマイズ]**&#x200B;ダイアログから列を選択または選択解除します。 「**[!UICONTROL 適用]**」を選択して、カスタマイズを適用します。列について詳しくは、[プロジェクトリスト](#project-list)を参照してください。

## フィルターパネル

フィルターパネル ➍ を使用して、[プロジェクトリスト](#project-list)のプロジェクトとフォルダーをフィルタリングできます。フィルターパネルを表示または非表示にするには、![フィルター](/help/assets/icons/Filter.svg) を使用します。

フィルターパネルは、次のセクションで構成されています。

### タグ

| タグ | 説明 |
|---|---|
| ![タグ](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | 「**[!UICONTROL タグ]**」セクションでは、タグでフィルタリングできます。 <ul><li>フィルタリングに使用するタグを検索するには、![検索](/help/assets/icons/Search.svg) *タグを検索*&#x200B;を使用します。</li><li>複数のタグを選択できます。使用できるタグは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**2︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できるタグ数。</li><li>7︎⃣：特定のタグに関連付けられているプロジェクト数。</li></ul></li></ul> |


### データビュー

| データビュー | 説明 |
|---|---|
| ![データビュー](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | 「**[!UICONTROL データビュー]**」セクションでは、データビューでフィルタリングできます。 <ul><li>フィルタリングに使用するデータビューを検索するには、![検索](/help/assets/icons/Search.svg) *データビューを検索*&#x200B;を使用します。</li><li>複数のデータビューを選択できます。使用できるデータビューは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**3︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できるデータビュー数。</li><li>4︎⃣：特定のデータビューに関連付けられているプロジェクト数。</li></ul></li></ul> |


### 所有者

| 所有者 | 説明 |
|---|---|
| ![所有者](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | 「**[!UICONTROL 所有者]**」セクションでは、所有者でフィルタリングできます。 <ul><li>フィルタリングに使用する所有者を検索するには、![検索](/help/assets/icons/Search.svg) *所有者を検索*&#x200B;を使用します。</li><li>複数の所有者を選択できます。使用できる所有者は、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**3︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できる所有者数。</li><li>4︎⃣：特定の所有者に関連付けられているプロジェクト数。</li></ul></li></ul> |


### タイプ

| タイプ | 説明 |
|---|---|
| ![タイプ](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | 「**[!UICONTROL タイプ]**」セクションでは、プロジェクトやフォルダーのタイプでフィルタリングできます。<ul><li>次のオプションから 1 つ以上を選択できます。<ul><li> **[!UICONTROL フォルダー]**</li><li>**[!UICONTROL ワークスペースプロジェクト]**</li><li>**[!UICONTROL モバイルスコアカード]**</li></ul> <li>複数のフィルターを選択できます。使用できるその他のフィルターは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**5︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できるその他のフィルター数。</li><li>4︎⃣：特定のその他のフィルターに関連付けられているプロジェクト数。</li></ul></li></ul> |


### その他のフィルター

| その他のフィルター | 説明 |
|---|---|
| ![その他のフィルター](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} | 「**[!UICONTROL その他のフィルター]**」セクションでは、他の定義済みフィルターでフィルタリングできます。<ul><li>次のオプションから 1 つ以上を選択できます。<ul><li> **[!UICONTROL すべてを表示]**</li><li>**[!UICONTROL 自分と共有済み]**</li><li>**[!UICONTROL 自分が所有]**</li><li>**[!UICONTROL 承認済み]**</li><li>**[!UICONTROL お気に入り]**</li></ul> 選択できる内容は、役割と権限によって異なります。</li><li>複数のフィルターを選択できます。使用できるその他のフィルターは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**5︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できるその他のフィルター数。</li><li>4︎⃣：特定のその他のフィルターに関連付けられているプロジェクト数。</li></ul></li></ul> |

## 検索

「![検索](/help/assets/icons/Search.svg)」フィールドを使用してプロジェクトとフォルダーを検索するには、検索領域 ➎ を使用します。入力を開始すると、[プロジェクトリスト](#project-list)が検索入力に基づいて自動的にフィルタリングされます。

また、検索領域には、フィルターパネルから適用されたフィルターも表示されます。

* フィルターを削除するには、フィルターで ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択します。
* すべてのフィルターを削除するには、「すべてクリア」を選択します。

個々のフィルターを表示するスペースが制限されている場合は、「**[!UICONTROL *x* 個のフィルターでセグメント化]**」と表示されます。

* フィルターを削除するには：

   1. **[!UICONTROL *x *個のフィルター]**![ChevronDown](/help/assets/icons/ChevronDown.svg) を使用して、フィルターのタイプと個々のフィルターを一覧表示するコンテキストメニューを開きます。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用して、タグを削除します。


<!--

The Projects page contains the following information: 

>[!NOTE]
>
>Some columns are not displayed by default. To customize the columns you see, click the **Customize table** icon ![Customize table](assets/projects-page-customize-columns-icon.png).

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch.  |
|  Show more  |Reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=ja), or [viewing release notes](/help/release-notes/latest.md).  |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  Customize table (icon)  | Allows you to customize the information that shows for each project on the Projects page.  |
|  Name  | Name of the Workspace project.  |
| Type | Indicates whether this is a Workspace Project, a folder, or a [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=ja). |
|  Tags  |Tags that were applied to the project.  |
| Scheduled | Indicates whether projects are scheduled to be emailed to recipients on a schedule. See [Send project data to others](/help/analysis-workspace/export/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone--even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analysis-workspace/curate-share/share-projects.md) for more information. |
| Data view | The data view that the project is associated with. |
| [Project Role](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja) | Indicates your role for the project - owners, edit, duplicate, view. |
|  Owner  | The person who created this project (either you or someone who shared the project with you.)  |
|  Shared with  | Users that the project has been shared with.  |
|  Last Modified  | Date and time when the project was last modified.  |
|  Last Opened  | Date and time when the project was last opened.  |
|  Project ID  | The ID of the project.  |
|  Longest Date Range  | The longest date range of the project.  |
|  Number of Queries  | The total number of queries contained in the project.  |
|  Location  | The folder where the project resides.  |

## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. Each menu option can also be accessed by keyboard [shortcuts](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![New Project options including the Project, Edit, Insert, Components, Share, and Help options.](assets/menu.png)

|  Menu item  | Description  |
|---|---|
|  Project  | Includes common actions for project management, including New, Open, Save, and Save As. You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download project data](/help/analysis-workspace/export/download-send.md) options enable you to export data from Workspace. **Project Info & Settings** (see below) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All will reset your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left panel.  |
|  [Components](/help/components/overview.md)  | Create new segments, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
|  [Share](/help/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ja). Manage the visibility of Workspace tips as well as the [debugger](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/apis/using-analysis-workspace-to-build-api-2-requests). Find details about Workspace and factors that impact project [performance](/help/technotes/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you will see the project owner's name. |

### Project Info & Settings {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** provides project-level information on the currently active project.

![The Project Info & Settings window.](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Created By  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances in project  | Specifies whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |

## Left panel

Within a project, various icons are available in the left panel, and each represents important parts of a project:

* [Panels](/help/analysis-workspace/c-panels/panels.md) ![panels icon](assets/panels-icon.png)

* [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualizations icon](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components icon](assets/components-icon.png)

* [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md)![data dictionary icon](assets/data-dictionary-icon.png)

* [Table of contents](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![toc icon](assets/toc-icon.png)

Components (Dimensions, Metrics, Segments, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

![The components relating to the active panel data view for Cross-Industry Demo Data data view.](assets/left-rail.png)

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case. The active panel will have a blue border around it, and determines what components are available in the left panel.

Depending on the starting point you chose for your projects, you will either have a [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data will automatically be rendered for you. [Learn more](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage our [training tutorial](/help/analysis-workspace/home.md) for more guidance on building your first project.

![A Freeform Table for the project.](assets/canvas.png)

## Project Manager {#manager}

Analysis Workspace projects can be managed under **Analytics > Components >  Projects**. The Project Manager shows the projects that a specific user created. You can transfer project ownership to a new user under Admin > Analytics Users & Assets > Transfer Assets.

In Projects Manager, you can add, tag, share, duplicate/copy, and more. Search for a project in the search bar or by using the filter options in the left panel. You can filter by tag, owners, project type and more.

![Project Manager Tags search field and Title search field.](assets/project-manager.png)

The following are common actions in the Projects manager, and can be taken on one or many projects at once:

|  Action  | Description  |
|---|---|
|  Add  | Create a new project from scratch.  |
|  Tag or Approve  | Choose "Tag" or "Approve" to organize your projects and make them easier to search for.  |
|  [Share](/help/analysis-workspace/curate-share/share-projects.md)  | Make a project available to other Analysis Workspace users in your organization.  |
|  Delete  | Delete your project.  |
|  Rename  | Edit the name of your project.  |
|  Copy  | Create a duplicate copy of your project. This creates a new project and project ID. Any shares or schedules tied to the original project will not be copied. |
|  Export to CSV  | Download your project as a CSV file, which includes plain-text data.  |

-->

