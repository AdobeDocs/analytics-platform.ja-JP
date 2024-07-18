---
description: 計算指標ビルダーを使用して、誰でもパーティシペーション指標を作成できます。
title: パーティシエーション指標
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# パーティシペーション指標の作成

この記事では、パーティシペーション指標の作成方法を説明します。 パーティシペーション指標は、ディメンション（ページビュー数、マーケティングチャネルなど）の個々の値が、特定の指標（注文など）を含むセッションにどのように貢献し、またはどのようにセッションに参加するかを示します。

このタイプの情報は、あらゆるコンテンツ所有者に役立つ可能性があります。

>[!NOTE]
>
>パーティシペーションなどの他のアトリビューションモデルを使用した指標は、管理者が [ データビュー ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja) の一部として作成することもできます。 詳しくは、[ アトリビューションコンポーネントの設定 ](../../../data-views/component-settings/attribution.md) を参照してください。<br/> 以下の例は、Workspaceの計算指標ビルダーにアクセスできるユーザーがパーティシペーション指標を作成する方法を示しています。


1. 指標の作成を開始します。詳しくは、[ 指標の作成 ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) を参照してください。
1. 計算指標ビルダーで、指標に `Participation` などの名前を付けます。
1. 成功イベントを含む指標（例：[!DNL Orders]）を [!UICONTROL  定義 ] キャンバスにドラッグします。
1. 指標の ![ 歯車 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) を選択します。
1. 表示されるポップアップで、「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」を選択して [ パーティシペーション ](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) に対するそのイベントの **[!UICONTROL アトリビューションモデル]** を定義し、「[!UICONTROL  ルックバックウィンドウ ] に対して **[!UICONTROL セッション]** を選択します。 「**[!UICONTROL 適用]**」を選択して確定します。

   「定義」ボックスで、名前に **（Partitpation|Session）** を追加すると、選択した指標が更新されます。

   ![ モデルとしてパーティシペーションが選択され、ルックバックウィンドウにセッションが選択されていることを示す列アトリビューションモデルのポップアップ ](assets/participation-setup.png)



1. 「[!UICONTROL **保存**]」を選択して、指標を保存します。
1. レポートで計算指標を使用します。 例えば、レポートで計算された [!DNL Orders (Session Participation)] 指標（手順 5 で定義）を使用して、どの顧客層が注文を含むセッションに貢献（または参加）したかを示します。

   ![ 顧客の階層と注文を示すフリーフォームテーブル。](assets/participation-pages-customer-tier.png)

1. （任意） [ 計算指標の共有 ](/help/components/calc-metrics/cm-workflow/cm-sharing.md) の説明に従って、組織の他のユーザーと指標を共有します。
