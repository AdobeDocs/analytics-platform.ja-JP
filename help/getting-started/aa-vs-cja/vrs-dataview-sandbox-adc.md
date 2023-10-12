---
title: 仮想レポートスイート、データビュー、Adobe Experience Platformサンドボックス、Analytics ソースコネクタ
description: 仮想レポート環境とサンドボックス環境について説明します。
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
source-git-commit: 59aabb38ea3e5ba1501ab8da11d14ea2385d8a6b
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 90%

---

# 仮想レポートスイート、データビュー、Adobe Experience Platformサンドボックス、Analytics ソースコネクタ

アドビでは、仮想レポート環境サンドボックス環境を作成するための様々な手段を提供しています。次の機能の類似点と相違点およびこれらの機能が [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)にどのように関連するかを理解する場合に役立ちます。

* Adobe Analytics 仮想レポートスイート
* Customer Journey Analytics データビュー
* Adobe Experience Platform サンドボックス

## Adobe Analytics 仮想レポートスイート

詳しくは、[仮想レポートスイートの概要](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ja)を参照してください。

仮想レポートスイート：

* Adobe Analytics セグメントに基づくことができる。
* 履歴データにも新しいデータにも、非破壊で適用できる。
* 異なるビジネスチームで使用するために、Adobe Analytics レポートスイートの上に 1 つまたは複数の仮想ビューを作成できる。
* Adobe Analytics のユーザーごとに異なる種類のデータへのアクセスを制御し、キュレーションするために使用される可能性がある。
* Adobe Analytics にオプションの[レポート時の処理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)機能を提供する。この場合、「訪問」のカスタム定義を作成するために仮想レポートスイートを使用できます。
* セグメント評価と同様に、レポート実行時に適用される。これは、データが収集され、Adobe Analytics 内に保存された&#x200B;_後_&#x200B;です。
* Adobe Analytics の[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja)に必要。
* 仮想レポートスイートのキュレーションによって、ユーザーに公開される変数を制限できますが、標準の Analytics レポートスイート（250 個の eVar、250 個の prop、1,000 個のイベント）として使用できる変数の数は同じです。
* カスタムカレンダーオプションをサポートする。

仮想レポートスイートに該当しないこと：

* レポートスイートを組み合わせる手段。
* Adobe Analytics Data Warehouse で利用可能。
* Analytics ソースコネクタを介した Adobe Experience Platform へのデータフローのソースとして利用できる。Analytics ソースコネクタで使用できるのは、完全な（非仮想）レポートスイートのみです。


## Customer Journey Analytics データビュー

詳しくは、[データビューの概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja)を参照してください。

データビューに該当すること：

* Customer Journey Analytics フィルターに基づくことができる。
* 履歴データにも新しいデータにも、非破壊で適用できる。
* 異なるビジネスチームで使用するために、Customer Journey Analytics 接続の上に 1 つまたは複数の仮想ビューを作成できる。
* Customer Journey Analytics のユーザーごとに異なる種類のデータへのアクセスを制御し、キュレーションするために使用される可能性がある。
* Customer Journey Analytics 接続を通じて Customer Journey Analytics に取り込まれるデータを変換および強化するための強力な非破壊オプションを提供する。
* Customer Journey Analytics のレポート時の処理機能に基づく。
* 「セッション」のカスタム定義をユーザーが作成できるようにする。
* フィルター評価と同様に、レポート実行時に適用される。これは、ソースコネクタ（Adobe Analytics など）が Adobe Experience Platform データレイク内のデータセットにデータを書き込んだ&#x200B;_後_&#x200B;と、Customer Journey Analytics 接続を介してデータが Customer Journey Analytics に取り込まれた&#x200B;_後_&#x200B;です。
* 変数の数は無制限だが、キュレーションにより、ユーザーに公開する変数を制限できる
* イベント、セッションおよび人物コンテナにカスタムの名前を付けることができる。
* カスタムカレンダーオプションをサポートする。

データビューに該当しないこと：

* レポートスイートや他のデータセットを組み合わせるための手段を直接提供する。代わりに、データセットは Customer Journey Analytics 接続で組み合わされます。Customer Journey Analytics 接続から組み合わされたデータは、その接続に基づくすべてのデータビューで使用できます。

## Adobe Experience Platform サンドボックス

詳しくは、[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)を参照してください。

Adobe Experience Platform サンドボックスに該当すること：

* 単一の Adobe Experience Platform インスタンスを別々の仮想環境（開発、テスト、ステージ、実稼動など）に分割する手段を提供する。デジタルエクスペリエンスアプリケーションの開発と発展を支援する。
* 所定の環境のすべてのデータとアプリケーションを保持するコンテナと考えることができる。

Adobe Experience Platform サンドボックスに該当しないこと：

* 仮想レポートスイート、Customer Journey Analytics 接続またはデータビューと同様の機能を提供する。
* そのままで、レポートスイートを他のデータセットと組み合わせたり、レポートスイートを他のデータセットなしで組み合わせたりする。ただし、サンドボックス内のデータセットは、Customer Journey Analytics 接続内で組み合わせることができます。

メモ：

* 異なるサンドボックスからのデータを Customer Journey Analytics 内で組み合わせることはできません。
* Analytics ソースコネクタは、レポートスイートデータを特定のサンドボックス&#x200B;_に_&#x200B;送信します。各レポートスイートは、単一のサンドボックスのソースとして設定できます。詳しくは、[Analytics ソースコネクタのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を参照してください。
