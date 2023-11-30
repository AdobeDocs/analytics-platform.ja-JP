---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: 指標
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
source-git-commit: dbc0210936e8205fbe97b3c88e6c37597e7e43e3
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 49%

---

# 指標

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

## 指標のタイプ

アドビでは、Analysis Workspace で使用するためのいくつかのタイプの指標を提供しています。

* **標準指標**：標準指標の例は、人、セッション、イベントです。

* **計算指標** ![計算指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)：標準指標、静的数値またはアルゴリズム関数に基づくユーザー定義の指標。

* **計算指標テンプレート**  <img src="./assets/adobe-logo.svg" width="18"> :Adobe定義の指標。計算指標と同様に動作します。 これらを Workspace プロジェクトでそのまま使用することも、コピーを保存してロジックをカスタマイズすることもできます。


![左側のペインで指標をハイライトする Workspace パネル。](assets/cja-metrics.png)

指標が承認されているかどうかを確認できます ![承認済みアイコン](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  またはそうではありません。 指標の詳細を表示するには、指標の上にマウスポインターを置いて、「 ![情報アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


指標は、Analysis Workspace内で柔軟に使用できます。 指標を空のフリーフォームテーブルにドラッグすると、プロジェクトの日付期間にわたるその指標のトレンドを確認できます。また、ディメンションが存在する場合に指標をドラッグして、各ディメンション項目と比較した指標を確認できます。 既存の指標ヘッダーの上にある指標をドラッグすると、その指標が置き換えられます。ヘッダーの横にある指標をドラッグすると、両方の指標が並べて表示されます。

## 計算指標

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連しているかを簡単に確認できます。計算指標を作成する方法はいくつかあります。

次の項目を選択できます。 **[!UICONTROL コンポーネント]** > **[!UICONTROL 計算指標]**. これにより、 [計算指標ビルダー](/help/components/calc-metrics/calc-metr-overview.md)：既存の指標からカスタム指標を作成できます。

計算指標をすばやく簡単に作成できるように、フリーフォームテーブルの列の右クリックメニューに「**[!UICONTROL 選択から指標を作成]**」が追加されました。このオプションは、ヘッダー列のセルが 1 つ以上選択されると表示されます。

![Workspace パネルハイライト選択から作成](assets/create-metric-from-selection.png)

[計算指標： 実装なしの指標](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ja)（3:42）

## 様々なアトリビューションモデルとの指標の比較

アトリビューションモデルを相互にすばやく簡単に比較したい場合は、指標を右クリックし、「 **[!UICONTROL アトリビューションモデルの比較]**:

![アトリビューションモデルの比較をハイライトする Workspace パネル](assets/compare-attribution.png)

これにより、指標にドラッグして設定を 2 回おこなわなくても、アトリビューションモデルをすばやく簡単に相互比較できます。
