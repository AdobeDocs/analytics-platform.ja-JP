---
title: 会話インサイトの実装
description: 会話インサイト用にエージェントアプリケーションまたはサービスを測定する方法について説明します。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 7%
---
# 会話インサイトの実装

会話データをXDM エクスペリエンスイベントとして生成し、これらの会話エクスペリエンスイベントがデータセットとしてAdobe Experience Platformに格納されるようにするには、エージェントアプリケーションまたはサービスにConversation Insightsを使用するようにインストルメントします。

この記事では、必要な実装ステップについて説明します。

>[!PREREQUISITES]
>
>* データを収集するには、Experience Platform環境（組織とサンドボックス）が使用可能である必要があります。
>* Adobeの組織は、実験的なエージェントと会話のフィールドグループに対して有効にする必要があります。
>

## スキーマとデータセット

主な会話イベントのデータセット（プロンプト、応答、フィードバック）を設定します。 これらのデータセットは、同じスキーマ（汎用的なConversation Insights スキーマなど）に基づくことも、個々のスキーマに基づくこともできます。
プロンプト、レスポンス、フィードバックに対して個別のデータセットを定義したり、データセットにデータを組み合わせたりできます。 例えば、プロンプトや回答にデータセットを、フィードバックにデータセットを使用できます。 単一のデータセットを使用して会話イベントを更新したりできます。

プロンプト、応答、およびフィードバックデータセットに使用されるスキーマは、必須フィールドグループを含むXDM Experience Event ベーススキーマを拡張する必要があります。 追加のフィールドグループを使用してXDM Experience Event基本スキーマを拡張できます。

### エージェント情報フィールドグループ

**[!UICONTROL エージェント情報]** フィールドグループは必須フィールドグループであり、`agenticExperience` オブジェクトを使用します。

+++ 詳細

