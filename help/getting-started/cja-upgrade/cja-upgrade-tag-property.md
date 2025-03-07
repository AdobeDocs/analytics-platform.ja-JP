---
title: タグプロパティを作成して web SDK拡張機能を追加
description: タグプロパティを作成し、web SDK拡張機能を追加する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 45%

---

# プロパティのタグの作成 {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Adobe Experience Platform データ収集でのタグプロパティの作成"
>abstract="タグの使用は、データ収集の一般的な標準です。Adobe Experience Platform インターフェイスでタグを作成し、いつでもデータ収集変数を更新できるようにします。<br><br>タグプロパティの作成は数回のクリックで完了し、わずか数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Experience Platformのタグ機能を使用して、データを収集するコードをサイトに実装できます。 このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。タグは、Adobe Experience Platform Web SDK 拡張機能を使用して、Adobe Experience Platform とのシームレスな統合を提供します。

次の情報では、プロパティのタグを作成する方法について説明します。 詳しくは、Experience Platform ドキュメントの [Web SDK タグ拡張機能の設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) を参照してください。 Web SDKには、[!UICONTROL Adobe Experience Cloud ID サービス ] がネイティブに含まれているので、タグに ID サービス拡張機能を追加する必要はありません。

プロパティは基本的に、サイトにタグをデプロイする際に拡張機能、ルール、データ要素およびライブラリを入力するコンテナです。多くのユーザーは、同じタグセットをデプロイする web サイト（または密接に関連するサイトのグループ）ごとにプロパティを作成しています。 プロパティについて詳しくは、Experience Platform データ収集ドキュメントの [ プロパティ ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties) を参照してください。

プロパティのタグを作成するには：

1. Adobe IDの資格情報を使用してexperience.adobe.comにログインします。

1. Adobe Experience Platformで、**[!UICONTROL Data Collection]**/**[!UICONTROL Tags]** に移動します。

1. 「**[!UICONTROL 新しいプロパティ]**」を選択します。

   タグに名前を付け、「**[!UICONTROL Web]**」を選択し、ドメイン名を入力します。「**[!UICONTROL 保存]**」を選択して続行します。

   ![ プロパティの作成](assets/create-property.png)

{{upgrade-final-step}}
