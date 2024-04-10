---
title: Customer Journey Analytics ドキュメントの更新
description: 2019年12月以降の Customer Journey Analytics ドキュメントセットのアップデートについて説明します。
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: 3ca28d9c9f1c6a9e14ce4c9080bd180a5699ad5b
workflow-type: tm+mt
source-wordcount: '3290'
ht-degree: 76%

---

# Customer Journey Analytics - ドキュメントのアップデート

Customer Journey Analytics ドキュメントには、初回リリース以降に次の更新が行われました。

## 2024

| 機能 | 説明 |
| --- | --- |
| **2024 年 4 月** | |
| 統計的手法の予測 | を説明する記事を追加しました [予測サービスで使用される統計的手法](../analysis-workspace/c-forecast/statistics-forecasting.md). |
| 基数の高いディメンションに対して完全なテーブル書き出しを推奨する情報を追加しました | に箇条書きを追加しました [基数の高いディメンションのベストプラクティス](/help/components/dimensions/high-cardinality.md) カーディナリティの高いディメンションに対して完全テーブル書き出しを使用することをお勧めします。 |
| **2024年3月** | |
| 「使用場所」列に関する使用状況情報は、2023年9月以降のみ使用可能です。 | [プロジェクトのランディングページ](/help/getting-started/landing.md)の&#x200B;**使用場所**&#x200B;列に関する使用状況情報は、2023年9月までしか遡らないことを明確にしました。 |
| **2024年2月** | |
| プロジェクト共有ドキュメントの更新 | 方法に関する情報を追加しました [自分と共有されているプロジェクトを表示する](/help/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you).<p>また、[個々または複数のプロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role)に関する情報も整理しました。</p> |
| クラウド書き出し場所を設定する際に、Azure SAS と Azure RBAC にファイルをアップロードするための権限要件を追加しました | 次の場合に Azure SAS と Azure RBAC にファイルをアップロードするための正確な権限要件を追加しました [クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md) および [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md). |
| クラウド書き出しの場所を設定する際に、Amazon S3 ロール ARN および GCP バケットにファイルをアップロードするための権限要件を追加しました | 次の場合にAmazon S3 ロール ARN およびGoogle Cloud Platform バケットにファイルをアップロードするための正確な権限要件を追加しました [クラウドの書き出し場所の設定](/help/components/exports/cloud-export-locations.md). |
| 製品管理者が常にすべてのテーブルをエクスポートするためのアクセス権を持っていることを明確にしました | 製品管理者の役割を割り当てられたユーザーが、デフォルトでAnalysis Workspaceからすべてのテーブルを書き出すためのアクセス権を持つことを明確にするために、次の変更を加えました。 <ul><li>に新しい箇条書きを追加しました。 [製品管理者のデフォルトの権限](/help/admin/cja-access-control.md#product-admin-default-permissions).</li><li>の下にメモを追加しました [完全なテーブルをクラウドに書き出すための最小要件](/help/analysis-workspace/export/export-cloud.md#minimum-requirements).</li></ul> |
| Adobe Analyticsからのコンポーネント移行中にセグメントが再作成されることを明確にしました | が含まれる [Adobe Analytics ユーザー向けユーザーガイド](/help/getting-started/aa-to-cja-user.md)を使用する場合、コンポーネントの移行プロセスの一環としてAdobe Analyticsでセグメントが自動的に再作成され、手動で再作成する必要がないことを明確にしました。 |
| スキップされたレコードの詳細 | 接続のスキップされたレコードの詳細機能に関するドキュメントを追加しました。 詳しくは、[接続の詳細](../connections/manage-connections.md#connection-details)を参照してください。 |
| **2024年1月** | |
| 予測 | のドキュメントを追加しました [予測](../analysis-workspace/c-forecast/forecasting.md)は、フリーフォームテーブルおよび折れ線グラフでサポートされる任意の時間精度（時間別、日別、週別、月別、年別）で標準指標または計算指標を予測する、Analysis Workspaceの新しい機能です。 |
| フルテーブルを書き出す際のアカウントと場所の追加に関するドキュメントを更新しました | 新しいアカウントまたは場所を設定する際のマイナーインターフェイスの更新を反映するように、ドキュメントを更新しました。 [Analysis Workspaceからの完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace).<p>新品 [!UICONTROL **アカウントを追加**] オプションが [!UICONTROL **アカウント**] ドロップダウンメニュー。 この [!UICONTROL **場所を追加**] 以前は横のボタンとして使用できたオプション [!UICONTROL **場所名**] ドロップダウンメニューがメニュー自体の中で使用できるようになりました。 |
| Adobe Analyticsから移行する際の新しいコンポーネントの移行情報 | に情報を追加しました [Adobe Analyticsからの進化](/help/getting-started/aa-to-cja.md) 新しいを参照する [コンポーネントの移行](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=ja) Adobe Analytics管理ガイドに記載されている機能。 |
| 特定の情報は管理者のみが利用できることを明確化 | で説明されている「前回の使用」列と「使用された場所」列を示す情報を追加しました [計算指標マネージャー](/help/components/calc-metrics/cm-workflow/cm-manager.md) および [フィルターマネージャー](/help/components/filters/manage-filters.md) は、システム管理者のみが使用できます。 |
| データセットのエクスポートに必要な権限 | の説明を追加しました [必要な権限](/help/admin/cja-access-control.md) で、データセットをクラウド宛先に書き出します。 |
| 接続の管理 | が更新されました [接続の管理](../connections/manage-connections.md) お客様からのフィードバックに基づいた記事。 |
| 派生フィールド | 関数の概要を追加しました [制限事項](/help/data-views/derived-fields/derived-fields.md#limitations) 次の数を決定する方法の説明 [演算子](/help/data-views/derived-fields/derived-fields.md#operators) 関数で使用されます。 |

{style="table-layout:auto"}


## 2023年

| 機能 | 説明 |
| --- | --- |
| **2023年12月** | |
| データセンター | Customer Journey Analyticsに関する記事を追加しました [ホスティングの場所](../technotes/cja-datacenters.md). |
| ガードレール | 記事一覧Customer Journey Analyticsを追加しました [ガードレール](../admin/guardrails.md). |
| 通貨換算の更新 | 方法に関するドキュメントを明確にしました。 [通貨換算の設定](/help/data-views/component-settings/format.md). |
| 異常値検出ドキュメントの更新 | 異常値検出のドキュメントは、以前は Virtual Analyst に関する節に記載されていました。 次の変更を行いました。 <ul><li>Virtual Analyst という用語はドキュメントから削除しました。</li><li>[異常値検出](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)に関する節は、Analysis Workspace の節のすぐ下に移動しました。</li></ul> |
| **2023年10月** | |
| 派生フィールドを使用した目標/ターゲットの設定 | 追加済み [ユースケース](../use-cases/goals-using-derived-fields.md) 目標/ターゲットを設定し、これらに関するレポートを作成するために、派生フィールドを使用する方法を説明する記事。 |
| 完全なテーブルをクラウドに書き出す | 数百万の Workspace 行を含んだ完全なテーブルのクラウド宛先への書き出しに関するドキュメントを追加しました。 <p>完全なテーブルを書き出すと、Workspace 内で設計されたデータテーブルを 1 回限りまたは予定どおりに配信でき、連結されたテーブルで、最大 5 つの分類、5 つの指標、フィルター、計算指標をすべてサポートします。これは、Adobe Analytics のデータウェアハウスレポートの進化版で、現在のデータウェアハウスでは利用できない、リクエストの多い新機能が多数追加されています。</p><p>詳しくは、[Customer Journey Analytics レポートをクラウドに書き出し](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=ja)を参照してください。 |
| レポートアクティビティマネージャー | レポートアクティビティマネージャーに関するドキュメントを追加しました。 <p>レポートアクティビティマネージャーでは、組織内の各接続のレポート処理能力を確認できます。管理者はレポートの使用状況を詳細に把握できるため、ピーク時のレポート作成時の容量に関する問題を容易に診断および修正できます。</p> <p>次の新しい記事が追加されました。<ul><li>[レポートアクティビティマネージャーの概要](/help/reporting-activity-manager/reporting-activity-overview.md)</li><li>[レポートアクティビティマネージャーでのレポートアクティビティの表示](/help/reporting-activity-manager/reporting-activity.md)</li><li>[レポートアクティビティマネージャーでのリクエストのキャンセル](/help/reporting-activity-manager/reporting-activity-cancel-requests.md)</ul> |
| 管理ページの新しい列 | で利用できるようになったドキュメント化された新しい列 [計算指標マネージャー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=ja) および [フィルターマネージャー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=ja). |
| Adobe Analytics との比較 | さんがを追加しました [概要ページ](../getting-started/aa-vs-cja/overview.md) Customer Journey AnalyticsとAdobe Analyticsの違いの比較と理解に関する概要です。 |
| その他の派生フィールド機能 | 新しいのドキュメントを更新しました [`Lookup`](/help/data-views/derived-fields/derived-fields.md#lookup) 関数。 |
| **2023年9月** | |
| メディア再生滞在時間パネルの記事の構造を更新しました。 | メディア再生滞在時間というフォルダーを削除し、フォルダーの内容を 1 つの記事である[メディア再生滞在時間](/help/analysis-workspace/c-panels/media-playback-time-spent.md)パネルに統合しました。 <p>この変更は、その他のパネルのドキュメントに沿ったものになります。</p> |
| その他の派生フィールド機能 | 新しい [`Lowercase`](/help/data-views/derived-fields/derived-fields.md#lowercase) 関数および [`Trim`](/help/data-views/derived-fields/derived-fields.md#trim) 関数と、[`Classify`](/help/data-views/derived-fields/derived-fields.md#classify) 関数に追加したその他の CSV 機能に関するドキュメントを更新しました。 |
| 地域データ収集 | [FAQ](../getting-started/cja-faq.md#12-regional-data-collection) を更新し、Customer Journey Analytics を使用する際の地域データ収集に関する情報を追加しました。 |
| **2023年8月** | |
| メディア再生滞在時間パネル | 読みやすさを向上させるために、[メディア再生滞在時間パネル](/help/analysis-workspace/c-panels/media-playback-time-spent.md)のコンテンツを更新しました。 |
| Report Builder の機能強化 | スケジュールされたタスクをダウンロードするための情報を提供するために、[ワークブックのスケジュール設定](/help/report-builder/schedule-reportbuilder.md)のコンテンツを更新しました。開始日をディメンションとして使用するための情報を提供するために、[データブロックの作成](/help/report-builder/create-a-data-block.md)のコンテンツを更新しました。 |
| スケジュールされたプロジェクトの管理に関するコンテンツの移動 | Analytics コンポーネントガイドに[スケジュールされたプロジェクト](/help/components/scheduled-projects-manager.md)という新しい記事を作成しました。このコンテンツは、以前は Analytics ツールガイドの[プロジェクトのスケジュール](/help/analysis-workspace/export/t-schedule-report.md)という記事に記載されていました。 |
| Adobe Customer Journey Analytics の機能のサポート | *新しい方法でサポート*&#x200B;の表に、Adobe Analytics と比較した Customer Journey Analytics のセッション機能に関する詳細情報を追加しました。[詳細情報](../getting-started/aa-vs-cja/cja-aa.md#supported-in-a-new-way) |
| Adobe Analytics からの進化 | 派生フィールドのマーケティングチャネル関数テンプレートへの参照を含めて、*マーケティングチャネルの（再）設定*&#x200B;の節を更新しました。[詳細情報](../getting-started/aa-to-cja.md#3-reconfigure-your-marketing-channels) |
| モバイルアプリケーションおよびその他のプラットフォームのデータ取り込みクイックスタートガイド | Customer Journey Analytics でモバイルアプリケーションやその他のプラットフォーム（デスクトップアプリケーション、コンソール上のゲーム、セットトップボックスや IoT デバイス上のアプリケーションなど）からデータを取り込んで使用する方法を説明するデータ取り込みクイックスタートガイドを追加しました。[詳細情報](../data-ingestion/data-ingestion.md) |
| **2023年7月** | |
| セッション設定 | このデータビュー設定に関するトピックを追加しました。[詳細情報](/help/data-views/session-settings.md) |
| Adobe Product Analytics | Adobe Product Analytics は、Customer Journey Analytics でクロスチャネルのデータやインサイトを操作する新しい方法です。これらの新機能により、製品チームは、[ガイド付き分析](/help/guided-analysis/overview.md)ワークフローを通じて、製品エクスペリエンスに関するデータとインサイトをセルフサービスで提供できるようになります。 |
| 派生フィールド | [派生フィールド](/help/data-views/derived-fields/derived-fields.md)を使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。 |
| プロファイルデータやルックアップデータへのルックアップサポートの拡張 | プロファイルデータセットまたはルックアップデータセット内のフィールドのルックアップとしてデータセットを追加できるようになります。これまでは、イベントデータセットのみがサポートされていました。[詳細情報](/help/connections/create-connection.md) |
| Report Builder の機能強化 | <ul><li>[セルからの複数データブロックのフィルタリング](/help/report-builder/select-data-view.md)</li><li>[行ヘッダーと列ヘッダーの表示／非表示の切り替え](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=ja#build-the-data-block)</li></ul> |
| Edge ネットワーク位置情報検索 | [データストリーム設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja) では、統一された地理データを提供する地理検索サービスをどのようにして提供するのでしょうか。 |
| **2023年6月** | |
| クロスチャネル分析とステッチ | ステッチを有効にするための変更と、ステッチを使用してクロスチャネル分析を向上させる方法をさらに明確にするための変更が今後見込まれるので、クロスチャネル分析機能に関連するドキュメントを編集して、[クロスチャネル分析](../use-cases/cross-channel/cross-channel.md)を Customer Journey Analytics の機能およびユースケースとして、また、[ステッチ](../stitching/overview.md)をそれを実現するための重要な機能として取り上げています。 |
| Power BI および Tableau から Customer Journey Analytics データビューへのアクセス | Customer Journey AnalyticsBI 拡張機能を使用すると、Customer Journey Analyticsで定義したデータビューへの SQL アクセスが可能になります。 [詳細情報](/help/data-views/bi-extension.md) |
| Adobe Journey Optimizer データビュー | Customer Journey Analytics 管理者は、「AJO データビュー (サンドボックス名)」というタイトルの、Customer Journey Analytics のいくつかの追加データビューにアクセスできます。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html?lang=ja)。 |
| 通貨換算 | [通貨換算](../data-views/component-settings/format.md#currency)のサポートに関するドキュメントを更新しました。 |
| 計算指標の更新 | 現在の Customer Journey Analytics 機能と整合させるために、計算指標のドキュメントで次の更新を行いました。 <ul><li>Customer Journey Analytics で利用可能な[デフォルトの計算指標](/help/components/calc-metrics/default-calcmetrics.md)のリストを更新しました</li><li>様々な計算指標に関する記事のスクリーンショットと手順を更新しました </li></ul> |
| **2023年5月** | |
| ディープリンク（モバイルアプリ）ドキュメント | ユーザーが、アプリ内のスコアカードプロジェクトに直接アクセスできるスコアカードへのリンクを送信できるようにします。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ja#share-scorecards-using-a-shareable-link) |
| Report Builder の「セルからデータビューを選択」に関するドキュメント | この機能を使用すると、ユーザーはセルからデータブロックのデータビューを選択できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=ja) |
| Analytics ダッシュボードアプリ（モバイルアプリ）の更新されたホーム画面に関するドキュメント | 更新された新しいホーム画面では、すべてのスコアカードが、統合された 1 つのスコアカードリストに表示されます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=ja#use-dashboards) |
| 最適化の更新 | [Customer Journey Analytics のパフォーマンスの最適化](/help/admin/optimizing-performance.md)に関する記事を更新しました |
| Analysis Workspace の概要 | より一般的な概要情報と関連コンテンツへのリンクを含むように、[Analysis Workspace の概要](/help/analysis-workspace/home.md)の概要を更新しました。 |
| プロジェクトの作成 | Analysis Workspace で[プロジェクトの作成](/help/analysis-workspace/build-workspace-project/create-projects.md)を行う方法を詳しく説明する新しい記事を作成しました。 |
| 左側のパネルでのコンポーネントの並べ替え | 左側のパネルでのコンポーネントのリストの並べ替えに関する情報を追加しました。詳しくは、[コンポーネントの概要](/help/components/overview.md)の「コンポーネントリストの検索、フィルタリング、並べ替え」の節を参照してください。 |
| フリーフォームテーブルからの動的ディメンションを含む行の削除 | 「x」アイコンを使用して、動的ディメンションを含む特定の行をすばやく削除する方法に関する情報を追加しました。[テーブルのフィルタリングと並べ替え](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)の「テーブルから特定の行をすばやく除外する」の節を参照してください。 |
| パネル内にビジュアライゼーションを追加するボタン | Analysis Workspace の各パネルの下部にある、ビジュアライゼーションをすばやく追加できる新しいボタンに関する情報を追加しました。詳しくは、[ビジュアライゼーションの概要](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)の「パネルへのビジュアライゼーションの追加」の節を参照してください。 |
| インテリジェントキャプションドキュメント | 折れ線グラフのビジュアライゼーションの[自然言語による要約](/help/analysis-workspace/visualizations/intelligent-captions.md)を使用して、ユーザー向けのストーリーテリングを強化します。 |
| 派生フィールド | [派生フィールド](../data-views/derived-fields/derived-fields.md)機能のドキュメントを追加しました。 |
| **2023年4月** |  |
| フィルターをディメンションとして使用する方法に関するビデオ | フィルターをディメンションとして使用する方法に関するビデオを更新しました。 <p>このビデオは、[フィルターの作成](/help/components/filters/create-filters.md)ページからリンクされています。</p> <p>次に、[Analysis Workspace でフィルターをディメンションとして使用](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html?lang=ja)のビデオへの直接リンクを示します。</p> |
| フィルタードキュメント | [フィルタービルダー](/help/components/filters/filter-builder.md)を使用する方法に関する記事を追加しました。 <p>[フィルターの作成](/help/components/filters/create-filters.md)と[フィルターの概要](/help/components/filters/filters-overview.md)のドキュメントを合理化しました。</p> |
| 実験パネルのドキュメントの更新 | [非ランダム化ディメンションの解釈](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html#non-randomized)に関する節を追加しました。 |
| プロジェクトフィルター（アドホックおよびクイックフィルター） | プロジェクトフィルターに関するドキュメントを簡素化し、重複する情報を削除しました。アドホックフィルターの作成手順は、[クイックフィルターの作成](/help/components/filters/quick-filters.md)手順と統合しました。 |
| **2023年3月** | |
| 意思決定管理データの統合 | [Customer Journey Analytics での Adobe Journey Optimizer 意思決定管理データの統合](/help/integrations/ajo-od.md)方法を説明するコンテンツを追加しました。 |
| モバイルスコアカードでのデータストーリーの作成 | [データストーリー](/help/mobile-app/create-scorecard.md#create-data-stories)は、中心的なテーマや指標に基づいて作成された、サポート対象データポイント、ビジネスコンテキスト、関連指標のコレクションです。 |
| 更新された機能のサポート | [Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を更新して、Customer Journey Analytics で使用でき AA では使用できないかサポートされていない機能の一覧表を追加しました。 |
| デフォルトの計算指標 | [アドビが提供するデフォルトの計算指標](/help/components/calc-metrics/default-calcmetrics.md)を説明するコンテンツを追加しました。 |
| データ要素 | <p>データ要素の[概要](/help/components/data-dictionary/data-dictionary-overview.md)、[表示](/help/components/data-dictionary/view-data-dictionary.md)、[編集](/help/components/data-dictionary/edit-entries-data-dictionary.md)、[監視](/help/components/data-dictionary/monitor-data-dictionary-health.md)など、データ要素に関する新しいドキュメントを追加しました。</p><p>[コンポーネント説明の追加](/help/components/add-component-descriptions.md)の情報を、データ要素機能を説明するために更新しました。</p> |
| プロジェクトのリンク共有（ログインは不要） | <p>Analysis Workspace へのアクセス権を持たないユーザーとプロジェクトの読み取り専用リンクを共有する方法を説明するために、既存のドキュメントを更新しました。</p> <p>ユーザードキュメントの更新内容には、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)と[共有可能なリンクの作成](/help/analysis-workspace/curate-share/shareable-links.md)が含まれています。</p> <p>[環境設定](/help/analysis-workspace/user-preferences.md)に管理者向けのオプションを追加しました。</p> |
| **2023年2月** | |
| Customer Journey Analytics と BI ソリューションの比較 | Customer Journey Analytics と一般的な BI ソリューションの[比較](../getting-started/cja-vs-bi.md)に関する新しいドキュメントです。 |
| Audiences ドキュメントの更新 | [待ち時間に関する考慮事項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)に関する新しい節です。 |
| Audiences ドキュメントの更新 | オーディエンスを作成すると、[新しい Customer Journey Analytics オーディエンスごとに Experience Platform ストリーミングセグメントが作成](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=ja#after-audience-created)されます。 |
| Workspace のカレンダーと日付範囲 | 内容を更新して、相対的な日付範囲、数式計算の更新およびカレンダー UI の変更について説明しました。[パネルを基準とする相対的な日付範囲について](/help/components/date-ranges/calendar.md#relative-panel-dates)を参照してください。 |
| モバイルスコアカード | 比較日付範囲の表示／非表示を切り替える方法について説明する新しい節をドキュメントに追加しました。Customer Journey Analytics の[比較日付範囲の表示](/help/mobile-app/create-scorecard.md#show-comparison-dates)を参照してください。 |
| **2023年1月** | |
| テーブルのフィルタリングと並べ替え | [テーブルのフィルタリングと並べ替え](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)に関する記事の内容を更新しました（手順の追加や使用可能なオプションの説明など）。この記事の名前を「テーブルのページネーション、フィルタリングおよび並べ替え」から変更しました。 |
| データ取り込みクイックスタートガイド | Customer Journey Analytics での[データの取り込みと使用](/help/data-ingestion/data-ingestion.md)の方法に関する新しい節をドキュメントに追加しました。 |
| Workspace フォルダー | [フォルダー管理](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)の専用ページ。 |
| Workspace ユーザー環境設定 | 多くの追加のユーザー環境設定が[環境設定](/help/analysis-workspace/user-preferences.md)で使用できるようになりました。 |
| Workspace プロジェクトの自動保存 | 内容が更新されて、[プロジェクトの保存](/help/analysis-workspace/build-workspace-project/save-projects.md)に自動保存機能の説明が含まれるようになりました。 |
| ランディングページ | CJA の[ランディングページ](/help/getting-started/landing.md)が更新されました。 |
| ワークブックのスケジュール設定 | Report Builder で[ワークブックのスケジュールを設定](/help/report-builder/schedule-reportbuilder.md)する方法について説明する専用ページを追加しました。 |
| プロファイルおよびルックアップデータセットでのオブジェクト配列のサポート | [オブジェクトの配列の使用](/help/use-cases/object-arrays.md)および [Adobe Experience Platform オーディエンスの取り込み](/help/use-cases/data-ingestion/ingest-aep-segments.md)を更新して、プロファイルデータセットとルックアップデータセットでのオブジェクト配列のサポートを反映しました。 |

{style="table-layout:auto"}

## 2022

| 日付 | アップデートの内容 |
| --- | --- |
| **2022年12月** |  |
| 2022年12月16日（PT） | [Customer Journey Analytics データ使用状況の測定と管理](/help/admin/estimate-usage.md)に関する新しいトピック。 |
| **2022年10月** | |
| 2022年10月 | [スケジュール済みプロジェクトのパスワード保護](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=ja#password)に関する新しいトピック。この機能は、[HIPAA 対応](https://www.adobe.com/trust/compliance/hipaa-ready.html)をサポートしています。 |
| 2022年10月 | [顧客管理キー](/help/privacy/cmk.md)に関する新しいトピック。この機能は、[HIPAA 対応](https://www.adobe.com/trust/compliance/hipaa-ready.html)をサポートしています。 |
| 2022年10月 | [Customer Journey Analytics 監査ログ](/help/privacy/audit-log.md)に関する新しいトピック。 |
| 2022年10月 | [主要な指標の概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=ja)ビジュアライゼーションに関する新しいトピック。 |
| 2022年10月 | [データビューの日付と日時の機能](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#date)に関する新しい節 |
| 2022年10月 | モバイルアプリ：[カスタム詳細ビュー](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#view-detail-slides)に関する新しいトピック。 |
| 2022年10月 | [Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)トピックを更新しました。 |
| **2022年9月** | |
| 2022年9月 | [Google Analytics データの Customer Journey Analytics への移行](/help/use-cases/ga/overview.md)に関する新しいユースケース。 |
| 2022年9月 | Workspace の[複合グラフ](/help/analysis-workspace/visualizations/combo-charts.md)に関する新しいトピック。 |
| 2022年9月 | Workspace の[実験パネル](/help/analysis-workspace/c-panels/experimentation.md)に関する新しいトピック。 |
| **2022年8月** | |
| 2022年8月 | [Analytics ソースコネクタのクロス地域サポート](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)に関する Adobe Experience Platform の記事。 |
| 2022年8月 | [Customer Journey Analytics のアクセス制御](/help/admin/cja-access-control.md)に関する記事の大幅な更新。 |
| 2022年8月 | [Customer Journey Analytics でのデータガバナンスラベルおよびポリシーのサポート](/help/data-views/data-governance.md)に関する新しい記事。 |
| 2022年8月 | [Analytics ソースコネクタを通じて渡された Analytics データに関する用語の比較](/help/getting-started/aa-vs-cja/terminology.md)に関する新しい記事。 |
| 2022年8月 | に関する新しいドキュメント [リアルタイム顧客プロファイルへのオーディエンス公開](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=ja). |
| **2022年7月** | |
| 2022年7月 | [メディア再生滞在時間パネル](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=ja)に関するドキュメント。 |
| 2022年7月 | [メディア同時視聴者数パネル](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=ja)に関するドキュメント。 |
| 2022年7月 | [初回セッション](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ja#new-repeat)のレポートドキュメント。 |
| **2022年6月** | |
| 2022年6月 | [AAID、ECID、AACUSTOMID および Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=ja)に関する新しい記事。 |
| 2022年6月 | [Adobe Analytics 処理ルール、VISTA および分類と Analytics ソースコネクタのデータ準備の比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)に関する新しい記事。 |
| 2022年6月 | についての新しい記事 [仮想レポート環境とサンドボックス環境](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md). |
| 2022年6月 | [Adobe Analytics と Customer Journey Analytics のレポート機能におけるデータ処理の比較](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)に関する新しい記事。 |
| 2022年6月 | についての新しい記事 [レポートスイートと様々なスキーマの組み合わせ](/help/use-cases/aa-data/combine-report-suites.md). |
| 2022年6月 | についての新しい記事 [モバイルスコアカードでの注釈の共有](/help/components/annotations/mobile-annotations.md). |
| 2022年6月 | [Customer Journey Analytics の Analytics ラボ](/help/labs/labs.md)に関する新しい記事。 |
| 2022年6月 | に関する新しい節 [ルックアップキーおよびルックアップ値としての数値フィールドの使用のサポート](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#numeric). |
| 2022年6月 | 「」に対する更新 [フロービジュアライゼーションワークフロー](/help/analysis-workspace/visualizations/c-flow/create-flow.md). |
| **2022年5月** | |
| 2022年5月 | Customer Journey Analytics での[接続の作成](/help/connections/create-connection.md)に関する記事の大幅な更新。 |
| 2022年5月 | [Customer Journey Analytics の Report Builder におけるデータブロックの管理](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=ja)方法に関する新しい記事。 |
| 2022年5月 | [Adobe Experience Platform オーディエンスの Customer Journey Analytics への取り込み](/help/use-cases/data-ingestion/ingest-aep-segments.md)に関する新しい記事。 |
| **2022年4月** | |
| 2022年4月 | [ディメンションの部分文字列](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=ja)に関するドキュメント。 |
| 2022年4月 | [Adobe Analytics ユーザー向けの Customer Journey Analytics ユーザーガイド](/help/getting-started/aa-to-cja-user.md)（新規）。 |
| **2022年3月** | |
| 2022年3月 | [Customer Journey Analytics Annotations API ドキュメント](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)（新規）。 |
| 2022年3月 | [ワークスペースでの注釈](/help/components/annotations/overview.md)に関するドキュメント（新規）。 |
| 2022年3月 | [接続サイズの予測](/help/getting-started/cja-faq.md)に関するコンテンツの大幅な更新。 |
| **2022年2月** | |
| 2022年2月 | Adobe Analytics から Customer Journey Analytics に移行する管理者を対象とした新しいガイド：[Adobe Analytics から Customer Journey Analytics への進化](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=ja) |
| **2022年1月** | |
| 2022年1月 | [Customer Journey Analytics でのバインディングディメンションと指標の使用](/help/use-cases/data-views/binding-dimensions-metrics.md)の新しいユースケース |
| 2022年1月 | [バインディングディメンションと指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)、および新しい[[!UICONTROL 最初の事例]と[!UICONTROL 最後の事例]の配分設定](/help/data-views/component-settings/persistence.md#allocation-settings)に関する新機能のドキュメントを追加しました |
| 2022年1月 | [Adobe Analytics データと Customer Journey Analytics の Analytics データの比較](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=ja)に関する新しい記事 |

{style="table-layout:auto"}

## 2021

| 日付 | アップデートの内容 |
| --- | --- |
| **2021年11月** | |
| 2021年11月 | 接続の詳細ページの「[[!UICONTROL スキップされたレコード]](/help/connections/manage-connections.md)」のドキュメントを更新しました。 |
| **2021年10月** | |
| 2021年10月 | Customer Journey Analytics の [Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/report-buider-overview.html?lang=ja#) のドキュメント。 |
| 2021年10月 | Customer Journey Analytics [監査ログ](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) API ドキュメント |
| 2021年10月 | ドキュメント化した [Analytics ダッシュボードのビジュアライゼーション](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ja#apply-visualizations) |
| 2021年10月 | [!UICONTROL 接続][データ保持](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ja#set-rolling-window-for-connection-data-retention)のためのローリングウィンドウ（相対期間）のドキュメント。 |
| **2021年9月** | |
| 2021年9月 | [指標の重複排除](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=ja)ドキュメント |
| 2021年9月 | [レポートでの夏時間のサポート](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja#calendar) |
| 2021年9月 | [顧客カレンダー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja#calendar)ドキュメント |
| 2021年9月 | [ブール値フィールド](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/behavior.html?lang=ja)ドキュメント |
| 2021年9月 | データビューのコンポーネント設定を個々のファイルに分割しました。<ul><li>[[!UICONTROL コンポーネント]設定の概要](/help/data-views/component-settings/overview.md)</li><li>[[!UICONTROL アトリビューション] コンポーネントの設定](/help/data-views/component-settings/attribution.md)</li><li>[[!UICONTROL 動作] コンポーネントの設定](/help/data-views/component-settings/behavior.md)</li><li>[[!UICONTROL 形式] コンポーネントの設定](/help/data-views/component-settings/format.md)</li><li>[[!UICONTROL 含む／除外] コンポーネントの設定](/help/data-views/component-settings/include-exclude-values.md)</li><li>[[!UICONTROL 指標の重複排除] コンポーネントの設定](/help/data-views/component-settings/metric-deduplication.md)</li><li>[[!UICONTROL 値なし] コンポーネントの設定](/help/data-views/component-settings/no-value-options.md)</li><li>[[!UICONTROL 永続性]コンポーネント設定](/help/data-views/component-settings/persistence.md)</li><li>[[!UICONTROL 値のバケット化]コンポーネント設定](/help/data-views/component-settings/value-bucketing.md)</li></ul> |
| 2021年9月 | Customer Journey Analytics における[レポートスイートの結合の影響](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#6-considerations-when-merging-report-suites-in-cja)に関する新しい節。 |
| **2021年8月** | |
| 2021年8月 | Customer Journey Analytics の機能強化された[接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ja)エクスペリエンスに関する新しい節。 |
| 2021年8月 | [データビューディメンションの大文字と小文字の区別](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja#configure-behavior-settings) に関する新しい節を追加しました。 |
| **2021年6月** | |
| 2021年6月 | ワークスペースの [以前のプロジェクトバージョン](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/build-workspace-project/save-projects.html?lang=ja#previous-version) に関する新しいドキュメントを追加しました。 |
| **2021年4月** | |
| 2021年4月 | [永続性](/help/data-views/component-settings/persistence.md) に関する新しいトピックを追加しました。 |
| 2021年4月 | ワークスペースでのスケジュール済みプロジェクトのサポートに関する新しいドキュメントを追加しました。 |
| 2021年4月 | [強化されたデータビューエクスペリエンス](/help/data-views/data-views.md) に関する新しいトピックを追加しました。 |
| 2021年4月 | [Google Analytics データの取り込み](/help/use-cases/ga/overview.md) と [データの分析](/help/use-cases/ga/report.md) に関する新しいトピックを追加しました。 |
| 2021年4月 | ワークスペースの[予定レポート](/help/analysis-workspace/export/t-schedule-report.md)に関するトピックを追加しました。 |
| 2021年4月 | [Customer Journey Analytics の高基数ディメンション](/help/components/dimensions/high-cardinality.md)に関する新しいトピック。 |
| **2021年3月** | |
| 2021年3月 | [Analytics ダッシュボード](/help/mobile-app/home.md)（モバイルアプリ）のサポートに関するトピックを追加しました。 |
| 2021年3月 | ワークスペースの [ユーザーの環境設定](/help/analysis-workspace/user-preferences.md) に関する新しいトピックを追加しました。 |
| **2021年2月** | |
| 2021年2月 | [Adobe Experience Platform でのマーケティングチャネルディメンション](/help/use-cases/aa-data/marketing-channels.md) の使用に関する新しいトピックを追加しました。 |
| 2021年2月 | 新しい [Customer Journey Analytics API](https://www.adobe.io/cja-apis/docs/) ドキュメントを公開しました。 |
| **2021年1月** | |
| 2021年1月 | [データセットへの標準検索の追加](/help/connections/standard-lookups.md)に関する新しいトピックです。 |

{style="table-layout:auto"}

## 2020

| 日付 | アップデートの内容 |
| --- | --- |
| 2020年11月13日（PT） | についての新しいトピック [クロスチャネル分析](/help/stitching/overview.md)を使用すると、データセットの人物 ID のキーを変更でき、複数のデータセットをシームレスに組み合わせることができます。 |
| 2020年11月13日（PT） | [コールセンターと web データの読み込み](/help/use-cases/cross-channel/call-center.md) に関する新しいユースケースを追加しました。 |
| 2020年11月10日（PT） | [FAQ](/help/getting-started/cja-faq.md) に対するデータコンポーネントの削除の影響に関する節を追加しました。 |
| 2020年11月2日（PT） | 「[Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)」ページを更新しました。 |
| 2020年11月 | 接続の [バックフィル制限の削除](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#backfill-historical-data) に関する内容を追加しました。 |
| 2020年10月7日（PT） | [組み合わせイベントデータセット](/help/connections/combined-dataset.md) に関するトピックを追加しました。 |
| 2020年9月15日（PT） | [データの取り込み](/help/data-ingestion/data-ingestion.md) に関するトピックを追加しました。 |
| 2020年9月2日（PT） | [ユーザー権限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) に関する節を更新しました。 |
| 2020年8月7日（PT） | [B2B のユースケース - ルックアップデータセット](/help/use-cases/b2b/b2b.md)に関する新しいトピックを追加しました。 |
| 2020年7月 | [ユーザー ID の「ID マップ」オプション](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja) に関する情報を追加しました。 |
| 2020年7月 | [オブジェクト配列](/help/use-cases/object-arrays.md) または「データ階層」に関する新しいトピックを追加しました。 |
| 2020年4月14日（PT） | 「[接続の作成](/help/connections/create-connection.md)」トピックの最新 UI を更新しました。 |
| 2020年2月27日（PT） | [Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を更新しました。 |
| 2019年12月 | Customer Journey Analytics ドキュメントの最初のドラフト |

{style="table-layout:auto"}
