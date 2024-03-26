---
title: Customer Journey Analytics での Adobe Analytics レポートスイートデータの使用
description: Adobe Experience Platform および Customer Journey Analytics に取り込むための Adobe Analytics レポートスイートの設定方法
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '847'
ht-degree: 100%

---

# Customer Journey Analytics での Adobe Analytics レポートスイートデータの使用

Adobe Analytics のお客様は、[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を使用することで、Adobe Experience Platform および Customer Journey Analytics で、簡単にレポートスイートを活用できます。その方法について、次に説明します。

>[!IMPORTANT]
>
>複数のレポートスイートにわたるデータ分析を実行するには、**Select** パッケージが必要です。使用している Customer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。

## 準備

Adobe Experience Platform および Customer Journey Analytics で Adobe Analytics レポートスイートの使用を開始する準備が整ったら、Customer Journey Analytics にシームレスに移行するためのデータを準備する際に検討すべき点がいくつかあります。詳しくは、次のページを参照してください。

* [Adobe Analytics から Customer Journey Analytics への進化](/help/getting-started/aa-to-cja.md)

## Adobe Experience Platform および Customer Journey Analytics に取り込むレポートスイートの設定

データの準備が完了したら、Adobe Experience Platform および Customer Journey Analytics で使用するレポートスイートの設定を開始できます。

1. **Adobe Experience Platform および Customer Journey Analytics で使用する各レポートスイートのデータフローを作成します。**[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)は、Adobe Analytics と Adobe Experience Platform の間に[接続を作成](/help/connections/create-connection.md)（データフローとも呼ばれる）するためのツールです。ソースコネクタを使用して、Adobe Experience Platform で使用するレポートスイートごとに 1 つのデータフローを作成します。データフローは、Customer Journey Analytics を含む Adobe Experience Platform アプリケーションで使用するために、スキーマが [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ja) に変換されたレポートスイートデータのコピーを作成します。<p>ソースコネクタを介してデータフローで設定された各レポートスイートは、個別のデータセットとして Adobe Experience Platform データレイクに保存されます。13 か月分の履歴レポートスイートデータが各データフローに自動的に含まれ、新しいデータが継続的に Adobe Experience Platform に送られます。（2023年4月26日（PT）以降、非実稼動用サンドボックスのバックフィルは、3 か月に制限されています）。Analytics ソースコネクタを使用すると、事前にスキーマを作成する必要がなくなります。Adobe Analytics 専用の標準化されたスキーマが自動的に作成されます。ただし、Adobe Experience Platform [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)ツールを使用すると、データがデータレイクに保存されて Customer Journey Analytics で使用できるようになる前に、このスキーマを拡張できます。特定のタイプのデータはソースコネクタによって除外され、Adobe Experience Platform データレイクのデータセットには存在しないことに注意してください。他の行は、データレイクと Customer Journey Analytics の間で除外される場合があります。詳しくは、[Adobe Analytics データと Customer Journey Analytics データの比較](/help/troubleshooting/compare.md)を参照してください。
1. **データ準備を使用すると、Customer Journey Analytics でレポートスイートを組み合わせるのに役立ちます。**&#x200B;データ準備は、様々な種類のデータ変換に使用できます。Adobe Analytics データの一般的な使用方法の 1 つは、複数のレポートスイート間での prop や eVar マッピングの違いを解決し、レポートスイートを Customer Journey Analytics 内で簡単に組み合わせられるようにすることです。詳しくは、[異なるスキーマを使用したレポートスイートの組み合わせ](/help/use-cases/aa-data/combine-report-suites.md)を参照してください。
1. 必要に応じて、**ステッチを有効**&#x200B;にします。Customer Journey Analytics で複数のデータセットを組み合わせる場合、ステッチ機能を使用すると、様々な ID 名前空間を単一のステッチ ID に解決し、デバイスやチャネルをまたいで顧客の単一のビューで利用できます。詳しくは、[ステッチの概要](../../stitching/overview.md)を参照してください。
1. **1 つ以上の Customer Journey Analytics 接続を作成します。**&#x200B;レポートスイートのデータセットを Adobe Experience Platform データレイクで使用できるようになったら、1 つ以上の [Customer Journey Analytics 接続](/help/connections/overview.md)を作成して、これらのデータセットを Customer Journey Analytics に取り込みます。接続内で、レポートスイートのデータを他のタイプのデータと組み合わせ、顧客体験の真のクロスチャネルビューを作成できます。
1. **1 つ以上の Customer Journey Analytics データビューを作成します。**[データビュー](/help/data-views/data-views.md)は、Customer Journey Analytics に特有のコンテナで、Customer Journey Analytics 接続からデータを解釈する方法を決定できます。データビューには多くの強力な[設定オプション](/help/data-views/create-dataview.md)があり、[Analysis Workspace](/help/analysis-workspace/home.md) 内でユーザーに表示するデータをカスタマイズすることができます。

## Customer Journey Analytics と Adobe Analytics の比較

Customer Journey Analytics および Adobe Analytics には多くの類似点があります。例えば、Customer Journey Analytics と Adobe Analytics の両方が、フリーフォームの思考速度分析を行うための Analysis Workspace 機能を提供します。ただし、Customer Journey Analytics は Adobe Experience Platform 内のアプリケーションで、Adobe Experience Platform をデータ取り込みに利用するため、Customer Journey Analytics と Adobe Analytics では、いくつかの重要な点に違いがあります。次の記事は、これらの違いを理解するのに役立ちます。

* [Adobe Analytics データと Customer Journey Analytics データの比較](/help/troubleshooting/compare.md)
* [Customer Journey Analytics の機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Analytics ソースコネクタを通じて渡された Analytics データに関する用語を比較](/help/getting-started/aa-vs-cja/terminology.md)
* [Adobe Analytics と Customer Journey Analytics のレポート機能におけるデータ処理の比較](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [仮想レポートスイート、データビュー、Adobe Experience Platform サンドボックスおよび Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [処理ルール、VISTA および分類とデータ準備の比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
