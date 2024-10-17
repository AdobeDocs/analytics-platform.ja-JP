---
description: 計算指標ビルダーは、ディメンション、指標、フィルターおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成するためのキャンバスです。この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。
title: 計算指標の作成
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 37209097327ffb142068b5df184c07c7c8021442
workflow-type: tm+mt
source-wordcount: '1526'
ht-degree: 10%

---

# 計算指標の作成 {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_productcompatibility"
>title="製品の互換性"
>abstract="Analysis Workspace、Report Builder など、この計算指標を使用できる Customer Journey Analytics の場所を示します。一部の計算指標は、実験では使用できません。"
>additional-url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="実験で計算指標を使用"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="外部 ID を変更すると、ビジネスインテリジェンスツールなどの外部ソースでの計算指標の表示方法に影響する可能性があります"

<!-- markdownlint-enable MD034 -->


**[!UICONTROL 計算指標ビルダー]** ダイアログは、新しい計算指標の作成または既存の計算指標の編集に使用します。 このダイアログには、**[!UICONTROL 計算指標]** マネージャーから作成または管理する指標のタイトルが **** 新しい計算指標 [[!UICONTROL  または ] 計算指標を編集 ](/help/components/calc-metrics/cm-workflow/cm-manager.md) になります。

>[!BEGINTABS]

>[!TAB 計算指標ビルダー]

![ 次の節で説明するフィールドとオプションを示す、計算指標の詳細ウィンドウ。](assets/calculated-metric-builder.png)

>[!TAB  計算指標の作成または編集 ]

