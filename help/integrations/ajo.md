---
title: Adobe Journey Optimizerの統合
description: Adobe Journey Optimizer で生成したデータを取り込み、Customer Journey Analytics 内で Analysis Workspace を使用して分析します。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 5e239753928f5c994245025c8b5d2aee3eee6091
workflow-type: tm+mt
source-wordcount: '3020'
ht-degree: 99%

---

# Journey Optimizerの統合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/get-started/get-started) は、接続され、コンテキストに応じて、パーソナライズされたエクスペリエンスを提供するのに役立ちます。カスタマージャーニーで次のステップに顧客を表示するのに役立ちます。

Journey Optimizer で生成されたデータを設定して、Customer Journey Analytics でアドバンス分析を実行できます。この統合は、自動的に設定できます。必要に応じて、接続またはデータビューで使用できるデータセット、ディメンションまたは指標に対して追加の手動カスタマイズを行うことができます。

## Journey Optimizer 統合の自動設定

Journey Optimizer では、レポートエンジンとして Customer Journey Analytics の使用をサポートしています。Journey Optimizer ドキュメントの[新しいレポートインターフェイスの基本を学ぶ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channel-report/report-gs-cja)を参照してください。

Journey Optimizer の Customer Journey Analytics レポートを有効にすると、特定のサンドボックスに対して[接続](/help/connections/overview.md)と[データビュー](/help/data-views/data-views.md)が自動的に作成されます。

### 接続

接続の名前は **[!UICONTROL AJO が有効な接続（*サンドボックス名*）]**&#x200B;で、設定とデータセットには次の標準の値があります。

| **接続設定** | 値 |
|---|---| 
| [!UICONTROL 接続名] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL 接続の説明] | [!UICONTROL *接続の説明をここに入力*] |
| [!UICONTROL タグ] | [!UICONTROL *タグを選択*] |


| **データ設定** | 値 |
|---|---| 
| [!UICONTROL 周期的なデータ時間枠を有効にする] | 有効。[!UICONTROL 選択した月数] `13`。 |
| [!UICONTROL サンドボックス] | [!UICONTROL *サンドボックスの名前*]（無効。この設定は変更できません）。 |
| [!UICONTROL 毎日のイベントの平均数] | 100 万未満（無効。この設定は変更できません）。 |


