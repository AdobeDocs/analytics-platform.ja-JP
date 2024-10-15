---
title: アセットを転送
description: ユーザー間でコンポーネントを転送する方法を説明します
role: Admin
solution: Customer Journey Analytics
source-git-commit: faa9545fa3928a19aeaaf7285a9643e7dc253cea
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---


# アセットを転送

アセット転送ツールを使用すると、アセットの所有権を他のユーザーに転送できます。 Assetsには、プロジェクト、フィルター、日付範囲、計算指標、注釈、アラート、スケジュールされたプロジェクトなどのコンポーネントを含めることができます。

Assetsは多くの場合、個々の所有者に結び付けられ、場合によっては（フィルターや計算指標など）、管理者でさえ編集または共有できない場合があります。 ユーザーが組織を離れたり、役割が変更されたりすると、継続性と適切なアクセスを確保するために、これらのアセットの所有権を他のユーザーに転送する必要が生じる場合があります。

## 権限

アセット転送のCustomer Journey Analyticsには、製品管理者権限が必要です。

## アセットを転送

1. CJA で、**[!UICONTROL ツール]**/**[!UICONTROL アセット転送]** に移動します。

   ![ アセット転送メニュー項目 ](/help/tools/asset-transfer/assets/asset-transfer.png)

1. **[!UICONTROL ユーザー]** ダイアログで、アセットを転送するユーザーを検索して選択します。

   >[!IMPORTANT]
   >
   >1 対 1 の転送は、あるユーザーから別のユーザーに対してのみ実行できます。 1 対多または多対 1 の転送はサポートされていません。


1. ユーザーを選択すると、画面の下部に「アセットを転送」オプションが表示されます。

   ![ メニューオプション ](/help/tools/asset-transfer/assets/after-selection.png)

1. **[!UICONTROL アセットを転送]** をクリックします。

1. **[!UICONTROL アセットを転送]** 画面で、まずアセットの転送先となる受信者を選択します。

1. 左側のナビゲーションの各コンポーネントフォルダーで、転送する個々のコンポーネントまたはフォルダー内のすべてのアセットを選択します。

   管理者から管理者以外のユーザーにアセットを転送しても、受信者は管理者にアップグレードされません。

1. フォルダー内の _すべて_ のアセットを選択するには、テーブル上部の **[!UICONTROL 名前]** の横にあるチェックボックスをオンにします。

   ![ 転送するアセットの選択 ](/help/tools/asset-transfer/assets/select-assets.png)

1. すべての選択を行ったら、右上の「**[!UICONTROL 転送]**」をクリックします。

1. 確認メッセージが表示されたら、「**[!UICONTROL 確認]**」をクリックします。

   >[!IMPORTANT]
   >
   >プロセスの中絶を避けるために、転送中に画面を閉じないでください。 これにより、スムーズな転送エクスペリエンスが確保されます。

## Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード中にアセットを転送

アセット転送の主なユースケースの 1 つは、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード中です。

Adobe Analyticsの [ コンポーネント移行 ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) 機能を使用すると、管理者が所有するプロジェクトを他の管理者に移行できます。 その後、これらのプロジェクトを構成するすべてのコンポーネントがCustomer Journey Analytics内に再作成され、受信者管理者は、コンポーネントの作成者に関係なく、これらすべてのコンポーネントを所有します。

その後、このアセット転送ツールを使用して、管理者は、適切な所有者にコンポーネントを再割り当てできます。

## CSV に書き出し

あるユーザーから別のユーザーに転送されたアセットのリストを.csv ファイルに書き出すことができます。

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->