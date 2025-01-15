---
description: フォールアウトレポートとビジュアライゼーションについて説明します。
title: フォールアウトレポートとビジュアライゼーションについて
feature: Visualizations
exl-id: c4338821-64ac-4345-828a-15af18a95ea6
role: User
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 30%

---

# フォールアウトの概要 {#fallout-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_fallout_button"
>title="フォールアウト"
>abstract="ユーザーがどのようにして目的のチェックポイントに到達したかを確認するためのビジュアライゼーションを作成します。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*この記事では、**Customer Journey Analyticsのフォールアウトビジュアライゼーションについて説明します**。 この記事の [2}Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow) バージョンについては&#x200B;**フォールアウト* を参照してください。**

>[!ENDSHADEBOX]

![ コンバージョンファネル ](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL フォールアウト]** ビジュアライゼーションは、事前に定義された一連のページ間で、人物が離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。

+++ [!UICONTROL  フォールアウトビジュアライゼーション ] のビデオデモをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/345883/?quality=12)

{{videoaa}}

+++

フォールアウトビジュアライゼーションを使用すると、次のことができます。

* 同じレポートで異なる 2 つのフィルターを並べて比較
* ファネル手順（タッチポイント）をドラッグ&amp;ドロップ（および並べ替え）します。
* 様々なディメンションや指標の値を組み合わせて一致させます。
* 複数ディメンションのフォールアウトレポートを作成します。
* 顧客がフォールアウトした直後にどこに移動するかを特定します。

フォールアウトは、各ステップまたはシーケンスのタッチポイント間のコンバージョン率とフォールアウト率を表示します。

例えば、購入プロセス中にユーザーのフォールアウトポイントを追跡できます。 開始タッチポイントと終了タッチポイントを選択し、中間タッチポイントを追加して、Web サイトのナビゲーションパスを作成します。ただし、複数ディメンションのフォールアウトも可能です。

## フォールアウト、フロー、ジャーニーのいずれかのキャンバスビジュアライゼーションを選択します

フォールアウトビジュアライゼーションは、[ フロービジュアライゼーション ](/help/analysis-workspace/visualizations/c-flow/flow.md) および [ジャーニーキャンバスビジュアライゼーション ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) と類似点があります。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### フォールアウトを使用するタイミング

フォールアウトと [ジャーニーキャンバスの両方 ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) ビジュアライゼーションは、次の項目を分析するのに役立ちます。

* サイト上の特定のプロセス（購入や登録プロセスなど）を通してのコンバージョン率。
* 一般的な、より範囲の広いトラフィックフロー：ホームページを訪問したユーザーのうち、このフローは、検索を実行した数を示します。 そして、最終的に特定の項目を見た人の数。
* サイト上のイベント間の関連性。例えばプライバシーポリシーを閲覧した訪問者のうち製品の購入に到達した人の割合を示します。

フォールアウトビジュアライゼーションは、次の場合に最適です。

* 事前定義された一連のページと、単一のエントリポイントおよびパスを持つジャーニーが関与するフォールアウト分析。 （複数のエントリポイントとパスを持つジャーニーでは、ジャーニーキャンバスを使用します）。

* 同じレポートで 2 つの異なるフィルターを並べて比較する必要があるジャーニー。

[ 上の表 ](#understand-the-differences) を使用して、ジャーニーキャンバス、フォールアウトおよびフロービジュアライゼーションの違いを理解します。

>[!MORELIKETHIS]
>
>[フォールアウトビジュアライゼーションの設定](configuring-fallout.md)



