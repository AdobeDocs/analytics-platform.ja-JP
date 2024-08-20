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
source-git-commit: 056c23c584823c7b3633d04585d15197692a2ee2
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 98%

---


# Adobe Customer Journey Analytics ガイド {#using}

+ [Adobe Customer Journey Analytics ガイド](../getting-started/cja-landing.md)
+ [Adobe Customer Journey Analytics 向けの AI アシスタント](../ai-assistant.md)
+ リリースノート {#releases}
   + [最新リリース](../release-notes/latest.md)
   + [2024年リリース](../release-notes/2024.md)
   + [2023年リリース](../release-notes/2023.md)
   + [2022年リリース](../release-notes/2022.md)
   + [2021年リリース](../release-notes/2021.md)
   + [2020年リリース](../release-notes/2020.md)
   + [機能リリース戦略](../release-notes/releases.md)
   + [ドキュメントのアップデート](../release-notes/doc-changes.md)

+ はじめに {#cja-overview}
   + [Customer Journey Analytics の概要](../getting-started/cja-overview.md)
   + [クイックスタートガイド](../getting-started/cja-getting-started.md)
   + [ランディングページ](../getting-started/landing.md)
   + [ランディングページ（旧）](../getting-started/cja-landing-old.md)
   + [よくある質問](../getting-started/cja-faq.md)
   + [Customer Journey Analytics と BI ソリューションの比較](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics と Adobe Analytics {#compare-aa-cja}
   + Customer Journey Analytics にアップグレード {#upgrade-to-cja}
      + [基本を学ぶ](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [アップグレードパスの選択](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Platform にデータを送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [履歴データの保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
   + Adobe Analytics との比較 {#cja-aa-comparison}
      + [概要](../getting-started/aa-vs-cja/overview.md)
      + [Adobe Analytics データの Customer Journey Analytics での使用](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Customer Journey Analytics の機能のサポート](../getting-started/aa-vs-cja/cja-aa.md)
      + [Analytics ソースコネクタを通じて渡された Analytics データに関する用語を比較](../getting-started/aa-vs-cja/terminology.md)
      + [Adobe Analytics と Customer Journey Analytics におけるデータ処理の比較](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [仮想レポート環境とサンドボックス環境](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [処理ルール、VISTA および分類とデータ準備の比較](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Adobe Analytics からの進化](../getting-started/aa-to-cja.md)
   + [Adobe Analytics ユーザー向けユーザーガイド](../getting-started/aa-to-cja-user.md)

+ データ取り込み {#cja-data-ingestion}
   + [データ取り込みの概要](../data-ingestion/data-ingestion.md)
   + 取り込みと使用のクイックスタートガイド{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Adobe Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [Server API](../data-ingestion/serverapi.md)
      + [バッチデータ](../data-ingestion/batch.md)
      + [ストリーミングデータ](../data-ingestion/streaming.md)
      + [ソースコネクタ](../data-ingestion/sources.md)

+ 接続 {#cja-connections}
   + [接続の概要](../connections/overview.md)
   + [接続の作成または編集](../connections/create-connection.md)
   + [接続の管理](../connections/manage-connections.md)
   + [組み合わせイベントデータセット](../connections/combined-dataset.md)
   + [標準検索](../connections/standard-lookups.md)
   + [B2B ルックアップ](../connections/transform-datasets-b2b-lookups.md)

+ データビュー {#cja-dataviews}
   + [データビューの概要](../data-views/data-views.md)
   + [データビューの作成または編集](../data-views/create-dataview.md)
   + [セッション設定](../data-views/session-settings.md)
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
      + [概要データグループ](../data-views/component-settings/summary-data-group.md)
      + [値のバケット化](../data-views/component-settings/value-bucketing.md)
   + [標準コンポーネントリファレンス](../data-views/component-reference.md)
   + [BI 拡張機能](../data-views/bi-extension.md)
   + [派生フィールド](../data-views/derived-fields/derived-fields.md)
   + [概要データ](../data-views/summary-data.md)
   + [ラベルとポリシー](../data-views/data-governance.md)

+ Workspace プロジェクト {#cja-workspace}
   + [Analysis Workspace の概要](../analysis-workspace/home.md)
   + [基本分析の実行](../analysis-workspace/perform-basic-analysis.md)
   + [アドバンス分析の実行](../analysis-workspace/perform-adv-analysis.md)
   + プロジェクト {#build-workspace-project}
      + [プロジェクトの概要](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [プロジェクトの作成](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [プロジェクトの保存](../analysis-workspace/build-workspace-project/save-projects.md)
      + [プロジェクトの目次](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)
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
         + [フリーフォームテーブルでディメンションのハイパーリンクを作成する](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
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
      + [メディア分平均オーディエンスパネル](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [クイックインサイトパネル](../analysis-workspace/c-panels/quickinsight.md)
      + [メディアの同時視聴者数パネル](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [メディア再生滞在時間パネル](../analysis-workspace/c-panels/media-playback-time-spent.md)
   + プロジェクトのキュレーション、共有、スケジュール {#curate-share}
      + [共有メニュー](../analysis-workspace/curate-share/send-schedule-files.md)
      + [プロジェクトのキュレーション](../analysis-workspace/curate-share/curate.md)
      + [プロジェクトの共有](../analysis-workspace/curate-share/share-projects.md)
      + [共有可能なリンクの作成](../analysis-workspace/curate-share/shareable-links.md)
      + [表示専用プロジェクト](../analysis-workspace/curate-share/view-only-projects.md)
   + 書き出し {#export}
      + [書き出しの概要](../analysis-workspace/export/export-project-overview.md)
      + [ダウンロード](../analysis-workspace/export/download-send.md)
      + [その他に送信](../analysis-workspace/export/t-schedule-report.md)
      + [クラウドへの書き出し](../analysis-workspace/export/export-cloud.md)
   + 異常値検出 {#anomaly-detection}
      + [異常値検出の概要](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [Analysis Workspace での異常値の表示](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [異常値検出で使用される統計的手法](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + 予測 {#forecasting}
      + [予測の概要](../analysis-workspace/c-forecast/forecasting.md)
      + [Analysis Workspace での予測表示](../analysis-workspace/c-forecast/view-forecasts.md)
      + [予測サービスで使用される統計的手法](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [ユーザー環境設定](../analysis-workspace/user-preferences.md)
   + Workspace FAQ {#workspace-faq}
      + [よくある質問](../analysis-workspace/workspace-faq/faq.md)
      + [エラーメッセージ](../analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace の制限](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [管理要件](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Analysis Workspace のアクセシビリティ](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Analytics ダッシュボード {#cja-dashboards}
   + [Analytics ダッシュボード - 概要](../mobile-app/home.md)
   + [キュレータータスク](../mobile-app/curator.md)
   + [モバイルスコアカードの作成](../mobile-app/create-scorecard.md)
   + [モバイルスコアカードの管理](../mobile-app/manage-scorecard.md)
   + [ダッシュボードを使用するエグゼクティブの設定](../mobile-app/set-up-execs.md)
   + [エグゼクティブユーザー向けクイックスタートガイド](../mobile-app/executive.md)

+ ガイド付き分析 {#guided-analysis}
   + [概要](../guided-analysis/overview.md)
   + 機能マトリックス {#feature-matrix}
      + [エンゲージメント](../guided-analysis/types/engagement.md)
   + ファネル {#funnel}
      + [フリクションビュー](../guided-analysis/types/friction.md)
      + [コンバージョントレンドビュー](../guided-analysis/types/conversion-trends.md)
   + 影響 {#impact}
      + [リリースビュー](../guided-analysis/types/release.md)
      + [初回使用ビュー](../guided-analysis/types/first-use.md)
   + 保持 {#retention}
      + [リテンション率](../guided-analysis/types/retention-rates.md)
   + トレンド {#trends}
      + [使用状況ビュー](../guided-analysis/types/usage.md)
      + [頻度ビュー](../guided-analysis/types/frequency.md)
   + ユーザーの増加率 {#user-growth}
      + [アクティブビュー](../guided-analysis/types/active.md)
      + [純増加率ビュー](../guided-analysis/types/net-growth.md)
   + ユーザーストリーム {#streams}
      + [タイムライン](../guided-analysis/types/timeline.md)
   + [業界ユースケース](../guided-analysis/industry-use-cases.md)
   + [FAQ](../guided-analysis/faq.md)

+ コンポーネント {#cja-components}
   + [コンポーネントの概要](../components/overview.md)
   + [Analysis Workspace でのコンポーネントの使用](../components/use-components-in-workspace.md)
   + [コンポーネントの説明の追加](../components/add-component-descriptions.md)
   + 注釈 {#annotations}
      + [注釈の概要](../components/annotations/overview.md)
      + [注釈を作成](../components/annotations/create-annotations.md)
      + [注釈を管理](../components/annotations/manage-annotations.md)
      + [注釈を表示](../components/annotations/view-annotations.md)
      + [モバイル注釈](../components/annotations/mobile-annotations.md)
   + [スケジュール済みプロジェクト](../components/scheduled-projects-manager.md)
   + オーディエンス {#audiences}
      + [オーディエンスの概要](../components/audiences/audiences-overview.md)
      + [オーディエンスの作成と公開](../components/audiences/publish.md)
      + [オーディエンス管理](../components/audiences/manage.md)
   + ディメンション {#dimensions}
      + [ディメンションの概要](../components/dimensions/overview.md)
      + [ディメンションのプレビュー](../components/dimensions/view-dimensions.md)
      + [ディメンションの分類](../components/dimensions/t-breakdown-fa.md)
      + [時間分割ディメンション](../components/dimensions/time-parting-dimensions.md)
      + [基数が非常に高いディメンション](../components/dimensions/high-cardinality.md)
   + [指標](../components/apply-create-metrics.md)
   + フィルター {#cja-filters}
      + [フィルターの概要](../components/filters/filters-overview.md)
      + [フィルターの作成](../components/filters/create-filters.md)
      + [順次フィルターの作成](../components/filters/seg-sequential-build.md)
      + [フィルターの共有](../components/filters/filters-share.md)
      + [タグフィルター](../components/filters/filters-tag.md)
      + [フィルターリストのフィルタリング](../components/filters/filters-filter.md)
      + [フィルターのお気に入りへの登録](../components/filters/filters-favorite.md)
      + [フィルターの承認](../components/filters/filters-approve.md)
      + [フィルターのコピー](../components/filters/filters-copy.md)
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
         + [パーティシペーション指標の作成](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [フィルタリングされた指標](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [フィルターの積み重ねと置き換え](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [フィルター適用済み指標と重み付け指標](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [計算指標をフィルタリング](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [計算指標をお気に入りに登録](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [計算指標をコピー](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [関数の使用](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [計算指標をタグ付け](../components/calc-metrics/cm-workflow/cm-tagging.md)
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
   + 書き出し {#exports}
      + [クラウドの書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)
      + [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md)
      + [クラウドの書き出し場所の管理](/help/components/exports/manage-export-locations.md)
      + [書き出しの管理](/help/components/exports/manage-exports.md)
      + [書き出しログの管理](/help/components/exports/manage-export-logs.md)
      + [書き出しのトラブルシューティング](/help/components/exports/troubleshoot-exports.md)
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

+ レポートアクティビティマネージャー {#reporting-activity-manager}
   + [概要](../reporting-activity-manager/reporting-activity-overview.md)
   + [レポートアクティビティの表示](../reporting-activity-manager/reporting-activity.md)
   + [レポートリクエストのキャンセル](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ ステッチ {#stitching}
   + [概要](../stitching/overview.md)
   + [ステッチされたデータセットの作成と管理](../stitching/stitching-ui.md)
   + [よくある質問](../stitching/faq.md)

+ アドビの統合 {#integrations}
   + [概要](/help/integrations/overview.md)
   + [Adobe Analytics の統合](/help/integrations/aa.md)
   + [Target の統合](/help/integrations/at.md)
   + [Journey Optimizer データの統合](/help/integrations/ajo.md)
   + [意思決定管理データの統合](/help/integrations/ajo-od.md)
   + [顧客 AI の統合](/help/integrations/customer-ai.md)

+ データガバナンス {#cja-privacy}
   + [データガバナンス](../privacy/privacy-overview.md)
   + [監査ログ](../privacy/audit-log.md)
   + [顧客管理キー](../privacy/cmk.md)

+ ユースケース {#cja-usecases}
   + [Customer Journey Analytics のユースケース](../use-cases/cja-usecases.md)
   + Google Analytics データ {#ga}
      + [Google Analytics から Customer Journey Analytics へのデータ移行の概要](../use-cases/ga/overview.md)
      + [Platform への Google Analytics 履歴データの取り込み](../use-cases/ga/backfill.md)
      + [Platform への Google Analytics データのストリーミングの設定](../use-cases/ga/streaming.md)
      + [Customer Journey Analytics での Google Analytics データに関するレポート](../use-cases/ga/report.md)
   + データ取り込み {#data-ingestion}
      + [Marketo Engageデータの取り込みと使用](../use-cases/data-ingestion/marketo.md)
      + [Experience Platformオーディエンスの取り込みと使用](../use-cases/data-ingestion/ingest-aep-segments.md)
   + データビュー {#data-views}
      + [データビューのユースケース](../use-cases/data-views/data-views-usecases.md)
      + [バインディングディメンションと指標の使用](../use-cases/data-views/binding-dimensions-metrics.md)
      + [概要データの使用](../use-cases/data-views/summary-data.md)
   + データの書き出し {#data-export}
      + [概要](../use-cases/data-export/overview.md)
      + [BI 拡張機能](../use-cases/data-export/bi-extension.md)
      + [データセットの書き出し](../use-cases/data-export/export-datasets.md)
      + [フルテーブルの書き出し](../use-cases/data-export/export-full-table.md)
      + [クエリサービスとデータセットの書き出し](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [B2B プロジェクトの例](../use-cases/b2b/example.md)
      + [アカウントレベルのデータをルックアップデータセットとして追加](../use-cases/b2b/b2b.md)
   + クロスチャネルデータ {#cross-channel}
      + [チャネルをまたいだデータの分析](../use-cases/cross-channel/cross-channel.md)
      + [コールセンターデータと web データの読み込み](../use-cases/cross-channel/call-center.md)
   + ステッチ {#stitching}
      + [共有デバイス](/help/use-cases/stitching/shared-devices.md)
   + Adobe Analytics データ {#aa-data}
      + [マーケティングチャネルディメンションの使用](../use-cases/aa-data/marketing-channels.md)
      + [スキーマの異なるレポートスイートの結合](../use-cases/aa-data/combine-report-suites.md)
   + 複雑なデータ {#complex-data}
      + [オブジェクトの配列の使用](../use-cases/object-arrays.md)
   + 派生フィールド {#derived-fields}
      + [派生フィールドを使用した目標に関するレポート](../use-cases/goals-using-derived-fields.md)

+ ラボ {#labs}
   + [ラボユーザーガイド](../labs/labs.md)

+ トラブルシューティング {#troubleshooting}
   + [Adobe Analytics データと Customer Journey Analytics データの比較](../troubleshooting/compare.md)
   + [Real-Time CDP と Customer Journey Analytics 間の指標およびオーディエンスメンバーシップカウントの一貫性](../troubleshooting/consistency-rcdp-cja.md)
   + [権限の不足](../troubleshooting/lack-of-permissions.md)

+ テクニカルノート {#technotes}
   + [アクセス制御](../technotes/access-control.md)
   + [データセンター](../technotes/data-centers.md)
   + [削除の影響](../technotes/deletion.md)
   + [ドメイン](../technotes/domains.md)
   + [用語集](../technotes/glossary.md)
   + [ガードレール](../technotes/guardrails.md)
   + [IP アドレス](../technotes/ip-addresses.md)
   + [Customer Journey Analytics のパフォーマンスの最適化](../technotes/optimizing-performance.md)
   + [使用状況の表示と管理](../technotes/estimate-usage.md)

+ [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)
