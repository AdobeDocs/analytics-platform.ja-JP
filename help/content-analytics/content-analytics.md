---
title: Content Analytics の概要
description: Content Analyticsの価値と用語について説明し、Content Analyticsの仕組みについて説明します。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
TQID: https://experienceleague.adobe.com/x5FpRmZ-Wv6pPxYBEAyDzRqUSUpmwHFwbi55FwVKT5A
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 905
ht-degree: 55%

---


# Content Analytics の概要

Content Analytics は、ビジネスが定義した主要業績評価指標に影響を与えるコンテンツをマーケターが理解するのに役立ちます。 Content Analyticsは、行動データに加えて、コンテンツがどのように消費され、コンテンツがどのように影響を与えるかについてのデータを収集します。 例えば、特定のトーン、特定のカラーパレット、特定のテーマに対するお客様の反応は良いですか？ この情報と、特別に設計されたレポートワークフローおよびテンプレートを組み合わせることで、Customer Journey Analytics でさらに優れた分析を実行し、カスタマージャーニーデータに関するより深いインサイトを得ることができます。

Content Analytics では、AI と機械学習ベースの&#x200B;**機能サービス**&#x200B;を使用して、コンテンツをコンポーネントと属性に分類します。 あらゆるコンテンツに対して構造化されたメタデータプロファイルを作成することで、そのコンテンツのどのコンテンツや属性がビジネス成果を促進しているのかを分析できます。

この構造化メタデータプロファイルの作成に加えて、Content Analytics では、単一の識別子を使用してアセットとエクスペリエンスを識別する **ID サービス**&#x200B;を提供します。 ID サービスは、まったく同じアセットが複数の場所に表示される場合に認識できます。 その場合、アセットの 2 つのインスタンスは同じアセットとして扱われ、コンテンツの使用状況と消費の全体像を把握できます。

## 値

Content Analytics では、次のような増加レベルで価値を提供します。

1. コンテンツ&#x200B;**使用状況**：Content Analytics を使用すると、インプレッションを受信しているアセットと、インプレッションを受信しているアセットの場所に関するインサイトを得ることができます。 こうしたインサイトは、webやモバイルのプロパティでアセットが過小使用されているか、過剰に使用されているかを確認するのに役立ちます。
1. コンテンツ&#x200B;**エンゲージメント**：Content Analytics では、特定の属性を持つアセットの平均クリックスルー率などのエンゲージメントインサイトを提供できます。 これらのインサイトは、特定のタイプのエクスペリエンスが引き続き効果的かどうかを判断するのに役立ちます。
1. コンテンツジャーニー：さらに、Adobe Experience Platformに保管されているあらゆるデータと組み合わせることで、エンゲージメントだけでなく、特定のコンテンツがコンバージョンにつながるかどうかなど、コンテンツジャーニーに関するさらなるインサイトを獲得できます。 たとえば、特定のコンテンツがエンゲージメントだけでなくコンバージョンにつながるかどうかを確認します。 次に、その知識があれば、コンテンツのタイプに関する ROI を判断できます。
1. コンテンツ&#x200B;**パーソナライゼーション**：最終的に、Content Analytics により、インサイトに基づいて行動し、これらのインサイトを使用してコンテンツに費やす費用を決定できます。 例えば、特定のタイプのコンテンツを特定のオーディエンスに送信する必要があるでしょうか？ 高度なパーソナライゼーションの機会を提供してくれるコンテンツは何ですか？

## 用語

Content Analytics では、次の主要な用語を使用します。

