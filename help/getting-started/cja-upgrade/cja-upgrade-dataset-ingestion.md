---
title: Customer Journey Analyticsへのアップグレード時のデータセット取り込みの監視
description: Customer Journey Analyticsへのアップグレード時にデータセットの取り込みを監視する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Customer Journey Analyticsへのアップグレード時のデータセット取り込みの監視 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="データセット内のデータの検証"
>abstract="Web SDKの実装が完了したので、データセットアクティビティマネージャーを使用して、取り込まれたバッチと失敗したバッチを確認できます。 主に取り込まれたバッチが表示された場合、この手順は完了です。 主に失敗したバッチが表示される場合やバッチが表示されない場合は、web SDKの実装を調べて、Adobeに正しくデータが送信されていることを確認してください。<br><br> すべてが正しく完璧に行われた場合、この手順は 1 日未満で完了できます。 データ収集に関する複数の問題がある場合、トラブルシューティングに時間がかかる可能性があります。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Web SDKの実装を設定した後、個々のバッチのステータスを確認して、データがデータセットに取り込まれていることを確認する必要があります。

1. Experience PlatformUI で、左側のナビゲーションにある「**[!UICONTROL モニタリング]**」を選択します。

   監視ダッシュボードが表示されます。 このダッシュボードでは、バッチまたはストリーミング取り込みからの受信データのステータスを表示できます。

   <!-- insert screenshot -->

1. **[!UICONTROL エンドツーエンドのバッチ]** を選択して、バッチのリストを表示します。

   バッチが表示されない場合は、web SDKの実装を調べて、Adobeに正しくデータが送信されていることを確認してください。

   <!-- insert screenshot -->

1. 特定のデータセットのバッチ ID を選択し、**[!UICONTROL 成功]** が **[!UICONTROL ステータス]** フィールドに表示されることを検証します。

   **[!UICONTROL 失敗]** が **[!UICONTROL ステータス]** フィールドに表示される場合は、Web SDKの実装を確認し、Adobeに正しくデータが送信されていることを確認します。

   この手順を繰り返して、各バッチのステータスを確認します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。

