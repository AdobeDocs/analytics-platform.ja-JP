---
title: Adobe Journey OptimizerとCustomer Journey Analyticsの統合
description: AJO で生成されたデータを取り込み、CJA 内でAnalysis Workspaceを使用して分析します。
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 4%

---


# Adobe Journey OptimizerとCustomer Journey Analyticsの統合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=ja) は、連携し、コンテキストに応じて、パーソナライズされたエクスペリエンスを提供するのに役立ちます。 カスタマージャーニーの次のステップに顧客を導くのに役立ちます。

次の手順を実行すると、Journey Optimizerで生成されたデータをインポートして、Customer Journey Analyticsで高度な分析を実行できます。

## Journey OptimizerからAdobe Experience Platformにデータを送信する

Adobe Experience Platformは、中央のデータソースとして機能し、Journey OptimizerとCustomer Journey Analyticsの間のリンクです。 詳しくは、 [データセットの基本を学ぶ](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) ( Journey Optimizerユーザーガイド ) を参照してください。

## Customer Journey Analyticsでの接続の作成

Journey OptimizerデータをAdobe Experience Platformに配置すると、 [接続の作成](/help/connections/create-connection.md) Journey Optimizerデータセットに基づいて Platform に送信したデータセットを選択します。

## データビューを、Journey Optimizerのディメンションと指標に合わせて設定する

接続を作成した後、1 つ以上の [データビュー](/help/data-views/create-dataview.md) 「Customer Journey Analytics」で使用できる目的のディメンションと指標を設定する場合。

データビューで次の指標を作成して、Journey Optimizerで類似の指標とほぼ同等の値を達成できます。 詳しくは、 [コンポーネント設定](/help/data-views/component-settings/overview.md) （データビューマネージャー）を参照してください。

| 指標 | 説明 | データビュー設定 |
| --- | --- | --- |
| バウンス | バウンスしたメッセージの数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：いずれかの条件を満たす場合<br>次と等しい： `bounce`<br>次と等しい： `denylist` |
| エラー | エラーが発生したメッセージの数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `error` |
| Excludes | 除外されたメッセージの数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `exclude` |
| 登録解除 | 配信停止の数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageInteraction.interactionType` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `unsubscribe` |
| クリック数 | メッセージ内のクリック数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageInteraction.interactionType` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `click` |
| 開封数 | 開かれたメッセージの数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageInteraction.interactionType` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `open` |
| スパムの苦情数 | スパムの苦情数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageInteraction.interactionType` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `spam_complaint` |
| メッセージが正常に送信されました | 正常に送信されたメッセージ数 | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `sent` |
| 同期エラー | 同期に失敗したメッセージの合計数です | スキーマ文字列要素を使用する `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` を次の設定で使用します。<br>コンポーネントタイプ：指標<br>値を含める：次と等しい `sync` |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer指標を使用した計算指標の設定

Journey Optimizerデータセット用の目的のディメンションと指標を設定したら、 [計算指標](/help/components/calc-metrics/calc-metr-overview.md) を参照してください。 これらの計算指標は、データビューマネージャーで作成された上記の指標に基づいています。

| 計算指標 | 説明 | 数式 |
| --- | --- | --- |
| 送信されたメッセージ総数 | 送信された、成功または失敗したメッセージの合計数 | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Journey OptimizerとCustomer Journey Analyticsのレポートの違い

製品間のデータの相違は、通常、1～2%です。 製品間の大きな相違は、次の原因になる可能性があります。

* 受信データの処理時間は、製品間で若干異なる場合があります。特に、過去 2 時間以内に収集されたデータの場合は異なります。 処理時間に関わる不一致を軽減するために、今日を除く日付範囲を使用します。
* 計算指標「送信された合計メッセージ数」には「再試行」指標は含まれません。 「再試行」指標のデータはデータセットに含まれず、CJA レポートと AJO レポートで表示される回数が少なくなる可能性があります。 ただし、再試行データは、「メッセージは正常に送信されました」または「バウンス」指標に収束されます。 1 週間以上の日付範囲を使用して、製品間の「送信されたメッセージの合計」指標との不一致を軽減します。
