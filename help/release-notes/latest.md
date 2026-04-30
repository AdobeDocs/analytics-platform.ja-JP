---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 852bafc87c377ba1abb511574eef497c8829e132
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 66%

---

# 現在の Customer Journey Analytics リリースノート（2026年4月）

**最終更新**: 2026年4月22日（PT）

このリリースノートは、2026年4月のリリース期間を対象としています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **イタリア語のサポート**<br/> Customer Journey Analytics の Analysis Workspace で、イタリア語ロケール（it-IT）がサポートされるようになりました。 <p>Customer Journey Analytics は、Experience Platform UI でサポートされているすべての言語をサポートしています。詳しくは、[Experience Platform UI のブラウザーと言語のサポート](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)を参照してください。</p><p>Experience Platform では、[デフォルトの言語を変更](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)できます。</p> | | 2026年4月8日（PT） |
| **Adobe Engineering Agent でのデータ検証** <br/>新しいデータ検証スキルは、Data Engineering Agent 内で使用できます。 これらのスキルは、Customer Journey Analytics でデータが分析される前に、Adobe Experience Platform でデータ品質を直接すばやく評価するのに役立ちます。 <p>データ検証スキルにより、オンデマンド、フィールドレベル、データセットレベルでの検証が可能になり、統計的要約と無効値や異常値のインテリジェントな検出を組み合わせることができます。 </p><p>データ検証スキルを使用することで、手動の QA 作業を削減し、データエンジニアリングワークフローをまたいで信頼できるデータのオンボーディングと変換を高速化できます。</p><p>（ドキュメントのリンクは以下を参照。）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/ja/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年5月 <p>（当初は 2026年3月31日（PT）にリリースされる予定でした）</p> |
| **Customer Journey Analytics用MCP サーバー** <br/>Analytics MCP （Model Context Protocol）サーバーを使用すると、サポートされているMCP クライアントをAdobe Customer Journey Analyticsに接続できます。 接続が完了すると、MCP クライアントは、製品固有のツールを呼び出して、データの取得、クエリの実行、またはLLMまたはエージェント型ワークフローの一部としてサポートされている操作を実行できます。 詳しくは、[Analytics MCP サーバー](https://developer.adobe.com/analytics-mcp/docs/)を参照してください。<p>ベータ期間中にこれらのMCP サーバーを使用した場合は、ベータ版と実稼動エンドポイントの間に異なるURLがあることに注意してください。 ベータ期間中に作成されたエージェント型ワークフローが、5月31日より前に実稼動エンドポイントを使用するように更新されていることを確認します。</p> | | 2026年4月29日（PT） |
| **ネイティブモバイルアプリエクスペリエンスに対するContent Analyticsのサポート**<br/>&#x200B;企業は、iOSおよびAndroid アプリに対してコンテンツパフォーマンス分析を拡張し、画像アセットと詳細なエクスペリエンス要素をキャプチャして、どのアプリ内コンテンツがユーザーエンゲージメントとビジネス成果を促進するのかを把握できます。<p>Adobe Content Analyticsのすべてのユーザーがインサイトを利用できます。</p> | 2026年5月6日（PT） | 未定 |
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |
| **複数のディメンション API レポート**<br/> 1 つの API リクエストで複数のディメンションをレポートし、ディメンションレベルの検索を実行します。 [詳細情報](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | 2026年3月 |
| **複数列 API の並べ替え**<br/> API リクエストで複数のディメンションおよび指標オブジェクトを並べ替えます。 同じ並べ替え定義でディメンションと指標を混在させます。 [詳細情報](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | 2026年3月 |

## Customer Journey Analytics の修正点

**Analysis Workspace**: AN-442813、AN-442410、AN-442231、AN-441943、AN-441717、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**コンポーネント**:
**接続**: AN-442824、AN-440937、AN-440092、AN-429781
**Content Analytics**:
**ガイド付き分析**:
**書き出し**:
**データビュー**: AN-442809、AN-434824、AN-434210、AN-424000
**実装**:
**Report Builder**: AN-441136、AN-438147、AN-425150
**レポート**: AN-443900、AN-441811、AN-441506、AN-440919、AN-440545、AN-440505、AN-440300
**セグメント化**:
**スケジュール済みレポート**:
**共有の指標とディメンション**:
**その他**: AN-423359、AN-406242、AN-397985

## 関連リソース

* [2025年の以前の Customer Journey Analytics リリースノート](/help/release-notes/2025.md)
* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
* [Streaming Media Collection リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
