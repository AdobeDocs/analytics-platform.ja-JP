---
description: Customer Journey Analytics に Analysis Workspaceでクイックフィルターを使用
title: クイックフィルター
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 53d367e51f739ebf324390ba4114ddb58138fac8
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 39%

---

# クイックフィルター

クイックフィルターを使用すると、特定のプロジェクト内のデータを簡単に調べることができます。[ フィルタービルダー ](/help/components/filters/create-filters.md) でより複雑なコンポーネントリストフィルターを作成する必要はありません。

クイックフィルターを作成する際は、次の点を考慮してください。

* クイックフィルターは、クイックフィルターを作成したプロジェクトにのみ適用されます。 他のプロジェクトでは使用できず、他のユーザーと共有できません。
* ルールは最大 3 つまで使用できます。
* ネストされたコンテナや順次ルールはサポートされていません。
* プロジェクトを他のユーザーと共有する場合、それらのユーザーは、クイックフィルターや、共有プロジェクトに埋め込まれたプロジェクトのみの他のコンポーネントを編集できます。

次のビデオでは、クイックフィルターの使用方法を説明します。 （メモ：このビデオでは、「クイックフィルター」ではなく「クイックセグメント」という用語を使用します。 ただし、機能は同じです）。

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## クイックフィルターの作成 {#create}

Analysis Workspace内の任意のユーザーがクイックフィルターを作成できます。

クイックフィルターを作成するには：

