---
description: 権限に応じて、指標を組織全体、グループまたは個々のユーザーと共有できます。
title: 計算指標の共有
feature: Calculated Metrics
exl-id: b2a3e4e3-f0aa-4505-b3f5-7d9f14dc1640
source-git-commit: b3c7ceedec7b3f6a916e97bab38fd55f1d6c7f51
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 11%

---

# 計算指標の共有

[ 計算指標マネージャー ](cm-manager.md) で、計算指標を共有できます。 権限に応じて、計算指標を組織全体、グループまたは個々のユーザーと共有できます。

* **管理者**：管理者は、計算指標を組織全体、組織内のグループおよび個々のユーザーと共有できます。 詳しくは、[Admin Console のドキュメント](https://helpx.adobe.com/jp/enterprise/using/manage-products.html)を参照してください。
* **管理者以外**：管理者以外のユーザーは、自身が作成した計算指標を共有でき、個々のユーザーとのみ共有できます。

1 つ以上の計算指標を共有するには：

1. [ 計算指標マネージャー ](cm-manager.md) で、共有する計算指標を 1 つ以上選択します。
1. アクションバーの「![ 共有 ](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共有]**」を選択します。
1. **[!UICONTROL 計算指標を共有]** ダイアログで、次の手順を実行します。

   ![ 計算指標を共有ダイアログ ](assets/share-calculated-metrics-dialog.png)

   1. （オプション） ![ 検索 ](/help/assets/icons/Search.svg) を使用して *個人またはグループを検索*、計算指標を共有するグループまたは個人のリストを制限します。

   1. 「**[!UICONTROL 組織]**」セクションまたは「**[!UICONTROL グループ]**」セクションから 1 つ以上のオプションを選択するか、1 人または複数の個人を検索して選択します。 使用できるオプションは、の役割によって異なります。

   1. 「**[!UICONTROL 保存]**」を選択して、計算指標を共有します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

## ベストプラクティス

以下は、計算指標を共有する必要がある場合と、計算指標を共有する必要がある場合のベストプラクティスです。

* 管理者は、組織内の誰かが計算指標を使用するのに慣れていると確信している場合にのみ、計算指標を「すべて」と共有します。 また、これらの計算指標のお気に入りを検討することもできます。 詳しくは [ 計算指標をお気に入りとしてマーク ](cm-favorite.md) を参照してください。

* 計算指標が特定のグループのユーザーにビジネス価値を提供する場合、管理者はそのグループと計算指標を共有します。

* 管理者または個々のユーザーは、計算指標を 1 人以上の個人と共有して計算指標を検証します。 セグメントが役に立つことが証明されない場合は、計算指標を削除できます。


<!--

Depending on your permissions, you can share metrics with your whole organization, groups, or individual users.

|  Role | Permissions |
|---|---|
|  Administrator  | Can share metrics with All, with Groups, and with Users. Groups are set up as permission groups in the Admin console.  |
|  Non-Administrator  | Can share metrics only with individual users.  |

To share a calculated metric:

1. In the Calculated metrics manager, mark the checkbox next to the metric you want to share.

   ![Calculated metrics manager showing the available icons across the top of the window including Hide Filters, Tag, Share, Delete, and Copy.](assets/cm_task_bar.png)

1. Select the **[!UICONTROL Share]** icon. ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

   The Share Calculated metric dialog box displays.

   ![Share Calculated metric window with All selected for the Organization.](assets/cm_share.png)

1. Select **[!UICONTROL Share]**.

1. Choose who you want to share with:

   * **[!UICONTROL All]** (Administrators only): Shares with all users in the organization.

     Consider sharing with all only if it's of use to the entire company and everyone is comfortable using it. In this case, you should also consider making it an [approved metric](/help/components/calc-metrics/cm-workflow/cm-approving.md).
   
   * **[!UICONTROL Groups]** (Administrators only): Select any groups you want to share with.

     Consider sharing with a group if the metric provides good business value for that team.
   
   * **[!UICONTROL Individual users]**: Search for and select the individual users you want to share with.

      This is the only share option available to all users. Administrators might want to use this option to vet and validate a metric prior to making it available to a group or to everyone. If the metric isn't useful, it can be discarded. Administrators should not officially approve this type of metric.

1. Select **[!UICONTROL Share]**.

   The Shared icon appears next to the metric: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg).

1. You can filter on metrics shared with you by going to **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

1. (Optional) To filter the list of calculated metrics in the Calculated metrics manager to show only metrics that are shared with you, select the **Filter** icon, expand **[!UICONTROL Other filters]**, then select **[!UICONTROL Shared with me]**.

-->