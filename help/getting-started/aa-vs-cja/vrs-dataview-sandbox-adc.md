---
title: 仮想レポートスイート、データビュー、AEP サンドボックスおよび Analytics ソースコネクタ
description: 仮想レポート環境とサンドボックス環境について説明します。
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 8%

---


# 仮想レポートスイート、データビュー、AEP サンドボックスおよび Analytics ソースコネクタ

Adobeは、仮想レポート環境とサンドボックス環境を作成するための様々な方法を提供します。 次の機能の類似点と相違点、およびこれらの機能と [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja):

* Adobe Analytics仮想レポートスイート
* CJA データビュー
* AEP サンドボックス

## Adobe Analytics仮想レポートスイート (VRS)

詳しくは、以下を参照してください。 [仮想レポートスイートの概要](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ja).

VRS:

* Adobe Analyticsセグメントに基づくことができます。
* 非破壊的な方法で、履歴データと新しいデータの両方に適用できます。
* Adobe Analyticsレポートスイート上に 1 つ以上の仮想ビューを作成し、様々なビジネスチームで使用できるようにします。
* Adobe Analyticsでは、様々な種類のユーザーに対するアクセスを制御し、様々な種類のデータをキュレーションするために使用できます。
* オプション [レポート時間処理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) Adobe Analyticsの機能 この場合、VRS を使用して、「訪問」のカスタム定義を作成できます。
* セグメントの評価と同様に、レポートの実行時に適用されます。 これは _後_ データが収集され、Adobe Analytics内に保存されている。
* 次の場合に必要： [クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja) Adobe Analytics
* は、VRS キュレーションによって、ユーザーに公開される変数を制限できますが、標準の Analytics レポートスイート（250 個の eVar、250 個の prop、1,000 個のイベント）として使用する変数を同数使用できます。
* カスタムカレンダーオプションをサポートします。

仮想レポートスイートは、次のものではありません。

* は、レポートスイートを組み合わせる手段です。
* Adobe AnalyticsData Warehouse。
* Analytics ソースコネクタを介して AEP にデータフローのソースとして使用できます。 完全な（仮想以外の）レポートスイートのみ、Analytics ソースコネクタで使用できます。


## CJA データビュー

詳しくは、以下を参照してください。 [データビューの概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja).

データビュー：

* CJA フィルターに基づいて設定できます。
* 非破壊的な方法で、履歴データと新しいデータの両方に適用できます。
* CJA 接続の上に 1 つ以上の仮想ビューを作成し、異なるビジネスチームで使用できます。
* CJA でのユーザーごとに異なる種類のデータへのアクセスを制御し、キュレーションするために使用できます。
* CJA 接続を通じて CJA に送信されるデータを変換し強化する、強力な非破壊オプションを提供します。
* CJA のレポート時間処理機能に基づいています。
* ユーザーが「セッション」のカスタム定義を作成できるようにします。
* フィルター評価と同様に、レポートの実行時に適用されます。 これは _後_ ソースコネクタ (Adobe Analyticsなど ) が、AEP データレイクのデータセットにデータを書き込み、 _後_ データは、CJA 接続を介して CJA に取り込まれています。
* キュレーションではユーザーに公開される変数を制限できますが、変数の数に制限はありません
* イベント、セッション、ユーザーコンテナのカスタム名を設定できます。
* カスタムカレンダーオプションをサポートします。

データビューには次の機能はありません。

* レポートスイートや他のデータセットを組み合わせる手段を直接提供します。 代わりに、データセットは、CJA 接続でと組み合わされます。 CJA 接続から結合されたデータは、その接続に基づくすべてのデータビューで使用できます。

## AEP サンドボックス

詳しくは、以下を参照してください。 [サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja).

AEP サンドボックス：

* 単一の AEP インスタンスを別々の仮想環境（開発、テスト、ステージング、実稼動など）に分割する手段を提供します。 デジタルエクスペリエンスアプリケーションの開発と発展を支援する。
* は、特定の環境のすべてのデータとアプリケーションを格納するコンテナと考えることができます。

AEP サンドボックスは以下を実行しません。

* 仮想レポートスイート、CJA 接続、またはデータビューと同様の機能を提供します。
* 独自に、他のデータセットと組み合わせるか、他のデータセットと組み合わせます。 ただし、サンドボックス内のデータセットは、CJA 接続内で組み合わせることができます。

 

* 異なるサンドボックスのデータは、CJA 内で結合できません。
* Analytics ソースコネクタは、レポートスイートのデータを送信します _into_ 特定のサンドボックス。 各レポートスイートは、単一のサンドボックスのソースとして設定できます。 詳しくは、 [Analytics ソースコネクタのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) を参照してください。