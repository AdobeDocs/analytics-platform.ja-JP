---
title: Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用
description: Adobe Experience PlatformとCustomer Journey Analyticsに取り込むためのAdobe Analyticsレポートスイートの設定方法
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 29%

---

# Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用

Adobe Analytics のお客様は、[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を使用することで、Adobe Experience Platform および Customer Journey Analytics で、簡単にレポートスイートを活用できます。その方法について、次に説明します。

## 準備

Adobe Experience PlatformおよびCustomer Journey AnalyticsでAdobe Analyticsレポートスイートの使用を開始する準備が整ったら、Customer Journey Analyticsにシームレスに移行するためにデータを準備する際に検討する必要がある点がいくつかあります。 詳しくは、次のページを参照してください。

* [Adobe Analytics から Customer Journey Analytics への進化](/help/getting-started/aa-to-cja.md)

## Adobe Experience PlatformおよびCustomer Journey Analyticsに取り込むためのレポートスイートの設定

データの準備が完了したら、Adobe Experience PlatformおよびCustomer Journey Analyticsで使用するレポートスイートの設定を開始する準備が整いました。

1. **Adobe Experience PlatformとCustomer Journey Analyticsで使用する各レポートスイートのデータフローを作成します。** この [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja) は、次の操作を行うためのツールです。 [接続の作成](/help/connections/create-connection.md) Adobe AnalyticsとAdobe Experience Platformの間の（データフローと呼ばれる） ソースコネクタを使用して、Adobe Experience Platformで使用するレポートスイートごとに 1 つのデータフローを作成します。 データフローは、スキーマが変換されたレポートスイートデータのコピーを作成します。  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ja) Customer Journey Analyticsを含むAdobe Experience Platformアプリケーションでの消費に対して<p>ソースコネクタを介してデータフローで設定された各レポートスイートは、別のデータセットとしてAdobe Experience Platform Data Lake に保存されます。 13 か月分の履歴レポートスイートデータが各データフローに自動的に含まれ、新しいデータが継続的にAdobe Experience Platformに送られます。 （2023 年 4 月 26 日以降、非実稼動用サンドボックスのバックフィルは、3 か月に制限されています）。 Analytics ソースコネクタを使用すると、事前にスキーマを作成する必要がなくなります。 Adobe Analytics 専用の標準化されたスキーマが自動的に作成されます。しかし、Adobe Experience Platform [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) ツールを使用して、データレイクにデータを保存してCustomer Journey Analyticsで使用できるようにする前に、このスキーマを拡張できます。 特定のタイプのデータはソースコネクタによって除外され、Adobe Experience Platform Data Lake のデータセットには存在しないことに注意してください。 その他の行は、データレイクとCustomer Journey Analyticsの間で除外できます。 詳しくは、 [Adobe AnalyticsデータとCustomer Journey Analyticsデータの比較](/help/troubleshooting/compare.md) を参照してください。
1. **Data Prep を使用すると、レポートスイートを組み合わせてCustomer Journey Analyticsできます。** Adobe AnalyticseVarは、様々な種類のデータ変換に使用できます。また、Data Prep の一般的な使用方法の 1 つは、複数のレポートスイート間での prop やデータマッピングの違いを解決し、Customer Journey Analytics内でレポートスイートを簡単に組み合わせられるようにすることです。 詳しくは、[異なるスキーマを使用したレポートスイートの組み合わせ](/help/use-cases/aa-data/combine-report-suites.md)を参照してください。
1. **ステッチを有効にする** 必要に応じて。 Customer Journey Analyticsで複数のデータセットを組み合わせる場合、ステッチ機能を使用して、デバイスやチャネルをまたいで顧客の単一のビューに対して、様々な ID 名前空間を単一のステッチ ID に解決できます。 詳しくは、 [ステッチの概要](../../stitching/overview.md) を参照してください。
1. **1 つ以上のCustomer Journey Analytics接続を作成** レポートスイートのデータセットをAdobe Experience Platform Data Lake で使用できるようになったら、1 つ以上の [Customer Journey Analytics接続](/help/connections/overview.md) を使用して、これらのデータセットをCustomer Journey Analyticsに取り込みます。 接続内で、レポートスイートのデータを他のタイプのデータと組み合わせ、顧客体験の真のクロスチャネルビューを作成できます。
1. **1 つ以上のCustomer Journey Analyticsデータビューを作成します。** A [データビュー](/help/data-views/data-views.md) は、Customer Journey Analytics接続からのデータの解釈方法を決定できる、Customer Journey Analytics固有のコンテナです。 データビューには多くの強力な[設定オプション](/help/data-views/create-dataview.md)があり、[Analysis Workspace](/help/analysis-workspace/home.md) 内でユーザーに表示するデータをカスタマイズすることができます。

## Customer Journey Analytics と Adobe Analytics の比較

Customer Journey Analytics および Adobe Analytics には多くの類似点があります。例えば、Customer Journey AnalyticsとAdobe Analyticsの両方が、フリーフォームの思考速度を分析するAnalysis Workspaceの機能を提供します。 ただし、Customer Journey AnalyticsはAdobe Experience Platform内のアプリケーションで、データ取り込みにAdobe Experience Platformを利用するので、Customer Journey AnalyticsとAdobe Analyticsは多くの重要な方法で異なります。 次の記事は、これらの違いを理解するのに役立ちます。

* [Adobe AnalyticsデータとCustomer Journey Analyticsデータの比較](/help/troubleshooting/compare.md)
* [Customer Journey Analytics の機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Analytics ソースコネクタを通じて渡された Analytics データに関する用語の比較](/help/getting-started/aa-vs-cja/terminology.md)
* [Adobe AnalyticsとCustomer Journey Analyticsのレポート機能でデータ処理を比較する](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [仮想レポートスイート、データビュー、Adobe Experience Platformサンドボックス、Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [処理ルール、VISTA および分類とデータ準備の比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
