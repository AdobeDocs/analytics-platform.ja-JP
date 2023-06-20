---
title: 現在の Customer Journey Analytics リリースノートを表示
description: 最新のCustomer Journey Analyticsリリースノート
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 75%

---

# 最新のAdobe Customer Journey Analyticsリリースノート（2023 年 6 月）

**最終更新日**：2023年19月6日（PT）

Customer Journey Analytics リリースは、機能のデプロイメントに対する、よりスケーラブルで段階的なアプローチを実現する[継続的な配信モデル](releases.md)に基づいて動作します。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## リリースのハイライト {#highlights}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **インテリジェントキャプション** | [!UICONTROL 折れ線グラフ]ビジュアライゼーションの自然言語による要約を使用して、ユーザー向けのストーリーテリングを強化します。[詳細情報](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023年5月17日（PT） | 2023年6月1日（PT） |
| **プロジェクトのリンク共有（ログインは不要）** | Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。これには、組織外のユーザーや、組織内で Adobe Analytics 用にプロビジョニングされていないユーザーとの共有が含まれます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja#share-public-link) <p>この機能はデフォルトで有効になっており、システム管理者が無効にできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=ja#company-preferences)</p> | 2023年5月3日（PT） | 2023年6月6日（PT） |
| **派生フィールド** | これは、派生フィールドの最初のリリースを表します。派生フィールドを使用すると、カスタマイズ可能なルールビルダーを使用して、（多くの場合、複雑な）データ操作をその場で定義できます。さらに、派生フィールドをデータビューのコンポーネント（指標またはディメンション）として定義し、その派生フィールドを Workspace のコンポーネントとして使用することもできます。<p>このリリースでは、マーケティングチャネルテンプレートと次の機能がサポートされています。</p><ul><li>連結</li><li>Case When</li><li>検索と置換</li><li>ルックアップ</li><li>URL の解析</li></ul> <p>[詳細情報](/help/data-views/derived-fields/derived-fields.md)</p> | 2023年5月10日（PT） | 2023年6月14日（PT） |
| **PowerBI および Tableau によるCustomer Journey Analyticsデータビューへのアクセス** | Adobe Customer Journey Analytics SQL Connector を使用すると、Customer Journey Analyticsで定義したデータビューに SQL からアクセスできます。 Power BI、Tableau、またはその他のビジネスインテリジェンスやビジュアライゼーションツールに詳しいCustomer Journey Analyticsエンジニアやアナリストは、Analysis Workspaceプロジェクトで使用するのと同じデータビューに基づいて、レポートやダッシュボードを作成できます。 [詳細情報](/help/data-views/sql-connector.md) |  | 2023年6月30日（PT） |
| **Experience Edge 位置情報検索** | Experience Edge 地域ルックアップがデータストリームに対して有効になると、Customer Journey Analyticsの位置情報データを使用してレポートを作成できるようになります。 |  | 2023年6月30日（PT） |
| **プロファイルおよびルックアップデータに対するルックアップサポートの拡張** | ルックアップデータセットをイベントデータセットだけでなく、プロファイルデータセットやルックアップデータセットにも追加できるようになります。 | 2023年6月28日（PT） | 2023年7月12日（PT） |
| **通貨換算のサポート** | 通貨コンバージョンは、データビューでの指標コンポーネントの書式設定の一環としてサポートされています。 [詳細情報](../data-views/component-settings/format.md#currency) | 2023年6月7日（PT） | 2023年6月21日（PT） |

{style="table-layout:auto"}

## その他の新機能または更新された機能 {#other-new}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer データ表示** | Customer Journey Analytics管理者は、「AJO Data view (Sandbox-name)」と呼ばれる、Customer Journey Analyticsの追加のデータビューにアクセスできます。 これらのデータビューは、Adobe Journey Optimizerでレポートを強化するために使用されます。 また、Customer Journey AnalyticsでAdobe Journey Optimizerのアクティビティをより深く分析する場合にも使用できます。 [詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html?lang=ja)。 | | 2023年5月25日（PT） |
| **非実稼動用サンドボックスのバックフィル** | 非実稼動用サンドボックスで Analytics ソースコネクタのデータフローを作成する場合、非実稼動用サンドボックスでのバックフィルは 3 か月に制限されます。実稼動用サンドボックスの場合、13 か月間の状態が保たれます。 | 該当なし | 2023年4月26日（PT） |
| **プロジェクトのリンク共有（ログインは不要）** | Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。これには、組織外のユーザーや、組織内で Adobe Analytics 用にプロビジョニングされていないユーザーとの共有が含まれます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=ja#share-public-link) <p>この機能はデフォルトで有効になっており、システム管理者が無効にできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=ja#ims-organization-preferences)</p> | 2023年5月3日（PT） | 2023年6月6日（PT） |
| **Analytics ダッシュボードアプリ（モバイルアプリ）の更新されたホーム画面** | 新しく更新されたホーム画面では、すべてのスコアカードを 1 つの統合されたスコアカードリストで表示できます。1 回のログインで複数の組織にアクセスできる場合、組織のすべてのスコアカードが 1 つのリストで使用できるようになります。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=ja#use-dashboards) | 該当なし | 2023年5月10日（PT） |
| **Customer Journey AnalyticsのReport Builder — セルからデータビューを選択します** | この機能を使用すると、ユーザーはセルからデータブロックのデータ表示を選択できます。これは、ワークブックを作成し、同様のデータ構造を持つ複数のデータ表示があり、異なるデータ表示で複数回ワークブックを再利用する場合に便利です。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=ja) | 該当なし | 2023年5月24日（PT） |
| **Customer Journey Analyticsの学習ページを更新しました** | Customer Journey Analyticsランディングページの「学習」タブに、Adobe AnalyticsからCustomer Journey Analyticsへの移行に重点を置いたコンテンツなど、Customer Journey Analyticsに固有のコンテンツが含まれるようになりました。<p>「学習」タブでは、さらに次の機能強化も利用できます。</p><ul><li>ナビゲーションが改善され、単一ページによりその他のラーニングコンテンツが表示されるデザインの改善</li><li>エクスペリエンスレベル（初級、中級、上級）に応じてラーニングコンテンツをパーソナライズする機能</li></ul><p>以前は、Customer Journey Analyticsの「学習」タブには、Adobe Analyticsの「学習」タブと同じ情報が含まれていました。</p> [詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | 該当なし | 2023年6月30日（PT） |
| **Analysis Workspace でのコンポーネントの並べ替え** | <p>新しい「並べ替え」オプションは、Analysis Workspace の左側のパネルまたはデータ要素でコンポーネントを表示する際に使用できるようになりました。コンポーネントは、推奨（最も一般的に使用されるコンポーネント）、アルファベット順、またはカテゴリ順（タイプ）で並べ替えることができます。</p><p>以前は、コンポーネントを検索またはフィルタリングすることしかできませんでした。[詳細情報](/help/components/overview.md)</p> | 該当なし | 2023年6月7日（PT） |
| **フリーフォームテーブルからの動的ディメンションを含む行の削除** | Analysis Workspace のフリーフォームテーブルで、「x」アイコンを使用して、動的ディメンションを含む特定の行をすばやく削除できるようになりました。その際、「常に項目を除外」フィルタールールが自動的に適用されます。<p>以前は、動的ディメンションを含む行を削除する唯一の方法は、フィルターダイアログでルールを手動で作成することでした。[詳細情報](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 該当なし | 2023年5月17日（PT） |
| **パネル内にビジュアライゼーションを追加する新しいボタン** | Analysis Workspace の各パネルの下部に新しいボタンが表示され、ビジュアライゼーションをすばやく追加できるようになりました。 <p>以前は、パネルにビジュアライゼーションを追加する唯一の方法は、左側のパネルからビジュアライゼーションをドラッグしたり、既存のビジュアライゼーションを複製またはコピーしたり、空のパネルを作成したりすることでした。[詳細情報](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 該当なし | 2023年5月17日（PT） |
| **ディープリンク（モバイルアプリ）** | ユーザーが、アプリ内のスコアカードプロジェクトに直接アクセスできるスコアカードへのリンクを送信できるようにします。これにより、プロジェクトの共有がさらに簡単になり、技術に詳しくないオーディエンスからのエンゲージメントを高めることができます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ja#share-scorecards-using-a-shareable-link) | 該当なし | 2023年5月17日（PT） |
| **インテリジェントキャプション** | [!UICONTROL 折れ線グラフ]ビジュアライゼーションの自然言語による要約を使用して、ユーザー向けのストーリーテリングを強化します。[詳細情報](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023年5月17日（PT） | 2023年6月1日（PT） |

{style="table-layout:auto"}

## Customer Journey Analytics の修正点

AN-318343、AN-319453

## Customer Journey Analytics管理者向けの重要な注意事項

| 通知 | 追加または更新された通知 | 説明 |
| --- | --- | --- |
| 該当なし | 該当なし | 該当なし |

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **AdobeIO OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | AdobeIO JWT 資格情報を使用しているAdobe Analytics API、Customer Journey AnalyticsAPI、Livestream のお客様は、次の手順で AdobeIO OAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. AdobeIO では、2024年5月1日（PT）以降、新しい JWT 資格情報の作成を許可しません。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## 関連リソース

* [2023 年の以前のCustomer Journey Analyticsリリースノート](/help/release-notes/2023.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
