---
title: 製品使用状況の概要
description: 組織が Customer Journey Analytics をどのように使用しているかに関するインサイトとレポートを表示します。
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 22f3059ffef5df76028f36ffa00da8f98956dee1
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 91%

---

# 製品使用状況の概要

製品の使用状況により、組織が Customer Journey Analytics をどのように使用しているかに関する分析データを表示できます。これは、Customer Journey Analytics を使用するすべての組織で利用できます。有効にすると、次の Adobe Experience Platform コンポーネントが自動的に作成およびフックされます。これらのコンポーネントはすべてシステムが所有し、読み取り専用で、編集できません。

* Adobe Experience Platform のスキーマ
* Adobe Experience Platform のデータセット
* Customer Journey Analytics の接続
* Customer Journey Analytics のデータビュー

有効にすると、すべてのデータ収集と設定が自動的に設定されます。ユーザーが Analysis Workspace でアクションを実行するたびに、そのアクションが追跡され、レポートに使用できます。

>[!IMPORTANT]
>
>製品の使用状況を有効にすると、使用状況データがAdobe Experience Platform データレイクに保存されます。 この機能を有効にすることで生成される追加のデータセットに対応できるように、組織のデータレイクストレージの割り当てを確認します。
>
>この機能は、ライセンスを取得したCustomer Journey Analytics レポートの行の制限やイベントデータの使用権限にはカウントされません。

## 製品の使用状況を有効にする

**[!UICONTROL Customer Journey Analytics]**／**[!UICONTROL ツール]**／**[!UICONTROL 製品の使用状況]**

Customer Journey Analytics のインターフェイスのこのセクションに移動すると、[データ設定](data-settings.md)に移動し、この機能を有効にできます。

## 使用可能なディメンション

製品の使用状況を有効にすると、次のディメンションを使用できます。ディメンション設定を変更する場合は、システム所有のデータビューのコピーを作成し、コピーしたデータビューを Analysis Workspace で使用します。

* **[!UICONTROL アクション名]**：ユーザーが実行したアクションのタイプ。データビュー設定でコピーを作成して、このディメンションを目的の指標として使用できます。ディメンション項目には以下が含まれます。
   * [!UICONTROL アトリビューションを追加]
   * [!UICONTROL コンポーネントを追加]
   * [!UICONTROL パネルを追加]
   * [!UICONTROL ビジュアライゼーションを追加]
   * [!UICONTROL 新しいガイド付き分析を作成]
   * [!UICONTROL 新しいプロジェクトを作成]
   * [!UICONTROL コンポーネントをキュレート]
   * [!UICONTROL CSV をダウンロード]
   * [!UICONTROL PDF をダウンロード]
   * [!UICONTROL ガイド付き分析を読み込み]
   * [!UICONTROL プロジェクトを読み込み]
   * [!UICONTROL 読み込んだ新しいスコアカード]
   * [!UICONTROL データ辞書を開く]
   * [!UICONTROL インテリジェントキャプションを開く]
   * [!UICONTROL プロジェクトの共有]
   * [!UICONTROL 実験パネルを実行]
   * [!UICONTROL プロジェクトを保存]
   * [!UICONTROL 保存したスコアカード]
   * [!UICONTROL ファイルを送信]
   * [!UICONTROL スケジュールに従ってファイルを送信]
   * [!UICONTROL 任意のユーザーとプロジェクトを共有]
   * [!UICONTROL Workspace ユーザーとプロジェクトを共有]
   * [!UICONTROL データビューを切り替え]
* **[!UICONTROL アトリビューションモデルの使用]**：コンポーネントが使用するアトリビューションモデルのタイプ。 ディメンション項目には以下が含まれます。
   * [!UICONTROL ラストタッチ]
   * [!UICONTROL ファーストタッチ]
   * [!UICONTROL 線形]
   * [!UICONTROL パーティシペーション]
   * [!UICONTROL 同じタッチ]
   * [!UICONTROL U 字型]
   * [!UICONTROL J カーブ]
   * [!UICONTROL 逆 J]
   * [!UICONTROL タイムディケイ]
   * [!UICONTROL カスタム]
   * [!UICONTROL アルゴリズム]
