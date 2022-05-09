---
title: AEP オーディエンスのCustomer Journey Analyticsへの取り込み
description: AEP オーディエンスをCustomer Journey Analyticsに取り込み、分析する方法を説明します。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 9c4869bb632f3d69d8704009744246b975cb5c4a
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 2%

---

# AEP オーディエンスのCustomer Journey Analyticsへの取り込み (CJA)

この使用例では、Adobe Experience Platform(AEP) オーディエンスを CJA に導く中間的で手動の方法を調べます。 これらのオーディエンスは、AEP Segment Builder、Adobe Audience Manager、またはその他のツールで作成され、リアルタイム顧客プロファイル (RTCP) に保存されている場合があります。 オーディエンスは、一連のプロファイル ID と、適用可能な属性やイベントなどで構成されます。 CJA Workspace に取り込んで分析を行います。

## 前提条件

* Adobe Experience Platform(AEP)、特にリアルタイム顧客プロファイルへのアクセス
* AEP スキーマとデータセットを作成/管理するためのアクセス権。
* AEP クエリサービス（および SQL を書き込む機能）へのアクセス、またはいくつかの光変換を実行する別のツールへのアクセス。
* Customer Journey Analyticsへのアクセス CJA 接続とデータビューを作成/変更するには、CJA 製品管理者である必要があります。
* AdobeAPI の使用機能（セグメント化、オプションでその他）

## 手順 1:リアルタイム顧客プロファイルでのオーディエンスの選択 {#audience}

Adobe Experience Platform [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja) (RTCP) を使用すると、オンライン、オフライン、CRM、サードパーティなど、複数のチャネルからのデータを組み合わせることで、各顧客の全体像を確認できます。

RTCP には、様々なソースから来た可能性のあるオーディエンスが既に存在する可能性があります。 CJA に取り込むオーディエンスを 1 つ以上選択します。

## 手順 2:エクスポート用のプロファイル和集合データセットの作成

オーディエンスをデータセットに書き出し、最終的に CJA の接続に追加するには、スキーマがプロファイルのデータセットを作成する必要があります [和集合スキーマ](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

和集合スキーマは、同じクラスを共有し、プロファイルに対して有効にされた複数のスキーマで構成されます。 和集合スキーマを使用すると、同じクラスを共有するスキーマ内に含まれるすべてのフィールドの統合を表示できます。 リアルタイム顧客プロファイルは、和集合スキーマを使用して、各顧客の全体像を作成します。

## 手順 3:API 呼び出しを使用してオーディエンスをプロファイル和集合データセットに書き出す {#export}

オーディエンスを CJA に取り込む前に、AEP データセットに書き出す必要があります。 これは、Segmentation API、特に [書き出しジョブ API エンドポイント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en).

任意のオーディエンス ID を使用して書き出しジョブを作成し、その結果を手順 2 で作成したプロファイルの和集合 AEP データセットに格納できます。 オーディエンスに対して様々な属性やイベントを書き出すことができますが、必要なのは、活用する CJA 接続で使用するユーザー ID フィールドに一致する特定のプロファイル ID フィールドのみです（手順 5 の後述）。

## 手順 4:書き出し出力の編集

書き出しジョブの結果を CJA に取り込むには、別のプロファイルデータセットに変換する必要があります。  この変換は、 [AEP クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)、または任意の別の変換ツールを使用できます。 CJA でのレポートをおこなうには、プロファイル ID（CJA のユーザー ID と一致する）と 1 つ以上のオーディエンス ID のみが必要です。

ただし、標準のエクスポートジョブには、より多くのデータが含まれているので、この出力を編集して不要なデータを削除し、いくつかの点を移動する必要があります。  また、変換後のデータを追加する前に、まずスキーマ/データセットを作成する必要があります。

次に、プロファイル和集合データセットの書き出し出力の例を示します。 **前** 任意の編集：

![未編集の出力](assets/export-unedited.png)

以下のことに注意してください。

* オーディエンス ID は、 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* ステータスは、「適合」または「入口」である必要がありますが、「出口」ではありません。

これは、CJA に送信できるプロファイルデータセットの形式です。

![編集された出力](assets/export-edited.png)

存在する必要があるデータ要素を次に示します。

* `_aresprodvalidation` 文字列フィールド：組織 ID を参照します。 君のは違う。
* `personID` 文字列フィールド：これは、人物を識別するための、プロファイルデータセットの標準 XDM スキーマフィールドです。 エクスポートからプロファイル ID を使用します。
* `audienceMembershipId` 文字列フィールド：書き出しからのオーディエンス ID。  注意：このフィールドには、任意の名前を付けることができます（独自のスキーマから）。
* オーディエンスのわかりやすい名前を追加します (`audienceMembershipIdName`など )

   ![わかりやすいオーディエンス名](assets/audience-name.png)

* 必要に応じて、他のオーディエンスメタデータを追加します。

## 手順 5:このプロファイルデータセットを CJA の既存の接続に追加します。

以下が可能です。 [新しい接続を作成](/help/connections/create-connection.md)を使用する場合でも、ほとんどの場合は、プロファイルデータセットを既存の接続に追加する必要があります。 オーディエンス ID が CJA の既存のデータを「エンリッチメント」する。

## 手順 6:既存の（または新しい）CJA データビューの変更

追加 `audienceMembershipId`, `audienceMembershipIdName` および `personID` をデータビューに追加します。

## 手順 7:Workspace のレポート

次の項目に関するレポートが作成されました： `audienceMembershipId`, `audienceMembershipIdName` および `personID` Workspace で使用できます。

## 追加情報

* オーディエンスデータが CJA 内で常に更新されるように、このプロセスを定期的に実行する必要があります。
* 1 つの CJA 接続内で複数のオーディエンスをインポートできます。 これにより、プロセスがさらに複雑になりますが、可能です。 これを機能させるには、上記のプロセスを少し変更する必要があります。
   1. RTCP 内のオーディエンスコレクション内の目的のオーディエンスごとに、このプロセスを実行します。
   1. 書き出しジョブの出力の変換を実行する場合は、次のリストを作成する必要があります。 `audienceMembershipId(s)`と呼ばれます。これは、単一の CJA ユーザー ID が複数のオーディエンスに属している可能性があるからです。 CJA は、将来のある時点で、プロファイルデータセット内の配列/オブジェクト配列をサポートする予定です。 これらをサポートした後は、 `audienceMembershipId` または `audienceMembershipIdName` が最適なオプションになります。 中間では、書き出しジョブ出力で各プロファイル ID の現在のオーディエンス ID をすべて抽出し（ステータスは「適合済み」または「入力済み」）、コンマ区切りの値文字列 ( `<id1>,<id2>,...`) をクリックします。  ステータスが「出口」のオーディエンス ID がある場合は、それがリストにないことを確認します。  ID とのわかりやすい名前の関連付けを維持する場合は、リスト内の各 ID の末尾に（他のメタデータと共に）添付できます。
   1. データビューで、 `audienceMembershipId` フィールドに値を入力します。 注意：現在、配列には 10 個の値の制限があります。
   1. これで、この新しいディメンションに関するレポートを作成できます `audienceMembershipIds` （CJA Workspace 内）を参照してください。
