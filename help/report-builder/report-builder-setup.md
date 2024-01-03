---
title: Customer Journey Analytics での Report Builder の設定方法
description: Customer Journey AnalyticsでReport Builderを設定する方法を説明します
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 99aedc28-05d5-4fc1-8c32-6e5d1d3b0f84
solution: Customer Journey Analytics
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 89%

---

# Report Builder の設定

Excel のアドインメニューを使用して、Report Builder にすばやくアクセスできます。

## 要件

Customer Journey Analytics の Report Builder は、次のオペレーティングシステムおよび web ブラウザーでサポートされています。

### macOS

- macOS バージョン 10.x 以降
- すべての Excel バージョン

### Windows

- Windows 10、バージョン 1904 以降
- Excel バージョン 2106 以降

  すべての Windows デスクトップ Excel ユーザーは、アドインを使用するために Microsoft Edge Webview2 をインストールする必要があります。コントローラーをインストールするには：

   1. <https://aka.ms/webview2installer> にアクセスします。
   1. Evergreen スタンドアロンインストーラーを選択してダウンロードします。
   1. インストールプロンプトに従います。

### Web Office

- すべてのブラウザーとバージョンをサポート


## Report Builder Excel アドイン

Customer Journey Analytics の Report Builder を使用するには、Report Builder Excel アドインをインストールする必要があります。Report Builder Excel アドインをインストールすると、開いている Excel ワークブック内から Report Builder にアクセスできます。

### Report Builder アドインのダウンロードとインストール

Report Builder アドインをダウンロードしてインストールするには

1. Excel を起動し、新しいワークブックを開きます。

1. 挿入／アドインの取得を選択します。

1. Office アドインダイアログで、「ストア」タブを選択します。

1. 「Report Builder」を検索し、「追加」をクリックします。

1. 「ライセンス条件とプライバシーポリシー」ダイアログボックスで、「続行」をクリックします。

**「ストア」タブが表示されない場合**

1. Excel で、ファイル／アカウント／設定を管理を選択します。

1. 「オプションの接続されたエクスペリエンスを有効にする」の横のボックスをオンにします。

1. Excel を再起動します。

**組織が Microsoft ストアへのアクセスをブロックしている場合**

IT またはセキュリティチームに連絡して、Report Builder アドインの承認をリクエストします。承認されたら、Office アドインダイアログで、「管理者による管理」タブを選択します。

![Office アドインダイアログの [ 管理 ] タブ](./assets/image1.png)

Report Builder アドインをインストールすると、Report Builder アイコンが Excel の「ホーム」タブのリボンに表示されます。Excel リボンの「ホーム」タブに「Report Builder」アイコンが表示されます。

![Excel のReport Builderアイコン](./assets/rb_app_icon.png)

## Report Builder へのログイン

使用しているプラットフォームまたはブラウザーに Report Builder for Excel アドインをインストールした後、次の手順に従って Report Builder にログインします。

1. Excel ワークブックを開きます。

1. Report Builder アイコンをクリックして、Report Builder を起動します。

1. Adobe Report Builder ツールバーで、「**ログイン**」をクリックします。

   ![「ログインReport Builder」ボタンをクリックします。](./assets/rb_login.png)

1. Adobe Experience ID アカウント情報を入力します。アカウント情報は、Customer Journey Analytics の資格情報と一致する必要があります。

   ![ログインアイコンと組織。](./assets/image4.png)

ログインすると、パネルの上部にログインアイコンと組織が表示されます

## 組織の切り替え

最初のログインでは、プロファイルに割り当てられたデフォルトの組織にログインすることになります。

1. ログイン時に表示された組織の名前をクリックします。

1. 使用可能な組織のリストから組織を選択します。自身がアクセス権を持っている組織のみが表示されます。

   ![アクセスできる組織のリスト。](./assets/image5.png)

## ログアウト

ユーザープロファイルで Report Builder からログアウトできます。

1. 開いているワークブックに加えた変更を保存します。

1. アバターアイコンをクリックして、ユーザープロファイルを表示します。

   ![ユーザープロファイルのアバターと「サインアウト」ボタン。](./assets/image6.png)

1. 「**ログアウト**」をクリックします。
