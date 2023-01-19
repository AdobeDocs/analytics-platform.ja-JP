---
title: Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用
description: AEP および CJA に取り込むための Adobe Analytics レポートスイートの設定方法
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: ht
source-wordcount: '767'
ht-degree: 100%

---

# Customer Journey Analytics での Adobe Analytics レポートスイートデータの利用

Adobe Analytics のお客様は、[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を使用することで、Adobe Experience Platform および Customer Journey Analytics で、簡単にレポートスイートを活用できます。その方法について、次に説明します。

## 準備

AEP および CJA で Adobe Analytics レポートスイートの使用を開始する準備が整ったら、Customer Journey Analytics にシームレスに移行するためのデータを準備する際に検討すべき点がいくつかあります。詳しくは、次のページを参照してください。

* [Adobe Analytics から Customer Journey Analytics への進化](/help/getting-started/aa-to-cja.md)

## Adobe Experience Platform および CJA に取り込むレポートスイートの設定

データの準備が完了したら、AEP および CJA で使用するレポートスイートの設定を開始できます。

1. **AEP および CJA で使用する各レポートスイートのデータフローを作成します。**[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)は、Adobe Analytics と AEP の間に[接続を作成](/help/connections/create-connection.md)（データフローとも呼ばれる）するためのツールです。ソースコネクタを使用して、AEP で使用するレポートスイートごとに 1 つのデータフローを作成します。データフローは、CJA を含む AEP アプリケーションで使用するために、スキーマが [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ja) に変換されたレポートスイートデータのコピーを作成します。ソースコネクタを介してデータフローで設定された各レポートスイートは、個別のデータセットとして AEP データレイクに保存されます。13 か月分の履歴レポートスイートデータが各データフローに自動的に含まれ、新しいデータが継続的に AEP に送られます。Analytics ソースコネクタを使用すると、事前にスキーマを作成する必要がなくなります。 Adobe Analytics 専用の標準化されたスキーマが自動的に作成されます。ただし、AEP の[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)ツールを使用すると、データがデータレイクに保存されて CJA で使用できるようになる前に、このスキーマを拡張できます。特定のタイプのデータはソースコネクタによって除外され、AEP データレイクのデータセットには存在しないことに注意してください。他の行は、データレイクと CJA の間で除外される場合があります。詳しくは、[Adobe Analytics データと CJA データの比較](/help/troubleshooting/compare.md)を参照してください。
1. **データ準備を使用すると、CJA でレポートスイートを組み合わせるのに役立ちます。**&#x200B;データ準備は、様々な種類のデータ変換に使用できます。Adobe Analytics データの一般的な使用方法の 1 つは、複数のレポートスイート間での prop や eVar マッピングの違いを解決し、レポートスイートを CJA 内で簡単に組み合わせられるようにすることです。詳しくは、[異なるスキーマを使用したレポートスイートの組み合わせ](/help/use-cases/aa-data/combine-report-suites.md)を参照してください。
1. 必要に応じて&#x200B;**Cross-Channel Analytics を有効化**&#x200B;します。 CJA で複数のデータセットを組み合わせる場合、Cross-Channel Analytics の ID ステッチ機能を使用すると、様々な ID 名前空間を単一の stitchedID に解決し、デバイスやチャネルをまたいで顧客の単一のビューで利用できます。詳しくは、[Cross-Channel Analytics の概要](/help/cca/overview.md)を参照してください。
1. **1 つ以上の CJA 接続を作成します。**&#x200B;レポートスイートのデータセットを AEP データレイクで使用できるようになったら、1 つ以上の [CJA 接続](/help/connections/overview.md)を作成して、これらのデータセットを CJA に取り込みます。接続内で、レポートスイートのデータを他のタイプのデータと組み合わせ、顧客体験の真のクロスチャネルビューを作成できます。
1. **1 つ以上の CJA データビューを作成します。**[データビュー](/help/data-views/data-views.md)は、Customer Journey Analytics に特有のコンテナで、CJA 接続からデータを解釈する方法を決定できます。データビューには多くの強力な[設定オプション](/help/data-views/create-dataview.md)があり、[Analysis Workspace](/help/analysis-workspace/home.md) 内でユーザーに表示するデータをカスタマイズすることができます。

## Customer Journey Analytics と Adobe Analytics の比較

Customer Journey Analytics および Adobe Analytics には多くの類似点があります。例えば、CJA と Adobe Analytics の両方が、フリーフォームの思考速度分析を行うための Analysis Workspace 機能を提供します。ただし、CJA は Adobe Experience Platform 内のアプリケーションで、AEP をデータ取り込みに利用するため、CJA と Adobe Analytics はいくつかの重要な点において違いがあります。次の記事は、これらの違いを理解するのに役立ちます。

* [Adobe Analytics データと CJA データの比較](/help/troubleshooting/compare.md)
* [Customer Journey Analytics の機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Analytics ソースコネクタを通じて渡された Analytics データに関する用語の比較](/help/getting-started/aa-vs-cja/terminology.md)
* [Adobe Analytics と CJA にまたがるレポート機能のデータ処理の比較](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [仮想レポートスイート、データビュー、AEP サンドボックスおよび Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [処理ルール、VISTA および分類とデータ準備の比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
