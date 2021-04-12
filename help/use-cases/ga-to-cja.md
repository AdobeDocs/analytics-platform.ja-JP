---
title: Customer Journey AnalyticsでのGoogle Analyticsレポートの設定
description: null
translation-type: tm+mt
source-git-commit: 1324ad5768a7ab215431b9447d9519367dfe17a0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 1%

---


# Customer Journey AnalyticsでのGoogle Analyticsレポートの設定



## 前提条件

* Adobe Experience Platformへのアクセス
* ユニバーサルGoogle Analytics(Google Analytics360版)またはGoogle Analytics4(無料版またはGoogle Analytics360版)へのアクセス
* Customer Journey Analyticsへのアクセス

## 1.Google AnalyticsデータをAdobe Experience Platformに接続する

Google AnalyticsデータをAdobe Experience Platformに取り込む方法は、使用しているGoogle Analyticsのバージョンに応じて異なります。

| 使用する ID | このライセンスも必要です… | それで… |
| --- | --- | --- |
| **ユニバーサルGoogle Analytics** | Google Analytics360 | 次の手順の手順1 ～ xを実行します。 |
| **Google Analytics4** | 無料のGAバージョンまたはGoogle Analytics360 | 以下の手順では、手順xは不要です。 |

以下の手順はユニバーサルGoogle Analyticsに基づいています。

1. Google AnalyticsデータをBigQueryに接続し、
[これらの説明](https://support.google.com/analytics/answer/3416092?hl=en)を参照してください。

1. （Universal Analyticsのお客様のみ）BigQueryでGoogle Analyticsセッションをイベントに変換します。
これにより、データはAdobe Experience Platformと互換性があります。 [これらの説明](https://support.google.com/analytics/answer/3437618?hl=en)を参照してください。

   詳細：BigQueryでは、GAデータは表として表示されます。

   ![](assets/ga-bigquery.png)
ユニバーサル分析データをエクスペリエンスプラットフォームに準拠した形式に変換するには、SQLクエリを作成する必要があります。このビデオの表示の手順：

   >[!VIDEO](https://video.tv.adobe.com/v/332634)

1. Google AnalyticsイベントをJSON形式でGoogle Cloudストレージに書き出し、グループに保存します。
[これらの説明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)を参照してください。

1. Google CloudストレージのデータをExperience Platformに取り込みます。
このビデオの表示の手順：

   >[!VIDEO](https://video.tv.adobe.com/v/332641)

1. GCSイベントをAdobe Experience Platformに読み込み、XDMスキーマにマップ

BigQueryエクスポートスキーマ(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

