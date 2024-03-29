---
title: Customer Journey Analytics ガイド
description: Customer Journey Analytics のランディングページ。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 2f5bd8bec1580077675d249fa0431d84ee2269fa
workflow-type: ht
source-wordcount: '622'
ht-degree: 100%

---

# Customer Journey Analytics ガイド

このテクニカルドキュメントガイドでは、Customer Journey Analytics のセルフサポートを提供します。Customer Journey Analytics を使用すると、選択したチャネル（オンラインとオフラインの両方）から顧客データを Adobe Experience Platform に取り込み、今すぐ Analysis Workspace を使用して、このデータを既存のデジタルデータと同じように分析できます。

Customer Journey Analytics を使用すると、共通の顧客 ID に基づいて Analysis Workspace のオンラインデータとオフラインデータの接続方法を制御し、最終的には、顧客データ全体でアトリビューション、フィルター、フロー、フォールアウトなどを。実行できます。

## 新着情報

Customer Journey Analytics 製品およびドキュメントにおける、最新の機能強化の概要を説明します。機能、改善点、修正の包括的なリストについては、詳細な[リリースノート](../release-notes/latest.md)を参照してください。[ドキュメントのアップデートページ](../release-notes/doc-changes.md)にアクセスして、最新の変更を反映し、ドキュメントを常に最新の状態に保ってください。

>[!BEGINTABS]

>[!TAB 予測]

予測は、標準指標または計算指標を、サポートされている任意の時間精度（時間単位、日単位、週単位、月単位、年単位）で予測する Analysis Workspace 機能です。予測は、時系列関連のデータに対してのみ使用できます。

[![i画像](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)


>[!TAB ガイド付き分析* - リテンション率]

目的の日付範囲内で最初にエンゲージメントした後に再来訪するユーザーの割合を示す、新しいビュータイプ。横軸は、ユーザーの最初のエンゲージメントからの日数を表します。縦軸は、再度エンゲージするユーザーの割合を表します。

[![i画像](assets/learn-more-button.svg)](/help/guided-analysis/types/retention-rates.md)

<span style="color:gray">*_ガイド付き分析は、Adobe Product Analytics の一部で、Customer Journey Analytics の有料アドオンです。_</span>


>[!TAB ガイド付き分析* - トレンドライン]

使用状況ビューでトレンドラインオーバーレイが使用できるようになりました。これは、データの、より明確なパターンを示すのに役立ちます。使用可能なトレンドラインのタイプは、線形、対数、移動平均です。

[![画像](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_ガイド付き分析は、Adobe Product Analytics の一部で、Customer Journey Analytics の有料アドオンです。_</span>


>[!TAB 主要指標の概要ビジュアライゼーション]

主要指標の概要ビジュアライゼーションを使用する際、選択した比較日付範囲オプションが主な日付範囲に対して相対的であるか固定であるかに応じて、比較日付範囲が自動的に更新されるようになりました。

[![画像](assets/learn-more-button.svg)](/help/analysis-workspace/visualizations/key-metric.md)

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
    <div><strong>ガイド付き分析</strong><br/>ワークフローを使用して、お客様の製品エクスペリエンスに関するデータとインサイトを取得する方法について説明します。ガイド付き分析による製品分析...
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

Customer Journey Analytics と Adobe Analytics を比較する方法と、ソリューションにデータを取り込み、そのデータと結果として得られる分析とレポートを準備、表示、分析し、民主化する方法について説明します。

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Adobe Analytics との比較</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">概要</a> - <a href="/help/getting-started/aa-to-cja.md">進化</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Adobe Analytics データの使用</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">機能のサポート</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">用語</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">データ処理</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>接続</strong><br/><a href="/help/connections/overview.md">概要</a> - <a href="/help/connections/create-connection.md">作成</a> - <a href="/help/connections/manage-connections.md">管理</a> - <a href="/help/stitching/overview.md">ステッチ</a> - <a href="/help/connections/combined-dataset.md">組み合わせイベントデータセット</a> - <a href="/help/connections/standard-lookups.md">標準参照</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>データビュー</strong><br/><a href="/help/data-views/data-views.md">概要</a> - <a href="/help/data-views/create-dataview.md">作成または編集</a> - <a href="/help/data-views/session-settings.md">セッション設定</a> - <a href="/help/data-views/derived-fields/derived-fields.md">派生フィールド</a> - <a href="/help/data-views/component-reference.md">コンポーネントの参照</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace プロジェクト</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本分析</a>と<a href="/help/analysis-workspace/perform-adv-analysis.md">アドバンス分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">プロジェクト</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">ビジュアライゼーション</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">パネル</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>ガイド付き分析</strong><br/><a href="/help/guided-analysis/overview.md">概要</a> - <a href="/help/guided-analysis/types/active.md">ユーザーの増加</a> - <a href="/help/guided-analysis/types/usage.md">トレンド</a> - <a href="/help/guided-analysis/types/friction.md">ファネル</a> - <a href="/help/guided-analysis/types/release.md">影響</a> - <a href="/help/guided-analysis/industry-use-cases.md">業界のユースケース</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>共有、書き出し、統合</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">プロジェクト</a> - <a href="/help/mobile-app/home.md">Analytics ダッシュボード</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">統合</a>
    </td>
  </tr>
</table>

## その他のリソース

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/overview.html?lang=ja" target="_blank">チュートリアル</a> - <a href="https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 製品の説明</a> - <a href="https://helpx.adobe.com/jp/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics（Customer Journey Analyticsアドオン）製品の説明</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a>
</td>
<td><strong>データ取り込み</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概要</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">バッチ</a> - <a href="/help/data-ingestion/streaming.md">ストリーミング</a> - <a href="/help/data-ingestion/sources.md">ソース</a> - <a href="/help/data-ingestion/serverapi.md">Server API</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>常に最新情報を入手、コミュニティに貢献し、Customer Journey Analytics エクスペリエンスを向上させましょう。</b><br>Adobe Analytics コミュニティにアクセスして、実務担当者と機能について語り合いましょう。<a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ja">今すぐコミュニティに参加</a></td></tr></tbody></table>