* **[!UICONTROL コンポーネント ID]**：追加、削除または変更されたコンポーネントの ID。
* **[!UICONTROL コンポーネント名]**：追加、削除または変更されたコンポーネントのわかりやすい名前。
* **[!UICONTROL コンポーネントタイプ]**：追加、削除または変更されたコンポーネントのタイプ。 ディメンション項目には以下が含まれます。
   * [!UICONTROL ディメンション]
   * [!UICONTROL 指標]
   * [!UICONTROL セグメント]
   * [!UICONTROL 計算指標]
   * [!UICONTROL 日付範囲]
   * [!UICONTROL 注釈]
   * [!UICONTROL アラート]
* **[!UICONTROL データビュー ID]**：データビューの ID。
* **[!UICONTROL データビュー名]**：データビューのわかりやすい名前。
* **[!UICONTROL ログインユーザー]**：アクションを実行したユーザー。
* **[!UICONTROL 使用したパネル]**：追加、削除または変更されたパネル。ディメンション項目には以下が含まれます。
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
* **[!UICONTROL プロジェクト ID]**：プロジェクトの ID。
* **[!UICONTROL プロジェクト名]**：プロジェクトのわかりやすい名前。
* **[!UICONTROL プロジェクトタイプ]**：プロジェクトのタイプ。ディメンション項目には以下が含まれます。
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL 使用したビジュアライゼーション]**：追加、削除または変更されたビジュアライゼーション。ディメンション項目には以下が含まれます。
   * [!UICONTROL フリーフォームテーブル]
   * [!UICONTROL コホートテーブル]
   * [!UICONTROL フォールアウト]
   * [!UICONTROL フロー]
   * [!UICONTROL ジャーニーキャンバスレポートレット]
   * [!UICONTROL 面グラフ]
   * [!UICONTROL 積み重ね面グラフ]
   * [!UICONTROL 棒グラフ]
   * [!UICONTROL 積み重ね棒グラフ]
   * [!UICONTROL ブレット]
   * [!UICONTROL コンボ]
   * [!UICONTROL ドーナツ]
   * [!UICONTROL ヒストグラム]
   * [!UICONTROL 横棒グラフ]
   * [!UICONTROL 積み重ね横棒グラフ]
   * [!UICONTROL 主要指標の概要]
   * [!UICONTROL 折れ線グラフ]
   * [!UICONTROL マップ]
   * [!UICONTROL 散布図]
   * [!UICONTROL セクションヘッダー]
   * [!UICONTROL 変更の概要]
   * [!UICONTROL 数値の概要]
   * [!UICONTROL テキスト]
   * [!UICONTROL ツリーマップ]
   * [!UICONTROL ベン図]

プロジェクトを単に開いたり表示したりしているだけの場合、製品の使用状況によって個々のプロジェクトコンポーネントが追跡されることはありません。ただし、プロジェクトを開くというユーザーアクションは追跡されます。

## 使用可能なテンプレート

この機能によって自動生成されたコンポーネントを使用する[アドビテンプレート](/help/analysis-workspace/templates/use-templates.md)を使用できます。

**[!UICONTROL アドビテンプレート]**／**[!UICONTROL その他]**／**[!UICONTROL 製品の使用状況の概要]**

データビューセレクターで、製品の使用状況から自動的に作成されたデータビューを選択し、**[!UICONTROL 製品の使用状況の概要]**&#x200B;テンプレートを選択します。「**[!UICONTROL プレビュー]**」を選択してテンプレートで使用するパネルを確認し、理想的なユースケースの詳細を見るか、「**[!UICONTROL テンプレートを使用]**」を選択して Analysis Workspace で開きます。
