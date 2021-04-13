---
title: Customer Journey Analyticsでの分析(CJA)のためにGoogle AnalyticsデータをAdobe Experience Platformに取り込む方法
description: 'Customer Journey Analytics(CJA)を活用してGoogle AnalyticsやファイアベースのデータをAdobe Experience Platformに取り込む方法を説明します。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# Google AnalyticsデータをAdobe Experience Platformに取り込む

この使用例では、Google AnalyticsデータをデータセットとしてAdobe Experience Platformに取り込む方法に重点を置いています。 （これは、履歴データとライブデータの両方に適用されます）。 完了したら、両方のデータセットを組み合わせて、ユーザーのジャーニーをデバイス間で表示できます。

Experience Platform内のデータセットは、次の2つの要素で構成されています。スキーマと、データセット内の実際のレコード。 スキーマ（短く言うとExperience Data ModelまたはXDM）は、データセットの列に似ており、データ自体を記述する設計図やルールのようです。 プラットフォーム内で、Adobeは次の2種類のスキーマを提供します。

* Google Analyticsデータを自動的にマッピングする(エクスペリエンスイベントスキーマと呼ばれる)、あらかじめ用意されているスキーマー（エクスペリエンス）
* Google Analyticsデータを作成し、簡単にマッピングできるカスタムスキーマ

Adobeのデータモデルの最も強力な側面の1つは、顧客のインタラクションデータをすべて1つの共通スキーマに標準化できる点です。これにより、CJAでデータをより簡単に結合できます。

## 前提条件

これらのタスクを達成するには、次のアクセス権と権限が必要です。

* Adobe Experience Platformへのアクセス
* ユニバーサルGoogle Analytics(Google Analytics360版)またはGoogle Analytics4(無料版またはGoogle Analytics360版)へのアクセス
* Customer Journey Analyticsとその[管理者権限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja-JP#admin-access-permissions)へのアクセス。

Google AnalyticsデータをAdobe Experience Platformに取り込む方法は、使用しているGoogle Analyticsのバージョンに応じて異なります。

| 使用する ID | このライセンスも必要です… | それで… |
| --- | --- | --- |
| **ユニバーサルGoogle Analytics** | Google Analytics360 | 次の手順の手順1 ～ 5を実行します。 |
| **Google Analytics4** | 無料のGAバージョンまたはGoogle Analytics360 | 次の手順の手順1 ～ 5を実行します。 手順2は不要です。 |

## 1.Google AnalyticsデータをBigQueryに接続する

次の手順はユニバーサルGoogle Analyticsに基づいています。

[これらの説明](https://support.google.com/analytics/answer/3416092?hl=en)を参照してください。

## 2. BigQueryでGoogle Analyticsセッションをイベントに変換する

>[!IMPORTANT]
>
>この手順は、Universal Analyticsのお客様のみに適用されます

GAデータは、各レコードを、個々のイベントではなく、ユーザーのセッションとしてデータに保存します。 データを変換すると、そのデータはAdobe Experience Platformと互換性があります。

[これらの説明](https://support.google.com/analytics/answer/3437618?hl=en)を参照してください。

ユニバーサル分析データをエクスペリエンスプラットフォームに準拠した形式に変換するには、SQLクエリを作成する必要があります。 このビデオの表示の手順：

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3.Google AnalyticsイベントをJSON形式でGoogle Cloudストレージに書き出し、バケットに保存する

[これらの説明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)を参照してください。

## 4. Google CloudストレージのデータをExperience Platformに取り込む

このビデオの表示の手順：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. GCSイベントをAdobe Experience Platformに読み込み、XDMスキーマにマッピング

BigQueryエクスポートスキーマ(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
