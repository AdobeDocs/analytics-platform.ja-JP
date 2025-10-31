---
title: アトリビューションコンポーネントの設定
description: 指標のデフォルトのアトリビューションを設定できます。
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 2fd79da264d60bb90e1193ead2eee67602404b4c
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 63%

---

# アトリビューションコンポーネントの設定 {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="アトリビューション"
>abstract="レポートの指標に適用されるデフォルトのアトリビューションモデルを設定します。"

<!-- markdownlint-enable MD034 -->


アトリビューションを使用すると、ディメンション項目で成功イベントのクレジットを取得する方法をカスタマイズできます。

例：

1. サイトのユーザーが、いずれかの製品ページへの有料検索リンクをクリックします。製品を買い物かごに追加しますが、購入はしません。
2. 次の日に、ユーザーは友達の 1 人からのソーシャルメディアの投稿を見ます。リンクをクリックし、購入を完了します。

一部のレポートでは、注文を有料検索に関連付けることが望まれるかもしれません。他のレポートでは、注文を「ソーシャル」に関連付けることが望まれるかもしれません。アトリビューションを使用すると、レポートのこのような側面を制御できます。

## コンポーネントのアトリビューションモデルの設定

データビューでコンポーネントの設定を更新することで、特定のコンポーネントのデフォルトのアトリビューションモデルを変更できます。 これにより、Analysis Workspaceで使用されるたびに、コンポーネントのアトリビューションモデルが上書きされます。

>[!NOTE]
>
>指標でデフォルト以外のアトリビューションモデルを有効にする場合は、次の点を考慮してください。
>
>* ***単一のディメンション* でレポートで指標を使用する場合：** 指標のアトリビューションが、ディメンションに設定された配分モデルを上書きします。 例えば、「ファーストタッチ」アトリビューションを持つ指標は、「最新」のディメンション配分を上書きします。
>
>* ***複数のディメンション* を含むレポートで指標を使用する場合：** 指標のアトリビューションが、各ディメンションの配分モデルの上に適用されます。 例えば、「ファーストタッチ」アトリビューションを持つ指標は、「最新」のディメンション配分の上に適用されます。
>
> 配分について詳しくは、[コンポーネントの永続性設定](/help/data-views/component-settings/persistence.md)を参照してください。

コンポーネントのデフォルトのアトリビューションモデルを更新するには：

1. デフォルトのアトリビューションモデルを更新するコンポーネントを含むデータビューに移動します。

1. コンポーネントを選択して、画面の右側にある **[!UICONTROL アトリビューション]** セクションを展開します。

   ![「アトリビューションを設定」オプションをハイライト表示するデータビューウィンドウ](../assets/attribution-settings.png)

1. [!UICONTROL **アトリビューションを設定**] を選択してから、[&#x200B; アトリビューションモデル &#x200B;](#attribution-models)、[&#x200B; コンテナ &#x200B;](#container)、[&#x200B; ルックバック &#x200B;](#lookback-window) ウィンドウを選択します。



1. 「[!UICONTROL **保存して続行**]」を選択します。

>[!TIP]
>
>組織で指標に複数のアトリビューション設定が必要な場合は、次のいずれかを実行できます。
>
> * 目的のアトリビューション設定ごとに、データビューで指標をコピーします。同じ指標をデータビューに複数回含めて、各指標に異なる設定を指定できます。アナリストがレポートを生成する際にこれらの指標の違いを理解できるように、各指標に適切なラベルを付けてください。
>
> * Analysis Workspace の指標を上書きします。指標の[列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)で、「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」を選択して、その特定のレポートの指標のアトリビューションモデルとルックバックウィンドウを変更します。

## アトリビューションモデル {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="モデル"
>abstract="指標のアトリビューションモデルを選択します。"

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## コンテナ

{{attribution-container}}

## ルックバックウィンドウ

{{attribution-lookback-window}}

## 例

{{attribution-example}}
