---
title: Adobe Journey Optimizer Decision Management とCustomer Journey Analytics(CJA) の統合
description: Adobe Journey Optimizer Decision Management で生成されたデータを取り込み、Customer Journey Analytics内でAnalysis Workspaceを使用して分析します。
source-git-commit: 00a87f5f370310672ca37ab9df08350d14fc6a91
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 19%

---

# 決定管理とCustomer Journey Analyticsの統合


Adobe Journey Optimizer [決定管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) は、マーケティングオファーの一元化されたライブラリと、Adobe Experience Platformが作成するリッチなリアルタイムプロファイルにルールと制約を適用する決定エンジンを使用して、適切なタイミングで顧客に適切なオファーを送信しやすくします。

判定管理は、Adobe Journey Optimizer(AJO) の一部であり、統合されています。 また、AJO で定義されたジャーニーやキャンペーンとは独立して、豊富な [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) サポート。

次の手順を実行すると、決定管理で生成されたデータをインポートして、Customer Journey Analytics(CJA) での高度な分析を実行できます。

## 決定管理からAdobe Experience Platformへのデータの送信

Adobe Experience Platformは、中央のデータソースとして機能し、決定管理とCustomer Journey Analyticsの間のリンクを提供します。 決定管理からのデータは、Experience Platformで収集されます **自動** またはの一部として **明示的に送信されたエクスペリエンスイベント** （インプレッション数やクリック数など）。 詳しくは、 [データ収集の概要](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) を参照してください。

## 接続の作成

決定管理データがAdobe Experience Platformに取り込まれたら、 [接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja) 決定管理データセットに基づいて または、決定管理データセットを既存の接続に追加できます。

次のデータセットを選択して設定します。

| データセット | データセットタイプ | 接続設定 | 説明 |
| --- | --- | --- | --- |
| ODE DecisonEvents - _サンドボックス_ 判定 | イベント | ユーザー ID: `IdentityMap` | 決定管理の決定イベント用に自動生成されたデータが含まれます。 _サンドボックス_ は、特定のサンドボックス名を参照します。 |
| AJO メッセージフィードバックイベントデータセット | イベント | ユーザー ID: `IdentityMap` | メッセージ配信イベントを含みます。 |
| AJO メールトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID: `IdentityMap` | 電子メールトラッキングイベントが含まれます。 |
| AJO プッシュトラッキングエクスペリエンスイベントデータセット | イベント | ユーザー ID: `IdentityMap` | プッシュトラッキングイベントが含まれます。 |
| AJO エンティティデータセット | ルックアップ | キー： `_id`<br>一致するキー： `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | すべての AJO イベントデータにジャーニーとキャンペーンのメタデータを関連付ける分類が含まれます。 |

{style="table-layout:auto"}

## データレイヤーの作成

接続を作成した後、1 つ以上の [データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja) :CJA で使用できる目的のディメンションと指標を設定します。

>[!NOTE]
>
>AJO と CJA の間のデータの不一致は通常、1～2％未満です。過去 2 時間以内に収集されたデータについては、より大きな不一致が生じる可能性があります。処理時間に関わる不一致を軽減するために、当日を除く日付範囲を使用します。

### ディメンションの設定

データビューで次のディメンションを作成して、決定管理で類似のディメンションとほぼ同等にすることができます。 ディメンションのカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| ディメンション | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- |
| アクティビティ名 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | コンポーネントタイプ：ディメンション |
| コンテナ識別子 | `_experience.decisioning.containerID` | コンポーネントタイプ：ディメンション |
| 相関識別子 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | コンポーネントタイプ：ディメンション |
| 決定オプション名 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | コンポーネントタイプ：ディメンション |
| フォールバック判定オプション名 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | コンポーネントタイプ：ディメンション |
| プレースメント名 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | コンポーネントタイプ：ディメンション |

{style="table-layout:auto"}


### 指標の設定

データビューで次の指標を作成して、決定管理で類似の指標との近似的な同等性を実現できます。 指標のカスタマイズオプションについて詳しくは、データビューマネージャーの[コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

| 指標 | 説明 | スキーマ要素 | コンポーネント設定 |
| --- | --- | --- | --- |
| イベントタイプ（名前を変更して特定のイベントを参照する、など） `Feedback` 対象 `message.feedback`) [1] | 特定のタイプのイベントの量 | `eventType` | コンポーネントタイプ：指標<br/>**[!UICONTROL 次を含める値を設定&#x200B;]**:オン<br/>**[!UICONTROL 一致]**: [!UICONTROL すべての条件を満たす場合]<br/>**[!UICONTROL 条件&#x200B;]**:**[!UICONTROL &#x200B;次と等しい&#x200B;]**`message.feedback` |
| 決定オプションスコア | 単一のスコープのコンテキストにおける判定オプションの計算値。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | コンポーネントタイプ：指標 |
| フォールバック判定オプションのスコア | 単一のスコープのコンテキストにおけるフォールバック判定オプションの計算値。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | コンポーネントタイプ：指標 |
| 解除するオファー | 他の直接のインタラクションなしで却下または却下されたオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.display` | コンポーネントタイプ：指標 |
| オファーの表示 | プロファイルに表示されるオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.display` | コンポーネントタイプ：指標 |
| オファーの操作 | プロファイルに表示されるオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | コンポーネントタイプ：指標 |
| 送信するオファー | プロファイルに送信されたオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.send` | コンポーネントタイプ：指標 |
| オファートリガー | クライアント SDK によって表示されるように選択されたオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | コンポーネントタイプ：指標 |
| オファー配信停止 | プロファイルによってリクエストされた今後表示されないオファーの数。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | コンポーネントタイプ：指標 |

{style="table-layout:auto"}

[1] 使用可能な各種イベントタイプに対して複数の指標を定義できます。 詳しくは、 [「値を除外」コンポーネント設定を含める](/help/data-views/component-settings/include-exclude-values.md) を参照してください。