1. クイックフィルターの作成を開始するには、次のいずれかの方法を選択します。

   * **アドホック（ドラッグ&amp;ドロップ）:** 左のパネルから、コンポーネントをパネルヘッダーのフィルタードロップゾーンにドラッグします。

     ![ドロップゾーンへのセグメントのドロップ](assets/filter-dropzone.png)

     [ クイックフィルターの編集 ](#edit-a-quick-filter) の説明に従って、クイックフィルターを編集できます。

     >[!NOTE]
     >
     > クイックフィルターのアドホックを作成する場合（ドラッグ&amp;ドロップ）は、次の点を考慮してください。
     > * 次のコンポーネントタイプはサポートされていません。計算指標とディメンション、およびフィルターを作成できない指標です。
     > * 完全なディメンションとイベントの場合、Analysis Workspaceは「exists」イベントフィルターを作成します。 例：`Hit where eVar1 exists` または `Hit where event1 exists`。
     > * 「未指定」または「なし」がフィルタードロップゾーンにドロップされると、フィルターで正しく処理できるようにするため、「存在しない」フィルターに自動変換されます。


   * **フィルターアイコンの使用：** フリーフォームテーブルで、パネルヘッダーの「**フィルター**」アイコンを選択します。

     ![セグメントフィルター](assets/quick-seg1.png)

1. 次のいずれかの設定を調整します。

   | 設定 | 説明 |
   | --- | --- |
   | [!UICONTROL 名前] | フィルターのデフォルト名は、フィルター内のルール名の組み合わせです。フィルターの名前を、わかりやすい名前に変更できます。 |
   | [!UICONTROL 含む／除く] | フィルター定義にコンポーネントを含めるか除外することはできますが、両方を使用することはできません。 |
   | [!UICONTROL ヒット／訪問／訪問者]コンテナ | クイックフィルターには、ディメンション／指標／日付範囲をフィルターに含める（または除外する）ための [フィルターコンテナ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=ja#filter-containers) が 1 つだけ含まれます。[!UICONTROL  訪問者 ] には、訪問およびページビューをまたいでユーザーに固有の、包括的なデータが含まれます。 [!UICONTROL  訪問 ] コンテナでは、ユーザーのデータを訪問に基づいて分類するルールを設定でき、[!UICONTROL  ヒット ] コンテナでは、ユーザー情報を個々のページビューに基づいて分類できます。 デフォルトのコンテナは [!UICONTROL  ヒット]です。 |
   | [!UICONTROL コンポーネント]（ディメンション／指標／日付範囲） | コンポーネント（ディメンション、指標、日付範囲、ディメンション値）を追加して、最大 3 つのルールを定義できます。適切なコンポーネントを見つける方法は 3 つあります。<ul><li>入力を開始すると、クイックフィルタービルダーが適切なコンポーネントを自動的に見つけます。</li><li>ドロップダウンリストを使用して、コンポーネントを検索します。</li><li>データセットを左側のパネルからドラッグ＆ドロップします。</li></ul> |
   | [!UICONTROL 演算子] | 標準演算子と[!UICONTROL 個別カウント]演算子を検索するには、ドロップダウンメニューを使用します。詳しくは、 [フィルター演算子](operators.md)を参照してください。 |
   | プラス（+）記号 | 別のルールの追加 |
   | AND／OR 修飾子 | 「AND」修飾子または「OR」修飾子をルールに追加できますが、「AND」と「OR」を 1 つのフィルター定義で混在させることはできません。 |
   | [!UICONTROL 適用] | このフィルターをパネルに適用します。フィルターにデータが含まれていない場合は、続行するかどうかを確認するメッセージが表示されます。 |
   | [!UICONTROL ビルダーを開く] | フィルタービルダーを開きます。フィルタービルダーで保存または適用したフィルターは、「クイックフィルター」とは見なされなくなります。 これは、コンポーネントリストフィルターライブラリの一部になります。 <p>コンポーネントをすべてのプロジェクトと左側のレールで使用できるようにするには、オプション [!UICONTROL **このフィルターをすべてのプロジェクトで使用できるようにして、コンポーネントリストに追加する**] を選択します。</p><p>詳しくは、この記事の [ クイックフィルターをコンポーネントリストフィルターとして保存する ](#save-a-quick-filter-as-a-component-list-filter) を参照してください。</p><p>**メモ：** フィルタービルダーを開くことができるのは、[Adobe Admin Consoleのセグメントの作成権限を持つユーザーのみ ](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=ja) です。</p> |
   | [!UICONTROL キャンセル] | このクイックフィルターをキャンセルします（適用しないでください）。 |
   | [!UICONTROL 日付範囲] | バリデーターは、データ参照にパネルの日付範囲を使用します。 ただし、クイックフィルターで適用した日付範囲は、パネルの上部にあるパネルの日付範囲より優先されます。 |
   | プレビュー（右上） | 有効なフィルターがあるかどうか、およびフィルターの範囲を確認できます。このフィルターを適用した場合に予想されるデータセットの分類を表します。 このフィルターにデータがないことを示す通知が表示される場合があります。 この場合は、続行するか、フィルター定義を変更できます。 |

1. 「[!UICONTROL **適用**]」を選択して変更を保存します。

## クイックフィルターの編集 {#edit}

1. 編集するクイックフィルターにポインタを合わせて、「**編集** アイコンを選択します。

   ![アドホックフィルターを編集](assets/filter-adhoc-edit.png)

1. フィルター定義またはフィルター名を編集します。
1. 「[!UICONTROL **適用**]」を選択して変更を保存します。

## クイックフィルターをコンポーネントリストフィルターとして保存 {#save}

>[!IMPORTANT]
>
> クイックフィルターを保存する際は、次の点を考慮してください。
> 
> * クイックフィルターを保存するには、[Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=ja) でのセグメントの作成権限が必要です。
> 
> * フィルターを保存または適用すると、クイックフィルタービルダーで編集できなくなります。 代わりに、通常のフィルタービルダーを使用する必要があります。

クイックフィルターをコンポーネントリストフィルターとして保存するように選択できます。 コンポーネントリストフィルターの利点は次のとおりです。

* すべての Workspace プロジェクトでの利用可能性。
* より複雑なフィルターおよび順次フィルターのサポート

フィルターは、クイックフィルタービルダーまたは [!UICONTROL  フィルタービルダー ] から保存できます。

### クイックフィルタービルダーでの保存 {#save2}

1. クイックフィルターを適用したら、その上にマウスポインターを置いて、情報（「i」）アイコンを選択します。
1. 「**[!UICONTROL すべてのプロジェクトで使用できるようにして、コンポーネントリストに追加]**」を選択します。
1. （任意）フィルターの名前を変更します。
1. 「**[!UICONTROL 保存]**」を選択します。

   フィルターが、左側のパネルのコンポーネントリストに表示されます。 また、フィルターのサイドバーが明るい青から暗い青に変わり、クイックフィルタービルダーで編集または開くことができなくなったことを示します。

### フィルタービルダーで保存 {#save3}

1. クイックフィルターを適用したら、その上にマウスポインターを置いて、情報（「i」）アイコンを選択します。
1. 「**[!UICONTROL フィルターを保存]**」を選択します。
1. （オプション）フィルターの名前を変更し、「[!UICONTROL **適用**]」を選択します。

   Workspaceに戻り、フィルターのサイドバーが明るい青から暗い青に変わり、クイックフィルタービルダーで編集または開くことができなくなったことを示していることに注意してください。 保存すると、コンポーネントリストの一部になります。

   ![フィルターコンポーネントのリスト](assets/quick-seg4.png)

フィルターを適用したら、フィルターコンポーネントリストに追加して、すべてのプロジェクトで使用できるようにします。

1. 保存したフィルターの上にマウスポインターを置いて、鉛筆アイコンを選択します。

1. 「[!UICONTROL **ビルダーを開く**]」を選択します。

1. フィルタービルダーの上部に、次のダイアログが表示されます。

   ![フィルターダイアログ](assets/project-only-filter-dialog.png)

1. **[!UICONTROL このフィルターをすべてのプロジェクトで使用できるようにして、コンポーネントリストに追加する]** の横にあるチェックボックスを選択します。

1. 「**[!UICONTROL 保存]**」を選択します。

   フィルターが、すべてのプロジェクトのフィルターコンポーネントリストに表示されます。
また、組織内の他のユーザーと [フィルターを共有](/help/components/filters/filters-share.md) することもできます。

## クイックフィルターの例

次のフィルターの例では、ディメンションと指標を組み合わせています。

![フィルター定義の例](assets/quick-seg2.png)

