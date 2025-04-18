---
title: アセットを転送
description: ユーザー間でコンポーネントを転送する方法を説明します
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---

# アセットを転送

アセット転送ツールを使用すると、アセットの所有権を他のユーザーに転送できます。 Assetsには、プロジェクト、セグメント、日付範囲、計算指標、注釈、アラート、スケジュールされたプロジェクトなどのコンポーネントを含めることができます。

Assetsは多くの場合、個々の所有者に結び付けられており、場合によっては（セグメントや計算指標など）、管理者でさえ編集または共有できない場合があります。 ユーザーが組織を離れたり、役割が変更されたりすると、継続性と適切なアクセスを確保するために、これらのアセットの所有権を他のユーザーに転送する必要が生じる場合があります。

## 権限

アセット転送には、Customer Journey Analyticsの製品管理者権限が必要です。

## アセットを転送

1. CJAで、**[!UICONTROL ツール]**/**[!UICONTROL アセット転送]** に移動します。

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

   >[!NOTE]
   >
   >管理者から管理者以外のユーザーにアセットを転送しても、受信者は管理者にアップグレードされません。


   >[!NOTE]
   >
   >    他のコンポーネントを参照するアセットを転送する場合（例えば、他のセグメントを参照するプロジェクトや計算指標など）、プロジェクトの現在の所有者が所有していないコンポーネントは、受信者とのみ共有されます。 その他すべてのコンポーネントの所有権は、受信者に転送されます。

1. フォルダー内の _すべて_ のアセットを選択するには、テーブル上部の **[!UICONTROL 名前]** の横にあるチェックボックスをオンにします。

   ![ 転送するアセットの選択 ](/help/tools/asset-transfer/assets/select-assets.png)

1. すべての選択を行ったら、右上の「**[!UICONTROL 転送]**」をクリックします。

1. 確認メッセージが表示されたら、「**[!UICONTROL 確認]**」をクリックします。

   >[!IMPORTANT]
   >
   >プロセスの中絶を避けるために、転送中に画面を閉じないでください。 これにより、スムーズな転送エクスペリエンスが確保されます。

## 結果の転送

転送には、次の 3 つの結果が考えられます。

- **転送成功**:「Assetsは正常に転送されました。」

- **部分成功**:「一部のアセットは正常に転送されました。」

- **転送エラー**:「アセットを転送できませんでした。 もう一度やり直してください」

## Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード中にアセットを転送

アセット転送の主なユースケースの 1 つは、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード中です。

Adobe Analyticsの [ コンポーネント移行 ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) 機能を使用すると、管理者が所有するプロジェクトを他の管理者に移行できます。 その後、これらのプロジェクトを構成するすべてのコンポーネントがCustomer Journey Analyticsで再作成され、受信者管理者は、コンポーネントの作成者に関係なく、これらすべてのコンポーネントを所有します。

その後このアセット転送ツールを使用すると、管理者は、管理者であるかどうかに関係なく、正当な所有者にコンポーネントを再割り当てできます。

>[!IMPORTANT]
>
>このツールを使用してコンポーネントを転送することもできますが、管理者は、受信者がこれらのコンポーネントの表示や使用に必要なデータビューにアクセスできることを確認する必要があります。 [Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) で権限を表示して割り当てることができます。

## CSV に書き出し

**[!UICONTROL CSV に書き出し]** オプションを使用すると、管理者は、.csv ファイルに表示されたユーザーのリストをダウンロードできます。 転送したアセットのリストを.csv ファイルに書き出すことはできません。

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->
