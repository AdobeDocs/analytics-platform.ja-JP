---
description: Adobe Analysis Workspace とその関連コンポーネントに関する既知の制限のリスト
title: Analysis Workspace の既知の制限
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 87%

---


# Analysis Workspace の既知の制限

>[!NOTE] Customer Journey Analytics内のAnalysis Workspaceに関するドキュメントを表示している。 この機能セットは、従来のAdobeAnalyticsの [Analysis Workspaceとは少し異なります](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html)。 [詳細情報...](/help/getting-started/cja-aa.md)

以下に、Analysis Workspace とその関連コンポーネントに関する既知の制限を示します。

## テーブル

* 日付範囲または指標がテーブルの行として使用されている場合は、日付比較列を追加できません。
* セグメントをテーブルの行として使用すると、「選択から指標を作成」が無効になります。また、「選択から指標を作成」は、日付順の列には適用しないでください。
* 分類行の条件付き書式では、カスタム範囲を使用することはできません。
* 行の値を合計して合計を計算する設定が適用されている場合は、テーブルの合計行をトレンド表示できません（通常は静的な行項目で使用されます）。
* [!UICONTROL 貢献度分析]は、[!UICONTROL 毎日]の精度でのみ&#x200B;_実行_&#x200B;できます。[!UICONTROL 時間別]、[!UICONTROL 週別]などのデータに対して実行することはできません。

## ビジュアライゼーション

* セグメント化（[!UICONTROL フォールアウト]、[!UICONTROL フロー]、[!UICONTROL コホート]、[!UICONTROL ヒストグラム]など）を利用するビジュアライゼーションでは、計算指標を入力として使用することはできません。
* [!UICONTROL フロー]：入口／出口ディメンション（例：[!UICONTROL 入口ページ]）は、フローでは使用できません。
* [!UICONTROL コホート]：整数以外の値をコホート条件として使用することはできません。

<!--## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.<-->

## コンポーネント/フィルター

* 指標やディメンションには、セグメント化できないものがあります（[!UICONTROL 回数]、[!UICONTROL 個別訪問者数]など）。
* Certain components and operators are unavailable if a filter is created from Workspace (as opposed to being created from [!UICONTROL Components > Filters]). 例：IP アドレス。

## コンポーネント／計算指標

* 計算指標は、一部のビジュアライゼーションでは使用できません。上記の「ビジュアライゼーション」を参照してください。
* 計算指標自体に別々のアトリビューションモデルを含めることができるので、[!UICONTROL アトリビューションパネル]で計算指標を使用することはできません。
* 計算指標が Workspace から作成される場合（[!UICONTROL コンポーネント／セグメント]から作成される場合とは異なり）、使用できないコンポーネントや演算子があります。例：[!UICONTROL IP アドレス]。

## コンポーネント／日付範囲

* カスタム日付範囲では、[!UICONTROL 昨年の今日]、[!UICONTROL 先月の今日]などはサポートされません。

## コンポーネント／レポート設定

* 「[!UICONTROL レポート設定]」ページの一部の設定は適用されません。Analysis Workspace では、一番下の「[!UICONTROL 言語 / 通貨 / エンコード]」設定（[!UICONTROL 千単位区切り文字]、[!UICONTROL 予定レポートのエンコード]、[!UICONTROL CSV 区切り文字]）のみが使用されます。

## Attribution IQ

* 指標のサブセットは、[!UICONTROL Attribution IQ] ではサポートされません。完全なリストについては、[Attribution IQ に関する FAQ](../attribution/faq.md) を参照してください。
