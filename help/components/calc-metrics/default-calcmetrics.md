---
description: Adobeは、使用できる様々な計算指標を提供します。 このページでは、これらの指標とその意図された用途を示します。
title: デフォルトの計算指標
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 51%

---

# デフォルトの計算指標

Customer Journey Analyticsには、最も一般的な使用例に対応するための様々な計算指標が用意されています。 これらの計算指標は、Analysis Workspaceではデフォルトで使用できます。

次に、Adobeが提供する各計算指標と、その計算に使用する基になる関数の一覧を示します。

>[!NOTE]
>
>このページで説明するデフォルトの計算指標に加えて、データビューに計算指標を追加することもできます。
>
>次のことができます。
> * ストリーミングメディア用のデフォルトの計算指標を追加します。詳しくは、 [計算指標](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 既存の指標からカスタム計算指標を作成する ( [計算指標および高度な計算（派生）指標](/help/components/calc-metrics/cm-adv-functions.md).



| 計算指標名 | 関数 | 数式 |
|---------|----------|---------|
| バウンス率 | そのページの訪問数に対する、イベントが 1 つだけ含まれた訪問の割合。 これは、バウンス率が最も高いディメンション項目を把握したり、サイトのバウンス率の合計を時間の経過と共に確認したりするのに役立ちます。 | `[Bounces] / [Entries]` |
| 売上高/訪問者 | サイトへの各訪問者個人が生成した平均収益額。 | `[Revenue] / [Unique Visitors]` |
| 注文件数/訪問者数 | サイトの個々の訪問者が発生した注文またはトランザクションの平均数 | `[Orders] / [Unique Visitors]` |
| 売上高/訪問回数 | サイトへの 1 回の訪問で得られる平均収益額。 | `[Revenue] / [Visits]` |
| 売上高/注文 | サイト上で完了したトランザクションまたは注文ごとに生成された平均収益額。 | `[Revenue] / [Orders]` |
| 注文件数/訪問回数 | 完了したトランザクションにつながったサイトへの訪問の割合。 | `[Orders] / [Visits]` |
| ページビュー数/訪問回数 | ユーザーが 1 回のサイト訪問中に表示するページの平均数。 | `[Page Views] / [Visits]` |
| 訪問回数/訪問者 | ユニーク訪問者がサイトに訪問した平均回数。 | `[Visits] / [Unique Visitors]` |
| リロード回数/ページビュー数 | ページのリロードまたは更新につながったページビューの割合。 | `[Reloads] / [Page Views]` |
| 重み付けられた直帰率 | 関数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 注文支援 | チャネルまたはソースが、購入に至るまでの顧客のジャーニーに貢献したが、最終的な購入には至らなかった回数。 | `[Orders (Visit Participation)] - [Orders]` |
| 出口率 | 特定のページを表示した後にサイトを離れた訪問者の割合。 | `[Exits] / [Visits]` |
| 入口率 | サイトの合計セッション数と比較した、特定のページでサイトに入った訪問者の割合。 | `[Entries] / [Visits]` |
| サイトでの平均時間 | 訪問者がサイトを離れたり移動したりする前にサイトに滞在した平均時間。 | `[Average Time Spent on Site (Seconds)]` |
| 滞在時間/ユーザー（状態） | 平均訪問者がサイトで特定の状態に滞在した時間の長さ。 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| ユーザー（モバイル） | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| アプリのユーザー | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 状態ビュー | アプリの様々な状態または画面へのビュー数 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| アクション | アプリで実行されたアクションの合計数 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| ダウンロード計測用リンククリック数 | サイトへのトラフィックを推進するように設計されたリンクをユーザーがクリックした回数。 | `[Campaign Click-throughs]` |
| ページベロシティ | コンテンツの一部が生成する追加のページビューの数。 これは、どのコンテンツが追加のエンゲージメントを促すかを判断するのに役立ちます。 | `[Page Views] / [Visits]` |
| コンバージョン率 | 購入など、目的のアクションを行った訪問者の割合。 | `[Orders] / [Visits]` |
| 平均セッション時間（モバイル） | 訪問者が単一セッション中にサイトに滞在した平均時間。 | 空白 |
| Experience Cloud ID の適用範囲 | Experience Cloud ID を持つ訪問者の割合。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| コンテンツベロシティ | 新しいコンテンツがサイト上で作成および公開される速度と、そのコンテンツがユーザーエンゲージメントを生成する速度。 | `[Page Views] / [Visits]` |
| ITP 2.1 個別訪問者/個別訪問者 | ITP 2.1 cookie 制限の影響を受けるブラウザーを使用するユニーク訪問者の割合。つまり、CNAME 実装を使用していないお客様です (これは、クライアントサイドの JavaScript を介して Cookie を設定するお客様に適用されます)。 | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 個別訪問者数/7 日後に再訪する個別訪問者数 | 7 日以上の期間の後に再訪問するユニーク訪問者の割合。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| ページビュー / ユニーク訪問者 | サイトへの各ユニーク訪問者に表示されたページの平均数。 | `[Page Views] / [Unique Visitors]` |
| 訪問回数 / 訪問者数 | ユニーク訪問者がサイトに訪問した平均回数。 | `[Visits] / [Unique Visitors]` |
| 推定ユニーク訪問者 (ITP 2.1) | ITP 訪問者（Safari ブラウザーを使用するユーザー）の場合、個別訪問者数を 2 以下で割ります。 この計算指標は、（CNAME 実装を使用せずに）クライアント側の JavaScript を使用して cookie を設定していることを前提としています。 クライアント側 JavaScript を使用して Cookie を設定する実装は、ITP 2.1 以降に影響を受けました。詳しくは、 [Intelligent tracking prevention](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 」を参照してください。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| ページビュー / 推定ユニーク訪問者 (ITP 2.1) | 推定ユニーク訪問者数 (ITP 2.1) で表示されたページの平均数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
