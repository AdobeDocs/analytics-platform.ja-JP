---
description: ジャーニーキャンバスの概要
title: ジャーニーキャンバス
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: c42858908aa8e73c5f3b622b9911ff9e9724f2dc
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 2%

---

# ジャーニーキャンバスの概要

{{release-limited-testing}}

ジャーニーキャンバスのビジュアライゼーションを使用すると、ユーザーや顧客に提供するジャーニーを分析し、深いインサイトを得ることができます。 ジャーニーを一から定義したり、Journey Optimizerからジャーニーを表示して、ジャーニー内でのユーザーの離脱や継続の様子を確認できます。

イベント、ディメンション項目、フィルター、日付範囲を任意に組み合わせて ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) ジャーニーノードを作成することで、[ ユーザージャーニーの分析を作成」できます。 ノードを接続してジャーニーのフローを作成し、複数のパスと決定ポイントを含めます。 キャンバス上でノードをドラッグして、ジャーニーのイベントや条件を並べ替えます。 変更を加えると、データがリアルタイムで更新されます。

## 主な特長

ジャーニーキャンバスビジュアライゼーションの主な機能には、次のものがあります。

* 最も複雑なユーザージャーニーに対応するフォールアウトおよびフォールスルーの詳細な分析。

* ユーザージャーニーの様々なエントリポイント、ノード、パスをマッピングおよび視覚化するためのキャンバス。

* キャンバスにコンポーネントを追加したり、既存のノードを再配置したりするためのドラッグ&amp;ドロップ操作。

* ジャーニーキャンバス内にユーザージャーニーの分析を作成するオプション、またはJourney Optimizer ジャーニーに基づいてユーザージャーニーを自動作成するオプション。

## 潜在的なインサイト

ジャーニーキャンバスが提供するのに役立つインサイトのタイプの例を以下に示します。 これらのインサイトを、データビューのすべてのユーザー、ジャーニーを開始したすべてのユーザー、ジャーニーの以前のノードのすべてのユーザーのいずれに基づくかを選択できます。

**フォールスルー**

* ジャーニーを完了した（終了ノードに到達した）ユーザーの数と割合

* ジャーニーの特定の時点（ノード）に到達した人物の数と割合

* ジャーニーの特定の時点（ノード）の後または前に発生した最も一般的なステップ

**フォールアウト**

* ジャーニーのポイント（ノード）。ジャーニーからフォールアウトする頻度が最も高い（直近の次のノードに到達しなかった）

**その他**

* ジャーニー内の任意のノードの追加データ（ノードの分類ディメンションの追加による）


## ジャーニーキャンバスとフォールアウトビジュアライゼーションのどちらかを選択します

ジャーニーキャンバスのビジュアライゼーションは、[ フォールアウトビジュアライゼーション ](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) に似ていますが、どちらのビジュアライゼーションも、事前に定義された一連のページの間で、人物が離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。

ただし、重要な違いがあります。

### 違いについて

次の表に、ジャーニーキャンバスビジュアライゼーションとフォールアウトビジュアライゼーションでサポートされている分析のタイプを示します。

| 関数 | ジャーニーキャンバスビジュアライゼーション | フォールアウトビジュアライゼーション |
|---------|----------|---------|
| 線形ジャーニー | ○ | ○ |
| 複数のエントリポイントとパスを持つ非線形ジャーニー | ○ | × |
| Adobe Journey Optimizer ジャーニー | ○ | × |
| プライマリ指標 | 計算指標を含む任意の指標 | セッションまたはユーザー指標のみを使用できます |
| セカンダリ指標 | ○<p>計算指標を含む任意の指標</p> | × |
| フィルターの比較 | × | ○<p>フィルターの比較 [ 無制限の数 ](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### 使用するビジュアライゼーションを選択

ジャーニーキャンバスとフォールアウトのどちらを使用するかを選択する前に、[2 つの違いを理解する ](#understand-the-differences) ことを確認してください。

フォールアウト分析で関係するジャーニーが開始と終了が既知のジャーニーがいずれも 1 つだけの場合は、より簡単なユーザージャーニーのオプションとして [ フォールアウトビジュアライゼーション ](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) を使用することを検討してください。

ジャーニーキャンバスは、複数のエントリポイントとパスを持つジャーニーや、Journey Optimizerで作成されたジャーニーを分析する場合に不可欠です。

## Journey Optimizer ジャーニーの分析

>[!NOTE]
>
>組織がJourney Optimizerへのアクセス権を持っていない場合でも、[ジャーニーキャンバスで分析を作成 ](#build-analyses-in-customer-journey-analytics) できます。

ジャーニーキャンバスでJourney Optimizer ジャーニーを分析すると、ジャーニーとのやり取りに関する、アクションにつながる深いインサイトが得られます。

ジャーニーキャンバスでJourney Optimizer ジャーニーを分析すると、ジャーニーは、Journey Optimizerの場合と同じ順序、順序、構造で表示されます。 ジャーニーキャンバス内でジャーニーを変更できる場合、[ 変更内容はJourney Optimizerから同期されなくなります ](#synchronization-between-journey-optimizer-and-journey-canvas)。

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

さらに、Journey Optimizerのジャーニーに加えられた変更は、ジャーニーキャンバスでジャーニーが変更されていない場合にのみ、ジャーニーキャンバスに同期されます。 ジャーニーキャンバスでジャーニーを変更した後は、Journey Optimizerでジャーニーに加えた変更は、ジャーニーキャンバスには反映されません。 ジャーニーキャンバスに反映された変更を確認するには、ジャーニーキャンバスでジャーニーを削除して [ 再作成 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) します。

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

ジャーニーキャンバスでJourney Optimizer ジャーニーを変更した後、変更に応じて、次の機能の機能が変わる場合があります。

* 「[!UICONTROL **ノードタイプ**]」フィールドに表示される値が変わります。

* [!UICONTROL **矢印設定**] ドロップダウンフィールドで使用できるオプションが変わります。

これらのフィールドについて詳しくは、[ 設定の指定 ](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) を参照してください。

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
