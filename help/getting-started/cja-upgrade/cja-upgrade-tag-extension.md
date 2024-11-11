---
title: タグプロパティを作成して Web SDK 拡張機能を追加する
description: タグプロパティを作成し Web SDK 拡張機能を追加する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 23%

---

# タグに Web SDK 拡張機能を追加します

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Adobe Experience Platformのタグ機能を使用して、データを収集するコードをサイトに実装できます。 このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。タグは、Adobe Experience Platform Web SDK 拡張機能を使用して、Adobe Experience Platform とのシームレスな統合を提供します。

次の情報では、タグに Web SDK 拡張機能を追加する方法について説明します。 詳しくは、Experience Platformドキュメントの [Web SDK タグ拡張機能の設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) を参照してください。 Web SDK には、[!UICONTROL Adobe Experience Cloud ID サービス ] がネイティブに含まれているので、タグに ID サービス拡張機能を追加する必要はありません。

[ タグを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) した後、Adobe Experience Platform Web SDK 拡張機能を使用して設定する必要があります。 これにより、（データストリームを通じて）Adobe Experience Platformにデータを送信できるようになります。

タグに Web SDK 拡張機能を追加するには：

1. Adobe IDの資格情報を使用してexperience.adobe.comにログインします。

1. Adobe Experience Platformで、**[!UICONTROL Data Collection]**/**[!UICONTROL Tags]** に移動します。

1. [!UICONTROL タグのプロパティ]をクリックして新しく作成したタグを開きます。

1. 左パネルで「**[!UICONTROL 拡張機能]**」を選択します。

1. 上部のバーで「**[!UICONTROL カタログ]**」をクリックします。

1. **[!UICONTROL Adobe Experience Platform Web SDK 拡張機能]** を検索またはスクロールし、「**[!UICONTROL インストール]**」をクリックしてインストールします。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. サンドボックスと、以前に作成した[!UICONTROL 実稼動環境]、（オプション）[!UICONTROL ステージング環境]および[!UICONTROL 開発環境]用のデータストリームを選択します。

   ![AEP Web SDK 拡張機能の設定](assets/aepwebsk-extension-datastreams.png)

1. 「**[!UICONTROL 保存]**」を選択します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。