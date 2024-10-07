---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: コンポーネント情報の表示
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: df0fd0af8a22c84705c3dea11065132359dd80ff
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 73%

---

# コンポーネント情報の表示

データ要素を使用すると、コンポーネントの説明、類似のコンポーネント、コンポーネントが頻繁に使用される他のコンポーネントなど、コンポーネントに関する情報を表示できます。

データ要素でコンポーネントに関する情報を表示するには：

1. 表示するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspaceの左側のパネルにある「[!UICONTROL **データ要素**]」アイコンを選択します （データ要素にアクセスする別の方法については、[データ要素の概要](/help/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

   データ要素ウィンドウが表示されます。

   ![Dimension、指標、セグメントおよび日付範囲のクイックフィルターを表示するデータ要素ウィンドウ ](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 表示するコンポーネントを含むデータビューがドロップダウンメニューで選択されていることを確認します。 デフォルトでは、既に存在するデータビューが表示されます。

1. （オプション）検索フィールドに、表示するコンポーネントの名前の入力します。

   コンポーネントのタイプは、カラーとアイコンの両方で識別できます。**Dimension** ![Dimensionアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) オレンジ色、**フィルター** ![ セグメントアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 青色、**日付範囲** ![ 日付範囲アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 紫色、**指標** ![ 指標アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 緑色です。 アドビアイコン ![アドビアイコン](assets/default-calc-metric-icon.png) は計算指標テンプレートまたはフィルターテンプレートのいずれか、電卓アイコン ![電卓アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は組織の Analytics 管理者によって作成された計算指標を示します。

{{dd-filter-criteria}}

1. （オプション）「**並べ替え**」アイコン ![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) を選択し、次のフィルターオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

   {{components-sort-options}}

1. コンポーネントのリストから、表示するコンポーネントを選択します。

   コンポーネントに関する次の情報が表示されます。

   {{dd-component-information}}

1. （オプション）データ要素から Analysis Workspace にコンポーネントをドラッグします。
