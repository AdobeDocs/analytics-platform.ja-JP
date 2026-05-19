---
title: Customer Journey Analyticsの使用状況の管理
description: Customer Journey Analyticsの使用状況を管理する方法について説明します。
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
autotag-review: '2026-05-19T09:30:13.855Z'
TQID: 'https://experienceleague.adobe.com/SWjkycY-YwNFMXRXwBypDtTL2ffFn40-Fp88vSxv-74'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 37%

---

# Customer Journey Analyticsの使用状況の管理

>[!TIP]
>
>Customer Journey Analyticsのすべてのコネクションで取り込まれた行とレポート可能な行の使用状況を[**[!UICONTROL 使用状況&#x200B;]**&#x200B;インターフェイス &#x200B;](/help/connections/manage-connections.md#usage)から&#x200B;**&#x200B;表示&#x200B;**&#x200B;します。



Customer Journey Analyticsの使用状況は、[**[!UICONTROL Connections &#x200B;]**&#x200B;インターフェイス &#x200B;](/help/connections/create-connection.md)で管理できます。 このインターフェイスでは、Customer Journey Analytics データ保持を、接続レベルで月単位（1か月、3か月、6か月など）のローリングウィンドウとして定義できます。

主な利点は、該当する有用なデータのみを保存またはレポートして、有用でなくなった古いデータを削除できるという点です。 契約上の上限を超えないようにし、超過コストのリスクを軽減します。

デフォルト（オフ）のままにすると、Adobe Experience Platform のデータ保持設定によって保持期間が置き換えられます。 Experience Platformに25 ヶ月分のデータがある場合、Customer Journey Analyticsはバックフィルを通じて25 ヶ月分のデータを取得します。 Platform でこのうち 10 か月を削除すると、Customer Journey Analytics は残りの 15 か月を保持します。

データ保持はタイムスタンプに基づいており、イベントデータセットとサマリーデータデータセットにのみ適用されます。 適用可能なタイムスタンプがないので、プロファイルまたはルックアップデータセットには、周期的なデータ時間枠設定は存在しません。 接続にプロファイルまたはルックアップデータセットが含まれている場合、イベントデータセットと結合されるため、データはイベントデータセットのタイムスタンプのデータ保持設定に基づいてCustomer Journey Analyticsに保持されます。


>[!MORELIKETHIS]
>
>[Customer Journey Analyticsの使用状況を表示](/help/connections/manage-connections.md#usage)

