---
title: コホートテーブルの概要
description: Analysis Workspaceでコホートテーブルをコホート分析に使用する方法を説明します
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 30%

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
>abstract="イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントとチャーンの推移を分析します。<br/><br/>**パラメーター&#x200B;**<br/>**インクルージョン条件**：最初の訪問者コホートの定義に使用するコンポーネント。<br/>**再来訪条件**：訪問者が再来訪したかどうかを判断するために使用するコンポーネント。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、{CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) ![4}Customer Journey Analytics_ のコホートテーブルについて説明します **。_**_<br/>_[ この記事の ](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis)AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_**Adobe Analytics**版については、_ コホートテーブル ![ を参照してください。_

>[!ENDSHADEBOX]


*コホート* とは、特定の期間、共通の特徴を共有する人々のグループです。 ![ テキスト番号付き ](/help/assets/icons/TextNumbered.svg)**[!UICONTROL コホートテーブル]** ビジュアライゼーションは、例えば、コホートがブランドとどのように関わっているかを学びたい場合に役立ちます。 トレンドの変更を簡単に見分けて、それに応じて対応できます（[!UICONTROL コホート分析]の説明は、[コホート分析 101](https://ja.wikipedia.org/wiki/Cohort_analysis) など、Web 上で参照できます）。

コホートレポートを作成したら、コンポーネント（特定のディメンション、指標およびフィルター）をキュレートして、任意のユーザーとコホートレポートを共有できます。[キュレートおよび共有](/help/analysis-workspace/curate-share/curate.md)を参照してください。

[!UICONTROL  コホートテーブル ] を使用して実行できる操作の例：

* 目的のアクションを促進するために設計したキャンペーンを開始する。
* 顧客のライフサイクルのまさに適切なタイミングでマーケティング予算を振り替える。
* 価値を最大化するために、体験版またはオファーを終了するタイミングを認識します。
* 価格やアップグレードパスなどの領域で、A/B テストの着想を得る。

[!UICONTROL  コホートテーブル ] は、[!UICONTROL Analysis Workspace] へのアクセス権を持つすべてのCustomer Journey Analyticsユーザーが利用できます。


>[!BEGINSHADEBOX]

デモビデオについては、![Analysis Workspaceでの VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ コホート分析 ](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"} を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL  コホート分析 ] では、フィルタリングできない指標（計算指標など）、整数以外の指標（売上高など）、発生件数はサポートしていません。 [!UICONTROL  コホート分析 ] で使用できるのはフィルターで使用できる指標のみで、一度に増やせるのは 1 つのみです。

Customer Journey Analyticsのコホートテーブルでは、ダブルベース（または任意の数値ベース）の指標をサポートしています。 例えば、Purchase.Value （double）はインクルージョン/リターン指標として使用できます。 また、Analytics Source Connector を介してAdobe Experience Platformに渡されるすべての指標も重複しています。

## コホートテーブル機能

以下の節では、作成するコホートを微調整して制御できるコホート分析機能について説明します。

コホートの作成および [!UICONTROL  コホート分析 ] レポートの実行について詳しくは、[ コホートテーブルの設定 ](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) を参照してください。

### [!UICONTROL  リテンション ] テーブル

[!UICONTROL  保持 ] コホートテーブルは人物を返します。各データセルは、その期間中にアクションを実行したコホート内の人物の生の数と割合を示します。 指標は最大 3 個、フィルターは最大 10 個含めることができます。

![ コホート内のユーザーの単位と割合を示すレンションコホートレポート。](assets/retention-report.png)

### [!UICONTROL  チャーン ] テーブル

[!UICONTROL  チャーン ] コホートテーブルは、リテンション テーブルの逆であり、コホートの返品条件を満たさなかったユーザーまたは満たさなかったユーザーの経時的な数を示します。 指標は最大 3 個、フィルターは最大 10 個含めることができます。

![ コホートの返品条件を満たさないユーザーの数量と割合を示すチャーンテーブル。](assets/churn-report.png)

### [!UICONTROL ローリング計算]

リテンションまたはチャーンは、「ローリング計算」と呼ばれる「含める」列ではなく、前の列に基づいて計算できます。

![ 前のデータ列に基づく計算を示すコホート保持レポート。](assets/retention-report-rolling.png)

### [!UICONTROL  待ち時間 ] テーブル

待ち時間テーブルは、インクルージョンイベントが発生する前後の経過時間を測定します。 待ち時間の測定は、事前分析および事後分析に最適なツールです。 「**[!UICONTROL 含む]**」列がテーブルの中央にあり、インクルージョンイベント発生の前と後の期間が両側に表示されます。

![ イベント前後の経過時間を示すコホートレポート。](assets/retention-report-latency.png)

### [!UICONTROL  カスタムディメンション ] コホート

時間ベースのコホート（デフォルト）ではなく、選択したディメンションに基づいてコホートを作成できます。 [!UICONTROL  市区町村地域 ]、[!UICONTROL  マーケティングチャネル ]、[!UICONTROL  キャンペーン ]、[!UICONTROL  製品 ]、[!UICONTROL  ページ ]、[!UICONTROL  地域 ] などのディメンションや、その他のディメンションを使用して、リテンションがどのように変化しているかを表示します。 これらのディメンションの様々な値に基づいています。

![ 選択したディメンションでカスタマイズされたレポートを表示するコホートレポート。デフォルトの時間ベースのコホートではありません。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[ コホートテーブルの設定 ](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>

