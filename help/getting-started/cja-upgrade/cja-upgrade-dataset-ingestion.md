---
title: Customer Journey Analyticsへのアップグレード時のデータセット取り込みの監視
description: Customer Journey Analyticsへのアップグレード時にデータセットの取り込みを監視する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a5425eccff643cd45fd630172b0113e646b2a9cc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Customer Journey Analyticsへのアップグレード時のデータセット取り込みの監視

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Web SDK 実装を設定した後、個々のバッチのステータスを確認して、データがデータセットに取り込まれていることを確認する必要があります。

1. Experience PlatformUI で、左側のナビゲーションにある「**[!UICONTROL モニタリング]**」を選択します。

   監視ダッシュボードが表示されます。 このダッシュボードでは、バッチまたはストリーミング取り込みからの受信データのステータスを表示できます。

   <!-- insert screenshot -->

1. **[!UICONTROL エンドツーエンドのバッチ]** を選択して、バッチのリストを表示します。

   バッチが表示されない場合は、Web SDK 実装を調べて、Adobeに正しくデータが送信されていることを確認してください。

   <!-- insert screenshot -->

1. 特定のデータセットのバッチ ID を選択し、**[!UICONTROL 成功]** が **[!UICONTROL ステータス]** フィールドに表示されることを検証します。

   **[!UICONTROL 失敗]** が「**[!UICONTROL ステータス]**」フィールドに表示される場合は、Web SDK 実装を確認し、Adobeに正しくデータが送信されていることを確認します。

   この手順を繰り返して、各バッチのステータスを確認します。




