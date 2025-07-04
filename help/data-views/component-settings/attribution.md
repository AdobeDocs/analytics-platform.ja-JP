---
title: アトリビューションコンポーネントの設定
description: 指標のデフォルトのアトリビューションを設定できます。
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 93%

---

# アトリビューションコンポーネントの設定 {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="アトリビューション"
>abstract="レポートの指標に適用されるデフォルトのアトリビューションモデルを設定します。"

<!-- markdownlint-enable MD034 -->


アトリビューションを使用すると、ディメンション項目で成功イベントのクレジットを取得する方法をカスタマイズできます。

![「アトリビューションを設定」オプションをハイライト表示するデータビューウィンドウ](../assets/attribution-settings.png)

例：

1. サイトのユーザーが、いずれかの製品ページへの有料検索リンクをクリックします。製品を買い物かごに追加しますが、購入はしません。
2. 次の日に、ユーザーは友達の 1 人からのソーシャルメディアの投稿を見ます。リンクをクリックし、購入を完了します。

一部のレポートでは、注文を有料検索に関連付けることが望まれるかもしれません。他のレポートでは、注文を「ソーシャル」に関連付けることが望まれるかもしれません。アトリビューションを使用すると、レポートのこのような側面を制御できます。

## コンポーネントのデフォルトのアトリビューションモデルの設定

データビューで指標の設定を更新することで、特定の指標に対してデフォルトのアトリビューションモデルを設定できます。これにより、Analysis Workspaceで使用されるたびに指標のアトリビューションモデルが上書きされます。

>[!NOTE]
>
>指標でアトリビューションを有効にする際は、次の点を考慮してください。
>
>* ***単一のディメンション*を持つレポートでコンポーネントを使用する場合：**&#x200B;デフォルト以外のアトリビューションモデルを使用する場合、コンポーネントのアトリビューションでは配分モデルが無視されます。
>
>* ***複数のディメンション*を持つレポートでコンポーネントを使用する場合：**&#x200B;デフォルト以外のアトリビューションモデルを使用する場合、コンポーネントのアトリビューションでは配分モデルが保持されます。
>
>   複数のディメンションは、[クラウドへのデータの書き出し](/help/analysis-workspace/export/export-cloud.md)時にのみ使用できます。
>
> 配分について詳しくは、[コンポーネントの永続性設定](/help/data-views/component-settings/persistence.md)を参照してください。

コンポーネントのデフォルトのアトリビューションモデルを更新するには：

1. デフォルトのアトリビューションモデルを更新するコンポーネントを含むデータビューに移動します。

1. コンポーネントを選択して、画面の右側にある **[!UICONTROL アトリビューション]** セクションを展開します。

   ![「アトリビューションを設定」オプションをハイライト表示するデータビューウィンドウ](../assets/attribution-settings.png)

1. [!UICONTROL **アトリビューションを設定**] を選択してから、[ アトリビューションモデル ](#attribution-models)、[ コンテナ ](#container)、[ ルックバック ](#lookback-window) ウィンドウを選択します。



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
