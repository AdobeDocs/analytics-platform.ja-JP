---
description: 電子メールを使用して Analysis Workspace を送信したり Analysis Workspace の配信をスケジュールしたりします。
keywords: Analysis Workspace
title: プロジェクトのスケジュール
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 6f3ae14e4d34de17ed64ae30cee4611e4d6f3226
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 79%

---

# プロジェクトのスケジュール

ワークスペースから **[!UICONTROL 共有]** メニューを使用して、選択した受信者に電子メールでAnalysis Workspaceプロジェクトを送信できます。 ファイルは CSV 形式または PDF 形式で送信できます。

## ファイルを今すぐ送信 {#now}

電子メールで受信者に直ちにファイルを送信するには、以下を実行します。

1. クリック **[!UICONTROL 共有] > [!UICONTROL ファイルを書き出し]**.
1. ファイルタイプを指定します。
   * [!UICONTROL **CSV**]：プレーンテキストデータが必要な場合は、このオプションを選択します。
   * [!UICONTROL **PDF**]：ダウンロードしたファイルに、プロジェクト内に表示されている（表示されている）すべてのテーブルとビジュアライゼーションを含める場合は、このオプションを選択します。
1. （オプション）受信するファイルについて説明する説明を E メールに追加します。
1. 受信者またはグループを追加します。電子メールアドレスを入力することもできます。
1. （Healthcare Shield のお客様のみ）パスワードを入力します。予定レポートのパスワード保護の節を参照してください。
1. 「**[!UICONTROL 今すぐ送信]**」をクリックします。
1. （任意）「**[!UICONTROL スケジュールオプションを表示する]** 」をクリックして、配信スケジュールを指定します。

![ファイルを今すぐ送信](assets/send-file-no-scheduling-options.JPG)

## ファイルをスケジュールに従って送信 {#schedule}

定期的なスケジュールでファイルを電子メールで受信者に送信するには、以下を実行します。

1. クリック **[!UICONTROL 共有] > [!UICONTROL スケジュールファイルの書き出し]**.
1. ファイルタイプ（CSV または PDF）を指定します。
1. （任意）電子メールに含まれる、受信ファイルについての説明を追加します。
1. 受信者またはグループを追加します。電子メールアドレスを入力することもできます。
1. （Healthcare Shield のお客様のみ）パスワードを入力します。予定レポートのパスワード保護の節を参照してください。
1. 入力時に「開始」と「終了」を変更して、スケジュールを配信する範囲を指定します。終了日は、スケジュールの作成日または変更日から 1 年以内に設定する必要があります。
1. 配信頻度を指定します。頻度ごとに異なるカスタマイズが可能です。
1. 「**[!UICONTROL 送信スケジュール]**」をクリックします。

![](assets/send-file.JPG)

## スケジュール済みプロジェクトマネージャー {#manager}

スケジュールされたAnalysis Workspaceプロジェクトは、以下で管理できます。 **[!UICONTROL Analytics] > [!UICONTROL コンポーネント] > [!UICONTROL スケジュール済みプロジェクト]**.

詳しくは、 [スケジュール済みプロジェクト](/help/components/scheduled-projects-manager.md)

## スケジュールされたプロジェクトのパスワード保護 {#password}

>[!NOTE]
>
>スケジュール済みプロジェクトをパスワードで保護するオプションは、 [医療用盾](https://business.adobe.com/jp/solutions/experience-cloud-for-healthcare.html) アドオン製品。

アドビは、スケジュールされたプロジェクトを .pdf 形式と .csv 形式のどちらで送信した場合でも、パスワードを使用して暗号化します。

Healthcare Shield SKU を購入して有効にすると、次の 2 つの状況において、スケジュールされたプロジェクトのパスワードを作成するプロンプトがポップアップ表示されます。

* 誰かがスケジュールされたプロジェクトを新規作成する場合。

* 既存のスケジュールされたプロジェクトが送信されようとしている場合。現在スケジュールされているプロジェクトは、パスワード保護が行われるまで無効になります。スケジュールされたプロジェクトの所有者に、この影響に関するメールが送信されます。

![パスワード保護](assets/password.png)

### パスワード要件

パスワード要件は、アドビの規格に準拠しており、数字 1 文字以上および特殊文字 1 文字以上を含める 8 文字以上のパスワードが必要です。

### 新しくスケジュールされたプロジェクトのパスワード保護

1. プロジェクトを保存したら、**[!UICONTROL 共有]**／**[!UICONTROL 今すぐファイルを送信]**&#x200B;または[!UICONTROL 共有]／**[!UICONTROL スケジュールに従ってファイルを送信]**&#x200B;に移動します。
1. [今すぐファイルを送信](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=ja#now)または[スケジュールに従ってファイルを送信](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=ja#schedule)で、上記の手順に従います。

### 既存のスケジュール済みプロジェクトのパスワード保護

プロジェクトがスケジュールされる前に、プロジェクトの所有者に次のようなメールが送信されます。

![電子メール](assets/email-password.png)

1. Customer Journey Analytics にログインし直します。
1. 「**[!UICONTROL スケジュールされたプロジェクトを表示]**」をクリックします。
1. **[!UICONTROL スケジュールされたプロジェクトを編集]**&#x200B;ダイアログで、パスワードを入力、再入力します。
1. スケジュールされたプロジェクトの受信者に（のみ）、このパスワードを知らせます。