| フィールドパス（ドット表記法） | タイプ | 値の例 | メモ |
|---|---|---|---|
| `conciergeID` | string | `"concierge-abc123"` | **新規。** Concierge の一意の ID |
| `name` | string | `"Brand Concierge"` | エージェントのセットを組み合わせた Concierge の名前 |
| `version` | string | `"1.0.0"` | エージェントのセットを組み合わせた Concierge のバージョン |
| `environment` | string | `"prod"` | このイベントの発生元の環境（開発、ステージ、製品） |
| `mode` | string | `"release"` | エージェントのモード（テスト、プレビュー、リリース） |
| `agents[]` | 配列 | 以下のエージェントオブジェクトを参照してください | 使用されるエージェントの配列 |
| `agents[].agentID` | string | `"agent-001"` | **新規。** エージェントの一意の識別子（以下`skills[].agentID`が参照） |
| `agents[].name` | string | `"Chatbot Assistant"` | エージェント名 |
| `agents[].version` | string | `"2.1.3"` | エージェントバージョン |
| `agents[].score` | number | `0.92` | 返された値のエージェント信頼スコア |
| `agents[].skills[]` | 配列 | 以下のスキルオブジェクトを参照してください | **非推奨** – 代わりに以下のトップレベル `skills[]`配列を使用します。この配列は、スキル呼び出しの完全な順序付きリストを所有し、`agentID`を介して各1つをエージェントにリンクします |
| `agents[].skills[].name` | string | `"Intent Recognition"` | スキル名（非推奨の配列） |
| `agents[].skills[].version` | string | `"1.0.0"` | スキルバージョン（非推奨の配列） |
| `agents[].skills[].score` | number | `0.95` | スキルの信頼性スコア （0-1） （非推奨の配列） |
| `agents[].skills[].parameters[]` | 配列 | 以下のパラメーターを参照してください | スキルに送信されるパラメーター（キーと値のペア）（非推奨の配列） |
| `agents[].skills[].parameters[].key` | string | `"language"` | パラメーターキー |
| `agents[].skills[].parameters[].value` | string | `"en-US"` | パラメーター値 |
| `skills[]` | 配列 | 以下のスキル呼び出しオブジェクトを参照してください | **新規、実験的。** このエクスペリエンスに対するスキルの呼び出しを、すべてのエージェントをまたいで完全に順序付けしたリストです。 非推奨のエージェントごとの`agents[].skills[]`配列を置き換えます |
| `skills[].skillID` | string | `"skill-intent-recognition"` | 呼び出されたスキル定義の識別子 |
| `skills[].skillInvocationID` | string | `"inv-9f2a-001"` | 再配信でも一貫性のある、個々のスキルの呼び出しに対する一意のID。 スキルアレイをダウンストリームに結合する際の重複排除キー |
| `skills[].name` | string | `"Intent Recognition"` | 呼ばれたスキルの名前 |
| `skills[].version` | string | `"1.0.0"` | 呼び出されたスキルのバージョン |
| `skills[].agentID` | string | `"agent-001"` | `agents[].agentID`に関連するこのスキルを呼び出したエージェントの識別子。 サブエージェントが並行して実行されるため、主要な消費者がエージェント内でスキルを注文するために使用するグループ化 |
| `skills[].invocationSource` | string | `"main"` | メイン エージェンティック ループ （`main`）によって呼び出されたか、サブエージェント （`subagent`）によって呼び出されたか |
| `skills[].score` | number | `0.95` | スキルのマッチング結果のスコア |
| `skills[].failed` | ブール型 | `false` | スキルの実行に失敗したことを示すフラグ |
| `skills[].errorReason` | string | `"timeout"` | `failed`がtrueの場合、スキルが失敗した理由 |
| `skills[].sequenceNumber` | 整数 | `1` | サブエージェントが並行して実行されるため、単一のエージェント実行内でこのスキルコールのインデックスが単調に増加します。これはターン・グローバルではありません。 消費者は`agentID`、次いで`sequenceNumber`、`timestamp`をタイブレークとして注文します。 オプション |
| `skills[].timestamp` | string （date-time） | `"2026-09-11T00:03:15Z"` | スキルが呼び出された時間（ISO 8601 UTC）。 `sequenceNumber`の後にキーを注文しています。 プロデューサーは必ずこれを入力する必要があります |
| `skills[].skillSource` | string | `"inline"` | スキル定義がランタイムに配信された方法：`inline` （コンテキストにインラインで読み込まれた）または`deferred` （オンデマンドで読み込まれた） |
| `skills[].executionContext` | string | `"inline"` | スキルが呼び出し元エージェントに対して実行される場所：`inline`または`forked` （分岐されたサブエージェントコンテキストで実行） |
| `skills[].reasoning.narration` | string | `"Recognized an intent to verify a geography fact"` | なぜこのスキルが呼ばれたのかを自然言語で説明 |
| `skills[].parameters[]` | 配列 | 以下のパラメーターを参照してください | スキルに渡されるパラメーター |
| `skills[].parameters[].key` | string | `"language"` | パラメーターキー |
| `skills[].parameters[].value` | string | `"en-US"` | パラメーター値 |

+++

エージェント情報フィールドグループをデータで伝播するイベントを実装するには、次のことを確認する必要があります。

* エージェント設定

  * 各エージェントには、一意のエージェント ID、名前、バージョンの組み合わせがあります。
  * エージェントスコアは`0.0`から`1.0`の間で正規化されます。
  * `agentID`を使用して、スキル呼び出しでエージェントを参照します。

* スキル呼び出し

  * 各エージェントの下にスキルをネストするのではなく、すべてのエージェントをまたいで、スキル呼び出しごとに1つのエントリのみを出力します。
  * skillInvocationIDを設定して、ダウンストリームブレンドで重複する再配信イベントを削除できるようにします。
  * 消費者に適切な注文を行う： `agentID`でグループ化し、`sequenceNumber`で並べ替えて、`timestamp`にフォールバックします。 サブエージェントは並行して実行できるため、注文が必要です
  * `invocationSource`と`executionContext`を使用して、プライマリとサブエージェントのスキルを区別し、インラインとフォークされた実行を区別します。
  * 非推奨の`agents[].skills[]`配列を使用しないでください。 過去に配列を使用したことがある場合は、その配列を読み取り専用オブジェクトとして扱います。

