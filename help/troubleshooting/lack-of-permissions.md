---
title: 権限の不足
description: 権限の不足によって生じる問題のトラブルシューティング方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '189'
ht-degree: 100%

---

# 権限の不足

特定の Adobe Experience Platform 権限を設定していない場合、Customer Journey Analytics は正しく機能しません。

例えば、[接続](../connections/overview.md)および[データビュー](../data-views/data-views.md)を作成した後、[コンポーネント](/help/data-views/create-dataview.md#components)の節に次のエラーメッセージが表示される場合があります。


>[!BEGINSHADEBOX]

*[!UICONTROL DULE ポリシーの取得中にエラーが発生しました。アカウントの権限、ポリシーまたはラベルを確認してください。メッセージ : 禁止されています。]*

>[!ENDSHADEBOX]


1. 適切なアクセス制御が行われていることを確認します。

   * Experience Platform 製品を持つ組織に対して、システム管理者権限または製品管理者権限を持っている必要があります。詳しくは、[アクセス制御の概要](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions?lang=ja)を参照してください。

   * AEP-Default-All-Users 製品プロファイルのユーザーである必要があります。このプロファイルに自分自身を追加する権限がない場合は、管理者にお問い合わせください。詳しくは、[アクセス制御の階層とワークフロー](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja#access-control-hierarchy-and-workflow)を参照してください。


1. Adobe Experience Platform UI に移動します。

1. 左側のパネルから「**[!UICONTROL 権限]**」を選択します。

1. 「**[!UICONTROL 役割]**」を選択します。

1. 関連する役割に移動します。

1. 役割を編集するには、![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)「**[!UICONTROL 編集]**」を選択します。

1. **[!UICONTROL データ使用ポリシーを管理]**&#x200B;と&#x200B;**[!UICONTROL データ使用ポリシーを表示]**&#x200B;が&#x200B;**[!UICONTROL データガバナンス]**&#x200B;コンテナに追加されていることを確認します。

1. 「**[!UICONTROL 保存]**」を選択して変更を保存します。
