---
title: Adobe Journey Optimizer と Customer Journey Analytics の統合
description: Adobe Journey Optimizer で生成したデータを取り込み、Customer Journey Analytics 内で Analysis Workspace を使用して分析します。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 5185c28c7a2cf1a0690e783633bbfbf851a1dcd1
workflow-type: tm+mt
source-wordcount: '1541'
ht-degree: 52%

---

# Journey OptimizerとCustomer Journey Analyticsの統合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/get-started) は、接続され、コンテキストに応じて、パーソナライズされたエクスペリエンスを提供するのに役立ちます。カスタマージャーニーで次のステップに顧客を表示するのに役立ちます。

Journey Optimizerで生成されたデータを設定して、Customer Journey Analyticsでアドバンス分析を実行できます。 この統合は自動的に設定できます。 必要に応じて、接続ビューまたはデータビューで使用できるデータセット、ディメンションまたは指標を手動で追加カスタマイズできます。

## Journey Optimizer統合の自動設定

{{release-limited-testing-section}}

Journey Optimizerでは、レポートエンジンとしてのCustomer Journey Analyticsの使用をサポートしています。 参照： [新しいレポートインターフェイスの概要](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja) Journey Optimizerのドキュメントで説明しています。

Journey OptimizerのCustomer Journey Analyticsレポートを有効にすると、自動的に [接続](/help/connections/overview.md) および [データビュー](/help/data-views/data-views.md) は、特定のサンドボックス用に作成されます。

### 接続

接続の名前はです **[!UICONTROL AJO対応の接続（*サンドボックス名*）]** とは、設定およびデータセットに次の標準値があります。

| **接続設定** | 値 |
|---|---| 
| [!UICONTROL 接続名] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL 接続の説明] | [!UICONTROL *ここに接続の説明を入力*] |
| [!UICONTROL タグ] | [!UICONTROL *タグを選択*] |


| **データ設定** | 値 |
|---|---| 
| [!UICONTROL 周期的なデータ時間枠を有効にする] | 有効。 [!UICONTROL 選択した月数] `13`. |
| [!UICONTROL サンドボックス] | [!UICONTROL *サンドボックスの名前*] （無効。この設定は変更できません）。 |
| [!UICONTROL 毎日のイベントの平均数] | 100 万未満（無効。この設定は変更できません）。 |


| データセット名 | スキーマ | データセットタイプ | データソースタイプ | 人物 Id | キー | 一致するキー | 新しいデータを読み込む | データをバックフィル |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO エンティティデータセット] | [!UICONTROL AJO エンティティレコードスキーマ] | [!UICONTROL ルックアップ] | [!UICONTROL その他] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![ステータス グリーン](assets/../../connections/assets/status-green.svg) 日付： | ![ステータス グレー](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL ジャーニーステップイベント] | [!UICONTROL Journey Orchestrationのジャーニーステップイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL  IdentityMap （\&lt;primary>）] | - | - | ![ステータス グリーン](assets/../../connections/assets/status-green.svg) 日付： | ![ステータス グレー](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL AJO メールトラッキングエクスペリエンスイベントデータセット] | [!UICONTROL AJO メールトラッキングエクスペリエンスイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL IdentityMap （\&lt;primary>）] | - | - | ![ステータス グリーン](assets/../../connections/assets/status-green.svg) 日付： | ![ステータス グレー](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL AJO メールトラッキングエクスペリエンスイベントデータセット] | [!UICONTROL AJO メールトラッキングエクスペリエンスイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL IdentityMap （\&lt;primary>）] | - | - | ![ステータス グリーン](assets/../../connections/assets/status-green.svg) 日付： | ![ステータス グレー](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL AJO メッセージフィードバックイベントデータセット] | [!UICONTROL AJO メッセージフィードバックイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL IdentityMap （\&lt;primary>）] | - | - | ![ステータス グリーン](assets/../../connections/assets/status-green.svg) 日付： | ![ステータス グレー](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL AJO プッシュトラッキングエクスペリエンスイベントデータセット] | [!UICONTROL AJO プッシュトラッキングエクスペリエンスイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL IdentityMap （\&lt;primary>）] | - | - | ![ステータス グリーン](assets/../../connections/assets/status-green.svg) 日付： | ![ステータス グレー](assets/../../connections/assets/status-gray.svg) オフ |


### データビュー

データビューには名前が付けられます **AJOのデータビューを有効にする（*サンドボックス名*）**.

