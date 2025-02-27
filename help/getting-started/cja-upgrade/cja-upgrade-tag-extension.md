---
title: タグプロパティを作成して web SDK拡張機能を追加
description: タグプロパティを作成し、web SDK拡張機能を追加する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 27%

---

# タグへの Web SDK 拡張機能の追加 {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="タグプロパティに Platform Web SDK拡張機能を追加します"
>abstract="タグプロパティにAdobe Experience Platform Web SDK拡張機能を追加します。 タグプロパティへの Web SDK拡張機能の追加は効率化されており、完了までわずか数分で済みます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Experience Platformのタグ機能を使用して、データを収集するコードをサイトに実装できます。 このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。タグは、Adobe Experience Platform Web SDK 拡張機能を使用して、Adobe Experience Platform とのシームレスな統合を提供します。

ここでは、タグに web SDK拡張機能を追加する方法について説明します。 詳しくは、Experience Platform ドキュメントの [Web SDK タグ拡張機能の設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) を参照してください。 Web SDKには、[!UICONTROL Adobe Experience Cloud ID サービス ] がネイティブに含まれているので、タグに ID サービス拡張機能を追加する必要はありません。

[ タグを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) した後、Adobe Experience Platform Web SDK拡張機能を使用して設定する必要があります。 これにより、（データストリームを通じて）Adobe Experience Platformにデータを送信できるようになります。

タグに web SDK拡張機能を追加するには、次の手順を実行します。

1. Adobe IDの資格情報を使用してexperience.adobe.comにログインします。

1. Adobe Experience Platformで、**[!UICONTROL Data Collection]**/**[!UICONTROL Tags]** に移動します。

1. [!UICONTROL タグのプロパティ]をクリックして新しく作成したタグを開きます。

1. 左パネルで「**[!UICONTROL 拡張機能]**」を選択します。

1. 上部のバーで「**[!UICONTROL カタログ]**」をクリックします。

1. **[!UICONTROL Adobe Experience Platform Web SDK拡張機能]** を検索またはスクロールし、「**[!UICONTROL インストール]**」をクリックしてインストールします。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. サンドボックスと、以前に作成した[!UICONTROL 実稼動環境]、（オプション）[!UICONTROL ステージング環境]および[!UICONTROL 開発環境]用のデータストリームを選択します。

   ![AEP Web SDK 拡張機能の設定](assets/aepwebsk-extension-datastreams.png)

1. 「**[!UICONTROL 保存]**」を選択します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