![ 次の節で説明するフィールドとオプションを示す、計算指標の詳細ウィンドウ。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 次の詳細を指定します（![ 必須 ](/help/assets/icons/Required.svg) は必須）。

   | 要素 | 説明 |
   | --- | --- |
   | **[!UICONTROL データビュー]** | 計算指標のデータビューを選択できます。  定義した計算指標は、選択したデータビューに基づいてWorkspace プロジェクトで使用できます。 |
   | **[!UICONTROL プロジェクトのみの指標]** | 指標が作成されたプロジェクトにのみ表示され、指標がコンポーネントリストに追加されないことを説明する情報ボックス。 **[!UICONTROL この指標をすべてのプロジェクトで使用できるようにして、コンポーネントリストに追加する]** を有効にして、その設定を変更します。 この情報ボックスは、「選択から指標を作成 **[!UICONTROL を使用してWorkspaceで指標を作成し、関数]****[!UICONTROL 平均]** や **[!UICONTROL 中央値]** など）を選択している場合にのみ表示されます。 後で [ コンポーネント情報 ](/help/components/use-components-in-workspace.md#component-info) を使用して、作成した指標を編集します。 |
   | **[!UICONTROL タイトル]** ![ 必須 ](/help/assets/icons/Required.svg) | 計算指標に名前を付けます（例：`Conversion Rate`）。 |
   | **[!UICONTROL 外部 ID]** ![ 必須 ](/help/assets/icons/Required.svg) | 外部 BI ツールと BI 拡張機能を使用する場合の計算指標の名前。 値を上書きしない限り、値は自動的に `undefined_xxx` として定義されます。 |
   | **[!UICONTROL 説明]** | フィルターの説明（例：`Calculated metric to define the conversion rate.` 計算指標の数式は、既に [!UICONTROL  概要 ] で自動的に使用可能なので、説明する必要はありません。 |
   | **[!UICONTROL 形式]** | 計算指標の形式の選択：**[!UICONTROL 小数]**、**[!UICONTROL 時間]**、**[!UICONTROL パーセント]**、**[!UICONTROL 通貨]** から選択できます。 |
   | **[!UICONTROL 小数点以下の桁数]** | 選択した書式の小数点以下の桁数を指定します。 選択した形式が小数、通貨、パーセントの場合にのみ有効です。 |
   | **[!UICONTROL 上昇傾向を次の形式で表示]** | 計算指標の上昇傾向を▲ **** 良（緑）または▼**[!UICONTROL 悪（赤）]** のいずれで表示すかを指定します。 |
   | **[!UICONTROL 通貨]** | 計算指標の通貨を指定します。 「形式」で「通貨」を選択した場合にのみ有効になります。 |
   | **[!UICONTROL タグ]** | 1 つ以上のタグを作成または適用して、計算指標を整理します。 入力を開始して、選択可能な既存のタグを検索します。 または、**[!UICONTROL Enter]** キーを押して新しいタグを追加します。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、タグを削除します。 |
   | **[!UICONTROL プレビュー]** | プレビューは過去 90 日間をカバーしており、指標が正しく定義されているかどうかを判断するための手段となります。 |
   | **[!UICONTROL 概要]** | 計算指標の定義の概要を表示します。 <br/> 例：![ イベント ](/help/assets/icons/Event.svg) **[!UICONTROL 合計注文数]** ![ 除算 ](/help/assets/icons/Divide.svg) ![ イベント ](/help/assets/icons/Event.svg) **[!UICONTROL セッション]**。 |
   | **[!UICONTROL 定義]** ![ 必須 ](/help/assets/icons/Required.svg) | [ 定義ビルダー ](#definition-builder) を使用してフィルターを定義します。 |

1. 計算指標の定義が正しいかどうかを確認するには、計算指標の結果の絶えず更新される **[!UICONTROL プレビュー]** を使用します。 **[!UICONTROL プレビュー]** は過去 90 日間をカバーし、計算指標の定義を継続的に評価します。

   **[!UICONTROL 製品の互換性]** は、計算指標を実験で使用できるかどうかを示します。 使用可能な値：
   * **[!UICONTROL Customer Journey Analytics内のすべての場所]**：計算指標は、すべてのCustomer Journey Analyticsで使用できます。
   * **[!UICONTROL Customer Journey Analyticsのすべての場所（実験を除く）]**：計算指標は、実験パネルを除くすべてのCustomer Journey Analyticsで使用できます。

1. 選択：
   * **[!UICONTROL 保存]**：計算指標を保存します。
   * **[!UICONTROL 名前を付けて保存]**：計算指標のコピーを保存します。
   * **[!UICONTROL キャンセル]**：計算指標に対して行った変更をキャンセルするか、新しい計算指標の作成をキャンセルします。


## 定義ビルダー

定義ビルダーを使用して、ディメンション、指標、フィルターおよび関数をドラッグ&amp;ドロップし、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成します。 この構成では、標準指標、Adobe定義指標、計算指標、フィルター、ディメンションおよび関数を使用できます。 これらのすべてのコンポーネントは、計算指標ビルダーのコンポーネントパネルから使用できます。 さらに、定義内で演算子やコンテナを使用できます。

![ 計算指標を作成 ](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

**[!UICONTROL 定義]** 領域では、指標のみが単一のコンポーネントとして定義されます。 その他のコンポーネントはすべて、コンテナ、ラッピング指標、またはその他のコンテナとして定義されます。 詳しくは、[ コンテナ ](#containers) を参照してください。

### 指標

指標を追加するには：

* コンポーネントパネルから ![ イベント ](/help/assets/icons/Event.svg) **[!UICONTROL 指標]** コンポーネントを **[!UICONTROL ここに指標、ディメンション、ディメンション項目、フィルター、関数をドラッグ&amp;ドロップ]** にドラッグ&amp;ドロップします。 コンポーネントバーの ![ 検索 ](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。

定義の一部として計算指標を使用すると、計算指標が展開されます。

指標を変更するには：

1. ![ 定義 ](/help/assets/icons/Setting.svg) 領域の指標コンポーネントで **[!UICONTROL 設定]** を選択します。
1. ポップアップダイアログで、指標のタイプとアトリビューションモデルを定義できます。 [ 指標タイプとアトリビューション ](m-metric-type-alloc.md) を参照してください。

指標を削除するには：

* 指標で ![ 閉じる ](/help/assets/icons/Close.svg) を選択します。

### 演算子

演算子を使用すると、コンポーネントまたはコンテナ間の演算子を指定できます。 次の期間の演算子は自動的に表示されます

* コンテナ内の 2 つ以上の指標。
* コンテナ内の 2 つ以上のコンテナ
* コンテナ内の 1 つ以上の指標と 1 つ以上のコンテナ。

以下を選択できます。

| 記号 | 演算子 |
|:---:|---|
| ![ 除算 ](/help/assets/icons/Divide.svg) | 除算（デフォルト） |
| ![閉じる](/help/assets/icons/Close.svg) | 乗算 |
| ![削除](/help/assets/icons/Remove.svg) | 減算 |
| ![追加](/help/assets/icons/Add.svg) | 追加 |

### 静的数

計算指標の定義に静的な数値を追加できます。 静的な数値を追加するには：

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Add]** を選択します。
* **[!UICONTROL 静的な数値]** を選択します。 静的な数値コンテナが表示されます。
* [!UICONTROL *クリックして値を追加*] を選択し、値を入力します。


### コンテナ

ディメンション、フィルターおよび関数をコンテナとして計算指標の定義に追加します。 汎用のコンテナを追加することもできます。 コンテナは数式のように機能し、演算の順序を指定します。コンテナ内の処理はすべて、次のコンポーネントまたはコンテナの前に行われます。


#### フィルターコンテナ

フィルターコンテナの概念を使用して、[ フィルターされた指標 ](metrics-with-segments.md) を作成します。 フィルターを使用するか、ディメンションから作成したフィルターを使用して、フィルターコンテナを作成できます。

* ディメンションからフィルターコンテナを追加するには：

   1. コンポーネントパネルから ![Dimension](/help/assets/icons/Dimensions.svg)**[!UICONTROL Dimension]** コンポーネントを **[!UICONTROL ここに指標、ディメンション、ディメンション項目、フィルター、関数]** にドラッグ&amp;ドロップします。 コンポーネントバーの ![ 検索 ](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。
   1. **[!UICONTROL Dimensionからフィルターを作成]** ポップアップで、フィルターの条件を定義します。 演算子のリストから選択し、値を選択するか、値を入力します。 例えば、**[!UICONTROL Month]****[!UICONTROL equals]**![ChevronDown](/help/assets/icons/ChevronDown.svg)`Sep 2024` です。
   1. 「**[!UICONTROL 完了]**」を選択します。 フィルターコンテナが **[!UICONTROL 定義]** に追加されます。


* フィルターからフィルターコンテナを追加するには、次を使用できます。

   * コンポーネントパネルから ![ セグメント化 ](/help/assets/icons/Segmentation.svg)**[!UICONTROL フィルター]** コンポーネントを **[!UICONTROL ここに指標、ディメンション、ディメンション項目、フィルター、関数をドラッグ&amp;ドロップ]** にドラッグ&amp;ドロップします。 コンポーネントバーの ![ 検索 ](/help/assets/icons/Search.svg) を使用して、特定のフィルターを検索できます。
自動的にフィルターコンテナが、フィルターの名前を使用して **[!UICONTROL 定義]** に追加されます。

   * ![ セグメント化 ](/help/assets/icons/Segmentation.svg)**[!UICONTROL フィルター]** コンポーネントをコンポーネントパネルから汎用コンテナにドラッグ&amp;ドロップします。 コンテナがフィルターコンテナに変更されます。

   * コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Add]** を選択します。

      1. **[!UICONTROL フィルター]** を選択します。 フィルターコンテナが **[!UICONTROL 定義]** に追加されます。
      1. 新しいフィルターコンテナで、「[!UICONTROL *選択…*]」ドロップダウンメニューからフィルターを選択します。

  >[!TIP]
  >
  >コンテナには複数のフィルターを追加できます。

  コンテナ内のフィルターは、フィルターコンポーネントに従って名前が付けられます。 例えば、![ セグメント化 ](/help/assets/icons/Segmentation.svg)**[!UICONTROL web セッション]** などです。 ![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、フィルターの詳細を含むポップアップが表示されます。 ポップアップで、「![ 編集 ](/help/assets/icons/Edit.svg) を選択して、フィルター定義を編集します。

コンテナからフィルターを削除するには：

* フィルター名の横にある「![ 閉じる ](/help/assets/icons/Close.svg)」を選択します。

詳細と例については、「[ フィルター適用済み指標 ](metrics-with-segments.md)」を参照してください。

#### 関数コンテナ

関数コンテナを追加するには、以下を使用します。

* ドラッグ アンド ドロップ：

   1. コンポーネントパネルから ![ 関数 ](/help/assets/icons/Effect.svg) **[!UICONTROL 関数]** コンポーネントを **[!UICONTROL ここに指標、ディメンション、ディメンション項目、フィルター、関数をドラッグ&amp;ドロップ]** にドラッグ&amp;ドロップします。 コンポーネントバーの ![ 検索 ](/help/assets/icons/Search.svg) を使用して、特定の関数を検索できます。
   1. 自動的に、関数の名前を使用して、関数コンテナが **[!UICONTROL 定義]** に追加されます。

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Add]** を選択します。

   1. **[!UICONTROL 関数]** を選択します。
   1. コンテナで、「選択 [!UICONTROL *ドロップダウンメニューから関数を選択*] ます。

関数コンテナの名前は、関数コンポーネントの名前を取って付けられます。 例えば、![Function](/help/assets/icons/Effect.svg)**[!UICONTROL SQUARE ROOT （metric）]** のように指定します。 「![InfoOutline](/help/assets/icons/InfoOutline.svg)」を選択すると、関数の詳細を示すポップアップが表示されます。 関数について詳しくは、**[!UICONTROL 詳細情報]** を選択してください。

関数の使用方法と計算指標の作成に使用できる関数について詳しくは、[ 関数の使用 ](cm-using-functions.md) を参照してください。


#### 汎用コンテナ

汎用コンテナを追加するには：

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL Add]** を選択します
* **[!UICONTROL コンテナ]** を選択します。 新しい空の汎用コンテナが **[!UICONTROL 定義]** に追加されます。 汎用コンテナを使用して、計算指標の定義で階層をネストまたは作成できます。


#### コンテナの削除

コンテナを削除するには、コンテナレベルで ![ 閉じる ](/help/assets/icons/Close.svg) を選択します。

>[!MORELIKETHIS]
>
>[関数の使用](cm-using-functions.md)
>[フィルター](/help/components/filters/filters-overview.md)
>

