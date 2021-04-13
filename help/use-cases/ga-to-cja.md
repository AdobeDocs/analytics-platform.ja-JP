---
title: Customer Journey Analyticsでの分析(CJA)のためにGoogle AnalyticsデータをAdobe Experience Platformに取り込む方法
description: 'Customer Journey Analytics(CJA)を活用してGoogle AnalyticsやファイアベースのデータをAdobe Experience Platformに取り込む方法を説明します。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: cc212d8b1e0a229fd246f6678a8dc8e5bbadce79
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 1%

---


# Google AnalyticsデータをAdobe Experience Platformに取り込む

この使用例では、Google AnalyticsデータをデータセットとしてAdobe Experience Platformに取り込む方法に重点を置いています。 履歴データと実データの両方を取り込む方法を説明します。 完了したら、両方のデータセットをCustomer Journey Analyticsで組み合わせて、ユーザのジャーニーをデバイス間で表示できます。

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
| **ユニバーサル解析** | Google Analytics360 | 次の手順の手順1 ～ 5を実行します。 |
| **Google Analytics4** | 無料のGAバージョンまたはGoogle Analytics360 | 次の手順の手順1 ～ 5を実行します。 手順2は不要です。 |

## 履歴データを取り込む

### 1.Google AnalyticsデータをBigQueryに接続する

次の手順はユニバーサルGoogle Analyticsに基づいています。 これらは履歴データに適用されます。 ライブストリーミングデータの手順については、ライブストリーミングデータをAEPに取り込むを参照してください。

[これらの説明](https://support.google.com/analytics/answer/3416092?hl=en)を参照してください。

### 2. BigQueryでGoogle Analyticsセッションをイベントに変換する

>[!IMPORTANT]
>
>この手順は、Universal Analyticsのお客様のみに適用されます

GAデータは、各レコードを、個々のイベントではなく、ユーザーのセッションとしてデータに保存します。 ユニバーサル分析データをエクスペリエンスプラットフォームに準拠した形式に変換するには、SQLクエリを作成する必要があります。 GAスキーマの「ヒット」フィールドに「アンネスト」関数を適用します。 使用できるSQLの例を次に示します。

`SELECT
*,
timestamp_seconds(`` + hit.time) AS `` 
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
`visitStartTimetimestampyour_bq_table_2021_04_*`,
UNNEST(hits) AS hit 
)`

クエリが完了したら、完全な結果をBigQueryテーブルに保存します。

[これらの説明](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)を参照してください。

または、このビデオを表示します。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3.Google AnalyticsイベントをJSON形式でGoogle Cloudストレージに書き出し、バケットに保存する

次に、Google AnalyticsイベントをJSON形式でGoogle Cloudストレージに読み込みます。 Experience Platformに持って行く。

[これらの説明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)を参照してください。

### 4. Google CloudストレージのデータをExperience Platformに取り込む

「Experience Platform」で「**[!UICONTROL ソース]**」を選択し、「**[!UICONTROL Google Cloudストレージ]**」オプションを探します。 そこから、Bigクエリから保存したデータセットを探すだけです。

このビデオの表示の手順：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5. GCSイベントをAdobe Experience Platformに読み込み、XDMスキーマにマッピング

次に、GAイベントデータを以前に作成した既存のデータセットにマップするか、XDMスキーマを選択して新しいデータセットを作成します。 スキーマを選択すると、Experience Platformは機械学習を適用し、Google Analyticsデータの各フィールドを自分のスキーマに自動的にマッピングします。

マッピングは非常に簡単に変更でき、Google Analyticsデータから派生フィールドや計算フィールドを作成することもできます。 フィールドのXDMスキーマへのマッピングが完了したら、このインポートを定期的にスケジュールし、インジェストプロセス中にエラー検証を適用できます。 これにより、読み込んだデータに問題が生じなくなります。

## ライブストリーミングGoogle Analyticsデータを取り込む

ライブストリーミングイベントをGoogle Tag Managerから直接Adobe Experience Platformに取り込むこともできます。

### 追加カスタム変数

Google Tag Managerアカウントにサインインした後、Adobe組織IDとデータセットIDに関連するカスタム定数変数を追加する必要があります。 おそらく、Google Tag Managerに、お客様の電子メール、お客様の名前、言語、お客様のログイン状況など、Google Analyticsに送信される変数が既に存在します。 5つの新しいカスタム変数を定義する必要があります。

* Adobe Experience Cloud組織ID
* DCSストリーミングエンドポイント
* Experience PlatformデータセットID
* スキーマ参照
* ページのタイムスタンプ。

これらの値を取得することで、すべてのGoogle Analyticsデータが正しいデータセットに送信され、適切なスキーマを持つようになります。 Experience Cloud組織や先ほど説明した変数がわからない場合は、Adobeのアカウントマネージャーが追跡にご協力ください。

これらのカスタム変数を定義したら、既にGoogle Analyticsに送信しているすべてのデータをExperience Platformに送信するトリガーも設定できます。

### Google Tag Managerでのトリガーの設定

この例では、「アカウントの作成」トリガーが定義されています。ここで`pageUrl equals account-creation`が定義されています。 このトリガーに情報を追加することで、ユーザーが認証に成功し、アカウント作成ページが読み込まれた場合に、データがGoogle AnalyticsとAEPの両方に送信されることを確認できます。

手順については、次のビデオを表示してください。

>[!VIDEO](https://video.tv.adobe.com/v/332668)

### 次の手順

Adobe Experience PlatformがライブGoogle Analyticsデータの受信を開始し、BigQueryからの履歴Google Analyticsデータをバックフィルすると、CJAにジャンプして

1. [最初の接続を作成し、共通の「顧客ID」を使用して、GAデータと他のすべての顧客データを結合します。](/help/connections/create-connection.md) 
1. Workspaceで、次のような素晴らしい分析を行います。

*このトピックを停止する必要があるか、接続の詳細を調べる必要があるか。*
