---
title: フリーフォームテーブルへの複数のディメンションの含め
description: フリーフォームテーブルに複数のディメンションを含める方法を説明します
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: bff352181392c19b6c4fe70893a016179fb77f06
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 2%

---

# フリーフォームテーブルへの複数のディメンションの含め

{{release-limited-testing}}

フリーフォームテーブルには最大 5 つのディメンション列を含めることができ、複数のディメンション項目を並べて表示できます。 ディメンション項目の各行は、単一の連結項目として機能します。

より完全なカスタム分析を行うために、（指標列と共に）ディメンション列を並べ替えることができます。

## 複数のディメンション列と分類

Analysis Workspaceでは、フリーフォームテーブル内に複数のディメンションを追加する次の方法を提供します。

* 複数のディメンション列を含める（この記事を参照）

* [分類を追加](/help/components/dimensions/t-breakdown-fa.md)

これらの両方の方法を使用すると、他のディメンションに対してディメンションを分析できます。 ただし、重要な違いがあり、両方の方法を同じ表で使用すると、さらに深く分析できます。

複数のディメンション列を使用すると、次のことができます。

* 複数のディメンションと指標にわたってデータ行を関連付けます。

* テーブルの各ディメンション列に適用される場合にのみデータを表示します。 これを行うには、列フィルターを使用して、各ディメンション列の **[!UICONTROL 「値なし」を含める]** 設定の選択を解除します。

  詳しくは、「[ テーブルのフィルタリングと並べ替え ](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)」を参照してください。

* 複数のディメンション列と指標列でデータを並べ替えます。

  詳しくは、「[ テーブルのフィルタリングと並べ替え ](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)」を参照してください。

分類を使用すると、次のことができます。

* 1 つのディメンション項目のみを表示

* 単一の上位ディメンション項目の表示

## ディメンション列の追加

ディメンション列は、1 つずつ追加することも、一括して追加することもできます。

1. Analysis Workspaceで、フリーフォームテーブルを作成します。

   詳しくは、[ ビジュアライゼーションの概要 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) の [ パネルへのビジュアライゼーションの追加 ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) を参照してください。

1. フリーフォームテーブルにディメンションを追加します。 ディメンションは、1 つずつ追加することも、一度に複数のディメンションを追加することもできます。

   * ディメンションを 1 つずつフリーフォームテーブルにドラッグします。 テーブル内の既存のディメンション列の左側または右側に、追加のディメンション列を配置します。 新しい列が作成される場所に、青い縦線 **[!UICONTROL 追加]** が表示されます。

     ![ 個々の寸法をドラッグ ](assets/dimensions-add-individually.png)

   * コンポーネントメニューで最大 5 つのディメンションを選択し、フリーフォームテーブルにドラッグします。 ディメンションは、選択した順序で左から右にテーブルに追加されます。

     複数の寸法を選択するには、***Command*** キー（Macの場合）または ***Ctrl*** キー（Windows の場合）を押します。

     ![ 複数の寸法をドラッグする ](assets/dimensions-add-multiple.png)

## テーブルのフィルタリング

テーブルのフィルタの詳細については、「テーブルのフィルタと並べ替え [ の ](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables)[ テーブルのフィルタ ](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) を参照してください。

## テーブルの並べ替え {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails article. -->

フリーフォームテーブルのデータを、Analysis Workspaceのディメンションまたは指標のいずれかの列で並べ替えることができます。

デフォルトでは、ディメンションは昇順で並べ替えられ、指標は降順で並べ替えられます。

### 1 つの列でテーブルを並べ替え

