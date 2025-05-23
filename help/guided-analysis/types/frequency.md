---
title: 頻度分析
description: 使用頻度別にエンゲージメントを測定します。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '657'
ht-degree: 100%

---

# [!UICONTROL 頻度]分析 {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="頻度"
>abstract="特定のイベントに対するリピートユーザーアクティビティの配分を表示します。"

<!-- markdownlint-enable MD034 -->

![頻度](/help/assets/icons/Histogram.svg) **[!UICONTROL 頻度]**&#x200B;分析では、製品でイベントが発生する頻度に応じてイベントデータをグループ化します。この分析の垂直軸には、イベントの頻度を表すバケットが含まれています。横軸は、各バケットのユーザーまたはセッションの数を測定します。

>[!VIDEO](https://video.tv.adobe.com/v/3435803/?quality=12&learn=on&captions=jpn)

## ユースケース

この分析のユースケースには、次のようなものがあります。

* **エンゲージメント**：製品のイベントに対してユーザーがどの程度関与しているかを追跡します。棒グラフの任意の部分をクリックすると、セグメントとして保存できます。エンゲージメントの低いバケットのセグメントは、ユーザーの希望の頻度でイベントに関与していない理由を判断するのに役立ちます。エンゲージメントの高いバケットのセグメントは、ユーザーがイベントに頻繁に関与する理由を理解するのに役立ちます。そこから、他のユーザーに同様の行動をとるよう促すことができます。
* **顧客の忠誠度**：イベントを「注文」に、指標を「ユーザー」に設定します。この分析では、指定した日付範囲内でユーザーがサイトで購入した回数ごとにユーザーをグループ化できます。
* **サポートの最適化**：ユーザー別のサポートへのコール数やオープンケース数を表示して、最も多くの問題に発生しているユーザーを把握します。次に、エクスペリエンスに焦点を当てたセグメントを作成し、問題の特定と解決に役立てることができます。
* **購読サービス**：エンゲージメントが低いユーザーは、チャーンする可能性が高くなります。エンゲージメントが高いユーザーの行動を理解することで、エンゲージメントが低いユーザーにも類似の行動を促し、購読をキャンセルする可能性を低くすることができます。

## インターフェイス

ガイド付き分析インターフェイスの概要については、[インターフェイス](../overview.md#interface)を参照してください。次の設定は、この分析に固有です。

### クエリパネル

クエリパネルでは、次のコンポーネントを設定できます。

* **[!UICONTROL 表示]**：この分析と[トレンド](trends.md)を切り替えます。
* **[!UICONTROL イベント]**：測定するイベントです。選択した各イベントは、個別のグラフとして表されます。トレンドイベントを表す行がテーブルに追加されます。最大 5 つのイベントを含めることができます。
* **[!UICONTROL 次としてカウント]**：選択したイベントに適用するカウント方法。オプションには、[!UICONTROL ユーザー]、[!UICONTROL セッション]、[!UICONTROL ユーザーの割合]、[!UICONTROL セッションの割合]が含まれます。この分析における割合ベースの指標の分母は、製品のすべてのアクティブユーザーではなく、選択したイベントを実行したユーザーまたはセッションです。
* **[!UICONTROL セグメント]**：測定するセグメント。選択したセグメントごとに、グラフの棒の数とテーブルの行数が 2 倍になります。最大 5 つのセグメントを含めることができます。

### グラフ設定

[!UICONTROL 頻度]分析には次のグラフ設定が用意されており、グラフの上にあるメニューで調整できます。

* **[!UICONTROL グラフのタイプ]**：使用するビジュアライゼーションのタイプ。オプションには、[!UICONTROL 横棒グラフ]および [!UICONTROL 積み重ね棒グラフ] が含まれます。

### バケット設定

イベントをグループ（バケット）に分類する方法を決定します。トレンドテーブルビューでは、ユーザーは合計および各間隔での使用頻度に基づいてバケット化されます。つまり、1 人のユーザーが異なる間隔で異なるバケットにカウントされる場合があります。

* **[!UICONTROL 自動バケット]**：データ分布に基づいて最適なバケットサイズを自動的に特定します。
* **[!UICONTROL カスタマイズされたバケット]**：データをバケットにグループ化する方法をカスタマイズします。
   * [!UICONTROL 開始]：最初のバケット。この値より小さい頻度は、レポートから除外されます。
   * [!UICONTROL 終了]：この値より大きい頻度は、最後のバケットにグループ化されます。
   * [!UICONTROL サイズ]：バケットの間隔。

### 時間比較

{{apply-time-comparison}}

### 日付範囲

分析に対する目的の日付範囲。この設定には、次の 2 つのコンポーネントがあります。

* **[!UICONTROL 間隔]**：トレンドデータの表示に使用する日付の精度。グラフとテーブルにはデフォルトで集計データが表示されますが、テーブルをトレンドビューに展開するオプションもあります。トレンドビューでは、ユーザーは合計および各間隔での使用頻度に基づいてバケット化されます。つまり、1 人のユーザーが異なる間隔で異なるバケットにカウントされる場合があります。
* **[!UICONTROL 日付]**：開始日と終了日。便宜上、周期的な日付範囲のプリセットと以前に保存したカスタム範囲を使用できます。または、カレンダーセレクターを使用して固定日付範囲を選択することもできます。


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
