---
description: セグメントマネージャーを使用して、共有、フィルター、タグ付け、承認、コピー、セグメントの削除、セグメントをお気に入りとしてマークするなど、セグメントを管理する方法について説明します。
title: セグメントの管理
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
TQID: https://experienceleague.adobe.com/Qzg97F1FVB6RSdjM8YISl47HYWtkQihxrOzLVO-4kOo
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0id: f2ef16dc-055a-4bb7-baa5-7039653f3966id: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 932
ht-degree: 32%

---

# セグメントの管理


[共有](seg-share.md)、[ セグメント ](seg-filter.md)、[ タグ ](seg-tag.md)、[承認](seg-approve.md)、名前変更、[ コピー](seg-copy.md)、セグメントの削除、書き出し、セグメントを[お気に入り](seg-favorite.md)としてマークできます。これらは、中央の[!UICONTROL  セグメント ]管理インターフェイスから実行できます。 セグメントを管理するには：

* メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL セグメント]**」を選択します。


>[!NOTE]
>
>特定のWorkspace プロジェクト内で作成したクイックセグメントは、すべてのプロジェクトでセグメントを使用可能にしていない限り、[!UICONTROL  セグメント ] マネージャーには表示されません。
>

## セグメントマネージャー

セグメントマネージャーには、次のインターフェイス要素があります。

![ セグメントインターフェイス ](assets/filters-manager.png)

### セグメントリスト

セグメント リスト ➊には、所有しているすべてのセグメント、すべてのプロジェクトに対してスコープが設定されているセグメント、および共有されているセグメントが表示されます。 リストには、次の列があります。

| 列 | 説明 |
| --- | --- |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | セグメントの![Star](/help/assets/icons/Star.svg)を優先するか、![StarOutline](/help/assets/icons/StarOutline.svg)を優先しないかを選択します。 [ セグメントをお気に入りにマーク ](/help/components/segments/seg-favorite.md)する |
| **[!UICONTROL タイトルと説明]** | セグメントを編集するには、タイトルリンクを選択します。これにより、[ セグメントビルダー](seg-builder.md)が開きます。 共有セグメントは![Share](/help/assets/icons/ShareAlt.svg)で示されます。 |
| **[!UICONTROL データビュー]** | このセグメントが適用されるデータビュー。 |
| **[!UICONTROL 所有者]** | セグメントの所有者。 ユーザーは、自分が所有するセグメントまたは自分と共有されている注釈のみを表示できます。 |
| **[!UICONTROL タグ]** | このセグメントのタグ。 |
| **[!UICONTROL 共有先]** | セグメントを共有した個人またはグループの数。 選択して、**[!UICONTROL コンポーネントを共有]**&#x200B;ダイアログを開きます。 詳しくは、[ セグメントの共有](seg-share.md)を参照してください。 |
| **[!UICONTROL 変更日時]** | セグメントが最後に変更された日時。 |
| **[!UICONTROL 使用場所]** | セグメントが現在使用されている場所と、各領域でセグメントが何回使用されているかを示します。 <p>例えば、セグメントが40件のプロジェクトと2件のアラートで使用されている場合、この列の値は&#x200B;[!UICONTROL **42個のコンポーネント**]&#x200B;として表示されます。</p> <p>この列の値を選択して、セグメントが使用されている場所の内訳を表示します（例：[!UICONTROL **プロジェクト（40）**]、[!UICONTROL **モバイルスコアカード（2）**]）。 さらに、セグメントが使用されている項目のリストを表示できます。 例えば、使用されているプロジェクトのリストを表示するには、[!UICONTROL **プロジェクト（40）**]&#x200B;リンクを選択します。</p><p>次の各領域は、その領域で使用されているセグメントのインスタンス数を示しています。</p>  <ul><li>[!UICONTROL **プロジェクト**]<p>セグメントビルダー](/help/components/segments/seg-builder.md#)で作成された[ セグメントが含まれており、すべてのプロジェクトで使用できます。</p></li><li>[!UICONTROL **アドホックコンポーネント**]<p>[ クイックセグメント ](/help/components/segments/seg-quick.md)として作成され、1つのプロジェクト内でのみ使用できるセグメントが含まれています。</p></li><li>[!UICONTROL **スケジュールされたプロジェクト**]</li><li>[!UICONTROL **モバイルスコアカード**]</li><li>[!UICONTROL **注釈**]</li><li>[!UICONTROL **計算指標**]</li><li>[!UICONTROL **Report Builder**]<p>このオプションを選択すると、次のデータ列を含む CSV ファイルがダウンロードされます。</p><ul><li>Report Builder 名</li><li>前回のアクセス</li><li>最後にアクセスした IMS ユーザー ID</li><li>前回アクセスしたユーザー名</li></ul></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報は、システム管理者のみが使用できます。</li><li>[!UICONTROL **使用**]&#x200B;列はデフォルトでは表示されません。 この列の表示を構成するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。</li><li>この情報には、API またはデータウェアハウスからの使用は含まれません。</li><li>特定のコンポーネントのこの列にデータがないが、そのコンポーネントに&#x200B;[!UICONTROL **最終使用**]&#x200B;がある場合、そのコンポーネントは保存されずに分析で使用された可能性があります。</li><li>使用状況に関する情報は、2023年9月より提供されます。</li></ul><p>この情報と共に[データ辞書](/help/components/data-dictionary/data-dictionary-overview.md)を使用すると、組織内でのコンポーネントの使用方法を追跡し、より深く理解することができます。</p> |
| **[!UICONTROL 前回の使用]** | セグメントが最後に使用された日時。 |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

