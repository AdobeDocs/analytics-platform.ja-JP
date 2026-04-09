---
title: 現在の Customer Journey Analytics リリースノート
description: 最新の Customer Journey Analytics リリースノートを表示
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7fc7475001505749cf59aa82a62e5abb7e81ea97
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 41%

---

# 最新のCustomer Journey Analytics リリースノート（2026年4月）

**最終更新**: 2026年4月9日（PT）

これらのリリースノートは、2026年4月のリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **イタリア語サポート**<br/> イタリア語ロケール（it-IT）がCustomer Journey AnalyticsのAnalysis Workspaceでサポートされるようになりました。 <p>Customer Journey Analyticsは、Experience Platform UIでサポートされているすべての言語をサポートしています。詳しくは、[Experience Platform UIのブラウザーと言語のサポート ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)を参照してください。</p><p>Experience Platformで[既定の言語](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)を変更できます。</p> | | 2026年4月8日（PT） |
| **Adobe Engineering Agentでのデータ検証** <br/>新しいデータ検証スキルは、Data Engineering Agent内で利用できます。 Customer Journey Analyticsでデータを分析する前に、Adobe Experience Platformで直接データ品質を迅速に評価できます。 <p>データ検証スキルにより、オンデマンド、フィールドレベル、データセットレベルの検証が可能になり、統計的な要約と、無効な値や異常値のインテリジェントな検出を組み合わせることができます。 </p><p>データ検証スキルを活用することで、手作業のQA作業を削減し、データエンジニアリングワークフロー全体で信頼できるデータオンボーディングと変換を加速できます。</p><p>（ドキュメントへのリンクを添付）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年4月末 <p>（当初は 2026年3月31日（PT）にリリースされる予定でした）</p> |
| **Customer Journey Analytics用MCP サーバー** <br/>MCP （Model Context Protocol）を使用して、Customer Journey Analyticsを既存のエージェント型ワークフローに関連付けることができるようになりました。 自然言語を使ってレポートやインサイトをリクエストできます。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年4月末 |
| **ストリーミングメディアサービス：サポートスケジュールのデータ** <br/>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、視聴者をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |
| **複数ディメンション API レポート**<br/>&#x200B;単一のAPI リクエストで複数ディメンションをレポートし、ディメンション レベルの検索を実行します。 [詳細情報](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | 2026年3月 |
| **複数列APIの並べ替え**<br/> API リクエスト内の複数のディメンションと指標オブジェクトの並べ替え。 同じ並べ替え定義でディメンションと指標を組み合わせます。 [詳細情報](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | 2026年3月 |

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
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
* [Customer Journey Analytics ドキュメントのアップデート](/help/release-notes/doc-changes.md)