* スキルのパラメーター

  * パラメーターは、Adobe XDM キー値データタイプを使用し、言語設定、しきい値、モデル設定に共通のパラメータータイプを使用します。 例えば、`"key":"language", "value":"en-US"` のように設定します。

+++ エージェンティック情報フィールドグループの使用例 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### 会話イベントフィールドグループ

**[!UICONTROL 会話イベント]** フィールドグループは必須フィールドグループであり、`conversation` オブジェクトを使用します。

会話オブジェクトは、次のデータをキャプチャします。

#### 会話

一意の`conversationID`が会話を識別します。 例：`conversationID = "conv-001"`。 スキーマは`conversationName`もサポートしています。 会話の全体的なコンテキストを説明する、人間が読み取れる名前（例：`France Geography Q&A`）。

`conversationID`を使用すると、関連するすべてのturns イベントを同じ会話型エクスペリエンスにグループ化できます。

#### ターン

ターンとは、会話内のひとつのインタラクションサイクルのことです。

`turnID`一意の`turnID`はターンを識別します。 次に例を示します。

`conversationID = "conv-001"`
`turnID = "turn-001"`

同じ`conversationID`と`turnID`を使用して、そのターンに関連付けられたプロンプト、応答、フィードバックを関連付けます。 この相関関係は、別々に配信されるか、異なるデータセットに格納されるレコードをまたいで機能します。


#### プロンプト

プロンプトは、エージェントに送信された入力です。 ほとんどの顧客シナリオでは、この入力はユーザーの質問、リクエスト、命令、またはメッセージです。

プロンプトは次の表現を使用します：`conversation.prompt`

重要なプロンプトフィールドは次のとおりです。

| フィールド | 意味 |
|---|---|
| `prompt.source` | 誰が、何をプロンプトコンテンツとして制作したのか、一般的にはエンドユーザーです。 |
| `prompt.raw[]` | 1つ以上の生コンテンツセグメント。 |
| `prompt.raw[].text` | 実際のプロンプトテキストやコンテンツ。 |
| `prompt.raw[].purpose` | ユーザー入力やリンクなど、コンテンツの目的。 |

1つのプロンプトに複数の生セグメントを含めることができます。 例えば、ユーザーがテキストを入力し、URLを含めるとします。

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### 応答

応答とは、エージェントまたは他の応答者から返されるコンテンツです。

`conversation.response`一意の`responseID`は応答を表します。

重要な応答フィールドは次のとおりです。

| フィールド | 意味 |
|---|---|
| `response.source` | 誰が、何が、反応を生んだのか。 |
| `response.raw[]` | 1つ以上のレスポンシブコンテンツセグメント |
| `response.raw[].text` | 応答テキストまたはコンテンツ。 |
| `response.raw[].purpose` | コンテンツセグメントの目的。 |

文書化されたソースタイプには、次のものが含まれます。

| ソース | 意味 |
|---|----|
| `bot` | 自動エージェント応答： |
| `canned` | 事前定義済みまたはテンプレート化された応答。 |
| `concierge` | 人間のエージェント応答： |
| `end-user` | 該当する場合、人間が生成したコンテンツ： |

#### フィードバック

フィードバックとは、インタラクションに対するユーザーの明示的な評価または反応を指します。

フィードバック構造に含まれるもの：`conversation.feedback`。

例：

* `feedback.raw[].text: "Great help"`
* feedback.rating.score: 1
* feedback.rating.classification: &quot;Thumbs Up&quot;
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

文書化された評価スコアの範囲は`-1.0`から`1.0`です。

フィードバックイベントは、`eventType = "conversation.feedback"`を使用してフィードバック専用イベントとして表すことができます。

フィードバックが特定のターンに適用される場合は、会話ブレンダーがフィードバックを関連するインタラクションに関連付けられるように、適切な`conversationID`と`turnID`を保持します。


