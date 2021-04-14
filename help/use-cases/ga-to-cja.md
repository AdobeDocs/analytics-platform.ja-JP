---
title: Google AnalyticsデータをAdobe Experience Platformに取り込む
description: 'Customer Journey Analytics(CJA)を活用してGoogle AnalyticsやファイアベースのデータをAdobe Experience Platformに取り込む方法を説明します。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: df3b69b837fda821e1b50b0ba211ac578d856892
workflow-type: tm+mt
source-wordcount: '1253'
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

## 履歴（バックフィル）データを取り込む

### 1.Google AnalyticsデータをBigQueryに接続する

次の手順はユニバーサルGoogle Analyticsに基づいています。 これらは履歴データに適用されます。 ライブストリーミングデータの手順については、[ライブストリーミングデータをAEPに取り込む](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/ga-to-cja.html?lang=en#ingest-live-streaming-google-analytics-data)を参照してください。

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

次に、Google AnalyticsイベントをJSON形式でGoogle Cloudストレージに書き出します。 **Export/Export to GCS**&#x200B;をクリックするだけです。 そこに到着したら、データをAdobe Experience Platformに引き込む準備ができている。

Universal Analytics](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)については、[以下の説明を参照してください。
Google Analytics4](https://support.google.com/analytics/answer/7029846?hl=en)については、[以下の説明を参照してください。

### 4. Google CloudストレージからExperience Platformにデータをインポートする

「Experience Platform」で「**[!UICONTROL ソース]**」を選択し、「**[!UICONTROL Google Cloudストレージ]**」オプションを探します。 BigQueryで保存したデータセットを見つけるだけです。

次の点に注意してください。

* JSON形式を選択していることを確認します。
* 既存のデータセットを選択することも、新しいデータセットを作成することもできます（推奨）。
* 履歴Google AnalyticsデータとライブストリーミングGoogle Analyticsデータは、別々のスキーマセットにある場合でも、同じデータに対して同じデータを選択する必要があります。 その後、[CJA接続](/help/connections/combined-dataset.md)のデータセットをマージできます。

このビデオの表示の手順：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

このインポートを定期的にスケジュールする場合は、Googleのドキュメントを参照してください。

### 5. GCSイベントをAdobe Experience Platformに読み込み、XDMスキーマにマッピング

次に、GAイベントデータを以前に作成した既存のデータセットにマップするか、XDMの任意のスキーマを使用して新しいデータセットを作成します。 スキーマを選択すると、Experience Platformは機械学習を適用し、Google Analyticsデータの各フィールドを自動的に[XDMスキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui)に事前マッピングします。

![](assets/schema-map.png)

マッピングは非常に簡単に変更でき、Google Analyticsデータから派生フィールドや計算フィールドを作成することもできます。 フィールドのXDMスキーマへのマッピングが完了したら、このインポートを定期的にスケジュールし、インジェストプロセス中にエラー検証を適用できます。 これにより、読み込んだデータに問題が生じなくなります。

このビデオの表示の手順：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

**タイムスタンプ計算済みフィールド**

Google Analyticsデータの`timestamp`フィールドには、Experience PlatformスキーマUIで特別な計算済みフィールドを作成する必要があります。 **[!UICONTROL 追加計算済みのフィールド]**&#x200B;をクリックし、`timestamp`文字列を`date`関数に含めます。例：

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

次に、この計算済みフィールドをスキーマ内のtimestampデータ構造に保存する必要があります。

![](assets/timestamp.png)

**_id XDM計算フィールド**

`_id`スキーマフィールドには値が必要です。CJAは値を気にしません。 フィールドに「1」を追加できます。

![](assets/_id.png)

## ライブストリーミングGoogle Analyticsデータを取り込む

ライブストリーミングイベントをGoogle Tag Managerから直接Adobe Experience Platformに取り込むこともできます。

### 1.追加カスタム変数

Google Tag Managerアカウントにサインインした後、Adobeに関連するカスタム定数変数をいくつか追加する必要があります。 おそらく、Google Tag Managerに、お客様の電子メール、お客様の名前、言語、お客様のログイン状況など、Google Analyticsに送信される変数が既に存在します。 5つの新しいカスタム変数を定義する必要があります。

* Adobe Experience Cloud組織ID
* DCSストリーミングエンドポイント
* Experience PlatformデータセットID
* スキーマ参照
* ページのタイムスタンプ

これらの値を取得することで、すべてのGoogle Analyticsデータが正しいデータセットに送信され、適切なスキーマを持つようになります。 Experience Cloud組織や先ほど説明した変数がわからない場合は、Adobeのアカウントマネージャーが追跡にご協力ください。

これらのカスタム変数を定義したら、既にGoogle Analyticsに送信しているすべてのデータをExperience Platformに送信するトリガーも設定できます。

### 2. Google Tag Managerでのトリガーの設定

この例では、「アカウントの作成」トリガーが定義されています。ここで`pageUrl equals account-creation`が定義されています。 このトリガーに情報を追加することで、ユーザーが認証に成功し、アカウント作成ページが読み込まれた場合に、データがGoogle AnalyticsとAEPの両方に送信されることを確認できます。

手順については、次のビデオを表示してください。

>[!VIDEO](https://video.tv.adobe.com/v/332668)

また、「[データ取り込み」および「Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9)」も参照してください。

## Google AnalyticsデータセットへのCJAでの接続の作成

Adobe Experience PlatformがライブGoogle Analyticsデータの受信を開始し、BigQueryからの履歴Google Analyticsデータをバックフィルすると、CJAにジャンプして
[最初の接続](/help/connections/create-connection.md)を作成します。 この接続により、共通の「顧客ID」を使用して、GAデータと他のすべての顧客データが結合されます。

手順については、次のビデオを表示してください。

>[!VIDEO](https://video.tv.adobe.com/v/332676)

## Workspaceで驚くべき分析を行う

その他の内容はこちら。