---
description: ジャーニーキャンバスの概要
title: ジャーニーキャンバス
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: acbe705647e508bbc85f596c3165b1acd8cb15bb
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 3%

---

# ジャーニーキャンバスの概要 {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="ジャーニーキャンバス"
>abstract="フォールアウト率と同様に、このビジュアライゼーションでは、ユーザーが一連のタッチポイントをどのように通過するか、または離脱するかを示します。ジャーニーキャンバスは、複数のエントリポイントとパスを持つジャーニー、または Journey Optimizer で作成されたジャーニーを分析する場合に使用します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="ジャーニーキャンバス"
>abstract="ユーザーが定義されたジャーニーをどのように進めたり、そこから外れたりするかを分析します。 イベント、ディメンション項目、フィルターの任意の組み合わせを表すノードと矢印の柔軟なグラフを作成することで、ユーザージャーニーの分析を構築します。キャンバス上でノードをドラッグして、ジャーニーのイベントや条件を並べ替えます。 すると、データはそれに応じて更新されます。 <br/><br/>Adobe Journey Optimizerへのアクセス権を持つお客様は、既存のJourney Optimizer ジャーニーを分析できます"

<!-- markdownlint-enable MD034 -->



ジャーニーキャンバスのビジュアライゼーションを使用すると、ユーザーや顧客に提供するジャーニーを分析し、深いインサイトを得ることができます。 ジャーニーを一から定義したり、Journey Optimizerからジャーニーを表示して、ジャーニー内でのユーザーの離脱や継続の様子を確認できます。

