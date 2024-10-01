---
description: Analysis Workspace のアクセシビリティサポート機能
title: Analysis Workspace のアクセシビリティ
feature: FAQ
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 42%

---

# Analysis Workspace のアクセシビリティ

Customer Journey Analytics の主要な分析ツールである [!UICONTROL Analysis Workspace]のアクセシビリティサポートについて説明します。

アクセシビリティとは、視覚、聴覚、認知、モーターなどの障害を持つユーザーに対して、製品を使用できるようにすることです。ソフトウェア製品のアクセシビリティ機能の例を次に示します。

* スクリーンリーダーのサポート
* グラフィックの代替テキスト
* ショートカットキー
* ディスプレイの色の高コントラストへの変更、
* その他。

[!UICONTROL Analysis Workspace] には、次のような、使いやすいツールが用意されています。

## キーボードナビゲーション

[!UICONTROL Analysis Workspace] のナビゲーションは、上から下、左から右に移動します。 次のナビゲーション要素はアクセシビリティを容易にします。

* **[!UICONTROL Tab]** キーを押すと、Workspace内の大きなセクション間を移動するランドマークショートカットが有効になります。 左側のパネルの **[!UICONTROL Tab]** では、ドラッグ可能なオプション間を移動することもできます。
* **[!UICONTROL Tab]** キーで要素がハイライト表示された後、◀︎と▶︎は個々の要素間を移動します。
* **[!UICONTROL F6]** キーを押すとプロジェクト内の最初のパネルに移動し、そのパネル内のビジュアライゼーション間を移動します。 その後、プロジェクト内の次のパネルに移動し、同じ動作を繰り返します。
* フォーカスインジケーターが適用されて、目の見えるキーボードユーザーが、現在フォーカスされている UI 要素を明確に示すことができます。 インジケーターは、フォーカスされたパネルの青い境界線です。 最近の選択された機能と機能内の選択に関するグレーの背景。 この例では、[!UICONTROL  コンポーネント ] とページディメンションが最近選択されています。

  ![フリーフォームテーブル周囲の青い境界線のフォーカスインジケーターを表示するフリーフォームテーブル。](assets/focus-indicator.png)

### メニューバーのキーボードナビゲーション

1. メニューバーに到達するまで Tab キーを押します。
1. 矢印キーを使用して、メニューとメニュー項目を移動します。
1. **[!UICONTROL Enter]** キーを押してメニューを開くか、メニュー項目を選択します。
1. メニューを閉じるには **[!UICONTROL Esc]** を使用します。

### ドラッグ&amp;ドロップ操作のキーボードナビゲーション

[!UICONTROL Analysis Workspace] はドラッグ&amp;ドロップのユーザーインターフェイスです。 ただし、ユーザーは、代わりにキーボードを使用してコンポーネントを追加できます。

1. 左パネルのコンポーネントに Tab キーを押します。
1. **[!UICONTROL Enter]** キーを押して選択します。
1. 矢印キーを使用して、コンポーネントをドロップする領域に移動します。
1. **[!UICONTROL Enter]** キーを押して、コンポーネントを配置します。

### キーボードショートカット（ホットキー）

[!UICONTROL Analysis Workspace] には、よりシームレスなワークフローを実現するための豊富な [ キーボードショートカット ](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys) が用意されています。

## スクリーンリーダーとスクリーン拡大鏡のサポート

スクリーンリーダーは、コンピューターの画面に表示されるテキストを読み上げます。また、ボタンのラベルやアプリケーション内の画像の説明など、テキスト以外の情報も読み取ります。

## カラーパレットとコントラスト

[!UICONTROL Analysis Workspace] は、WCAG 2.1 AA への準拠を目指しています（カラーコントラストの要件を含む）。

また、プロジェクトに対しては、**[!UICONTROL プロジェクト]**／**[!UICONTROL プロジェクト設定]**／[プロジェクトのカラーパレット](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes)で、ユーザーが希望するカラーパレットを設定できます。

## 必須の検証

コンポーネント、ビジュアライゼーションまたはパネルを作成する場合、保存すると必須フィールドが検証されます。 必須フィールドが検証に合格しない場合は、赤で囲まれ、エラーアイコンが表示されます。 修正が必要な事項は、書面による説明で説明します。

![セグメントビルダーとエラー検証インジケーター。](assets/error-validation.png)

## オペレーティングシステムのアクセシビリティ機能のサポート

Analysis Workspaceは、高コントラストモード、スティッキーキー、スローキー/フィルターキーなど、組み込みの Windows およびmacOSのアクセシビリティ機能をサポートしています。 また、Windows 上の VoiceOver for macOS や NVDA などの支援テクノロジーとの対話を可能にするためのユーザーインターフェイスに関する情報も提供します。
