---
title: タグプロパティを作成し、Web SDK 拡張機能を追加
description: タグプロパティを作成し、Web SDK 拡張機能を追加する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
autotag-review: '2026-05-19T08:18:58.656Z'
TQID: 'https://experienceleague.adobe.com/8Wld534ijt7cmJnlbq4cB7tURTb8hch99Z6FIrhzAcQ'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 100%

---

# タグへの Web SDK 拡張機能の追加 {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="タグプロパティに Platform Web SDK 拡張機能を追加"
>abstract="タグプロパティに Adobe Experience Platform Web SDK 拡張機能を追加します。 タグプロパティへの Web SDK拡張機能の追加は効率化されており、完了するまでに数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Experience Platform 内のタグ機能を使用して、サイトにデータを収集するためのコードを実装できます。 このタグ管理ソリューションを使用すると、他のタグ要件と共にコードをデプロイできます。 タグは、Adobe Experience Platform Web SDK 拡張機能を使用して、Adobe Experience Platform とのシームレスな統合を提供します。

次の情報では、タグに Web SDK 拡張機能を追加する方法について説明します。 補足情報について詳しくは、Experience Platform ドキュメントの [Web SDK タグ拡張機能の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)を参照してください。 Web SDK には [!UICONTROL Adobe Experience Cloud ID サービス]がネイティブに含まれているので、タグに ID サービス拡張機能を追加する必要はありません。

[タグを作成](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)した後、Adobe Experience Platform Web SDK 拡張機能を使用して設定する必要があります。 これにより、Adobe Experience Platform に（データストリームを通じて）データを送信できます。

タグに Web SDK 拡張機能を追加するには：

1. Adobe ID 資格情報を使用して experiencecloud.adobe.com にログインします。

1. Adobe Experience Platform で、**[!UICONTROL データ収集]**／**[!UICONTROL タグ]**&#x200B;に移動します。

1. [!UICONTROL タグのプロパティ]をクリックして新しく作成したタグを開きます。

1. 左パネルで「**[!UICONTROL 拡張機能]**」を選択します。

1. 上部のバーで「**[!UICONTROL カタログ]**」をクリックします。

1. **[!UICONTROL Adobe Experience Platform Web SDK 拡張機能]**&#x200B;を検索またはスクロールし、「**[!UICONTROL インストール]**」を選択してインストールします。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. サンドボックスと、以前に作成した[!UICONTROL 本番環境]、（オプション）[!UICONTROL ステージング環境]および[!UICONTROL 開発環境]用のデータストリームを選択します。

   ![AEP Web SDK 拡張機能の設定](assets/aepwebsk-extension-datastreams.png)

1. 「**[!UICONTROL 保存]**」を選択します。

{{upgrade-final-step}}
