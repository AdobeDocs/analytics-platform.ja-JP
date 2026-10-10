---
title: Adobe Analytics の無効化
description: Customer Journey Analyticsにアップグレードした後にAdobe Analytics データ収集を無効にする方法について説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
autotag-review: '2026-05-19T08:13:26.040Z'
TQID: 'https://experienceleague.adobe.com/EGQMwo2ENqJqJTTslytcooquVgsU-zGS7TU9fmJv8UQ'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 614a234f8db9783dacaf9d2f3c21a5afd5ea02ef
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 85%
---
# Adobe Analytics の無効化 {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="AppMeasurement データ収集の無効化"
>abstract="Web SDK のデータがすべて正常に機能するようになったら、開発者チームと協力して、web サイトまたはプロパティから AppMeasurement.js を削除します。<br><br>Web サイトから AppMeasurement を削除する作業は数分で完了します。ただし、エンジニアリングチームは時間がかかります。 ただし、Analytics ユーザーが Adobe Analytics ではなく Customer Journey Analytics を使用していることを確認してください。まだ行っていない場合は、全員を移行するためのこの通知プロセスに大幅に時間がかかる可能性があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Analytics を無効にする前に、[Customer Journey Analytics へのアップグレード後、Adobe Analytics を無効にするタイミングの評価](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)の情報を確認します。

* **タグ：** Adobe Analytics 拡張機能を無効にする

* **AppMeasurement:** AppMeasurement.js ライブラリ s=newobjectを置換します

>[!NOTE]
>
>この情報はまだ利用できません。 近い将来に利用可能になる予定です。
