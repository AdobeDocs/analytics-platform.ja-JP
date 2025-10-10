---
description: Analysis Workspaceでのジャーニーキャンバスの使用方法を説明します。
title: ジャーニーキャンバスの概要
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1996'
ht-degree: 99%

---

# ジャーニーキャンバスの概要 {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="ジャーニーキャンバス"
>abstract="人物が一連のタッチポイントを通過またはフォールアウトする仕組みを示します。複数のエントリポイントとパスがあるジャーニーに使用するか、Journey Optimizer で作成されたジャーニーを分析するのに使用します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="ジャーニーキャンバス"
>abstract="人物が定義されたジャーニーを通過またはフォールアウトする仕組みを分析します。イベント、ディメンション項目およびセグメントの任意の組み合わせを表すノードと矢印の柔軟なグラフを作成して、ユーザージャーニーの分析を作成します。キャンバス上のノードをドラッグして、ジャーニーのイベントと条件を並べ替えます。これを行うと、それに応じてデータが更新されます。<br/><br/>Adobe Journey Optimizer へのアクセス権を持つお客様は、既存の Journey Optimizer ジャーニーを分析できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="ジャーニーキャンバス"
>abstract="人物が一連のタッチポイントを通過またはフォールアウトする仕組みを示します。複数のエントリポイントとパスがあるジャーニーに使用するか、Journey Optimizer で作成されたジャーニーを分析するのに使用します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="ジャーニーキャンバス"
>abstract="人物が定義されたジャーニーを通過またはフォールアウトする仕組みを分析します。イベント、ディメンション項目およびセグメントの任意の組み合わせを表すノードと矢印の柔軟なグラフを作成して、ユーザージャーニーの分析を作成します。キャンバス上のノードをドラッグして、ジャーニーのイベントと条件を並べ替えます。これを行うと、それに応じてデータが更新されます。<br/><br/>Adobe Journey Optimizer へのアクセス権を持つお客様は、既存の Journey Optimizer ジャーニーを分析できます。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_この記事では、_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** のジャーニーキャンバスビジュアライゼーションについて説明します。<br/>**Adobe Analytics** には同等のビジュアライゼーションはありません。_

>[!ENDSHADEBOX]

ジャーニーキャンバスのビジュアライゼーションを使用すると、ユーザーやお客様に提供するジャーニーを分析し、深いインサイトを得ることができます。これにより、ゼロからジャーニーを定義したり、Journey Optimizer からジャーニーを表示したりして、人物がジャーニーを離脱した（フォールアウト）か、次に進んだ（フォールスルー）かを確認できます。

イベント、ディメンション項目、セグメント、日付範囲を任意に組み合わせてジャーニーノードを作成して、[ユーザージャーニーの分析を作成](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)できます。ノードを接続してジャーニーのフローを作成し、複数のパスと決定ポイントを含めます。 キャンバス上のノードをドラッグして、ジャーニーのイベントと条件を並べ替えます。変更を行うと、データがリアルタイムで更新されます。

[ノードは「最終的なパス」として接続されます](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)。つまり、2 つのノード間で発生するイベントに関係なく、訪問者が最終的に 1 つのノードから別のノードに移動する限り、訪問者はカウントされます。ユーザーがパスに沿って移動するために割り当てられた時間は、コンテナの設定によって決まります。

![ジャーニーキャンバス](assets/journey-canvas.png)

## 主な特長

ジャーニーキャンバスビジュアライゼーションの主な機能は次のとおりです。

* 最も複雑なユーザージャーニーに対応するフォールアウトとフォールスルーの詳細な分析。

* ユーザージャーニーの様々なエントリ ポイント、ノード、パスをマッピングおよび視覚化するためのキャンバス。

* キャンバスにコンポーネントを追加したり、既存のノードを再配置したりするためのドラッグ＆ドロップ操作。

* ジャーニーキャンバス内でユーザージャーニーの分析を作成するか、Journey Optimizer ジャーニーに基づいて自動的に作成するオプション。

