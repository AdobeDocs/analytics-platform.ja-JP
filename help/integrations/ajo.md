---
title: Adobe Journey Optimizer(AJO) とCustomer Journey Analytics(CJA) の統合
description: AJO で生成したデータを取り込み、CJA 内で Analysis Workspace を使用して分析します。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 3a4dbe9a87f8e195a4daf78423d29d73f2be0f83
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 53%

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

>!![NOTE]
AJO と CJA のデータの相違は、通常 1～2%未満です。 過去 2 時間以内に収集されたデータに大きな相違が生じる可能性があります。 処理時間に関わる不一致を軽減するために、当日を除く日付範囲を使用します。

### データビューでのディメンションの設定

データビューで次のディメンションを作成して、Journey Optimizerで類似のディメンションとほぼ同等にすることができます。 詳しくは、 [コンポーネント設定](/help/data-views/component-settings/overview.md) （データビューマネージャー）を参照してください。

| ディメンション | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- |
| ジャーニー名 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | コンポーネントタイプ：Dimension |
| ジャーニー名とバージョン | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | コンポーネントタイプ：Dimension |
| ジャーニーノード名 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | コンポーネントタイプ：Dimension |
| ジャーニーノードタイプ | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | コンポーネントタイプ：Dimension |
| キャンペーン名 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | コンポーネントタイプ：Dimension |
| チャネル | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | コンポーネントタイプ：Dimension |
| プッシュタイトル | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | コンポーネントタイプ：Dimension |
| 電子メールの件名 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | コンポーネントタイプ：Dimension |
| リンクラベル | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | コンポーネントタイプ：Dimension |
| 実験名 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | コンポーネントタイプ：Dimension<br>コンテキストラベル：実験 |
| 治療名 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | コンポーネントタイプ：Dimension<br>コンテキストラベル：実験バリアント |
| E メール配信失敗の理由 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | コンポーネントタイプ：Dimension |
| メール配信の除外理由 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | コンポーネントタイプ：Dimension |

{style=&quot;table-layout:auto&quot;}

### データビューでの指標の設定

データビューで次の指標を作成すると、Journey Optimizer の同様の指標とほぼ同等にすることができます。詳しくは、 [コンポーネント設定](/help/data-views/component-settings/overview.md) （データ表示マネージャー）を参照してください。

| 指標 | 説明 | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- | --- |
| バウンス | バウンスしたメッセージの数（配信後の即時バウンスとバウンスの両方を含む） | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>値を含める：いずれかの条件を満たす場合<br>次と等しい： `bounce`、次と等しい： `denylist` |
| 配信後のバウンス | 一部の電子メールサービスは、配信された電子メールを報告し、後でそれらをバウンスさせます。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | コンポーネントタイプ：指標<br>値を含める：次と等しい `async` |
| 電子メールのクリック数 | メッセージ内のクリック数. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>値を含める：次と等しい `click` |
| メール開封数 | 開封済みメッセージの数. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>値を含める：次と等しい `open` |
| エラー | エラーが発生したメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>値を含める：次と等しい `error` |
| 除外 | 除外されたメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>値を含める：次と等しい `exclude` |
| 送信数 | E メールプロバイダーが受け入れたメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>値を含める：次と等しい `sent` |
| スパムの苦情 | スパム報告の件数. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>値を含める：次と等しい `spam_complaint` |
| 登録解除 | 登録解除の数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>値を含める：次と等しい `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### Analysis Workspaceでの計算指標の設定

Journey Optimizer データセットに必要なディメンションと指標を設定したら、[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を設定し、そのデータに関する追加のインサイトを得ることもできます。これらの計算指標は、データビューマネージャーで作成された上記の指標に基づいています。

| 計算指標 | 説明 | 数式 |
| --- | --- | --- |
| 送信済みメッセージ | 送信されたメッセージの合計数。 成功または失敗したメッセージが含まれます。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| メッセージ配信済み | 顧客に配信された電子メールの数。 | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
