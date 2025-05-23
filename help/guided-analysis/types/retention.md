---
title: リテンション分析
description: 製品を引き続き使用するユーザーの数を測定します。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '1259'
ht-degree: 100%

---

# リテンション分析 {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="リテンション"
>abstract="製品を引き続き使用するユーザーの数を測定します。"

<!-- markdownlint-enable MD034 -->

![リテンション](/help/assets/icons/Retention.svg) **[!UICONTROL リテンション]**&#x200B;分析では、ユーザーが時間の経過と共に製品を引き続き使用する方法を測定します。これは、製品の市場適合性を理解するのに役立ちます。分析では、次の 2 つの重要なイベントに基づいてユーザーをカウントします。

* 開始イベント：分析に含めるユーザーの選定に使用するイベント。
* 再来訪イベント：分析で再来訪ユーザーとしてカウントするためにユーザーが関与する必要がある 1 つ以上のイベント。

この分析では、グラフの x 軸はユーザーの最初の開始イベントからの時間を表し、y 軸は 1 つ以上の再来訪イベントに関与したユーザーの割合を表します。期間をまたいでリテンションとチャーンの両方を表示でき、表示される期間はクエリ設定を通じてカスタマイズできます。グラフの下にあるテーブルには、集計データと、同じ日に開始イベントを行った人物のグループである個々のコホートを表示するオプションが表示されます。

