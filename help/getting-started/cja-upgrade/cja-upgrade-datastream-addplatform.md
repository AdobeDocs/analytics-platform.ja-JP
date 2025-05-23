---
title: Customer Journey Analytics のスキーマの作成
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパスについて説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '274'
ht-degree: 100%

---

# Platform をサービスとしてデータストリームに追加 {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Adobe Experience Platform をサービスとしてデータストリームに追加"
>abstract="データストリームには、データの送信先となる 1 つ以上のサービスが必要です。Adobe Experience Platform をデータストリームのサービスとして設定します。<br><br>データストリームへのサービスの追加は簡単なプロセスで、完了するまでに数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

この節の手順を完了する前に、データストリームが既に存在している必要があります。データストリームを作成するタイミングと方法は、次のように Adobe Analytics の実装によって異なります。

* Adobe Analytics 実装で Web SDK または Web SDK 拡張機能を使用する場合、アップグレードプロセスの前に、Adobe Analytics 環境でデータストリームを使用できました。

* 他の Adobe Analytics 実装の場合、[Customer Journey Analytics で使用するデータストリームの作成](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)で説明されているように、データストリームの作成はアップグレードプロセスの一部です。

データストリームを使用できる状態で、Platform をサービスとして追加する必要があります。

1. Adobe Experience Platform UI の左パネルで、「[!UICONTROL データ収集]」から「**[!UICONTROL データストリーム]**」を選択します。

1. 以前に設定したデータストリームを選択します。<!--true?-->

1. 「**[!UICONTROL サービスを追加]**」を選択します。

1. [!UICONTROL サービスを追加画面]で、次の操作を行います。

   1. [!UICONTROL サービス]リストから&#x200B;**[!UICONTROL Adobe Experience Platform]** を選択します。

   1. 「**[!UICONTROL 有効]**」が選択されていることを確認します。

   1. [!UICONTROL イベントデータセット]リストからお使いのデータセットを選択します。

      ![Datastream AEP サービス](./assets/datastream-aep-service.png)

   1. その他の設定はそのままにし、「**[!UICONTROL 保存]**」を選択してデータストリームを保存します。

   これで、web サイトから収集したデータを Adobe Experience Platform でデータセットに転送するように、データストリームが設定されました。

   データストリームの設定方法と機密データの処理方法について詳しくは、[データストリームの概要](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=ja)を参照してください。

{{upgrade-final-step}}
