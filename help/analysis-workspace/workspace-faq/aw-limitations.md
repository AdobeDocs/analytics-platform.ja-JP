---
description: Adobe Analysis Workspace とその関連コンポーネントに関する既知の制限事項について説明します。
title: Analysis Workspaceの既知の制限事項
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 98%

---

# Analysis Workspace の既知の制限

次に、Analysis Workspace とその関連コンポーネントに関する既知の制限を示します。

## テーブル

* 日付範囲または指標がテーブルの行として使用されている場合は、日付比較列を追加できません。
* セグメントをテーブルの行として使用すると、「選択から指標を作成」が無効になります。また、「選択から指標を作成」は、日付順の列には適用しないでください。
* 分類行の条件付き書式では、カスタム範囲を使用することはできません。
* 行の値を合計して合計を計算する設定が適用されている場合は、テーブルの合計行をトレンド表示できません（通常は静的な行項目で使用されます）。

## ビジュアライゼーション

* セグメント（[!UICONTROL フォールアウト]、[!UICONTROL フロー]、[!UICONTROL コホート]、[!UICONTROL ヒストグラム]など）を利用するビジュアライゼーションでは、計算指標を入力として使用することはできません。
* [!UICONTROL フロー]：入口／出口ディメンション（例：[!UICONTROL 入口ページ]）は、フローでは使用できません。
* [!UICONTROL コホート]：整数以外の値をコホート条件として使用することはできません。

## セグメント

* 指標やディメンションには、セグメント化できないものがあります（[!UICONTROL イベント]、[!UICONTROL ユーザー]など）。
* [パネルのドロップゾーン](/help/analysis-workspace/c-panels/panels.md)で作成されたアドホックセグメントは、クイックセグメントのタイプです。公開されない限り、Workspace の左パネルまたはセグメントマネージャーには表示されません。詳しくは、[クイックセグメント](/help/components/segments/seg-quick.md)を参照してください。

## 計算指標

* 計算指標は、一部のビジュアライゼーションでは使用できません。詳しくは、[ビジュアライゼーション](#visualizations)を参照してください。
* 計算指標自体に別々のアトリビューションモデルを含めることができるので、[!UICONTROL アトリビューションパネル]で計算指標を使用できません。
* 計算指標が Workspace から作成される場合（[!UICONTROL コンポーネント／セグメント]から作成される場合とは異なり）、使用できないコンポーネントや演算子があります。例：[!UICONTROL IP アドレス]。

## 日付範囲

* カスタム日付範囲では、[!UICONTROL 昨年の今日]、[!UICONTROL 先月の今日]などはサポートされません。


## レポート設定

* 「[!UICONTROL レポート設定]」ページの一部の設定は適用されません。Analysis Workspace では、一番下の「[!UICONTROL 言語 / 通貨 / エンコード]」設定（[!UICONTROL 桁区切り記号]、[!UICONTROL 予定レポートのエンコード]、[!UICONTROL CSV 区切り記号]）のみが使用されます。

