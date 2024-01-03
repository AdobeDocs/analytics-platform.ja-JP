---
title: Adobe Analytics と Customer Journey Analytics のレポート機能におけるデータ処理の比較
description: 様々なレポート機能におけるデータ処理の違いを理解する
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 100%

---

# Adobe Analytics と Customer Journey Analytics におけるデータ処理の比較

データをレポートで活用する前に、データを処理する機能が必要になる場合がよくあります。データの収集からレポートやビジュアライゼーションの生成に至るまで、ジャーニーの複数の段階でそのデータを処理できます。

Adobe Analytics では、データの処理のほとんどは、データの収集直後に行われます。この&#x200B;**収集時の処理**をサポートするには、VISTA ルール、処理ルール、マーケティングチャネル処理ルールなどの機能を使用できます。
その後、データは保存され、レポート時に追加の処理を適用できます。例えば、ディメンションの分類、セグメント化の適用、別のアトリビューションモデルの選択などを行うことができます。この**レポート時の処理**&#x200B;はその場で行われます。

Adobe Analytics では、通常、レポート時の処理は、収集時に発生する処理量よりも少ない処理量を表します。

![Adobe Analytics の収集時の処理](../assets/aa-processing.png)

これに対し、Customer Journey Analytics は、データを整理して保存する前に、収集時の事前処理を最小限に抑えるように設計されています。Customer Journey Analytics の基盤となるアーキテクチャは、レポート時に保存されたデータを操作するように設計されており、Workspace だけでなく、さらに重要なことに、データビューでの[コンポーネント](/help/data-views/component-settings/overview.md)と[派生フィールド](/help/data-views/derived-fields/derived-fields.md)の定義を通じて、強力なレポート時の処理機能を提供します。

![Customer Journey Analytics のレポート時の処理](../assets/cja-processing.png)

様々なレポート機能におけるデータ処理の違いを理解することは、どの指標がどこで利用でき、なぜ異なるのかを理解するのに役立ちます。

例えば、Adobe Analytics の指標としての「訪問数」はデータ処理時に定義され、Customer Journey Analytics の指標としての「セッション数」はレポート時に計算されるので、2 つの指標は Customer Journey Analytics データビュー内のセッション定義に使用されるルールに基づいて異なる場合があります。

また、Analytics ソースコネクタで作成されたデータセットでは、指標として訪問数もセッション数も使用できないので、比較を行うには、クエリロジックでセッションを定義する必要があります。

## 用語 {#terms}

次の表に、Adobe Analytics と Customer Journey Analytics に適用される様々なタイプの処理ロジックの用語の定義を示します。

| 用語 | 定義 | メモ |
| --- | --- | --- |
| 収集時の処理 | レポートや分析の目的で保存される前に、データ収集時および処理時に実行されるロジック。 | このロジックは、履歴データに「織り込み済み」で、通常、簡単には変更できません。 |
| レポート時の処理 | レポート実行時に実行されるロジック。 | このロジックは、レポート実行時に未来と履歴のデータに非破壊で適用できます。 |
| ヒットレベルのロジック | 行単位で適用されるロジック。 | 例：処理ルール、VISTA、特定のマーケティングチャネルのルール。 |
| 訪問レベルのロジック | 訪問レベルで適用されるロジック。 | 例：訪問およびセッション定義。 |
| 訪問者レベルのロジック | ユーザーレベルで適用されるロジック。 | 例：クロスデバイス／クロスチャネルのユーザーのステッチ。 |
| セグメント（フィルター）ロジック | イベント／訪問／ユーザー（イベント／セッション／ユーザー）セグメント（フィルター）ルールの評価。 | 例：赤い靴を購入した人物。 |
| 計算指標 | セグメントやフィルターを含む複雑な数式に基づく可能性のある、お客様が作成したカスタム指標の評価。 | 例：赤い靴を購入した人物の数。 |
| アトリビューションロジック | アトリビューションを計算するためのロジック。 | 例：eVar の永続性。 |
| コンポーネント設定 | アトリビューション、動作、形式など、指標やディメンションへのカスタマイズの適用 | 例：範囲に基づいて数値を組み合わせる値のバケット化 |
| 派生フィールド | データビューでのコンポーネント定義の一部としてスキーマまたは標準フィールドに適用されるロジック。 | 例：新しいマーケティングチャネルディメンションの作成 |

{style="table-layout:auto"}

Adobe Analytics や現在の Customer Journey Analytics は、時間の経過と共に、訪問やユーザーレベルのデータロジックをレポートの実行時に実行できるようになり、その柔軟性が向上しています。

## データ処理のタイプ {#types}

