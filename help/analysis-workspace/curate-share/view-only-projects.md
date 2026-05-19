---
description: Analysis Workspaceの読み取り専用プロジェクトのエクスペリエンスについて説明します。
keywords: 読み取り専用プロジェクト
title: 読み取り専用プロジェクト
feature: Curate and Share
exl-id: 2bc26444-aeea-4695-92a5-a2b45ac18e0d
role: User
autotag-review: '2026-05-19T08:24:39.395Z'
TQID: 'https://experienceleague.adobe.com/unXy2ZoBYHCtuKNQ9VfM3iJEEjVUU-fr-XRQ7pci5fo'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a3b826fd-7a63-4a83-8736-83eee6668f44
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 328
ht-degree: 39%

---

# 読み取り専用プロジェクト

[共有機能](/help/analysis-workspace/curate-share/share-projects.md)を使用して、プロジェクトを受信者に読み取り専用として共有できます。 **[!UICONTROL 読み取り専用]**&#x200B;の役割に配置された受信者は、より限定的なプロジェクト体験を受け取ることができます。

これは、組織のデータ構造、Analysis WorkspaceやCustomer Journey Analyticsに精通していないユーザーにプロジェクトを共有している場合に望ましい場合がありますが、安全な環境でデータとインサイトを利用することを望んでいます。

![読み取り専用として共有](assets/read-only-project-sender.png)

読み取り専用の受信者のインタラクションは制限されています。

![読み取り専用として共有](assets/read-only-project-receiver.png)

## 無効な操作

表示のみのプロジェクトで無効になる操作には、次のものが含まれます。

* 非表示の左パネル
* パネルカレンダーの日付範囲 注意：受信者にカレンダーコントロールを付与する場合は、日付範囲[&#128279;](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=ja)の ドロップダウンセグメントを追加します。
* フリーフォームセグメンテーション
* 表示可能な行のフリーフォーム数
* フリーフォーム行、列またはビジュアライゼーションの設定
* パネルセグメント
* 編集、挿入、コンポーネントメニュー
* Workspace のヒント

## 有効な操作

表示のみのプロジェクトで有効になっているインタラクションのいくつかは、次のとおりです。

| 面グラフ | 有効な操作 |
| --- | --- |
| **フリーフォームテーブル** | <li>ページネーションと並べ替え</li><li>ホバリング</li><li>リンクされたビジュアライゼーションを更新するセル選択</li><li>コンテキストメニュー/ビジュアライゼーションリンクの取得</li><li>コンテキストメニュー/クリップボードにコピー</li> |
| **ビジュアライゼーション** | <li>クリックして凡例のオン／オフを切り替え</li><li>ホバリング</li><li>コンテキストメニュー/ビジュアライゼーションリンクの取得</li><li>折りたたみ／展開</li><li>フロー — フローノードを展開</li><li>マップ — ズーム</li></ul> |
| **パネル** | <li>インタラクティブなドロップダウンセグメント</li><li>コンテキストメニュー/パネルリンクを取得から</li><li>折りたたみ／展開</li> |
| **プロジェクト** | <li>すべての情報アイコンの検査</li><li>プロジェクトメニュー — 新規、開く、ランディングページとして設定、更新、CSV／PDF をダウンロード、限られたプロジェクト情報および設定</li><li>共有メニュー — プロジェクトリンクを取得、今すぐファイルを送信</li><li>ヘルプメニュー — 「ヒント」および「デバッガー」オプション以外のすべてのアクション</li> |


## 誰でも共有できるエクスペリエンス

[誰とでも共有](share-projects.md#share-a-project-with-anyone-no-login-required)を使用してプロジェクトを選択した場合、リンクの受信者はプロジェクトを表示するだけで、プロジェクトを操作することはできません。

![誰とでも共有](assets/share-with-anyone-receiver.png)
