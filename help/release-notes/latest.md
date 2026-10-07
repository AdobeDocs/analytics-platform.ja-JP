---
title: 最新のCustomer Journey Analytics リリースノート
description: 最新のCustomer Journey Analytics リリースノート（新機能、修正済みの問題、現在延期されているリリースなど）をご覧ください。
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 0a83f4d08806b4d9b97265989f9d687011b232c3
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 28%
---
# 最新のCustomer Journey Analytics リリースノート（2026年10月）

**最終更新**: 2026年10月7日

これらのリリースノートは、2026年10月のリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP サーバーの読み取り専用アクセス許可**<br/>&#x200B;管理者は、ユーザーにCustomer Journey Analytics MCP サーバーへの読み取り専用アクセス権を付与できるようになりました。 新しい[!UICONTROL MCP読み取り専用]権限アイテムでは、プロジェクト、セグメント、計算指標を作成せずに、すべての読み取り専用ツールにアクセスできます。<p>既存の[!UICONTROL MCP アクセス ]権限項目の名前が[!UICONTROL MCP フルアクセス ]に変更されました。 この権限を持つユーザーは、コンポーネントの作成、変更、削除を行うツールを含む、すべてのツールにアクセスできます。</p><p>詳しくは、[Customer Journey Analytics MCP server](https://developer.adobe.com/analytics-mcp/docs/cja/)を参照してください。</p> | | 2026年10月6日（PT） |
| **会話インサイトを利用して、Analysis WorkspaceのLLM カスタマーエクスペリエンスを分析**<br/> Customer Journey Analyticsでは、非構造化チャットデータをAnalysis Workspaceに取り込み、プロパティ全体で発生するLLMを活用した閲覧体験と購買体験についてレポートを作成できるようになりました。<p>この機能を使用すると、次のことが可能になります。</p><ul><li>Web SDKを使用して、会話型エージェント（組織のカスタムエージェントまたはAdobe Brand Concierge）からプロンプト、レスポンス、エージェントメタデータを収集します。</li><li>意図、トーン、センチメントを分析することで、顧客が何を求めているのか、担当者がどのように反応するのか、顧客がどのように感じているのかを把握できます。</li><li>既存のスキーマ、データセット、データビューを利用して大規模に分析し、Analysis Workspaceでインサイトを獲得できます。</li><li>エージェントとのやり取りを、より広範なカスタマージャーニーに結び付けることで、結果に会話を結びつけ、コンバージョンやエンゲージメントなどへの実際の影響を測定することができます。</li></ul><p>以前は、LLMを活用したエクスペリエンスを測定するのは困難で、既存のカスタマージャーニーとつながることもほぼ不可能でした。</p><p>詳しくは、[会話インサイト ](/help/conversation-insights/overview.md)を参照してください。</p> | | 2026年10月8日（PT）<p>（当初は2026年9月22日に予定）</p> |
| **コンポーネントの説明を自動生成** <br/> ディメンション、指標、計算指標、セグメント、日付範囲の説明を自動的に生成できるようになりました。 これにより、Workspace ユーザーは、特に大規模なコンポーネントライブラリを持つ組織で、使用するコンポーネントを理解できます。 <p>1つのコンポーネントに対して説明を生成したり、同時に多くのコンポーネントに対して説明を生成したりできます。</p> <p>（ドキュメントのリンクは以下を参照。）<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026年10月28日（PT） |
| **Adobe Brand Visibilityとの統合**<br/> Adobe Adobe Brand Visibilityを組織のCustomer Journey Analyticsデータと連携させて、AIを活用した発見が、web サイトの実際のエンゲージメントとビジネスの成果にどのように結びつくのかを測定できます。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年10月 |


### Customer Journey Analytics の修正点

**Analysis Workspace**: AN-495340、AN-494789、AN-493307、AN-468900
**コンポーネント**: AN-492523
**接続**: AN-492236
**コンテンツ分析**：
**ガイド付き分析**: AN-495592
**書き出し**: AN-495077、AN-494337、AN-486563、AN-469919、AN-462560、AN-462372
**データビュー**: AN-492093、AN-467770、AN-455367、AN-444467
**データ収集**: AN-496439、AN-495339、AN-493456、AN-491984、AN-490515、AN-490479、AN-470065
**実装**:
**Report Builder**: AN-496602、AN-494224、AN-493737、AN-493508、AN-493505、AN-492806、AN-468981、AN-454376
**レポート**: AN-495661、AN-493562、AN-487058、AN-478768
**セグメント化**：
**スケジュール済みレポート**: AN-491103、AN-468049
**共有の指標とディメンション**: AN-493722
**オーディエンス分析**: AN-469101
**その他**: AN-493865

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **合計母集団レポート**<br/> Customer Journey Analytics接続に存在するプロファイルおよびルックアップデータセットで定義されたエンティティを分析してレポートできるようになりました。 また、分析とレポートは、イベントデータセットの時間ベースの一連のイベントにとどまりません。 <p>この能力により、ビジネスの顧客基盤のあらゆる範囲を反映する、新しいクラスのクエリ、指標、オーディエンス定義が可能になります。</p><p>（ドキュメントのリンクは以下を参照。）</p> | | 未定<p>（当初は2026年9月22日に予定）</p> |
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>次に、スケジュールデータアップロードでサポートされるライブコンテンツの例を示します。</p><ul><li>FAST （無料の広告サポート付きテレビ）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、「[ ライブコンテンツを追跡するためのスケジュールデータのアップロード ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)」を参照してください。</p> | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |

>[!MORELIKETHIS]
>
>* [2026年の以前のCustomer Journey Analytics リリースノート ](/help/release-notes/2026.md)
>* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
>* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
>* [CX Enterprise リリースノート ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
>* [Customer Journey Analytics ドキュメントの更新](/help/release-notes/doc-changes.md)

