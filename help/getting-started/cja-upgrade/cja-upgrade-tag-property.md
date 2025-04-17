---
title: タグプロパティを作成し、Web SDK 拡張機能を追加
description: タグプロパティを作成し、Web SDK 拡張機能を追加する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 100%

---

# プロパティのタグの作成 {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Adobe Experience Platform データ収集にタグプロパティを作成"
>abstract="タグの使用は、データ収集の一般的な標準です。Adobe Experience Platform インターフェイスでタグを作成し、いつでもデータ収集変数を更新できるようにします。<br><br>タグプロパティの作成は数回のクリックで完了し、わずか数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Experience Platform 内のタグ機能を使用して、サイトにデータを収集するためのコードを実装できます。このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。タグは、Adobe Experience Platform Web SDK 拡張機能を使用して、Adobe Experience Platform とのシームレスな統合を提供します。

次の情報では、プロパティのタグを作成する方法について説明します。補足情報について詳しくは、Experience Platform ドキュメントの [Web SDK タグ拡張機能の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)を参照してください。Web SDK には [!UICONTROL Adobe Experience Cloud ID サービス]がネイティブに含まれているので、タグに ID サービス拡張機能を追加する必要はありません。

プロパティは基本的に、サイトにタグをデプロイする際に拡張機能、ルール、データ要素およびライブラリを入力するコンテナです。多くの人物は、同じタグのセットをデプロイする各 web サイト（または密接に関連するサイトのグループ）に対してプロパティを作成します。プロパティについて詳しくは、Experience Platform データ収集ドキュメントの[プロパティ](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/admin/companies-and-properties)を参照してください。

プロパティのタグを作成するには：

1. Adobe ID 資格情報を使用して experiencecloud.adobe.com にログインします。

1. Adobe Experience Platform で、**[!UICONTROL データ収集]**／**[!UICONTROL タグ]**&#x200B;に移動します。

1. 「**[!UICONTROL 新しいプロパティ]**」を選択します。

   タグに名前を付け、「**[!UICONTROL Web]**」を選択し、ドメイン名を入力します。「**[!UICONTROL 保存]**」を選択して続行します。

   ![ プロパティの作成](assets/create-property.png)

{{upgrade-final-step}}
