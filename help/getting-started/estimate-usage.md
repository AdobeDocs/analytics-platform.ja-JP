---
title: CJA 使用状況の推定と管理
description: 2 つの使用状況の推定方法と 1 つの管理方法を示します。
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 68%

---


# CJA 使用状況の推定と管理

CJA の使用方法を理解するには、次の 2 つの方法を使用できます。

* 各接続のイベントデータを追加します ( **接続サイズの予測** 下 )
* Analysis Workspaceを使用して…

CJA の使用を管理するには：

* CJA API の使用

## 接続サイズの予測 {#estimate-size}

現在、にあるイベントデータの行数を知る必要が生じる場合があります。 [!UICONTROL Customer Journey Analytics]. 組織のイベントデータレコード（データ行）の使用状況を正確に把握するには、**組織が作成した各接続に対して**、次の手順を実行します。

>[!NOTE]
>
>これは、Adobeがその日に最新の使用状況レポートを実行するので、毎月最初の金曜日に実行します。

1. [!UICONTROL Customer Journey Analytics] で、「**[!UICONTROL 接続]**」タブをクリックします。

   これで、現在のすべての接続のリストが表示されます。

1. 各接続名をクリックして、接続マネージャーに移動します。

1. 作成されたすべての接続で&#x200B;**[!UICONTROL 使用可能なイベントデータのレコード]**&#x200B;を合計します（接続のサイズによっては、数字の表示に時間がかかる場合があります）。

   ![イベントデータ](assets/event-data.png)

1. すべてのイベントデータ行の合計が表示されたら、自社とアドビで合意した Customer Journey Analytics 契約の「データ行」使用権を確認してください。

   これにより、受注で許可されているデータ行の最大数がわかります。手順 3 で取得したデータ行数がこの許可されている行数より多い場合は、データ使用量の超過が発生しています。

1. この状況を修正するには、次のようなオプションがあります。

   * [データ保持設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ja#set-rolling-window-for-connection-data-retention)を変更する。
   * [未使用の接続を削除する](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components)。
   * [AEP のデータセットを削除する](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components)。
   * 追加容量のライセンスを取得する（アドビのアカウントマネージャーにお問い合わせください）。