アクション バー➋を使用して、セグメントに対してアクションを実行できます。 アクションバーには、次のアクションが含まれます。

| アクション | 説明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | [ セグメントビルダー](seg-builder.md)を使用して、別のセグメントを追加します。 |
| ![検索](/help/assets/icons/Search.svg)[!UICONTROL *タイトルで検索*] | リストでセグメントが選択されていない場合は、この検索フィールドを使用してセグメントを検索します。 |
| ![ラベル](/help/assets/icons/Label.svg)、**[!UICONTROL タグ]** | 選択したセグメントにタグ付けします。 **[!UICONTROL タグセグメント]** ダイアログで、選択したセグメントのタグを選択または選択解除します。 選択したセグメントのタグを保存するには、**[!UICONTROL 保存]**&#x200B;を選択します。 詳しくは、[ セグメントのタグ付け](/help/components/segments/seg-tag.md)を参照してください。 |
| ![共有](/help/assets/icons/ShareAlt.svg)、**[!UICONTROL 共有]** | 選択したセグメントを共有します。 **[!UICONTROL セグメントを共有]** ダイアログで、![検索](/help/assets/icons/Search.svg) *個人またはグループを検索*&#x200B;するか、**[!UICONTROL 組織]**&#x200B;または&#x200B;**[!UICONTROL グループ]**&#x200B;を選択できます。 選択したセグメントの共有の詳細を保存するには、**[!UICONTROL 保存]**&#x200B;を選択します。 詳しくは、[ セグメントの共有](seg-share.md)を参照してください。 |
| ![削除](/help/assets/icons/Delete.svg)、**[!UICONTROL 削除]** | 選択したセグメントを削除します。 確認メッセージが表示されます。 <br/> セグメントを削除する場合は、次の点に注意してください。 <ul><li>このセグメントが適用されたスケジュール済みレポートとプロジェクトは、引き続き正常に機能します。</li><li> スケジュールされたレポートは、同じ名前のセグメントを編集しても更新されません。</li> </ul> |
| ![編集](/help/assets/icons/Edit.svg)**[!UICONTROL 名前を変更]** | 選択した1つのセグメントの名前を変更します。 選択すると、セグメントの名前をインラインで変更できます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 承認]** | 選択したセグメントを承認します。 詳しくは、[ セグメントの承認](seg-approve.md)を参照してください。 |
| ![コピー](/help/assets/icons/Copy.svg)**[!UICONTROL コピー]** | 選択したセグメントをコピーします。 新しいセグメントが、同じ名前とサフィックス `(Copy)`で作成されます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV に書き出し]** | セグメントを`Segments List.csv` ファイルに書き出します。 |

### アクティブなフィルターバー

フィルターバー➌には、フィルターパネルからセグメントのリスト（存在する場合）に適用されたアクティブなセグメントが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。 複数のフィルターが指定されている場合は、**[!UICONTROL すべてを削除]**&#x200B;を使用してすべてのフィルターを削除できます。

### フィルターパネル

![ フィルター](/help/assets/icons/Filter.svg) **[!UICONTROL フィルター]**&#x200B;左側のパネル ➍を使用して、セグメントのリストをフィルターできます。 フィルターパネルには、フィルターのタイプと、特定のフィルターを適用するセグメントの数が表示されます。 「![ フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターパネルの表示を切り替えます。

詳しくは、[ セグメントのリストのフィルタリング ](seg-filter.md)を参照してください。