#### シグナル

シグナルとは、会話コンテンツに関する体系化された分析観察のことです。 信号抽出サービスは、信号を抽出する。

信号には次のフィールドがあります。

| フィールド | 意味 |
|---|----|
| `scope` | turnやconversation-to-dateなど、信号の導出に使用される入力範囲。 |
| `name` | 被写体、インテント、トーン、センチメントなどの信号ID。 製品定義の信号名もサポートされています。 |
| `type` | 値タイプ：文字列、数値、またはブール値。 |
| `values[]` | 信号に関連付けられた1つ以上の値。 |
| `stringValue` | 意図、トーン、被写体などの文字列信号の値。 |
| `numberValue` | センチメントスコアなどの数値シグナル値。 |
| `booleanValue` | true/false シグナル値。 |
| `confidence` | シグナル値に対するオプションのプロデューサーの信頼性（通常は0 ～ 1の間）。 |
| `qualifiers[]` | シグナル値にコンテキストを追加するオプション記述子。 |
| `metadata[]` | オプションのプロデューサー定義キー/値メタデータ。 |


信号抽出サービスは、信号データセットの`signals` オブジェクトにデータを入力します。

以前の`signals[].attributes.{subjects,intents,tones,sentiment}` コンテナは非推奨です。

#### 会話

会話オブジェクトの詳細については、以下を参照してください。

+++ 詳細 

