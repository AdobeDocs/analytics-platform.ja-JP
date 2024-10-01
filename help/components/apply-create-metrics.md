---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: 指標
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 20%

---

# 指標

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

## 指標のタイプ

アドビでは、Analysis Workspace で使用するためのいくつかのタイプの指標を提供しています。


* **標準指標**：標準指標の例は、人物、セッション、イベントです。

* **計算指標**![ 計算ツール ](/help/assets/icons/Calculator.svg)：標準指標、静的数値、アルゴリズム関数に基づくユーザー定義の指標です。

* **計算指標テンプレート**![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)：計算指標と同様に動作するAdobe定義指標です。 これらは、Workspace プロジェクトでそのまま使用することも、コピーを保存してロジックをカスタマイズすることもできます。

指標が承認されているかどうか ![ 承認済みアイコン ](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) を確認できます。 指標に関する詳細が必要な場合は、指標の上にマウスポインターを置いて、「![ 情報アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」を選択します。 詳しくは、[ コンポーネント情報 ](use-components-in-workspace.md#component-info) を参照してください。



## Analysis Workspace での指標の使用

指標は、Analysis Workspace内で柔軟に使用できます。 指標を空のフリーフォームテーブルにドラッグすると、プロジェクトの日付期間にわたるその指標のトレンドを確認できます。 また、ディメンションが存在する場合に指標をドラッグすると、その指標を各ディメンション項目と比較して確認できます。 指標を既存の指標ヘッダーの上にドラッグすると指標が置き換えられ、指標をヘッダーの横にドラッグすると両方の指標を並べて表示できます。

Analysis Workspaceに指標やその他のタイプのコンポーネントを追加する方法について詳しくは、[Analysis Workspaceでのコンポーネントの使用 ](/help/components/use-components-in-workspace.md) を参照してください。

## 計算指標

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連するかを簡単に設定できます。 詳しくは、[ 計算指標の概要 ](/help/components/calc-metrics/calc-metr-overview.md) を参照してください。

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

+++

-->

## 様々なアトリビューションモデルとの指標の比較

指標のアトリビューションモデルを別のアトリビューションモデルと素早く簡単に比較したい場合は、指標のコンテキストメニューから **[!UICONTROL アトリビューションモデルを比較]** を選択します。

![ アトリビューションモデルの比較を強調表示したWorkspace パネル ](assets/compare-attribution.png)

このショートカットを使用すると、アトリビューションモデルをすばやく簡単に比較できます。
