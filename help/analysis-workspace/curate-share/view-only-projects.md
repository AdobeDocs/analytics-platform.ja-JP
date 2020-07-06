---
description: Workspaceの表示のみのプロジェクト
keywords: View-only projects
title: 表示のみの Workspace プロジェクト
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 8%

---


# 表示のみの Workspace プロジェクト

>[!NOTE]
>
>Customer Journey Analytics内のAnalysis Workspaceに関するドキュメントを表示している。 この機能セットは、従来のAdobeAnalyticsの [Analysis Workspaceとは少し異なります](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html)。 [詳細情報...](/help/getting-started/cja-aa.md)

プロジェクト共有ワークフローを使用して、受信者に「表示のみ」として [プロジェクトを共有できます](/help/analysis-workspace/curate-share/share-projects.md)。 表示の管理ロールに配置された受信者は、より限定的なプロジェクト体験を受け取るようになります。 組織のデータ構造、Analysis Workspace、またはアドビAnalyticsの一般的な知識が低いユーザーにプロジェクトを共有し、安全な環境でデータやインサイトを利用したい場合に、この方法が望ましい場合があります。

![](assets/view-only-project.png)

## 無効な操作

表示のみのプロジェクトで無効になった操作には、次のものが含まれます。

* 左側のレールを隠す
* レポートスイート
* パネルカレンダーの日付範囲。 注意： 受信者にカレンダー制御を付与する場合は、日付範囲を含む [ドロップダウンフィルターを追加し](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html)ます。
* フリーフォームフィルター
* 表示可能な行のフリーフォーム数
* フリーフォーム行、列またはビジュアライゼーションの設定
* パネルセグメント
* 編集、挿入、コンポーネントメニュー
* ワークスペースのヒント

## 有効な操作

表示のみのプロジェクトで有効になっているインタラクションのいくつかは、次のとおりです。

| 面グラフ | 有効な操作 |
|---|---|
| フリーフォームテーブル | <ul><li>ページネーションと並べ替え</li><li>ホバリング</li><li>リンクされたビジュアライゼーションを更新するセルの選択</li><li>右クリック/ビジュアライゼーションリンクを取得</li><li>右クリック/クリップボードにコピー</li></ul> |
| ビジュアライゼーション | <ul><li>クリックして凡例のオン/オフを切り替え</li><li>ホバリング</li><li>右クリック/ビジュアライゼーションリンクを取得</li><li>折りたたみ/展開</li><li>フロー — フローノードを展開</li><li>マップ — ズーム</li></ul> |
| パネル | <ul><li>対話型ドロップダウンフィルター</li><li>右クリック/パネルリンクを取得</li><li>折りたたみ/展開</li></ul> |
| プロジェクト | <ul><li>すべての情報アイコンの検査</li><li>プロジェクトメニュー — 新規、開く、ランディングページとして設定、更新、CSV/PDFのダウンロード、限られたプロジェクト情報および設定</li><li>共有メニュー — プロジェクトリンクを取得、今すぐファイルを送信</li><li>[ヘルプ]メニュー — [ヒント]および[デバッガ]オプション以外のすべてのアクション</li></ul> |
