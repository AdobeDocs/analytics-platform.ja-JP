---
title: 権限の欠如
description: 権限の欠如に起因する問題のトラブルシューティング方法を説明します。
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 1905e37b76843a7622af4e874a2d74aceff55384
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---


# 権限の欠如

Customer Journey Analyticsは、特定のAdobe Experience Platform権限が設定されていない場合、正しく機能しません。

例えば、 [接続](../connections/overview.md) および [データビュー](../data-views/data-views.md)を含めている場合、 [コンポーネント](/help/data-views/create-dataview.md#components) セクション：


>[!BEGINSHADEBOX]

*[!UICONTROL 問題が発生したため、スキーマフィールドを読み込めませんでした。再度お試しください。]*

>[!ENDSHADEBOX]


このエラーを修正するには、システム製品を持つ組織のシステム管理者権限またはExperience Platform管理者権限が必要です。 詳しくは、 [アクセス制御の概要](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) を参照してください。

1. Adobe Experience Platform UI に移動します。

1. 選択 **[!UICONTROL 権限]** をクリックします。

1. 選択 **[!UICONTROL 役割]**.

1. 関連する役割に移動します。

1. 選択 ![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** をクリックして、役割を編集します。

1. 確認 **[!UICONTROL データ使用ポリシーの管理]** および **[!UICONTROL データ使用ポリシーの表示]** が **[!UICONTROL データガバナンス]** コンテナ。

1. 選択 **[!UICONTROL 保存]** をクリックして変更を保存します。