Adobe Analytics と Customer Journey Analytics に対して実行されるデータ処理の手順とそのタイミングは、Analytics の機能ごとに異なります。次の表に、各 Analytics 機能のデータ処理のタイプと、データ処理が適用されるタイミングの概要を示します。

| 機能 | 処理時に適用 | レポート時に適用 | 使用不可 | メモ |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=ja) レポート<br/>（レポート時の処理を含む Attribution IQ や仮想レポートスイートを除く） | <ul><li>[処理ルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=ja)</li><li>[VISTA ルール](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=ja)</li><li>ヒットレベルの[マーケティングチャネルのルール](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=ja)</li><li>訪問レベルのマーケティングチャネルのルール（メモを参照）</li><li>訪問定義</li><li>アトリビューションロジック</li></ul> | <ul><li>セグメントのロジック</li><li>計算指標</li></ul> | <ul><li>クロスデバイス分析（メモを参照）</li></ul> | <ul><li>CDA では、レポート時の処理を含む仮想レポートスイートの使用が必要です。</li><li>「訪問レベルのマーケティングチャネルのルール」には、**訪問の最初のページ**、**ラストタッチチャネルを上書き**&#x200B;および&#x200B;**マーケティングチャネルの期限**&#x200B;が含まれます（[ドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja)を参照）。</li></ul> |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=ja) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li><li>訪問定義</li><li>アトリビューションロジック</li></ul> | <ul><li>セグメントのロジック</li></ul> | <ul><li>計算指標</li><li>クロスデバイス分析</li></ul> |     |
| Adobe Analytics [データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=ja) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li><li>訪問定義（visitnum フィールド）</li><li>アトリビューションロジック（post 列内）</li></ul> |   | <ul><li>セグメントのロジック</li><li>計算指標</li><li>クロスデバイス分析</li></ul> | <ul><li>データフィードの特定のマーケティングチャネル関連列に対する ID マッピングは、データフィードには含まれません（[データフィードのドキュメント](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja)を参照）。</li></ul> |
| Adobe Analytics [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 処理ルール</li><li>VISTA ルール</li><ul> |   | <ul><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li><li>訪問ロジック</li><li>アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li><li>クロスデバイス分析</li></ul> |  |
| Adobe Analytics [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=ja) | <ul><li>処理ルール</li><li>VISTA ルール</li><li>訪問定義（メモを参照）</li><li>クロスデバイス分析（メモを参照）</li></ul> | <ul><li>ヒットレベルのマーケティングチャネルのルール（メモを参照）</li><li>訪問レベルのマーケティングチャネルのルール（メモを参照）アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li></ul> |  | <ul><li>CDA では、レポート時の処理を含む仮想レポートスイートの使用が必要です。</li><li>コア Analytics の Attribution IQ は、レポート時に完全に派生されるマーケティングチャネルを使用します（つまり、派生した中央値）。</li><li>Attribution IQ は、レポート時の処理仮想レポートスイートで使用される場合を除き、処理時の訪問定義を使用します。</li></ul> |
| [レポート時の処理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)を含む Adobe Analytics 仮想レポートスイート | <ul><li>処理ルール</li><li>VISTA ルール</li><li>[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja)</li></ul> | <ul><li>訪問定義</li><li>アトリビューションロジック</li><li>セグメントのロジック</li><li>計算指標</li><li>その他の仮想レポートスイートのレポート時の処理設定</li></ul> | <ul><li>ヒットレベルのマーケティングチャネルのルール</li><li>訪問レベルのマーケティングチャネルのルール</li></ul> | <ul><li>仮想レポートスイートのレポート時の処理の[ドキュメント](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)を参照してください。</li></ul> |
| Adobe Experience Platform データレイクの [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセット | <ul><li>処理ルール</li><li>VISTA ルール</li><li>ヒットレベルのマーケティングチャネルのルール</li><li>フィールドベースのステッチ（メモを参照）</li></ul> |   | <ul><li>[訪問レベルのマーケティングチャネルのルール](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja)</li><li>訪問ロジック</li><li>アトリビューションロジック</li><li>フィルターロジック</li></ul> | <ul><li>独自のフィルターロジックおよび計算指標を適用する必要があります</li><li>フィールドベースのステッチでは、Analytics ソースコネクタで作成されたデータセットに加えて、個別のステッチされたデータセットが作成されます。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=ja) レポート | <ul><li>Adobe Experience Platform データ収集の一部として実装</li></ul> | <ul><li>セッション定義</li><li>[データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ja)設定<li>アトリビューションロジック</li><li>計算指標</li><li>フィルターロジック</li></ul> | <ul><li>訪問レベルのマーケティングチャネルのルール</li></ul> | <ul><li>クロスチャネル分析を活用するには、ステッチされたデータセットを使用する必要があります。</li></ul> |

{style="table-layout:auto"}