![アセットとエクスペリエンス](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **エクスペリエンス**：エクスペリエンスは、最初のユーザーがweb ページにアクセスするために使用したURLを使用して再現可能なweb ページ上のすべてのテキストです。 モバイルアプリ内のアクションに対するテキスト、アセット、クリックの組み合わせから実行できます。 各エクスペリエンスには、一意の ID が付与されます。
* **アセット**：アセットとは、画像などの個別の一意のコンテンツです。 各アセットには、一意の ID と知覚的 ID も割り当てられます。 知覚的 ID は、視覚的に同一のアセットと共有される識別子です。 知覚的IDは、異なるアセット URLを持つ可能性があり、したがって異なるアセット IDを持つアセットの重複を排除するのに役立ちますが、知覚的には同じです。
* **属性**：属性とは、エクスペリエンスまたはアセットに関連付けられた説明的なメタデータ要素です。 属性の例としては、フォトのスタイル、読みやすさ、説得戦略、オブジェクトカラー、背景色などがあります。

## 仕組み

Content Analyticsは、Experience Platform イベントデータセットのwebおよびモバイル画像ビューデータを使用して、[&#x200B; コンテンツイベントデータを収集](config/datacollection.md)します。 これらのコンテンツエクスペリエンスイベントでは、Experience Platform Edge Network（Web SDK、モバイルSDK、サーバーAPI）を使用してデータを収集する必要があります。 行動データは、Web SDK、モバイルSDK、Analytics Sourceコネクタを使用して収集できます。

![Content Analytics - 仕組み](assets/aca-overview-new.gif)

1. Content Analytics[&#128279;](config/configuration.md)用に設定された サイトまたはアプリにユーザーがアクセスすると、Experience Platform Webまたはモバイル SDKは、インプレッションとコンテンツとのインタラクションを記録します。
1. IDおよび特徴化サービスは、これらのやり取りを処理します。 このプロセスは、インタラクションを定義する、設定済み URL の公開バージョンを再訪問する取得サービスで構成されます。 取得したすべての URL について、ID サービスはエクスペリエンスとアセットを一意に識別します。 また、特徴量化サービスは、AI/マシンラーニングサービスを適用して、エクスペリエンスとアセットのメタデータと属性を発見します。
1. これらのサービスの結果（[コンポーネント、属性、ID](/help/content-analytics/report/components.md)）は、Experience Platform 内の関連する特定のコンテンツ分析データセットを更新するのに使用されます。
1. Customer Journey Analyticsの設定（[Connection](/help/connections/overview.md)、[Data view](/help/data-views/data-views.md)、[Workspace](/help/analysis-workspace/home.md)）では、Content Analytics データを行動データやその他のルックアップデータと組み合わせて使用できます。 この設定は、コンテンツに関する独自のマクロレベルのインサイトの基盤となります。 <br/>Content Analytics テンプレート [を使用して、Content Analytics レポートと分析をすばやく開始できます](/help/content-analytics/report/report.md#template)。


>[!NOTE]
>
>Content Analytics では AI／ML サービスを活用するので、不正確な結果や誤解を招く結果が生成される場合があります。 その結果、AI／ML で生成された出力を確認および検証するには、自身の判断で行ってください。
>
>メインインターフェイスの ![InfoOutline](/help/assets/icons/InfoOutline.svg) から使用可能な「**[!UICONTROL フィードバック]**」タブを使用して、AI／ML で生成された出力に関するフィードバックを提供できます。
>

>[!NOTE]
>
>Privacy and Security Shield アドオンのライセンスを取得している場合、DULE ラベルまたはCustomer Managed Keysは、Content Analyticsの対象となるエクスペリエンスやアセットをカバーしていないことに注意してください。 また、Content Analytics は HIPAA 対応のサービスではありません。
>

>[!IMPORTANT]
>
>Content Analyticsでは、英語での特徴化のみがサポートされています。
>


>[!MORELIKETHIS]
>
>[Content Analytics レポート](report/report.md)
>[Content Analytics の設定](config/configuration.md)
>[Customer Journey Analytics でのバウンス数とバウンス率の計算](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/calculating-bounces-bounce-rate-in-adobe-customer-journey-analytics-options-and-implications-12722?profile.language=ja)
>

