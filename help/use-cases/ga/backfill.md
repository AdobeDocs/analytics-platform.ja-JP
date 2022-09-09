---
title: Google Analyticsの履歴データをAdobe Experience Platformに取り込む
description: Customer Journey Analytics(CJA) を使用してGoogle AnalyticsデータをAdobe Experience Platformに取り込む方法について説明します。
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# Google Analyticsの履歴データをAdobe Experience Platformに取り込む

このページでは、Google Analyticsの履歴データをデータセットとしてAdobe Experience Platformに取り込み、Customer Journey Analytics内のデータビューでそのデータセットを参照できるようにする方法について説明します。 このページの手順を [ライブGoogle Analyticsの実装の設定](streaming.md)：繰り返しデータセットを生成します。 この履歴データセットを現在の実装のデータセットと組み合わせて、現在のデータとバックフィルされたデータの両方にCustomer Journey Analyticsし、データをシームレスに表示できます。

## 前提条件

これらのタスクを遂行するには、次のアクセスと権限が必要です。

* Adobe Experience Platform へのアクセス
* Google Analytics（GA Standard または GA 360）へのアクセス
* [管理アクセス](/help/getting-started/cja-access-control.md) Customer Journey Analytics

## BigQuery 書き出しの設定

Universal Analytics プロパティのデータ構造は、Google Analytics4 プロパティのデータ構造とは異なります。 データを書き出すプロパティタイプに基づいて、BigQuery 書き出しを設定します。

* [ユニバーサルアナリティクスプロパティ用の BigQuery 書き出しの設定](https://support.google.com/analytics/answer/3416092)
* [Google Analytics4 プロパティの BigQuery 書き出しを設定する](https://support.google.com/analytics/answer/9823238)

### Universal Analytics プロパティの追加要件

>[!NOTE]
>
>この節は、Universal Analytics プロパティにのみ適用されます。 GA4 プロパティから書き出す場合は、次に進みます。 [Google Cloud Platform へのデータの書き出し](#export-gcp).

ユニバーサル分析プロパティは、各レコードを、個々のイベントではなくユーザーのセッションとしてデータに保存します。 Universal Analytics データをAdobe Experience Platformと互換性のある形式に変換する SQL クエリが必要です。 を適用します。 `UNNEST` 関数を `hits` フィールドに値を入力し、BigQuery テーブルとして保存します。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Google Cloud Platform へのデータの書き出し {#export-gcp}

Google Cloud Platform で、に移動します。 **書き出し/GCS に書き出し**. データがGoogle Cloud Storage に取り込まれたら、Adobe Experience Platformに取り込む準備が整います。

## Google Cloud Storage からExperience Platformへのデータのインポート

1. Adobe Experience Platformで、 **[!UICONTROL ソース]** 左側に
1. カタログで、 **[!UICONTROL Google Cloud Storage]** オプション。 クリック **[!UICONTROL データを追加]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>履歴データとライブストリーミングGoogle Analyticsの両方のデータを読み込む場合は、必ず両方のデータセットで同じスキーマを使用してください。 を使用して、データセットを CJA に結合できます [組み合わせデータセット](/help/connections/combined-dataset.md).

GA イベントデータを以前に作成した既存のデータセットにマッピングしたり、選択した XDM スキーマを使用してデータセットを作成したりできます。 スキーマを選択すると、Experience Platform は機械学習を適用して、Google Analytics データの各フィールドを自動的に [XDM スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja#ui)に事前マッピングします。

![スキーママップ](../assets/schema-map.png)

フィールドの XDM スキーマへのマッピングが完了したら、このインポートを定期的にスケジュールし、取り込みプロセス中にエラー検証を適用できます。 この検証では、読み込んだデータに問題がないことを確認します。

## 必須 XDM フィールド

データを正しく処理するために、Platform の特定の XDM フィールドでは正しい形式が必要です。

* **`timestamp`**:スキーマスキーマ UI で特別な計算フィールドをExperience Platformします。 クリック **[!UICONTROL 計算フィールドを追加]** そして、 `timestamp` 文字列 `date` 関数：

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   計算フィールドをスキーマのタイムスタンプデータ構造に保存します。

   ![タイムスタンプ](../assets/timestamp.png)

* **`_id`**:このフィールドには値が必要です。CJA は値を気にしません。 「1」をフィールドに追加できます。

   ![ID](../assets/_id.png)

## 次の手順

* Adobe Experience Platformにストリーミングする現在のデータがある場合は、 [ストリーミングのGoogle Analyticsデータ](streaming.md).
* バックフィルしたデータのレポートを開始する場合は、 [接続の作成](/help/connections/create-connection.md).
