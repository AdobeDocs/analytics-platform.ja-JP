---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: c818dd36bc900b3945b87503afad8e944a3716a7
workflow-type: tm+mt
source-wordcount: 721
ht-degree: 100%

---

# 現在の Customer Journey Analytics リリースノート（2026年5月）

**最終更新日**：2026年5月13日（PT）

このリリースノートは、2026年5月のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **CJA API Postman コレクション** <br/>CJA API エンドポイントの呼び出しにダウンロード可能な Postman コレクションが使用可能です。<p>詳しくは、[analytics-cja-postman-collections Github リポジトリ](https://github.com/AdobeDocs/analytics-cja-postman-collections)を参照してください。  </p> | | 2026年5月1日（PT） |
| **Customer Journey Analytics 用 MCP サーバー** <br/>Analytics MCP（モデルコンテキストプロトコル）サーバーを使用すると、サポートされている MCP クライアントを Adobe Customer Journey Analytics に接続できます。 接続すると、MCP クライアントは製品固有のツールを呼び出し、LLM またはエージェント型ワークフローの一部として、データの取得、クエリの実行、サポートされている操作を実行できます。 詳しくは、[Analytics MCP サーバー](https://developer.adobe.com/analytics-mcp/docs/)を参照してください。<p>ベータ版期間中にこれらの MCP サーバーを使用した場合は、ベータ版エンドポイントと本番エンドポイントでは URL が異なることに注意してください。 ベータ版期間中に作成したエージェント型ワークフローは、5月31日（PT）より前に本番エンドポイントを使用するように更新されていることを確認してください。</p> | | 2026年5月5日（PT） |
| **ネイティブモバイルアプリエクスペリエンスのコンテンツ分析サポート**<br/>&#x200B;組織は、コンテンツのパフォーマンス分析を iOS および Android アプリに対して拡張し、画像アセットや詳細なエクスペリエンス要素を取得して、ユーザーエンゲージメントとビジネス成果を推進するアプリ内コンテンツを把握できます。<p> モバイルチャネルの機能と設定について説明する[ドキュメント](/help/content-analytics/content-analytics.md)が更新されています。 [コンテンツ分析の Mobile SDK 拡張機能](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)について詳しくは、[Adobe Developer](https://developer.adobe.com/) を参照してください。</p><p>すべての Adobe Content Analytics のお客様のインサイトが使用可能です。</p> | | 2026年5月6日（PT） |
| **ジャーニーキャンバスの機能強化** <br/>ジャーニーキャンバスのビジュアライゼーションでは、次の機能強化が使用可能です。 <ul><li>ジャーニーから[ノードを除外](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#exclude-nodes)する。</li><li>ノードのフォールアウトデータを使用して、[セグメント](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-a-segment-based-on-a-node-or-arrow)、[トレンド](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#view-trend-data)、[オーディエンス](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-an-audience)、[分類](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#apply-a-breakdown)を作成する。</li></ul> | | 2026年5月18日（PT） |
| **コンテンツ分析：折れ線グラフビジュアライゼーションのサムネイルとプレビュー** コンテンツ分析の折れ線グラフビジュアライゼーションでは、アセットとエクスペリエンスの<br/>[サムネイルとプレビュー](/help/content-analytics/report/report.md)が使用可能になりました。 |  | 2026年5月20日（PT） |
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |

{style="table-layout:auto"}


## Customer Journey Analytics の修正点

**Analysis Workspace**：AN-446522、AN-445779、AN-445759、AN-444676、AN-442813、AN-441943、AN-441717、AN-441538、AN-441123、AN-440976、AN-440952、AN-440919、AN-439797、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**コンポーネント**：
**接続**：AN-449652、AN-444560、AN-442824、AN-440937、AN-440092、AN-439823、AN-429781
**コンテンツ分析**：
**ガイド付き分析**：
**書き出し**：AN-438953、AN-437115
**データビュー**：AN-442809
**実装**:
**Report Builder**：AN-448697、AN-447128、AN-441148、AN-441136、AN-438147、AN-425150
**レポート**：AN-445123、AN-442231、AN-442169、AN-441811、AN-441733、AN-440505、AN-440300、AN-434824、AN-434210、AN-424000、AN-423359、AN-406242
**セグメント化**：
**予定レポート**：
**共有指標と共有ディメンション**：
**その他**：AN-449159、AN-444661、AN-443900、AN-397985

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [CX Enterprise リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
