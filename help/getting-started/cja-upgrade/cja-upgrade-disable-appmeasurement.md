---
title: 接続への Analytics ソースコネクタデータセットの追加
description: 接続に Analytics ソースコネクタデータセットを追加する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 9cfe89aef069d777424eb8a5d9ef8ae03a9d0486
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 6%

---

# Adobe Analyticsを無効にする {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="AppMeasurement データ収集の無効化"
>abstract="Web SDKのデータがすべて機能するので、開発者チームと協力して、web サイトまたはプロパティからAppMeasurement.js を削除します。<br><br>Web サイトからAppMeasurementを削除する作業は数分で完了します。ただし、エンジニアリングチームは時間がかかります。 ただし、Analytics ユーザーがAdobe AnalyticsではなくCustomer Journey Analyticsを使用していることを確認してください。まだ行っていない場合は、全員を移行するためのこの通知プロセスに大幅に時間がかかる可能性があります。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Adobe Analyticsを無効にする前に、[Customer Journey Analyticsへのアップグレード後にAdobe Analyticsを無効にするタイミングを評価する ](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) の内容を確認してください。

* **タグ：** Adobe Analytics拡張機能を無効にする

* **AppMeasurment:** AppMeasurement.js ライブラリ s=newobject を置き換えます
