---
description: インテリジェントキャプションを使用して自然言語のインサイトを生成し、ビジュアライゼーション内にトレンドを表示します。
title: インテリジェントキャプション
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 4d566411778774d21be04c4f3d6cf2ffabed6db2
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 16%

---

# インテリジェントキャプション {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="インテリジェントキャプション：領域"
>abstract="自然言語形式でインサイトを生成すると、このビジュアライゼーションのデータをより簡単に理解し、解釈できるようになります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="インテリジェントキャプション：棒"
>abstract="自然言語形式でインサイトを生成すると、このビジュアライゼーションのデータをより簡単に理解し、解釈できるようになります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="インテリジェントキャプション : ドーナツ"
>abstract="自然言語形式でインサイトを生成すると、このビジュアライゼーションのデータをより簡単に理解し、解釈できるようになります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="インテリジェントキャプション：横棒"
>abstract="自然言語形式でインサイトを生成すると、このビジュアライゼーションのデータをより簡単に理解し、解釈できるようになります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="インテリジェントキャプション：折れ線"
>abstract="自然言語形式でインサイトを生成すると、このビジュアライゼーションのデータをより簡単に理解し、解釈できるようになります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="インテリジェントキャプション：フォールアウト"
>abstract="自然言語形式でインサイトを生成すると、このビジュアライゼーションのデータをより簡単に理解し、解釈できるようになります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="インテリジェントキャプション：フロー"
>abstract="自然言語形式でインサイトを生成すると、このビジュアライゼーションのデータをより簡単に理解し、解釈できるようになります。"

<!-- markdownlint-enable MD034 -->

インテリジェントキャプション機能は、高度な生成 AI を使用して、自然言語で最も頻繁に使用されるWorkspaceのビジュアライゼーションに対する重要なインサイトを提供します。

インテリジェントキャプションは、次の目的に合わせて調整されます。

* 他のユーザーと共有するためにストーリーを必要とするアナリスト。 アナリストがユーザーにコンテキストを提供するには、これらのインサイトが必要です。
* ビジネスユーザーは、ハイレベルな留意点をすばやく見つけたいと考えています。

