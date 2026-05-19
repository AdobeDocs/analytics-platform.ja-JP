---
description: Analysis Workspaceでフォールアウトビジュアライゼーションを使用する方法を説明します。
title: フォールアウト概要
feature: Visualizations
exl-id: c4338821-64ac-4345-828a-15af18a95ea6
role: User
autotag-review: '2026-05-19T08:41:54.033Z'
TQID: 'https://experienceleague.adobe.com/sitlejANJcDN2u-baGg2iz2SaOyZJe8jbyXjgBbasss'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 74%

---

# フォールアウトの概要 {#fallout-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_fallout_button"
>title="フォールアウト"
>abstract="ユーザーがどのようにして目的のチェックポイントに到達したかを確認するためのビジュアライゼーションを作成します。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、この記事の_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** バージョンの&#x200B;_Customer Journey Analytics![&#128279;](/help/assets/icons/CustomerJourneyAnalytics.svg)_&#x200B;**&#x200B;**&#x200B;_<br/>_ フォールアウト [&#128279;](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow)を参照参照してください。_

>[!ENDSHADEBOX]

![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL フォールアウト]**&#x200B;ビジュアライゼーションは、事前に指定した一連のページ間で、ユーザーが離脱した（フォールアウト）箇所や、次に進んだ（フォールスルー）箇所を表示します。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [フォールアウトビジュアライゼーションレポートの作成](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


フォールアウトビジュアライゼーションでは、次の操作を行うことができます。

* 同じレポートの異なる 2 つのセグメントを並べて比較します。
* ファネルステップ（タッチポイント）をドラッグ＆ドロップ（および並べ替え）。
* 様々なディメンションと指標の値を組み合わせて一致。
* 複数ディメンションのフォールアウトレポートを作成。
* フォールアウト直後にお客様が移動する場所を識別。

フォールアウトは、各ステップまたはシーケンスのタッチポイント間のコンバージョン率とフォールアウト率を表示します。

例えば、購入プロセス中のユーザーのフォールアウトポイントを追跡できます。 最初の顧客接点と最後の顧客接点を選択し、中間接点を追加してweb サイトのナビゲーションパスを構築します。 多次元のフォールアウトも実行できます。

## フォールアウト、フロー、ジャーニーキャンバスのいずれかのビジュアライゼーションの選択

フォールアウトビジュアライゼーションは、[フロービジュアライゼーション](/help/analysis-workspace/visualizations/c-flow/flow.md)や[ジャーニーキャンバスビジュアライゼーション](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)と似ています。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### フォールアウトを使用するタイミング

フォールアウトと[ジャーニーキャンバス](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)の両方のビジュアライゼーションは、次の項目を分析するのに役立ちます。

* サイト上の特定のプロセス（購入や登録プロセスなど）を通してのコンバージョン率。
* 一般的な、より広範囲のトラフィックフロー：このフローは、ホームページを訪問した人物のうち、検索を実行した数を示します。 次に、最終的に特定の項目を閲覧した数を示します。
* サイトのイベント間の相関関係。 相関関係とは、プライバシーポリシーを閲覧したオーディエンスのうち、製品を購入した割合を指します。

フォールアウトビジュアライゼーションは、次の場合に最適です。

* 事前定義済みの一連のページおよび単一のエントリポイントとパスを持つジャーニーが関与するフォールアウト分析 （複数のエントリポイントとパスを持つジャーニーでは、ジャーニーキャンバスを使用します）。

* 同じレポート内で 2 つの異なるセグメントを並べて比較する必要があるジャーニー。

ジャーニーキャンバスビジュアライゼーション、フォールアウトビジュアライゼーションおよびフロービジュアライゼーションの違いを理解するには、[上記の表](#understand-the-differences)を参照してください。

>[!MORELIKETHIS]
>
>[フォールアウトビジュアライゼーションの設定](configuring-fallout.md)



