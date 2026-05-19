---
title: Google Analytics 履歴データの取り込み
description: Adobe Customer Journey Analyticsを使用してGoogle Analytics データをAdobe Experience Platformに取り込む方法について説明します。
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T07:58:46.205Z'
TQID: 'https://experienceleague.adobe.com/X5R0sqTkZKxvzH7mwv69-Ez3MIbuTg6XDGuxrw-iugw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 83%

---

# Google Analytics 履歴データの取り込み

このページでは、Google Analytics の履歴データをデータセットとして Adobe Experience Platform に取り込み、Customer Journey Analytics 内のデータビューでそのデータセットを参照できるようにする方法について重点的に説明します。 このページの手順を、繰り返しデータセットの生成について説明した[ライブ Google Analytics の実装の設定](streaming.md)のページと組み合わせることができます。 この履歴データセットを現在の実装環境のデータセットと組み合わせることで、Customer Journey Analytics に現在のデータとバックフィルされたデータの両方をシームレスに表示して確認できます。

## 前提条件

これらのタスクを遂行するには、次のアクセスと権限が必要です。

* Adobe Experience Platform へのアクセス
* Google Analytics（GA スタンダード版または GA 360）へのアクセス権限
* Customer Journey Analytics への[管理者アクセス権限](/help/technotes/access-control.md)

## BigQuery エクスポートの設定

ユニバーサルアナリティクスのプロパティのデータ構造は、Google Analytics 4 のプロパティのデータ構造とは異なります。 データをエクスポートするプロパティタイプに基づいて、BigQuery エクスポートを設定します。

* [ユニバーサル Analytics プロパティ用のBigQuery エクスポートの設定](https://support.google.com/analytics/answer/3416092)
* [Google Analytics 4 プロパティのBigQuery書き出しの設定](https://support.google.com/analytics/answer/9823238)

### ユニバーサルアナリティクスのプロパティに関するその他の要件

>[!NOTE]
>
>この節は、ユニバーサルアナリティクスのプロパティにのみ適用されます。 GA4 プロパティからエクスポートする場合は、[Google Cloud Platform へのデータのエクスポート](#export-gcp)の節に進んでください。

ユニバーサルアナリティクスのプロパティは、各レコードを、個々のイベントではなくユーザーのセッションとしてデータに保存します。 ユニバーサルアナリティクスデータを Adobe Experience Platform と互換性のある形式に変換する SQL クエリが必要です。 GA スキーマで `UNNEST` 関数を `hits` フィールドに適用し、BigQuery テーブルとして保存します。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Google AnalyticsからCustomer Journey Analyticsまで – BigQuery](https://video.tv.adobe.com/v/332634?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


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

## Google Cloud Platform へのデータのエクスポート {#export-gcp}

Google Cloud Platform で、**エクスポート／GCS にエクスポート**&#x200B;に移動します。 データが Google Cloud Storage に取り込まれたら、Adobe Experience Platform に取り込む準備が整いました。

## Google Cloud Storage から Experience Platform へのデータのインポート

1. Adobe Experience Platform で、左側の「**[!UICONTROL ソース]**」を選択します。
1. カタログの下で、「**[!UICONTROL Google Cloud Storage]**」オプションを見つけます。 「**[!UICONTROL データを追加]**」をクリックします。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Google Analytics データをAdobe Experience Platform](https://video.tv.adobe.com/v/3437167?captions=jpn&quality=12&learn=on){target="_blank"}に読み込むを参照してください。

>[!ENDSHADEBOX]


>[!TIP]
>
>Google Analytics の履歴データとライブストリーミングデータの両方をインポートする場合は、必ず両方のデータセットで同じスキーマを使用してください。 [結合データセット &#x200B;](/help/connections/combined-dataset.md)を使用して、Customer Journey Analyticsのデータセットを結合できます。

選択した XDM スキーマを使用して、GA イベントデータを作成済みの既存データセットにマッピングしたり、データセットを作成したりできます。 スキーマを選択すると、Experience Platform は機械学習を適用して、Google Analytics データの各フィールドを自動的に [XDM スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja#ui)に事前マッピングします。

GA データフィールドとTarget スキーママッピングを強調表示する![&#x200B; スキーママップ &#x200B;](../../assets/schema-map.png)

フィールドから XDM スキーマへのマッピングが完了したら、このインポートを繰り返しスケジュールしたり、取り込みプロセス中にエラー検証を適用したりできます。 この検証により、インポートしたデータに関する問題が生じなくなります。

## 必須の XDM フィールド

データを正しく処理するために、Platform の特定の XDM フィールドには正しい形式が必要です。

* **`timestamp`**：Experience Platform スキーマ UI で特別な計算フィールドを作成します。 「**[!UICONTROL 計算フィールドを追加]**」をクリックして、次のように `timestamp` 文字列を `date` 関数に含めます。

  `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

  計算フィールドをスキーマのタイムスタンプデータ構造に保存します。

  ![タイムスタンプ](../../assets/timestamp.png)

* **`_id`**：このフィールドには値が含まれている必要があります。Customer Journey Analyticsは値を気にしません。 フィールドに「1」を追加できます。

  ![ID](../../assets/_id.png)

## 次の手順

* Adobe Experience Platform にストリーミングする現在のデータがある場合は、[Google Analytics データのストリーミング設定](streaming.md)を参照してください。
* バックフィルしたデータのレポートを開始する場合は、[接続の作成](/help/connections/create-connection.md)を参照してください。
