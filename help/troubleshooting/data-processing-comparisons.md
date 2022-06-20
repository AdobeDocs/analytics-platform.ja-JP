---
title: Adobe Analyticsと CJA のレポート機能間でのデータ処理の比較
description: 様々なレポート機能のデータ処理の違いの理解
source-git-commit: bdb2f09c5c0778640c505557adf8ac82037f9b90
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 21%

---


# Adobe Analyticsと CJA のレポート機能間でのデータ処理の比較

様々なレポート機能のデータ処理の違いを理解すると、どの指標がどこで、なぜ異なるのかを把握するのに役立ちます。

例えば、Adobe Analyticsの指標として「訪問」がデータ処理時に定義され、CJA の指標として「セッション」がレポート時に計算されるので、2 つの指標は CJA データビュー内のセッション定義で使用されるルールに基づいて異なる場合があります。

また、指標としての訪問もセッションも、Analytics ソースコネクタで作成されたデータセットでは使用できないので、比較をおこなうには、クエリロジックでセッションを定義する必要があります。

## 用語 {#terms}

次の表に、Adobe Analyticsと CJA に適用される様々なタイプの処理ロジックの用語を示します。

| 用語 | 定義 | メモ |
| --- | --- | --- |
| 処理時間ロジック | データの処理時に実行され、レポートや分析のために保存されるロジックです。 | このロジックは、履歴データに「組み込まれて」いるので、通常は簡単に変更できません。 |
| レポート時間ロジック | レポートの実行時に実行されるロジックです。 | このロジックは、レポートの実行時に将来のデータと履歴データに非破壊的な方法で適用できます。 |
| ヒットレベルのロジック | 行ごとのレベルで適用されるロジックです。 | 例：処理ルール、VISTA、特定のマーケティングチャネルルール。 |
| 訪問レベルのロジック | 訪問レベルで適用されるロジック。 | 例：訪問とセッションの定義。 |
| 訪問者レベルのロジック | 訪問者レベルで適用されるロジックです。 | 例：クロスデバイス/クロスチャネルの訪問者のステッチ。 |
| セグメント（フィルター）論理 | ヒット/訪問/訪問者（イベント/セッション/人）セグメント（フィルター）ルールの評価。 | 例：赤い靴を買った人。 |
| 計算指標 | セグメントやフィルターを含む複雑な数式に基づく、顧客が作成したカスタム指標の評価。 | 例：赤い靴を購入した人の数。 |
| アトリビューションロジック | アトリビューションを計算するロジック。 | 例：eVarの持続性。 |

{style=&quot;table-layout:auto&quot;}

時間の経過と共に、Adobe AnalyticsとCustomer Journey Analyticsは、レポートの実行時に訪問レベルと訪問者レベルのデータロジックを実行できるようになり、柔軟性が向上しました。

## データ処理のタイプ {#types}

Adobe Analyticsおよび CJA に対して実行されるデータ処理手順とそのタイミングは、Analytics の機能と Analytics の機能とで異なります。 次の表に、各 Analytics 機能のデータ処理のタイプと、データ処理が適用される場合の概要を示します。

| 分析機能 | 処理時に適用 | レポート時に適用 | 利用不可 | メモ |
| --- | --- | --- | --- | --- |
| [コア AA](https://experienceleague.adobe.com/docs/analytics.html?lang=ja) レポート<br/>( レポート時間処理を含むAttribution IQまたは仮想レポートスイートを除く ) | <ul><li>[処理ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=ja)</li><li>[VISTA ルール](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>ヒットレベル [マーケティングチャネルルール](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=ja)</li><li>訪問レベルのマーケティングチャネルルール（注意を参照）</li><li>訪問の定義</li><li>アトリビューションロジック</li></ul> | <ul><li>セグメントのロジック</li><li>計算指標</li></ul> | <ul><li>クロスデバイス分析（注を参照）</li></ul> | <ul><li>CDA では、仮想レポートスイートをレポート時間処理と共に使用する必要があります。</li><li>「訪問レベルのマーケティングチャネルルール」には、次の内容が含まれます。 **訪問の最初のページ**, **ラストタッチチャネルの上書き**、および **マーケティングチャネルの有効期限**. ( [ドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja).)</li></ul> |
| コア AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルルール</li><li>訪問レベルのマーケティングチャネルルール</li><li>訪問の定義</li><li>アトリビューションロジック</li></ul> | <ul><li>セグメントのロジック</li></ul> | <ul><li>計算指標</li><li>クロスデバイス分析</li></ul> |  |
| コア AA [データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルルール</li><li>訪問レベルのマーケティングチャネルルール</li><li>訪問の定義（visitnum フィールド）</li><li>アトリビューションロジック（post 列）</li></ul> |  | <ul><li>セグメントのロジック</li><li>計算指標</li><li>クロスデバイス分析</li></ul> | <ul><li>データフィード内の特定のマーケティングチャネル関連列の ID マッピングは、データフィードには含まれません。 ( [データフィードドキュメント](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja).)</li></ul> |
| コア AA [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 処理ルール</li><li>VISTA ルール</li><ul> |  | <ul><li>ヒットレベルのマーケティングチャネルルール</li><li>訪問レベルのマーケティングチャネルルール</li><li>訪問ロジック</li><li>アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li><li>クロスデバイス分析</li></ul> |  |
| コア AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=ja) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>訪問の定義（注意を参照）</li><li>クロスデバイス分析（注を参照）</li></ul> | <ul><li>ヒットレベルのマーケティングチャネルルール（注意を参照）</li><li>訪問レベルのマーケティングチャネルルール（注意）アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li></ul> |  | <ul><li>CDA では、仮想レポートスイートをレポート時間処理と共に使用する必要があります。</li><li>Core Analytics のAttribution IQは、レポート時に完全に派生したマーケティングチャネル（つまり、派生した中間値）を使用します。</li><li>Attribution IQは、レポート時間処理の VRS で使用される場合を除き、処理時間訪問の定義を使用します。</li></ul> |
| コア AA 仮想レポートスイートの [レポート時間処理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) (VRS RTP) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja)</li></ul> | <ul><li>訪問の定義</li><li>アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li><li>その他の VRS RTP 設定</li></ul> | <ul><li>ヒットレベルのマーケティングチャネルルール</li><li>訪問レベルのマーケティングチャネルルール</li></ul> | <ul><li>VRS RTP を参照 [ドキュメント](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)AEP データレイクのベースのデータセット | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルルール</li><li>フィールドベースのステッチ（注を参照）</li></ul> |  | <ul><li>[訪問レベルのマーケティングチャネルルール](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>訪問ロジック</li><li>アトリビューションロジック</li><li>フィルターロジック</li></ul> | <ul><li>独自のフィルターロジックと計算指標を適用する必要がある</li><li>フィールドベースのステッチでは、Analytics ソースコネクタで作成されたデータセットに加えて、個別のステッチ済みデータセットを作成します。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=ja) レポート | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベル [マーケティングチャネルルール](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[接続設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja)</li><li>フィールドベースのステッチ（注を参照）</li></ul> | <ul><li>セッション定義</li><li>[データビュー設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja)</li><li>アトリビューションロジック</li><li>計算指標</li><li>フィルターロジック</li></ul> | <ul><li>訪問レベルのマーケティングチャネルルール</li></ul> | <ul><li>フィールドベースのステッチを利用するには、ステッチされたデータセットを使用する必要があります。</li></ul> |

{style=&quot;table-layout:auto&quot;}