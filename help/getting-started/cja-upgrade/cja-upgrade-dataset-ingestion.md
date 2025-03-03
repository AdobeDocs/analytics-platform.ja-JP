---
title: Customer Journey Analytics にアップグレードする際のデータセットの取り込みの監視
description: Customer Journey Analyticsへのアップグレード時にデータセットの取り込みを監視する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 40%

---

# Customer Journey Analytics にアップグレードする際のデータセットの取り込みの監視 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="データセット内のデータの検証"
>abstract="Web SDK 実装の設定が完了したら、データセットアクティビティマネージャーを使用して、取り込まれたバッチと失敗したバッチを確認できます。主に取り込まれたバッチが表示されている場合、この手順は完了です。主に失敗したバッチが表示されるか、バッチがまったく表示されない場合は、Web SDK の実装を確認して、アドビにデータが正しく送信されていることを確認してください。<br><br>すべてが正しく完璧に行われた場合、この手順は 1 日未満に完了できます。データ収集の問題が複数ある場合、トラブルシューティングにかなり長い時間がかかる可能性があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Web SDKの実装を設定した後、個々のバッチのステータスを確認して、データがデータセットに取り込まれていることを確認する必要があります。

1. Experience Platform UI の左側のナビゲーションで「**[!UICONTROL モニタリング]**」を選択します。

   監視ダッシュボードが表示されます。 このダッシュボードでは、バッチまたはストリーミング取り込みからの受信データのステータスを表示できます。

   <!-- insert screenshot -->

1. **[!UICONTROL エンドツーエンドのバッチ]** を選択して、バッチのリストを表示します。

   バッチが表示されない場合は、web SDKの実装を調べ、Adobeに正しくデータが送信されていることを確認してください。

   <!-- insert screenshot -->

1. 特定のデータセットのバッチ ID を選択し、**[!UICONTROL 成功]** が **[!UICONTROL ステータス]** フィールドに表示されることを検証します。

   **[!UICONTROL 失敗]** が **[!UICONTROL ステータス]** フィールドに表示される場合は、Web SDKの実装を確認し、Adobeに正しくデータが送信されていることを確認します。

   この手順を繰り返して、各バッチのステータスを確認します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。

