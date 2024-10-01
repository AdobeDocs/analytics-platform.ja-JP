---
title: 注釈を管理
description: ワークスペースでの注釈を管理する方法。
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 6%

---

# 注釈を管理

一元的な [!UICONTROL  注釈 ] 管理インターフェイスから、共有、フィルター、タグ付け、承認、コピー、削除および注釈をお気に入りとしてマークできます。 注釈を管理するには：

* メインインターフェイスで **[!UICONTROL コンポーネント]** を選択し、「**[!UICONTROL 注釈]**」を選択します。


>[!NOTE]
>
>特定のWorkspace プロジェクト内で作成した注釈は、すべてのプロジェクトで注釈を使用できるように設定していない限り、[!UICONTROL  注釈 ] マネージャーに表示されません。
>

## 注釈マネージャー

注釈マネージャーには、次のインターフェイス要素があります。

![ 注釈インターフェイス ](assets/annotations-manager.png)

### 注釈リスト

注釈リストに➊は、所有するすべての注釈、すべてのプロジェクトを対象とした注釈、自分と共有されている注釈が表示されます。 リストには次の列があります。

| 列 | 説明 |
| --- | --- | 
| ![ 星の輪郭 ](/help/assets/icons/StarOutline.svg) | 注釈を ![ 星 ](/help/assets/icons/Star.svg) または ![ 星の輪郭 ](/help/assets/icons/StarOutline.svg) に変更します。 |
| **[!UICONTROL タイトルと説明]** | 注釈ビルダーで提供されます。タイトルと説明を編集するには、タイトルリンクを選択して [ 注釈ビルダー ](/help/components/annotations/create-annotations.md#annotation-builder) を開きます。 共有注釈には、「![ 共有 ](/help/assets/icons/ShareAlt.svg) と表示されます。 |
| **[!UICONTROL データビュー]** | この注釈が適用されるデータビュー。 |
| **[!UICONTROL 所有者]** | 注釈の所有者。 ユーザーには、自分が所有する注釈または自分と共有されている注釈のみが表示されます。 |
| **[!UICONTROL 適用された日付範囲]** | この注釈が適用される日付または日付範囲。 |
| **[!UICONTROL タグ]** | この注釈のタグ。 |
| **[!UICONTROL 共有先]** | 注釈を共有した個人またはグループ。 選択して、「**[!UICONTROL コンポーネントを共有]** ダイアログを開きます。 |
| **[!UICONTROL 変更日]** | 注釈が最後に変更された日時を表示します。 |

{style="table-layout:auto"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

注釈に対するアクションは、アクションバーの➋を使用して実行できます。 アクションバーには、次のアクションが含まれます。

| アクション | 説明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | [ 注釈ビルダー ](create-annotations.md#annotation-builder) を使用して、別の注釈を追加します。 |
| ![ 検索 ](/help/assets/icons/Search.svg)[!UICONTROL *タイトルで検索*] | リストで注釈が選択されていない場合は、この検索フィールドを使用して注釈を検索します。 |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | 選択した注釈にタグを付けます。 **[!UICONTROL タグコンポーネント]** ダイアログで、選択した注釈のタグを選択または選択解除します。 「**[!UICONTROL 保存]**」を選択して、選択した注釈のタグを保存します。 |
| ![Share](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | 選択した注釈を共有します。 **[!UICONTROL コンポーネントを共有]** ダイアログでは、![ 検索 ](/help/assets/icons/Search.svg)*個人またはグループを検索* または **[!UICONTROL 組織]** または **[!UICONTROL グループ]** を選択できます。 「**[!UICONTROL 保存]**」を選択して、選択した注釈の共有の詳細を保存します。 詳しくは、[ 注釈を共有 ](#share-annotations) を参照してください。 |
| ![Delete](/help/assets/icons/Delete.svg)**[!UICONTROL Delete]** | 選択した注釈を削除します。 確認メッセージが表示されます。 |
| ![ 編集 ](/help/assets/icons/Edit.svg) 名前 **[!UICONTROL 変更]** | 選択した 1 つの注釈の名前を変更します。 選択すると、注釈の名前をインラインで変更できます。 |
| ![ コピー ](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]** | 選択した注釈をコピーします。 同じ名前とサフィックスを持つ新しい注釈が作成されます（コピー） |
| ![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL CSV への書き出し]** | 注釈を `Annotations List.csv` ファイルに書き出します。 |

### アクティブなフィルターバー

フィルターバー➌には、アクティブなフィルター（存在する場合）が表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。 複数のフィルターを指定した場合は、「すべて削除 **[!UICONTROL を使用して、すべてのフィルターを削除でき]** す。

### フィルターパネル

注釈は、左パネルの「**[!UICONTROL フィルター]**➍を使用してフィルタリングできます。 フィルターパネルには、フィルターのタイプと、フィルターに従う注釈の数が表示されます。 ![ フィルター ](/help/assets/icons/Filter.svg) を選択して、フィルターパネルの表示を切り替えます。

フィルターのリストをフィルタリングするには：

1. ![ フィルター ](/help/assets/icons/Filter.svg) を選択して、フィルターパネルを開きます。 「フィルター」リストにスペースが必要な場合は、もう一度 ![ フィルター ](/help/assets/icons/Filter.svg) を選択してパネルを閉じることができます。
1. 使用可能な任意の [ フィルターセクション ](#filter-sections) を使用して、注釈をフィルタリングできます。

   >[!INFO]
   >
   >*項目* [ 注釈リスト ](manage-annotations.md#annotations-list) に表示される注釈項目を参照します。
   > 

#### フィルターセクション

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


[ 注釈リスト ](manage-annotations.md#annotations-list) は、フィルター設定に基づいて自動的に更新されます。 設定済みのフィルターは、「アクティブなフィルターバー [ に表示さ ](manage-annotations.md#active-filter-bar) ます。


## 注釈を編集

注釈は、次の 2 つの方法で編集できます。

* Workspace プロジェクトでは、「[ コンポーネント情報 ](/help/components/use-components-in-workspace.md#component-info) アイコンを使用します。

* [[!UICONTROL  注釈 ] リスト ](#annotations-list) で、注釈のタイトルを選択します。

注釈を編集するには、[ 注釈ビルダー ](/help/components/annotations/create-annotations.md#annotation-builder) を使用します。

## 注釈の共有

注釈を共有する場合や、自分と共有されている注釈を操作する場合は、次の操作が適用されます。

* 他のユーザーと共有するプロジェクト内のプロジェクトのみの注釈は、それらのユーザーに対して表示されます。 ユーザーは、これらのプロジェクトのみの注釈を編集または削除できません。
* 注釈を保存してユーザーと直接注釈を共有する場合、そのユーザーは、管理者権限を持っている場合にのみ、注釈を編集および削除できます。

* プロジェクトが共有されている場合、そのプロジェクトで作成された注釈は、そのプロジェクトでのみ表示されます。 注釈を直接共有すると、その注釈を表示できるすべてのプロジェクトに注釈が表示されます。

## 注釈とタイムゾーン

すべての注釈は、タイムスタンプを使用して作成されますが、時間やタイムゾーンの情報は含まれません。 レポート時には、パネルに設定されたデータビューのタイムゾーンが使用されます。
