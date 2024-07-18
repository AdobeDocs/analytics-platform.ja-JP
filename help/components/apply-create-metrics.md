---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: 指標
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 53d367e51f739ebf324390ba4114ddb58138fac8
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 40%

---

# 指標

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

## 指標のタイプ

アドビでは、Analysis Workspace で使用するためのいくつかのタイプの指標を提供しています。

* **標準指標**：標準指標の例は、人物、セッション、イベントです。

* **計算指標**![ 計算指標アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)：標準指標、静的数値、アルゴリズム関数に基づくユーザー定義の指標です。

* **計算指標テンプレート**  <img src="./assets/adobe-logo.svg" width="18">：計算指標と同様に動作するAdobe定義の指標です。 Workspace プロジェクトでそのまま使用することも、コピーを保存してロジックをカスタマイズすることもできます。


![ 左側のパネルで指標をハイライト表示したWorkspace パネル。](assets/cja-metrics.png)

指標が承認されているかどうか ![ 承認済みアイコン ](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) を確認できます。 指標に関する詳細が必要な場合は、指標の上にマウスポインターを置いて、「![ 情報アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」を選択します。


指標は、Analysis Workspace内で柔軟に使用できます。 指標を空のフリーフォームテーブルにドラッグすると、プロジェクトの日付期間にわたるその指標のトレンドを確認できます。 また、ディメンションが存在する場合に指標をドラッグすると、その指標を各ディメンション項目と比較して確認できます。 指標を既存の指標ヘッダーの上にドラッグすると指標が置き換えられ、指標をヘッダーの横にドラッグすると両方の指標を並べて表示できます。

## Analysis Workspace での指標の使用

指標は、Analysis Workspace 内で様々な方法で使用できます。 Analysis Workspaceに指標やその他のタイプのコンポーネントを追加する方法について詳しくは、[Analysis Workspaceでのコンポーネントの使用 ](/help/components/use-components-in-workspace.md) を参照してください。

## 計算指標

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連しているかを簡単に確認できます。計算指標を作成する方法はいくつかあります。

**[!UICONTROL コンポーネント]**/**[!UICONTROL 計算指標]** を選択できます。 これにより、[ 計算指標ビルダー ](/help/components/calc-metrics/calc-metr-overview.md) に移動し、既存の指標からカスタム指標を作成できます。

計算指標をすばやく簡単に作成できるように、フリーフォームテーブルの列の右クリックメニューに「**[!UICONTROL 選択から指標を作成]**」が追加されました。このオプションは、ヘッダー列のセルが 1 つ以上選択されると表示されます。

![ 選択範囲から作成を強調表示したWorkspace パネル ](assets/create-metric-from-selection.png)

[計算指標： 実装なしの指標](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ja)（3:42）

## 様々なアトリビューションモデルとの指標の比較

アトリビューションモデルを別のアトリビューションモデルと素早く簡単に比較したい場合は、指標を右クリックし、「**[!UICONTROL アトリビューションモデルを比較]**」を選択します。

![ アトリビューションモデルの比較を強調表示したWorkspace パネル ](assets/compare-attribution.png)

これにより、指標にドラッグして設定を 2 回おこなわなくても、アトリビューションモデルをすばやく簡単に相互比較できます。
