---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素でのエントリの編集
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: ec8760cf9984d4e962992f613c4a58a52fa29d47
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 45%

---

# データ要素でのコンポーネントエントリの編集

Customer Journey Analytics管理者は、特定のデータビューのデータディクショナリ内のコンポーネントエントリを編集できます。 加えた変更は、データビューのすべてのユーザーに表示されます。

データ要素でのコンポーネントを編集するには：

1. 編集するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspace の左側のパネルにある「**データ要素**」アイコンを選択します（データ要素にアクセスする別の方法については、[データ要素の概要](/help/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

データ要素ウィンドウが表示されます。

![データ要素の管理者表示](assets/data-dictionary-admin.png)

1. ドロップダウンメニューで正しいデータビューが選択されていることを確認します。 デフォルトでは、既に存在するデータビューが表示されます。

1. （オプション）検索フィールドに、編集するコンポーネントの名前を入力します。

コンポーネントの種類は、色とアイコンの両方で識別できます。 **Dimension** ![Dimensionアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) オレンジ色です **セグメント** ![セグメントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 青い **日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 紫色で **指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑です。 Adobeアイコンは、計算指標テンプレートまたはセグメントテンプレート、および計算ツールアイコンを示します ![計算ツールアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は、組織の Analytics 管理者が作成した計算指標を示していました。

{{dd-filter-criteria}}

1. （オプション） **並べ替え** アイコン ![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)次に、次のいずれかのフィルターオプションを選択して、コンポーネントのリストを並べ替えます。

{{components-sort-options}}

1. コンポーネントのリストから、編集するコンポーネントを選択します。

1. コンポーネント名の横にある&#x200B;**編集**&#x200B;アイコン ![データ要素編集アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) を選択します。

1. コンポーネントに関する次の情報を編集します。

{{dd-component-information}}

1. **保存**&#x200B;アイコン ![データ要素保存アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) をクリックして、変更内容を保存します。
