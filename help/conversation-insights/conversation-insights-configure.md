---
title: 会話インサイト設定の作成または編集
description: 会話インサイト設定の設定方法について説明します。
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 4eaf8820fd847426ba6a471e1bfbc7b397283905
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 7%
---
# 設定の作成または編集

会話インサイトを活用すれば、顧客に提供するエージェント体験から会話を分析できます。 そのようなエージェントの体験は、大規模言語モデル（LLM）にもとづいて提供されるか、または人間の会話にもとづいて提供されます。 たとえば、顧客やコールセンターとのやり取りを担当するチャットボットは、文字起こしを処理します。
会話インサイトを通じて、実際のユーザーの成果に対する代表者の影響を把握することができます。

会話インサイト設定インターフェイスを使用すると、設定と関連するアーティファクト（接続、データビューなど）をすばやく作成または編集できます。

会話インサイト設定を作成または編集する際に、プロンプト、応答、フィードバックデータを含むサンドボックスとイベントデータセットを指定します。 また、これらのデータセットを追加するCustomer Journey Analytics接続も選択します。 会話インサイトの指標とディメンションを追加するデータビュー。

会話インサイト設定を作成または編集できるのはシステム管理者のみです。

[会話インサイト設定インターフェイス &#x200B;](./conversation-insights-manage.md)から設定を作成または編集します。

## 欠落しているブレンド済みデータセットを復元

設定を編集し、その設定のために生成されたブレンドデータセットが存在しなくなった場合は、**[!UICONTROL 復元]**&#x200B;を選択して、ブレンドデータセットを再生成します。


## 設定の手順

各設定について：

1. 「**[!UICONTROL 詳細]**」セクションで、次の情報を指定します。

   ![会話インサイトの詳細](assets/conversation-insights-configuration-details.png)

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL 名前]** | 設定の名前を指定します。 |
   | **[!UICONTROL サンドボックス]** | 接続に追加するプロンプト、応答、フィードバックイベントデータセットを含むExperience Platform サンドボックスを選択します。 |

1. 「**[!UICONTROL データセット]**」セクションで、次の情報を指定します。

   ![会話インサイトデータセット &#x200B;](assets/conversation-insights-configuration-datasets.png)

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL イベントデータセットのプロンプト]** | プロンプトイベントデータを含むデータセットを選択します。 |
   | **[!UICONTROL 応答イベントデータセット]** | 応答イベントデータを含むデータセットを選択します。 |
   | **[!UICONTROL フィードバックイベントデータセット]** | フィードバックイベントデータを含むデータセットを選択します。 |

1. **[!UICONTROL 接続]** セクションで、接続が既に設定されていない場合は、**[!UICONTROL 接続を選択]**&#x200B;して接続を選択します。

   ![会話インサイト接続](assets/conversation-insights-configuration-connection.png)

   接続が既に設定されている場合は、![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**&#x200B;を選択して別の接続を選択します。

   ![会話インサイト編集接続](assets/conversation-insights-configuration-edit-connection.png)

   **[!UICONTROL 接続を選択]** ダイアログで、次の操作を行います。

   ![会話インサイト選択の接続](assets/conversation-insights-configuration-select-connection.png)

   1. プロンプト、応答、フィードバックイベントデータセットを追加する接続の横にあるチェックボックスを選択します。
   1. 「**[!UICONTROL 接続を使用]**」を選択します。

   * 選択する接続のリストで検索するには、![検索](/help/assets/icons/Search.svg) フィールドを使用します。
   * テーブルに表示する列を設定するには、![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) を選択します。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログで、表示する列を選択します。 次に、**[!UICONTROL 適用]**&#x200B;を選択します。

1. 「**[!UICONTROL データビュー]**」セクションで、データビューが既に設定されていない場合は、「**[!UICONTROL データビューを選択]**」を選択してデータビューを選択します。

   データビューが既に設定されている場合は、「![編集](/help/assets/icons/Edit.svg) **[!UICONTROL データビュー選択を編集]**」を選択して、データビューの選択を再設定します。

   **[!UICONTROL 複数のデータビューを選択]** ダイアログ：

   ![会話インサイト データビューの選択](assets/conversation-insights-configuration-select-data-views.png)

   1. 会話インサイト設定に使用する1つ以上のデータビューを選択します。

   1. 「**[!UICONTROL データビューを使用]**」を選択して、データビューを使用します。 キャンセルするには、「キャンセル」を選択します。

   * 選択するデータビューのリストで検索するには、![検索](/help/assets/icons/Search.svg) フィールドを使用します。
   * テーブルに表示する列を設定するには、![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) を選択します。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログで、表示する列を選択します。 次に、**[!UICONTROL 適用]**&#x200B;を選択します。

1. 設定を完了するには：

   * 作成されていない新しい設定の場合は、**[!UICONTROL Discard]**&#x200B;を選択します。

   * 保存する新しい設定で、アーティファクトを作成しない（データビューの更新など）場合は、**[!UICONTROL 後で保存]**&#x200B;を選択します。 後で設定を再確認し、設定の実際の作成を完了できます。

   * **[!UICONTROL 作成]**&#x200B;を選択して、新しい設定を作成します。

   * 変更した設定を保存するには、**[!UICONTROL 保存]**&#x200B;を選択します。

   * **[!UICONTROL 復元]**&#x200B;を選択して設定を復元し、設定の新しいブレンドデータセットを再生成します。

   * 設定の変更を無視するには、**[!UICONTROL 終了]**&#x200B;を選択します。


## データビューの検証

（関連するデータセットから表示される指標とディメンションについて説明します）


<!--

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 


 
## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

-->