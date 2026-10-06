---
title: 最新のCustomer Journey Analytics リリースノート
description: 最新のCustomer Journey Analytics リリースノート（新機能、修正済みの問題、現在延期されているリリースなど）をご覧ください。
hold: true
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
source-git-commit: 4f62a406436915d581ab30f26b82544388957782
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 29%
---
# 最新のCustomer Journey Analytics リリースノート（2026年9月）

**最終更新**: 2026年9月9日（PT）

これらのリリースノートは、2026年9月のリリース期間をカバーしています。 Adobe Customer Journey Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または更新された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **会話インサイトを利用して、Analysis WorkspaceのLLM カスタマーエクスペリエンスを分析**<br/> Customer Journey Analyticsでは、非構造化チャットデータをAnalysis Workspaceに取り込み、プロパティ全体で発生するLLMを活用した閲覧体験と購買体験についてレポートを作成できるようになりました。<p>この機能を使用すると、次のことが可能になります。</p><ul><li>Web SDKを使用して、会話型エージェント（組織のカスタムエージェントまたはAdobe Brand Concierge）からプロンプト、レスポンス、エージェントメタデータを収集します。</li><li>意図、トーン、センチメントを分析することで、顧客が何を求めているのか、担当者がどのように反応するのか、顧客がどのように感じているのかを把握できます。</li><li>既存のスキーマ、データセット、データビューを利用して大規模に分析し、Analysis Workspaceでインサイトを獲得できます。</li><li>エージェントとのやり取りを、より広範なカスタマージャーニーに結び付けることで、結果に会話を結びつけ、コンバージョンやエンゲージメントなどへの実際の影響を測定することができます。</li></ul><p>以前は、LLMを活用したエクスペリエンスを測定するのは困難で、既存のカスタマージャーニーとつながることもほぼ不可能でした。</p><p>詳しくは、[会話インサイト &#x200B;](/help/conversation-insights/overview.md)を参照してください</p> | | 2026年10月8日（PT）<p>（当初は2026年9月22日に予定）</p> |
| **コンポーネントの説明を自動生成** <br/> ディメンション、指標、計算指標、セグメント、日付範囲の説明を自動的に生成できるようになりました。 これにより、Workspace ユーザーは、特に大規模なコンポーネントライブラリを持つ組織で使用するコンポーネントを理解できます。 <p>1つのコンポーネントに対して説明を生成したり、同時に多くのコンポーネントに対して説明を生成したりできます。</p> <p>（ドキュメントのリンクは以下を参照。）<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026年10月28日（PT） |
| **Adobe Brand Visibilityとの統合**<br/> Adobe Adobe Brand Visibilityを組織のAdobe Analyticsデータと連携させて、AIを活用した発見が、web サイトの実際のエンゲージメントとビジネスの成果にどのように結びつくのかを測定できます。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年10月</p> |


### Customer Journey Analytics の修正点

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930, AN-468325
**コンポーネント**：
**接続**: AN-451458、AN-365942
**コンテンツ分析**：
**ガイド付き分析**: AN-485600
**書き出し**: AN-489161、AN-467131、AN-464746、AN-469034、AN-447252、AN-437803、AN-394444
**データビュー**: AN-478732、AN-468836、AN-467851、AN-487651、AN-423592
**データ収集**: AN-489829、AN-489722、AN-469451、AN-467436、AN-467049、AN-466087、AN-465049、AN-463524、AN-457433、AN-490288、AN-487500、AN-390916、AN-342311
**実装**:
**Report Builder**: AN-487486、AN-478944、AN-470036、AN-468589、AN-468436、AN-456747、AN-456700、AN-442695、AN-492330、AN-490564、AN-468293、AN-460921
**レポート**: AN-479145、AN-469095、AN-468070、AN-467786、AN-456684、AN-465257、AN-422685、AN-406114、AN-356706、AN-322733
**セグメント化**: AN-486561、AN-278260
**スケジュール済みレポート**: AN-479157
**共有指標と共有ディメンション**：
**オーディエンス分析**:AN-468237、AN-462553
**その他**: AN-469601、AN-462817、AN-362308、AN-349757、AN-326432、AN-326345、AN-324341、AN-309317

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **合計母集団レポート**<br/> Customer Journey Analytics接続に存在するプロファイルおよびルックアップデータセットで定義されたエンティティを分析してレポートできるようになりました。 また、分析とレポートは、イベントデータセットの時間ベースの一連のイベントにとどまりません。 <p>この能力により、ビジネスの顧客基盤のあらゆる範囲を反映する、新しいクラスのクエリ、指標、オーディエンス定義が可能になります。</p><p>（ドキュメントのリンクは以下を参照。）</p> | | 未定<p>（当初は2026年9月22日に予定）</p> |
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>次に、スケジュールデータアップロードでサポートされるライブコンテンツの例を示します。</p><ul><li>FAST（広告付き無料テレビ）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、「[&#x200B; ライブコンテンツを追跡するためのスケジュールデータのアップロード &#x200B;](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)」を参照してください。</p> | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |

>[!MORELIKETHIS]
>
>* [2026年の以前のCustomer Journey Analytics リリースノート &#x200B;](/help/release-notes/2026.md)
>* [Adobe Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
>* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
>* [CX Enterprise リリースノート &#x200B;](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)
>* [Customer Journey Analytics ドキュメントの更新](/help/release-notes/doc-changes.md)

