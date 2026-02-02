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
source-git-commit: 905d32421b4c1d3135a51dfd9898a02e750555d0
workflow-type: tm+mt
source-wordcount: '1363'
ht-degree: 96%

---

# Adobe Customer Journey Analytics ガイド {#using}

+ [Adobe Customer Journey Analytics ガイド](../getting-started/cja-landing.md)

+ リリースノート {#releases}
   + [最新リリース](../release-notes/latest.md)
   + [プレリリースノート](../release-notes/pre-release-notes.md)
   + [2025年リリース](../release-notes/2025.md)
   + [2024年リリース](../release-notes/2024.md)
   + [2023年リリース](../release-notes/2023.md)
   + [2022年リリース](../release-notes/2022.md)
   + [2021年リリース](../release-notes/2021.md)
   + [2020年リリース](../release-notes/2020.md)
   + [機能リリース戦略](../release-notes/releases.md)
   + [ドキュメントの更新](../release-notes/doc-changes.md)

+ はじめに {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [概要](../getting-started/cja-overview.md)
      + [クイックスタートガイド](../getting-started/cja-getting-started.md)
      + [ランディングページ](../getting-started/landing.md)
      + [よくある質問](../getting-started/cja-faq.md)
      + [BI ソリューションとの比較](../getting-started/cja-vs-bi.md)
      + [AI アシスタント](../ai-assistant.md)
      + [Data Insights Agent](../data-analysis-ai.md)
   + Customer Journey Analytics B2B Edition {#cja-b2b}
      + [概要](/help/getting-started/cja-b2b-edition.md)
      + [B2B の概念と機能](/help/getting-started/cja-b2b-concepts-features.md)
      + [クイックスタートガイド](/help/getting-started/cja-b2b-quick-start-guide.md)
      + [移行ガイド](/help/getting-started/cja-b2b-transition.md)

+ アップグレードと比較 {#compare-aa-cja}
   + Customer Journey Analytics にアップグレード {#upgrade-to-cja}
      + [基本を学ぶ](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [アップグレードパスの選択](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Platform にデータを送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [履歴データの保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [推奨されるアップグレードプロセス](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + [組織の準備](/help/getting-started/cja-upgrade/cja-upgrade-org-readiness.md)
      + スキーマの設計と作成 {#schema}
         + [スキーマの設計](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [スキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [既存のスキーマの使用](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + データストリームの作成 {#create-datastream}
         + [データストリームの作成](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [Platform をサービスとして追加](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + データセットの作成 {#create-datasets}
         + [データセットの作成](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [分類のルックアップデータセットの作成](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [データ取り込みの監視](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + タグを使用した Web SDK の実装 {#create-tags}
         + [プロパティのタグの作成](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [タグへの Web SDK 拡張機能の追加](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [Web SDK 拡張機能用のローダータグの実装](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [タグへの XDM データ収集ロジックを追加](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [手動での Web SDK の実装](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [API を使用した Web SDK の実装](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [接続の作成](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [データビューの作成](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [マーケティングチャネル派生フィールドの作成](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [データフローの検証](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [ストリーミングメディアコレクション設定](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + Analytics ソースコネクタを使用した履歴データの保持 {#historical-data-source-connector}
         + [Analytics ソースコネクタ用に XDM スキーマを作成します](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [Analytics ソースコネクタの作成とフィールドのマッピング](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [接続への Analytics ソースコネクタデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Adobe Analytics を無効にするタイミングの評価](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [Adobe Analytics の無効化](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + 別のアップグレード方法 {#alternative-upgrade-methods}
         + [AppMeasurement データ収集の使用](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [データレイヤーの送信](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Analytics ソースコネクタ](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + その他のアップグレードシナリオ {#other-upgrade-scenarios}
         + [Analytics ソースコネクタから Web SDK への移動](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [Adobe Analytics 以外のソリューションからのアップグレード](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + 追加情報 {#additional-information}
         + [Analytics の実装について](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [アップグレード時の Adobe Analytics 機能のサポート](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Customer Journey Analytics 機能](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Web SDK 実装オプション](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [Platform 用の Adobe Analytics Web SDK の設定](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [Adobe Journey Optimizer を使用したパーソナライゼーションの使用](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + Adobe Analytics との比較 {#cja-aa-comparison}
      + [概要](../getting-started/aa-vs-cja/overview.md)
      + [Adobe Analytics データの使用](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Adobe Analytics データのマッピング](../getting-started/aa-vs-cja/mapping-data-ims-orgs.md)
      + [機能のサポート](../getting-started/aa-vs-cja/cja-aa.md)
      + [用語の比較](../getting-started/aa-vs-cja/terminology.md)
      + [データ処理の比較](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [環境](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Analytics 処理とデータ準備の比較](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Analytics ID](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Adobe Analytics からの進化](../getting-started/aa-to-cja.md)
   + [Adobe Analytics ユーザー向けユーザーガイド](../getting-started/aa-to-cja-user.md)

+ データ取り込み {#cja-data-ingestion}
   + [概要](../data-ingestion/data-ingestion.md)
   + 取り込みと使用のクイックスタートガイド{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [モバイル SDK](../data-ingestion/aepmobilesdk.md)
         + [Server API](../data-ingestion/serverapi.md)
      + [バッチデータ](../data-ingestion/batch.md)
      + [ストリーミングデータ](../data-ingestion/streaming.md)
      + [ソースコネクタ](../data-ingestion/sources.md)
      + [アドホックデータ](/help/data-ingestion/adhoc.md)

+ データミラー {#cja-data-mirror}
   + [概要](/help/data-mirror/data-mirror.md)
   + 設定 {#configure}
      + [データウェアハウスネイティブソリューション](/help/data-mirror/datawarehouse.md)
      + [Experience Platform](/help/data-mirror/aep.md)
      + [Customer Journey Analytics](/help/data-mirror/cja.md)
   + [データミラークイックスタートガイド](/help/data-mirror/relational.md)

+ 接続 {#cja-connections}
   + [接続の概要](../connections/overview.md)
   + [接続の作成または編集](../connections/create-connection.md)
   + [接続の管理](../connections/manage-connections.md)
   + [組み合わせイベントデータセット](../connections/combined-dataset.md)
   + [標準検索](../connections/standard-lookups.md)
   + [B2B ルックアップ](../connections/transform-datasets-b2b-lookups.md)
   + オーディエンス分析 {#audience-analysis}
      + [概要](/help/connections/audience-analysis/audience-analysis-overview.md)
      + [設定](/help/connections/audience-analysis/audience-analysis-configure.md)
      + [管理](/help/connections/audience-analysis/audience-analysis-manage.md)
      + [分析](/help/connections/audience-analysis/analyze-audiences.md)
+ データビュー {#cja-dataviews}
   + [データビューの概要](../data-views/data-views.md)
   + [データビューの作成または編集](../data-views/create-dataview.md)
   + [セッション設定](../data-views/session-settings.md)
   + コンポーネント設定 {#component-settings}
      + [コンポーネント設定の概要](../data-views/component-settings/overview.md)
      + [アトリビューション](../data-views/component-settings/attribution.md)
      + [動作](../data-views/component-settings/behavior.md)
      + [形式](../data-views/component-settings/format.md)
      + [値を含む／除外](../data-views/component-settings/include-exclude-values.md)
      + [指標の重複排除](../data-views/component-settings/metric-deduplication.md)
      + [値なしオプション](../data-views/component-settings/no-value-options.md)
      + [永続性](../data-views/component-settings/persistence.md)
      + [部分文字列](../data-views/component-settings/substring.md)
      + [概要データグループ](../data-views/component-settings/summary-data-group.md)
      + [値のバケット化](../data-views/component-settings/value-bucketing.md)
   + [標準コンポーネントリファレンス](../data-views/component-reference.md)
   + [BI 拡張機能](../data-views/bi-extension.md)
   + [派生フィールド](../data-views/derived-fields/derived-fields.md)
   + [概要データ](../data-views/summary-data.md)
   + [ラベルとポリシー](../data-views/data-governance.md)
   + 共有指標とディメンション{#shared-metrics-dimensions}
      + [概要](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [編集者](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)
+ ツール {#tools}
   + アセットを転送 {#asset-transfer}
      + [アセットを転送](../tools/asset-transfer/transfer-assets.md)
   + 製品の使用状況 {#product-usage}
      + [概要](../tools/product-usage/usage-overview.md)
      + [データ設定](../tools/product-usage/data-settings.md)
      + [オプトアウト設定](../tools/product-usage/opt-out-settings.md)

+ Workspace プロジェクト {#cja-workspace}
   + [Analysis Workspace の概要](../analysis-workspace/home.md)
   + [基本分析の実行](../analysis-workspace/perform-basic-analysis.md)
   + [アドバンス分析の実行](../analysis-workspace/perform-adv-analysis.md)
   + プロジェクト {#build-workspace-project}
      + [概要](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [プロジェクトの迅速な開始](/help/analysis-workspace/build-workspace-project/starter-projects.md)
      + [プロジェクトの作成](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [プロジェクトを開く](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [プロジェクトへのコメント](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [プロジェクトを保存](../analysis-workspace/build-workspace-project/save-projects.md)
      + [目次](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
      + Workspace のフォルダー {#workspace-folders}
         + [概要](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [フォルダーの作成](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [フォルダーの管理](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [プロジェクトの追加または移動](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [ホットキー](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [カラーパレット](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [表示密度](../analysis-workspace/build-workspace-project/view-density.md)
      + [デバッガー](../analysis-workspace/build-workspace-project/debugger.md)
   + テンプレート {#templates}
      + [テンプレートの使用](../analysis-workspace/templates/use-templates.md)
      + [テンプレートの作成と管理](../analysis-workspace/templates/create-templates.md)
   + ビジュアライゼーション {#visualizations}
      + [概要](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [データソースの管理](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [インテリジェントキャプション](../analysis-workspace/visualizations/intelligent-captions.md)
      + フリーフォームテーブル {#freeform-table}
         + [概要](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [ハイパーリンクを作成](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + [トレンドデータの表示](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)
         + [複数のディメンションを含める](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)
         + [フィルタリングと並べ替え](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [合計](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
         + 列および行の設定 {#column-row-settings}
            + [列設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [行設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [動的項目と静的項目](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
      + コホートテーブル {#cohort-table}
         + [概要](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [設定](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [ユースケース](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + フォールアウト {#fallout}
         + [概要](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [設定](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [ディメンション間のフォールアウト](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [セグメントの適用](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + フロー {#flow}
         + [概要](../analysis-workspace/visualizations/c-flow/flow.md)
         + [設定](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [ディメンション間のフロー](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + ジャーニーキャンバス {#journey-canvas}
         + [概要](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [設定](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [トラブルシューティング](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [積み重ね面グラフ](../analysis-workspace/visualizations/area.md)
      + [積み重ね棒グラフ](../analysis-workspace/visualizations/bar.md)
      + [ブレット](../analysis-workspace/visualizations/bullet-graph.md)
      + [コンボ](../analysis-workspace/visualizations/combo-charts.md)
      + [ドーナツ](../analysis-workspace/visualizations/donut.md)
      + [ヒストグラム](../analysis-workspace/visualizations/histogram.md)
      + [積み重ね横棒グラフ](../analysis-workspace/visualizations/horizontal-bar.md)
      + [主要指標の概要](../analysis-workspace/visualizations/key-metric.md)
      + [行](../analysis-workspace/visualizations/line.md)
      + [マップ](/help/analysis-workspace/visualizations/map.md)
      + [散布図](../analysis-workspace/visualizations/scatterplot.md)
      + [セクションヘッダー](/help/analysis-workspace/visualizations/section-header.md)
      + [数と変更の概要](../analysis-workspace/visualizations/summary-number-change.md)
      + [テキスト](../analysis-workspace/visualizations/text.md)
      + [ツリーマップ](../analysis-workspace/visualizations/treemap.md)
      + [ベン図](../analysis-workspace/visualizations/venn.md)
   + パネル {#panels}
      + [概要](../analysis-workspace/c-panels/panels.md)
      + [空のパネル](../analysis-workspace/c-panels/blank-panel.md)
      + [アトリビューション](../analysis-workspace/c-panels/attribution.md)
      + [実験](../analysis-workspace/c-panels/experimentation.md)
      + [フリーフォーム](../analysis-workspace/c-panels/freeform-panel.md)
      + [メディア分平均オーディエンス](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [メディア同時視聴者数](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [メディア再生滞在時間](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [次または前の項目](../analysis-workspace/c-panels/next-previous.md)
      + [クイックインサイト](../analysis-workspace/c-panels/quickinsight.md)
   + キュレーションと共有 {#curate-share}
      + [概要](../analysis-workspace/curate-share/send-schedule-files.md)
      + [プロジェクトのキュレーション](../analysis-workspace/curate-share/curate.md)
      + [プロジェクトの共有](../analysis-workspace/curate-share/share-projects.md)
      + [共有可能なリンクの作成](../analysis-workspace/curate-share/shareable-links.md)
      + [読み取り専用プロジェクト](../analysis-workspace/curate-share/view-only-projects.md)
      + [スライドプレゼンテーションの生成](/help/analysis-workspace/curate-share/generate-slides.md)
   + 書き出し {#export}
      + [概要](../analysis-workspace/export/export-project-overview.md)
      + [ダウンロード](../analysis-workspace/export/download-send.md)
      + [送信とスケジュール](../analysis-workspace/export/t-schedule-report.md)
      + [クラウドへの書き出し](../analysis-workspace/export/export-cloud.md)
   + アトリビューション {#attribution}
      + [アトリビューションの概要](../analysis-workspace/attribution/overview.md)
      + [モデル, コンテナ, ルックバックウィンドウ](../analysis-workspace/attribution/models.md)
      + [アルゴリズムアトリビューション](../analysis-workspace/attribution/algorithmic.md)
      + [ベストプラクティス](../analysis-workspace/attribution/best-practices.md)
      + [よくある質問](../analysis-workspace/attribution/faq.md)
   + 異常値検出 {#anomaly-detection}
      + [概要](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [異常値を表示](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [統計的手法](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + 予測 {#forecasting}
      + [概要](../analysis-workspace/c-forecast/forecasting.md)
      + [予測を表示](../analysis-workspace/c-forecast/view-forecasts.md)
      + [統計的手法](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [ユーザー環境設定](../analysis-workspace/user-preferences.md)
   + Workspace に関する FAQ とその他 {#workspace-faq}
      + [よくある質問](../analysis-workspace/workspace-faq/faq.md)
      + [パフォーマンスの最適化](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [エラーとトラブルシューティング](../analysis-workspace/workspace-faq/error-messages.md)
      + [制限事項](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [要件](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [アクセシビリティ](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Content Analytics {#content-analytics}
   + [概要](/help/content-analytics/content-analytics.md)
   + レポート {#report}
      + [概要](/help/content-analytics/report/report.md)
      + [コンポーネント](/help/content-analytics/report/components.md)
   + 設定 {#configuration}
      + [概要](/help/content-analytics/config/configuration.md)
      + [ガイド付き設定](/help/content-analytics/config/guided.md)
      + [手動設定](/help/content-analytics/config/manual.md)
      + [スタンドアロン設定](/help/content-analytics/config/standalone.md)
      + [データ収集](/help/content-analytics/config/datacollection.md)

+ Analytics ダッシュボード {#cja-dashboards}
   + [概要](../mobile-app/home.md)
   + [キュレータータスク](../mobile-app/curator.md)
   + [モバイルスコアカードの作成](../mobile-app/create-scorecard.md)
   + [モバイルスコアカードの管理](../mobile-app/manage-scorecard.md)
   + [ダッシュボードを使用するエグゼクティブの設定](../mobile-app/set-up-execs.md)
   + [エグゼクティブユーザー向けクイックスタートガイド](../mobile-app/executive.md)

+ ガイド付き分析 {#guided-analysis}
   + [概要](../guided-analysis/overview.md)
   + [アクティブな増加](../guided-analysis/types/active-growth.md)
   + [コンバージョントレンド](../guided-analysis/types/conversion-trends.md)
   + [エンゲージメント](../guided-analysis/types/engagement.md)
   + [初回使用の影響](../guided-analysis/types/first-use-impact.md)
   + [頻度](../guided-analysis/types/frequency.md)
   + [ファネル](../guided-analysis/types/funnel.md)
   + [純増加率](../guided-analysis/types/net-growth.md)
   + [リリースの影響](../guided-analysis/types/release-impact.md)
   + [リテンション](../guided-analysis/types/retention.md)
   + [タイムライン](../guided-analysis/types/timeline.md)
   + [トレンド](../guided-analysis/types/trends.md)
   + [業界ユースケース](../guided-analysis/industry-use-cases.md)
   + [FAQ](../guided-analysis/faq.md)

+ コンポーネント {#cja-components}
   + [概要](../components/overview.md)
   + [コンポーネントの使用](../components/use-components-in-workspace.md)
   + [コンポーネントの説明の追加](../components/add-component-descriptions.md)
   + 注釈 {#annotations}
      + [概要](../components/annotations/overview.md)
      + [注釈を作成](../components/annotations/create-annotations.md)
      + [注釈を管理](../components/annotations/manage-annotations.md)
      + [注釈を表示](../components/annotations/view-annotations.md)
      + [モバイルスコアカードの注釈](../components/annotations/mobile-annotations.md)
   + オーディエンスパブリッシング {#audiences}
      + [オーディエンス公開の概要](../components/audiences/audiences-overview.md)
      + [オーディエンスの作成と公開](../components/audiences/publish.md)
      + [公開済みオーディエンスの管理](../components/audiences/manage.md)
   + ディメンション {#dimensions}
      + [概要](../components/dimensions/overview.md)
      + [ディメンションのプレビュー](../components/dimensions/view-dimensions.md)
      + [ディメンションの分類](../components/dimensions/t-breakdown-fa.md)
      + [時間分割ディメンション](../components/dimensions/time-parting-dimensions.md)
      + [基数の高いディメンション](../components/dimensions/high-cardinality.md)
   + [指標](../components/apply-create-metrics.md)
   + セグメント {#segments}
      + [概要](/help/components/segments/seg-overview.md)
      + [セグメントの作成](/help/components/segments/seg-create.md)
      + [セグメントの作成](/help/components/segments/seg-builder.md)
      + [クイックセグメント](/help/components/segments/seg-quick.md)
      + [順次セグメント](/help/components/segments/seg-sequential-build.md)
      + [セグメントの共有](/help/components/segments/seg-share.md)
      + [セグメントのタグ設定](/help/components/segments/seg-tag.md)
      + [セグメントリストのフィルタリング](/help/components/segments/seg-filter.md)
      + [セグメントのお気に入りへの登録](/help/components/segments/seg-favorite.md)
      + [セグメントの承認](/help/components/segments/seg-approve.md)
      + [セグメントのコピー](/help/components/segments/seg-copy.md)
      + [セグメントの管理](/help/components/segments/seg-manage.md)
      + [演算子](/help/components/segments/seg-operators.md)
      + [セグメントの使用](/help/components/segments/seg-use.md)
   + 計算指標 {#cja-calcmetrics}
      + [概要](../components/calc-metrics/calc-metr-overview.md)
      + ワークフロー {#cm-workflow}
         + [計算指標の作成](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [指標の検索](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [計算指標の作成](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [シンプルな例](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [より複雑な例](../components/calc-metrics/cm-workflow/cm-orders-participation.md)
         + [指標タイプとアトリビューション](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [パーティシペーション指標](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [セグメント化指標](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [セグメントの積み重ねと置き換え](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [計算指標をフィルタリング](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [計算指標のお気に入りへの登録](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [計算指標をコピー](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [関数の使用](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [計算指標をタグ付け](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [計算指標の承認](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [計算指標の共有](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [計算指標の管理](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [例](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [計算指標テンプレート](../components/calc-metrics/default-calcmetrics.md)
      + [基本関数](../components/calc-metrics/cm-functions.md)
      + [高度な関数](../components/calc-metrics/cm-adv-functions.md)
   + 日付範囲 {#cja-date-ranges}
      + [概要](../components/date-ranges/overview.md)
      + [日付範囲の作成](../components/date-ranges/create.md)
      + [日付範囲の管理](../components/date-ranges/manage.md)
      + [日付の比較](../components/date-ranges/time-comparison.md)
      + [例](../components/date-ranges/custom-date-ranges.md)
   + アラート {#alerts}
      + [概要](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [アラートの作成](/help/components/c-intelligent-alerts/alert-builder.md)
      + [アラートの管理](/help/components/c-intelligent-alerts/alert-manager.md)
      + [機能の比較](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [ユースケース](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + 書き出し {#exports}
      + [クラウドの書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)
      + [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md)
      + [クラウドの書き出し場所の管理](/help/components/exports/manage-export-locations.md)
      + [書き出しの管理](/help/components/exports/manage-exports.md)
      + [書き出しログの管理](/help/components/exports/manage-export-logs.md)
      + [書き出しのトラブルシューティング](/help/components/exports/troubleshoot-exports.md)
   + データ辞書 {#data-dictionary}
      + [概要](../components/data-dictionary/data-dictionary-overview.md)
      + [データ辞書でのコンポーネント情報の表示](../components/data-dictionary/view-data-dictionary.md)
      + [データ辞書でのコンポーネントエントリの編集](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [データ辞書の正常性の監視](../components/data-dictionary/monitor-data-dictionary-health.md)
   + リアルタイムレポート {#real-time-reporting}
      + [概要](/help/components/real-time/real-time.md)
      + [リアルタイムレポートの使用](/help/components/real-time/use-real-time.md)
   + [スケジュールされたプロジェクト](../components/scheduled-projects-manager.md)
+ Report Builder {#cja-reportbuilder}
   + [概要](../report-builder/rb-overview.md)
   + [Report Builder の設定](../report-builder/report-builder-setup.md)
   + [データブロックの作成](../report-builder/create-a-data-block.md)
   + [Report Builder ハブ](../report-builder/report-builder-hub.md)
   + [データビューの選択](../report-builder/select-data-view.md)
   + [日付範囲の選択](../report-builder/select-date-range.md)
   + [セグメントの操作](../report-builder/work-with-filters.md)
   + [ディメンションのフィルタリング](../report-builder/filter-dimensions.md)
   + [データブロックの管理](../report-builder/manage-reportbuilder.md)
   + [メールのワークブックのスケジュール設定](../report-builder/schedule-reportbuilder.md)
   + [クラウド書き出しのワークブックのスケジュール設定](../report-builder/report-builder-export.md)
   + [ワークブックスケジュールの管理](/help/report-builder/manage-schedules-reportbuilder.md)
   + [制限付きラベル](../report-builder/restricted-labels.md)
   + [Report Builder の設定](../report-builder/report-builder-settings.md)


+ レポートアクティビティマネージャー {#reporting-activity-manager}
   + [概要](../reporting-activity-manager/reporting-activity-overview.md)
   + [レポートアクティビティの表示](../reporting-activity-manager/reporting-activity.md)
   + [レポートリクエストのキャンセル](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ ステッチ {#stitching}
   + [概要](/help/stitching/overview.md)
   + [フィールドベースのステッチ](/help/stitching/fbs.md)
   + [グラフベースのステッチ](/help/stitching/gbs.md)
   + [リクエストのステッチ](/help/stitching/use-stitching.md)
   + [ステッチの使用](/help/stitching/use-stitching-ui.md)
   + [ステッチの検証](/help/stitching/validate.md)
   + [よくある質問](/help/stitching/faq.md)

+ アドビの統合 {#integrations}
   + [概要](/help/integrations/overview.md)
   + [Adobe Analytics の統合](/help/integrations/aa.md)
   + [Target の統合](/help/integrations/at.md)
   + [Journey Optimizer データの統合](/help/integrations/ajo.md)
   + [意思決定管理データの統合](/help/integrations/ajo-od.md)
   + [顧客 AI の統合](/help/integrations/customer-ai.md)
   + [Adobe Analytics の統合](/help/integrations/advertising.md)

+ データガバナンス {#cja-privacy}
   + [データガバナンス](../privacy/privacy-overview.md)
   + [監査ログ](../privacy/audit-log.md)
   + [顧客管理キー](../privacy/cmk.md)

+ ユースケース {#cja-usecases}
   + [Customer Journey Analytics のユースケース](../use-cases/cja-usecases.md)
   + Adobe Analytics データ {#aa-data}
      + [マーケティングチャネルディメンションの使用](../use-cases/aa-data/marketing-channels.md)
      + [スキーマの異なるレポートスイートの結合](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [ユーザーベースの B2B プロジェクトの例](../use-cases/b2b/example.md)
      + B2B Edition {#b2b-edition}
         + [ユースケースの概要](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)
         + [設定](/help/use-cases/b2b/b2b-edition/setup.md)
         + [アカウントマーケティングの最適化](/help/use-cases/b2b/b2b-edition/optimize-account-marketing.md)
         + [主要アカウントの拡大](/help/use-cases/b2b/b2b-edition/grow-key-accounts.md)
         + [製品価値の構築](/help/use-cases/b2b/b2b-edition/build-product-value.md)
   + 複雑なデータ {#complex-data}
      + [オブジェクトの配列を使用](../use-cases/object-arrays.md)
   + クロスチャネルデータ {#cross-channel}
      + [チャネルをまたいだデータの分析](../use-cases/cross-channel/cross-channel.md)
      + [コールセンターデータと web データの読み込み](../use-cases/cross-channel/call-center.md)
   + データの書き出し {#data-export}
      + [概要](../use-cases/data-export/overview.md)
      + [BI 拡張機能](../use-cases/data-export/bi-extension.md)
      + [データセットの書き出し](../use-cases/data-export/export-datasets.md)
      + [フルテーブルの書き出し](../use-cases/data-export/export-full-table.md)
      + [クエリサービスとデータセットの書き出し](../use-cases/data-export/queryservice-export-datasets.md)
   + データ取り込み {#data-ingestion}
      + [Marketo Engage データの取り込みと使用](../use-cases/data-ingestion/marketo.md)
      + [Experience Platform オーディエンスの取り込みと使用](../use-cases/data-ingestion/ingest-aep-segments.md)
   + データビュー {#data-views}
      + [データビューのユースケース](/help/use-cases/data-views/data-views-usecases.md)
      + [バインディングディメンションと指標の使用](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [概要データの使用](/help/use-cases/data-views/summary-data.md)
      + BI 拡張機能 {#bi-extension}
         + [ユースケース](/help/use-cases/data-views/bi-extension-usecases.md)
         + [データビューの接続とリスト表示](/help/use-cases/data-views/bi-extension/connect-and-validate.md)
         + [毎日のトレンド](/help/use-cases/data-views/bi-extension/daily-trend.md)
         + [毎時トレンド](/help/use-cases/data-views/bi-extension/hourly-trend.md)
         + [月間トレンド](/help/use-cases/data-views/bi-extension/monthly-trend.md)
         + [ランク付けされた単一ディメンション](/help/use-cases/data-views/bi-extension/single-dimension-ranked.md)
         + [複数のディメンションのランク](/help/use-cases/data-views/bi-extension/multiple-dimension-ranked.md)
         + [個別ディメンション値のカウント](/help/use-cases/data-views/bi-extension/count-distinct-dimension-values.md)
         + [日付範囲名を使用してフィルター](/help/use-cases/data-views/bi-extension/use-date-range-names-to-filter.md)
         + [セグメント名を使用したセグメント化](/help/use-cases/data-views/bi-extension/use-segment-names-to-segment.md)
         + [ディメンション値を使用したセグメント化](/help/use-cases/data-views/bi-extension/use-dimension-values-to-segment.md)
         + [並べ替え](/help/use-cases/data-views/bi-extension/sort.md)
         + [制限](/help/use-cases/data-views/bi-extension/limits.md)
         + [変換](/help/use-cases/data-views/bi-extension/transformations.md)
         + [ビジュアライゼーション](/help/use-cases/data-views/bi-extension/visualizations.md)
         + [注意事項](/help/use-cases/data-views/bi-extension/caveats.md)

   + 派生フィールド {#derived-fields}
      + [LLM および AI 生成トラフィックのレポート](/help/use-cases/ai-traffic.md)
      + [目標に関するレポート](../use-cases/goals-using-derived-fields.md)
   + 製品分析 {#product-analysis}
      + [製品分析](/help/use-cases/product-analysis.md)
   + ステッチ {#stitching}
      + [共有デバイス](/help/use-cases/stitching/shared-devices.md)
   + サードパーティデータ {#third-party}
      + [概要](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [Google Analytics からデータを移行](/help/use-cases/third-party/ga/overview.md)
         + [Google Analytics 履歴データの取り込み](/help/use-cases/third-party/ga/backfill.md)
         + [Google Analytics データのストリーミングの設定](/help/use-cases/third-party/ga/streaming.md)
         + [Google Analytics データに関するレポート](/help/use-cases/third-party/ga/report.md)
      + 量子指標 {#qm}
         + [概要](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [セッション再生を結合](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [ヒートマップを使用](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [摩擦イベントを追加](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [ソースコネクタ](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ ラボ {#labs}
   + [ラボユーザーガイド](../labs/labs.md)

+ トラブルシューティング {#troubleshooting}
   + [ソースコネクタデータの比較](../troubleshooting/compare.md)
   + [指標とオーディエンスの一貫性](../troubleshooting/consistency-rcdp-cja.md)
   + [権限の不足](../troubleshooting/lack-of-permissions.md)

+ テクニカルノート {#technotes}
   + [アクセス制御](../technotes/access-control.md)
   + [データセンター](../technotes/data-centers.md)
   + [削除の影響](../technotes/deletion.md)
   + [ドメイン](../technotes/domains.md)
   + [用語集](../technotes/glossary.md)
   + [ガードレール](../technotes/guardrails.md)
   + [IP アドレス](../technotes/ip-addresses.md)
   + [パフォーマンスの最適化](../technotes/optimizing-performance.md)
   + [使用状況の管理](../technotes/estimate-usage.md)

+ [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)
