---
git-repo: https://github.com/AdobeDocs/analytics-platform.ja-JP
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics ガイド
user-guide-description: Adobe Customer Journey Analytics と、Experience Platform のデータを使った Analysis Workspace の使用方法について説明します。
breadcrumb-title: Customer Journey Analytics ガイド
source-git-commit: eacb6eeaeadce7dfe39e6fb67eaba76986078363
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 84%

---


# Adobe Customer Journey Analyticsガイド {#using}

+ [Adobe Customer Journey Analyticsガイド](../getting-started/cja-landing.md)

+ リリースノート {#releases}
   + [最新リリース](../release-notes/latest.md)
   + [2023年リリース](../release-notes/2023.md)
   + [2022年リリース](../release-notes/2022.md)
   + [2021年リリース](../release-notes/2021.md)
   + [2020年リリース](../release-notes/2020.md)
   + [Customer Journey Analyticsリリース](../release-notes/releases.md)
   + [Customer Journey Analytics ドキュメントのアップデート](../release-notes/doc-changes.md)

+ はじめに {#cja-overview}
   + [Customer Journey Analytics の概要](../getting-started/cja-overview.md)
   + [クイックスタートガイド](../getting-started/cja-getting-started.md)
   + [ランディングページ](../getting-started/landing.md)
   + [よくある質問](../getting-started/cja-faq.md)
   + [Customer Journey Analytics と BI ソリューションの比較](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics と Adobe Analytics {#compare-aa-cja}
   + [Adobe Analytics からの進化](../getting-started/aa-to-cja.md)
   + [Adobe Analytics ユーザー向けユーザーガイド](../getting-started/aa-to-cja-user.md)
   + Adobe Analytics との比較 {#cja-aa-comparison}
      + [Adobe Analytics データの Customer Journey Analytics での活用](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Customer Journey Analytics の機能のサポート](../getting-started/aa-vs-cja/cja-aa.md)
      + [Analytics ソースコネクタを通じて渡された Analytics データに関する用語の比較](../getting-started/aa-vs-cja/terminology.md)
      + [Adobe AnalyticsとCustomer Journey Analyticsでのデータ処理の比較](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [仮想レポート環境とサンドボックス環境](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [処理ルール、VISTA および分類とデータ準備の比較](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ データ取り込み {#cja-data-ingestion}
   + [データ取り込みの概要](../data-ingestion/data-ingestion.md)
   + 取り込みと使用のクイックスタートガイド{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + [Adobe Experience Platform Web SDK および Edge ネットワーク](../data-ingestion/aepwebsdk.md)
      + [バッチデータ](../data-ingestion/batch.md)
      + [ストリーミングデータ](../data-ingestion/streaming.md)
      + [ソースコネクタ](../data-ingestion/sources.md)

+ 接続 {#cja-connections}
   + [接続の概要](../connections/overview.md)
   + [接続の作成](../connections/create-connection.md)
   + [接続の管理](../connections/manage-connections.md)
   + [組み合わせイベントデータセット](../connections/combined-dataset.md)
   + [標準検索](../connections/standard-lookups.md)
   + [クロスチャネル分析](../connections/cca.md)

+ データビュー {#cja-dataviews}
   + [データビューの概要](../data-views/data-views.md)
   + [データビューの作成または編集](../data-views/create-dataview.md)
   + コンポーネント設定 {#component-settings}
      + [コンポーネント設定の概要](../data-views/component-settings/overview.md)
      + [アトリビューション](../data-views/component-settings/attribution.md)
      + [動作](../data-views/component-settings/behavior.md)
      + [形式](../data-views/component-settings/format.md)
      + [値を含める / 除外](../data-views/component-settings/include-exclude-values.md)
      + [指標の重複排除](../data-views/component-settings/metric-deduplication.md)
      + [値オプションなし](../data-views/component-settings/no-value-options.md)
      + [永続性](../data-views/component-settings/persistence.md)
      + [部分文字列](../data-views/component-settings/substring.md)
      + [値のバケット化](../data-views/component-settings/value-bucketing.md)
   + [標準コンポーネントリファレンス](../data-views/component-reference.md)
   + [SQL コネクター](../data-views/sql-connector.md)
   + [派生フィールド](../data-views/derived-fields/derived-fields.md)
   + [ラベルとポリシー](../data-views/data-governance.md)

+ Workspace プロジェクト {#cja-workspace}
   + [Analysis Workspace の概要](../analysis-workspace/home.md)
   + [基本分析の実行](../analysis-workspace/perform-basic-analysis.md)
   + [アドバンス分析の実行](../analysis-workspace/perform-adv-analysis.md)
   + プロジェクト {#build-workspace-project}
      + [プロジェクトの概要](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [プロジェクトの作成](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [プロジェクトの保存](../analysis-workspace/build-workspace-project/save-projects.md)
      + Workspace のフォルダー {#workspace-folders}
         + [Workspace のフォルダーについて](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [フォルダーとサブフォルダーの作成](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [フォルダーを削除](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [プロジェクトの追加](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [プロジェクトの削除](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [新しいプロジェクトの保存](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [ホットキー（ショートカット）](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [カラーパレット](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [表示密度](../analysis-workspace/build-workspace-project/view-density.md)
   + ビジュアライゼーション {#visualizations}
      + [ビジュアライゼーションの概要](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [データソースの管理](../analysis-workspace/visualizations/t-sync-visualization.md)
      + フリーフォームテーブル {#freeform-table}
         + [フリーフォームテーブル](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + 列および行の設定 {#column-row-settings}
            + [列設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [行設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [動的項目と静的項目](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [テーブルのフィルタリングと並べ替え](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [ワークスペースの合計](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + コホートテーブル {#cohort-table}
         + [コホート分析とは](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [コホート分析レポートの設定](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [コホート分析のユースケース](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + フォールアウト {#fallout}
         + [フォールアウトの概要](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [フォールアウトビジュアライゼーションの設定](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [ディメンション間のフォールアウト](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [フォールアウト分析でのフィルターの適用](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + フロー {#flow}
         + [フローの概要](../analysis-workspace/visualizations/c-flow/flow.md)
         + [フロービジュアライゼーションの設定](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [ディメンション間のフロー](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [面グラフおよび積み重ね面グラフ](../analysis-workspace/visualizations/area.md)
      + [棒グラフおよび積み重ね棒グラフ](../analysis-workspace/visualizations/bar.md)
      + [ブレットグラフ](../analysis-workspace/visualizations/bullet-graph.md)
      + [複合グラフ](../analysis-workspace/visualizations/combo-charts.md)
      + [ドーナツ](../analysis-workspace/visualizations/donut.md)
      + [ヒストグラム](../analysis-workspace/visualizations/histogram.md)
      + [横棒グラフおよび積み重ね横棒グラフ](../analysis-workspace/visualizations/horizontal-bar.md)
      + [インテリジェントキャプション](../analysis-workspace/visualizations/intelligent-captions.md)
      + [主要指標の概要](../analysis-workspace/visualizations/key-metric.md)
      + [行](../analysis-workspace/visualizations/line.md)
      + [散布図](../analysis-workspace/visualizations/scatterplot.md)
      + [数値の概要と変更概要](../analysis-workspace/visualizations/summary-number-change.md)
      + [テキスト](../analysis-workspace/visualizations/text.md)
      + [ツリーマップ](../analysis-workspace/visualizations/treemap.md)
      + [ベン図](../analysis-workspace/visualizations/venn.md)
   + パネル {#panels}
      + [パネルの概要](../analysis-workspace/c-panels/panels.md)
      + [アトリビューションパネル](../analysis-workspace/c-panels/attribution.md)
      + [空のパネル](../analysis-workspace/c-panels/blank-panel.md)
      + [実験パネル](../analysis-workspace/c-panels/experimentation.md)
      + [フリーフォームパネル](../analysis-workspace/c-panels/freeform-panel.md)
      + [クイックインサイトパネル](../analysis-workspace/c-panels/quickinsight.md)
      + [メディアの同時視聴者数パネル](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + メディア再生滞在時間 {#media-playback-timespent}
         + [概要](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [入力と出力の設定](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [よくある質問（FAQ）](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + プロジェクトのキュレーション、共有、スケジュール {#curate-share}
      + [共有メニュー](../analysis-workspace/curate-share/send-schedule-files.md)
      + [プロジェクトのキュレーション](../analysis-workspace/curate-share/curate.md)
      + [プロジェクトの共有](../analysis-workspace/curate-share/share-projects.md)
      + [共有可能なリンクの作成](../analysis-workspace/curate-share/shareable-links.md)
      + [表示専用プロジェクト](../analysis-workspace/curate-share/view-only-projects.md)
      + [PDF ファイルまたは CSV ファイルのダウンロード](../analysis-workspace/curate-share/download-send.md)
      + [プロジェクトのスケジュール](../analysis-workspace/curate-share/t-schedule-report.md)
   + 仮想アナリスト {#virtual-analyst}
      + [仮想アナリストの概要](../analysis-workspace/virtual-analyst/overview.md)
      + 異常値検出 {#anomaly-detection}
         + [異常値検出の概要](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Analysis Workspace での異常値の表示](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [異常値検出で使用される統計的手法](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [ユーザー環境設定](../analysis-workspace/user-preferences.md)
   + Workspace FAQ {#workspace-faq}
      + [よくある質問](../analysis-workspace/workspace-faq/faq.md)
      + [エラーメッセージ](../analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace の制限](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [管理要件](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Analysis Workspace のアクセシビリティ](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Analysis Workspace のロングテール](../analysis-workspace/workspace-faq/long-tail.md)

+ Analytics ダッシュボード {#cja-dashboards}
   + [Analytics ダッシュボード - 概要](../mobile-app/home.md)
   + [キュレータータスク](../mobile-app/curator.md)
   + [モバイルスコアカードの作成](../mobile-app/create-scorecard.md)
   + [ダッシュボードを使用するエグゼクティブの設定](../mobile-app/set-up-execs.md)
   + [エグゼクティブユーザー向けクイックスタートガイド](../mobile-app/executive.md)

+ ガイド付き分析 {#guided-analysis}
   + [概要](../guided-analysis/overview.md)
   + 影響 {#impact}
      + [リリース表示](../guided-analysis/types/release.md)
      + [初回使用ビュー](../guided-analysis/types/first-use.md)
   + ファネル {#funnel}
      + [摩擦ビュー](../guided-analysis/types/friction.md)
      + [コンバージョントレンドビュー](../guided-analysis/types/conversion-trends.md)
   + ユーザーの増加率 {#user-growth}
      + [アクティブビュー](../guided-analysis/types/active.md)
      + [正味の成長見通し](../guided-analysis/types/net-growth.md)
   + 傾向 {#trends}
      + [使用状況ビュー](../guided-analysis/types/usage.md)
   + [業界の使用例](../guided-analysis/industry-use-cases.md)
   + [FAQ](../guided-analysis/faq.md)

+ コンポーネント {#cja-components}
   + [コンポーネントの概要](../components/overview.md)
   + [コンポーネントの説明の追加](../components/add-component-descriptions.md)
   + 注釈 {#annotations}
      + [注釈の概要](../components/annotations/overview.md)
      + [注釈を作成](../components/annotations/create-annotations.md)
      + [注釈を管理](../components/annotations/manage-annotations.md)
      + [注釈を表示](../components/annotations/view-annotations.md)
      + [モバイル注釈](../components/annotations/mobile-annotations.md)
   + オーディエンス {#audiences}
      + [オーディエンスの概要](../components/audiences/audiences-overview.md)
      + [オーディエンスの作成と公開](../components/audiences/publish.md)
      + [オーディエンス管理](../components/audiences/manage.md)
   + ディメンション {#dimensions}
      + [ディメンションのプレビュー](../components/dimensions/view-dimensions.md)
      + [ディメンションの分類](../components/dimensions/t-breakdown-fa.md)
      + [時間分割ディメンション](../components/dimensions/time-parting-dimensions.md)
      + [基数が非常に高いディメンション](../components/dimensions/high-cardinality.md)
   + [指標](../components/apply-create-metrics.md)
   + フィルター {#cja-filters}
      + [フィルターの概要](../components/filters/filters-overview.md)
      + [フィルターの作成](../components/filters/create-filters.md)
      + [クイックフィルター](../components/filters/quick-filters.md)
      + [フィルタービルダー](../components/filters/filter-builder.md)
      + [フィルターの管理](../components/filters/manage-filters.md)
      + [演算子](../components/filters/operators.md)
   + 計算指標 {#cja-calcmetrics}
      + [計算指標の概要](../components/calc-metrics/calc-metr-overview.md)
      + 計算指標のワークフロー {#cm-workflow}
         + [計算指標のワークフロー](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [指標の検索](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [指標の作成](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [指標タイプとアトリビューション](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [「パーティシペーション」指標の作成](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [フィルタリングされた指標](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [フィルターの積み重ねと置き換え](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [フィルター適用済み指標と重み付け指標](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [関数の使用](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [計算指標のタグ付け](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [計算指標の承認](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [計算指標の共有](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [計算指標マネージャー](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [デフォルトの計算指標](../components/calc-metrics/default-calcmetrics.md)
      + [基本関数](../components/calc-metrics/cm-functions.md)
      + [高度な関数](../components/calc-metrics/cm-adv-functions.md)
   + カレンダーと日付範囲 {#cja-date-ranges}
      + [カレンダーと日付範囲の概要](../components/date-ranges/calendar.md)
      + [日付範囲の作成](../components/date-ranges/create.md)
      + [日付範囲を管理](../components/date-ranges/manage.md)
      + [カスタム日付範囲の作成](../components/date-ranges/custom-date-ranges.md)
      + [日付の比較](../components/date-ranges/time-comparison.md)
   + データ要素 {#data-dictionary}
      + [データ要素の概要](../components/data-dictionary/data-dictionary-overview.md)
      + [データ要素でのコンポーネント情報の表示](../components/data-dictionary/view-data-dictionary.md)
      + [データ要素でのコンポーネントエントリの編集](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [データ要素の正常性の監視](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [Report Builder の概要](../report-builder/report-buider-overview.md)
   + [Report Builder の設定](../report-builder/report-builder-setup.md)
   + [データブロックの作成](../report-builder/create-a-data-block.md)
   + [Report Builder ハブ](../report-builder/report-builder-hub.md)
   + [データビューを選択](../report-builder/select-data-view.md)
   + [日付範囲を選択します。](../report-builder/select-date-range.md)
   + [フィルターの操作](../report-builder/work-with-filters.md)
   + [ディメンションのフィルタリング](../report-builder/filter-dimensions.md)
   + [データブロックの管理](../report-builder/manage-reportbuilder.md)
   + [ワークブックのスケジュール設定](../report-builder/schedule-reportbuilder.md)
   + [制限付きラベル](../report-builder/restricted-labels.md)
   + [Report Builder の設定](../report-builder/report-builder-settings.md)

+ ステッチ {#stitching}
   + [概要](../stitching/overview.md)
   + [ステッチの仕組み](../stitching/explained.md)
   + [ステッチされたデータセットの作成と管理](../stitching/stitching-ui.md)
   + [よくある質問](../stitching/faq.md)

+ クロスチャネル分析 {#cca}
   + [クロスチャネル分析の概要](../cca/overview.md)
   + [再生の仕組み](../cca/replay.md)
   + [クロスチャネル分析に関する FAQ](../cca/faq.md)

+ アドビの統合 {#integrations}
   + [AdobeソリューションとCustomer Journey Analyticsの概要](/help/integrations/overview.md)
   + [Adobe Analytics と Customer Journey Analytics の統合](/help/integrations/aa.md)
   + [Journey OptimizerデータとCustomer Journey Analyticsの統合](/help/integrations/ajo.md)
   + [決定管理データとCustomer Journey Analyticsの統合](/help/integrations/ajo-od.md)
   + [顧客 AI とCustomer Journey Analyticsの統合](/help/integrations/customer-ai.md)

+ データガバナンス {#cja-privacy}
   + [データガバナンス](../privacy/privacy-overview.md)
   + [監査ログ](../privacy/audit-log.md)
   + [顧客管理キー](../privacy/cmk.md)

+ ユースケース {#cja-usecases}
   + [Customer Journey Analytics のユースケース](../use-cases/cja-usecases.md)
   + Google Analytics データ {#ga}
      + [データを移行からGoogle AnalyticsへCustomer Journey Analyticsの概要](../use-cases/ga/overview.md)
      + [Platform への Google Analytics 履歴データの取り込み](../use-cases/ga/backfill.md)
      + [Platform への Google Analytics データのストリーミングの設定](../use-cases/ga/streaming.md)
      + [Customer Journey Analytics での Google Analytics データに関するレポート](../use-cases/ga/report.md)
   + データ取り込み {#data-ingestion}
      + [Marketo EngageデータのAdobe Experience Platformへの取り込みとCustomer Journey Analyticsでのレポート](../use-cases/data-ingestion/marketo.md)
      + [Adobe Experience PlatformオーディエンスのCustomer Journey Analyticsへの取り込み](../use-cases/data-ingestion/ingest-aep-segments.md)
   + データビュー {#data-views}
      + [データビューのユースケース](../use-cases/data-views/data-views-usecases.md)
      + [バインディングディメンションと指標の使用](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [アカウントレベルのデータをルックアップデータセットとして追加](../use-cases/b2b/b2b.md)
   + クロスチャネルデータ {#cross-channel}
      + [チャネルをまたいだデータの分析](../use-cases/cross-channel/cross-channel.md)
      + [コールセンターデータと web データの読み込み](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics データ {#aa-data}
      + [マーケティングチャネルディメンションの使用](../use-cases/aa-data/marketing-channels.md)
      + [スキーマの異なるレポートスイートの結合](../use-cases/aa-data/combine-report-suites.md)
   + 複雑なデータ {#complex-data}
      + [オブジェクトの配列の使用](../use-cases/object-arrays.md)

+ 管理 {#cja-admin}
   + [アクセス制御](../admin/cja-access-control.md)
   + [使用状況の表示と管理](../admin/estimate-usage.md)
   + [削除の影響](../admin/cja-deletion.md)
   + [Customer Journey Analyticsパフォーマンスの最適化](../admin/optimizing-performance.md)

+ ラボ {#labs}
   + [ラボユーザーガイド](../labs/labs.md)

+ トラブルシューティング {#troubleshooting}
   + [Adobe AnalyticsデータとCustomer Journey Analyticsデータの比較](../troubleshooting/compare.md)
   + [リアルタイム CDP とCustomer Journey Analyticsの間の指標とオーディエンスメンバーシップ数の一貫性](../troubleshooting/consistency-rcdp-cja.md)

+ [Customer Journey Analytics の用語集](../getting-started/cja-glossary.md)

+ [Customer Journey AnalyticsAPI](https://developer.adobe.com/cja-apis/docs/)
