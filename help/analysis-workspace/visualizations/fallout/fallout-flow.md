---
description: Analysis Workspaceでのフォールアウトビジュアライゼーションの使用方法を説明します。
title: フォールアウトの概要
feature: Visualizations
exl-id: c4338821-64ac-4345-828a-15af18a95ea6
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 96%

---

# フォールアウトの概要 {#fallout-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_fallout_button"
>title="フォールアウト"
>abstract="ユーザーがどのようにして目的のチェックポイントに到達したかを確認するためのビジュアライゼーションを作成します。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** のフォールアウトビジュアライゼーションについて説明します。_<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** バージョンについて詳しくは、[フォールアウト](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow)を参照してください。_

>[!ENDSHADEBOX]

![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL フォールアウト]**&#x200B;ビジュアライゼーションは、事前に指定した一連のページ間で、ユーザーが離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [フォールアウトビジュアライゼーションレポートの作成](https://video.tv.adobe.com/v/345883/?quality=12&learn=on){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


フォールアウトビジュアライゼーションでは、次の操作を行うことができます。

* 同じレポートの異なる 2 つのセグメントを並べて比較する。
* ファネルステップ（タッチポイント）をドラッグ＆ドロップ（および並べ替え）。
* 様々なディメンションと指標の値を組み合わせて一致。
* 複数ディメンションのフォールアウトレポートを作成。
* フォールアウト直後にお客様が移動する場所を識別。

フォールアウトは、各ステップまたはシーケンスのタッチポイント間のコンバージョン率とフォールアウト率を表示します。

例えば、購入プロセス中のユーザーのフォールアウトポイントを追跡できます。開始タッチポイントと終了タッチポイントを選択し、中間タッチポイントを追加して、Web サイトのナビゲーションパスを作成します。ただし、複数ディメンションのフォールアウトも可能です。

## フォールアウト、フロー、ジャーニーキャンバスのいずれかのビジュアライゼーションの選択

フォールアウトビジュアライゼーションは、[フロービジュアライゼーション](/help/analysis-workspace/visualizations/c-flow/flow.md)や[ジャーニーキャンバスビジュアライゼーション](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)と似ています。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### フォールアウトを使用するタイミング

フォールアウトと[ジャーニーキャンバス](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)の両方のビジュアライゼーションは、次の項目を分析するのに役立ちます。

* サイト上の特定のプロセス（購入や登録プロセスなど）を通してのコンバージョン率。
* 一般的な、より広範囲のトラフィックフロー：このフローは、ホームページを訪問した人物のうち、検索を実行した数を示します。次に、最終的に特定の項目を閲覧した数を示します。
* サイト上のイベント間の関連性。例えばプライバシーポリシーを閲覧した訪問者のうち製品の購入に到達した人の割合を示します。

フォールアウトビジュアライゼーションは、次の場合に最適です。

* 事前定義済みの一連のページおよび単一のエントリポイントとパスを持つジャーニーが関与するフォールアウト分析（複数のエントリポイントとパスを持つジャーニーでは、ジャーニーキャンバスを使用します）。

* 同じレポート内で 2 つの異なるセグメントを並べて比較する必要があるジャーニー。

ジャーニーキャンバスビジュアライゼーション、フォールアウトビジュアライゼーションおよびフロービジュアライゼーションの違いを理解するには、[上記の表](#understand-the-differences)を参照してください。

>[!MORELIKETHIS]
>
>[フォールアウトビジュアライゼーションの設定](configuring-fallout.md)



