---
title: Customer Journey Analytics ガイド
description: Customer Journey Analytics のランディングページ。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 94d1bcdb2419f8c2e27bd77bb2e35b04cd30d632
workflow-type: ht
source-wordcount: '795'
ht-degree: 100%

---

# Customer Journey Analytics ガイド

このテクニカルドキュメントガイドでは、Customer Journey Analytics のセルフサポートを提供します。 Customer Journey Analytics を使用すると、任意のチャネル（オンラインとオフラインの両方）から顧客データを Adobe Experience Platform に取り込むことができます。 また、Analysis Workspace を使用すると、既存のデジタルデータと同様にこのデータを分析することもできます。

Customer Journey Analytics を使用すると、共通の顧客 ID に基づく Analysis Workspace のオンラインデータとオフラインデータの接続方法を制御し、顧客データ全体でアトリビューション、セグメント、フロー、フォールアウトなどを実行できます。

## 新着情報

Customer Journey Analytics 製品およびドキュメントにおける、最新の機能強化の概要を説明します。 機能、改善点、修正の包括的なリストについては、詳細な[リリースノート](../release-notes/latest.md)を参照してください。 最新のドキュメントアップデート内容を常に把握するには、[ドキュメントのアップデートページ](../release-notes/doc-changes.md)にアクセスしてください。

>[!BEGINTABS]

>[!TAB B2B Edition]

Customer Journey Analytics B2B Edition は、売上高の増加を促進する実用的なアカウントインサイトを提供することで、B2B 企業のマーケティング、セールス、製品の各チームが連携できるよう支援します。アカウントをデータモデルの中心に配置し、すべての分析でアカウントジャーニーに焦点を当てます。

