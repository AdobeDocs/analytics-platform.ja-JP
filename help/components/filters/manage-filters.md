---
title: フィルターの管理
description: Customer Journey Analytics でのフィルターの管理方法について説明します
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: ht
source-wordcount: '884'
ht-degree: 100%

---

# フィルターの管理


中央の[!UICONTROL フィルター]管理インターフェイスから、[共有](filters-share.md)、[フィルター](filters-filter.md)、[タグ](filters-tag.md)、[承認](filters-approve.md)、名前変更、[コピー](filters-copy.md)、削除、フィルターの書き出し、[お気に入り](filters-favorite.md)としてフィルターをマークできます。フィルターを管理するには、以下の手順に従います。

* メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL フィルター]**」を選択します。


>[!NOTE]
>
>特定の Workspace プロジェクト内で作成したフィルターは、すべてのプロジェクトでフィルターを使用できるように設定していない限り、[!UICONTROL フィルター]マネージャーに表示されません。
>

## フィルターマネージャー

フィルターマネージャーには、次のインターフェイス要素があります。

![フィルターインターフェイス](assets/filters-manager.png)

### フィルターリスト

フィルターリスト ➊ には、所有するすべてのフィルター、すべてのプロジェクトを対象とするフィルター、および自身と共有されているフィルターが表示されます。リストには、次の列があります。

| 列 | 説明 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | フィルター「![星](/help/assets/icons/Star.svg)」を優先するか、「![StarOutline](/help/assets/icons/StarOutline.svg)」を優先しないかを選択します。[フィルターをお気に入りとしてマーク](/help/components/filters/filters-favorite.md)を参照してください。 |
| **[!UICONTROL タイトルと説明]** | フィルターを編集するには、タイトルリンクを選択して、[フィルタービルダー](filter-builder.md)を開きます。共有フィルターには、「![共有](/help/assets/icons/ShareAlt.svg)」と表示されます。 |
| **[!UICONTROL データビュー]** | このフィルターが適用されるデータビュー。 |
| **[!UICONTROL 所有者]** | フィルターの所有者。ユーザーには、自分が所有しているフィルターまたは自分と共有されているフィルターのみが表示されます。 |
| **[!UICONTROL タグ]** | このフィルターのタグ。 |
| **[!UICONTROL 共有先]** | フィルターを共有した個人またはグループの数。選択して、**[!UICONTROL コンポーネントを共有]**&#x200B;ダイアログを開きます。詳しくは、[フィルターの共有](filters-share.md)を参照してください。 |
| **[!UICONTROL 変更日時]** | フィルターが最後に修正された日時。 |
| **[!UICONTROL 使用場所]** | フィルターが現在使用されている場所と、各領域で使用されている回数を表示します。 <p>例えば、フィルターが 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は [!UICONTROL **42 コンポーネント**]&#x200B;と表示されます。</p> <p>この列の値を選択して、フィルターが使用されている場所（例：[!UICONTROL **プロジェクト（40）**]、[!UICONTROL **モバイルスコアカード（2）**]）の分類を確認します。さらに、フィルターが使用されている項目のリストを表示できます。例えば、使用されているプロジェクトのリストを表示するには、[!UICONTROL **プロジェクト（40）**]&#x200B;リンクを選択します。</p><p>次の各領域には、その領域で使用されているフィルターのインスタンス数が表示されます。</p>  <ul><li>[!UICONTROL **プロジェクト**]<p>[フィルタービルダーで作成](/help/components/filters/filter-builder.md#)されたフィルターを含み、すべてのプロジェクトで使用できます。</p></li><li>[!UICONTROL **アドホックコンポーネント**]<p>[クイックフィルターとして作成](/help/components/filters/quick-filters.md)されたフィルターを含み、1 つのプロジェクト内でのみ使用できます。</p></li><li>[!UICONTROL **スケジュールされたプロジェクト**]</li><li>[!UICONTROL **モバイルスコアカード**]</li><li>[!UICONTROL **注釈**]</li><li>[!UICONTROL **計算指標**]</li><li>[!UICONTROL **Report Builder**]<p>このオプションを選択すると、次のデータ列を含む CSV ファイルがダウンロードされます。</p><ul><li>Report Builder 名</li><li>前回のアクセス</li><li>最後にアクセスした IMS ユーザー ID</li><li>前回アクセスしたユーザー名</li></ul></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報は、システム管理者のみが使用できます。</li><li>[!UICONTROL **使用**]&#x200B;列はデフォルトでは表示されません。この列の表示を構成するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。</li><li>この情報には、API またはデータウェアハウスからの使用は含まれません。</li><li>特定のコンポーネントのこの列にデータがないが、そのコンポーネントに&#x200B;[!UICONTROL **最終使用**]&#x200B;がある場合、そのコンポーネントは保存されずに分析で使用された可能性があります。</li><li>使用状況に関する情報は、2023年9月より提供されます。</li></ul><p>この情報と共に[データ辞書](/help/components/data-dictionary/data-dictionary-overview.md)を使用すると、組織内でのコンポーネントの使用方法を追跡し、より深く理解することができます。</p> |
| **[!UICONTROL 前回の使用]** | フィルターが最後に使用された日時。 |

