---
title: コンバージョントレンドビュー
description: コンバージョン率の経時的な変化を追跡します。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# [!UICONTROL  コンバージョンのトレンド ] ビュー

**[!UICONTROL コンバージョンのトレンド]** ビューでは、コンバージョン率のトレンドを経時的に視覚化します。 横軸は時間間隔、縦軸はコンバージョン率を表します。

>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)

## ユースケース

この表示タイプの使用例を次に示します。

* **最適化の取り組みを追跡**: [ 摩擦 ](friction.md) を使用して改善したい主なボトルネックを特定した後、このビューを使用して、それらの最適化が時間の経過と共にコンバージョン率に与える影響を追跡できます。
* **A/B テストの評価**：ファネルのコンテキスト内で行われた A/B テストまたは実験の有効性を評価します。 異なるバリエーション間でコンバージョン率を比較することで、どのテストがより高いコンバージョン率を提供するかを簡単に判断でき、どのバリエーションを永続的に実装するかのデータに基づく決定につながります。
* **キャンペーン評価の履歴**: マーケティングキャンペーンの効果を経時的に測定します。 特定のキャンペーンにタッチしたユーザーに焦点を当てたセグメントを作成し、そのコンバージョン率を他のキャンペーンと比較できます。 また、現在のコンバージョン率を、過去に実行された類似のキャンペーンと比較することもできます。

## クエリパネル

クエリパネルでは、次のコンポーネントを設定できます。

* **[!UICONTROL 表示]**：このビュータイプと [ 摩擦 ](friction.md) を切り替えます。
* **[!UICONTROL 手順]**：トラッキングするイベントタッチポイント。 グラフ内の各棒グラフはステップを表します。 最大 10 個の手順を含めることができます。
* **[!UICONTROL カウント対象]**：選択したイベントに適用するカウント方法。 オプションには [!UICONTROL  ユーザー ] と [!UICONTROL  セッション ] があります。
* **[!UICONTROL セグメント]**：ファネルを比較するセグメント。 選択したセグメントごとに、各ステップが複数の棒に分割されます。 それぞれの色が異なるセグメントを表します。 最大 3 つのセグメントを含めることができます。

## グラフ設定

[!UICONTROL  コンバージョンのトレンド ] ビューには、次のグラフ設定が表示され、グラフの上のメニューで調整できます。

* **[!UICONTROL グラフのタイプ]**：使用するビジュアライゼーションのタイプ。 オプションには [!UICONTROL  折れ線グラフ ] があります。
* **[!UICONTROL 変換元]**：ステップからステップへのパーセンテージ計算を決定します。 オプションには、[!UICONTROL  最初の手順 ] または [!UICONTROL  前の手順 ] からのコンバージョンの計算が含まれます。

>[!NOTE]
>
>変換トレンドビューのテーブルの **平均** 列は、[ 摩擦ビュー ](friction.md) テーブルの **合計** 列とは異なります。 前者は間隔列の平均（例：日別コンバージョン率の平均）で、後者は日付範囲全体の集計計算です。

## 時間比較

{{apply-time-comparison}}

![ コンバージョントレンドと時間比較 ](../assets/conversion-trends-compare.png){style="border:1px solid gray"}

## 日付範囲

分析に必要な日付範囲。 この設定には、次の 2 つのコンポーネントがあります。

* **[!UICONTROL 間隔]**：トレンドデータの表示に使用する日付の精度。 有効なオプションには、時間別、日別、週別、月別、四半期別があります。 同じ日付範囲に異なる間隔を設定すると、グラフのデータポイント数とテーブルの列数に影響します。 例えば、毎日の精度で 3 日間の分析を表示すると、3 日間の精度で 3 つのデータポイントのみが表示され、時間単位の精度で 3 日間の分析では、72 のデータポイントが表示されます。
* **[!UICONTROL 日付]**：開始日と終了日。 周期的な日付範囲のプリセットと以前に保存したカスタム範囲は便利に使用できます。または、カレンダーセレクターを使用して固定された日付範囲を選択できます。