[![画像](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB コンテンツ分析]

Content Analytics を使用すると、大量のコンテンツデータをすばやく容易に調べて、トレンドを明らかにし、異常を発見し、コンテンツ疲れを特定し、コンテンツの閲覧状況からインサイトを取得できます。

[![画像](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB イベント深度]

イベント深度は新しい標準ディメンションであり、顧客セッションにおけるイベントの位置づけを測定および深く理解するための新しい手段となります。イベント深度ディメンションを使用すると、セッション内でのユーザーインタラクションの順次フローにおいて、特定のイベントが発生するタイミングを詳細にトラッキングおよび分析できます。

[![画像](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB 共有指標と共有ディメンション]

共有指標と共有ディメンションでは、任意の数のデータビューっをまたいで使用できるディメンションと指標を、一元的に管理できます。これらのコンポーネントは、特に、組織が複数のデータビューを使用し、これらのデータビューでコンポーネント設定が共通している場合に役立ちます。

[![画像](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB グラフベースのステッチ*]

グラフベースのステッチを実行すると、Experience Platform ID サービスの ID グラフを使用して、次の方法でカスタマージャーニーをより詳細に把握できます。 <ul><li>単一の識別子を反映させるために追加のデータの抽出、変換、読み込みを行わずに、異なる識別子を持つデータセットを結合する。</li> <li>データセット間で ID を共有して、単一のデータセットの優先 ID またはゴールデン ID の適用範囲を向上させる。</li><li>Real-Time Customer Data Platform と Journey Optimizer で作成したプロファイルを Customer Journey Analytics のユーザーと整合する。</li></ul>

[![画像](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_グラフベースのステッチには、Prime パッケージが必要です。_*

>[!TAB BI 拡張機能*]

BI 拡張機能を使用すると、Customer Journey Analytics で定義したデータビューへの SQL アクセスが可能になります。 お気に入りの BI ツール（Power BI Desktop、Tableau Desktop、Looker、Juyter Notebook、RStudio）を使用し、Customer Journey Analytics ユーザーが Analysis Workspace プロジェクトで使用するのと同じデータビューに基づいて、レポートとダッシュボードを作成できるようになりました。[ユースケース](/help/use-cases/data-views/bi-extension-usecases.md)が提供されます。

[![画像](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_BI 拡張機能を使用するには、Select パッケージ以上が必要です。_*


>[!ENDTABS]

## 基本について学ぶ

まず、以下のリンクの資料を読んで、Customer Journey Analytics の機能を理解してください。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>オンラインデータ以外</strong><br/>Customer Journey Analytics と Adobe Analytics の比較、共有される機能、Analytics データの使用方法について説明します。</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>データの取り込みと使用</strong><br/>データを Experience Platform に取り込み、Customer Journey Analytics での分析とレポートに使用するために必要なオプションについて説明します。</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>ガイド付き分析</strong><br/>ワークフローを使用して、お客様の製品エクスペリエンスに関するデータとインサイトを取得する方法について説明します。 ガイド付き分析による製品分析…
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Analysis Workspace を使用して、アトリビューション、フロー図とフォールアウト図、ディメンションの分類などの基本分析とアドバンス分析を実行します。</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## ドキュメントの参照

Customer Journey Analytics と Adobe Analytics の比較方法について説明します。 また、ソリューションにデータを取り込み、そのデータと結果として得られる分析とレポートを準備、表示、分析、民主化する方法についても説明します。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Adobe Analytics との比較</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">概要</a> - <a href="/help/getting-started/aa-to-cja.md">進化</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Adobe Analytics データの使用</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">機能のサポート</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">用語</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">データ処理</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B Edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>接続</strong><br/><a href="/help/connections/overview.md">概要</a> - <a href="/help/connections/create-connection.md">作成</a> - <a href="/help/connections/manage-connections.md">管理</a> - <a href="/help/stitching/overview.md">ステッチ</a> - <a href="/help/connections/combined-dataset.md">組み合わせイベントデータセット</a> - <a href="/help/connections/standard-lookups.md">標準検索</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>データビュー</strong><br/><a href="/help/data-views/data-views.md">概要</a> - <a href="/help/data-views/create-dataview.md">作成または編集</a> - <a href="/help/data-views/session-settings.md">セッション設定</a> - <a href="/help/data-views/derived-fields/derived-fields.md">派生フィールド</a> - <a href="/help/data-views/summary-data.md">概要データ</a> - <a href="/help/data-views/component-reference.md">コンポーネントの参照</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace プロジェクト</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本分析</a>と<a href="/help/analysis-workspace/perform-adv-analysis.md">アドバンス分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">プロジェクト</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">ビジュアライゼーション</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">パネル</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>ガイド付き分析</strong><br/><a href="/help/guided-analysis/overview.md">概要</a> - <a href="/help/guided-analysis/types/active-growth.md">ユーザーの増加</a> - <a href="/help/guided-analysis/types/trends.md">トレンド</a> - <a href="/help/guided-analysis/types/funnel.md">ファネル</a> - <a href="/help/guided-analysis/types/release-impact.md">影響</a> - <a href="/help/guided-analysis/industry-use-cases.md">業界のユースケース</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>共有、書き出し、統合</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">プロジェクト</a> - <a href="/help/mobile-app/home.md">Analytics ダッシュボード</a> - <a href="/help/report-builder/rb-overview.md">Report Builder</a> - <a href="/help/components/exports/manage-exports.md">クラウドの書き出し</a> - <a href="/help/integrations/overview.md">統合</a>
    </td>
  </tr>
</table>

## その他のリソース

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">チュートリアル</a> - <a href="https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics製品説明</a> - <a href="https://helpx.adobe.com/jp/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics（Customer Journey Analytics アドオン）製品説明</a> - <a href="https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics-b2b.html" target="_blank">Customer Journey Analytics B2B edition 製品説明</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a> - <a href="/help/ai-assistant.md">AI アシスタント</a>
</td>
<td><strong>データ取り込み</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概要</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">バッチ</a> - <a href="/help/data-ingestion/streaming.md">ストリーミング</a> - <a href="/help/data-ingestion/sources.md">ソース</a> - <a href="/help/data-ingestion/serverapi.md">Server API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>常に最新情報を入手、コミュニティに貢献し、Customer Journey Analytics エクスペリエンスを向上させましょう。</b><br>Adobe Analytics コミュニティにアクセスして、実務担当者と機能について語り合いましょう。 <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ja">今すぐコミュニティに参加</a></td></tr></tbody></table>
