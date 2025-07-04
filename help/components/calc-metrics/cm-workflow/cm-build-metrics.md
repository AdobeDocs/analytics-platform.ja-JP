---
description: 計算指標ビルダーは、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルール、演算子に基づいてカスタム指標を作成するためのキャンバスです。この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。
title: 計算指標の作成
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: ec2fc88372814b01a04d4cc824181222ee55a83d
workflow-type: tm+mt
source-wordcount: '1628'
ht-degree: 94%

---

# 計算指標の作成 {#build-metrics}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="製品の互換性"
>abstract="Analysis Workspace、Report Builder など、この計算指標を使用できる Customer Journey Analytics の場所を示します。一部の計算指標は、実験では使用できません。"
>additional-url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="実験での計算指標の使用"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="外部 ID を変更すると、ビジネスインテリジェンスツールなどの外部ソースでの計算指標の表示方法に影響する可能性があります"

Customer Journey Analytics には、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルール、演算子に基づいてカスタム指標を作成できる、キャンバスが用意されています。この統合開発ツールでは、シンプルまたは複雑な計算指標を作成および保存できます。

計算指標ビルダーを使用して、計算指標を作成または編集できます。この方法で作成すると、コンポーネントリストで計算指標を使用できるようになります。このリストは、組織全体のプロジェクトで使用できます。または、[指標](/help/components/apply-create-metrics.md)の[単一プロジェクトの計算指標の作成](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)の説明に従って、作成されたプロジェクトでのみ使用可能な計算指標をすばやく作成することもできます。

[ 計算指標の作成 ](cm-workflow.md) では、新しい計算指標の作成に使用できる様々なオプションについて説明します。

## 計算指標ビルダーのエリア

**[!UICONTROL 計算指標ビルダー]**&#x200B;ダイアログは、新しい計算指標の作成または既存の計算指標の編集に使用します。ダイアログのタイトルは、[[!UICONTROL 計算指標]マネージャー](/help/components/calc-metrics/cm-workflow/cm-manager.md)から作成または管理する指標の場合、**[!UICONTROL 新しい計算指標]**&#x200B;または&#x200B;**[!UICONTROL 計算指標を編集]**&#x200B;になります。

>[!BEGINTABS]

>[!TAB 計算指標ビルダー]

![次の節で説明するフィールドとオプションを表示する計算指標の詳細ウィンドウ。](assets/calculated-metric-builder.png)

>[!TAB 計算指標の作成または編集]

