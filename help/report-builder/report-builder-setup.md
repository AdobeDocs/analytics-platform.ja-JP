---
title: Report Builderの設定
description: Customer Journey AnalyticsでReport Builderを設定する方法について説明します。
role: User
feature: Report Builder
type: Documentation
exl-id: 99aedc28-05d5-4fc1-8c32-6e5d1d3b0f84
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/JAuvA8NU9j1Jx4bSw-JTHYF0c6mW249C6MWvzti-kB0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 539
ht-degree: 25%

---

# Report Builder の設定

この記事では、Microsoft ExcelでCustomer Journey Analytics用Report Builderを使用する要件について説明します。 アドインのインストール方法や設定方法を説明します。

## 要件

Report Builder Customer Journey Analytics版は、次のオペレーティングシステムおよびWeb ブラウザーでサポートされています。

### macOS

- macOS バージョン 10.x 以降
- すべての Excel バージョン

### Windows

- Windows 10、バージョン 1904 以降
- Excel バージョン 2106 以降

  すべての Windows デスクトップ Excel ユーザーは、アドインを使用するために Microsoft Edge Webview2 をインストールする必要があります。 インストールするには：

   1. <https://developer.microsoft.com/en-us/microsoft-edge/webview2/> にアクセスします。
   1. お使いのプラットフォームに適したバージョンの&#x200B;**[!UICONTROL Evergreen Standalone Installer]**&#x200B;を選択してダウンロードします。
   1. インストーラーを実行し、インストールプロンプトに従います。

### Web Office

- すべてのブラウザーとバージョンをサポートしています。


## Report Builder Excel アドイン

Report Builder Excel アドインをインストールして、Report Builder for Customer Journey Analyticsを使用します。 Report Builder Excel アドインをインストールすると、開いているExcel ブック内からReport Builderにアクセスできます。

### Report Builder アドインのダウンロードとインストール

Report Builder アドインをダウンロードしてインストールするには

1. Excel を起動し、新しいワークブックを開きます。

1. メインメニューから&#x200B;**[!UICONTROL 挿入]**/**[!UICONTROL アドイン]**/**[!UICONTROL アドインを取得]**&#x200B;を選択します。

1. Office アドインダイアログで、「**[!UICONTROL ストア]**」タブを選択します。

1. `Report Builder`を検索し、**[!UICONTROL 追加]**&#x200B;を選択します。

1. ライセンス条件とプライバシーポリシーのダイアログボックスで、**[!UICONTROL 続行]**&#x200B;を選択します。

「**[!UICONTROL ストア]**」タブが表示されない場合：

1. Excelで、メインメニューから&#x200B;**[!UICONTROL ファイル]** > **[!UICONTROL アカウント]** > **[!UICONTROL 設定を管理]**&#x200B;を選択します。

1. 「**[!UICONTROL オプションの接続されたエクスペリエンスを有効にする]**」の横にあるチェックボックスをオンにします。

1. Excel を再起動します。

お客様の組織がMicrosoft ストアへのアクセスをブロックする場合：

- Report Builder アドインの承認を依頼するには、IT部門またはセキュリティ部門にお問い合わせください。 承認が付与されたら、Office **[!UICONTROL アドイン]** ダイアログで「**[!UICONTROL 管理者管理]**」タブを選択します。

  ![Office アドインダイアログの「管理者管理」タブ。](./assets/image1.png){zoomable="yes"}

Report Builder アドインをインストールすると、**[!UICONTROL ホーム]** タブの下のExcel リボンに![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** アイコンが表示されます。

![ExcelのReport Builder アイコン &#x200B;](./assets/rb_app_icon.png){zoomable="yes"}


## Report Builder へのログイン

オペレーティングシステムまたはブラウザーにReport Builder for Excel アドインをインストールしたら、次の手順に従ってReport Builderにログインします。

1. Excel ワークブックを開きます。

1. ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**&#x200B;を選択して、Report Builderを起動します。

1. Adobe Report Builder ツールバーから、「**[!UICONTROL ログイン]**」を選択します。

   ![Report Builder ログインボタンをクリックします。](./assets/rb_login.png){zoomable="yes"}

1. Adobeのアカウント情報を入力します。 アカウント情報は、Customer Journey Analytics の資格情報と一致する必要があります。

   ![&#x200B; ログインアイコンと組織。](./assets/image4.png){zoomable="yes"}

ログインすると、パネルの上部にログインアイコンと組織が表示されます


## 組織の切り替え

最初にログインすると、プロファイルに割り当てられたデフォルトの組織、またはログインフローの一部として選択した組織にログインします。

1. ログイン時に表示される組織の名前を選択します。

1. 使用可能な組織のリストから組織を選択します。 自身がアクセス権を持っている組織のみが表示されます。

   ![&#x200B; アクセスできる組織のリスト。](./assets/image5.png){zoomable="yes"}

## ログアウト

Report Builderからログアウトするには：

1. 開いているワークブックに加えた変更を保存します。

1. アバターアイコンを選択して、ユーザープロファイルを表示します。

   ![&#x200B; ユーザープロファイルのアバターとログアウトボタン。](./assets/image6.png){zoomable="yes"}

1. **[!UICONTROL ログアウト]**&#x200B;を選択します。
