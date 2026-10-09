---
title: ブランドの可視性の統合
description: Customer Journey Analyticsとブランドの可視性の統合
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Adobe Brand Visibilityとの連携

[Adobe Brand Visibility](https://experienceleague.adobe.com/ja/docs/brand-visibility/using/home){target="_blank"}は、生成AIを利用した生成エンジンの最適化向けの生成AI ファースト アプリケーションで、AIを活用した検索環境における企業の認知度、正確性、影響力の向上を支援するように設計されています。 ブランドの可視性は、AIが生成した回答のブランドプレゼンスに関するインサイトを提供し、規範的なコンテンツレコメンデーションを提供し、最適化の修正を自動化します。

AIが主要な発見チャネルに。 ChatGPT、Claude、Copilot、Perplexityなどの大規模言語モデル（LLM）エージェントは、ブランドコンテンツをクロールします。

>[!NOTE]
>
>ブランドの可視性の有料サービスがプロビジョニングされ、マネージドコネクタを介してExperience Platform設定に接続されている必要があります。


>[!IMPORTANT]
>
>この統合の一環として、ブランドの可視性データの一時的な処理が米国で行われます。 データは、Customer Journey Analytics コントラクトで設定されたとおりに、指定したリージョンに最終的に保存されます。


## ユースケース

Customer Journey Analyticsとブランドの可視性の連携には、次のふたつの利点があります。

* **インバウンド統合**: Customer Journey Analyticsのブランドの可視性データを使用して、既存のweb、モバイル、その他の種類のデータと並行して、LLM主導のトラフィック（ボットweb クローラー、RAG リクエスト、エージェントアクティビティ）を測定します。 例えば、次のことができます。

  * 従来のチャネルと並行して、エージェントソース別にLLMによるトラフィックを測定。

  * LLMが頻繁に使用するものの、人間のコンバージョンではパフォーマンスが低いコンテンツを特定します。

  * クリティカルパスをまたいで、LLM-agent リクエストが失敗する場所を検出します。

  * ページに対するLLM ボットの需要を、URLおよびホストレベルで照合された、web データ内のページのコンバージョンと収益と比較します。

* **アウトバウンド統合**: Customer Journey Analytics パフォーマンスデータをブランドの可視性に送信して、ChatGPTやPerplexityなどの価値あるトラフィックを送信するLLM ソースに対してAIによる可視性を最適化できるようにします。 例えば、次のことができます。

  * コンバージョンや売上の向上に成功した人間の訪問者を送り込むLLM ソースを確認します。 Customer Journey Analyticsは、ボットデータセットからではなく、参照されるweb トラフィックからこれを測定します。
  * LLM ソースを、送信する訪問者のダウンストリームの価値によってランク付けし、AIによる可視化作業を最もパフォーマンスの高いソースに集中させます。


## インバウンド統合

LLMのトラフィックは、ふたつの方法でサイトに到達します。 Customer Journey Analyticsは、それぞれの方法で異なるデータソースから測定します。

まず、AIによる回答を読み、クリックしてサイトにアクセスする人が最初に考えられます。 その訪問では、web データの残りの部分を収集するのと同じJavaScriptが実行されます。 したがって、既存のCustomer Journey Analytics web データには、ユーザーを送信した訪問と参照ドメイン（例：chatgpt.com）が含まれます。 Customer Journey Analyticsは、これらの訪問を単独ではAI トラフィックとしてラベル付けしません。 それらを識別してグループ化するには、AI参照ドメインに一致する接続に派生フィールドを作成し、そのフィールドにセグメントとレポートを作成します。 [派生フィールド &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}を参照してください。 ブランドの可視性データセットは必要ありません。

ふたつ目の方法は、ページを直接リクエストするボットやエージェントです。 これには、AI インデックスを構築するweb クローラーや、利用者がAI アシスタントにプロンプトを送信したときに発生するライブフェッチが含まれます。 これらのリクエストはJavaScriptを実行しないため、既存のweb データには記録されません。 ブランドの可視性データセットは、CDN レイヤーからこのトラフィックをキャプチャします。 この節の残りの部分では、そのデータセットについて説明します。


### データセットのオンボーディング

ブランドの可視性管理コネクタは、サマリーデータセットとしてデータをExperience Platformに配信します。 Customer Journey Analyticsで測定するには、次の2つの設定手順を実行します。

1. ブランドの可視性データセットを含む接続を作成します。
2. その接続にデータビューを作成します。 データビューでは、以下のディメンションと指標をAnalysis Workspaceで使用できます。

データセット：

* XDM要約指標クラスに基づく[概要データセット &#x200B;](/help/data-views/summary-data.md)を使用します。
* URLとホスト、時間、ボットの種類、CDN プロバイダー、ステータスなどのリクエスト特性ごとにデータをバケット化します。

>[!NOTE]
>
>ブランドの可視性データセットには、集約データが含まれます。 ユーザーID、プロンプト、応答などのPIIが含まれていません。
>

サマリーデータセットなので、ルックアップデータセットとして使用し、完全URL キーのイベントデータセットに結合できます。

ブランドの可視性は、**CDN URL** ディメンションでこのキーを提供します。 これは、Customer Journey Analyticsがweb データを保存する方法と同様に、ホストとリクエストされたパスを1つの正規化された完全なURLに結合します。 結合が成功するかどうかは、独自のデータ収集によって異なります。 イベントデータセットには、同等の完全なURL フィールド、またはブランドの可視性が提供するURLに一致するように解析および正規化できるフィールドが必要です。 双方が同じ完全なURLに解決すると、ブランドの可視性レコードはweb データ内の対応するページと一致します。

詳しくは、以下を参照してください。

* [インバウンド統合の設定と設定](/help/integrations/bv/configure.md)
* [データセット参照](/help/integrations/bv/reference.md)

## アウトバウンド統合

アウトバウンド統合について詳しくは、Adobe Brand Visibility ドキュメントの[Customer Journey Analytics統合](https://experienceleague.adobe.com/ja/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"}を参照してください。
