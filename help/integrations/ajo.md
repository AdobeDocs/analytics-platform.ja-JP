---
title: Adobe Journey Optimizer（AJO）と Customer Journey Analytics（CJA）の統合
description: AJO で生成したデータを取り込み、CJA 内で Analysis Workspace を使用して分析します。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 933f3f0336c325bf0973a0379532b3e19f1c6d68
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 84%

---

# Adobe Journey Optimizer と Customer Journey Analytics の統合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=ja) は、接続され、コンテキストに応じて、パーソナライズされたエクスペリエンスを提供するのに役立ちます。カスタマージャーニーで次のステップに顧客を表示するのに役立ちます。

Journey Optimizer で生成されたデータを読み込み、Customer Journey Analytics でアドバンス分析を実行するには、次の手順に従ってください。

## Journey Optimizer から Adobe Experience Platform にデータを送信

Adobe Experience Platform は、中央のデータソースとして機能し、Journey Optimizer と Customer Journey Analytics の間をリンクします。Journey Optimizer データをプラットフォームにデータセットとして送信する手順については、Journey Optimizer ユーザーガイドの[データセットの基本を学ぶ](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=ja)を参照してください。

## Customer Journey Analytics で接続を作成する

Journey OptimizerデータをAdobe Experience Platformに配置すると、 [接続の作成](/help/connections/create-connection.md) Journey Optimizerデータセットに基づいて または、既存の接続にJourney Optimizerデータセットを追加できます。

次のデータセットを選択して設定します。

| データセット | データセットタイプ | 接続設定 | 説明 |
| --- | --- | --- | --- |
| AJO メッセージフィードバックイベントデータセット | イベント | ユーザー ID: `IdentityMap` | メッセージ配信イベント（「 」など）が含まれます[!UICONTROL 送信数]&#39;および&#39;[!UICONTROL バウンス]&#39;. |
| AJO メールトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID: `IdentityMap` | 「 」などの E メールトラッキングイベントが含まれます[!UICONTROL 開封数]&#39;、&#39;[!UICONTROL クリック数]&#39;、&#39;[!UICONTROL 配信停止]&#39;. |
| AJO プッシュトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID: `IdentityMap` | 「 」などのプッシュトラッキングイベントが含まれます[!UICONTROL アプリの起動回数]&#39;. |
| ジャーニーステップイベント | イベント | ユーザー ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | ジャーニーの各ノードに関係したプロファイルを示すイベントが含まれます。 |
| AJO エンティティデータセット | ルックアップ | キー： `_id`<br>一致するキー： `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | すべての AJO イベントデータにジャーニーとキャンペーンのメタデータを関連付ける分類が含まれます。 |

{style="table-layout:auto"}


## Journey Optimizer のディメンションと指標に対応するようにデータビューを設定

接続を作成したら、1 つ以上の[データビュー](/help/data-views/create-dataview.md)を作成して、Customer Journey Analytics で使用できる目的のディメンションと指標を設定できます。

>[!NOTE]
>
>AJO と CJA の間のデータの不一致は通常、1～2％未満です。過去 2 時間以内に収集されたデータについては、より大きな不一致が生じる可能性があります。処理時間に関わる不一致を軽減するために、当日を除く日付範囲を使用します。


### データビューでのディメンションの設定

データビューで次のディメンションを作成すると、Journey Optimizer の同様のディメンションとほぼ同等にすることができます。ディメンションのカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| ディメンション | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- |
| ジャーニー名 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | コンポーネントタイプ：ディメンション |
| ジャーニー名とバージョン | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | コンポーネントタイプ：ディメンション |
| ジャーニーノード名 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | コンポーネントタイプ：ディメンション |
| ジャーニーノードタイプ | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | コンポーネントタイプ：ディメンション |
| キャンペーン名 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | コンポーネントタイプ：ディメンション |
| チャネル | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | コンポーネントタイプ：ディメンション |
| プッシュタイトル | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | コンポーネントタイプ：ディメンション |
| メールの件名 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | コンポーネントタイプ：ディメンション |
| リンクラベル | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | コンポーネントタイプ：ディメンション |
| 実験の名前 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | コンポーネントタイプ：ディメンション<br>コンテキストラベル：実験 |
| 処理の名前 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | コンポーネントタイプ：ディメンション<br>コンテキストラベル：実験バリアント |
| メール配信失敗の理由 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | コンポーネントタイプ：ディメンション |
| メール配信除外の理由 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | コンポーネントタイプ：ディメンション |

{style="table-layout:auto"}

### データビューでの指標の設定

データビューで次の指標を作成すると、Journey Optimizer の同様の指標とほぼ同等にすることができます。指標のカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| 指標 | 説明 | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- | --- |
| バウンス | バウンスしたメッセージの数（即時バウンスと配信後のバウンスの両方を含む） | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：いずれかの条件を満たす場合<br>次と等しい：`bounce`、次と等しい：`denylist` |
| 配信後のバウンス | 一部のメールサービスでは、メールが配信されたと報告した後で、バウンスが発生します。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | コンポーネントタイプ：指標<br>除外値を含める：`async` と等しい |
| メールのクリック数 | メッセージ内のクリック数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`click` と等しい |
| メール開封数 | 開封済みメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`open` と等しい |
| エラー | エラーが発生したメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：`error` と等しい |
| 除外 | 除外されたメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：`exclude` と等しい |
| 送信数 | メールプロバイダーが受け入れたメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：`sent` と等しい |
| スパム報告件数 | スパム報告の件数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`spam_complaint` と等しい |
| 登録解除 | 登録解除の数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`unsubscribe` と等しい |

{style="table-layout:auto"}

### Analysis Workspace の計算指標の設定

Journey Optimizer データセットに必要なディメンションと指標を設定したら、[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を設定し、そのデータに関する追加のインサイトを得ることもできます。これらの計算指標は、データビューマネージャーで作成された上記の指標に基づいています。

| 計算指標 | 説明 | 数式 |
| --- | --- | --- |
| 送信済みメッセージ | 送信済みメッセージの合計数。成功または失敗したメッセージが含まれます。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 配信済みメッセージ | 顧客に配信されたメールの数。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
