---
title: Customer Journey AnalyticsでのAdobe Analyticsレポートスイートデータの利用
description: AEP および CJA に取り込むためのAdobe Analyticsレポートスイートの設定方法
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 13%

---

# Customer Journey AnalyticsでのAdobe Analyticsレポートスイートデータの利用

Adobe Analyticsのお客様は、 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja). 以下では、その方法について説明します。

## 準備

AEP および CJA でAdobe Analyticsレポートスイートの使用を開始する準備が整ったら、Customer Journey Analyticsにシームレスに移行するためにデータを準備する際に検討する必要がある点がいくつかあります。 詳しくは、次のページを参照してください。

* [Adobe Analytics から Customer Journey Analytics への進化](/help/getting-started/aa-to-cja.md)

## Adobe Experience Platformおよび CJA に取り込むためのレポートスイートの設定

データの準備が完了したら、AEP および CJA で使用するレポートスイートの設定を開始する準備が整います。

1. **AEP および CJA で使用する各レポートスイートのデータフローを作成します。** この [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) は、次の操作を行うためのツールです。 [接続の作成](/help/connections/create-connection.md) （データフローと呼ばれる）Adobe Analyticsと AEP の間。 ソースコネクタを使用して、AEP で使用するレポートスイートごとに 1 つのデータフローを作成します。 データフローは、スキーマが変換されたレポートスイートデータのコピーを作成します。  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ja) CJA を含む AEP アプリケーションでの使用に関する情報です。 ソースコネクタを介してデータフローで設定された各レポートスイートは、個別のデータセットとして AEP データレイクに保存されます。 13 か月分の履歴レポートスイートデータが各データフローに自動的に含まれ、新しいデータが継続的に AEP に送られます。 Analytics ソースコネクタを使用すると、事前にスキーマを作成することを気にする必要がなくなります。 Adobe Analytics専用の標準化されたスキーマが自動的に作成されます。 ただし、AEP の [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) ツールを使用して、データがデータレイクに保存されて CJA で使用できるようになる前に、このスキーマを拡張できます。 特定のタイプのデータはソースコネクタによって除外され、AEP データレイクのデータセットには存在しないことに注意してください。 他の行は、データレイクと CJA の間で除外される場合があります。 詳しくは、 [Adobe Analyticsデータと CJA データの比較](/help/troubleshooting/compare.md) を参照してください。
1. **データ準備を使用すると、CJA でレポートスイートを組み合わせるのに役立ちます。** Data Prep は様々な種類のeVar変換に使用できます。Adobe Analyticsデータの一般的な使用方法の 1 つは、複数のレポートスイート間での prop やデータマッピングの違いを解決し、レポートスイートを CJA 内で簡単に組み合わせられるようにすることです。 詳しくは、 [異なるスキーマでレポートスイートを組み合わせる](/help/use-cases/aa-data/combine-report-suites.md) を参照してください。
1. **クロスチャネル分析の有効化** 必要に応じて。 CJA で複数のデータセットを組み合わせる場合、クロスチャネル分析の ID ステッチ機能を使用すると、様々な ID 名前空間を単一の stetchedID に解決し、デバイスやチャネルをまたいで顧客の単一のビューで利用できます。 詳しくは、 [クロスチャネル分析の概要](/help/connections/cca/overview.md) を参照してください。
1. **1 つ以上の CJA 接続を作成します。** レポートスイートのデータセットを AEP データレイクで使用できるようになったら、1 つ以上のデータセットを作成できます [CJA 接続](/help/connections/overview.md) を使用して、これらのデータセットを CJA に取り込みます。 接続内で、レポートスイートのデータを他のタイプのデータと組み合わせ、顧客体験の真のクロスチャネル表示を作成できます。
1. **1 つ以上の CJA データビューを作成します。** A [データビュー](/help/data-views/data-views.md) は、CJA 接続からのCustomer Journey Analyticsの解釈方法を決定するための、データに固有のコンテナです。 データビューには多くの強力な機能があります [設定オプション](/help/data-views/create-dataview.md) ユーザーに表示されるデータを [Analysis Workspace](/help/analysis-workspace/home.md).

## Customer Journey AnalyticsとAdobe Analyticsの比較

Customer Journey AnalyticsとAdobe Analyticsには多くの類似点があります。 例えば、CJA とAdobe Analyticsの両方が、フリーフォームの思考速度を分析するAnalysis Workspaceの機能を提供します。 ただし、CJA はAdobe Experience Platform内のアプリケーションで、AEP をデータ取り込みに利用するので、CJA とAdobe Analyticsは多くの重要な方法で異なります。 次の記事は、これらの違いを理解するのに役立ちます。

* [Adobe Analytics データと CJA データの比較](/help/troubleshooting/compare.md)
* [Customer Journey Analytics の機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Analytics ソースコネクタを通じて渡された Analytics データに関する用語の比較](/help/getting-started/aa-vs-cja/terminology.md)
* [Adobe Analytics と CJA にまたがるレポート機能のデータ処理の比較](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [仮想レポートスイート、データビュー、AEP サンドボックスおよび Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [処理ルール、VISTA および分類とデータ準備の比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
