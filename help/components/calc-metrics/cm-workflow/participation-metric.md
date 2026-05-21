---
description: 参加指標の作成方法を説明します。
title: パーティシペーション指標
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
TQID: https://experienceleague.adobe.com/no7rAZUl25LTEPqwRyC7vY4XcottzPGRq-DCAR5ez54
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 9%

---

# パーティシペーション指標

参加指標は、ディメンションの個々の値（ページビューなど）が、特定の指標（注文数など）を含むセッションに貢献したり、参加したりする方法を定量化するために使用されます。

>[!NOTE]
>
>管理者は、[ データビュー](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/data-views)の一部として、参加などのデフォルト以外のアトリビューションモデルを使用して指標を作成できます。 詳しくは、[ アトリビューションコンポーネント設定](../../../data-views/component-settings/attribution.md)を参照してください。

以下の手順は、[計算指標の作成権限](/help/technotes//access-control.md#user-level-access)を持つユーザーが参加指標を作成する方法を示しています。

1. [計算指標](cm-workflow.md)を作成し、[計算指標ビルダー](cm-build-metrics.md)で、指標`Participation`または類似の名前を付けます。
1. 成功イベントを含む指標（例：[!DNL Orders]）を[!UICONTROL **[!UICONTROL 定義]**]領域にドラッグします。
1. 指標に「![歯車](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)」を選択します。
1. 表示されるポップアップで、**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**&#x200B;を選択して、そのイベントの[ アトリビューションモデル ](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)を&#x200B;**[!UICONTROL 参加]**&#x200B;に定義し、[!UICONTROL  コンテナ ]の&#x200B;**[!UICONTROL セッション]**&#x200B;を選択します。 「**[!UICONTROL 適用]**」を選択して確認します。


   ![列アトリビューションモデルのポップアップに、「モデルとして選択された参加」と「ルックバックウィンドウ用に選択されたセッション」が表示されている](assets/participation-setup.png)。

   **（パーティション|セッション）**&#x200B;が指標コンポーネント名に追加されます。



1. [!UICONTROL **保存**]&#x200B;を選択して、指標を保存します。
1. レポートで計算指標を使用します。 例えば、レポートで計算された[!DNL Orders (Session Participation)]指標を使用して、注文を含むセッションに貢献した（または参加した）顧客層を表示します。

   顧客層と注文を示す![ フリーフォームテーブル。](assets/participation-pages-customer-tier.png)
