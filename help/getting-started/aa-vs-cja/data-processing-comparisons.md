---
title: Adobe Analytics と CJA にまたがるレポート機能のデータ処理の比較
description: 様々なレポート機能におけるデータ処理の違いを説明します
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: 80d0b95f3bc3d785d9ca7e4b50aa1bd8440373c2
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 91%

---

# Adobe AnalyticsとCustomer Journey Analyticsでデータ処理を比較する。

<!--

You often need the ability to process data before it is useful for reporting. You can process that data at several stages in the journey that spans from collecting data to generating your report or visualization.

In Adobe Analytics most of that processing of data occurs immediately after collecting the data. Functionalties like VISTA Rules, Processing Rules, Marketing Channels Processing Rules are available to support this **collection-time processing**. 
The data is then stored and at report time you can apply additional processing. For example, break down dimensions, apply segmentation, or  select a different attribution model. This **report-time processing** happens on the fly. 

In Adobe Analytics, report-time processing commonly represents a smaller amount of processing  than what happens at collection-time.

![Adobe Analytics collection-time processing](../assets/aa-processing.png)

In contrast, Customer Journey Analytics (CJA) is designed to require minimal upfront collection-time processing before data being is organized and stored. The underlying architecture of CJA is more designed to work with the stored data at report-time and offers its powerful report-time processing functionality not only in  Workspace but also, even more importantly, through the definition of components in your Data Views. 

![CJA report-time processing](../assets/cja-processing.png)

-->


様々なレポート機能におけるデータ処理の違いを理解することは、どの指標がどこで利用でき、なぜ異なるのかを理解するのに役立ちます。

例えば、Adobe Analytics の指標である「訪問」はデータ処理時に定義され、CJA の指標である「セッション」はレポート時に計算されるので、CJA のデータビュー内でセッション定義に使用されるルールに基づいて、2 つの指標は異なる可能性があります。

また、Analytics ソースコネクタで作成されたデータセットでは、指標として訪問もセッションも利用できないので、比較を行うには、クエリロジックでセッションを定義する必要があります。

## 用語 {#terms}

次の表に、Adobe Analytics と CJA に適用される様々なタイプの処理ロジックの用語の定義を示します。

| 用語 | 定義 | メモ |
| --- | --- | --- |
| 収集時間の処理 | データの収集および処理時に実行され、レポートおよび分析目的で保存される前に実行されるロジックです。 | このロジックは、履歴データに「織り込み済み」で、通常、簡単には変更できません。 |
| レポート時間処理 | レポート実行時に実行されるロジック。 | このロジックは、レポート実行時に未来と履歴のデータに非破壊で適用できます。 |
| ヒットレベルのロジック | 行単位で適用されるロジック。 | 例：処理ルール、VISTA、特定のマーケティングチャネルのルール。 |
| 訪問レベルのロジック | 訪問レベルで適用されるロジック。 | 例：訪問およびセッション定義。 |
| 訪問者レベルのロジック | 訪問者レベルで適用されるロジック。 | 例：クロスデバイス／クロスチャネルの訪問者のステッチ。 |
| セグメント（フィルター）ロジック | ヒット／訪問／訪問者（イベント／セッション／人物）セグメント（フィルター）ルールの評価。 | 例：赤い靴を購入した人物。 |
| 計算指標 | セグメントやフィルターを含む複雑な数式に基づく可能性のある、お客様が作成したカスタム指標の評価。 | 例：赤い靴を購入した人物の数。 |
| アトリビューションロジック | アトリビューションを計算するためのロジック。 | 例：eVar の永続性。 |
| コンポーネント設定 | アトリビューション、動作、形式など、指標やディメンションのカスタマイズを適用する | 例：値のグループ化を使用して、範囲に基づいて数値を組み合わせる |
| カスタムフィールド | 論理は、データビューでのコンポーネントの定義の一部として、スキーマまたは標準フィールドに適用されます。 | 例：新しいマーケティングチャネルディメンションの作成 |

{style="table-layout:auto"}

Adobe Analytics や現在の Customer Journey Analytics は、時間の経過と共に、訪問や訪問者レベルのデータロジックをレポートの実行時に実行できるようになり、その柔軟性が向上しています。

## データ処理のタイプ {#types}

Adobe と CJA に対して実行されるデータ処理の手順とそのタイミングは、Analytics の機能ごとに異なります。次の表に、各 Analytics 機能のデータ処理のタイプと、データ処理が適用されるタイミングの概要を示します。

