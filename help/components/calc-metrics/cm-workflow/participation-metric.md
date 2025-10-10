---
description: パーティシペーション指標の作成方法を説明します。
title: パーティシペーション指標
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 2%

---

# パーティシペーション指標

パーティシペーション指標は、ディメンション（ページビューなど）の個々の値が、特定の指標（注文など）を含むセッションにどのように貢献し、またはどのようにセッションに参加するかを定量化するために使用されます。

>[!NOTE]
>
>管理者は、[&#x200B; データビュー &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/data-views) の一部として、パーティシペーションなどのデフォルト以外のアトリビューションモデルを使用して指標を作成できます。 詳しくは、[&#x200B; アトリビューションコンポーネントの設定 &#x200B;](../../../data-views/component-settings/attribution.md) を参照してください。

次の手順では、[&#x200B; 計算指標の作成 &#x200B;](/help/technotes//access-control.md#user-level-access) 権限を持つユーザーがパーティシペーション指標をどのように作成できるかを示します。

1. [&#x200B; 計算指標を作成 &#x200B;](cm-workflow.md) し、[&#x200B; 計算指標ビルダー &#x200B;](cm-build-metrics.md) で、指標に `Participation` などの名前を付けます。
1. 成功イベントを含む指標（例：[!DNL Orders]）を [!UICONTROL **[!UICONTROL &#x200B; 定義 &#x200B;]**] 領域にドラッグします。
1. 指標の ![&#x200B; 歯車 &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) を選択します。
1. 表示されるポップアップで、**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]** を選択して [&#x200B; パーティシペーション &#x200B;](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) に対するそのイベントの **[!UICONTROL アトリビューションモデル]** を定義し、**[!UICONTROL コンテナ]** に対して [!UICONTROL &#x200B; セッション &#x200B;] を選択します。 「**[!UICONTROL 適用]**」を選択して確定します。


   ![&#x200B; モデルとしてパーティシペーションが選択され、ルックバックウィンドウにセッションが選択されていることを示す列アトリビューションモデルのポップアップ &#x200B;](assets/participation-setup.png)

   指標コンポーネント名に **（Partitation|Session）** が追加されます。



1. 「[!UICONTROL **保存**]」を選択して、指標を保存します。
1. レポートで計算指標を使用します。 例えば、レポート内の計算 [!DNL Orders (Session Participation)] 指標を使用して、どの顧客層が注文を含むセッションに貢献（または参加）したかを示します。

   ![&#x200B; 顧客の階層と注文を示すフリーフォームテーブル。](assets/participation-pages-customer-tier.png)
