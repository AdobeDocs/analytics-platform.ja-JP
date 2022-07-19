---
title: 仮想レポートスイート、データビュー、AEP サンドボックスおよび Analytics ソースコネクタ
description: 仮想レポート環境とサンドボックス環境について説明します。
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: 6603aed778980c37d69843f11f3ee64e64cd13b5
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 99%

---

# 仮想レポートスイート、データビュー、AEP サンドボックスおよび Analytics ソースコネクタ

アドビでは、仮想レポート環境サンドボックス環境を作成するための様々な手段を提供しています。次の機能の類似点と相違点、およびこれらの機能が [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)にどのように関連するかを把握することは有益です。

* Adobe Analytics 仮想レポートスイート
* CJA データビュー
* AEP サンドボックス

## Adobe Analytics 仮想レポートスイート（VRS）

詳しくは、[仮想レポートスイートの概要](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ja)を参照してください。

仮想レポートスイート：

* Adobe Analytics セグメントに基づくことができる。
* 履歴データにも新しいデータにも、非破壊で適用できる。
* 異なるビジネスチームで使用するために、Adobe Analytics レポートスイートの上に 1 つまたは複数の仮想ビューを作成できる。
* Adobe Analytics のユーザーごとに異なる種類のデータへのアクセスを制御し、キュレーションするために使用される可能性がある。
* Adobe Analytics にオプションの[レポート時の処理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)機能を提供する。この場合、VRS は、「訪問」のカスタム定義を作成するために使用されることがあります。
* セグメント評価と同様に、レポート実行時に適用される。これは、データが収集され、Adobe Analytics 内に保存された&#x200B;_後_&#x200B;です。
* Adobe Analytics の[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja)に必要。
* 標準の Analytics レポートスイート（250 eVar、250 prop、1000 イベント）と同じ数の変数を使用できるが、VRS のキュレーションによって、ユーザーに公開する変数を制限できる。
* カスタムカレンダーオプションをサポートする。

仮想レポートスイートに該当しないこと：

* レポートスイートを組み合わせる手段。
* Adobe Analytics Data Warehouse で利用可能。
* Analytics ソースコネクタを介した AEP へのデータフローのソースとして利用できる。Analytics ソースコネクタで使用できるのは、完全な（非仮想）レポートスイートのみです。


## CJA データビュー

詳しくは、[データビューの概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja)を参照してください。

データビューに該当すること：

* CJA フィルターに基づくことができる。
* 履歴データにも新しいデータにも、非破壊で適用できる。
* 異なるビジネスチームで使用するために、CJA 接続の上に 1 つまたは複数の仮想ビューを作成できる。
* CJA のユーザーごとに異なる種類のデータへのアクセスを制御し、キュレーションするために使用される可能性がある。
* CJA 接続を使用して CJA に取り込まれたデータを変換および強化するための強力な非破壊オプションを提供する。
* CJA のレポート時の処理機能に基づく。
* 「セッション」のカスタム定義をユーザーが作成できるようにする。
* フィルター評価と同様に、レポート実行時に適用される。これは、ソースコネクタ（Adobe Analytics またはその他）が AEP データレイク内のデータセットにデータを書き込んだ&#x200B;_後_、およびそのデータが CJA 接続を介して CJA に取り込まれた&#x200B;_後_&#x200B;です。
* 変数の数は無制限だが、キュレーションにより、ユーザーに公開する変数を制限できる
* イベント、セッションおよび人物コンテナにカスタムの名前を付けることができる。
* カスタムカレンダーオプションをサポートする。

データビューに該当しないこと：

* レポートスイートや他のデータセットを組み合わせるための手段を直接提供する。代わりに、データセットは、CJA 接続で組み合わされます。CJA 接続で組み合わされたデータは、その接続に基づくすべてのデータビューで使用できます。

## AEP サンドボックス

詳しくは、[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)を参照してください。

AEP サンドボックスに該当すること：

* 単一の AEP インスタンスを別々の仮想環境（開発、テスト、ステージ、実稼動など）に分割する手段を提供して、デジタルエクスペリエンスアプリケーションの開発と発展を支援する。
* 所定の環境のすべてのデータとアプリケーションを保持するコンテナと考えることができる。

AEP サンドボックスに該当しないこと：

* 仮想レポートスイート、CJA 接続またはデータビューと同等の機能を提供する。
* そのままで、レポートスイートを他のデータセットと組み合わせたり、レポートスイートを他のデータセットなしで組み合わせたりする。ただし、サンドボックス内のデータセットは、CJA 接続内で組み合わせることができます。

メモ：

* CJA 内では、異なるサンドボックスのデータを組み合わせることはできません。
* Analytics ソースコネクタは、レポートスイートデータを特定のサンドボックス&#x200B;_に_&#x200B;送信します。各レポートスイートは、単一のサンドボックスのソースとして設定できます。詳しくは、[Analytics ソースコネクタのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en)を参照してください。