| 機能 | 処理時に適用 | レポート時に適用 | 使用不可 | メモ |
| --- | --- | --- | --- | --- |
| [コア AA](https://experienceleague.adobe.com/docs/analytics.html?lang=ja)レポート<br/>（レポート時の処理を含む Attribution IQ や仮想レポートスイートを除く） | <ul><li>[処理ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=ja)</li><li>[VISTA ルール](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=ja)</li><li>ヒットレベルの[マーケティングチャネルのルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=ja)</li><li>訪問レベルのマーケティングチャネルのルール（メモを参照）</li><li>訪問定義</li><li>アトリビューションロジック</li></ul> | <ul><li>セグメントのロジック</li><li>計算指標</li></ul> | <ul><li>クロスデバイス分析（メモを参照）</li></ul> | <ul><li>CDA では、レポート時の処理を含む仮想レポートスイートの使用が必要です。</li><li>「訪問レベルのマーケティングチャネルのルール」には、**訪問の最初のページ**、**ラストタッチチャネルを上書き**&#x200B;および&#x200B;**マーケティングチャネルの期限**&#x200B;が含まれます（[ドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja)を参照）。</li></ul> |
| コア AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=ja) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li><li>訪問定義</li><li>アトリビューションロジック</li></ul> | <ul><li>セグメントのロジック</li></ul> | <ul><li>計算指標</li><li>クロスデバイス分析</li></ul> |  |
| コア AA [データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=ja) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li><li>訪問定義（visitnum フィールド）</li><li>アトリビューションロジック（post 列内）</li></ul> |  | <ul><li>セグメントのロジック</li><li>計算指標</li><li>クロスデバイス分析</li></ul> | <ul><li>データフィードの特定のマーケティングチャネル関連列に対する ID マッピングは、データフィードには含まれません（[データフィードのドキュメント](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja)を参照）。</li></ul> |
| コア AA [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 処理ルール</li><li>VISTA ルール</li><ul> |  | <ul><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li><li>訪問ロジック</li><li>アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li><li>クロスデバイス分析</li></ul> |  |
| コア AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=ja) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>訪問定義（メモを参照）</li><li>クロスデバイス分析（メモを参照）</li></ul> | <ul><li>ヒットレベルのマーケティングチャネルのルール（メモを参照）</li><li>訪問レベルのマーケティングチャネルのルール（メモを参照）アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li></ul> |  | <ul><li>CDA では、レポート時の処理を含む仮想レポートスイートの使用が必要です。</li><li>コア Analytics の Attribution IQ は、レポート時に完全に派生されるマーケティングチャネルを使用します（つまり、派生した中央値）。</li><li>Attribution IQ は、レポート時の処理 VRS で使用される場合を除き、処理時の訪問定義を使用します。</li></ul> |
| コア AA [レポート時の処理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)を含む仮想レポートスイート（VRS RTP） | <ul><li>処理ルール</li><li>VISTA ルール</li><li>[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja)</li></ul> | <ul><li>訪問定義</li><li>アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li><li>その他の VRS RTP 設定</li></ul> | <ul><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li></ul> | <ul><li>VRS RTP [ドキュメント](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)を参照してください。</li></ul> |
| AEP データレイクの [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセット | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルのルール</li><li>フィールドベースのステッチ（メモを参照）</li></ul> |  | <ul><li>[訪問レベルのマーケティングチャネルのルール](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja)</li><li>訪問ロジック</li><li>アトリビューションロジック</li><li>フィルターロジック</li></ul> | <ul><li>独自のフィルターロジックおよび計算指標を適用する必要があります</li><li>フィールドベースのステッチでは、Analytics ソースコネクタで作成されたデータセットに加えて、個別のステッチされたデータセットが作成されます。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=ja) レポート | <ul><li>Adobe Experience Platformデータ収集の一部として実装</li></ul> | <ul><li>セッション定義</li><li>[データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja)設定<li>アトリビューションロジック</li><li>計算指標</li><li>フィルターロジック</li></ul> | <ul><li>訪問レベルのマーケティングチャネルのルール</li></ul> | <ul><li>フィールドベースのステッチを活用するためには、ステッチされたデータセットを使用する必要があります。</li></ul> |

{style="table-layout:auto"}
