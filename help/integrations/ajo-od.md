---
title: Adobe Journey Optimizer 意思決定管理と Adobe Customer Journey Analytics の統合
description: Adobe Journey Optimizer 意思決定管理で生成されたデータを取り込み、Customer Journey Analytics 内で Analysis Workspace を使用して分析します。
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '710'
ht-degree: 100%

---

# 意思決定管理と Adobe Customer Journey Analytics の統合


Adobe Journey Optimizer [意思決定管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=ja)では、マーケティングオファーの一元化されたライブラリと、Adobe Experience Platform が作成するリッチなリアルタイムプロファイルにルールと制約を適用する意思決定エンジンを使用して、的確なオファーを適切なタイミングで顧客に送信します。

意思決定管理は、Adobe Journey Optimizer の一部であり、Adobe Journey Optimizer と統合されています。また、豊富な [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=ja) サポートを使用して、Adobe Journey Optimizer で定義されたジャーニーやキャンペーンとは独立して使用することもできます。

意思決定管理で生成されたデータを読み込み、Customer Journey Analytics でアドバンス分析を実行するには、次の手順に従ってください。

## 意思決定管理から Adobe Experience Platform にデータを送信

Adobe Experience Platform は、中央のデータソースとして機能し、意思決定管理と Customer Journey Analytics の間をリンクします。意思決定管理からのデータは、Experience Platform に&#x200B;**自動的に**&#x200B;または&#x200B;**明示的に送信されたエクスペリエンスイベント**（インプレッション数やクリック数など）の一部として収集されます。詳しくは、[データ収集の開始](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=ja)を参照してください。

## 接続の作成

意思決定管理データが Adobe Experience Platform に入ったら、意思決定管理データセットに基づいて[接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja)を作成できます。または、意思決定管理データセットを既存の接続に追加できます。

次のデータセットを選択して設定します。

| データセット | データセットタイプ | 接続設定 | 説明 |
| --- | --- | --- | --- |
| ODE DecisonEvents - _サンドボックス_&#x200B;決定 | イベント | ユーザー ID：`IdentityMap` | 意思決定管理の決定イベント用に自動生成されたデータが含まれます。_サンドボックス_&#x200B;は、特定のサンドボックス名を指します。 |
| Adobe Journey Optimizer メッセージフィードバックイベントのデータセット | イベント | ユーザー ID：`IdentityMap` | メッセージ配信イベントが含まれます。 |
| Adobe Journey Optimizer メールトラッキングエクスペリエンスイベントのデータセット | イベント | ユーザー ID：`IdentityMap` | メールトラッキングイベントが含まれます。 |
| Adobe Journey Optimizer プッシュトラッキングエクスペリエンスイベントのデータセット | イベント | ユーザー ID：`IdentityMap` | プッシュトラッキングイベントが含まれます。 |
| Adobe Journey Optimizer エンティティのデータセット | ルックアップ | キー：`_id`<br>一致するキー：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | すべての Adobe Journey Optimizer イベントデータにジャーニーとキャンペーンメタデータを関連付ける分類が含まれています。 |

{style="table-layout:auto"}

## データビューの作成

接続を作成したら、1 つ以上の[データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja)を作成して、Customer Journey Analytics で使用できる目的のディメンションと指標を設定できます。

>[!NOTE]
>
>Adobe Journey Optimizer と Customer Journey Analytics の間のデータの不一致は通常、1～2％未満です。過去 2 時間以内に収集されたデータについては、より大きな不一致が生じる可能性があります。処理時間に関わる不一致を軽減するために、当日を除く日付範囲を使用します。

### ディメンションの設定

データビューで次のディメンションを作成すると、意思決定管理の同様のディメンションとほぼ同等にすることができます。ディメンションのカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| ディメンション | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- |
| アクティビティ名 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | コンポーネントタイプ：ディメンション |
| コンテナ識別子 | `_experience.decisioning.containerID` | コンポーネントタイプ：ディメンション |
| 相関識別子 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | コンポーネントタイプ：ディメンション |
| 決定オプション名 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | コンポーネントタイプ：ディメンション |
| フォールバック決定オプション名 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | コンポーネントタイプ：ディメンション |
| プレースメント名 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | コンポーネントタイプ：ディメンション |

{style="table-layout:auto"}


### 指標の設定

データビューで次の指標を作成すると、意思決定管理の同様の指標とほぼ同等にすることができます。指標のカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| 指標 | 説明 | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- | --- |
| イベントタイプ（名前を変更して特定のイベントを参照する、`message.feedback` の場合 `Feedback` など）[1] | 特定のタイプのイベントの量 | `eventType` | コンポーネントタイプ：指標<br/>**[!UICONTROL 「値を含める／除外」を設定&#x200B;]**：オン<br/>**[!UICONTROL 一致]**：[!UICONTROL すべての条件を満たす場合]<br/>**[!UICONTROL 条件&#x200B;]**：**[!UICONTROL &#x200B;等しい&#x200B;]**`message.feedback` |
| 決定オプションスコア | 単一スコープのコンテキストにおける決定オプションの計算値。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | コンポーネントタイプ：指標 |
| フォールバック決定オプションのスコア | 単一スコープのコンテキストにおけるフォールバック決定オプションの計算値。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | コンポーネントタイプ：指標 |
| オファーの却下 | 他の直接のインタラクションなしで却下または拒否されたオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.display` | コンポーネントタイプ：指標 |
| オファーの表示 | プロファイルに表示されるオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.display` | コンポーネントタイプ：指標 |
| オファーの操作 | プロファイルに表示されるオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | コンポーネントタイプ：指標 |
| オファーの送信 | プロファイルに送信されたオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.send` | コンポーネントタイプ：指標 |
| オファーのトリガー | クライアント SDK によって表示されるように選択されたオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | コンポーネントタイプ：指標 |
| オファーの登録解除 | プロファイルによってリクエストされた今後表示されないオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | コンポーネントタイプ：指標 |

{style="table-layout:auto"}

[1] 使用可能な各種イベントタイプに対して複数の指標を定義できます。詳しくは、[値を含める／除外コンポーネント設定](/help/data-views/component-settings/include-exclude-values.md)を参照してください。
