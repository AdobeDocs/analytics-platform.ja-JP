---
title: 権限の欠如
description: 権限の欠如に起因する問題のトラブルシューティング方法を説明します。
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# 権限の欠如

Customer Journey Analyticsは、特定のAdobe Experience Platform権限が設定されていない場合、正しく機能しません。

例えば、 [接続](../connections/overview.md) および [データビュー](../data-views/data-views.md)を含めている場合、 [コンポーネント](/help/data-views/create-dataview.md#components) セクション：


>[!BEGINSHADEBOX]

*[!UICONTROL DULE ポリシーの取得中にエラーが発生しました。アカウントの権限、ポリシー、またはラベルを確認してください。 メッセージ：禁止されています。]*

>[!ENDSHADEBOX]


1. 適切なアクセス制御を持っていることを確認します。

   * システム製品を持つ組織のシステム管理者権限またはExperience Platform管理者権限が必要です。 詳しくは、 [アクセス制御の概要](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) を参照してください。

   * AEP-Default-All-Users 製品プロファイルのユーザーである。 このプロファイルに自分を追加する権限がない場合は、管理者に問い合わせてください。 詳しくは、 [アクセス制御階層とワークフロー](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) を参照してください。


1. Experience Platform UI のAdobeに移動します。

1. 選択 **[!UICONTROL 権限]** をクリックします。

1. 選択 **[!UICONTROL 役割]**.

1. 関連する役割に移動します。

1. 選択 ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** をクリックして、役割を編集します。

1. 確認 **[!UICONTROL データ使用ポリシーの管理]** および **[!UICONTROL データ使用ポリシーの表示]** が **[!UICONTROL データガバナンス]** コンテナ。

1. 選択 **[!UICONTROL 保存]** をクリックして変更を保存します。
