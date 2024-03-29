---
title: Customer Journey Analytics の使用状況の表示と管理
description: 使用状況の推定方法を 2 つ、管理方法を 1 つ示します。
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 71%

---

# Customer Journey Analytics の使用状況の表示と管理

Customer Journey Analyticsの使用状況を表示するには、次の複数の方法を使用できます。

* 各接続のイベントデータ行を追加します。詳しくは、 [接続サイズの予測](#estimate-connection-size) 下 この方法では、特定のタイムスタンプについて、接続ごとのイベント行データを簡単に確認することができます。

* 使用状況を 3 つの方法で表示します。それぞれの方法について詳しくは、以下で説明します。
   * Analysis Workspace を使用して先月のイベントを報告します。
   * Report Builder を使用して先月のイベントを報告します。
   * Customer Journey AnalyticsAPI を使用して、自動レポートを作成します。

Customer Journey Analytics使用を管理するには：

* 周期的なデータウィンドウを定義します。

## 接続サイズの予測 {#estimate-size}

[!UICONTROL Customer Journey Analytics] にある現在のイベントデータの行数を把握する必要が出ることがあります。組織のイベントデータレコード（データ行）の使用状況を正確に把握するには、**組織が作成した各接続に対して**、次の手順を実行します。

>[!NOTE]
>
>これを、毎月第一金曜日（アドビがその日に最新の使用状況レポートを実行するため）に実行します。

1. [!UICONTROL Customer Journey Analytics] で、「**[!UICONTROL 接続]**」タブをクリックします。

   これで、現在のすべての接続のリストが表示されます。

1. 各接続名をクリックして、接続マネージャーに移動します。

1. 組織が作成したすべての接続について、**[!UICONTROL 使用可能なイベントデータのレコード]**&#x200B;を追加します（接続のサイズによっては、数字の表示に時間がかかる場合があります）。

   ![使用可能なイベントデータのレコード。](./assets/event-data.png)

   >[!CAUTION]
   >
   >   このカウントは、プロファイルや参照データではなく、イベントデータのみに適用されます。プロファイルと参照データがある場合、カウントは若干多くなります。ただし、現在のところ、ユーザーインターフェイスでプロファイルと参照のデータの使用状況をレポートする方法はありません。この機能は 2023 年に予定されています。

1. すべてのイベントデータ行の合計が表示されたら、自社とアドビで合意した Customer Journey Analytics 契約の「データ行」使用権を確認してください。

   これにより、受注で許可されているデータ行の最大数がわかります。手順 3 で取得したデータ行数がこの許可されている行数より多い場合は、データ使用量の超過が発生しています。

1. この状況を修正するには、次のようなオプションがあります。

   * [データ保持設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ja#set-rolling-window-for-connection-data-retention)を変更する。
   * [未使用の接続を削除する](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components)。
   * [Adobe Experience Platformでのデータセットの削除](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#implications-of-deleting-data-components).
   * 追加容量のライセンスを取得するには、Adobeアカウントチームにお問い合わせください。

## すべてのイベントデータを使用してワークスペースプロジェクトを作成する {#workspace-event-data}

この方法を使用すると、使用状況データと使用状況の履歴を、より深く分析できます。

1. ワークスペースでプロジェクトを作成する前に、フィルターを適応せずに各接続について[データ表示を作成](/help/data-views/create-dataview.md)します。

>[!WARNING]
>
>    使用量が事実上 2 倍になってしまうので、使用量を測定するだけのために、すべてのデータを含む新しい接続を作成しないでください。

1. Workspace で、各データビューに基づいて新しいプロジェクトを作成し、( **[!UICONTROL 指標]** ドロップダウンリスト ) を参照し、現在のCustomer Journey Analytics契約の最初の日から始まる、月の最初の金曜日までを示します。

   ![イベントを示すフリーフォームテーブル。](./assets/events-usage.png)

   これにより、月々の使用状況のトレンドを把握できます。

1. 必要に応じて、データセット別などにドリルダウンできます。

## Report Builder でのデータブロックの作成 {#arb}

Report Builder で各データ表示に [1 つのデータブロックを作成](/help/report-builder/create-a-data-block.md)してから、合計を求めます。

## Customer Journey AnalyticsAPI での自動レポートの作成 {#api-report}

1. 以下を使用します。 [Customer Journey Analyticsレポート API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) すべてのイベントデータに関するレポートを実行するには、 **接続ごとに**. レポートが次のタイミングで実行されるように設定します

   * 毎月第一金曜日
   * 現在のCustomer Journey Analytics契約の最初の日に戻る

   これにより、月々の使用状況のトレンドを把握できます。すべてのCustomer Journey Analytics接続の合計行数が表示されます。

1. Excel を使用して、このレポートをさらにカスタマイズします。

## 周期的なデータウィンドウを定義して使用状況を管理する {#rolling}

使用状況を管理するには、 [接続 UI](/help/connections/create-connection.md) では、Customer Journey Analyticsデータの保持を、接続レベルで月（1 ヶ月、3 ヶ月、6 ヶ月など）単位の周期的な期間として定義できます。

主な利点は、該当する有用なデータのみを保存またはレポートして、有用でなくなった古いデータを削除できるという点です。契約上の上限を超えないようにし、超過コストのリスクを軽減します。

デフォルト（オフ）のままにすると、Adobe Experience Platform のデータ保持設定によって保持期間が置き換えられます。Experience Platformに 25 ヶ月分のデータがある場合、Customer Journey Analyticsはバックフィルを通じて 25 ヶ月分のデータを取得します。 Platform でこのうち 10 か月を削除すると、Customer Journey Analytics は残りの 15 か月を保持します。

データ保持は、イベントデータセットのタイムスタンプに基づいており、イベントデータセットにのみ適用されます。適用可能なタイムスタンプがないので、プロファイルまたはルックアップデータセットには、周期的なデータ時間枠設定は存在しません。接続に何らかのプロファイルまたは参照データセットが含まれる場合、それらはイベントデータセットと結合されるので、イベントデータセットのタイムスタンプのデータ保持設定に基づいて、Customer Journey Analyticsでデータが保持されます。