| フィールドパス（ドット表記法） | タイプ | 値の例 | メモ |
|---|---|---|---|
| `conversationID` | string | `"conv-001"` | 複数のターンをグループ化 |
| `conversationName` | string | `"France Geography Q&A"` | **新規。** 全体のコンテキストを表す会話に付けられた名前 |
| `turnID` | string | `"turn-001"` | このターンの一意のID |
| `prompt.source` | string | `"end-user"` | プロンプトのSource、その他のオプションには、キャッシュ値、定型値などが含まれます。 |
| `prompt.raw[]` | 配列 | 以下のRaw オブジェクトを参照してください | 生のプロンプト データ |
| `prompt.raw[].text` | string | `"What is the capital of France?"` | 実際のテキストコンテンツ |
| `prompt.raw[].purpose` | string | `"User Input"` | このテキストセグメントの目的 |
| `response.source` | string | `"bot"` | 応答のSource |
| `response.raw[]` | 配列 | 以下のRaw オブジェクトを参照してください | 生の応答データ |
| `response.raw[].text` | string | `"The capital of France is Paris."` | 応答テキストコンテンツ |
| `response.raw[].purpose` | string | `"main"` | レスポンスセグメントの目的。その他のオプションには、リンク、写真などが含まれます。 |
| `feedback.source` | string | `"end-user"` | Source of feedback |
| `feedback.raw[]` | 配列 | 以下のRaw オブジェクトを参照してください | 生のフィードバックデータ |
| `feedback.raw[].text` | string | `"Great help"` | フィードバックテキスト |
| `feedback.raw[].purpose` | string | `"free-form text"` | フィードバックセグメントの目的。スクリーンショットやメディアなど、他のオプションも考えられます |
| `feedback.rating.score` | number | `1` | -1.0から1.0までの数値レーティングスコア |
| `feedback.rating.classification` | string | `"Thumbs Up"` | 評定分類 |
| `feedback.rating.reasons[]` | 配列 | `["Accurate", "Quick response"]` | 評価理由の配列 |
| `signals[]` | 配列 | 以下の信号オブジェクトを参照してください | このイベントとこれまでの会話にもとづいて導き出されたシグナルです。 各エントリは、独自のスコープを持つ1つの名前付き信号です |
| `signals[].scope` | string | `"turn"` | この一連のシグナルが導き出される入力の範囲（ターン、会話の最新、最後のN ターン、フィードバック） |
| `signals[].attributes` | オブジェクト | 以下の属性を参照してください | **非推奨です。** 信号属性のコンテナ。 各属性は、値または値を含むオブジェクトです。 これは、シグナルを生成するために使用されるマシンラーニング/エージェント情報の母集団をサポートする予想されるニーズに対応するためです。 |
| `signals[].attributes.subjects` | オブジェクト | 以下の被写体を参照 | **非推奨です。** 被写体コンテナ |
| `signals[].attributes.subjects.values[]` | 配列 | 以下の件名の値を参照 | **非推奨です。** 件名の値の配列 |
| `signals[].attributes.subjects.values[].phrase` | string | `"product pricing"` | **非推奨です。** 範囲を指定した入力から抽出されたフレーズまたはキーワード |
| `signals[].attributes.subjects.values[].qualifiers[]` | 配列 | `["important", "urgent"]` | **非推奨です。** フレーズの修飾子のリスト |
| `signals[].attributes.intents` | オブジェクト | 以下のインテントを参照 | **非推奨です。** インテントコンテナ |
| `signals[].attributes.intents.values[]` | 配列 | `["make a purchase", "learn more"]` | **非推奨です。** スコープ付き入力から派生したインテント |
| `signals[].attributes.tones` | オブジェクト | 以下のトーンを参照してください | **非推奨です。** トーンコンテナ |
| `signals[].attributes.tones.values[]` | 配列 | `["thrilled", "contemplative"]` | **非推奨です。** 範囲指定された入力から派生したトーン |
| `signals[].attributes.sentiment` | オブジェクト | 以下のセンチメントを参照してください | **非推奨です。** センチメントコンテナ |
| `signals[].attributes.sentiment.value` | number | `0.71` | **非推奨です。** センチメントを示す–1 （負）から1 （正）のスコア |
| `signals[].name` | string | `"sentiment"` | **New** （非推奨の`attributes` コンテナに置き換わります）。 このシグナルの識別子（例：「被写体」、「インテント」、「トーン」、「センチメント」、またはプロデューサー定義の名前）。プロデューサーは、スキーマを変更することなく、新しいシグナルタイプを追加できます |
| `signals[].type` | string | `"number"` | **新規。** このシグナルの値のデータ型（`string`、`number`または`boolean`） — `values[]`の各エントリに入力される入力値フィールドを消費者に伝えます |
| `signals[].values[]` | 配列 | 以下のvalues オブジェクトを参照してください | この信号の1つ以上の値 |
| `signals[].values[].stringValue` | string | `"curious"` | `type`が「文字列」の場合に入力されます。意図、トーン、抽出されたフレーズなどのカテゴリ値です |
| `signals[].values[].numberValue` | number | `0.71` | `type`が「数値」の場合に入力されます。例えば、-1から1までのセンチメントスコアや、適用度などです |
| `signals[].values[].booleanValue` | ブール型 | `true` | `type`が「ブール値」 — true/false フラグの場合に入力 |
| `signals[].values[].confidence` | number | `0.9` | **新規。** プロデューサーがこの値に割り当てる信頼性（0から1まで） |
| `signals[].values[].qualifiers[]` | 配列 | `["important", "urgent"]` | キーワードと同様ですが、より意味のある、この値の追加の記述子 |
| `signals[].values[].metadata[]` | 配列 | 以下のパラメーターを参照してください | **新規。** この値に対するプロデューサー定義のメタデータをキーと値のペアとして（例：シグナルを生成したML/エージェントに関するコンテキスト） |

+++




### 追加のフィールドグループ

プロンプト、応答、フィードバックのデータセットに使用するスキーマに、オプションのフィールドグループを追加できます。 次に例を示します。

* **Web詳細** フィールドグループ。 会話が埋め込まれたweb ページの詳細をキャプチャします。
* **Commerce詳細** フィールドグループ。 会話の一部として言及された推奨製品の製品詳細を取り込みます。



お客様は、ソース会話イベントを作成する責任があります。 その後、Adobe Platformは信号抽出とデータブレンドを実行します。 お客様は、シグナル抽出または描画サービスを実装する必要はありません。

