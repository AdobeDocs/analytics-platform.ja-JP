---
description: 計算指標ビルダーを使用して、誰でもパーティシペーション指標を作成できます。
title: パーティシペーション指標
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 6%

---

# パーティシペーション指標の作成

この記事では、パーティシペーション指標の作成方法を説明します。 パーティシペーション指標は、ディメンションの個々の値（ページビュー数、マーケティングチャネルなど）が、特定の指標（注文件数など）を含むセッションにどのように貢献し、参加するかを示します。

このタイプの情報は、コンテンツ所有者にとって役立つ場合があります。

>[!NOTE]
>
>パーティシペーションなど、他のアトリビューションモデルを持つ指標は、 [データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja). 詳しくは、 [アトリビューションコンポーネントの設定](../../../data-views/component-settings/attribution.md) を参照してください。<br/>次の例は、Workspace の計算指標ビルダーへのアクセス権を持つ任意のユーザーがパーティシペーション指標を作成する方法を示しています。


1. 指標の作成を開始します ( [指標の作成](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 計算指標ビルダーで、指標に名前を付けます。 `Participation` 似たようなものです。
1. 成功イベントを含む指標をドラッグします（例： ）。 [!DNL Orders]、 [!UICONTROL 定義] キャンバス。
1. 選択 ![ギア](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) を参照してください。
1. 表示されるポップアップで、「 」を選択します。 **[!UICONTROL デフォルト以外のアトリビューションモデルを使用]** を定義するには、 [アトリビューションモデル](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) その出来事が **[!UICONTROL パーティシペーション]** を選択し、 **[!UICONTROL セッション]** （の） [!UICONTROL ルックバックウィンドウ]. 選択 **[!UICONTROL 適用]** をクリックして確定します。

   「定義」ボックスで、選択した指標が  **（加入│集会）** を名前に追加します。

   ![モデルとして選択されたパーティシペーションと、ルックバックウィンドウ用に選択されたセッションを示す列アトリビューションモデルポップアップ。](assets/participation-setup.png)



1. 選択 [!UICONTROL **保存**] をクリックして指標を保存します。
1. レポートで計算指標を使用します。 例えば、計算指標の [!DNL Orders (Session Participation)] （手順 5 で定義した）レポートの指標。注文を含むセッションに貢献した（または関係した）顧客層を示します。

   ![顧客層と注文を示すフリーフォームテーブル。](assets/participation-pages-customer-tier.png)

1. （オプション）指標を組織内の他のユーザーと共有します。詳しくは、 [計算指標の共有](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
