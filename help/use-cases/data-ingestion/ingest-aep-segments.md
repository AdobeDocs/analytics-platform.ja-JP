---
title: Adobe Experience PlatformオーディエンスのCustomer Journey Analyticsへの取り込み
description: Adobe Experience PlatformのオーディエンスをCustomer Journey Analyticsに取り込んで、さらに分析する方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 50%

---

# Adobe Experience PlatformオーディエンスのAdobe Customer Journey Analyticsへの取り込み

この使用例では、Adobe Experience Platform(Adobe Experience Platform) オーディエンスを手動でCustomer Journey Analyticsに導く、中間的な方法を説明します。 これらのオーディエンスは、Adobe Experience Platform Segment Builder、Adobe Audience Manager、またはその他のツールで作成され、リアルタイム顧客プロファイル (RTCP) に保存されている場合があります。 オーディエンスは、プロファイル ID のセットと、該当する属性やイベントなどで構成されており、Analysis Workspace に取り込んで分析をCustomer Journey Analyticsします。

## 前提条件

* Adobe Experience Platform(Adobe Experience Platform)、特にリアルタイム顧客プロファイルへのアクセス。
* Adobe Experience Platformのスキーマとデータセットを作成/管理するためのアクセス権。
* Adobe Experience Platformクエリサービス（および SQL を書き込む機能）へのアクセス、またはいくつかの光変換を実行する別のツールへのアクセス。
* Customer Journey Analytics にアクセスします。Customer Journey Analytics接続とデータ表示を作成/変更するには、Customer Journey Analyticsの製品管理者である必要があります。
* Adobe API（Segmentation、オプションでその他）を使用する機能

## 手順 1：リアルタイム顧客プロファイルでのオーディエンスの選択 {#audience}

Adobe Experience Platform [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)（RTCP）を使用すると、オンライン、オフライン、CRM、サードパーティなど、複数のチャネルのデータを組み合わせて、各顧客の全体像を確認できます。

RTCP のオーディエンスは、既に様々なソースから獲得している可能性があります。Customer Journey Analyticsに取り込むオーディエンスを 1 つ以上選択します。

## 手順 2：エクスポート用のプロファイル結合データセットの作成

オーディエンスをデータセットに書き出し、最終的にCustomer Journey Analyticsの接続に追加するには、スキーマがプロファイルのデータセットを作成する必要があります [和集合スキーマ](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html#understanding-union-schemas).

結合スキーマは、同じクラスを共有し、プロファイルが有効になっている複数のスキーマで構成されています。結合スキーマを使用すると、同じクラスを共有するスキーマ内に含まれるすべてのフィールドの融合を確認できます。リアルタイム顧客プロファイルは、結合スキーマを使用して、各顧客の全体像を作成します。

## 手順 3： API 呼び出しを使用したプロファイル結合データセットへのオーディエンスのエクスポート {#export}

オーディエンスをCustomer Journey Analyticsに取り込む前に、Adobe Experience Platformデータセットに書き出す必要があります。 これは、Segmentation API（特に[書き出しジョブ API エンドポイント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html)）を使用してのみ実行できます。

任意のオーディエンス ID を使用して書き出しジョブを作成し、その結果を手順 2 で作成したプロファイルの和集合Adobe Experience Platformデータセットに格納できます。 オーディエンスに対して様々な属性やイベントを書き出すことができますが、使用するCustomer Journey Analytics接続で使用するユーザー ID フィールドに一致する、特定のプロファイル ID フィールドを書き出すだけで済みます（手順 5 の以下を参照）。

## 手順 4：エクスポート出力の編集

書き出しジョブの結果をCustomer Journey Analyticsに取り込むには、別のプロファイルデータセットに変換する必要があります。  この変換は、 [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)、または任意の別の変換ツールを使用できます。 Customer Journey Analyticsでのレポートをおこなうには、プロファイル ID(Customer Journey Analyticsのユーザー ID と一致する ) と 1 つ以上のオーディエンス ID のみが必要です。

ただし、標準的な書き出しジョブには、より多くのデータが含まれているので、この出力を編集して余分なデータを削除したり、いくつかのデータを移動させたりする必要があります。また、先にスキーマ／データセットを作成してから、変換したデータを追加する必要があります。

次に、編集&#x200B;**前**&#x200B;の、プロファイル結合データセットのエクスポート出力の例を示します。

![未編集の出力](../assets/export-unedited.png)

次のことに注意してください。

* オーディエンス ID は、`segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` の下に含まれています。
* ステータスは、「exited」ではなく、「realized」または「entered」である必要があります。

これは、Customer Journey Analyticsに送信できるプロファイルデータセットの形式です。

![編集された出力](../assets/export-edited.png)

次に、存在する必要があるデータ要素を示します。

* `_aresprodvalidation` 文字列フィールド：組織 ID を示します。実際のものとは異なります。
* `personID` 文字列フィールド：これは、人物を識別するための、プロファイルデータセットの標準 XDM スキーマフィールドです。エクスポートからのプロファイル ID を使用します。
* `audienceMembershipId` 文字列フィールド：エクスポートからのオーディエンス ID。メモ：このフィールドには、（独自のスキーマから）好きな名前を付けることができます。
* 次のように、オーディエンス（`audienceMembershipIdName`）にわかりやすい名前を追加します。

  ![わかりやすいオーディエンス名](../assets/audience-name.png)

* 必要に応じて、他のオーディエンスメタデータを追加します。

## 手順 5：このプロファイルデータセットをCustomer Journey Analyticsの既存の接続に追加する

[新しい接続を作成](/help/connections/create-connection.md)できましたが、ほとんどのお客様は、既存の接続にプロファイルデータセットを追加したいはずです。オーディエンス ID が、Customer Journey Analyticsの既存のデータを「エンリッチメント」する。

## 手順 6：既存のCustomer Journey Analyticsデータビューを変更（または新規作成）する

データビューに `audienceMembershipId`、`audienceMembershipIdName` および `personID` を追加します。

## 手順 7：ワークスペースでのレポート

ワークスペースで、`audienceMembershipId`、`audienceMembershipIdName` および `personID` についてレポートできるようになりました。

## 追加情報

* オーディエンスデータが常にCustomer Journey Analytics内で更新されるように、このプロセスを定期的に実行する必要があります。
* 1 つのオーディエンス接続内で複数のオーディエンスをCustomer Journey Analyticsできます。 これは、プロセスがさらに複雑になりますが、可能です。これを機能させるには、前述のプロセスに少し修正を加える必要があります。
   1. RTCP 内のオーディエンスコレクションの目的の各オーディエンスに対して、このプロセスを実行します。
   1. Customer Journey Analyticsは、プロファイルデータセットで配列/オブジェクト配列をサポートします。 [オブジェクトの配列](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=ja) audienceMembershipId または audienceMembershipIdName の使用が最適なオプションです。
   1. データビューで、`audienceMembershipId` フィールドの部分文字列変換を使用して、新しいディメンションを作成し、コンマ区切り値の文字列を配列に変換します。メモ：現在、配列の値は 10 個までという制限があります。
   1. これで、この新しいディメンションに関するレポートを作成できます `audienceMembershipIds` Workspace 内で使用できます。