>[!VIDEO](https://video.tv.adobe.com/v/3435779/?quality=12&learn=on&captions=jpn)


## ユースケース

この分析のユースケースには、次のようなものがあります。

* **コホート分析**：新規登録や購入などのユーザーのアクションに基づいてユーザーをコホートにグループ化します。これらのグループの保持率を比較し、各グループのユーザーエクスペリエンスを向上させるためのアプローチ方法を決定できます。
* **製品の市場適合性**：製品の定期的な使用状況を測定し、リテンション曲線として視覚化します。リテンションが高いほど製品の市場適合性が高くなり、曲線が平坦になる場所は適合性に到達するまでにかかる時間を示します。この分析を全体的なレベルで表示するか、個々の製品機能別に分類を表示すると、より深いインサイトを得ることができます。
* **購読サービス分析**：製品に購読や別のタイプの繰り返し売上高モデルを使用している場合は、製品を最大限に活用しているユーザーの割合を確認できます。これらのユーザーが示す特定の性質や行動を識別できます。
* **ユーザーエンゲージメント**：特定のタイプのユーザーが製品と関与する方法を評価し、再来訪する頻度を並べて比較します。特定のセグメントのリテンションが他のセグメントよりも低い場合は、潜在的な標準以下のエクスペリエンスを改善するためのインサイトを得ることができます。

## インターフェイス

ガイド付き分析インターフェイスの概要については、[インターフェイス](../overview.md#interface)を参照してください。次の設定は、この分析に固有です。

### クエリパネル

クエリパネルでは、次のコンポーネントを設定できます。

* **[!UICONTROL 開始イベント]**：分析に含める選定に対してユーザーが関与する必要があるイベント条件。開始イベントに関与したユーザーは、テーブルの「ユーザー」列にカウントされます。このイベントは、表示されるリテンション率の分母として機能します。1 つのイベントがサポートされ、必要に応じてプロパティフィルターを適用できます。デフォルトでは、開始イベントと再来訪イベントはリンクされています。つまり、ユーザーをコホートに含めるには、選択したイベントを 1 回実行し、再来訪ユーザーとしてカウントするには、もう一度実行する必要があります。その他メニューで、再来訪アクションをインクルージョンアクションと異なるものにする場合は、開始イベントと再来訪イベントのリンクを解除できます。
* **[!UICONTROL 再来訪イベント]**：期間バケット内で再来訪ユーザーとしてカウントするためにユーザーが満たす必要があるイベント条件。最大 3 つの再来訪イベントを選択して、リテンション全体を比較できます。
* **[!UICONTROL 次としてカウント]**：保持されたユーザーに適用するカウント方法。オプションには、以下が含まれます。
   * **[!UICONTROL 指標]**：[!UICONTROL ユーザー]数または保持された[!UICONTROL ユーザーの割合]を表示します。保持されたユーザーの割合の分母は、コホートに含まれるユーザーで、すべての期間バケットで同じです。
   * **[!UICONTROL 再来訪]**：再来訪ユーザーをカウントする方法を制御できます。オプションには、以下が含まれます。
      * **[!UICONTROL 以降]**：多くの場合「無制限」のリテンションと呼ばれるこのオプションでは、指定期間以降に再来訪した場合のユーザーがカウントされます。例えば、7 日目または 7 日目以降の任意の時間を指定します。このオプションは、ユーザーが引き続き関与する方法を示すのに役立ち、その結果、よりスムーズなリテンション曲線が生成されます。
      * **[!UICONTROL 正確に]**：多くの場合「制限付き」のリテンションと呼ばれるこのオプションでは、正確に指定期間に再来訪した場合のユーザーがカウントされます。例えば、7 日目を正確に指定します。このオプションは、ユーザーが特定の期間内に再来訪する方法を示すのに役立ち、その結果、より起伏のあるリテンション曲線が生成されます。メモ：Analysis Workspace のコホート分析では、分析のベースとして「正確に」カウントを使用します。
   * **[!UICONTROL 期間ごと]**：各期間バケットに設定したい期間。オプションには、以下が含まれます。
      * **[!UICONTROL 日 / 週 / 月]**：使用可能なオプションは、選択した日付範囲によって異なります。これらのオプションは、日付範囲を選択するときに設定する「**[!UICONTROL 間隔]**」と同じであり、その設定を自動的に更新します。
      * **[!UICONTROL カスタムブラケット]**：このオプションは「期間ごと」設定の場合にのみ使用できます。より長い期間（例えば、7 日目だけでなく 7～10 日目）にわたってユーザーをカウントできます。
   * **[!UICONTROL 期間設定]**：グラフおよびテーブルに表示する期間バケットを制御できます。期間とは、開始イベントのあと復帰イベントが発生するまでの期間です。注意：期間バケットの対象となるユーザーは、カレンダー日ではなく経過時間に基づいています。例えば、ユーザーが 9月6日の午後 11:55 にイベントの対象となり、その後 9月7日の午前 12:05 に復帰イベントの対象となった場合、ユーザーは 1 日間の期間バケットには表示されません。ユーザーが 1 日間の期間バケットの対象になるには、完全に 24 時間が経過する必要があります。 使用可能な期間バケットは、設定した日付範囲によって異なります。
      * 「**[!UICONTROL 自動期間]**」では、日付範囲の長さと、日付範囲が当日にどれだけ近いかに応じて、期間バケットが自動的に定義されます。
      * 「**[!UICONTROL カスタム期間]**」を使用すると、グラフとテーブルに表示する 4 つの期間バケットをカスタマイズできます。
* **[!UICONTROL セグメント]**：測定するセグメント。各セグメントを選択するとは、コホートテーブルに行が 1 つ追加されます。最大 3 つのセグメントを含めることができます。

### グラフ設定

[!UICONTROL リテンション]分析には次のグラフ設定が用意されており、グラフの上にあるメニューで調整できます。

* **[!UICONTROL グラフのタイプ]**：使用するビジュアライゼーションのタイプ。オプションには、「[!UICONTROL 棒グラフ]」と「[!UICONTROL 折れ線グラフ]」があります。

### 日付範囲

分析に対する目的の日付範囲。この設定には、次の 2 つのコンポーネントがあります。

* **[!UICONTROL 間隔]**：リテンションデータの表示に使用する日付の精度。有効なオプションには、「毎日」、「毎週」、「毎月」があります。同じ日付範囲に異なる間隔を指定でき、その場合は期間バケットオプションに影響します。
* **[!UICONTROL 日付]**：開始日と終了日。便宜上、周期的な日付範囲のプリセットと以前に保存したカスタム範囲を使用できます。または、カレンダーセレクターを使用して固定日付範囲を選択することもできます。

当日に近い日付範囲を選択した場合、最初のエンゲージメントが当日に近すぎるユーザーは含まれません。この分析では、常にすべてのユーザーがすべての期間バケットに含まれる可能性があります。カレンダーピッカーの下に表示されるメッセージは、ユーザーが関与する日付範囲と、再来訪ユーザー専用に予約されている間隔に関する情報を提供します。

* **[!UICONTROL [日付範囲]]**&#x200B;内で開始イベントを行ったユーザーを分析：この日付範囲内でイベントとエンゲージしたユーザーは分析に含まれます。この日付範囲は、すべての期間バケットの対象となるだけの十分な時間をすべてのユーザーに保証します。この日付範囲は、当日に近い場合、選択した日付範囲とは異なる可能性があります。
* **[!UICONTROL [日付範囲]からのデータは分析を完了するために予約済み]**：この期間内に初めてエンゲージしたユーザーは、分析に含まれ&#x200B;**ません**。最近の日付範囲の場合、これらのユーザーには、すべての期間バケットの対象となる機会はありません。過去の日付範囲の場合、これらのユーザーは、選択した日付範囲外でアクティブでした。

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->