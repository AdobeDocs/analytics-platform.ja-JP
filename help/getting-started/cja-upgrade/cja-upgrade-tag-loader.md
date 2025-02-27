---
title: Web SDK 拡張機能用のローダータグの実装
description: Web SDK拡張機能のローダータグを実装する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 37%

---

# Web SDK 拡張機能用のローダータグの実装 {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="サイトにローダータグを実装"
>abstract="Web サイトの開発チームと協力して、サイトのすべてのページにローダータグをインストールします。<br><br> このタスクの完了時間は、コードのデプロイに協力するエンジニアリングチームの応答時間に大きく依存します。 高度にアダプティブなエンジニアリングチームを持つ組織では、このステップを数日で完了できる場合もあれば、タスクの膨大なバックログを持つエンジニアリングチームでは 1 か月以上かかる場合もあります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

追跡する web サイトにタグをインストールする必要があります。これは、web サイトのテンプレートのヘッダータグにコードを配置することを意味します。

次のプロセスでは、タグを参照するコードの取得方法を説明します。 補足情報については、Experience Platform ドキュメントの [ タグとイベント転送の実装ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides) を参照してください。

タグを参照するコードを取得するには：

1. Adobe IDの資格情報を使用してexperience.adobe.comにログインします。

1. Adobe Experience Platformで、**[!UICONTROL Data Collection]**/**[!UICONTROL Tags]** に移動します。

1. **[!UICONTROL タグプロパティ]** ページで、プロパティのリストから新しく作成したタグを選択して開きます。

1. 左パネルで「**[!UICONTROL 環境]**」を選択します。

1. 環境のリストから、正しいインストール（ボックス）ボタンを選択します。

   [!UICONTROL Web インストール手順]ダイアログで、次のように読み込むスクリプトコードの横にある「コピー」ボタンを選択します。

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![環境](assets/environment.png)

1. 「**[!UICONTROL 閉じる]**」を選択します。

   開発環境用のコードの代わりに、Adobe Experience Platform Web SDK をデプロイするプロセスの場所に基づいて、別の環境（ステージング、実稼動）を選択することもできます。

   詳しくは、[環境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ja)を参照してください。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
