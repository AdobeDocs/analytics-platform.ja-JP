---
title: フィルターの管理
description: Customer Journey Analyticsでフィルターを管理する方法を学ぶ
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 4%

---

# フィルターの管理


中央の [ フィルター ](filters-favorite.md) 管理インターフェイスから、](filters-share.md) 共有 [、](filters-tag.md) フィルター ](filters-filter.md)、[ タグ ]、[ 承認 ](filters-approve.md)、名前変更、[ コピー ](filters-copy.md)、削除、フィルターの書き出し、[ お気に入りとしてマークできます [!UICONTROL 。 フィルターを管理するには：

* メインインターフェイスで **[!UICONTROL コンポーネント]** を選択し、「**[!UICONTROL フィルター]**」を選択します。


>[!NOTE]
>
>特定のWorkspace プロジェクト内で作成したクイックフィルターは、すべてのプロジェクトでフィルターを使用できるように設定していない限り、[!UICONTROL  フィルター ] マネージャーに表示されません。
>

## フィルターマネージャー

フィルターマネージャーには、次のインターフェイス要素があります。

![ フィルターインターフェイス ](assets/filters-manager.png)

### フィルターリスト

このフィルターリストには、所有するすべてのフィルター、すべてのプロジェクトを対象としたフィルター、自分と共有されているフィルターが➊表示されます。 リストには次の列があります。

| 列 | 説明 |
| --- | --- | 
| ![ 星の輪郭 ](/help/assets/icons/StarOutline.svg) | フィルターの ![ 星 ](/help/assets/icons/Star.svg) を優先するか、![ 星のアウトライン ](/help/assets/icons/StarOutline.svg) を優先しないかを選択します。 [ フィルターをお気に入りとしてマーク ](/help/components/filters/filters-favorite.md) を参照してください。 |
| **[!UICONTROL タイトルと説明]** | フィルターを編集するには、タイトルリンクを選択して [ フィルタービルダー ](filter-builder.md) を開きます。 共有フィルターには「![ 共有 ](/help/assets/icons/ShareAlt.svg) と表示されます。 |
| **[!UICONTROL データビュー]** | このフィルターを適用するデータビュー。 |
| **[!UICONTROL 所有者]** | フィルターの所有者。 ユーザーには、自分が所有するフィルターまたは自分と共有されている注釈のみが表示されます。 |
| **[!UICONTROL タグ]** | このフィルターのタグ。 |
| **[!UICONTROL 共有先]** | フィルターを共有した個人またはグループの数。 選択して、「**[!UICONTROL コンポーネントを共有]** ダイアログを開きます。 詳しくは、[ フィルターの共有 ](filters-share.md) を参照してください。 |
| **[!UICONTROL 変更日]** | フィルターが最後に変更された日時。 |
| **[!UICONTROL 使用場所]** | フィルターが現在使用されている場所と、各領域で使用されている回数を表示します。 <p>例えば、フィルターが 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は [!UICONTROL **42 components**] と表示されます。</p> <p>この列の値を選択して、フィルターが使用されている場所（例：[!UICONTROL **プロジェクト （40）**]、[!UICONTROL **モバイルスコアカード （2）**]）の分類を確認します。 さらに、フィルターが使用されている項目のリストを表示できます。 例えば、使用されているプロジェクトのリストを表示するには、「[!UICONTROL **プロジェクト （40）**]」リンクを選択します。</p><p>次の各領域には、その領域で使用されているフィルターのインスタンス数が表示されます。</p>  <ul><li>[!UICONTROL **プロジェクト**]<p>[ フィルタービルダーで作成 ](/help/components/filters/filter-builder.md#) されたフィルターを含み、すべてのプロジェクトで使用できます。</p></li><li>[!UICONTROL **アドホックコンポーネント**]<p>[ クイックフィルターとして作成 ](/help/components/filters/quick-filters.md) されたフィルターを含み、1 つのプロジェクト内でのみ使用できます。</p></li><li>[!UICONTROL **スケジュールされたプロジェクト**]</li><li>[!UICONTROL **モバイルスコアカード**]</li><li>[!UICONTROL **注釈**]</li><li>[!UICONTROL **計算指標**]</li><li>[!UICONTROL **Report Builder**]<p>このオプションを選択すると、次のデータ列を含む CSV ファイルがダウンロードされます。</p><ul><li>Report Builder名</li><li>最終アクセス日</li><li>最終アクセス日の IMS ユーザー ID</li><li>最終アクセス日のユーザー名</li></ul></li></ul><p>この情報を使用すると、組織内のユーザーにとってコンポーネントが価値があるかどうか、コンポーネントが使用されている場所、コンポーネントを削除または変更する必要があるかどうかを判断できます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報は、システム管理者のみが使用できます。</li><li>[!UICONTROL **使用**] 列はデフォルトでは表示されません。 この列の表示を構成するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。</li><li>この情報には、API またはData Warehouseからの使用は含まれません。</li><li>特定のコンポーネントのこの列にデータがないが、そのコンポーネントに [!UICONTROL **最終使用日**] がある場合、そのコンポーネントは保存されずに分析で使用された可能性があります。</li><li>使用状況に関する情報は、2023年9月より提供されます。</li></ul><p>この情報と共に [ データ要素 ](/help/components/data-dictionary/data-dictionary-overview.md) を使用すると、組織でコンポーネントがどのように使用されているかを追跡し、よりよく理解できます。</p> |
| **[!UICONTROL 前回の使用]** | フィルターが最後に使用された日時。 |

{style="table-layout:auto"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

アクションバーの➋を使用して、フィルターに対してアクションを実行できます。 アクションバーには、次のアクションが含まれます。

| アクション | 説明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | [ フィルタービルダー ](filter-builder.md) を使用して、別のフィルターを追加します。 |
| ![ 検索 ](/help/assets/icons/Search.svg)[!UICONTROL *タイトルで検索*] | リストでフィルターが選択されていない場合、この検索フィールドを使用してフィルターを検索します。 |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | 選択したフィルターにタグを付けます。 **[!UICONTROL タグフィルター]** ダイアログで、選択したフィルターのタグを選択または選択解除します。 「**[!UICONTROL 保存]**」を選択して、選択したフィルターのタグを保存します。 詳しくは、[ タグフィルター ](/help/components/filters/filters-tag.md) を参照してください。 |
| ![Share](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | 選択したフィルターを共有します。 **[!UICONTROL フィルターを共有]** ダイアログでは、![ 検索 ](/help/assets/icons/Search.svg)*個人またはグループを検索* または **[!UICONTROL 組織]** または **[!UICONTROL グループ]** を選択できます。 「**[!UICONTROL 保存]**」を選択して、選択したフィルターの共有の詳細を保存します。 詳しくは、[ フィルターの共有 ](filters-share.md) を参照してください。 |
| ![Delete](/help/assets/icons/Delete.svg)**[!UICONTROL Delete]** | 選択したフィルターを削除します。 確認メッセージが表示されます。 |
| ![ 編集 ](/help/assets/icons/Edit.svg) 名前 **[!UICONTROL 変更]** | 選択した 1 つのフィルターの名前を変更します。 選択した場合、フィルターの名前をインラインで変更できます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | 選択したフィルターを承認します。 詳しくは、[ フィルターを承認 ](filters-approve.md) を参照してください。 |
| ![ コピー ](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]** | 選択したフィルターをコピーします。 新しいフィルターは、同じ名前とサフィックス `(Copy)` で作成されます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL CSV への書き出し]** | フィルターを `Filters List.csv` ファイルに書き出します。 |

### アクティブなフィルターバー

フィルターバー➌には、フィルターパネルからフィルターのリスト（ある場合）に適用されたアクティブなフィルターが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。 複数のフィルターを指定した場合は、「すべて削除 **[!UICONTROL を使用して、すべてのフィルターを削除でき]** す。

### フィルターパネル

左のパネル➍インの ![ フィルター ](/help/assets/icons/Filter.svg)**[!UICONTROL フィルター]** を使用して、フィルターのリストをフィルタリングできます。 フィルターパネルには、フィルターのタイプと、特定のフィルターに従うフィルターの数が表示されます。 ![ フィルター ](/help/assets/icons/Filter.svg) を選択して、フィルターパネルの表示を切り替えます。

詳しくは、[ フィルターのリストのフィルタリング ](filters-filter.md) を参照してください。
