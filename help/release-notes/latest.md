---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: c72fdec6717e94c42264836ebd7ed2f039d55087
workflow-type: tm+mt
source-wordcount: 891
ht-degree: 41%

---

# 最新のCustomer Journey Analytics リリースノート（2026年5月）

**最終更新**: 2026年5月13日（PT）

このリリースノートでは、2026年5月のリリース期間について説明します。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **CJA API Postman コレクション** <br/>CJA API エンドポイントの呼び出しにダウンロード可能なPostman コレクションを使用できます。<p>詳しくは、[analytics-cja-postman-collections Github リポジトリ ](https://github.com/AdobeDocs/analytics-cja-postman-collections)を参照してください。  </p> | | 2026年5月1日（PT） |
| **Customer Journey Analytics用MCP サーバー** <br/>Analytics MCP （Model Context Protocol）サーバーを使用すると、サポートされているMCP クライアントをAdobe Customer Journey Analyticsに接続できます。 接続が完了すると、MCP クライアントは、製品固有のツールを呼び出して、データの取得、クエリの実行、またはLLMまたはエージェント型ワークフローの一部としてサポートされている操作を実行できます。 詳しくは、[Analytics MCP サーバー](https://developer.adobe.com/analytics-mcp/docs/)を参照してください。<p>ベータ期間中にこれらのMCP サーバーを使用した場合は、ベータ版と実稼動エンドポイントの間に異なるURLがあることに注意してください。 ベータ期間中に作成されたエージェント型ワークフローが、5月31日より前に実稼動エンドポイントを使用するように更新されていることを確認します。</p> | | 2026年5月5日（PT） |
| **ネイティブモバイルアプリエクスペリエンスに対するContent Analyticsのサポート**<br/>&#x200B;企業は、iOSおよびAndroid アプリに対してコンテンツパフォーマンス分析を拡張し、画像アセットと詳細なエクスペリエンス要素をキャプチャして、どのアプリ内コンテンツがユーザーエンゲージメントとビジネス成果を促進するのかを把握できます。<p> [ ドキュメント ](/help/content-analytics/content-analytics.md)が更新され、モバイルチャネルの機能と設定が説明されます。 [Content Analytics Mobile SDK拡張機能](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)に関する情報は、[Adobe Developer](https://developer.adobe.com/)で入手できます。</p><p>Adobe Content Analyticsのすべてのユーザーがインサイトを利用できます。</p> | | 2026年5月6日（PT） |
| **Adobe Engineering Agent でのデータ検証** <br/>新しいデータ検証スキルは、Data Engineering Agent 内で使用できます。 これらのスキルは、Customer Journey Analytics でデータが分析される前に、Adobe Experience Platform でデータ品質を直接すばやく評価するのに役立ちます。 <p>データ検証スキルにより、オンデマンド、フィールドレベル、データセットレベルでの検証が可能になり、統計的要約と無効値や異常値のインテリジェントな検出を組み合わせることができます。 </p><p>データ検証スキルを使用することで、手動の QA 作業を削減し、データエンジニアリングワークフローをまたいで信頼できるデータのオンボーディングと変換を高速化できます。</p><p>（ドキュメントのリンクは以下を参照。）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年5月19日（PT） <p>（当初は 2026年3月31日（PT）にリリースされる予定でした）</p> |
| **Content Analytics:Content Analyticsのラインビジュアライゼーションのサムネールとプレビュー** <br/>[ サムネールとプレビュー](/help/content-analytics/report/report.md)が、のラインビジュアライゼーションでアセットとエクスペリエンスに使用できるようになりました。 |  | 2026年5月20日（PT） |
| **Agent OrchestratorのData Insights Agent** <br/> Data Insights Agentは、Customer Journey Analyticsの右側のパネルで利用できるだけでなく、Agent Orchestratorの一部として利用できるようになりました。 つまり、Journey Optimizer内などの他のExperience Platformアプリで作業している間に、Customer Journey Analyticsのデータと機能に基づいたインサイトを得ることができるようになりました。<p>Customer Journey Analyticsでは、Data Insights Agentに次の機能強化が含まれています。</p><ul><li>Agent Orchestratorによる、より一貫性のある顧客体験</li><li>説明的な要約の段落</li><li>根本原因の分析による「なぜ」の質問への回答</li><li>インラインテーブル</li><li>他にもたくさんあります！</l></ul><p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年5月末 |
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |

{style="table-layout:auto"}


## Customer Journey Analytics の修正点

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**コンポーネント**:
**接続**: AN-449652、AN-444560、AN-442824、AN-440937、AN-440092、AN-439823、AN-429781
**Content Analytics**:
**ガイド付き分析**:
**書き出し**: AN-438953、AN-437115
**データビュー**: AN-442809
**実装**:
**Report Builder**: AN-448697、AN-447128、AN-441148、AN-441136、AN-438147、AN-425150
**レポート**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**セグメント化**:
**スケジュール済みレポート**:
**共有の指標とディメンション**:
**その他**: AN-449159、AN-444661、AN-443900、AN-397985

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Streaming Media Collection リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
