---
description: トレンドのトピックのビジュアライゼーションを使用して、会話のトレンドのトピックを調べます。
title: トレンド分析トピック
feature: Visualizations
role: User
hide: true
source-git-commit: 65d4115d4c292cff7e074d37a91563d369072ba5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---
# トレンド分析トピック

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="トレンド分析トピック"
>abstract="階層的なドリルダウンを使用して、トレンドのトピックを出現率や割合で分類し、会話の重要なテーマを特定できるビジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="トレンド分析トピック"
>abstract="選択したランキング指標にもとづいてトレンドトピックを分析します。 トピックを選択して、最大5つのレベルまでドリルダウンします。 特定のトピックを検索し、トピックを他の日付範囲と比較します。"

![ フィード ](/help/assets/icons/Feed.svg) **[!UICONTROL トレンド トピック]**&#x200B;のビジュアライゼーションを使用すると、会話インサイトの一部として、トレンド トピックを探索および分析できます。

特定のトピックを検索し、各レベルの各トピックの数と割合を他のデータ範囲と比較できます。

## 作成と設定

トレンドトピックのビジュアライゼーションを作成および設定するには：

1. ![ フィード ](/help/assets/icons/Feed.svg) **[!UICONTROL トレンド トピック]** ビジュアライゼーションを追加します。 [パネルへのビジュアライゼーションの追加](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。

1. **[!UICONTROL トレンドトピック]**&#x200B;のビジュアライゼーション設定で、次の操作を行います。

   1. **[!UICONTROL ランキング指標]**&#x200B;を選択します。 例：**[!UICONTROL Conversations]**。
   1. オプションで、**[!UICONTROL 属性を設定]**&#x200B;を選択し、**[!UICONTROL モデル]**、**[!UICONTROL コンテナ]**、**[!UICONTROL ルックバックウィンドウ]**&#x200B;を選択します。
   1. **[!UICONTROL サブトピックレベルを制限]**&#x200B;のレベルを選択します。 既定は&#x200B;**[!UICONTROL レベル 5]**&#x200B;です。

      >[!NOTE]
      >
      >**[!UICONTROL サブトピックレベルの制限]**&#x200B;は、ビジュアライゼーション内のトピックをドリルダウンする最大レベル数を定義します。 定義された最大数内のレベルで使用できるトピックがこれ以上ない場合、![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL 見つかったトピックはありません]**&#x200B;が表示されます。

1. ビジュアライゼーションを作成するには、**[!UICONTROL ビルド]**&#x200B;を選択します。 設定値をデフォルトにリセットするには、**[!UICONTROL リセット]**&#x200B;を選択します。

トレンド トピックのビジュアライゼーションを再構成するには、**[!UICONTROL ランキング指標：_ランキング指標_ | サブトピックレベル：_x_]**の横にある![編集](/help/assets/icons/Edit.svg)を選択します。

## 使用

ビジュアライゼーションを使用するには：

* 下位レベルのトピックのトレンド サブトピックをドリルダウンして表示するには、特定のレベルのトピックを選択します。

* トピックを別の日付範囲と比較するには、「比較」から日付範囲を選択します。 カスタムの日付範囲を使用するには：
  * ドロップダウンメニューから「カスタム日付範囲」を選択し、新しい日付範囲ダイアログでカスタム日付範囲を定義して保存します。
  * カスタム日付範囲を選択し。

* 現在のトピック選択の折れ線グラフを表示するには、**[!UICONTROL トレンド トピック]** ビジュアライゼーションに[折れ線](/help/analysis-workspace/visualizations/line.md) ビジュアライゼーションをドロップします。 **[!UICONTROL 行]**&#x200B;のビジュアライゼーションは、**[!UICONTROL トレンド トピック]**&#x200B;のビジュアライゼーションに自動的にリンクされます。

## 設定

次の特定の[ ビジュアライゼーション設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)を使用できます。

| 設定 | 説明 |
|---|---|
| **[!UICONTROL 実際の値を表示]** | トピックの実際の値を表示します。 |
| **[!UICONTROL 表示率]** | トピックの推奨事項を表示します。 |



