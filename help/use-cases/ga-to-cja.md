---
title: Customer Journey AnalyticsでのGoogle Analyticsレポートの設定
description: null
translation-type: tm+mt
source-git-commit: 9bbc625aca9e0b8384b3e95d79fd695fda863f0b
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Customer Journey AnalyticsでのGoogle Analyticsレポートの設定

Google Cloudストレージコネクタの設定、

Google Tag Managerの設定

BigQueryエクスポートスキーマ(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. GAセッションをビッグクエリのイベントに変換
1. Google CloudストレージへのGoogle Analyticsイベントのエクスポート
1. GCSイベントをAdobe Experience Platformに読み込み、XDMスキーマにマップ

## 前提条件

* Adobe Experience Platformへのアクセス
* ユニバーサルGoogle Analytics(Google Analytics360版)またはGoogle Analytics4(無料版またはGoogle Analytics360版)へのアクセス
* Customer Journey Analyticsへのアクセス

## Google AnalyticsデータをAdobe Experience Platformに接続

Google AnalyticsデータをAdobe Experience Platformに取り込む方法は、使用しているGoogle Analyticsのバージョンに応じて異なります。

| 使用する ID | このライセンスも必要です… | それで… |
| --- | --- | --- |
| **ユニバーサルGoogle Analytics** | Google Analytics360 | 次の手順の手順1 ～ xを実行します。 |
| **Google Analytics4** | 無料のGAバージョンまたはGoogle Analytics360 | 以下の手順では、手順xは不要です。 |

以下の手順はユニバーサルGoogle Analyticsに基づいています。

1. Google AnalyticsデータをBigQueryに接続し、
[これらの説明](https://support.google.com/analytics/answer/3416092?hl=en)を参照してください。
1. （Universal Analyticsのお客様のみ）BigQueryでGoogle Analyticsセッションをイベントに変換します。
[これらの説明](https://support.google.com/analytics/answer/3437618?hl=en)を参照してください。
1. Google AnalyticsイベントをGoogle Cloudストレージに書き出します。
[これらの説明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)を参照してください。
