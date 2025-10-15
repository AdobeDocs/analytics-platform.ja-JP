---
title: Customer Journey Analyticsの使用状況の管理
description: Customer Journey Analyticsの使用状況を管理する方法を説明します。
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 37%

---

# Customer Journey Analyticsの使用状況の管理

>[!TIP]
>
>[**[!UICONTROL  使用状況 ]**インターフェイス ](/help/connections/manage-connections.md#usage) を使用して、Customer Journey Analyticsのすべての接続における取り込まれた行とレポート可能な行の使用状況を** 表示 **します。



Customer Journey Analyticsの使用状況は [**[!UICONTROL  接続 ]**インターフェイス ](/help/connections/create-connection.md) で管理できます。 このインターフェイスでは、Customer Journey Analytics データ保持を接続レベルでの月単位（1 か月、3 か月、6 か月など）のローリングウィンドウとして定義できます。

主な利点は、該当する有用なデータのみを保存またはレポートして、有用でなくなった古いデータを削除できるという点です。 契約上の上限を超えないようにし、超過コストのリスクを軽減します。

デフォルト（オフ）のままにすると、Adobe Experience Platform のデータ保持設定によって保持期間が置き換えられます。Experience Platformに 25 か月分のデータがある場合、Customer Journey Analyticsはバックフィルを通じて 25 か月分のデータを取得します。 Platform でこのうち 10 か月を削除すると、Customer Journey Analytics は残りの 15 か月を保持します。

データ保持はタイムスタンプに基づき、イベントデータセットと概要データセットにのみ適用されます。 適用可能なタイムスタンプがないので、プロファイルまたはルックアップデータセットには、周期的なデータ時間枠設定は存在しません。 接続にプロファイルデータセットまたはルックアップデータセットが含まれている場合、それらはイベントデータセットと結合されているので、データはイベントデータセットタイムスタンプのデータ保持設定に基づいてCustomer Journey Analyticsに保持されます。


>[!MORELIKETHIS]
>
>[Customer Journey Analyticsの使用状況の表示 ](/help/connections/manage-connections.md#usage)

