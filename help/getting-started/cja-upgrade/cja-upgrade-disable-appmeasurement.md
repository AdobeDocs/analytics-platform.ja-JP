---
title: 接続への Analytics ソースコネクタデータセットの追加
description: 接続に Analytics ソースコネクタデータセットを追加する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 64%

---

# Adobe Analyticsを無効にする {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="AppMeasurement データ収集の無効化"
>abstract="Web SDK データが完全に機能したら、開発者チームと協力して、web サイトまたはプロパティから AppMeasurement.js を削除します。<br><br>AppMeasurement を web サイトから削除する作業は数分しかかかりませんが、完了するにはエンジニアリングチームの時間が必要です。ただし、Analytics ユーザーが Adobe Analytics ではなく Customer Journey Analytics を使用していることを確認してください。まだこの操作を行っていない場合、全員を移行するこの通知プロセスには大幅に時間がかかる可能性があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Analyticsを無効にする前に、[Customer Journey Analyticsへのアップグレード後にAdobe Analyticsを無効にするタイミングを評価する ](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) の内容を確認してください。

* **タグ：** Adobe Analytics拡張機能を無効にする

* **AppMeasurment:** AppMeasurement.js ライブラリ s=newobject を置き換えます
