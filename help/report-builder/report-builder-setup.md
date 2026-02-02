---
title: Report Builderの設定
description: Customer Journey AnalyticsでReport Builderを設定する方法について説明します。
role: User
feature: Report Builder
type: Documentation
exl-id: 99aedc28-05d5-4fc1-8c32-6e5d1d3b0f84
solution: Customer Journey Analytics
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 25%

---

# Report Builder の設定

この記事では、Microsoft Excel でReport Builder for Customer Journey Analyticsを使用するための要件の概要を説明します。 アドインのインストール方法とセットアップ方法について説明します。

## 要件

Customer Journey AnalyticsのReport Builderは、次のオペレーティングシステムおよび web ブラウザーでサポートされています。

### macOS

- macOS バージョン 10.x 以降
- すべての Excel バージョン

### Windows

- Windows 10、バージョン 1904 以降
- Excel バージョン 2106 以降

  すべての Windows デスクトップ Excel ユーザーは、アドインを使用するために Microsoft Edge Webview2 をインストールする必要があります。次の手順でインストールします。

   1. <https://developer.microsoft.com/en-us/microsoft-edge/webview2/> にアクセスします。
   1. プラットフォームに適したバージョンの **[!UICONTROL Evergreen スタンドアロンインストーラー]** を選択してダウンロードします。
   1. インストーラーを実行し、インストールプロンプトに従います。

### Web Office

- すべてのブラウザーとバージョンをサポートしています。


## Report Builder Excel アドイン

Report Builder for Customer Journey Analyticsを使用するには、Report Builder Excel アドインをインストールします。 Report Builder Excel アドインをインストールすると、開いている Excel ワークブック内からReport Builderにアクセスできます。

### Report Builder アドインのダウンロードとインストール

Report Builder アドインをダウンロードしてインストールするには

1. Excel を起動し、新しいワークブックを開きます。

1. メインメニューから **[!UICONTROL 挿入]**/**[!UICONTROL アドイン]**/**[!UICONTROL アドインを取得]** を選択します。

1. Office アドインダイアログで、「**[!UICONTROL ストア]**」タブを選択します。

1. `Report Builder` を検索し、「**[!UICONTROL 追加]**」を選択します。

1. ライセンス条項とプライバシーポリシーのダイアログボックスで、「**[!UICONTROL 続行]**」を選択します。

**[!UICONTROL ストア]** タブが表示されない場合：

1. Excel で、メインメニューから **[!UICONTROL ファイル]**/**[!UICONTROL アカウント]**/**[!UICONTROL 設定を管理]** を選択します。

1. **[!UICONTROL オプションの接続されたエクスペリエンスを有効にする]** の横のチェックボックスをオンにします。

1. Excel を再起動します。

Microsoft ストアへのアクセスがブロックされている場合：

- IT またはセキュリティチームに連絡して、Report Builder アドインの承認をリクエストします。 承認されたら、Office **[!UICONTROL アドイン]** ダイアログで、「**[!UICONTROL 管理者による管理]**」タブを選択します。

  ![Office アドインダイアログの「管理者による管理」タブ ](./assets/image1.png){zoomable="yes"}

Report Builder アドインをインストールすると、Excel のリボンの ![ ホーム ](/help/assets/icons/AdobeLogoRedOnWhite.svg) タブの下に **[!UICONTROL AdobeLogoRedonWhite]** **[!UICONTROL Report Builder]** アイコンが表示されます。

![Excel の「Report Builder」アイコン ](./assets/rb_app_icon.png){zoomable="yes"}


## Report Builder へのログイン

使用しているプラットフォームまたはブラウザーにReport Builder for Excel アドインをインストールしたら、次の手順に従ってReport Builderにログインします。

1. Excel ワークブックを開きます。

1. ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** を選択して、Report Builderを起動します。

1. Adobe Report Builderのツールバーで「**[!UICONTROL ログイン]**」を選択します。

   ![ 「Report Builderへのログイン」ボタンをクリックします。](./assets/rb_login.png){zoomable="yes"}

1. Adobe アカウント情報を入力します。 アカウント情報は、Customer Journey Analytics の資格情報と一致する必要があります。

   ![ ログインアイコンと組織。](./assets/image4.png){zoomable="yes"}

ログインすると、パネルの上部にログインアイコンと組織が表示されます


## 組織の切り替え

最初のログインでは、プロファイルに割り当てられたデフォルトの組織、またはログインフローの一部として選択した組織にログインすることになります。

1. ログイン時に表示される組織の名前を選択します。

1. 使用可能な組織のリストから組織を選択します。自身がアクセス権を持っている組織のみが表示されます。

   ![ アクセスできる組織のリスト ](./assets/image5.png){zoomable="yes"}

## ログアウト

Report Builderからログアウトするには：

1. 開いているワークブックに加えた変更を保存します。

1. 「アバター」アイコンを選択して、ユーザープロファイルを表示します。

   ![ ユーザープロファイルのアバターと「ログアウト」ボタン ](./assets/image6.png){zoomable="yes"}

1. **[!UICONTROL ログアウト]** を選択します。
