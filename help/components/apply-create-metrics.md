---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: 指標
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 18%

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

## 計算指標の作成

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連しているかを簡単に確認できます。

計算指標を作成する方法はいくつかあります。 選択した方法によって、計算指標をすべてのプロジェクトのコンポーネントリストから使用できるか、計算指標が作成されたプロジェクトでのみ使用できるかが決まります。

### すべてのプロジェクトの計算指標を作成

計算指標ビルダーを使用して、計算指標を作成できます。 この方法で作成した場合、計算指標はコンポーネントリストで使用できるので、組織全体のプロジェクトで使用できます。

計算指標ビルダーへのアクセス方法について詳しくは、[ 指標の作成 ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) を参照してください。

### 単一プロジェクトの計算指標の作成

作成したプロジェクトでのみ使用できるクイック計算指標を作成できます。

単一プロジェクトの計算指標を作成するには：

1. Analysis Workspaceで、計算指標を作成するプロジェクトを開きます。

1. フリーフォームテーブルで、1 つ以上のヘッダー列のセルを右クリックし、「**[!UICONTROL 選択から指標を作成]**」を選択します。

   ![ 選択範囲から作成を強調表示したWorkspace パネル ](assets/create-metric-from-selection.png)

1. このプロジェクトにのみ計算指標を作成するには、次のオプションから選択します。

   * [!UICONTROL **除算**]

   * [!UICONTROL **減算**]

   * [!UICONTROL **追加**]

   * [!UICONTROL **Multiply**]

   計算指標ビルダーを開いて、すべてのプロジェクトの計算指標を作成するには、「[!UICONTROL **計算指標ビルダーで開く**]」を選択して [ 指標の作成 ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) を続行します。

[計算指標： 実装なしの指標](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ja)（3:42）

## 様々なアトリビューションモデルとの指標の比較

アトリビューションモデルを別のアトリビューションモデルと素早く簡単に比較したい場合は、指標を右クリックし、「**[!UICONTROL アトリビューションモデルを比較]**」を選択します。

![ アトリビューションモデルの比較を強調表示したWorkspace パネル ](assets/compare-attribution.png)

これにより、指標にドラッグして設定を 2 回おこなわなくても、アトリビューションモデルをすばやく簡単に相互比較できます。