このドキュメントでは、会話インサイト MVPの入力要件と現在のエージェント スキーマの更新について説明します。 これには、Conversation Insights 1.0の機能または以降のリリース要件は含まれていません。

### イベントタイプ

会話イベントごとに`eventType` （文字列）に次のいずれかの値を設定する必要があります。

| 値 | 説明 |
|---|---|
| `conversation turn` | プロンプトと応答による完全な会話の順番 |
| `conversation recommendation` | 会話ベースのレコメンデーション |
| `conversation feedback` | フィードバック専用イベント |


### ソースタイプ

イベント内の各`prompt`、`response`、または`feedback` オブジェクトに対して、`source`に次のいずれかの値を設定する必要があります。

| 値 | 説明 |
|---|---|
| `end-user` | 人間によるユーザー入力 |
| `bot` | 自動エージェント応答 |
| `canned` | 事前に定義/テンプレート化された応答 |
| `concierge` | 人間のエージェントの応答 |

### 目的の種類（生テキスト）

`prompt`、`response`、または`feedback` オブジェクト内の`raw` オブジェクトの任意の要素で、`purpose`属性に次のいずれかの値を設定する必要があります。

| 値 | 説明 |
|---|---|
| `User Input` | プライマリユーザー入力 |
| `main` | メインの応答コンテンツ |
| `advertisement` | プロモーションコンテンツ |
| `citation` | 参照/ソースリンク |
| `link` | 外部リンク |
| `image` | 画像参照 |
| `enum picker` | 構造化されたフィードバックの選択 |


### 例

様々なシナリオでの会話イベントフィールドグループの使用例については、以下を参照してください。

+++ 詳細 

>[!BEGINTABS]

>[!TAB  イベントの例を表示]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB 応答イベントの例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB  フィードバックイベントの例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB 商品レコメンデーションイベントの例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## データ収集

会話インサイトには、次のデータ収集戦略を使用します。


### イベントタイプ

エージェントのアプリケーションまたはサービスは、できるだけ早くイベントを送信します。 アプリまたはサービスが応答を待たないことを確認してから、イベント時に利用可能な情報を含むプロンプトを送信します。

この推奨事項は、次のことを意味します。

* プロンプト、応答、フィードバックのオブジェクトは個別に入力されるため、単一のイベントの一部として強制的に指定する必要はありません。
* データセット間で同じ`conversationID`と`turnID`を持つイベントが複数必要です。

### イベント相関性

エージェントアプリケーションまたはサービスは、関連するすべてのイベントにわたって安定した識別子を保持する必要があります。

| フィールドパス | 説明 |
|---|---|
| `conversation.conversationID` | 会話全体を表す一意のID。 |
| `conversation.turnID` | 会話内の個々のターンに対する一意のID。 |
| `_id` | エクスペリエンスイベントレコード ID。 |
| `timestamp` | イベントが発生した時刻。 |
| `eventType` | 会話イベントのタイプを識別します。 |

* 同じ会話に属するすべてのイベントには、同じ`conversationID`を使用する必要があります。

* 同じ`turnID`を、プロンプト、応答、および同じターンに関連付けられたすべてのフィードバックに使用する必要があります。 同じ`turnID`を持つイベントが、プロンプト、応答、フィードバックのデータセットをまたいで複数存在する可能性があります。

エージェントアプリケーションまたはサービスは、再試行または再配信中に安定したIDを生成します。 これにより、下流処理でイベントを正しく関連付け、意図しない重複イベントを回避できます。

## 信号抽出

シグナル抽出はデータ収集後に行われます。 エージェントのアプリケーションまたはサービスは、追加のシグナルを入力しません。

+++ シグナルを含むターンイベントの例

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## データブレンディング

会話ブレンダーサービスは、プロンプト、応答、フィードバック、およびシグナルイベントデータセットのイベントを、専用のブレンドされた会話イベントデータセットに統合します。 そのデータセットは、接続の一部としてCustomer Journey Analyticsで使用されます。 そのデータセット内のコンポーネントは、Conversation Insights設定に指定したデータビューに追加されます。
