---
git-repo: https://github.com/AdobeDocs/analytics-platform.ja-JP
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics ガイド
user-guide-description: このガイドでは、Adobe Experience Platform に基づいた、Cross-Channel Analytics 用のアドビの次世代ソリューションである Customer Journey Analytics についてのサポート情報を提供します。
breadcrumb-title: Customer Journey Analytics ガイド
source-git-commit: 9874626b52fd4e87bd6337b20ac03d837d8ad888
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 98%

---


# Customer Journey Analytics ガイド {#using}

+ [Customer Journey Analytics ガイド](getting-started/cja-landing.md)
+ リリースノート {#releases}
   + [最新リリース](release-notes/latest.md)
   + [2022年リリース](release-notes/2022.md)
   + [2021年リリース](release-notes/2021.md)
   + [2020年リリース](release-notes/2020.md)
   + [CJA リリース](release-notes/releases.md)
   + [CJA ドキュメントのアップデート](release-notes/doc-changes.md)
+ Customer Journey Analytics の概要 {#cja-overview}
   + [Customer Journey Analytics の概要](getting-started/cja-overview.md)
   + [はじめに](getting-started/cja-getting-started.md)
   + [CJA アクセス制御](getting-started/cja-access-control.md)
   + [Customer Journey Analytics のランディングページ](getting-started/landing.md)
   + [よくある質問](getting-started/cja-faq.md)
   + [リアルタイム CDP と CJA 間の指標の一貫性](getting-started/consistency-rcdp-cja.md)
   + [Adobe Analytics から Customer Journey Analytics への進化](getting-started/aa-to-cja.md)
   + [Customer Journey Analytics の新規ユーザー向けユーザーガイド](getting-started/aa-to-cja-user.md)
   + Adobe Analytics と Customer Journey Analytics の比較 {#compare-aa-cja}
      + [Customer Journey Analytics の機能のサポート](getting-started/aa-vs-cja/cja-aa.md)
      + [Adobe Analytics と CJA にまたがるデータ処理の比較](getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [仮想レポート環境とサンドボックス環境](getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [処理ルール、VISTA および分類とデータ準備の比較](getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [削除の影響](getting-started/cja-deletion.md)
   + [CJA の用語集](getting-started/cja-glossary.md)
+ 接続 {#cja-connections}
   + [接続の概要](connections/overview.md)
   + [接続の作成](connections/create-connection.md)
   + [接続の管理](connections/manage-connections.md)
   + [組み合わせイベントデータセット](connections/combined-dataset.md)
   + [標準検索](connections/standard-lookups.md)
   + Cross-Channel Analytics {#cca}
      + [Cross-Channel Analytics の概要](connections/cca/overview.md)
      + [再生の仕組み](connections/cca/replay.md)
      + [Cross-Channel Analytics に関する FAQ](connections/cca/faq.md)
+ データビュー {#cja-dataviews}
   + [データビューの概要](data-views/data-views.md)
   + [データビューの作成または編集](data-views/create-dataview.md)
   + コンポーネント設定 {#component-settings}
      + [コンポーネント設定の概要](data-views/component-settings/overview.md)
      + [アトリビューション](data-views/component-settings/attribution.md)
      + [動作](data-views/component-settings/behavior.md)
      + [形式](data-views/component-settings/format.md)
      + [値を含める / 除外](data-views/component-settings/include-exclude-values.md)
      + [指標の重複排除](data-views/component-settings/metric-deduplication.md)
      + [値オプションなし](data-views/component-settings/no-value-options.md)
      + [永続性](data-views/component-settings/persistence.md)
      + [部分文字列](data-views/component-settings/substring.md)
      + [値のバケット化](data-views/component-settings/value-bucketing.md)
   + [標準コンポーネントリファレンス](data-views/component-reference.md)
   + [データビューのユースケース](data-views/data-views-usecases.md)
+ ワークスペースプロジェクト {#cja-workspace}
   + [Analysis Workspace の概要](analysis-workspace/home.md)
   + [基本分析の実行](analysis-workspace/perform-basic-analysis.md)
   + [アドバンス分析の実行](analysis-workspace/perform-adv-analysis.md)
   + プロジェクト {#build-workspace-project}
      + [プロジェクトの概要](analysis-workspace/build-workspace-project/freeform-overview.md)
      + [プロジェクトの保存](analysis-workspace/build-workspace-project/save-projects.md)
      + [ホットキー（ショートカット）](analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [カラーパレット](analysis-workspace/build-workspace-project/color-palettes.md)
      + [表示密度](analysis-workspace/build-workspace-project/view-density.md)
   + ビジュアライゼーション {#visualizations}
      + [ビジュアライゼーションの概要](analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [データソースの管理](analysis-workspace/visualizations/t-sync-visualization.md)
      + フリーフォームテーブル {#freeform-table}
         + [フリーフォームテーブル](analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + 列および行の設定 {#column-row-settings}
            + [列設定](analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [行設定](analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [動的項目と静的項目](analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [テーブルのページネーション、フィルタリングおよび並べ替え](analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md)
         + [ワークスペースの合計](analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + コホートテーブル {#cohort-table}
         + [コホート分析とは](analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [コホート分析レポートの設定](analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [コホート分析のユースケース](analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + フォールアウト {#fallout}
         + [フォールアウトの概要](analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [フォールアウトビジュアライゼーションの設定](analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [ディメンション間のフォールアウト](analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [フォールアウト分析でのフィルターの適用](analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + フロー {#flow}
         + [フローの概要](analysis-workspace/visualizations/c-flow/flow.md)
         + [フロービジュアライゼーションの設定](analysis-workspace/visualizations/c-flow/create-flow.md)
         + [ディメンション間のフロー](analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [ヒストグラム](analysis-workspace/visualizations/histogram.md)
      + [ベン](analysis-workspace/visualizations/venn.md)
      + [面グラフおよび積み重ね面グラフ](analysis-workspace/visualizations/area.md)
      + [棒グラフおよび積み重ね棒グラフ](analysis-workspace/visualizations/bar.md)
      + [ブレットグラフ](analysis-workspace/visualizations/bullet-graph.md)
      + [ドーナツ](analysis-workspace/visualizations/donut.md)
      + [横棒グラフおよび積み重ね横棒グラフ](analysis-workspace/visualizations/horizontal-bar.md)
      + [行](analysis-workspace/visualizations/line.md)
      + [散布図](analysis-workspace/visualizations/scatterplot.md)
      + [数値の概要と変更概要](analysis-workspace/visualizations/summary-number-change.md)
      + [テキスト](analysis-workspace/visualizations/text.md)
      + [ツリーマップ](analysis-workspace/visualizations/treemap.md)
   + パネル {#panels}
      + [パネルの概要](analysis-workspace/c-panels/panels.md)
      + [アトリビューションパネル](analysis-workspace/c-panels/attribution.md)
      + [空のパネル](analysis-workspace/c-panels/blank-panel.md)
      + [フリーフォームパネル](analysis-workspace/c-panels/freeform-panel.md)
      + [クイックインサイトパネル](analysis-workspace/c-panels/quickinsight.md)
      + [メディアの同時視聴者数パネル](analysis-workspace/c-panels/media-concurrent-viewers.md)
      + メディア再生滞在時間 {#media-playback-timespent}
         + [概要](analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [入力と出力の設定](analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [よくある質問（FAQ）](analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + プロジェクトのキュレーション、共有、スケジュール {#curate-share}
      + [共有メニュー](analysis-workspace/curate-share/send-schedule-files.md)
      + [プロジェクトのキュレーション](analysis-workspace/curate-share/curate.md)
      + [プロジェクトの共有](analysis-workspace/curate-share/share-projects.md)
      + [共有可能なリンクの作成](analysis-workspace/curate-share/shareable-links.md)
      + [表示専用プロジェクト](analysis-workspace/curate-share/view-only-projects.md)
      + [PDF ファイルまたは CSV ファイルのダウンロード](analysis-workspace/curate-share/download-send.md)
      + [プロジェクトのスケジュール](analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [アトリビューションの概要](analysis-workspace/attribution/overview.md)
      + [アトリビューションモデルとルックバックウィンドウ](analysis-workspace/attribution/models.md)
      + [アルゴリズムアトリビューション](analysis-workspace/attribution/algorithmic.md)
      + [アトリビューションのベストプラクティス](analysis-workspace/attribution/best-practices.md)
      + [FAQ](analysis-workspace/attribution/faq.md)
   + 仮想アナリスト {#virtual-analyst}
      + [仮想アナリストの概要](analysis-workspace/virtual-analyst/overview.md)
      + 異常値検出 {#anomaly-detection}
         + [異常値検出の概要](analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Analysis Workspace での異常値の表示](analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [異常値検出で使用される統計的手法](analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [ユーザー環境設定](analysis-workspace/user-preferences.md)
   + ワークスペースの FAQ {#workspace-faq}
      + [よくある質問](analysis-workspace/workspace-faq/faq.md)
      + [Analysis Workspace のパフォーマンスの最適化](analysis-workspace/workspace-faq/optimizing-performance.md)
      + [エラーメッセージ](analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace の制限](analysis-workspace/workspace-faq/aw-limitations.md)
      + [管理要件](analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Analysis Workspace のアクセシビリティ](analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Analysis Workspace のロングテール](analysis-workspace/workspace-faq/long-tail.md)
+ Report Builder {#cja-reportbuilder}
   + [Report Builder の概要](report-builder/report-buider-overview.md)
   + [Report Builder の設定](report-builder/report-builder-setup.md)
   + [データブロックの作成](report-builder/create-a-data-block.md)
   + [Report Builder ハブ](report-builder/report-builder-hub.md)
   + [日付範囲を選択します。](report-builder/select-date-range.md)
   + [フィルターの操作](report-builder/work-with-filters.md)
   + [ディメンションのフィルタリング](report-builder/filter-dimensions.md)
   + [データブロックの管理](report-builder/manage-reportbuilder.md)
   + [Report Builder の設定](report-builder/report-builder-settings.md)
+ コンポーネント {#cja-components}
   + [コンポーネントの概要](components/overview.md)
   + 注釈 {#annotations}
      + [注釈の概要](components/annotations/overview.md)
      + [注釈を作成](components/annotations/create-annotations.md)
      + [注釈を管理](components/annotations/manage-annotations.md)
      + [注釈を表示](components/annotations/view-annotations.md)
      + [モバイル注釈](components/annotations/mobile-annotations.md)
   + ディメンション {#dimensions}
      + [ディメンションのプレビュー](components/dimensions/view-dimensions.md)
      + [ディメンションの分類](components/dimensions/t-breakdown-fa.md)
      + [時間分割ディメンション](components/dimensions/time-parting-dimensions.md)
      + [基数が非常に高いディメンション](components/dimensions/high-cardinality.md)
   + [指標](components/apply-create-metrics.md)
   + フィルター {#cja-filters}
      + [フィルターの概要](components/filters/filters-overview.md)
      + [フィルターの作成](components/filters/create-filters.md)
      + [フィルターの管理](components/filters/manage-filters.md)
      + [クイックフィルター](components/filters/quick-filters.md)
      + [アドホックフィルター](components/filters/ad-hoc-filters.md)
      + [演算子](components/filters/operators.md)
   + 計算指標 {#cja-calcmetrics}
      + [計算指標の概要](components/calc-metrics/calc-metr-overview.md)
      + 計算指標のワークフロー {#cm-workflow}
         + [計算指標のワークフロー](components/calc-metrics/cm-workflow/cm-workflow.md)
         + [指標の検索](components/calc-metrics/cm-workflow/cm-finding.md)
         + [指標の作成](components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [指標タイプとアトリビューション](components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [シンプルな「訪問あたりのページビュー数」指標の作成](components/calc-metrics/cm-workflow/cm-pvv.md)
         + [フィルタリングされた指標](components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [セグメントの積み重ねと置き換え](components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [フィルター適用済み指標と重み付け指標](components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [関数の使用](components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [パーティシペーション指標](components/calc-metrics/cm-workflow/participation-metric.md)
         + [計算指標のタグ付け](components/calc-metrics/cm-workflow/cm-tagging.md)
         + [計算指標の承認](components/calc-metrics/cm-workflow/cm-approving.md)
         + [計算指標の共有](components/calc-metrics/cm-workflow/cm-sharing.md)
         + [計算指標マネージャ](components/calc-metrics/cm-workflow/cm-manager.md)
      + [基本関数](components/calc-metrics/cm-functions.md)
      + [高度な関数](components/calc-metrics/cm-adv-functions.md)
   + 日付範囲 {#cja-date-ranges}
      + [日付範囲の概要](components/date-ranges/overview.md)
      + [日付範囲の作成](components/date-ranges/create.md)
      + [日付範囲を管理](components/date-ranges/manage.md)
      + [カレンダーの概要](components/date-ranges/calendar.md)
      + [カスタム日付範囲の作成](components/date-ranges/custom-date-ranges.md)
      + [日付の比較](components/date-ranges/time-comparison.md)
+ Analytics ダッシュボード {#cja-dashboards}
   + [Analytics ダッシュボード - 概要](mobile-app/home.md)
   + [キュレータータスク](mobile-app/curator.md)
   + [スコアカードの作成](mobile-app/create-scorecard.md)
   + [ダッシュボードを使用するエグゼクティブの設定](mobile-app/set-up-execs.md)
   + [エグゼクティブユーザー向けクイックスタートガイド](mobile-app/executive.md)
+ ユースケース {#cja-usecases}
   + [Customer Journey Analytics のユースケース](use-cases/cja-usecases.md)
   + [レポートスイートを様々なスキーマと組み合わせる](use-cases/combine-report-suites.md)
   + [オブジェクトの配列の使用](use-cases/object-arrays.md)
   + [バインディングディメンションと指標の使用](use-cases/binding-dimensions-metrics.md)
   + [（B2B）アカウントレベルのデータをルックアップデータセットとして追加](use-cases/b2b.md)
   + [Marketo Engage データの AEP への取り込みと CJA でのレポート](use-cases/marketo.md)
   + [AEP オーディエンスの CJA への取り込み](use-cases/ingest-aep-segments.md)
   + [チャネルをまたいだデータの分析](use-cases/cross-channel.md)
   + [コールセンターデータと web データの読み込み](use-cases/call-center.md)
   + [データ取り込みのユースケース](use-cases/data-ingestion.md)
   + [マーケティングチャネルディメンションの使用](use-cases/marketing-channels.md)
   + [Adobe Experience Platform への Google Analytics データの取り込み](use-cases/ga-to-cja.md)
   + [CJA での Google Analytics データに関するレポート](use-cases/ga-to-cja-reporting.md)
+ ラボ {#labs}
   + [ラボユーザーガイド](labs/labs.md)
+ トラブルシューティング {#troubleshooting}
   + [Adobe Analytics データと CJA データの比較](troubleshooting/compare.md)
+ プライバシー {#cja-privacy}
   + [プライバシーの概要](privacy/privacy-overview.md)
+ [CJA API](https://developer.adobe.com/cja-apis/docs/)