イベント、ディメンション項目、フィルター、日付範囲を任意に組み合わせて ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) ジャーニーノードを作成することで、[ ユーザージャーニーの分析を作成」できます。 ノードを接続してジャーニーのフローを作成し、複数のパスと決定ポイントを含めます。 キャンバス上でノードをドラッグして、ジャーニーのイベントや条件を並べ替えます。 変更を加えると、データがリアルタイムで更新されます。

[ ノードは「最終的なパス」として接続されます。つまり ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)2 つのノード間でイベントが発生しても、最終的にノード間で移動する限り、訪問者はカウントされます。 ユーザーがパスに沿って移動するために割り当てられた時間は、コンテナ設定によって決定されます。

![ジャーニー キャンバス ](assets/journey-canvas.png)

## 主な特長

ジャーニーキャンバスビジュアライゼーションの主な機能には、次のものがあります。

* 最も複雑なユーザージャーニーに対応するフォールアウトおよびフォールスルーの詳細な分析。

* ユーザージャーニーの様々なエントリポイント、ノード、パスをマッピングおよび視覚化するためのキャンバス。

* キャンバスにコンポーネントを追加したり、既存のノードを再配置したりするためのドラッグ&amp;ドロップ操作。

* ジャーニーキャンバス内にユーザージャーニーの分析を作成するオプション、またはJourney Optimizer ジャーニーに基づいて自動的に作成するオプション。

## 潜在的なインサイト

ジャーニーキャンバスは、最も複雑なジャーニーに対して、実用的なインサイトを提供します。

### コンバージョン率が最も高いパス {#conversion-rate-caption}

ジャーニーキャンバスで最も顕著なインサイトは、キャンバス自体の上部にキャプションとして表示されます。

このキャプションは、ジャーニーのすべてのパスのうち、コンバージョン率が最も高いパスを要約します。

ジャーニーに複数の開始ノードが含まれる場合、キャプションは次のようになります。

![ジャーニーキャンバスインサイトキャプション ](assets/journey-canvas-caption.png)

ジャーニーに 1 つの開始ノードが含まれる場合、キャプションは次のようになります。

![ジャーニーキャンバスインサイトキャプションの単一スタートノード ](assets/journey-canvas-caption-singlestart.png)

このキャプションを解釈する際は、次の点に注意してください。

* _パス_ は、終了ノードに矢印で接続される開始ノードとして定義され、それらの間に任意の数のノードが接続されます。

* コンバージョン率の計算は、ジャーニーのタイプ（ジャーニーに含まれる開始ノードと終了ノードの数と、パスが交差しているかどうか）によって異なります。

  次の表に、ジャーニータイプに基づくコンバージョン率の計算方法を示します。

  | ジャーニーの種類 | コンバージョン率の計算 | 例 |
  |---------|----------|---------|
  | **単一のスタートノードと単一のエンドノード** | コンバージョン率は、終了ノードの数を開始ノードの数で割ることによって計算されます。 | ![ 共通のノードに収束する、複数の開始を持つジャーニー](assets/journey-canvas-single-path.png) |
  | **1 つの開始ノードと複数の終了ノード** | コンバージョン率は、最も大きい数の終了ノードを見つけ、その数を開始ノードの数で割ることで計算されます。 | ![ 共通のノードに収束する、複数の開始を持つジャーニー](assets/journey-canvas-singlestart-multiend.png) |
  | **複数のスタンドアロンパス。各パスには、1 つの開始ノードと 1 つの終了ノードが含まれます** | コンバージョン率は、終了ノードの数を開始ノードの数で割ることによって計算されます。 最もコンバージョン率の高いパスがキャプションに表示されます。 | ![ 共通のノードに収束する、複数の開始を持つジャーニー](assets/journey-canvas-multi-start-separate.png) |
  | **ジャーニーの任意の時点で収束して共通のノードになる複数の開始ノード** | コンバージョン率は、最も大きい数の終了ノードを見つけ、その数を、最も小さい数の開始ノードの数で割ることで計算されます。 | ![ 共通のノードに収束する、複数の開始を持つジャーニー](assets/journey-canvas-multi-start-converge.png) |

### フォールスルー、フォールアウトなど

ジャーニーキャンバスが提供できる他のインサイトの例を以下に示します。 これらのインサイトを、データビューのすべてのユーザー、ジャーニーを開始したすべてのユーザー、ジャーニーの以前のノードのすべてのユーザーのいずれに基づくかを選択できます。

#### フォールスルー

* ジャーニーを完了した（終了ノードに到達した）ユーザーの数と割合

* ジャーニーの特定のノードに到達した人物の数と割合

* ジャーニーの特定のノードの後または前に発生した最も一般的なステップ

#### フォールアウト

* ジャーニーからフォールアウトすることが最も多いジャーニーのノード（直近の次のノードに到達しなかった）

#### 各ノードの追加データ

* ジャーニーのノードに分類ディメンションを追加して、その特定のノードの追加データを表示します

## ジャーニーキャンバス、フォールアウト、フロービジュアライゼーションから選択します

ジャーニーキャンバスビジュアライゼーションは、[ フォールアウトビジュアライゼーション ](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) および [ フロービジュアライゼーション ](/help/analysis-workspace/visualizations/c-flow/flow.md) と似ていますが、重要な違いがあります。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### ジャーニーキャンバスを使用するタイミング

ジャーニーキャンバスは、次の場合に不可欠です。

* 複数のエントリポイントとパスを持つジャーニーが関与するフォールアウト分析。

* 事前に定義されたページのシーケンスを使用した、複数のエントリポイントとパスを持つ非線形ジャーニー。

* 事前定義済みのジャーニーに基づく探索的なアドホック分析。

* セッション、ユーザーまたは発生件以外のプライマリ指標を必要とする分析。

* Adobe Journey Optimizerで作成されたジャーニーの詳細な分析。

[ 上の表 ](#understand-the-differences) を使用して、ジャーニーキャンバス、フォールアウトおよびフロービジュアライゼーションの違いを理解します。

## Journey Optimizer ジャーニーの分析

>[!NOTE]
>
>組織がJourney Optimizerへのアクセス権を持っていない場合でも、[ジャーニーキャンバスで分析を作成 ](#build-analyses-in-customer-journey-analytics) できます。

ジャーニーキャンバスでJourney Optimizer ジャーニーを分析すると、ジャーニーとのやり取りに関する、アクションにつながる深いインサイトが得られます。

ジャーニーキャンバスでJourney Optimizer ジャーニーを分析すると、ジャーニーは、Journey Optimizerの場合と同じ順序、順序、構造で表示されます。 ジャーニーキャンバス内のジャーニーに大きな変更を加えると、[ 変更はJourney Optimizerから同期されなくなります ](#synchronization-between-journey-optimizer-and-journey-canvas)。

### ジャーニーキャンバスを使用してJourney Optimizer ジャーニーを分析するメリット

ジャーニーキャンバスは、Journey Optimizerでは不可能な深く徹底的な分析を提供します。

ジャーニーキャンバスを使用して、Journey Optimizerで作成されたジャーニーを分析すると、次のような様々な利点があります。

* 任意のイベントディメンション、指標、フィルターまたは日付範囲を使用して、Customer Journey Analyticsを作成します。

  Journey Optimizerでは、テクニカルユーザーは、ジャーニーに追加する前にイベントを作成する必要があります。

* 作成したカスタムノードに基づいてオーディエンスを作成します（Customer Journey Analyticsオーディエンスビルダーを起動）。

  Journey Optimizerでは、事前に定義されたアクティビティに対してのみオーディエンスを作成できます。

* フォールスルーとフォールアウトの分析

* 任意のディメンションを持つイベントの分類

* イベントの組み合わせ

* イベントを接続

* イベントの名前変更と削除

* その他

### Journey Optimizerとジャーニーキャンバスの同期

ジャーニーキャンバスでJourney Optimizer ジャーニーの分析を作成すると、データはJourney Optimizerからジャーニーキャンバスに向かって 1 方向にのみ同期されます。 つまり、ジャーニーキャンバスでジャーニーに加えた変更は、Journey Optimizerには反映されません。

さらに、Journey Optimizerでジャーニーに加えた変更は、[ジャーニーキャンバスでジャーニーが大幅に変更されていない場合のみ ](#differences-after-modifying-a-journey-in-journey-canvas)ジャーニーキャンバスと同期されます。 ジャーニーキャンバスでジャーニーを変更した後は、Journey Optimizerでジャーニーに加えた変更は、ジャーニーキャンバスには反映されません。 ジャーニーキャンバスに反映された変更を確認するには、ジャーニーキャンバスでジャーニーを削除して [ 再作成 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) します。

### ジャーニーキャンバスでジャーニーを変更した後の違い {#differences-after-modifying}

ジャーニーキャンバスでJourney Optimizer ジャーニーを変更すると、データ処理、使用可能な機能、同期動作が変更される場合があります。

ジャーニーキャンバスでJourney Optimizer ジャーニーに大きな変更を加えると、データ処理、使用可能な機能、同期動作に変更が生じる可能性があります。 重要な変更には、次のいずれかが含まれます。

* ノードの追加または削除

* ノード間の矢印の追加または削除

* ノード上のコンポーネントの変更

ノードをドラッグしたり分類を追加したりするなど、ジャーニーキャンバスでJourney Optimizer ジャーニーに他の変更を加える場合、次の節で説明する違いは適用されません。

>[!NOTE]
>
>ジャーニーを元の状態に戻すには、ジャーニーキャンバスで最初の変更を行った後に Ctrl+Z キーを押します。 または、ジャーニーキャンバスでジャーニーを削除および [ 再作成 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) できます。

#### データ処理の違い

ジャーニーキャンバスでJourney Optimizer ジャーニーを変更した後、デフォルト以外のアトリビューションモデルを持つ指標がジャーニーに含まれている場合は、データが変更される場合があります。

これは、Journey Optimizerとは異なり、ジャーニーキャンバスを使用すると、1 つのジャーニー内に複数のディメンションを適用できるからです。 この機能は、[ 指標アトリビューション ](/help/data-views/component-settings/attribution.md) がサポートされていないことを意味します。

#### 機能の違い

ジャーニーキャンバスでJourney Optimizer ジャーニーを変更すると、変更に応じて、[!UICONTROL **矢印の設定**] ドロップダウンフィールドで使用できるオプションが変わります。 詳しくは、[ 設定の指定 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) を参照してください。

「[!UICONTROL **ノードタイプ**]」フィールドは、Journey Optimizerでのみ使用できます。 ジャーニーキャンバスでJourney Optimizer ジャーニーを表示している場合は、ジャーニーキャンバスでジャーニーを変更するかどうかに関係なく、この機能は使用できません。

#### 同期の違い

Journey Optimizerのジャーニーに加えられた変更は、ジャーニーキャンバスでジャーニーが変更されていない場合にのみ、ジャーニーキャンバスに同期されます。

ジャーニーキャンバスでJourney Optimizer ジャーニーを変更した後は、Journey Optimizerでジャーニーに加えた変更は、ジャーニーキャンバスには反映されません。 ジャーニーキャンバスに反映された変更を確認するには、ジャーニーキャンバスでジャーニーを削除して [ 再作成 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) します。

### Journey OptimizerとCustomer Journey Analyticsの用語の違い

Journey Optimizerにある 1 つのことを意味する特定の用語は、Customer Journey Analyticsでは他のことを意味します。 ジャーニーキャンバスを使用する場合、Customer Journey Analytics用語が使用されます。

| 用語 | ジャーニーキャンバス | Journey Optimizer |
|---------|----------|---------|
| **イベント** | Customer Journey Analyticsで使用できる複数の標準指標の 1 つ。 この指標は、売上高、サブスクリプション、生成されたリードなどをカウントします。 | オンライン購入など、パーソナライズされたジャーニーをトリガーにするアクティビティのカテゴリ。 |

### ジャーニーキャンバスでのJourney Optimizer ジャーニーの分析

ジャーニーキャンバスでのJourney Optimizer ジャーニーの分析について詳しくは、[ジャーニーキャンバスビジュアライゼーションの設定 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) を参照してください。

## ジャーニーキャンバスでの分析の作成

Analysis Workspaceで使用可能な任意のディメンションまたは指標に基づく分析を、ジャーニーキャンバスで作成できます。 または、Journey Optimizerで作成されたジャーニーを分析できます。 詳しくは、[ジャーニーキャンバスビジュアライゼーションの設定 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) を参照してください。