| データセット名 | スキーマ | データセットタイプ | データソースタイプ | ユーザー ID | キー | 一致するキー | 新しいデータを読み込む | データをバックフィル |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO エンティティデータセット] | [!UICONTROL AJO エンティティレコードスキーマ] | [!UICONTROL ルックアップ] | [!UICONTROL その他] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![緑のステータス](assets/../../connections/assets/status-green.svg) オン | ![グレーのステータス](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL ジャーニーステップイベント] | [!UICONTROL Journey Orchestration のジャーニーステップイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![緑のステータス](assets/../../connections/assets/status-green.svg) オン | ![グレーのステータス](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL AJO メールトラッキングエクスペリエンスイベントデータセット] | [!UICONTROL AJO メールトラッキングエクスペリエンスイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![緑のステータス](assets/../../connections/assets/status-green.svg) オン | ![グレーのステータス](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL AJO メッセージフィードバックイベントデータセット] | [!UICONTROL AJO メッセージフィードバックイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![緑のステータス](assets/../../connections/assets/status-green.svg) オン | ![グレーのステータス](assets/../../connections/assets/status-gray.svg) オフ |
| [!UICONTROL AJO プッシュトラッキングエクスペリエンスイベントデータセット] | [!UICONTROL AJO プッシュトラッキングエクスペリエンスイベントスキーマ] | [!UICONTROL イベント] | [!UICONTROL その他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![緑のステータス](assets/../../connections/assets/status-green.svg) オン | ![グレーのステータス](assets/../../connections/assets/status-gray.svg) オフ |


### データビュー

データビューの名前は **AJO が有効なデータビュー（*サンドボックス名*）**&#x200B;です。

- 「**[!UICONTROL 設定]**」タブでは、次の値が標準で設定されています。

  | 設定 | 値 |
  |---|---|
  | [!UICONTROL 接続] | AJO が有効な接続（*サンドボックス名*） |
  | [!UICONTROL 名前] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL 外部 ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_`（名前から派生） |
  | [!UICONTROL 説明] | `undefined` |

  {style="table-layout:fixed"}

  | 互換性 | 値 |
  |---|---|
  | [!UICONTROL Adobe Journey Optimizer のデフォルトのデータビューとして設定] | 有効（デフォルト）。<br/><br/>この設定オプションを使用すると、手動設定を行わなくても、Journey Optimizer で使用するデータビューを指定できます。この設定オプションを有効にする方法（デフォルトで有効になっていない場合）について詳しくは、[データビューの作成または編集](/help/data-views/create-dataview.md)の[互換性](/help/data-views/create-dataview.md#compatibility)の節を参照してください。<br/><br/>オプションを無効にすると、デフォルトのデータビューの変更を続行するかどうかを尋ねるダイアログが表示されます。「**[!UICONTROL 続行]**」を選択した場合は、デフォルトのデータビューとして別のデータビューを選択する必要があります。「**[!UICONTROL 確認]**」を選択して選択内容を確定します。デフォルトのデータビューの変更をキャンセルするには、「**[!UICONTROL キャンセル]**」を選択します。 |

  | コンテナ | 値 |
  |---|---|
  | [!UICONTROL 人物コンテナ名] | `Person` |
  | [!UICONTROL セッションコンテナ名] | `Session` |
  | [!UICONTROL イベントコンテナ名] | `Event` |

  | カレンダー | 値 |
  |---|---|
  | [!UICONTROL タイムゾーン] | 自身の地域に応じたタイムゾーン |
  | [!UICONTROL カレンダータイプ] | グレゴリオ暦 |
  | [!UICONTROL 年の最初の月] | 1月 |
  | [!UICONTROL 週の最初の日] | 日曜日 |


- 「**コンポーネント**」タブで、次の操作を行います。
   - 名前に[!UICONTROL （AJO）]が付加されたすべての指標とディメンションは、この自動設定の一部として自動的に追加されます。
   - 自動的に追加された指標やディメンションの一部は、派生フィールドに基づいています。これらの派生フィールドは、この統合用に特別に作成されます。例えば、[!UICONTROL ランディングページクリック数（AJO）]という指標は、「[!UICONTROL ランディングページクリック数]」派生フィールドに基づいています。
   - 一部の指標またはディメンションには、追加の設定があります。例えば、[!UICONTROL スパム報告件数（AJO）]には、[!UICONTROL 形式]と[!UICONTROL 値を含める／除外]の設定が適用されています。
   - 自動的に追加されたすべての指標とディメンションには、`:`*`name_of_metric_or_dimension`*という名前のコンテキストラベルが付きます。例えば、[!UICONTROL ランディングページクリック数（AJO）]という指標には、コンテキストラベル `:Landing page clicks (AJO)` が付きます。

- 「**[!UICONTROL 設定]**」タブでは、特定の設定値は適用されません

>[!IMPORTANT]
>
>接続とデータビューに対して自動設定された値を変更すると、自動設定された Customer Journey Analytics 統合に依存し、使用している Journey Optimizer レポートに影響します。


## Journey Optimizer で使用するデータビューの手動設定

次の節では、Journey Optimizer で生成されたデータを手動で使用して、Customer Journey Analytics でアドバンス分析を実行する方法について説明します。この手動設定は、[自動設定オプション](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)がニーズに対して不十分な場合にのみ必要です。

### Journey Optimizer から Experience Platform にデータを送信

Adobe Experience Platform は、中央のデータソースとして機能し、Journey Optimizer と Customer Journey Analytics の間をリンクします。Journey Optimizer データを Experience Platform にデータセットとして送信する手順については、Journey Optimizer ユーザーガイドの[データセットの基本を学ぶ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/data-management/datasets/get-started-datasets)を参照してください。

### 接続の作成

Journey Optimizer データが Adobe Experience Platform に入ったら、Journey Optimizer データセットに基づいて[接続を作成](/help/connections/create-connection.md)できます。または、既存の接続に Journey Optimizer データセットを追加できます。

次のデータセットを選択して設定します。

| データセット | データセットタイプ | 接続設定 | 説明 |
| --- | --- | --- | --- |
| AJO メッセージフィードバックイベントデータセット | イベント | ユーザー ID：`IdentityMap` | メッセージ配信イベント（[!UICONTROL 送信数]や[!UICONTROL バウンス数]など）が含まれています。 |
| AJO メールトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID：`IdentityMap` | メールトラッキングイベント（[!UICONTROL 開封数]、[!UICONTROL クリック数]、[!UICONTROL 登録解除数]など）が含まれています。 |
| AJO プッシュトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID：`IdentityMap` | プッシュトラッキングイベント（[!UICONTROL アプリの起動回数]など）が含まれています。 |
| ジャーニーステップイベント | イベント | ユーザー ID：`_experience.journeyOrchestration.`<br>`stepEvents.profileID` | ジャーニーの各ノードに参加したプロファイルを示すイベントが含まれています。 |
| AJO エンティティデータセット | ルックアップ | キー：`_id`<br>一致するキー：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | すべての Journey Optimizer イベントデータにジャーニーとキャンペーンメタデータを関連付ける分類が含まれています。 |

{style="table-layout:auto"}


### データビューの設定

接続を作成したら、1 つ以上の[データビュー](/help/data-views/create-dataview.md)を作成して、Customer Journey Analytics で使用できる目的のディメンションと指標を設定できます。

>[!NOTE]
>
>Journey Optimizer と Customer Journey Analytics の間のデータの不一致は通常、1～2％未満です。過去 2 時間以内に収集されたデータについては、より大きな不一致が生じる可能性があります。処理時間に関わる不一致を軽減するために、当日を除く日付範囲を使用します。


#### ディメンションの設定

データビューで次のディメンションを作成すると、Journey Optimizer の同様のディメンションとほぼ同等にすることができます。ディメンションのカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| ディメンション | 説明 | データセット | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- | --- | --- |
| アクション実行エラー（AJO） | ジャーニーの実行時にアクションを実行できないエラー条件。 | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | コンポーネントタイプ：ディメンション |
| アクションラベル（AJO） | エンドユーザーが操作した要素の顧客が生成した表示名。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositionAction.label` | コンポーネントタイプ：ディメンション |
| バッチ ID（AJO） | スケジュールされたジャーニーまたはキャンペーンアクションの新しい各バッチインスタンスの呼び出し時に作成される GUID。例えば、スケジュールされたジャーニーまたはキャンペーンアクションが午前 8:00 と午前 10:00 に実行される場合、2 つの異なるバッチインスタンス ID が存在します。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | コンポーネントタイプ：ディメンション |
| バッチインスタンスのタイムスタンプ（AJO) | バッチインスタンスのタイムスタンプ | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：ディメンション（派生フィールド） |
| キャンペーン ID（AJO） | キャンペーンの ID。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | コンポーネントタイプ：ディメンション |
| キャンペーン名（AJO） | キャンペーンの名前。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | コンポーネントタイプ：ディメンション |
| キャンペーンバージョン ID（AJO） | キャンペーンのバージョン ID。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | コンポーネントタイプ：ディメンション |
| チャネル（AJO） | このデータを相関させる必要があるチャネル。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | コンポーネントタイプ：ディメンション |
| 相関 ID（AJO） | 相関 ID。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | コンポーネントタイプ：ディメンション |
| 決定ポリシー ID（AJO） | この提案に含める項目を決定する際に使用する決定ポリシーの ID。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：ディメンション（派生フィールド） |
| メール受信者ドメイン（AJO） | メールアドレスのドメイン | AJO プッシュトラッキングエクスペリエンスイベントデータセット、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | コンポーネントタイプ：ディメンション |
| メールの件名（AJO） | メールの件名（パーソナライズされていない） | AJO エンティティデータセット | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | コンポーネントタイプ：ディメンション |
| イベント ID（AJO） | 時系列イベントの一意の ID。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_id` | コンポーネントタイプ：ディメンション（派生フィールド） |
| 終了条件 ID（AJO） | ジャーニーを終了するかどうかを決定する際に使用される終了条件の ID。 | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | コンポーネントタイプ：ディメンション |
| 終了条件名（AJO） | 終了条件の名前。 | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | コンポーネントタイプ：ディメンション |
| 実験 ID（AJO） | 実験の ID。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | コンポーネントタイプ：ディメンション |
| 実験名（AJO） | 実験の名前。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | コンポーネントタイプ：ディメンションコンテキストラベル：実験 |
| 取得エラー (AJO) | ジャーニーの実行時に取得を実行できないエラー条件。 | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | コンポーネントタイプ：ディメンション |
| 最適化された送信時間です (AJO) | メッセージ実行の最適化された送信時間です | AJO プッシュトラッキングエクスペリエンスイベントデータセット、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | コンポーネントタイプ：ディメンション |
| テストジャーニーです (AJO) | テストジャーニー実行のイベント部分です | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | コンポーネントタイプ：ディメンション |
| テストメッセージです (AJO) | テスト実行として送信されたメッセージです | AJO プッシュトラッキングエクスペリエンスイベントデータセット、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | コンポーネントタイプ：ディメンション |
| 項目 ID (AJO) | 項目の ID。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositions.items.id` | コンポーネントタイプ：ディメンション |
| 項目名 (AJO) | 項目の名前 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositions.items.name` | コンポーネントタイプ：ディメンション |
| ジャーニーアクション ID | MessageExecution がトリガーされるジャーニーアクション ID。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | コンポーネントタイプ：ディメンション |
| ジャーニーアクションノード名 (AJO) | ジャーニーのアクションノード名。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット, ジャーニーステップイベント, AJO メッセージフィードバックイベントデータセット, AJO メールトラッキングエクスペリエンスイベントデータセット, AJO エンティティデータセット | 派生フィールド | コンポーネントタイプ：ディメンション（派生フィールド） |
| ジャーニーイベントノード名 (AJO) | この値は、ジャーニーでセグメントまたは外部イベントが発生するたびに設定されます。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット, ジャーニーステップイベント, AJO メッセージフィードバックイベントデータセット, AJO メールトラッキングエクスペリエンスイベントデータセット, AJO エンティティデータセット | 派生フィールド | コンポーネントタイプ：ディメンション（派生フィールド） |
| ジャーニー ID (AJO) | ジャーニーの ID。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | コンポーネントタイプ：ディメンション |
| ジャーニー名 (AJO) | ジャーニーの名前。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | コンポーネントタイプ：ディメンション |
| ジャーニー名とバージョン (AJO) | ジャーニーの名前とバージョン。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | コンポーネントタイプ：ディメンション |
| ジャーニーバージョン ID (AJO) | ジャーニーのバージョン ID。 | AJO エンティティデータセット | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | コンポーネントタイプ：ディメンション |
| ランディングページ ID (AJO) | ランディングページの一意の ID | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | コンポーネントタイプ：ディメンション |
| ランディングページソース (AJO) | ランディングページのソース。 | AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：ディメンション（派生フィールド） |
| リンク URL (AJO) | ユーザーがクリックした URL。 | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | コンポーネントタイプ：ディメンション |

{style="table-layout:auto"}

#### 指標の設定

データビューで次の指標を作成すると、Journey Optimizer の同様の指標とほぼ同等にすることができます。指標のカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| 指標 | 説明 | データセット | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- | --- | --- |
| アプリのインストール数（AJO） | アプリのインストール数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット | `application.installs.value` | コンポーネントタイプ：指標 |
| アプリの起動回数 (AJO) | モバイルアプリが起動された回数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット | `application.launches.value` | コンポーネントタイプ：指標 |
| アウトバウンドチャネルのバウンス (AJO) | アウトバウンドチャネルでのバウンスされたメッセージの合計数 | AJO メッセージフィードバックイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標 |
| クリック数 (AJO) | すべてのチャネルでのクリックの合計数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット, ジャーニーステップイベント, AJO メールトラッキングエクスペリエンスイベントデータセット, AJO メッセージフィードバックイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| フォールバックオファー数 (AJO) | フォールバックオファー数。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | コンポーネントタイプ：指標 |
| オファー数 (AJO) | オファー数。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | ` _experience.decisioning.`<br/>`propositions.items.id` | コンポーネントタイプ：指標 |
| 重複排除の指標 (AJO) | 重複排除の指標 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_id` | コンポーネントタイプ：指標 |
| 配信済み (AJO) | 配信されたメッセージの合計数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| 却下済み (AJO) | エンドユーザーが選択して閉じたアクションに関係なく、Adobe SDK によってアプリ内メッセージが閉じられるたびにカウントします。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | コンポーネントタイプ：指標 |
| 表示数 (AJO) | このカウントには、AJO メッセージ数が表示されます。これには、メールの開封数、web 表示数、アプリ内表示数が含まれます。モバイルプラットフォームは SMS やプッシュメッセージの表示数を報告しないのでカウントされません。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット, ジャーニーステップイベント, AJO メールトラッキングエクスペリエンスイベントデータセット, AJO メッセージフィードバックイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| メール開封数（AJO） | メール開封の合計数 | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | コンポーネントタイプ：指標 |
| インバウンドクリック数（AJO） | インバウンドチャネルでのクリックの合計数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositionEventType.interact` | コンポーネントタイプ：指標 |
| インバウンド却下数（AJO） | インバウンドチャネルでの却下の合計数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | コンポーネントタイプ：指標 |
| インバウントインプレッション数（AJO） | インバウンドチャネルでのインプレッションの合計数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositionEventType.display` | コンポーネントタイプ：指標 |
| ジャーニーの終了 (AJO) | 現在のステップにより、ジャーニーのインスタンスが終了した場合は True。特定のプロファイルのジャーニーの最後のステップが正常に実行された場合。 | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | コンポーネントタイプ：指標 |
| ジャーニーエントリ (AJO) | ステップイベントがプロファイルのジャーニーエントリイベントであった場合は True。 | ジャーニーステップイベント | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| ジャーニーの出口 (AJO) | 現在のステップにより、ジャーニーのインスタンスが終了した場合は True。つまり、特定のプロファイルのジャーニーの最後のステップが正常に実行されたことになります。 | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | コンポーネントタイプ：指標 |
| ジャーニーの失敗 (AJO) | 実行を終了したステップの現在の状態を示します。可能な値 : `Transitions` (次のステップはイベントトランジション時に発生します)、`EndStep` (このジャーニーインスタンスの最後のステップが実行されました)、`Error` (このステップでエラー状態が発生し、現在のジャーニーインスタンスが終了しました)、`TimedOut` (取得またはアクションのタイムアウトにより、現在のステップが終了しました)。 | ジャーニーステップイベント | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | コンポーネントタイプ：指標 |
| ランディングページクリック数 (AJO) | ランディングページのクリックの合計数 | AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| ランディングページコンバージョン数 (AJO) | ランディングページのコンバージョンの合計数。 | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | コンポーネントタイプ：指標 |
| ランディングページビュー数 (AJO) | ランディングページのビューの合計数。 | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | コンポーネントタイプ：指標 |
| ノードエントリ (AJO) | ステップイベントがプロファイルのノードエントリイベントであった場合は True。 | ジャーニーステップイベント | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| アウトバウンドクリック数（AJO） | アウトバウンドチャネルでのクリックの合計数 | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | コンポーネントタイプ：指標 |
| アウトバウンドエラー数 (AJO) | アウトバウンドチャネル間でエラーのあるメッセージの合計数 | AJO メッセージフィードバックイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標 |
| アウトバウンド除外数 (AJO) | アウトバウンドチャネルでの除外イベントの合計数 | AJO メッセージフィードバックイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標 |
| アウトバウンド送信数（AJO） | アウトバウンドチャネルでのメッセージ送信の合計数 | AJO メッセージフィードバックイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | コンポーネントタイプ：指標 |
| プッシュカスタムアクション (AJO) | プッシュインタラクションのカスタムアクションの合計数。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `eventType` | コンポーネントタイプ：指標 |
| プッシュインタラクション（AJO） | 直接プッシュメッセージのインタラクションによりモバイルアプリが起動された回数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット | `application.launches.value` | コンポーネントタイプ：指標 |
| 送信数 (AJO) | すべてのチャネルでのメッセージ送信の合計数 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| SMS インバウンドメッセージ（AJO） | SMS インバウンド返信。例えば、停止、開始、購読など。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | コンポーネントタイプ：指標 |
| スパム報告件数（AJO） | スパム報告の合計件数 | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | コンポーネントタイプ：指標 |
| 製品リスト追加数（AJO） | サブスクリプションリストへの追加の合計数。 | AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| サブスクリプションリストの削除数（AJO） | サブスクリプションリストからの削除の合計数。 | AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| ターゲット（AJO） | 提案回数のこのカウントは、ユーザーに対してターゲットが絞り込まれていました。これは、ユーザーに対する表示の提案が考慮された回数です。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | 派生フィールド | コンポーネントタイプ：指標（派生フィールド） |
| トリガー済み（AJO） | 提案が Adobe SDK によって表示されるように選択されました。その他の要因により、実際には表示されない場合があります。 | AJO プッシュトラッキングエクスペリエンスイベントデータセット、ジャーニーステップイベント、AJO メッセージフィードバックイベントデータセット、AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.decisioning.`<br/>`propositionEventType.trigger` | コンポーネントタイプ：指標 |
| 実験のユニーク訪問者数（AJO） | 実験のユニーク訪問者数 | AJO エンティティデータセット | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | コンポーネントタイプ：指標 |
| 登録解除数（AJO） | 登録解除の合計数 | AJO メールトラッキングエクスペリエンスイベントデータセット | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | コンポーネントタイプ：指標 |

{style="table-layout:auto"}
