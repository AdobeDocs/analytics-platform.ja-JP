---
description: Analysis Workspaceのアクセシビリティサポート機能
title: Analysis Workspaceでのアクセシビリティ
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 4%

---


# Analysis Workspaceでのアクセシビリティ

>[!NOTE] Customer Journey Analytics内のAnalysis Workspaceに関するドキュメントを表示している。 この機能セットは、従来のAdobeAnalyticsの [Analysis Workspaceとは少し異なります](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html)。 [詳細情報...](/help/getting-started/cja-aa.md)

アドビAnalyticsの主要な分析ツールである [!UICONTROL Analysis Workspaceのアクセシビリティサポートについて説明します]。

アクセシビリティとは、視覚、聴覚、認知、モーターなどの障害を持つユーザーに対して、製品を使用できるようにすることです。 ソフトウェア製品のアクセシビリティ機能の例としては、スクリーンリーダーのサポート、グラフィックの代替テキスト、キーボードショートカット、表示色のコントラストの大きさの変更などがあります。

[!UICONTROL Analysis Workspace] には、次のような、使いやすいツールが用意されています。

## キーボードを使用した [!UICONTROL Workspaceの操作]

上/下、左 [!UICONTROL /右の] Analysis Workspaceでのナビゲーション機能。 次のナビゲーション要素はアクセシビリティを容易にします。

* この `F6` キーは、ランドマークショートカットを有効にします。
* キーを個々の要素間で `Tab` 移動します。
* 視覚的なキーボードユーザーが現在フォーカスを持っているUI要素を明確に示すように、フォーカスインジケーターを適用します。 インジケーターは、選択した要素の周りの青い境界線です。

   ![フォーカスインジケーター](assets/focus-indicator.png)

### ドラッグ&amp;ドロップ操作のキーボードナビゲーション

[!UICONTROL Analysis Workspace] は、ドラッグ&amp;ドロップによるユーザーインターフェイスです。 ただし、ユーザーは、代わりにキーボードを使用してコンポーネントを追加できます。

1. 左側のレールのコンポーネントにタブを移動します。
1. を押 `Enter` して選択します。
1. 矢印キーを使用して、コンポーネントをドロップする領域に移動します。
1. を押し `Enter` て、コンポーネントを配置します。

### キーボードショートカット（ホットキー）

[!UICONTROL Analysis Workspace] オファーは、シームレスなワークフローを実現するための豊富な [キーボードショートカットのセット](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) 。 ナビゲーション、分析の作成、インサイトの民主化に関する一般的なショートカットを以下に示します。

#### ナビゲーション

| ショートカット | アクション |
|---|---|
| Alt + Shift + 1 / 2 / 3 | 別のレールにジャンプする： [!UICONTROL パネル]、 [!UICONTROL ビジュアライゼーション]、 [!UICONTROL コンポーネント] |
| Alt +左向き矢印または右向き矢印 | パネル間の移動 |
| Alt + M | すべてのパネルを折りたたむ/展開する |
| Alt + Ctrl + M | アクティブパネルを折りたたむ/展開する |
| Ctrl + / | 左側のパネルを検索 |

#### 分析作成

| ショートカット | アクション |
|---|---|
| Alt + 1 | 新しいフリーフォームテーブル |
| Ctrl + Shift + C | 新しい計算指標 |
| Ctrl + Shift + D | 新しい日付範囲 |
| Ctrl + Shift + E | 新しいセグメント |
| Ctrl + Z | 元に戻す |
| shiftキーを押したまま（パネルセグメントドロップゾーン内） | ドロッ [プダウンフィルタの作成](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

#### 民主化

| ショートカット | アクション |
|---|---|
| Ctrl + S | 保存 |
| Ctrl + Shift + G | キュレート |
| Ctrl + G | 共有 |
| Alt + Shift + S | スケジュール |
| Alt + L | プロジェクトへのリンクを取得 |
| Ctrl + Shift + B | PDF をダウンロード |

## スクリーンリーダーとスクリーン拡大鏡のサポート

スクリーンリーダーは、コンピューターの画面に表示されるテキストを読み上げます。 また、アクセシビリティタグや属性で指定された、アプリケーション内のボタンラベルや画像の説明など、テキスト以外の情報も読み上げます。

## カラーパレットとコントラスト

[!UICONTROL WCAG 2.1 AA準拠向けのAnalysis Workspace] （カラーコントラストの要件を含む）

また、プロジェクトに対しては、 **[!UICONTROL プロジェクト]** / **[!UICONTROL プロジェクト設定]** /プロジェクトのカラーパレットで、ユーザーが希望するカラーパレットを設定できます [](/help/analysis-workspace/build-workspace-project/color-palettes.md)。

## コンポーネントビルダーの必須フィールドの検証

コンポーネントを構築する際、保存時に必須フィールドの検証が行われます。 必須フィールドが検証に合格しない場合は、赤い枠線にエラーアイコンが表示されます。 修正する必要がある問題の説明が文書で表示されます。

コンポーネントの検証が完了すると、を押すとビルダーが閉じ `Save` ます。

![エラーの検証](assets/error-validation.png)

## オペレーティングシステムのアクセシビリティ機能のサポート

Analysis Workspaceは、MS WindowsとmacOSに組み込まれたアクセシビリティ機能（コントラストの大きいモード、共通キー、遅いキー/フィルターキーなど）をサポートしています。 また、Windows上のVoiceOver for macOSやNVDAなどの支援テクノロジーとの対話を可能にするためのユーザーインターフェイスに関する情報も提供します。