この節で説明するように 1 列のデータを並べ替えると、テーブルに適用されている [ 詳細な並べ替え ](#sort-tables-by-multiple-columns-advanced-sorting) は削除されます。

テーブルのデータを 1 つの列で並べ替えるには：

1. 並べ替える列のヘッダーにマウスを移動し、表示された **並べ替え** アイコン ![ 並べ替え ](/help/assets/icons/SortOrderDown.svg) を選択します。

   ![ 並べ替えドロップダウンメニュー ](assets/sort-dropdown-menu.png)

1. **[!UICONTROL 昇順]** または **[!UICONTROL 降順]** を選択します。

   並べ替えが列に適用されている場合、並べ替えアイコンは表示されたままになります。 矢印は、データの並べ替え方法（昇順の場合は ![ 並べ替え ](/help/assets/icons/SortOrderUp.svg)、降順の場合は ![ 並べ替え ](/help/assets/icons/SortOrderDown.svg)）を示します。

### 複数の列でテーブルを並べ替える（詳細な並べ替え）

{{release-limited-testing-section}}

#### 複数の列への並べ替えの適用

テーブルのデータを複数の列で並べ替えるには：

1. 並べ替える列のヘッダーにマウスを移動し、表示された **並べ替え** アイコン ![ 並べ替え ](/help/assets/icons/SortOrderDown.svg) を選択します。

   ![ 並べ替えドロップダウンメニュー ](assets/sort-dropdown-menu.png)

1. **[!UICONTROL 詳細な並べ替え]** を選択します。

   ![ 詳細な並べ替えダイアログ ](assets/sort-advanced-dialog.png)

1. 詳細な並べ替えダイアログで、次のいずれかの操作を行います。

   * 「**[!UICONTROL 並べ替え列を追加]** ボタンを選択して、まだ並べ替えられていない列を追加します。

   * **削除** アイコン ![ 削除 ](/help/assets/icons/Close.svg) を選択して、ソートする必要がなくなった列を削除します。

   * リスト内の列を上下にドラッグして、並べ替えの優先度を調整します。

     詳細については、「[ 優先度を並べ替える ](#sort-priority)」を参照してください。

   * ドロップダウンメニューで **[!UICONTROL 昇順]** または **[!UICONTROL 降順]** を選択して、並べ替え値を変更します。

   * 列名ドロップダウンメニューを選択して、別の列を選択します。

1. 「**[!UICONTROL 適用]**」を選択します。

並べ替えが列に適用されている場合、並べ替えアイコンは表示されたままになります。 矢印は、データの並べ替え方法（昇順の場合は ![ 並べ替え ](/help/assets/icons/SortOrderUp.svg)、降順の場合は ![ 並べ替え ](/help/assets/icons/SortOrderDown.svg)）を示します。

![ マルチソートの例 ](assets/dimensions-multiple-sort.png)

#### 並べ替えの優先度

複数の列のデータを並べ替える場合、各列に割り当てた優先度に従ってデータが並べ替えられます。 優先度番号は、ソートアイコン ![ ソート優先度アイコン ](assets/sort-priority-icon.png) の横に表示されます。

プライマリの優先順位の列はメインの順序を決定し、セカンダリの優先順位の列はプライマリの列の値が同じ行の順序を決定し、プライマリの列とセカンダリの列は行の値が同じ行の順序を決定する、など。

例えば、次の列を持つテーブルについて考えてみます。

* 日（ディメンション）

* 時刻（ディメンション）

* イベント （指標）

次のように、各列に並べ替え優先度を割り当てることができます。

| 列（コンポーネント）名 | コンポーネントの種類 | 並べ替えの優先度 |
|---------|----------|---------|
| 日付 | ディメンション | 1 |
| 時刻 | ディメンション | 2 |
| イベント | 指標 | 3 |

各列に並べ替えの優先度を割り当てることで、テーブルでのデータの表示方法を正確に制御できます。 この例では、情報は最初に日、次に時間、最後にイベントで並べ替えられます。

![ マルチソートの例 ](assets/dimensions-multiple-sort.png)

## 複数のディメンション列を持つテーブルへの分類の追加

複数のディメンション列を持つテーブルに分類を追加すると、分類は、その追加先の行にあるすべてのディメンション項目にまたがります。

[ 分類ディメンション ](/help/components/dimensions/t-breakdown-fa.md) の説明に従って、分類を追加できます。

## サポートされていないディメンション {#unsupported}

次のディメンションの組み合わせはサポートされておらず、Analysis Workspaceでは追加が禁止されているか、追加後にエラーメッセージが表示されます。

* 同じフリーフォームテーブルで一緒に使用される異なる [ オブジェクトの配列 ](/help/use-cases/object-arrays.md) を参照するフィールドの複数のディメンション。

  オブジェクトの同じ配列を参照する場合、複数のディメンションを同じフリーフォームテーブルにまとめることができます。