![次の節で説明するフィールドとオプションを表示する計算指標の詳細ウィンドウ。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 次の詳細を指定します（![必須](/help/assets/icons/Required.svg)は必須です）。

   | 要素 | 説明 |
   | --- | --- |
   | **[!UICONTROL データビュー]** | 計算指標のデータビューを選択できます。定義した計算指標は、選択したデータビューに基づいて、Workspace プロジェクトで使用できます。 |
   | **[!UICONTROL プロジェクトのみの指標]** | [単一プロジェクトの計算指標の作成](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)の説明に従って、単一プロジェクト用に作成された計算指標を編集すると、このダイアログの上部に情報ボックスが表示されます。 <p>この計算指標をすべてのプロジェクトで使用できるようにする場合は、「**[!UICONTROL この指標をすべてのプロジェクトで使用できるようにし、コンポーネントリストに追加]**」オプションを選択します。</p> |
   | **[!UICONTROL タイトル]** ![必須](/help/assets/icons/Required.svg) | 計算指標に名前を付けます（例：`Conversion Rate`）。 |
   | **[!UICONTROL 外部 ID]** ![必須](/help/assets/icons/Required.svg) | 外部 BI ツールと BI 拡張機能を使用する際の計算指標の名前。値を上書きしない限り、値は自動的に `undefined_xxx` として定義されます。 |
   | **[!UICONTROL 説明]** | セグメントの説明を入力します（例：`Calculated metric to define the conversion rate.`）。計算指標の数式は既に[!UICONTROL 概要]で自動的に使用できるので、数式を説明する必要はありません。 |
   | **[!UICONTROL 形式]** | 計算指標の形式を選択します。**[!UICONTROL 小数]**、**[!UICONTROL 時間]**、**[!UICONTROL 割合]**、**[!UICONTROL 通貨]**&#x200B;から選択できます。 |
   | **[!UICONTROL 小数点以下の桁数]** | 選択した形式の小数点以下の桁数を指定します。選択した形式が小数、通貨、割合である場合にのみ有効になります。 |
   | **[!UICONTROL 上昇傾向を次の形式で表示]** | 計算指標の上昇傾向を ▲ **[!UICONTROL 良（緑）または ▼**&#x200B;[!UICONTROL &#x200B; 悪（赤） &#x200B;]&#x200B;**ど]** 表示するかを指定します。 |
   | **[!UICONTROL 通貨]** | 計算指標の通貨を指定します。選択した形式が通貨である場合にのみ有効になります。 |
   | **[!UICONTROL タグ]** | 1 つ以上のタグを作成または適用して、計算指標を整理します。入力を開始すると、選択できる既存のタグが見つかります。または、**[!UICONTROL Enter]** キーを押して新しいタグを追加します。「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択して、タグを削除します。 |
   | **[!UICONTROL プレビュー]** | プレビューは過去 90 日間をカバーしており、指標が正しく定義されているかどうかを判断するための手段となります。 |
   | **[!UICONTROL 概要]** | 計算指標の定義の概要を表示します。<br/>例：![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 合計注文数]** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL セッション]**。 |
   | **[!UICONTROL 定義]** ![必須](/help/assets/icons/Required.svg) | [定義ビルダー](#definition-builder)を使用して、セグメントを定義します。 |

1. 計算指標の定義が正しいかどうかを確認するには、計算指標の結果の絶えず更新される&#x200B;**[!UICONTROL プレビュー]**&#x200B;を使用します。**[!UICONTROL プレビュー]**&#x200B;は過去 90 日間をカバーしており、計算指標の定義を継続的に評価します。

   **[!UICONTROL 製品の互換性]**&#x200B;は、計算指標を実験で使用できるかどうかを示します。使用可能な値：
   * **[!UICONTROL Customer Journey Analytics のすべての場所]**：計算指標は、Adobe Customer Journey Analytics 全体で使用できます。
   * **[!UICONTROL Customer Journey Analytics のすべての場所 (実験を除く)]**：計算指標は、実験パネルを除く Adobe Customer Journey Analytics 全体で使用できます。

1. 次のいずれかを選択します。
   * 計算指標を保存する場合は、「**[!UICONTROL 保存]**」。
   * 計算指標のコピーを保存する場合は、「**[!UICONTROL 名前を付けて保存]**」。
   * 計算指標に対して行った変更をキャンセルするか、新しい計算指標の作成をキャンセルする場合は、「**[!UICONTROL キャンセル]**」。


## 定義ビルダー

定義ビルダーを使用すると、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップして、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成できます。この作成では、標準指標、アドビ定義の指標、計算指標、セグメント、ディメンションおよび関数を使用できます。これらのコンポーネントはすべて、計算指標ビルダーのコンポーネントパネルから使用できます。さらに、演算子やコンテナも定義で使用できます。

![計算指標を作成](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

**[!UICONTROL 定義]**&#x200B;エリアでは、指標のみが単一のコンポーネントとして定義されます。その他のコンポーネントはすべて、コンテナ、ラッピング指標またはその他のコンテナとして定義されます。詳しくは、[コンテナ](#containers)を参照してください。

### 指標

指標を追加するには：

* コンポーネントパネルから ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 指標]**&#x200B;コンポーネントを&#x200B;**[!UICONTROL ここに指標、ディメンション、ディメンション項目、セグメント、関数をドラッグ＆ドロップ]**&#x200B;にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。

定義の一部として計算指標を使用すると、その計算指標が展開されます。

指標を変更するには：

1. **[!UICONTROL 定義]**&#x200B;エリアの指標コンポーネントで「![設定](/help/assets/icons/Setting.svg)」を選択します。
1. ポップアップダイアログで、指標のタイプとアトリビューションモデルを定義できます。[指標タイプとアトリビューション](m-metric-type-alloc.md)を参照してください。

指標を削除するには：

* 指標の「![閉じる](/help/assets/icons/Close.svg)」を選択します。

### 演算子

演算子を使用すると、コンポーネント間またはコンテナ間の演算子を指定できます。以下の項目の間には演算子が自動的に表示されます。

* コンテナ内の 2 つ以上の指標
* コンテナ内の 2 つ以上のコンテナ
* コンテナ内の 1 つ以上の指標と 1 つ以上のコンテナ

以下を選択できます。

| 記号 | 演算子 |
|:---:|---|
| ![除算](/help/assets/icons/Divide.svg) | 除算（デフォルト） |
| ![閉じる](/help/assets/icons/Close.svg) | 乗算 |
| ![削除](/help/assets/icons/Remove.svg) | 減算 |
| ![追加](/help/assets/icons/Add.svg) | 追加 |

### 静的な数値

計算指標の定義に静的な数値を追加できます。静的な数値を追加するには：

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。
* 「**[!UICONTROL 静的な数値]**」を選択します。静的な数値コンテナが表示されます。
* 「[!UICONTROL *クリックして値を追加*]」を選択し、値を入力します。


### コンテナ

ディメンション、セグメントおよび関数をコンテナとして計算指標の定義に追加します。また、汎用コンテナを追加することもできます。コンテナは数式のように機能し、演算の順序を指定します。コンテナ内のものはすべて、次のコンポーネントまたはコンテナの前に処理されます。


#### セグメントコンテナ

セグメントコンテナの概念を使用すると、[セグメント適用済み指標](metrics-with-segments.md)を作成できます。セグメントコンテナを作成するには、セグメントを使用するか、ディメンションから作成したセグメントを使用します。

* ディメンションからセグメントコンテナを追加するには：

   1. コンポーネントパネルから ![ディメンション](/help/assets/icons/Dimensions.svg) **[!UICONTROL ディメンション]**&#x200B;コンポーネントを&#x200B;**[!UICONTROL ここに指標、ディメンション、ディメンション項目、セグメント、関数をドラッグ＆ドロップ]**&#x200B;にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。
   1. **[!UICONTROL Dimensionからセグメントを作成]** ポップアップで、セグメントの条件を定義します。 演算子のリストから選択し、値を選択するか入力します。例えば、**[!UICONTROL 月]** **[!UICONTROL 次に等しい]** ![ChevronDown](/help/assets/icons/ChevronDown.svg)`Sep 2024` などとなります。
   1. 「**[!UICONTROL 完了]**」を選択します。セグメントコンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に追加されます。


* セグメントからセグメントコンテナを追加するには、以下を使用します。

   * コンポーネントパネルから ![セグメント化](/help/assets/icons/Segmentation.svg) **[!UICONTROL セグメント]**&#x200B;コンポーネントを&#x200B;**[!UICONTROL ここに指標、ディメンション、ディメンション項目、フィルター、関数をドラッグ＆ドロップ]**&#x200B;にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定のセグメントを検索できます。
セグメントの名前を使用すると、セグメントコンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に自動的に追加されます。

   * ![ セグメント化 ](/help/assets/icons/Segmentation.svg)**[!UICONTROL セグメント]** コンポーネントをコンポーネントパネルから汎用コンテナにドラッグ&amp;ドロップします。 コンテナがセグメントコンテナに変更されます。

   * コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。

      1. **[!UICONTROL セグメント]** を選択します。 セグメントコンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に追加されます。
      1. 新しいセグメントコンテナで、「[!UICONTROL *選択…*]」ドロップダウンメニューからセグメントを選択します。

  >[!TIP]
  >
  >複数のセグメントをコンテナに追加できます。

  コンテナ内のセグメントは、セグメントコンポーネントにちなんで名前が付けられます。例えば、![セグメント化](/help/assets/icons/Segmentation.svg) **[!UICONTROL web セッション]**&#x200B;などです。![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、セグメントの詳細を含んだポップアップが表示されます。このポップアップで、![編集](/help/assets/icons/Edit.svg) を選択して、セグメント定義を編集します。

コンテナからセグメントを削除するには：

* セグメント名の横にある ![閉じる](/help/assets/icons/Close.svg) を選択します。

詳細と例については、[ セグメント化指標 ](metrics-with-segments.md) を参照してください。

#### 関数コンテナ

関数コンテナを追加するには、次の手順を使用します。

* ドラッグ＆ドロップ：

   1. コンポーネントパネルから ![関数](/help/assets/icons/Effect.svg) **[!UICONTROL 関数]**&#x200B;コンポーネントを「**[!UICONTROL ここに指標、ディメンション、ディメンション項目、セグメント、関数をドラッグ＆ドロップ]**」にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定の関数を検索できます。
   1. 関数の名前を使用すると、関数コンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に自動的に追加されます。

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。

   1. 「**[!UICONTROL 関数]**」を選択します。
   1. コンテナで、「[!UICONTROL *選択…*]」ドロップダウンメニューから関数を選択します。

関数コンテナの名前は、関数コンポーネントの名前を取って付けられます。例：![関数](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (metric)]**。![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、機能の詳細を含むポップアップが表示されます。関数について詳しくは、「**[!UICONTROL 詳細情報]**」を選択してください。

関数の使用方法と計算指標の作成に使用できる関数について詳しくは、[関数の使用](cm-using-functions.md)を参照してください。


#### 汎用コンテナ

汎用コンテナを追加するには：

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。
* 「**[!UICONTROL コンテナ]**」を選択します。 新しい空の汎用コンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に追加されます。汎用コンテナを使用して、計算指標の定義で階層をネストまたは作成できます。


#### 接続の削除

コンテナを削除するには、コンテナレベルで ![閉じる](/help/assets/icons/Close.svg) を選択します。

>[!MORELIKETHIS]
>
>[関数の使用](cm-using-functions.md)
>&#x200B;>[セグメント ](/help/components/segments/seg-overview.md)
>
