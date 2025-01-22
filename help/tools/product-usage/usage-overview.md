---
title: 製品の使用状況の概要
description: 組織でのCustomer Journey Analyticsの使用方法に関するインサイトとレポートを表示します。
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: ae22dc84406427567d45b670aa9737ea3a8b2f7b
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 12%

---

# 製品の使用状況の概要

{{release-limited-testing}}

製品の使用状況を使用すると、組織でのCustomer Journey Analyticsの使用状況に関する分析データを表示できます。 Customer Journey Analyticsを使用するすべての組織で利用できます。 有効にすると、次のAdobe Experience Platform コンポーネントが自動的に作成され、自動的に接続されます。 これらのコンポーネントはすべてシステムが所有し、読み取り専用で、編集できません。

* Adobe Experience Platformのスキーマ
* Adobe Experience Platformのデータセット
* Customer Journey Analyticsの接続
* Customer Journey Analyticsのデータビュー

すべてのデータ収集と設定は、有効にすると自動的に設定されます。 ユーザーがAnalysis Workspaceでアクションを実行するたびに、そのアクションが追跡され、レポートに使用できます。

>[!IMPORTANT]
>
>この機能は、Adobe Experience Platformの契約上の行制限にカウントされます。 この機能を有効にする前に、この機能で生成されたデータを組織が調整できることを確認してください。

## 製品の使用状況を有効にする

**[!UICONTROL Customer Journey Analytics]** / **[!UICONTROL ツール]** / **[!UICONTROL 製品の使用状況]**

Customer Journey Analyticsでインターフェイスのこのセクションに移動すると、[ データ設定 ](data-settings.md) に移動し、この機能を有効にできます。

## 使用可能なディメンション

製品の使用を有効にすると、次のディメンションを使用できます。 ディメンション設定を変更する場合は、システムが所有するデータビューのコピーを作成し、コピーしたデータビューをAnalysis Workspaceで使用します。

* **[!UICONTROL アクション名]**: ユーザーが実行したアクションのタイプ。 データビュー設定でコピーを作成すると、このディメンションを必要な指標として使用できます。 Dimension項目は次のとおりです。
   * [!UICONTROL  属性を追加 ]
   * [!UICONTROL  コンポーネントを追加 ]
   * [!UICONTROL  パネルを追加 ]
   * [!UICONTROL  ビジュアライゼーションを追加 ]
   * [!UICONTROL  新しいガイド付き分析の作成 ]
   * [!UICONTROL  新規プロジェクトを作成 ]
   * [!UICONTROL  コンポーネントをキュレーション ]
   * [!UICONTROL CSV をダウンロード]
   * [!UICONTROL PDF をダウンロード]
   * [!UICONTROL  読み込みガイド付き分析 ]
   * [!UICONTROL  プロジェクトの読み込み ]
   * [!UICONTROL  新しいスコアカードが読み込まれました ]
   * [!UICONTROL  データディクショナリを開く ]
   * [!UICONTROL  インテリジェントキャプションを開く ]
   * [!UICONTROL  プロジェクト共有 ]
   * [!UICONTROL  実験パネルを実行 ]
   * [!UICONTROL  プロジェクトを保存 ]
   * [!UICONTROL  スコアカードが保存されました ]
   * [!UICONTROL ファイルを送信]
   * [!UICONTROL  スケジュールに従ってファイルを送信 ]
   * [!UICONTROL  任意のユーザーとプロジェクトを共有 ]
   * [!UICONTROL Workspace ユーザーとプロジェクトを共有 ]
* **[!UICONTROL 使用されるアトリビューションモデル]**：コンポーネントが使用するアトリビューションモデルのタイプ。 Dimension項目は次のとおりです。
   * [!UICONTROL  ラストタッチ ]
   * [!UICONTROL  ファーストタッチ ]
   * [!UICONTROL 線形]
   * [!UICONTROL パーティシペーション]
   * [!UICONTROL  同一タッチ ]
   * [!UICONTROL U字型 ]
   * [!UICONTROL J カーブ ]
   * [!UICONTROL  逆 J]
   * [!UICONTROL  タイムディケイ ]
   * [!UICONTROL カスタム]
   * [!UICONTROL アルゴリズム]
* **[!UICONTROL コンポーネント名]**：追加、削除または変更されたコンポーネントの名前。
* **[!UICONTROL コンポーネントタイプ]**：追加、削除または変更されたコンポーネントのタイプ。 Dimension項目は次のとおりです。
   * [!UICONTROL ディメンション]
   * [!UICONTROL 指標]
   * [!UICONTROL フィルター]
   * [!UICONTROL 計算指標]
   * [!UICONTROL 日付範囲]
   * [!UICONTROL 注釈]
   * [!UICONTROL アラート]
* **[!UICONTROL ログインユーザー]**：アクションを実行したユーザー。
* **[!UICONTROL 使用されるパネル]**：コンポーネントが追加、削除または変更されたパネル。 Dimension項目は次のとおりです。
   * [!UICONTROL アトリビューション]
   * [!UICONTROL 空のパネル]
   * [!UICONTROL 実験]
   * [!UICONTROL フリーフォーム]
   * [!UICONTROL 次または前の項目]
   * [!UICONTROL クイックインサイト]
   * [!UICONTROL トレンド]
   * [!UICONTROL ファネル]
   * [!UICONTROL ユーザーの増加率]
   * [!UICONTROL 影響]
   * [!UICONTROL ユーザーストリーム]
   * [!UICONTROL Retention]
   * [!UICONTROL 機能マトリックス]
* **[!UICONTROL プロジェクト名]**: プロジェクトのわかりやすい名前。
* **[!UICONTROL プロジェクトタイプ]**: プロジェクトのタイプ。 Dimension項目は次のとおりです。
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL ユーザー ID]**：イベントをトリガーしたユーザー ID。
* **[!UICONTROL 使用されたビジュアライゼーション]**：追加、削除または変更されたビジュアライゼーション。 Dimension項目は次のとおりです。
   * [!UICONTROL フリーフォームテーブル]
   * [!UICONTROL コホートテーブル]
   * [!UICONTROL フォールアウト]
   * [!UICONTROL フロー]
   * [!UICONTROL ジャーニー キャンバス レポートレット ]
   * [!UICONTROL 面グラフ]
   * [!UICONTROL 積み重ね面グラフ]
   * [!UICONTROL 棒グラフ]
   * [!UICONTROL  積み重ね棒グラフ ]
   * [!UICONTROL ブレット]
   * [!UICONTROL コンボ]
   * [!UICONTROL ドーナツ]
   * [!UICONTROL ヒストグラム]
   * [!UICONTROL 横棒グラフ]
   * [!UICONTROL  積み重ね横棒グラフ ]
   * [!UICONTROL  主要指標の概要 ]
   * [!UICONTROL 折れ線グラフ]
   * [!UICONTROL マップ]
   * [!UICONTROL 散布図]
   * [!UICONTROL  セクションヘッダー ]
   * [!UICONTROL 変更の概要]
   * [!UICONTROL 数値の概要]
   * [!UICONTROL テキスト]
   * [!UICONTROL ツリーマップ]
   * [!UICONTROL ベン図]

プロジェクトを単に開いたり表示したりしているだけの場合、製品の使用状況によって個々のプロジェクトコンポーネントが追跡されることはありません。 ただし、プロジェクトを開くユーザーアクションは追跡されます。
