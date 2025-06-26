---
description: Workspaceの読み取り専用プロジェクト
keywords: 読み取り専用プロジェクト
title: 読み取り専用プロジェクト
feature: Curate and Share
exl-id: 2bc26444-aeea-4695-92a5-a2b45ac18e0d
role: User
source-git-commit: a462e736ddcdf1a5ea84a85eea2c2ce0b8a34fb0
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 37%

---

# 読み取り専用プロジェクト

[ 共有機能 ](/help/analysis-workspace/curate-share/share-projects.md) を使用して、受信者に読み取り専用としてプロジェクトを共有できます。 **[!UICONTROL 読み取り専用]** の役割に配置された受信者には、プロジェクトエクスペリエンスが制限されます。

組織のデータ構造、Analysis WorkspaceまたはCustomer Journey Analytics全般に慣れていないユーザーにプロジェクトを共有し、安全な環境でデータやインサイトを利用してもらいたい場合には、この方法が適しているかもしれません。

![ 読み取り専用として共有 ](assets/read-only-project-sender.png)

読み取り専用受信者に対するインタラクションは制限されています。

![ 読み取り専用受信済みとして共有 ](assets/read-only-project-receiver.png)

## 無効な操作

表示のみのプロジェクトで無効になる操作には、次のものが含まれます。

* 非表示の左パネル
* パネルカレンダーの日付範囲メモ：受信者にカレンダーコントロールを付与する場合は、[ 日付範囲を含むドロップダウンセグメント ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=ja) にを追加します。
* フリーフォームセグメント化
* 表示可能な行のフリーフォーム数
* フリーフォーム行、列またはビジュアライゼーションの設定
* パネルセグメント
* 編集、挿入、コンポーネントメニュー
* Workspace のヒント

## 有効な操作

表示のみのプロジェクトで有効になっているインタラクションのいくつかは、次のとおりです。

| 面グラフ | 有効な操作 |
| --- | --- |
| フリーフォームテーブル | <ul><li>ページネーションと並べ替え</li><li>ホバリング</li><li>リンクされたビジュアライゼーションを更新するセル選択</li><li>コンテキストメニュー/ ビジュアライゼーションリンクを取得から</li><li>コンテキストメニュー/ クリップボードにコピーから</li></ul> |
| ビジュアライゼーション | <ul><li>クリックして凡例のオン／オフを切り替え</li><li>ホバリング</li><li>コンテキストメニュー/ ビジュアライゼーションリンクを取得から</li><li>折りたたみ／展開</li><li>フロー — フローノードを展開</li><li>マップ — ズーム</li></ul> |
| パネル | <ul><li>インタラクティブなドロップダウンセグメント</li><li>コンテキストメニュー/ パネルリンクを取得から</li><li>折りたたみ／展開</li></ul> |
| プロジェクト | <ul><li>すべての情報アイコンの検査</li><li>プロジェクトメニュー — 新規、開く、ランディングページとして設定、更新、CSV／PDF をダウンロード、限られたプロジェクト情報および設定</li><li>共有メニュー — プロジェクトリンクを取得、今すぐファイルを送信</li><li>ヘルプメニュー — 「ヒント」および「デバッガー」オプション以外のすべてのアクション</li></ul> |


## すべてのユーザーとエクスペリエンスを共有

[ 任意のユーザーと共有 ](share-projects.md#share-a-project-with-anyone-no-login-required) を使用してプロジェクトを選択した場合、リンクの受信者は、プロジェクトを表示するだけで、プロジェクトを操作することはできません。

![ 任意のユーザーと共有 ](assets/share-with-anyone-receiver.png)