## 潜在的なインサイト

ジャーニーキャンバスは、最も複雑なジャーニーに対して実用的なインサイトを提供します。

### コンバージョン率が最も高いパス {#conversion-rate-caption}

ジャーニーキャンバスで最も顕著なインサイトは、キャンバス自体の上部にキャプションとして表示されます。

このキャプションは、ジャーニー内のすべてのパスの中で、コンバージョン率が最も高かったパスを要約したものです。

ジャーニーに複数の開始ノードが含まれる場合、キャプションは次のようになります。

![ジャーニーキャンバスインサイトキャプション](assets/journey-canvas-caption.png)

ジャーニーに単一の開始ノードが含まれる場合、キャプションは次のようになります。

![ジャーニーキャンバスインサイトキャプションの単一の開始ノード](assets/journey-canvas-caption-singlestart.png)

このキャプションを解釈する際は、次の点を考慮します。

* _パス_&#x200B;は、開始ノードと終了ノードが矢印で接続され、その間に任意の数のノードが接続されたものとして定義されます。

* コンバージョン率の計算は、ジャーニーのタイプ（ジャーニーに含まれる開始ノードおよび終了ノードの数と、これらの間のパスが交差するかどうか）によって異なります。

  次の表に、ジャーニータイプに基づくコンバージョン率の計算方法を示します。

  | ジャーニータイプ | コンバージョン率の計算 | 例 |
  |---------|----------|---------|
  | **単一の開始ノードと単一の終了ノード** | コンバージョン率は、終了ノードの数を開始ノードの数で割ることによって計算されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-single-path.png) |
  | **単一の開始ノードと複数の終了ノード** | コンバージョン率は、最大の数値を持つ終了ノードを見つけ、その数値を開始ノードの数値で割ることによって計算されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-singlestart-multiend.png) |
  | **単一の開始ノードと単一の終了ノードが含まれる複数のスタンドアロンパス** | コンバージョン率は、終了ノードの数を開始ノードの数で割ることによって計算されます。コンバージョン率が最も高いパスがキャプションに記載されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-multi-start-separate.png) |
  | **ジャーニーの任意の時点で共通のノードに収束する複数の開始ノード** | コンバージョン率は、最大の数値を持つ終了ノードを見つけ、その数値を最も低い数値を持つ開始ノードの数値で割ることによって計算されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-multi-start-converge.png) |

### フォールスルー、フォールアウトなど

ジャーニーキャンバスが提供できる他のインサイトの例を以下に示します。これらのインサイトが、データビュー内のすべての人物、ジャーニーを開始したすべての人物、ジャーニーの前のノードのすべての人物のいずれに基づくかを選択できます。

#### フォールスルー

* ジャーニを完了した（終了ノードに到着した）人物の数と割合

* ジャーニーの特定のノードに到達した人物の数と割合

* ジャーニーの特定のノードの後または前に発生した最も一般的な手順

#### フォールアウト

* 人物が最も共通してジャーニーからフォールアウトしたジャーニーのノード（すぐ次のノードのいずれにも到達しなかった）

#### 各ノードの追加データ

* ジャーニーの任意のノードに分類ディメンションを追加して、その特定のノードの追加データを表示します

## ジャーニーキャンバス、フォールアウト、フローのいずれかのビジュアライゼーションの選択

ジャーニーキャンバスビジュアライゼーションは、[フォールアウトビジュアライゼーション](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)や[フロービジュアライゼーション](/help/analysis-workspace/visualizations/c-flow/flow.md)と似ていますが、重要な違いがあります。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### ジャーニーキャンバスを使用するタイミング

ジャーニーキャンバスは、次の場合に不可欠です。

* 複数のエントリポイントとパスを持つジャーニーが関与するフォールアウト分析。

* 事前定義済みのページのシーケンスを使用した、複数のエントリポイントとパスを持つ非線形ジャーニー。

* 事前定義済みのジャーニーに基づく探索的、Ad Hoc Analysis。

