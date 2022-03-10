---
title: CJA 接続のサイズの見積り方法
description: Customer Journey Analytics の現在の使用状況を報告する
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
feature: Connections
source-git-commit: cd48a91ca3affc39cf71451bdd8a44ca7669523b
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 51%

---

# 接続サイズの予測

現在 [!UICONTROL Customer Journey Analytics] にあるデータの行数を知る必要がある場合があります。組織のイベントデータレコード（データ行）の使用状況を正確に把握するには、次の手順を実行します **組織が作成した各接続に対して**.

1. [!UICONTROL Customer Journey Analytics] で、「**[!UICONTROL 接続]**」タブをクリックします。

   これで、現在のすべての接続のリストが表示されます。

1. 各接続名をクリックして、接続マネージャに移動します。

1. 追加する **[!UICONTROL 使用可能なイベントデータのレコード]** （作成されたすべての接続用） （接続のサイズによっては、数の表示に時間がかかる場合があります）。

   ![イベントデータ](assets/event-data.png)

1. すべてのCustomer Journey Analyticsデータ行の合計を取得したら、Adobeで署名したイベント契約の「データの行」使用権限を調べます。

   これにより、受注で許可されるデータの最大行数が得られます。 手順 3 で取得したデータの行数がこの数より多い場合は、超過分のデータが発生しています。

1. この状況を修正するには、次のいくつかのオプションがあります。

   * を [データ保持設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ja#set-rolling-window-for-connection-data-retention).
   * [未使用の接続を削除します](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components).
   * [AEP でのデータセットの削除](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components).
   * 追加容量のライセンスを取得するには、Adobeのアカウントマネージャーにお問い合わせください。

## 使用超過について

使用制限は、Adobeが日々厳密に監視および適用します。 「データの行」とは、Customer Journey Analytics内の分析に使用できるデータの 1 日平均行を意味します。

契約に使用する権利付与の行数が 100 万に制限されているとします。 Customer Journey Analyticsを使用した Day 1 で、200 万行のデータをアップロードしたとします。 2 日目には、100 万行を削除し、使用量を最大限に抑えます。 1 日目の過剰使用料は引き続き発生します。

## 不一致の診断

場合によっては、接続によって取り込まれるイベントの合計数が [!UICONTROL Adobe Experience Platform] のデータセットの行数と異なることがあります。この例の場合、データセット「B2B Impression」には 7650 の行がありますが、[!UICONTROL Adobe Experience Platform] のデータセットの行数は 3830 です。不一致が発生する理由はいくつかあり、次の手順を実行して診断できます。

1. このディメンションを **[!UICONTROL プラットフォームデータセット ID]** で分類すると、サイズは同じでも、**[!UICONTROL プラットフォームデータセット ID]** が異なる 2 つのデータセットがあることがわかります。各データセットには 3825 件のレコードがあります。つまり、[!UICONTROL Customer Journey Analytics] では、ユーザー ID またはタイムスタンプが欠落していることにより、5 件のレコードが無視されています。

   ![分類](assets/data-size2.png)

1. また、[!UICONTROL Adobe Experience Platform] にチェックインすると、ID「5f21c12b732044194bffc1d0」のデータセットがありません。つまり、他のユーザーが最初の接続の作成時に [!UICONTROL Adobe Experience Platform] からこのデータセットを削除しています。その後、そのデータセットは Customer Journey Analytics に再び追加されましたが、[!UICONTROL Adobe Experience Platform] によって、異なる[!UICONTROL プラットフォームデータセット ID] が生成されました。

[!UICONTROL Customer Journey Analytics] と [!UICONTROL Adobe Experience Platform] におけるデータセットと接続の削除の影響については、[こちら](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components)を参照してください。
