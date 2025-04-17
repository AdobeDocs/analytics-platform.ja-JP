---
title: Customer Journey Analytics へのアップグレード時のデータセット取り込みの監視
description: Customer Journey Analytics へのアップグレード時にデータセット取り込みを監視する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 69%

---

# Customer Journey Analytics へのアップグレード時のデータセット取り込みの監視 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="データセット内のデータの検証"
>abstract="実装の設定が完了したら、データセットアクティビティマネージャーを使用して、取り込まれたバッチと失敗したバッチを確認できます。主に取り込まれたバッチが表示されている場合、この手順は完了です。主に失敗したバッチが表示されるか、バッチがまったく表示されない場合は、実装を確認して、アドビにデータが正しく送信されていることを確認してください。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Web SDKまたは API の実装を設定した後、データがデータセットに取り込まれていることを確認するには、個々のバッチのステータスを確認する必要があります。

1. Experience Platform UI で、左側のナビゲーションにある「**[!UICONTROL 監視]**」を選択します。

   監視ダッシュボードが表示されます。 このダッシュボードでは、バッチまたはストリーミングの取り込みからの受信データのステータスを表示できます。

   <!-- insert screenshot -->

1. バッチのリストを表示するには、「**[!UICONTROL エンドツーエンドのバッチ]**」を選択します。

   バッチが表示されない場合は、実装でAdobeにデータが正しく送信されていることを確認してください。

   <!-- insert screenshot -->

1. 特定のデータセットのバッチ ID を選択し、「**[!UICONTROL ステータス]**」フィールドに&#x200B;**[!UICONTROL 成功]**&#x200B;が表示されていることを検証します。

   **[!UICONTROL 失敗]** が **[!UICONTROL ステータス]** フィールドに表示される場合は、実装を確認し、Adobeに正しくデータが送信されていることを確認します。

   この手順を繰り返して、各バッチのステータスを確認します。

{{upgrade-final-step}}