>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ インテリジェントキャプション ](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## インテリジェントキャプションを起動 {#launch}

自動生成されたビジュアライゼーションのインテリジェントキャプションを起動するには、ビジュアライゼーションの右上にある ![ インテリジェントキャプション ](/help/assets/icons/AI.svg) を選択します。 この選択により、自然言語のインサイトが生成されます。

![ 製品表示のインテリジェントキャプションのトレンドを表示するローンチ分析ウィンドウ。](assets/intelligent-captions.gif)


次の点に注意してください。

* キャプションを正常に生成するには、少なくとも 3 つのデータポイントが必要です。 そうしないと、「分析するのに十分なデータがありません **[!UICONTROL というエラーが発生する可能性があ]** ます。

* キャプションは、ビジュアライゼーションを強化するテーブルで、基になる選択されたデータが変更されるたびに生成されます。

* 関連付けられたフリーフォームテーブルに複数の指標がある場合、キャプションは、最初の指標またはユーザーが現在選択している指標に対してのみ生成されます。 ただし、線と領域のビジュアライゼーションの複数の指標に対してキャプションを生成できます。

* プロジェクトを特定の時点で保存し、後で再度読み込むと、キャプションが新しいデータで自動更新されます。 同じことが、プロジェクトから書き出されたスケジュールされたプロジェクトとPDF ファイルにも当てはまります。


## ビジュアライゼーション {#visualizations}

インテリジェントキャプションは、次のビジュアライゼーションでサポートされています。

* [ 行 ](line.md) （複数行を含む）
* [棒グラフ](bar.md)
* [横棒グラフ](horizontal-bar.md)
* [ 面積 ](area.md) （複数のエリア ラインを含む）
* [ドーナツ](donut.md)
* [フォールアウト](fallout/fallout-flow.md)
* [フロー](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## アクション

インテリジェントキャプションに対して次のアクションを実行できます。

### クリップボードにコピー {#copy}

キャプションをクリップボードにコピーして、PowerPoint やその他のツールに貼り付けることができます。 個々のキャプションを 1 つずつ表示でコピーすることも、拡張キャプションビューですべてのキャプションを一度にコピーすることもできます。

* キャプションをコピーするには、キャプションダイアログの右上にある「![ クリップボードにキャプションをコピー ](/help/assets/icons/Copy.svg)」を選択します。

### すべてまたは個々のインテリジェントキャプションを表示  {#show-all-or-individual}

拡張ビューでは、すべてのインテリジェントキャプションを一度に表示することも、個々のインテリジェントキャプションを 1 つずつ表示することもできます。

* すべてのインテリジェントキャプションを表示するには、「![ すべてのインテリジェントキャプションを表示 ](/help/assets/icons/Maximize.svg)」を選択します。
* 個々のインテリジェントキャプションを 1 つずつ表示するには、「![ 個々のインテリジェントキャプションを表示 ](/help/assets/icons/Minimize.svg)」を選択します。

### ディスプレイを編集 {#edit}

特定のカテゴリのインサイトの非表示や非表示の解除など、キャプションの表示を編集できます。

1. インテリジェントキャプションダイアログで ![ インテリジェントキャプションの表示を編集 ](/help/assets/icons/EditInLight.svg) を選択します。

1. ![ 表示を切り替え ](/help/assets/icons/Visibility.svg) 特定のインサイトを表示する（「**[!UICONTROL Min]**」など）または ![ 表示を切り替える ](/help/assets/icons/VisibilityOff.svg) 特定のインサイトを非表示にする（「**[!UICONTROL スパイク]**」など）を切り替えます。

   ![ インテリジェントキャプションを編集 ](assets/edit-intelligent-captions.png)

1. 「**[!UICONTROL 適用]**」を選択します。


### フィードバックの提供

生成されたインテリジェントキャプションに対してフィードバックを提供できます（フィードバックは、展開されたキャプション表示でのみ提供できます）。

1. インテリジェントキャプションダイアログで ![ その他のアクション ](/help/assets/icons/More.svg) を選択します。

1. 「![ 良好な応答 ](/help/assets/icons/ThumbUpOutline.svg)**[!UICONTROL 良好な応答]**」、「![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg)**[!UICONTROL 不良な応答]**」または「![ フラグ ](/help/assets/icons/Flag.svg)**[!UICONTROL レポート]**」を選択します。

1. **[!UICONTROL フィードバックをいただきありがとうございます]** ダイアログで、フィードバックを入力し、「**[!UICONTROL 送信]**」を選択してフィードバックを送信します。

### 書き出し {#export}

生成されたインテリジェントキャプションでプロジェクトが保存されている限り、PDFの一部としてインテリジェントキャプションを書き出すことができます。

### オフ {#toggle}

インテリジェントキャプションを表示しない場合は、この機能をオフに切り替えることができます。

1. [ ビジュアライゼーション環境設定 ](/help/analysis-workspace/user-preferences.md#visualizations-preferences) に移動します。
1. 「**[!UICONTROL インテリジェントキャプションを表示]**」のチェックを外します。

   ![ 「インテリジェントキャプションを表示」のチェックボックスをオフにするオプションを示す折れ線グラフのビジュアライゼーションオプション ](assets/toggle-captions.png)

1. 「**[!UICONTROL 保存]**」を選択して、環境設定を保存します。


## モバイルスコアカードのインテリジェントキャプション

インテリジェントキャプションは、Customer Journey Analytics[ モバイルスコアカード ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) でも使用できます。

## 機能へのアクセス

次のパラメーターは、インテリジェントキャプションへのアクセスを制御します。

* **ソリューションアクセス**：インテリジェントキャプション機能は、Customer Journey Analyticsでは使用できますが、Adobe Analyticsでは使用できません。

* **契約によるアクセス**：インテリジェントキャプションを使用できない場合は、組織の管理者またはAdobeアカウント担当者（管理者）にお問い合わせください。 組織でインテリジェントキャプションを使用する前に、生成 AI に関する特定の法的条項に同意する必要があります。

* **権限**: [!UICONTROL Adobe Admin Console] では、[!UICONTROL  レポートツール ]**[!UICONTROL インテリジェントキャプション]** 権限によってアクセスが決まります。 [ 製品プロファイル管理者 ](https://helpx.adobe.com/jp/enterprise/using/manage-product-profiles.html) は、[!UICONTROL Admin Consoleの次の手順に従う必要があり ] す。
   1. **[!UICONTROL Admin Console]** / **[!UICONTROL 製品およびサービス]** / **[!UICONTROL 製品]** / **[!UICONTROL Customer Journey Analyticsプロファイル]** に移動します。
   1. インテリジェントキャプションへのアクセスを提供する製品プロファイルのタイトルを選択します。
   1. 特定の製品プロファイルで、「**[!UICONTROL 権限]**」を選択します。
   1. ![ 編集 ](/help/assets/icons/Edit.svg) を選択して **[!UICONTROL レポートツール]** を編集します。
   1. ![AddCircle](/help/assets/icons/AddCircle.svg) を選択して、**インテリジェントキャプション** を **[!UICONTROL 含まれる権限項目]** に追加します。

      ![ 権限を追加 ](./assets/intelligent-captions-permissions.png)

   1. 「**[!UICONTROL 保存]**」を選択して、権限を保存します。

詳しくは、[ アクセス制御 ](/help/technotes/access-control.md#access-control) を参照してください。
