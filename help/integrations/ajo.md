---
title: Adobe Journey Optimizer と Customer Journey Analytics の統合
description: AJO で生成したデータを取り込み、CJA 内で Analysis Workspace を使用して分析します。
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: ht
source-wordcount: '664'
ht-degree: 100%

---


# Adobe Journey Optimizer と Customer Journey Analytics の統合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=ja) は、接続され、コンテキストに応じて、パーソナライズされたエクスペリエンスを提供するのに役立ちます。カスタマージャーニーで次のステップに顧客を表示するのに役立ちます。

Journey Optimizer で生成されたデータを読み込み、Customer Journey Analytics でアドバンス分析を実行するには、次の手順に従ってください。

## Journey Optimizer から Adobe Experience Platform にデータを送信

Adobe Experience Platform は、中央のデータソースとして機能し、Journey Optimizer と Customer Journey Analytics の間をリンクします。Journey Optimizer データをプラットフォームにデータセットとして送信する手順については、Journey Optimizer ユーザーガイドの[データセットの基本を学ぶ](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=ja)を参照してください。

## Customer Journey Analytics で接続を作成する

Journey Optimizer データが Adobe Experience Platform に入ったら、Journey Optimizer データセットに基づいて[接続を作成](/help/connections/create-connection.md)できます。Platform に送信したデータセットを選択します。

## Journey Optimizer のディメンションと指標に対応するようにデータビューを設定

接続を作成したら、1 つ以上の[データビュー](/help/data-views/create-dataview.md)を作成して、Customer Journey Analytics で使用できる目的のディメンションと指標を設定できます。

データビューで次の指標を作成すると、Journey Optimizer の同様の指標とほぼ同等にすることができます。ディメンションと指標をカスタマイズする方法について詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| 指標 | 説明 | データビュー設定 |
| --- | --- | --- |
| バウンス | バウンスしたメッセージの数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：いずれかの条件を満たす場合<br>次に等しい：`bounce`<br>次に等しい：`denylist` |
| エラー | エラーが発生したメッセージの数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `error` |
| 除外 | 除外されたメッセージの数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `exclude` |
| 登録解除 | 登録解除の数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageInteraction.interactionType` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `unsubscribe` |
| クリック数 | メッセージ内のクリック数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageInteraction.interactionType` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `click` |
| 開封数 | 開封済みメッセージの数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageInteraction.interactionType` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `open` |
| スパム報告件数 | スパム報告の件数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageInteraction.interactionType` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `spam_complaint` |
| 正常に送信されたメッセージ | 正常に送信されたメッセージの数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `sent` |
| 同期の失敗 | 同期に失敗したメッセージの合計数 | 次の設定でスキーマ文字列要素 `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` を使用します。<br>コンポーネントタイプ：指標<br>除外値を含める：次に等しい `sync` |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer 指標を使用して計算指標を設定

Journey Optimizer データセットに必要なディメンションと指標を設定したら、[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を設定し、そのデータに関する追加のインサイトを得ることもできます。これらの計算指標は、データビューマネージャーで作成された上記の指標に基づいています。

| 計算指標 | 説明 | 数式 |
| --- | --- | --- |
| 送信されたメッセージの合計 | 送信され、成功または失敗したメッセージの合計数 | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer と Customer Journey Analytics のレポートの相違点

製品間のデータの不一致は、通常 1～2％です。製品間の不一致が大きい場合は、次の原因が考えられます。

* 特に、過去 2 時間以内に収集されたデータでは、受信データの処理時間は、製品間で若干異なる場合があります。処理時間に関わる不一致を軽減するために、当日を除く日付範囲を使用します。
* 計算指標「送信されたメッセージの合計」には「再試行」指標は含まれません。 「再試行」指標のデータはデータセットに含まれないことから、AJO レポートに対して、CJA レポートでは低い数字が表示される可能性があります。ただし、再試行データは、「正常に送信されたメッセージ」または「バウンス」指標に収束されます。 1 週間以上の日付範囲を使用して、製品間の「送信されたメッセージの合計」指標との不一致を軽減します。