- が含まれる **[!UICONTROL 設定]** タブで、次の値が標準で設定されています。

  | 設定 | 値 |
  |---|---|
  | [!UICONTROL 接続] | AJO対応の接続（*サンドボックス名*） |
  | [!UICONTROL 名前] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL 外部 ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` （名前から派生） |
  | [!UICONTROL 説明] | `undefined` |

  {style="table-layout:fixed"}

  | 互換性 | 値 |
  |---|---|
  | [!UICONTROL Adobe Journey Optimizerのデフォルトデータビューとして設定] | 有効（デフォルト）。<br/><br/>この設定オプションを使用すると、手動で設定しなくても、Journey Optimizerで使用するデータビューを指定できます。 この設定オプションを有効にする方法（デフォルトでまだ有効になっていない場合）については、 [互換性](/help/data-views/create-dataview.md#compatibility) のセクション [データビューの作成または編集](/help/data-views/create-dataview.md). <br/><br/>このオプションを無効にすると、デフォルトのデータビューの変更を続行するかどうかを確認するダイアログが表示されます。 選択した場合 **[!UICONTROL 続行]**&#x200B;を使用する場合、別のデータビューをデフォルトのデータビューとして選択する必要があります。 を選択 **[!UICONTROL 確認]** をクリックして選択を確定します。 を選択 **[!UICONTROL キャンセル]** デフォルトデータビューの変更をキャンセルします。 |

  | コンテナ | 値 |
  |---|---|
  | [!UICONTROL 人物のコンテナ名] | `Person` |
  | [!UICONTROL セッションのコンテナ名] | `Session` |
  | [!UICONTROL イベントのコンテナ名] | `Event` |

  | カレンダー | 値 |
  |---|---|
  | [!UICONTROL タイムゾーン] | 所在地に合ったタイム ゾーン |
  | [!UICONTROL カレンダータイプ] | グレゴリオ暦 |
  | [!UICONTROL 年の最初の月] | 1月 |
  | [!UICONTROL 週の最初の曜日] | 日曜日 |


- が含まれる **Components** タブ：
   - 次を持つすべての指標およびディメンション [!UICONTROL （AJO）] の名前にが追加され、この自動設定の一部として自動的に追加されます。
   - 自動的に追加された指標やディメンションの一部は、派生フィールドに基づいています。 これらの派生フィールドは、この統合用に特別に作成されます。 例えば、指標です [!UICONTROL ランディングページのクリック数（AJO）] は、に基づいています [!UICONTROL ランディングページクリック数] 派生フィールド。
   - 一部の指標またはディメンションには、追加の設定があります。 例： [!UICONTROL スパムの苦情（AJO）] 持つ [!UICONTROL 形式] および [!UICONTROL 値を含める/除外] 設定が適用されました。
   - 自動的に追加されたすべての指標およびディメンションには、という名前のコンテキストラベルがあります `:`*`name_of_metric_or_dimension`*. 例： [!UICONTROL ランディングページのクリック数（AJO）] 指標にコンテキストラベルがある `: Landing page clicks (AJO)`.

- が含まれる **[!UICONTROL 設定]** タブが表示され、特定の設定値が適用されない

>[!IMPORTANT]
>
>接続およびデータビューの自動設定された値を変更すると、自動設定されたCustomer Journey Analytics統合に依存し、使用しているJourney Optimizer レポートに影響します。


## Journey Optimizerで使用するデータビューの手動設定

次の節では、Journey Optimizerで生成されたデータを手動で使用して、Customer Journey Analyticsのアドバンス分析を実行する方法について説明します。 これは、 [自動設定オプション](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer) はニーズを満たすには不十分です。

### Journey OptimizerからExperience Platformへのデータの送信

Adobe Experience Platform は、中央のデータソースとして機能し、Journey Optimizer と Customer Journey Analytics の間をリンクします。参照： [データセットの基本を学ぶ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) Journey Optimizer データをデータセットとしてExperience Platformに送信する手順については、Journey Optimizer ユーザーガイドを参照してください。

### Customer Journey Analytics で接続を作成する

Journey Optimizer データが Adobe Experience Platform に入ったら、Journey Optimizer データセットに基づいて[接続を作成](/help/connections/create-connection.md)できます。または、既存の接続に Journey Optimizer データセットを追加できます。

次のデータセットを選択して設定します。

| データセット | データセットタイプ | 接続設定 | 説明 |
| --- | --- | --- | --- |
| AJO メッセージフィードバックイベントデータセット | イベント | ユーザー ID：`IdentityMap` | メッセージ配信イベント（[!UICONTROL 送信数]や[!UICONTROL バウンス数]など）が含まれています。 |
| AJO メールトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID：`IdentityMap` | メールトラッキングイベント（[!UICONTROL 開封数]、[!UICONTROL クリック数]、[!UICONTROL 登録解除数]など）が含まれています。 |
| AJO プッシュトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID：`IdentityMap` | プッシュトラッキングイベント（[!UICONTROL アプリの起動回数]など）が含まれています。 |
| ジャーニーステップイベント | イベント | ユーザー ID：`_experience.journeyOrchestration.`<br>`stepEvents.profileID` | ジャーニーの各ノードに参加したプロファイルを示すイベントが含まれています。 |
| AJO エンティティデータセット | ルックアップ | キー：`_id`<br>一致するキー：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | ジャーニーとキャンペーンのメタデータをすべてのJourney Optimizer イベントデータに関連付ける分類が含まれます。 |

{style="table-layout:auto"}


### Journey Optimizer のディメンションと指標に対応するようにデータビューを設定

接続を作成したら、1 つ以上の[データビュー](/help/data-views/create-dataview.md)を作成して、Customer Journey Analytics で使用できる目的のディメンションと指標を設定できます。

>[!NOTE]
>
>Journey OptimizerとCustomer Journey Analyticsの間のデータの不一致は、通常、1～2% 未満です。 過去 2 時間以内に収集されたデータについては、より大きな不一致が生じる可能性があります。処理時間に関わる不一致を軽減するために、当日を除く日付範囲を使用します。


#### データビューでのディメンションの設定

データビューで次のディメンションを作成すると、Journey Optimizer の同様のディメンションとほぼ同等にすることができます。参照： [コンポーネント設定](/help/data-views/component-settings/overview.md) ディメンションのカスタマイズオプションについて詳しくは、データビューマネージャーを参照してください。

| ディメンション | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- |
| ジャーニー名 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | コンポーネントタイプ：ディメンション |
| ジャーニー名とバージョン | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | コンポーネントタイプ：ディメンション |
| ジャーニーノード名 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | コンポーネントタイプ：ディメンション |
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
| 要素ラベル | `_experience.decisioning.propositionAction.label` | コンポーネントタイプ：ディメンション |

{style="table-layout:auto"}

#### データビューでの指標の設定

データビューで次の指標を作成すると、Journey Optimizer の同様の指標とほぼ同等にすることができます。指標のカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| 指標 | 説明 | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- | --- |
| バウンス数 | 即時バウンス数と配信後のバウンス数の両方を含む、バウンスしたメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：いずれかの条件を満たす場合<br>次と等しい：`bounce`、次と等しい：`denylist` |
| 配信後のバウンス | 一部のメールサービスでは、メールが配信されたと報告した後で、バウンスが発生します。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | コンポーネントタイプ：指標<br>除外値を含める：`async` と等しい |
| メールのクリック数 | メッセージ内のクリック数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`click` と等しい |
| メール開封数 | 開封済みメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`open` と等しい |
| エラー数 | エラーが発生したメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：`error` と等しい |
| 除外 | 除外されたメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：`exclude` と等しい |
| 送信数 | メールプロバイダーが受け入れたメッセージの数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標<br>除外値を含める：`sent` と等しい |
| スパム報告件数 | スパム報告の件数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`spam_complaint` と等しい |
| 登録解除 | 登録解除の件数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | コンポーネントタイプ：指標<br>除外値を含める：`unsubscribe` と等しい |
| エッジ送信数 | エッジネットワークが web または Mobile SDK にメッセージを送信した回数 | スキーマ文字列要素 `_experience.decisioning.propositionEventType.send` を使用します | |
| インバウンド表示数 | Web またはアプリ内メッセージがユーザーに表示された回数 | スキーマ文字列要素 `_experience.decisioning.propositionEventType.display` を使用します | |
| インバウンドクリック数 | Web またはアプリ内メッセージのクリック数 | スキーマ文字列要素 `_experience.decisioning.propositionEventType.interact` を使用します | |
| アプリ内トリガー数 | 決定支援エンジンがメッセージの表示を提案した回数。Mobile SDK は、決定を上書きして、実際のディスプレイの数を減らすことができます。 | スキーマ文字列要素 `_experience.decisioning.propositionEventType.trigger` を使用します | |
| アプリ内破棄数 | SDK によってアプリ内メッセージが UI から削除された回数 | スキーマ文字列要素 `_experience.decisioning.propositionEventType.dismiss` を使用します | |

{style="table-layout:auto"}

#### Analysis Workspace の計算指標の設定

Journey Optimizer データセットに必要なディメンションと指標を設定したら、[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を設定し、そのデータに関する追加のインサイトを得ることもできます。これらの計算指標は、データビューマネージャーで作成された上記の指標に基づいています。

| 計算指標 | 説明 | 数式 |
| --- | --- | --- |
| 送信済みメッセージ | 送信済みメッセージの合計数。成功または失敗したメッセージが含まれます。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 配信済みメッセージ | 顧客に配信されたメールの数。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