{style="table-layout:auto"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

アクションバー ➋ を使用して、フィルターへのアクションを実行できます。アクションバーには、次のアクションが含まれます。

| アクション | 説明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | [フィルタービルダー](filter-builder.md)を使用して、別のフィルターを追加します。 |
| ![検索](/help/assets/icons/Search.svg)[!UICONTROL *タイトルで検索*] | リストでフィルターが選択されていない場合は、この検索フィールドを使用してフィルターを検索します。 |
| ![ラベル](/help/assets/icons/Label.svg)、**[!UICONTROL タグ]** | 選択したフィルターにタグを付けます。**[!UICONTROL タグフィルター]**&#x200B;ダイアログで、選択したフィルターのタグを選択または選択解除します。「**[!UICONTROL 保存]**」を選択して、選択したフィルターのタグを保存します。詳しくは、[タグフィルター](/help/components/filters/filters-tag.md)を参照してください。 |
| ![共有](/help/assets/icons/ShareAlt.svg)、**[!UICONTROL 共有]** | 選択したフィルターを共有します。**[!UICONTROL フィルターを共有]**&#x200B;ダイアログでは、「![検索](/help/assets/icons/Search.svg)」、「*個人またはグループを検索*」、または「**[!UICONTROL 組織]**」または「**[!UICONTROL グループ]**」を選択できます。「**[!UICONTROL 保存]**」を選択して、選択したフィルターの共有の詳細を保存します。詳しくは、[フィルターを共有](filters-share.md)を参照してください。 |
| ![削除](/help/assets/icons/Delete.svg)、**[!UICONTROL 削除]** | 選択したフィルターを削除します。確認メッセージが表示されます。 |
| ![編集](/help/assets/icons/Edit.svg)**[!UICONTROL 名前を変更]** | 選択した 1 つのフィルターの名前を変更します。選択すると、フィルターの名前をインラインで変更できます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 承認]** | 選択したフィルターを承認します。詳しくは、[フィルターの承認](filters-approve.md)を参照してください。 |
| ![コピー](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]** | 選択したフィルターをコピーします。同じ名前とサフィックスを持つ新しいフィルターが作成されます `(Copy)`。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV に書き出し]** | フィルターを `Filters List.csv` ファイルに書き出します。 |

### アクティブなフィルターバー

フィルターバー ➌ には、フィルターパネルからフィルターのリスト（ある場合）に適用されたアクティブなフィルターが表示されます。![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。複数のフィルターを指定した場合は、「**[!UICONTROL すべて削除]**」を使用すると、すべてのフィルターを削除できます。

### フィルターパネル

左のパネル ➍ の![フィルター](/help/assets/icons/Filter.svg)**[!UICONTROL フィルター]**&#x200B;を使用して、フィルターのリストをフィルタリングできます。フィルターパネルには、フィルターのタイプと、特定のフィルターを適用するフィルターの数が表示されます。「![フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターパネルの表示を切り替えます。

詳しくは、[フィルターのリストのフィルタリング](filters-filter.md)を参照してください。
