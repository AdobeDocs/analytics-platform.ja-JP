---
title: AEP オーディエンスの Customer Journey Analytics への取り込み
description: 将来の分析用に AEP オーディエンスを Customer Journey Analytics に取り込む方法を説明します。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 04aaf9ae9f720255c97c9dc148953b5b9d6967ae
workflow-type: ht
source-wordcount: '937'
ht-degree: 100%

---

# AEP オーディエンスの Customer Journey Analytics（CJA）への取り込み

このユースケースでは、Adobe Experience Platform（AEP）オーディエンスを CJA に暫定的に手動で取り込む方法を調査します。これらのオーディエンスは、AEP セグメントビルダー、Adobe Audience Manager またはその他のツールで作成され、リアルタイム顧客プロファイル（RTCP）に保存されている可能性があります。オーディエンスは、プロファイル ID のセットと、該当する属性やイベントなどで構成されており、CJA Workspace に取り込んで分析したいと考えています。

## 前提条件

* Adobe Experience Platform（AEP）（特にリアルタイム顧客プロファイル）にアクセスします。
* AEP スキーマおよびデータセットを作成／管理にアクセスします。
* AEP クエリサービス（および SQL 記述機能）または軽い変換を実行するための別のツールにアクセスします。
* Customer Journey Analytics にアクセスします。CJA 接続およびデータビューを作成／変更するには、CJA 製品管理者である必要があります。
* Adobe API（Segmentation、オプションでその他）を使用する機能

## 手順 1：リアルタイム顧客プロファイルでのオーディエンスの選択 {#audience}

Adobe Experience Platform [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)（RTCP）を使用すると、オンライン、オフライン、CRM、サードパーティなど、複数のチャネルのデータを組み合わせて、各顧客の全体像を確認できます。

RTCP のオーディエンスは、既に様々なソースから獲得している可能性があります。1 つ以上のオーディエンスを選択して、CJA に取り込みます。

## 手順 2：エクスポート用のプロファイル結合データセットの作成

最終的に CJA の接続に追加できるデータセットにオーディエンスをエクスポートするために、スキーマがプロファイル[結合スキーマ](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=ja#understanding-union-schemas)であるデータセットを作成する必要があります。

結合スキーマは、同じクラスを共有し、プロファイルが有効になっている複数のスキーマで構成されています。結合スキーマを使用すると、同じクラスを共有するスキーマ内に含まれるすべてのフィールドの融合を確認できます。リアルタイム顧客プロファイルは、結合スキーマを使用して、各顧客の全体像を作成します。

## 手順 3： API 呼び出しを使用したプロファイル結合データセットへのオーディエンスのエクスポート {#export}

オーディエンスを CJA に取り込む前に、AEP データセットにエクスポートする必要があります。これは、Segmentation API（特に[書き出しジョブ API エンドポイント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=ja)）を使用してのみ実行できます。

任意のオーディエンス ID を使用して書き出しジョブを作成し、その結果を手順 2 で作成したプロファイル結合 AEP データセットに取り込むことができます。オーディエンスの様々な属性／イベントをエクスポートできますが、活用する CJA 接続で使用されるユーザー ID フィールドに一致する特定のプロファイル ID フィールドのみをエクスポートする必要があります（後述の手順 5 を参照）。

## 手順 4：エクスポート出力の編集

書き出しジョブの結果は、CJA に取り込むために、別のプロファイルデータセットに変換する必要があります。この変換は、[AEP クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)やその他の任意の変換ツールで行うことができます。CJA でレポートを作成するために必要なのは、（CJA のユーザー ID に一致する）プロファイル ID と 1 つ以上のオーディエンス ID だけです。

ただし、標準的な書き出しジョブには、より多くのデータが含まれているので、この出力を編集して余分なデータを削除したり、いくつかのデータを移動させたりする必要があります。また、先にスキーマ／データセットを作成してから、変換したデータを追加する必要があります。

次に、編集&#x200B;**前**&#x200B;の、プロファイル結合データセットのエクスポート出力の例を示します。

![未編集の出力](../assets/export-unedited.png)

次のことに注意してください。

* オーディエンス ID は、`segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` の下に含まれています。
* ステータスは、「exited」ではなく、「realized」または「entered」である必要があります。

これは、CJA に送信できるプロファイルデータセットの形式です。

![編集された出力](../assets/export-edited.png)

次に、存在する必要があるデータ要素を示します。

* `_aresprodvalidation` 文字列フィールド：組織 ID を示します。実際のものとは異なります。
* `personID` 文字列フィールド：これは、人物を識別するための、プロファイルデータセットの標準 XDM スキーマフィールドです。エクスポートからのプロファイル ID を使用します。
* `audienceMembershipId` 文字列フィールド：エクスポートからのオーディエンス ID。メモ：このフィールドには、（独自のスキーマから）好きな名前を付けることができます。
* 次のように、オーディエンス（`audienceMembershipIdName`）にわかりやすい名前を追加します。

   ![わかりやすいオーディエンス名](../assets/audience-name.png)

* 必要に応じて、他のオーディエンスメタデータを追加します。

## 手順 5： CJA の既存の接続に対するこのプロファイルデータセットの追加

[新しい接続を作成](/help/connections/create-connection.md)できましたが、ほとんどのお客様は、既存の接続にプロファイルデータセットを追加したいはずです。オーディエンス ID は、CJA の既存のデータを「強化」します。

## 手順 6：既存の（または新しく作成した）CJA データビューの変更

データビューに `audienceMembershipId`、`audienceMembershipIdName` および `personID` を追加します。

## 手順 7：ワークスペースでのレポート

ワークスペースで、`audienceMembershipId`、`audienceMembershipIdName` および `personID` についてレポートできるようになりました。

## 追加情報

* このプロセスは、定期的に実行して、CJA 内でオーディエンスデータが常に更新されるようにする必要があります。
* 単一の CJA 接続内で複数のオーディエンスを読み込むことができます。これは、プロセスがさらに複雑になりますが、可能です。これを機能させるには、前述のプロセスに少し修正を加える必要があります。
   1. RTCP 内のオーディエンスコレクションの目的の各オーディエンスに対して、このプロセスを実行します。
   1. CJA は、プロファイルデータセットの配列/オブジェクト配列をサポートします。[オブジェクトの配列](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/object-arrays.html?lang=ja) audienceMembershipId または audienceMembershipIdName の使用が最適なオプションです。
   1. データビューで、`audienceMembershipId` フィールドの部分文字列変換を使用して、新しいディメンションを作成し、コンマ区切り値の文字列を配列に変換します。メモ：現在、配列の値は 10 個までという制限があります。
   1. CJA Workspace 内で、この新しいディメンション `audienceMembershipIds` についてレポートできるようになりました。
