---
title: コホートテーブルの概要
description: Analysis Workspace でコホートテーブルをコホート分析に使用する方法について説明します
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 94%

---

# コホートテーブルの概要 {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="コホートテーブル"
>abstract="コホートビジュアライゼーションを作成して、イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントと時間の経過に伴うチャーンを分析します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="コホートテーブル"
>abstract="イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントとチャーンの推移を分析します。精度、コホート分析のタイプ、ローリング計算を使用するかどうかなどの追加設定を指定します。選択したディメンションに基づいて待ち時間テーブルまたはカスタムディメンションコホートを作成する詳細オプションを設定できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** のコホートテーブルについて説明します。_<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** バージョンについては、[コホートテーブル](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis)を参照してください。_

>[!ENDSHADEBOX]


*コホート*&#x200B;は、特定の期間にわたって共通の特性を持つ人物のグループです。![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL コホートテーブル]**&#x200B;ビジュアライゼーションは、例えば、あるコホートが、あるブランドとどのようにエンゲージしているかを知るのに役立ちます。トレンドの変更を簡単に見分けて、それに応じて対応できます（[!UICONTROL コホート分析]の説明は、[コホート分析 101](https://ja.wikipedia.org/wiki/Cohort_analysis) など、Web 上で参照できます）。

コホートレポートを作成したら、コンポーネント（特定のディメンション、指標およびセグメント）をキュレートして、任意のユーザーとコホートレポートを共有できます。[キュレートおよび共有](/help/analysis-workspace/curate-share/curate.md)を参照してください。

[!UICONTROL コホートテーブル]で実行できる操作の例：

* 目的のアクションを促進するために設計したキャンペーンを開始する。
* 顧客のライフサイクルのまさに適切なタイミングでマーケティング予算を振り替える。
* 価値を最大化するために、体験版やオファーを終了するタイミングを認識する。
* 価格やアップグレードパスなどの領域で、A/B テストの着想を得る。

[!UICONTROL コホートテーブル]は、[!UICONTROL Analysis Workspace] へのアクセス権を持つすべての Customer Journey Analytics ユーザーが使用できます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のコホート分析](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL &#x200B; コホート分析 &#x200B;] では、セグメント化できない指標（計算指標など）、整数以外の指標（売上高など）、発生件数はサポートしていません。 [!UICONTROL &#x200B; コホート分析 &#x200B;] で使用できるのはセグメントで使用できる指標のみで、一度に増やせるのは 1 つのみです。

Customer Journey Analytics のコホートテーブルでは、2 倍ベース（または任意の数値ベース）の指標をサポートします。例えば、Purchase.Value（2 倍）はインクルージョン／リターン指標として使用できます。また、Analytics ソースコネクタ経由で Adobe Experience Platform に渡されるすべての指標も 2 倍になります。

## コホートテーブルの機能

次の節では、作成しているコホートを微調整して制御できるコホート分析機能について説明します。

コホートの作成と[!UICONTROL コホート分析]レポートの実行について詳しくは、[コホートテーブルの設定](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)を参照してください。

### [!UICONTROL リテンション]テーブル

[!UICONTROL リテンション]コホートテーブルはユーザーを返します。各データセルには、その期間中にアクションを実行したコホートのユーザーの生の数と割合が表示されます。指標は最大 3 個、セグメントは最大 10 個含めることができます。

![コホート内のユーザーの単位と割合を示すリテンションコホートレポート。](assets/retention-report.png)

### [!UICONTROL チャーン]テーブル

[!UICONTROL チャーン]コホートテーブルは、リテンションテーブルの逆で、時間の経過と共にコホートからフォールアウトしたユーザーや、コホートへのリターン条件を満たさなかったユーザーが表示されます。指標は最大 3 個、セグメントは最大 10 個含めることができます。

![コホートのリターン条件を満たさなかった人物の数と割合を示すチャーンテーブル。](assets/churn-report.png)

### [!UICONTROL ローリング計算]

リテンションまたはチャーンは、「含む」列ではなく、前の列に基づいて計算できます。これをローリング計算と呼びます。

![前のデータ列に基づく計算を示すコホートリテンションレポート。](assets/retention-report-rolling.png)

### [!UICONTROL 待ち時間]テーブル

待ち時間テーブルは、インクルージョンイベント発生前後の経過時間を測定します。待ち時間の測定は、前後の分析に最適なツールです。「**[!UICONTROL 含む]**」列がテーブルの中央にあり、インクルージョンイベント発生の前と後の期間が両側に表示されます。

![イベント前後の経過時間を示すコホートレポート。](assets/retention-report-latency.png)

### [!UICONTROL カスタムディメンション]コホート

時間ベースのコホート（デフォルト）ではなく、選択したディメンションに基づいてコホートを作成できます。[!UICONTROL 市区町村地域]、[!UICONTROL マーケティングチャネル]、[!UICONTROL キャンペーン]、[!UICONTROL 製品]、[!UICONTROL ページ]、[!UICONTROL 地域]などのディメンションや、その他のディメンションを使用して、リテンションがどのように変化しているかを表示します。これらのディメンションの様々な値に基づいています。

![デフォルトの時間ベースのコホートではなく、選択したディメンションを使用してカスタマイズされたレポートを示すコホートレポート。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[コホートテーブルの設定](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>

