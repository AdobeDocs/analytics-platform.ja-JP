---
title: Adobe Experience Platform への Google Analytics データの取り込み
description: 'Customer Journey Analytics（CJA）を利用して Google Analytics データを Adobe Experience Platform に取り込む方法を説明します。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
source-git-commit: 316819116e9b47110763479af4e8504a2bffaff3
workflow-type: ht
source-wordcount: '1178'
ht-degree: 100%

---


# Adobe Experience Platform への Google Analytics データの取り込み

このユースケースでは、Google Analytics データをデータセットとして Adobe Experience Platform に取り込む方法を重点的に取り上げています。 履歴データとライブデータの両方を取り込む方法について説明します。 完了したら、Customer Journey Analytics で両方のデータセットを組み合わせて、ユーザーのジャーニーをクロスデバイスで表示できます。

Experience Platform 内のデータセットは、スキーマとデータセット内の実際のレコードの 2 つで構成されています。 スキーマ（Experience Data Model または略して XDM）は、データセットの列のようなものであり、データ自体を記述するブループリントまたはルールのようなものです。 Platform 内で、アドビは次の 2 種類のスキーマを提供します。

* Google Analytics データから自動的にマッピングできる標準提供スキーマ（エクスペリエンスイベントスキーマと呼ばれます）
* 独自に作成して Google Analytics データから簡単にマッピングできるカスタムスキーマ

アドビのデータモデルの最も強力な側面の 1 つは、顧客のインタラクションデータをすべて 1 つの共通スキーマに標準化できる点です。これにより、CJA でデータを結合するのがはるかに簡単になります。

## 前提条件

これらのタスクを遂行するには、次のアクセスと権限が必要です。

