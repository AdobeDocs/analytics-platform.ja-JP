---
title: Customer Journey Analytics へのアップグレード時のデータセット取り込みの監視
description: Customer Journey Analytics へのアップグレード時にデータセット取り込みを監視する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
autotag-review: '2026-05-19T08:10:42.746Z'
TQID: 'https://experienceleague.adobe.com/tAPQiUUPilyH50PlqwefoZjw14QDN9ER1D6EKsMAR9w'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 100%

---

# Customer Journey Analytics へのアップグレード時のデータセット取り込みの監視 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="データセット内のデータの検証"
>abstract="実装の設定が完了したら、データセットアクティビティマネージャーを使用して、取り込まれたバッチと失敗したバッチを確認できます。 主に取り込まれたバッチが表示されている場合、この手順は完了です。 主に失敗したバッチが表示されるか、バッチがまったく表示されない場合は、実装を確認して、アドビにデータが正しく送信されていることを確認してください。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Web SDK 実装または API 実装を設定したら、個々のバッチのステータスを確認して、データがデータセットに取り込まれていることを確認する必要があります。

1. Experience Platform UI で、左側のナビゲーションにある「**[!UICONTROL 監視]**」を選択します。

   監視ダッシュボードが表示されます。 このダッシュボードでは、バッチまたはストリーミング取り込みからの受信データのステータスを表示できます。

   <!-- insert screenshot -->

1. バッチのリストを表示するには、「**[!UICONTROL エンドツーエンドのバッチ]**」を選択します。

   バッチが表示されない場合は、実装を確認して、アドビにデータが正しく送信されていることを確認します。

   <!-- insert screenshot -->

1. 特定のデータセットのバッチ ID を選択し、「**[!UICONTROL ステータス]**」フィールドに&#x200B;**[!UICONTROL 成功]**&#x200B;が表示されていることを検証します。

   「**[!UICONTROL ステータス]**」フィールドに&#x200B;**[!UICONTROL 失敗]**&#x200B;と表示される場合は、実装を確認して、アドビにデータが正しく送信されていることを確認します。

   この手順を繰り返して、各バッチのステータスを確認します。

{{upgrade-final-step}}

