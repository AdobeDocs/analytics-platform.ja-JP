---
title: セグメントの管理
description: Customer Journey Analyticsでセグメントを管理する方法について説明します
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 34%

---

# セグメントの管理


中央の [ セグメント ](seg-favorite.md) 管理インターフェイスから、(seg-share.md) 共有 [、](seg-tag.md) セグメント [&#128279;](seg-filter.md)、[ タグ ]、[ 承認 ](seg-approve.md)、名前変更、[ コピー ](seg-copy.md)、セグメントの削除、書き出し、およびセグメントを  お気に入りとしてマークできます 。 セグメントを管理するには：

* メインインターフェイスで **[!UICONTROL コンポーネント]** を選択し、**[!UICONTROL セグメント]** を選択します。


>[!NOTE]
>
>特定のWorkspace プロジェクト内で作成したクイックセグメントは、すべてのプロジェクトでセグメントを使用できるように設定しない限り、[!UICONTROL &#x200B; セグメント &#x200B;] マネージャーに表示されません。
>

## セグメントマネージャー

セグメントマネージャーには次のインターフェイス要素があります。

![ セグメントインターフェイス ](assets/filters-manager.png)

### セグメントリスト

セグメントリスト ➊ は、所有するすべてのセグメント、すべてのプロジェクトを対象としているセグメント、自分と共有されているセグメントが表示されます。 リストには、次の列があります。

| 列 | 説明 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | セグメントの ![ 星 ](/help/assets/icons/Star.svg) または ![ 星のアウトライン ](/help/assets/icons/StarOutline.svg) を優先するかどうかを選択します。 詳しくは、[ セグメントをお気に入りとしてマーク ](/help/components/segments/seg-favorite.md) を参照してください。 |
| **[!UICONTROL タイトルと説明]** | セグメントを編集するには、タイトルリンクを選択して [ セグメントビルダー ](seg-builder.md) を開きます。 共有セグメントは「![ 共有 ](/help/assets/icons/ShareAlt.svg)」で示されます。 |
| **[!UICONTROL データビュー]** | このセグメントが適用されるデータビュー。 |
| **[!UICONTROL 所有者]** | セグメントの所有者。 ユーザーには、自分が所有するセグメントまたは自分と共有されている注釈のみが表示されます。 |
| **[!UICONTROL タグ]** | このセグメントのタグ。 |
| **[!UICONTROL 共有先]** | セグメントを共有した個人またはグループの数。 選択して、**[!UICONTROL コンポーネントを共有]**&#x200B;ダイアログを開きます。詳しくは、[ セグメントの共有 ](seg-share.md) を参照してください。 |
| **[!UICONTROL 変更日時]** | セグメントが最後に変更された日時。 |
| **[!UICONTROL 使用場所]** | セグメントが現在使用されている場所と、各領域で使用されている回数を表示します。 <p>例えば、セグメントが 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は [!UICONTROL **42 components**] と表示されます。</p> <p>この列の値を選択すると、セグメントが使用されている場所（例：[!UICONTROL **プロジェクト （40）**]、[!UICONTROL **モバイルスコアカード （2）**]）の分類が表示されます。 さらに、セグメントが使用されている項目のリストを表示できます。 例えば、使用されているプロジェクトのリストを表示するには、[!UICONTROL **プロジェクト（40）**]&#x200B;リンクを選択します。</p><p>次の各領域には、その領域で使用されているセグメントのインスタンス数が表示されます。</p>  <ul><li>[!UICONTROL **プロジェクト**]<p>[ セグメントビルダーで作成 ](/help/components/segments/seg-builder.md#) されたセグメントが含まれており、すべてのプロジェクトで使用できます。</p></li><li>[!UICONTROL **アドホックコンポーネント**]<p>[ クイックセグメントとして作成 ](/help/components/segments/seg-quick.md) されたセグメントを含み、1 つのプロジェクト内でのみ使用できます。</p></li><li>[!UICONTROL **スケジュールされたプロジェクト**]</li><li>[!UICONTROL **モバイルスコアカード**]</li><li>[!UICONTROL **注釈**]</li><li>[!UICONTROL **計算指標**]</li><li>[!UICONTROL **Report Builder**]<p>このオプションを選択すると、次のデータ列を含む CSV ファイルがダウンロードされます。</p><ul><li>Report Builder 名</li><li>前回のアクセス</li><li>最後にアクセスした IMS ユーザー ID</li><li>前回アクセスしたユーザー名</li></ul></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報は、システム管理者のみが使用できます。</li><li>[!UICONTROL **使用**]&#x200B;列はデフォルトでは表示されません。この列の表示を構成するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。</li><li>この情報には、API またはデータウェアハウスからの使用は含まれません。</li><li>特定のコンポーネントのこの列にデータがないが、そのコンポーネントに&#x200B;[!UICONTROL **最終使用**]&#x200B;がある場合、そのコンポーネントは保存されずに分析で使用された可能性があります。</li><li>使用状況に関する情報は、2023年9月より提供されます。</li></ul><p>この情報と共に[データ辞書](/help/components/data-dictionary/data-dictionary-overview.md)を使用すると、組織内でのコンポーネントの使用方法を追跡し、より深く理解することができます。</p> |
| **[!UICONTROL 前回の使用]** | セグメントが最後に使用された日時。 |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

セグメントに対するアクションを実行するには、アクションバーの ➋ を使用します。 アクションバーには、次のアクションが含まれます。

| アクション | 説明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | [ セグメントビルダー ](seg-builder.md) を使用して、別のセグメントを追加します。 |
| ![検索](/help/assets/icons/Search.svg) [!UICONTROL *タイトルで検索*] | リストでセグメントが選択されていない場合、この検索フィールドを使用してセグメントを検索します。 |
| ![ラベル](/help/assets/icons/Label.svg)、**[!UICONTROL タグ]** | 選択したセグメントにタグ付けします。 **[!UICONTROL セグメントをタグ付け]** ダイアログで、選択したセグメントのタグを選択または選択解除します。 「**[!UICONTROL 保存]**」を選択して、選択したセグメントのタグを保存します。 詳しくは、[ セグメントのタグ付け ](/help/components/segments/seg-tag.md) を参照してください。 |
| ![共有](/help/assets/icons/ShareAlt.svg)、**[!UICONTROL 共有]** | 選択したセグメントの共有 **[!UICONTROL セグメントを共有]** ダイアログでは、![ 検索 ](/help/assets/icons/Search.svg)*個人またはグループを検索* または **[!UICONTROL 組織]** または **[!UICONTROL グループ]** を選択できます。 「**[!UICONTROL 保存]**」を選択して、選択したセグメントの共有の詳細を保存します。 詳しくは、[ セグメントの共有 ](seg-share.md) を参照してください。 |
| ![削除](/help/assets/icons/Delete.svg)、**[!UICONTROL 削除]** | 選択したセグメントを削除します。 確認メッセージが表示されます。 |
| ![編集](/help/assets/icons/Edit.svg)**[!UICONTROL 名前を変更]** | 選択した 1 つのセグメントの名前を変更します。 選択した場合、セグメントの名前をインラインで変更できます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 承認]** | 選択したセグメントを承認します。 詳しくは、[ セグメントの承認 ](seg-approve.md) を参照してください。 |
| ![コピー](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]** | 選択したセグメントをコピーします。 同じ名前とサフィックス `(Copy)` を持つ新しいセグメントが作成されます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV に書き出し]** | セグメントを `Segments List.csv` ファイルに書き出します。 |

### アクティブなフィルターバー

フィルターバー ➌ は、フィルターパネルからセグメントのリスト（ある場合）に適用されたアクティブなセグメントが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。複数のフィルターを指定した場合は、「すべてを削除 **[!UICONTROL を使用して、すべてのフィルターを削除でき]** す。

### フィルターパネル

セグメントのリストは、左のパネル ➍ ージの ![ フィルター ](/help/assets/icons/Filter.svg)**[!UICONTROL フィルター]** を使用してフィルタリングできます。 フィルターパネルには、フィルターのタイプと、特定のフィルターを適用するセグメントの数が表示されます。 ![ フィルター ](/help/assets/icons/Filter.svg) を選択して、フィルターパネルの表示を切り替えます。

詳しくは、[ セグメントのリストのフィルタリング ](seg-filter.md) を参照してください。
