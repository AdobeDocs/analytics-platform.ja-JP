---
description: 指標の概要と Analysis Workspace での指標の使用方法について説明します。
title: 指標
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 6%

---

# 指標

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

## Analysis Workspace での指標の使用

指標は、Analysis Workspace内で柔軟に使用できます。 指標を空のフリーフォームテーブルにドラッグすると、プロジェクトの日付期間にわたるその指標のトレンドを確認できます。 また、ディメンションが存在する場合に指標をドラッグすると、その指標を各ディメンション項目と比較して確認できます。 指標を既存の指標ヘッダーの上にドラッグすると指標が置き換えられ、指標をヘッダーの横にドラッグすると両方の指標を並べて表示できます。

Analysis Workspaceに指標やその他のタイプのコンポーネントを追加する方法について詳しくは、[Analysis Workspaceでのコンポーネントの使用 &#x200B;](/help/components/use-components-in-workspace.md) を参照してください。


## 指標のタイプ

アドビでは、Analysis Workspace で使用するためのいくつかのタイプの指標を提供しています。


* **標準指標**：標準指標の例は、人物、セッション、イベントです。

  Adobe Analyticsとは異なり、Customer Journey Analyticsでは、接続とデータビューの範囲内で柔軟に標準指標を定義できます。

   * **人物**:Customer Journey Analyticsの人物指標は、ユーザー ID の個別カウントです。 接続でデータセットを設定する際にユーザー ID として選択した内容に応じて、人物指標は異なる意味を持つ場合があります。
   * **セッション**:Customer Journey Analyticsのセッション指標は、データビューのセッション設定の一部として定義するものです。 [&#x200B; セッション設定 &#x200B;](/help/data-views/session-settings.md) を参照してください。
   * **イベント**:Customer Journey Analyticsのイベント指標は、接続の一部として設定したイベントデータセットの一部であるイベントで構成されています。

  標準指標の完全なリストについては、[&#x200B; 標準指標 &#x200B;](#standard-metrics) を参照してください。

* **計算指標**![&#x200B; 計算ツール &#x200B;](/help/assets/icons/Calculator.svg)：標準指標、静的数値、アルゴリズム関数に基づくユーザー定義の指標です。

* **計算指標テンプレート**![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)：計算指標と同様に動作するAdobe定義の指標です。 これらは、Workspace プロジェクトでそのまま使用することも、コピーを保存してロジックをカスタマイズすることもできます。 [&#x200B; デフォルトの計算指標 &#x200B;](calc-metrics/cm-workflow/../default-calcmetrics.md) を参照してください。

指標が承認されているかどうか ![&#x200B; 承認済みアイコン &#x200B;](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) を確認できます。 指標に関する詳細が必要な場合は、指標の上にマウスポインターを置いて、「![&#x200B; 情報アイコン &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」を選択します。 詳しくは、[&#x200B; コンポーネント情報 &#x200B;](use-components-in-workspace.md#component-info) を参照してください。


## 標準指標

Customer Journey Analyticsの標準指標の完全なリスト：
{{standard-metrics}}


## 計算指標の作成

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連するかを簡単に設定できます。 詳しくは、[&#x200B; 計算指標の概要 &#x200B;](/help/components/calc-metrics/calc-metr-overview.md) を参照してください。

計算指標を作成する方法はいくつかあります。 選択した方法によって、計算指標をすべてのプロジェクトのコンポーネントリストから使用できるか、計算指標が作成されたプロジェクトでのみ使用できるかが決まります。

### すべてのプロジェクトの計算指標を作成

[&#x200B; 計算指標ビルダー &#x200B;](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) を使用して、[&#x200B; 計算指標を作成 &#x200B;](/help/components/calc-metrics/cm-workflow/cm-workflow.md) できます。 この方法で作成した場合、計算指標はコンポーネントリストで使用できるので、組織全体のプロジェクトで使用できます。

### 単一プロジェクトの計算指標の作成

計算指標を素早く作成できます。計算指標は、これを作成したプロジェクトでのみ使用できます。

単一プロジェクトの計算指標を作成するには：

1. Analysis Workspaceで、計算指標を作成するプロジェクトを開きます。

1. フリーフォームテーブルで、1 つの列の列ヘッダーを右クリックします。

   または

   Shift キーを押しながら 2 つの列を選択し、選択した列の 1 つを右クリックします。

1. 「**[!UICONTROL 選択から指標を作成]**」を選択します

   ![&#x200B; 選択範囲から作成を強調表示したWorkspace パネル &#x200B;](assets/create-metric-from-selection.png)

1. このプロジェクトにのみ計算指標を作成するには、使用可能なオプションから選択します。

   1 つの列を選択した場合、次のオプションを使用できます。

   * [!UICONTROL **平均**]：列のディメンション要素のセットの平均値を表示する新しい列を作成します。 これは [Mean](/help/components/calc-metrics/cm-functions.md#mean) 関数を使用します。

   * [!UICONTROL **中央値**]：列のディメンション要素セットの中央値を表示する新しい列を作成します。 [Median](/help/components/calc-metrics/cm-functions.md#median) 関数を使用します。

   * [!UICONTROL **列の最大値**]：列のディメンション要素のセットの中の最大値を表示する新しい列を作成します。 これは [Column Maximum](/help/components/calc-metrics/cm-functions.md#column-maximum) 関数を使用します。

   * [!UICONTROL **列の最小値**]：列のディメンション要素のセットの最小値を表示する新しい列を作成します。 これは [Column Minimum](/help/components/calc-metrics/cm-functions.md#column-minimum) 関数を使用します。

   * [!UICONTROL **列の合計**]:Creates （ディメンションのすべての要素にわたって）列内の指標のすべての数値を加算する新しい列。 [Column Sum](/help/components/calc-metrics/cm-functions.md#column-sum) 関数を使用します。

   2 つの列を選択した場合は、次のオプションを使用できます。

   * [!UICONTROL **除算**]：選択した 2 つの列の値を除算する新しい列を作成します。

   * [!UICONTROL **減算**]：選択した 2 つの列の値を減算する新しい列を作成します。

   * [!UICONTROL **追加**]：選択した 2 つの列の値を追加する新しい列を作成します。

   * [!UICONTROL **乗算**]：選択した 2 つの列の値を乗算する新しい列を作成します。

   * [!UICONTROL **変化率**]：選択した 2 つの列の間の変化率を示す新しい列を作成します。


## 様々なアトリビューションモデルとの指標の比較

指標のアトリビューションモデルを別のアトリビューションモデルとすばやく比較するには、指標のコンテキストメニューから **[!UICONTROL アトリビューションモデルを比較]** を選択します。

![&#x200B; アトリビューションモデルの比較を強調表示したWorkspace パネル &#x200B;](assets/compare-attribution.png)

このショートカットを使用すると、指標をドラッグして 2 回設定することなく、1 つのアトリビューションモデルを別のアトリビューションモデルと比較できます。


