---
title: LLM Optimizerとの連携
description: LLM OptimizerとCustomer Journey Analyticsの統合
feature: Experience Platform Integration
role: User
feature_v2: id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
source-git-commit: 3aa4e0c98e9a3e4163dad992e598638892fc88cd
workflow-type: tm+mt
source-wordcount: 2539
ht-degree: 3%

---


# LLM Optimizerとの連携

[Adobe LLM Optimizer](https://experienceleague.adobe.com/ja/docs/llm-optimizer/using/home){target="_blank"}は、生成AIを利用した生成エンジンの最適化向けの生成AI ファースト アプリケーションで、AIを活用した検索環境における企業の認知度、正確性、影響力の向上を支援するように設計されています。 LLM Optimizerは、AIが生成した回答のブランドプレゼンスに関するインサイトを提供し、規範的なコンテンツレコメンデーションを提供し、最適化の修正を自動化します。

AIが主要な発見チャネルに。 ChatGPT、Claude、Copilot、PerplexityなどのLLM エージェントは、ブランドコンテンツをクロールします。

>[!PREREQUISITES]
>
>LLM Optimizerの有料サービスがプロビジョニングされ、マネージドコネクタを介してExperience Platform設定に接続されている必要があります。


>[!IMPORTANT]
>
>この統合の一環として、LLM Optimizerデータの一時的な処理が米国で行われます。 データは、Customer Journey Analytics コントラクトで設定されたとおりに、指定したリージョンに最終的に保存されます。


## ユースケース

Customer Journey AnalyticsとLLM Optimizerの連携には、次のふたつの利点があります。

* **インバウンド統合**: Customer Journey AnalyticsのLLM Optimizer データを使用して、既存のweb、モバイル、その他の種類のデータと並行して、LLM主導のトラフィック（ボットweb クローラー、RAG リクエスト、エージェントアクティビティ）を測定します。 例えば、次のことができます。

  * 従来のチャネルと並行して、エージェントソース別にLLMによるトラフィックを測定。

  * LLMが頻繁に使用するものの、人間のコンバージョンではパフォーマンスが低いコンテンツを特定します。

  * クリティカルパスをまたいで、LLM-agent リクエストが失敗する場所を検出します。

  * ページに対するLLM ボットの需要を、URLおよびホストレベルで照合された、web データ内のページのコンバージョンと収益と比較します。

* **アウトバウンド統合**: Customer Journey AnalyticsのパフォーマンスデータをLLM Optimizerに送信して、ChatGPTやPerplexityなどの価値あるトラフィックを送信するLLM ソースのAIによる可視性を最適化できるようにします。 例えば、次のことができます。

  * コンバージョンや売上の向上に成功した人間の訪問者を送り込むLLM ソースを確認します。 Customer Journey Analyticsは、ボットデータセットからではなく、参照されるweb トラフィックからこれを測定します。
  * LLM ソースを、送信する訪問者のダウンストリームの価値によってランク付けし、AIによる可視化作業を最もパフォーマンスの高いソースに集中させます。


## インバウンド統合

LLMのトラフィックは、ふたつの方法でサイトに到達します。 Customer Journey Analyticsは、それぞれの方法で異なるデータソースから測定します。

まず、AIによる回答を読み、クリックしてサイトにアクセスする人が最初に考えられます。 その訪問では、web データの残りの部分を収集するのと同じJavaScriptが実行されます。 したがって、既存のCustomer Journey Analytics web データには、ユーザーを送信した訪問と参照ドメイン（例：chatgpt.com）が含まれます。 Customer Journey Analyticsは、これらの訪問を単独ではAI トラフィックとしてラベル付けしません。 それらを識別してグループ化するには、AI参照ドメインに一致する接続に派生フィールドを作成し、そのフィールドにセグメントとレポートを作成します。 [派生フィールド ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}を参照してください。 LLM Optimizerのデータセットは必要ありません。

ふたつ目の方法は、ページを直接リクエストするボットやエージェントです。 これには、AI インデックスを構築するweb クローラーや、利用者がAI アシスタントにプロンプトを送信したときに発生するライブフェッチが含まれます。 これらのリクエストはJavaScriptを実行しないため、既存のweb データには記録されません。 LLM Optimizer データセットは、CDN レイヤーからこのトラフィックをキャプチャします。 この節の残りの部分では、そのデータセットについて説明します。

### データセットをCustomer Journey Analyticsにオンボーディングする

LLM Optimizer管理コネクタは、サマリーデータセットとしてデータをExperience Platformに配信します。 Customer Journey Analyticsで測定するには、次の2つの設定手順を実行します。

1. LLM Optimizer データセットを含む接続を作成します。 [接続の作成または編集](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}を参照してください。
2. その接続にデータビューを作成します。 データビューでは、以下のディメンションと指標をAnalysis Workspaceで使用できます。 [ データビューの作成または編集](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}を参照してください。

データセット：

* XDM要約指標クラスに基づく[概要データセット ](/help/data-views/summary-data.md)を使用します。
* URLとホスト、時間、ボットの種類、CDN プロバイダー、ステータスなどのリクエスト特性ごとにデータをバケット化します。

>[!NOTE]
>
>LLM Optimizer データセットには、集計データが含まれています。 ユーザーID、プロンプト、応答などのPIIが含まれていません。
>

サマリーデータセットなので、ルックアップデータセットとして扱い、完全URL キーのイベントデータセットに結合できます。

LLM Optimizerは、**CDN URL** ディメンションでこのキーを提供します。 これは、Customer Journey Analyticsがweb データを保存する方法と同様に、ホストとリクエストされたパスを1つの正規化された完全なURLに結合します。 結合が成功するかどうかは、独自のデータ収集によって異なります。 イベントデータセットには、同等の完全なURL フィールド、またはLLM Optimizerが提供するURLに一致するように解析および正規化できるフィールドが必要です。 双方が同じ完全なURLに解決すると、LLM Optimizer レコードはweb データ内の対応するページと一致します。

### データセットについて

LLM Optimizerは、サーバーサイドでCDN アクセスログを読み取り、リクエスト側の関係者がボットまたは自動エージェントであるレコードを抽出します。 データはCDN レイヤーから取得されるため、LLM OptimizerはJavaScript タグを実行しないボットからのリクエストをキャプチャします。 標準的なweb分析ツールでは、このトラフィックを完全に見逃してしまいます。

データセットは、**CDN要求概要** フィールドグループを使用します。 すべてのフィールドは`cdn` オブジェクトの下に配置されているため、以下のテーブルのフィールド名は`cdn.<name>`の形式（例：`cdn.url`と`cdn.botType`）になります。

各レコードは、ホスト、URL パス、ボットタイプ、CDN プロバイダー、ステータスコード、リファラー、転送ホスト、1時間の最初のバイトまでの時間の1つの組み合わせを記述します。 同じ組み合わせが1時間に1回以上表示される場合、Customer Journey Analyticsはこれらのレコードを1行に組み合わせ、リクエスト数を増やします。 **CDN要求数**&#x200B;指標を使用して、ボリュームを測定します。 行数は使用しないでください。

### ディメンション

次のディメンションは、LLM Optimizer データセットを含む接続を設定した後に、データビューでコンポーネントとして使用できます。 **フィールド**&#x200B;列には、CDN リクエストの概要フィールドグループのソースフィールドが表示されます。

| ディメンション | フィールド | 説明 |
|-----------|-------|-------------|
| CDN URL | `cdn.url` | 結合キーとして意図された、リクエストの正規化された完全URL。 LLM Optimizerは、ホストとリクエストされたパスを1つのURLに結合し、Customer Journey Analyticsがweb データ用に保存する完全なURL フォームに一致するように正規化します。 このディメンションを使用して、LLM Optimizer ルックアップデータセットを、同等のフル URL フィールドを持つイベントデータセットに結合します。 ホストとパスは含まれますが、スキームは含まれません。 |
| CDN URL パス | `cdn.path` | CDNが配信した、エージェントが要求した生のURL パスとクエリ文字列。 スキームまたはホストが含まれていません。 正規化された結合キーではなく、要求されたパスを正確に取得する必要がある場合に使用します。 |
| CDN ホスト | `cdn.host` | リクエストを受け取ったホスト名（例：www.example.com）。 このホストは、CDN URL結合キーの一部でもあります。 1つのデータセットに、組織が同じCDN アカウントに複数のサブドメインを持つ場合、複数のホストを含めることができます。 |
| CDN ボットタイプ | `cdn.botType` | リクエスト側エージェントのLLM Optimizer分類。 値には、従来の検索web クローラー、AI インデックスweb クローラー、AI ライブフェッチ エージェントが含まれます。 完全な分類については、以下の[ ボットエージェントカテゴリ ](#bot-agent-categories)を参照してください。 |
| CDN ユーザーエージェント | `cdn.userAgent` | CDN ログの生のユーザーエージェント文字列。 ボット分類内のサブタイプを区別したり、LLM Optimizerによって割り当てられた分類を検証したりするのに便利です。 |
| CDN HTTP ステータス | `cdn.status` | HTTP応答ステータスコード。 ボットが要求したコンテンツを受信したかどうかを示します。 AI トラフィックに固有の解釈ガイダンスについては、以下の[ ステータスコード ](#status-codes)を参照してください。 |
| CDN プロバイダー | `cdn.cdnProvider` | CDNがリクエストを処理します。 値は`akamai`、`byocdn-akamai`、`byocdn-fastly`、`byocdn-cloudfront`です。 `byocdn-`接頭辞は、別のCDN ベンダーではなく、ログ収集パスを示します。 組織が異なるCDN設定の背後にホストを持つ場合、データセットに複数の値を含めることができます。 |
| CDN リファラー | `cdn.referer` | CDN ログのHTTP Referer ヘッダー値。 多くの場合、ボットトラフィックには空です。 存在する場合は、どのAI製品またはドメインがフェッチをトリガーしたかを示すことができます。 例：chat.openai.com |
| CDN転送ホスト | `cdn.xForwardedHost` | X-Forwarded-Host ヘッダー値（存在する場合）。 リクエストがオリジンに到達する前にリバースプロキシまたはCDN シールドレイヤーを通過した場合に関連します。 |
| CDN イベント日 | レコードのタイムスタンプから派生 | このレコードの時間単位のバッチタイムスタンプの日付部分。 |
| CDN イベント時間 | レコードのタイムスタンプから派生 | このレコードの時間バッチタイムスタンプの時間部分。 |

### ボットエージェントのカテゴリ

**CDN ボットタイプ** ディメンションは、エージェントを3つのカテゴリに整理します。 各カテゴリーは、それぞれ異なる分析的な質問に答えます。

従来の検索web クローラーのインデックス コンテンツ **従来の検索エンジンの**&#x200B;件。 このカテゴリーは、従来型の検索エンジンに対するコンテンツの見た目を測定するために使用します。

| ボットタイプ値 | ベンダー | 説明 |
|---|---|---|
| `GoogleBot` | Google | Googleのメイン検索インデックスweb クローラー。 Google DiscoverおよびGoogle Newsも提供しています。 |
| `BingBot` | Microsoft | Bingの検索インデックスweb クローラー Microsoft Copilotのweb グラウンディングインデックスにも対応しています。 |

**AI インデックスweb クローラー** AI製品のトレーニング コーパスまたは検索インデックスを作成または更新するためのコンテンツをクロールします。 これらのweb クローラーは、ライブユーザーリクエストに応答せずに、モデルのナレッジベースを準備しています。 URLのweb クローラー量が多い場合、AI ベンダーはコンテンツにインデックスを作成する価値があると考えます。 URLのweb クローラー量が少ないがライブフェッチ量が多い場合、モデルは新鮮なコンテンツをフェッチするのではなく、キャッシュされたナレッジから引き出します。

| ボットタイプ値 | ベンダー | 説明 |
|---|---|---|
| `GPTBot` | OpenAI | OpenAIの主なweb クローラーは、モデルのトレーニングデータとナレッジベースの構築です。 |
| `OAI-SearchBot` | OpenAI | ChatGPTのweb検索商品に対するOpenAIのweb クローラー。 GPTBotとは。 このエージェントは、トレーニングコーパスではなく、リアルタイム検索インデックスを構築します。 |
| `ClaudeBot` | 人文学 | モデルのトレーニングデータに対するAnthropicの主なweb クローラー。 |
| `Claude-SearchBot` | 人文学 | Claudeの検索および取得インデックスに対するAnthropicのweb クローラー。 ClaudeBotとは。 |
| `PerplexityBot` | 複雑性 | Perplexityのインデックスweb クローラー。 複雑性は、このエージェントを使用して、回答を生成するためのコーパスを構築します。 |

**AI ライブフェッチ**&#x200B;は、実際のユーザーがAI アシスタントにプロンプトを送信し、アシスタントが応答する前にページをライブでフェッチしたときに発生します。 このカテゴリは、AI アシスタントを通じてユーザーが直接到着する需要を測定するために使用します。

| ボットタイプ値 | ベンダー | 説明 |
|---|---|---|
| `ChatGPT-User` | OpenAI | あるユーザーがChatGPTに質問しました。 ChatGPTはこのURLを取得して読み、回答を入力しました。 |
| `ChatGPT Clients` | OpenAI | ChatGPT モバイルアプリ（iOSおよびAndroid）がライブフェッチを行います。 user-agent文字列には、アプリのバージョンとデバイスが含まれます。 |
| `Claude-User` | 人文学 | Claudeを使用するユーザーまたはアプリケーションは、このURLをライブフェッチしました。 ユーザーエージェント文字列は、特定のClaude製品を識別する場合があります（例：claude-code）。 |
| `Perplexity-User` | 複雑性 | ユーザーがPerplexityに質問しました。 複雑性がこのURLを取得し、回答をグラウンドにしました。 |
| `Google-NotebookLM` | Google | ユーザーがGoogle NotebookLMを開き、このドメインを取得しました。 NotebookLMは、ソース ドメイン内のすべての到達可能なURLを取得します。 |
| `Google-ai-mode` | Google | Google検索のAI概要このURLを取得し、検索結果のAI生成の回答パネルに含めました。 |
| `Gemini-Deep-Research` | Google | ユーザーが「ジェミニ深層調査」セッションを実施しました。 Deep Researchは、複数のソースにまたがる多くのシーケンシャルフェッチを行い、調査レポートを作成します。 |
| `GoogleAgent-URLContext` | Google | ユーザーはGeminiとURLを共有し、そのページについて質問しました。 Geminiは特定のコンテンツに関する質問に答えるためにURLをライブで取得しました。 |
| `Amzn-User` | Amazon | Amazon AlexaまたはAmazon AI エージェントがこのURLをライブフェッチしました。 通常は、参照コンテンツとドキュメントのコンテンツに表示されます。 |
| `MistralAI-User` | ミストラル | Mistralを活用した製品またはAPI コンシューマーからのライブフェッチ。 |

LLM Optimizerが認識されたパターンにuser-agentと一致しない場合、値`Unknown`が割り当てられます。 **CDN ユーザーエージェント** ディメンションを使用して、これらのリクエストを行ったエージェントを特定できます。

### ステータスコード

このデータセットのHTTP ステータスコードは、AI エージェントが要求したコンテンツを受信したかどうかを示します。

| ステータス | 名前 | 解釈 |
|--------|------|----------------|
| 200 | OK | ボットは完全な応答を受け取りました。 コンテンツはAIが利用できるようになりました。 |
| 304 | 未変更 | ボットは、コンテンツが変更されていないことを確認し、キャッシュされたバージョンを使用しました。 コンテンツは利用可能でした。 |
| 301 | 永続的に移動 | ボットは新しいURLにリダイレクトされました。 各リダイレクトは、追加のラウンドトリップを追加します。 頻繁にクロールされるURLで301 ボリュームが多い場合は、CDN レベルでリダイレクトを解決する必要があります。 |
| 302 | 見つかりました（一時的なリダイレクト） | 301と同じ遅延のペナルティ。 301とは異なり、恒久的な移動を示さないため、ボットは元のURLに戻り続けます。 |
| 403 | Forbidden | CDNまたは生成元がボットをブロックしました。 これは、意図的な場合（例：robots.txt ルールやWAF ポリシーなど）、意図的でない場合（例：過度に広いレート制限など）があります。 AIによる取得がブロックされると、そのコンテンツはAIの回答に表示されません。 |
| 404 | 見つかりません | URLが存在しません。 AI エージェントの種類で404件のボリュームが多い場合、AIのインデックスに古いURLが含まれていることを示します。 410 ステータスを使用して、web クローラーに対して、インデックスからURLを完全に削除するように指示します。 |
| 429 | リクエストが多すぎます | CDNは、ボットのレート制限を行いました。 ライブフェッチのエージェントタイプで429個のエラーが発生すると、AI アシスタントにコンテンツについて質問した利用者に対して、不完全な回答や欠けている回答が返されます。 |
| 504 | ゲートウェイがタイムアウトしました | CDNはオリジンが応答するのを待つのを停止しました。 コンテンツがAIに届かなかった。 ページがタイムアウトすると、AIはそのコンテンツにアクセスできず、回答に含めることもできません。 ライブフェッチのエージェントタイプで504個のボリュームが多いことは、AIによる直接的な可視化のリスクとなります。 |

### 指標

LLM Optimizer データセットを含む接続を設定すると、次の指標をデータビューでコンポーネントとして使用できます。 **フィールド**&#x200B;列には、CDN リクエストの概要フィールドグループのソースフィールドが表示されます。

| 指標 | フィールド | 説明 |
|--------|-------|-------------|
| CDN リクエスト数 | `cdn.requests` | すべての行のリクエストフィールドから合計されたCDN リクエストの合計数。 この指標は常にボリュームを測定するために使用します。 行数は使用しないでください。 |
| CDN エラー数 | `cdn.status`, `cdn.requests` | 4xxまたは5xx HTTP ステータスコードを返したリクエストの数。 |
| CDN エラー率 | CDN エラー数から派生 | エラー数は、リクエストの合計数に対する割合としてカウントされます。 |
| CDN平均最初のバイト時間 | `cdn.timeToFirstByte` | CDNがリクエストを受信してから応答の最初のバイトまでの平均時間（ミリ秒単位）です。 CDN キャッシュの応答は、通常50 ミリ秒未満です。 送信元から提供される応答は、通常300 ミリ秒から700 ミリ秒です。 AI ライブフェッチエージェントは、多くの場合、タイムアウトした応答や非常に遅い応答に対応する、より高い値を示します。 ライブフェッチのエージェントタイプの平均値が高いことは、AIによる可視化のリスクとして調査する価値があります。 |

### データセットの境界

このデータセットは、CDN アクセスログからのボットトラフィックのみをキャプチャします。 次の内容は含まれていません。

* **ユーザーセッション、コンバージョン、またはエンゲージメントデータ。** AIによる回答からクリックした利用者は、ページ上でJavaScriptを実行します。これにより、その訪問は、このデータセットではなく既存のweb データに格納されます。 両方のデータセットをCustomer Journey Analyticsに取り込み、同じURLとホストで比較できます。
* **ECIDなどの個人ID。** このデータセットから個人レベルの結合を行うことはできません。 結合は、URL レベルとホストレベルで動作します。
* **秒以下の時間の精度。** タイムスタンプは毎時間です。 1時間以内に数分や数秒に分割することはできません。
* **ページコンテンツまたはレンダリングされたHTML。** このデータセットには、AIがページから読み取ったものではなく、フェッチとその結果の事実が記録されます。
* **コンバージョンデータ。** このデータセットは、AIの回答が、オーディエンスのサイト訪問やコンバージョンにつながったかどうかを判断することはできません。 集約されたCDN概要データは個人ベースのイベントデータではなく保持されるので、リクエストを個々の個人またはセッションにリンクすることはありません。

## アウトバウンド統合

決定されます。


<!-- 

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl and reference brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII, such as user identifiers, prompts, or responses.
>

You use the LLM Optimizer dataset in a connection. Because the dataset is a summary dataset, you can use the dataset as a lookup dataset and potentially join to an event dataset on a full-URL key.

LLM Optimizer provides this key for you in the **CDN URL** dimension. The key combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. This join-key field facilitates the join. The outcome depends on your Customer Journey Analytics implementation and whether your event dataset has a page URL field that matches the URL representation LLM Optimizer provides. When both sides resolve to the same full URL, the LLM Optimizer record matches the corresponding page in your web data.

### About the dataset

LLM Optimizer reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, LLM Optimizer captures requests from bots that do not execute any JavaScript tag. Standard web analytics tools miss this traffic entirely.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears multiple times hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| CDN URL | The normalized full URL for the request, intended as the join key. LLM Optimizer combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the LLM Optimizer lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | LLM Optimizer's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by LLM Optimizer. |
| CDN HTTP Status | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and b`yocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When LLM Optimizer cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| CDN Request Count | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **Human sessions, conversions, or engagement data.** Human sessions are in your existing web analytics dataset. To correlate AI demand with human outcomes, join the two datasets in CJA at the URL and host level.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join works at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** Whether an AI answer led a user to visit the site or convert is not in this dataset. That analysis requires joining to human session data in CJA.

## Outbound integration

To be determined.

-->