* セッション、ユーザー、発生件数以外のプライマリ指標を必要とする分析。

* Adobe Journey Optimizer で発生したジャーニーの詳細な分析。

ジャーニーキャンバスビジュアライゼーション、フォールアウトビジュアライゼーションおよびフロービジュアライゼーションの違いを理解するには、[上記の表](#understand-the-differences)を参照してください。

## Journey Optimizer ジャーニーの分析

>[!NOTE]
>
>組織が Journey Optimizer へのアクセス権を持っていない場合でも、[ジャーニーキャンバスで分析を作成](#build-analyses-in-customer-journey-analytics)できます。

ジャーニーキャンバスで Journey Optimizer のジャーニーを分析すると、人物がジャーニーとやり取りする方法に関する、詳細かつ実用的なインサイトが得られます。

ジャーニーキャンバスで Journey Optimizer ジャーニーを分析すると、Journey Optimizer と同じ順序、シーケンス、構造でジャーニーが表示されます。ジャーニーキャンバス内でジャーニーに大幅な変更を行うと、[その変更は Journey Optimizer から同期されなくなります](#synchronization-between-journey-optimizer-and-journey-canvas)。

### ジャーニーキャンバスを使用してJourney Optimizer ジャーニーを分析するメリット

ジャーニー キャンバスは、Journey Optimizer では不可能な、詳細で徹底的な分析を提供します。

ジャーニーキャンバスを使用して、Journey Optimizer で作成されたジャーニーを分析すると、次のような様々なメリットがあります。

* 任意の Customer Journey Analytics ディメンション、指標、セグメントまたは日付範囲を使用してイベントを作成します。

  Journey Optimizer では、テクニカルユーザーがイベントを作成してから、イベントをジャーニーに追加する必要があります。

* 作成したカスタムノードに基づいてオーディエンスを作成します（Customer Journey Analytics オーディエンスビルダーを起動します）。

  Journey Optimizer では、事前定義済みのアクティビティに対してのみオーディエンスを作成できます。

* フォールスルーとフォールアウトを分析

* 任意のディメンションを持つイベントを分類

* イベントを組み合わせ

* イベントを接続

* コンテナを名前変更および削除

* その他

### Journey Optimizer とジャーニーキャンバス間の同期

Journey Optimizer とジャーニーキャンバス間の同期を理解するには、次の動作を考慮します。

* **データ同期は 1 方向のみである**

  ジャーニーキャンバスで Journey Optimizer ジャーニーの分析を作成すると、データは Journey Optimizer から Journey キャンバスへの 1 方向にのみ同期されます。つまり、ジャーニーキャンバスでジャーニーに行った変更は、Journey Optimizer に反映されません。

* **ジャーニーキャンバスでジャーニーを変更すると、同期が停止する**

  Journey Optimizer でジャーニーに行った変更は、[ジャーニーがジャーニーキャンバスで大幅に変更されていない場合にのみ](#differences-after-modifying-a-journey-in-journey-canvas)、ジャーニーキャンバスに同期されます。ジャーニーキャンバスでジャーニーを変更すると、Journey Optimizer でジャーニーに行った変更はジャーニーキャンバスに反映されません。ジャーニーキャンバスに反映された変更を確認するには、[ジャーニーキャンバスでジャーニーを削除して再作成](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)します。

* **「任意のユーザーと共有」リンクを使用するには、Journey Optimizer で変更を行った後に、プロジェクトを Customer Journey Analytics に保存する必要がある**

  「任意のユーザーと共有」リンクを使用すると、Journey Optimizer で行った変更は、プロジェクトを Customer Journey Analytics に保存するまで、ジャーニーキャンバスに反映されません。

  「任意のユーザーと共有」リンクについて詳しくは、[プロジェクトの共有](/help/analysis-workspace/curate-share/share-projects.md)の[任意のユーザーとプロジェクトを共有（ログイン不要）](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)を参照してください。

### ジャーニーキャンバスでジャーニーを変更した後の違い {#differences-after-modifying}

ジャーニーキャンバスで Journey Optimizer ジャーニーを変更すると、データ処理、使用可能な機能、同期動作に変更が生じる可能性があります。

ジャーニーキャンバスで Journey Optimizer ジャーニーに大幅な変更を行うと、データ処理、使用可能な機能、同期動作に変更が生じる可能性があります。大幅な変更には、次のいずれかが含まれます。

* ノードの追加または削除

* ノード間の矢印の追加または削除

* ノード上のコンポーネントの変更

ノードをドラッグしたり、分類を追加したりするなど、ジャーニーキャンバスで Journey Optimizer ジャーニーに他の変更を行った場合、次の節で説明する違いは適用されません。

>[!NOTE]
>
>ジャーニーを元の状態に戻すには、ジャーニー キャンバスで最初の変更を行った後に Ctrl + Z キーを押します。または、[ジャーニーキャンバスでジャーニーを削除して再作成することもできます](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### データ処理の違い

ジャーニーキャンバスで Journey Optimizer ジャーニーを変更すると、ジャーニーにデフォルト以外のアトリビューションモデルを持つ指標が含まれている場合は、データが変更される可能性があります。

これは、Journey Optimizer とは異なり、ジャーニーキャンバスでは 1 つのジャーニー内で複数のディメンションを適用できるからです。つまり、この機能では、[指標アトリビューション](/help/data-views/component-settings/attribution.md)がサポートされていません。

#### 機能の違い

ジャーニーキャンバスで Journey Optimizer ジャーニーを変更すると、変更に応じて、[!UICONTROL **矢印の設定**]&#x200B;ドロップダウンフィールドで使用できるオプションが変更されます。詳しくは、[設定の指定](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)を参照してください。

「[!UICONTROL **ノードタイプ**]」フィールドは、Journey Optimizer でのみ使用できます。ジャーニーキャンバスで Journey Optimizer ジャーニーを表示する場合、ジャーニーキャンバスでジャーニーに変更を行ったかどうかに関係なく、この機能は使用できません。

#### 同期の違い

Journey Optimizer でジャーニーに行った変更は、ジャーニーがジャーニーキャンバスで変更されていない場合にのみ、ジャーニーキャンバスに同期されます。

ジャーニーキャンバスで Journey Optimizer ジャーニーを変更すると、Journey Optimizer でジャーニーに行った変更はジャーニーキャンバスに反映されません。ジャーニーキャンバスに反映された変更を確認するには、[ジャーニーキャンバスでジャーニーを削除して再作成](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)します。

### Journey Optimizer と Customer Journey Analytics の用語の違い

Journey Optimizer で 1 つの意味を持つ特定の用語は、Customer Journey Analytics では別の意味を持ちます。ジャーニーキャンバスを使用する際は、Customer Journey Analytics の用語が使用されます。

| 用語 | ジャーニーキャンバス | Journey Optimizer |
|---------|----------|---------|
| **イベント** | Customer Journey Analytics で使用できる標準指標の 1 つです。この指標では、売上高、サブスクリプション、生成されたリードなどがカウントされます。 | オンライン購入など、パーソナライズされたジャーニーをトリガーするアクティビティのカテゴリ。 |

### ジャーニーキャンバスでの Journey Optimizer ジャーニーの分析

ジャーニーキャンバスでの Journey Optimizer ジャーニーの分析について詳しくは、[ジャーニーキャンバスビジュアライゼーションの設定](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)を参照してください。

## ジャーニーキャンバスでの分析の作成

Analysis Workspace で使用可能な任意のディメンションまたは指標に基づく分析を、ジャーニーキャンバスで作成できます。または、Journey Optimizer で作成されたジャーニーを分析できます。詳しくは、[ジャーニーキャンバスビジュアライゼーションの設定](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)を参照してください。


>[!MORELIKETHIS]
>
> * [Adobe Customer Journey Analytics でのジャーニーキャンバスビジュアライゼーションのガイド](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857?profile.language=ja)