* Adobe Experience Platform へのアクセス
* Universal Google Analytics（Google Analytics 360 版）または Google Analytics 4（無料版または Google Analytics 360 版）へのアクセス
* Customer Journey Analytics へのアクセスとその[管理者権限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja#admin-access-permissions)。

Google Analytics データを Adobe Experience Platform に取り込む方法は、使用している Google Analytics のバージョンによって異なります。

| 使用する ID | 同時に必要なライセンス | 実行するタスク |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | 次の手順 1～3 を実行します。 |
| **Google Analytics 4** | 無料版 GA または Google Analytics 360 | 次の手順 1 と 3 を実行します。 手順 2 は不要です。 |

## 履歴（バックフィル）データの取り込み

### 1. Google Analytics データを BigQuery に接続する

詳しくは、[これらの説明](https://support.google.com/analytics/answer/3416092?hl=ja)を参照してください。 これらの手順は Universal Google Analytics に基づいています。

### 2. Google Analytics セッションを BigQuery 内のイベントに変換し、Google クラウドストレージに書き出す

>[!IMPORTANT]
>
>この手順は、Universal Analytics ユーザーにのみ適用されます

GA データでは、データ内の各レコードが個々のイベントではなくユーザーのセッションとして格納されます。 Universal Analytics データを Experience-Platform に準拠した形式に変換するには、SQL クエリを作成する必要があります。 GA スキーマの「hits」フィールドに「unnest」関数を適用します。 使用できる SQL の例を次に示します。

```
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
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

クエリが完了したら、完全な結果を BigQuery テーブルに保存します。

[これらの手順](https://support.google.com/analytics/answer/7029846?hl=ja&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)（SQL クエリの説明を含む）を参照してください。

次のビデオでは、Google Analytics イベントを JSON 形式で Google クラウドストレージに書き出す次の手順についても説明します。 **エクスポート／GCS にエクスポート**&#x200B;をクリックするだけです。 ダイアログが開いたら、データを Adobe Experience Platform に取り込む準備ができています。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. データを Google クラウドストレージから Experience Platform にインポートし、XDM スキーマにマッピングする

Experience Platform で「**[!UICONTROL ソース]**」を選択し、「**[!UICONTROL Google クラウドストレージ]**」オプションを探します。 そこから、BigQuery から保存したデータセットを見つける必要があります。

次の点に注意してください。

* 必ず JSON 形式を選択します。
* 既存のデータセットを選択することも、新しいデータセットを作成することもできます（推奨）。
* Google Analytics の履歴データとライブストリーミングデータについては、別々のデータセットにある場合でも、必ず同じスキーマを選択してください。 その後、[CJA 接続](/help/connections/combined-dataset.md)のデータセットを結合できます。

手順については、次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/332676)

選択した XDM スキーマを使用して、GA イベントデータを作成済みの既存データセットにマッピングしたり、新しいデータセットを作成したりできます。 スキーマを選択すると、Experience Platform は機械学習を適用して、Google Analytics データの各フィールドを自動的に [XDM スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja#ui)に事前マッピングします。

![](assets/schema-map.png)

マッピングは非常に簡単に変更でき、Google Analytics データから派生フィールドや計算フィールドを作成することもできます。 フィールドから XDM スキーマへのマッピングが完了したら、このインポートを繰り返しスケジュールしたり、取り込みプロセス中にエラー検証を適用したりできます。 これにより、インポートしたデータに関する問題が生じなくなります。

**「timestamp」計算フィールド**

Google Analytics データの `timestamp` スキーマフィールドについては、Experience Platform スキーマ UI で特別な計算フィールドを作成する必要があります。 「**[!UICONTROL 計算フィールドを追加]**」をクリックして、次のように `timestamp` 文字列を `date` 関数に含めます。

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

次に、この計算フィールドをスキーマのタイムスタンプデータ構造に保存する必要があります。

![](assets/timestamp.png)

**「_id」計算フィールド**

`_id` スキーマフィールドには値が必要です。どのような値でも構いません。 フィールドに「1」を追加するだけです。

![](assets/_id.png)

## Google Analytics ライブストリーミングデータの取り込み

ライブストリーミングイベントを Google Tag Manager から直接 Adobe Experience Platform に取り込むこともできます。

### 1. カスタム変数を追加する

Google Tag Manager アカウントにサインインした後、アドビに関連するカスタム定数変数をいくつか追加する必要があります。 Google Tag Manager には、顧客のメールアドレス、顧客名、言語、顧客のログインステータスなど、Google Analytics に送信される変数が既に含まれている可能性があります。 次の 5 つの新しいカスタム変数を定義する必要があります。

* Adobe Experience Cloud 組織 ID
* DCS ストリーミングエンドポイント
* Experience Platform データセット ID
* スキーマ参照
* ページのタイムスタンプ

これらの値を取得することで、すべての Google Analytics データが正しいデータセットに送信され、適切なスキーマを持つようになります。 Experience Cloud 組織や、先ほど説明したその他の変数が不明な場合は、アドビのアカウントマネージャーにお問い合わせください。

これらのカスタム変数を定義したら、既に Google Analytics に送信しているすべてのデータを Experience Platform にも送信するようにトリガーを設定できます。

### 2. Google タグマネージャーでのトリガーの設定

この例では、「アカウントの作成」トリガーが `pageUrl equals account-creation` の条件で定義されています。 このトリガーに情報を追加することで、ユーザーの認証に成功しアカウント作成ページが読み込まれたときに、データが Google Analytics と AEP の両方に確実に送信されます。

また、[データ取り込みと Google タグマネージャー](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=ja#module9)も参照してください。

手順については、次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## CJA での Google Analytics データセットへの接続の作成

Adobe Experience Platform が Google Analytics のライブデータの受信を開始し、BigQuery から Google Analytics の履歴データをバックフィルしたら、CJA に移動して[最初の接続を作成](/help/connections/create-connection.md)する準備が整います。 この接続により、共通の「顧客 ID」を使用して GA データと他のすべての顧客データが結合されます。

## 次の手順

* Google Analytics データを含んだ接続に基づいて、[データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja#cja-dataviews)を作成します。

* [Workspace で驚くべき分析](/help/use-cases/ga-to-cja-reporting.md)をいくつか行います。