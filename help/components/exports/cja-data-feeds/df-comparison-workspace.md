---
description: Customer Journey AnalyticsとAdobe Analyticsのデータフィード機能の比較方法について説明します
keywords: クリックストリーム;データフィード;データフィード;データフィード
title: Customer Journey AnalyticsとAdobe Analyticsのデータフィード機能の比較
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 03beb4bd52769a5428ca084beacefd8996d4c810
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%
---
# データフィードとAnalysis Workspace間のデータの不一致を把握する

{{release-limited-testing}}

データフィードの書き出し内のデータが、Analysis Workspaceのデータと完全に一致するとは限りません。 このページの情報は、主な理由のいくつかを説明しています。

## 処理ウィンドウ（データフィード）とレポートウィンドウ（Analysis Workspace）の比較 {#processing-window}

各データフィード配信では、30日間のローリング処理ウィンドウを使用します。 処理ウィンドウには、データフィード配信のイベントを分類するために必要な履歴コンテキストが表示されます。 例を含む処理ウィンドウについて詳しくは、[処理ウィンドウについて](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window)を参照してください。

この意味で、処理ウィンドウはAnalysis Workspaceのレポートウィンドウ（レポート用に選択した日付範囲）と似ています。 しかし、両者には重要な違いがあります。

| 主な違い | レポートウィンドウ（Analysis Workspace） | 処理ウィンドウ（データフィード） |
|---------|---------|----------|
| **データ境界**<br/> データがレポートまたはフィードに含まれているかどうか | 柔軟な<p>次のいずれかの要因によってイベントが影響を受ける場合、レポートウィンドウ外のイベントは、引き続きWorkspace レポートに含めることができます。</p><ul><li>**Dimensionの永続性**: セッション、カスタム時間、または指標[有効期限](/help/data-views/component-settings/persistence.md#expiration-settings)を使用する場合、レポート ウィンドウを超えて永続化できます。 人物レポートウィンドウ [有効期限](/help/data-views/component-settings/persistence.md#expiration-settings)を使用する場合は、レポートウィンドウと同じです。 データは集約されます。</li><li>**セグメントの選定**: セグメントは、デフォルトでレポートウィンドウを超えて拡張できます。<p>ユーザーは、セグメントを作成するときに、レポート ウィンドウにセグメントを制限することができます。<!--add link to new docs--></p></li><li>**セッション計算**: セッションはレポートウィンドウを超えて拡張できます。 </li><li>**派生フィールド変換**</li></ul> | 固定<p>通常、処理ウィンドウ外に発生するイベントは、データフィードには影響しません。 処理ウィンドウは、次の要素に適用されます。</p><ul><li>**Dimensionの永続性**:Workspaceと同じカスタム時間[有効期限](/help/data-views/component-settings/persistence.md#expiration-settings)を使用する場合、処理期間（最大90日）を超えて永続化できます。 ユーザー報告ウィンドウ [有効期限](/help/data-views/component-settings/persistence.md#expiration-settings)を使用する場合、処理ウィンドウを超えて保持できません。 データは集約されません。</li><li>**セグメントの選定**：常に処理ウィンドウに限定されます。</li><li>**セッション計算**：常に処理ウィンドウに限定されます。</li><li>**派生フィールド変換**: コンテナを参照する派生フィールド関数は、データフィードの書き出しで処理ウィンドウを使用します。</li></ul> |
| **レポートまたはフィードに含まれるイベントの**<br/> レポートまでの期間 | レポートウィンドウと同じです。 | 処理ウィンドウと同じではありません。 <p>レポートする時間枠は頻度ウィンドウで、処理ウィンドウの最後に1時間または1日を設定できます。</p> |

>[!BEGINSHADEBOX]

**例**

次の例は、レポートウィンドウと処理ウィンドウの違いが、Workspace レポートとデータフィードの配信の間にデータの相違が生じる可能性があることを示しています。

45日前に個人コンテナを持つセグメントに適格であったユーザーが、本日イベントを開催しました。 30日間のレポートウィンドウを含むWorkspace レポートには、デフォルトでセグメントがレポートウィンドウを超えて拡張する可能性があるため、ユーザーのイベントが含まれます。 今日のデータフィード配信には、セグメントの選定は30日間の処理ウィンドウに制限されているため、イベントは含まれていません。

<!-- update the following graphic -->

![&#x200B; ワークスペースとデータフィードのデータの違い](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## ステッチリプレイ

ステッチリプレイが実行されるたびに、過去のID データが過去にさかのぼって更新されます。

データフィードとAnalysis Workspaceでは、ステッチリプレイの扱いが次のように異なります。

* **データフィード**：書き出し時にのみステッチ IDを反映します。 再生結果は、書き出したファイルに過去にさかのぼって適用されません。

* **Analysis Workspace**：最新のステッチ済みデータを表示します。このデータは、リプレイが実行されるたびに過去にさかのぼって更新されます。 過去のデータはリプレイごとに変更されるため、Workspaceは常に最新のID解決を反映します。

## 遅刻イベント

データフィードでは、データフィードの書き出しウィンドウが閉じた後にイベントが発生する可能性があります。

データフィードとAnalysis Workspaceの機能は、過去の出来事ごとに次のように異なります。

* **データフィード**: イベントを受信したタイミングに基づいて、データを固定時間内に書き出します。

  ウィンドウが閉じた後に到着したイベントは、書き出しに含まれない可能性があります。 これは、選択した[処理遅延](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay)の影響を受けます。

* **Analysis Workspace**: レポート時にデータを処理するので、イベントは、いつ受信したかに関係なくレポートに含まれます。

## データバッチ

データが長期間にわたるバッチで送信されることがあります。

データフィードとAnalysis Workspaceは、バッチ処理されたデータに関して次のように異なる機能を果たします。

* **データフィード**：元のタイムスタンプに基づいて、バッチ化されたデータを各日または時間に配信します。 たとえば、30日間のデータを含むバッチは30日間の書き出しに分散されるため、1回の書き出しでは小さなスライスのみが表示されます。

* **Analysis Workspace**: バッチに含まれる時間範囲に関係なく、完全に処理されるとすぐに、すべてのデータをバッチに表示します。

