---
title: フリーフォームテーブルへの複数のディメンションの含め
description: フリーフォームテーブルに複数のディメンションを含める方法を説明します
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 77acfaf2d186e7fe7d6b9d973af5dedb3956f5d5
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 2%

---

# フリーフォームテーブルに複数のディメンション列を含める

{{release-limited-testing}}

フリーフォームテーブルには最大 5 つのディメンション列を含めることができ、複数のディメンション項目を並べて表示できます。 ディメンション項目の各行は、単一の連結されたディメンション項目のように動作します。

複数のディメンション列を持つフリーフォームテーブルにフィルター、並べ替え、分類などを適用して、より深く、よりカスタムな分析を作成できます。

## 連結されたディメンション項目

[&#x200B; フリーフォームテーブルに複数のディメンション列を追加 &#x200B;](#add-multiple-dimension-columns) する場合、ディメンション項目の各行は、単一の連結ディメンション項目のように動作します。 この機能を使用すると、特定のディメンションの組み合わせに対する指標データを表示できます。

例えば、ディメンション列が _市区町村_、_デバイスタイプ_、および _日_ で、指標が _イベント_ であるフリーフォームテーブルについて考えてみます。 このテーブルの最初の行にある 3 つのディメンション項目は、月の 30 日に携帯電話からムンバイで発生したイベントが 2,056 件あったことを示す単一の連結ディメンション項目になります。

| Dimension：市 | Dimension：デバイスタイプ | Dimension：月の日 | 指標：イベント |
|---------|----------|---------|---------|
| ムンバイ | 携帯電話 | 30 | 2,056 |
| ニューヨーク | タブレット | 31 | 1,761 |
| バンガロール | デスクトップ | 1 | 1,666 |
| デリー | 携帯電話 | 14 | 1,396 |

Analysis Workspaceでのテーブルの表示方法を次に示します。

![&#x200B; 複数ディメンションの例 &#x200B;](assets/multi-dim-example.png)

## 複数のディメンション列の追加

複数のディメンション列を 1 つずつ追加することも、一括して追加することもできます。

1. Analysis Workspaceで、フリーフォームテーブルを作成します。

   詳しくは、[&#x200B; ビジュアライゼーションの概要 &#x200B;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) の [&#x200B; パネルへのビジュアライゼーションの追加 &#x200B;](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) を参照してください。

1. フリーフォームテーブルにディメンションを追加します。 ディメンションは、1 つずつ追加することも、一度に複数のディメンションを追加することもできます。

   * ディメンションを 1 つずつフリーフォームテーブルにドラッグします。 テーブル内の既存のディメンション列の左側または右側に、追加のディメンション列を配置します。 新しい列が作成される場所に、青い縦線 **[!UICONTROL 追加]** が表示されます。

     ![&#x200B; 個々の寸法をドラッグ &#x200B;](assets/dimensions-add-individually.png)

   * コンポーネントメニューで最大 5 つのディメンションを選択し、フリーフォームテーブルにドラッグします。 ディメンションは、選択した順序で左から右にテーブルに追加されます。

     複数の寸法を選択するには、***Command*** キー（Macの場合）または ***Ctrl*** キー（Windows の場合）を押します。

     ![&#x200B; 複数の寸法をドラッグする &#x200B;](assets/dimensions-add-multiple.png)

1. テーブルの各行を単一のディメンション項目として表示します。 詳しくは、[&#x200B; 連結されたディメンション項目 &#x200B;](#concatenated-dimension-items) を参照してください。

## テーブルのフィルタリング

フリーフォームテーブルの 1 つ以上のディメンション列にフィルターを適用できます。

テーブルのフィルタリングについて詳しくは、[&#x200B; フリーフォームテーブルのフィルタリングと並べ替え &#x200B;](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables) の [&#x200B; テーブルのフィルタリング &#x200B;](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) を参照してください。

## テーブルの並べ替え {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails -->

ディメンションか指標かに関わらず、Analysis Workspaceの任意の列でフリーフォームテーブルのデータを並べ替えることができます。

デフォルトでは、ディメンションは昇順で並べ替えられ、指標は降順で並べ替えられます。

### 1 つの列でテーブルを並べ替え

この節で説明するように 1 列のデータを並べ替えると、テーブルに適用されている [&#x200B; 詳細な並べ替え &#x200B;](#sort-tables-by-multiple-columns-advanced-sorting) は削除されます。

テーブルのデータを 1 つの列で並べ替えるには：

1. 並べ替える列のヘッダーにマウスを移動し、表示された **並べ替え** アイコン ![&#x200B; 並べ替え &#x200B;](/help/assets/icons/SortOrderDown.svg) を選択します。

   ![&#x200B; 並べ替えドロップダウンメニュー &#x200B;](assets/sort-dropdown-menu.png)

1. **[!UICONTROL 昇順]** または **[!UICONTROL 降順]** を選択します。

   並べ替えが列に適用されている場合、並べ替えアイコンは表示されたままになります。 矢印は、データの並べ替え方法（昇順の場合は ![&#x200B; 並べ替え &#x200B;](/help/assets/icons/SortOrderUp.svg)、降順の場合は ![&#x200B; 並べ替え &#x200B;](/help/assets/icons/SortOrderDown.svg)）を示します。

### 複数の列でテーブルを並べ替える（詳細な並べ替え）

<!-- add this back in when move this section back to the filter and sort article: {{release-limited-testing-section}} -->

#### 複数の列への並べ替えの適用

テーブルのデータを複数の列で並べ替えるには：

1. 並べ替える列のヘッダーにマウスを移動し、表示された **並べ替え** アイコン ![&#x200B; 並べ替え &#x200B;](/help/assets/icons/SortOrderDown.svg) を選択します。

   ![&#x200B; 並べ替えドロップダウンメニュー &#x200B;](assets/sort-dropdown-menu.png)

1. **[!UICONTROL 詳細な並べ替え]** を選択します。

   ![&#x200B; 詳細な並べ替えダイアログ &#x200B;](assets/sort-advanced-dialog.png)

1. 詳細な並べ替えダイアログで、次のいずれかの操作を行います。

   * 「**[!UICONTROL 並べ替え列を追加]** ボタンを選択して、まだ並べ替えられていない列を追加します。

   * **削除** アイコン ![&#x200B; 削除 &#x200B;](/help/assets/icons/Close.svg) を選択して、ソートする必要がなくなった列を削除します。

   * リスト内の列を上下にドラッグして、並べ替えの優先度を調整します。

     詳細については、「[&#x200B; 優先度を並べ替える &#x200B;](#sort-priority)」を参照してください。

   * ドロップダウンメニューで **[!UICONTROL 昇順]** または **[!UICONTROL 降順]** を選択して、並べ替え値を変更します。

   * 列名ドロップダウンメニューを選択して、別の列を選択します。

1. 「**[!UICONTROL 適用]**」を選択します。

並べ替えが列に適用されている場合、並べ替えアイコンは表示されたままになります。 矢印は、データの並べ替え方法（昇順の場合は ![&#x200B; 並べ替え &#x200B;](/help/assets/icons/SortOrderUp.svg)、降順の場合は ![&#x200B; 並べ替え &#x200B;](/help/assets/icons/SortOrderDown.svg)）を示します。

![&#x200B; マルチソートの例 &#x200B;](assets/dimensions-multiple-sort.png)

#### 並べ替えの優先度

複数の列のデータを並べ替える場合、各列に割り当てた優先度に従ってデータが並べ替えられます。 優先度番号は、ソートアイコン ![&#x200B; ソート優先度アイコン &#x200B;](assets/sort-priority-icon.png) の横に表示されます。

プライマリの優先順位の列は主な順序を決定し、セカンダリの優先順位の列は行が 1 次の列に同じ値を持つ場合の順序を決定し、3 次の優先順位の列は 1 次と 2 次の列に同じ値を持つ場合の順序を決定します。

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

![&#x200B; マルチソートの例 &#x200B;](assets/dimensions-multiple-sort.png)

## 複数のディメンション列と分類

Analysis Workspaceでは、フリーフォームテーブル内に複数のディメンションを追加する次の方法を提供します。

* 複数のディメンション列を含める（この記事を参照）

* [分類を追加](/help/components/dimensions/t-breakdown-fa.md)

これらの両方の方法を使用すると、他のディメンションに対してディメンションを分析できます。 ただし、重要な違いがあり、両方の方法を同じ表で使用すると、さらに深く分析できます。

### ディメンション列と分類の違い

複数のディメンション列を使用すると、次のことができます。

* 複数のディメンションをまたいで、ディメンション項目を個別のデータ行に連結します。

* ディメンション項目がテーブルの各ディメンション列に適用される場合にのみ、連結された行にディメンション項目を含めます。 これを行うには、列フィルターを使用して、各ディメンション列の **[!UICONTROL 「値なし」を含める]** 設定の選択を解除します。

  詳しくは、[&#x200B; 複数の列でテーブルを並べ替える（詳細な並べ替え） &#x200B;](#sort-tables-by-multiple-columns-advanced-sorting) を参照してください。

* 複数のディメンション列および指標列でデータを並べ替えて、よりカスタマイズされたデータを表示します。

  詳しくは、[&#x200B; 複数の列でテーブルを並べ替える（詳細な並べ替え） &#x200B;](#sort-tables-by-multiple-columns-advanced-sorting) を参照してください。

分類を使用すると、次のことができます。

* フリーフォームテーブルのディメンション項目をセカンダリディメンションで分類します。 セカンダリ ディメンションには、最大 400 個のディメンション項目を表示できます。

### 複数のディメンション列を持つテーブルへの分類の追加

複数のディメンション列を持つテーブルに分類を追加する場合、分類は、その分類を追加した行の（すべてのディメンション列に対して）連結されたディメンション項目に適用されます。

![&#x200B; 複数ソートの分類の例 &#x200B;](assets/dimensions-multiple-sort-breakdown.png)

さらに、分類内に複数のディメンション列を追加できます。 分類内のディメンション項目の各行は、単一の連結されたディメンション項目のように動作します。

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

分類の追加方法について詳しくは、[&#x200B; ディメンションの分類 &#x200B;](/help/components/dimensions/t-breakdown-fa.md) を参照してください。

## 複数のディメンション列にまたがるディメンション項目に基づいてセグメントを作成します

複数のディメンション列にまたがるディメンション項目に基づいてセグメントを作成する場合、各ディメンション項目はセグメント定義に含まれ、AND 演算子によって結合されます。

セグメントの作成について詳しくは、[&#x200B; セグメントの作成 &#x200B;](/help/components/segments/seg-create.md) を参照してください。

## サポートされていないディメンション {#unsupported}

次のディメンションの組み合わせはサポートされておらず、Analysis Workspaceでは追加が禁止されているか、追加後にエラーメッセージが表示されます。

* 同じフリーフォームテーブルで一緒に使用される異なる [&#x200B; オブジェクトの配列 &#x200B;](/help/use-cases/object-arrays.md) を参照するフィールドの複数のディメンション。

  オブジェクトの同じ配列を参照する場合、複数のディメンションを同じフリーフォームテーブルにまとめることができます。