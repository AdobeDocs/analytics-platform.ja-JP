---
title: コホートテーブルの概要
description: コホート分析を利用して、オーディエンスのデータを深く掘り下げ、そのデータを関連するグループに分類する方法を紹介します。 Analysis Workspaceのコホート分析では、
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
TQID: https://experienceleague.adobe.com/3WB5sKKSaLe9VvAe6rlCTUqDYsG3kiqLCN-KaEtIlDw
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: addf009e-030a-4310-8534-776a3e62ed48
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 754
ht-degree: 89%

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
>abstract="イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントとチャーンの推移を分析します。 精度、コホート分析のタイプ、ローリング計算を使用するかどうかなどの追加設定を指定します。 選択したディメンションに基づいて待ち時間テーブルまたはカスタムディメンションコホートを作成する詳細オプションを設定できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** バージョンの[ コホートテーブル ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis)を参照してください。_

>[!ENDSHADEBOX]


*コホート*&#x200B;は、特定の期間にわたって共通の特性を持つ人物のグループです。 ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL コホートテーブル]**&#x200B;ビジュアライゼーションは、例えば、あるコホートが、あるブランドとどのようにエンゲージしているかを知るのに役立ちます。 トレンドの変更を簡単に見分けて、それに応じて対応できます （[!UICONTROL コホート分析]の説明は、[コホート分析 101](https://ja.wikipedia.org/wiki/Cohort_analysis) など、Web 上で参照できます）。

コホートレポートを作成したら、コンポーネント（特定のディメンション、指標およびセグメント）をキュレートして、任意のユーザーとコホートレポートを共有できます。 [キュレートと共有](/help/analysis-workspace/curate-share/curate.md)を参照してください。

[!UICONTROL コホートテーブル]で実行できる操作の例：

* 目的の行動を促すためのキャンペーンを実施し、
* カスタマーライフサイクルにおける適切なタイミングでマーケティング予算を変更できます。
* 価値を最大化するために、体験版やオファーを終了するタイミングを認識する。
* 価格やアップグレードパスなどの領域で、A/B テストの着想を得る。

[!UICONTROL コホートテーブル]は、[!UICONTROL Analysis Workspace] へのアクセス権を持つすべての Customer Journey Analytics ユーザーが使用できます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のコホート分析](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL コホート分析]は、セグメント化できない指標（計算指標を含む）、整数以外の指標（売上高など）、発生件数をサポートしていません。 [!UICONTROL コホート分析]で使用できるのはセグメントで使用できる指標のみで、一度に 1 つのみを増分できます。

Customer Journey Analytics のコホートテーブルでは、2 倍ベース（または任意の数値ベース）の指標をサポートします。 例えば、Purchase.Value（2 倍）はインクルージョン／リターン指標として使用できます。 また、Analytics ソースコネクタ経由で Adobe Experience Platform に渡されるすべての指標も 2 倍になります。

## コホートテーブルの機能

次の節では、作成しているコホートを微調整して制御できるコホート分析機能について説明します。

コホートの作成と[!UICONTROL コホート分析]レポートの実行について詳しくは、[コホートテーブルの設定](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)を参照してください。

### リテンションテーブル

[!UICONTROL リテンション]コホートテーブルはユーザーを返します。各データセルには、その期間中にアクションを実行したコホートのユーザーの生の数と割合が表示されます。 指標は最大 3 個、セグメントは最大 10 個含めることができます。

![コホート内のユーザーの単位と割合を示すリテンションコホートレポート。](assets/retention-report.png)

### 解約テーブル

[!UICONTROL チャーン]コホートテーブルは、リテンションテーブルの逆で、時間の経過と共にコホートからフォールアウトしたユーザーや、コホートへのリターン条件を満たさなかったユーザーが表示されます。 指標は最大 3 個、セグメントは最大 10 個含めることができます。

![コホートのリターン条件を満たさなかった人物の数と割合を示すチャーンテーブル。](assets/churn-report.png)

### 周期計算

リテンションまたはチャーンは、「含む」列ではなく、前の列に基づいて計算できます。これをローリング計算と呼びます。

![前のデータ列に基づく計算を示すコホートリテンションレポート。](assets/retention-report-rolling.png)

### 待ち時間テーブル

待ち時間テーブルは、インクルージョンイベント発生前後の経過時間を測定します。 待ち時間の測定は、前後の分析に最適なツールです。 「**[!UICONTROL 含む]**」列がテーブルの中央にあり、インクルージョンイベント発生の前と後の期間が両側に表示されます。

![イベント前後の経過時間を示すコホートレポート。](assets/retention-report-latency.png)

### カスタムディメンションコホート

時間ベースのコホート（デフォルト）ではなく、選択したディメンションに基づいてコホートを作成できます。 [!UICONTROL 市区町村地域]、[!UICONTROL マーケティングチャネル]、[!UICONTROL キャンペーン]、[!UICONTROL 製品]、[!UICONTROL ページ]、[!UICONTROL 地域]などのディメンションや、その他のディメンションを使用して、リテンションがどのように変化しているかを表示します。 これらのディメンションの様々な値に基づいています。

![デフォルトの時間ベースのコホートではなく、選択したディメンションを使用してカスタマイズされたレポートを示すコホートレポート。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[コホートテーブルの設定](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>

