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
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# データフィードとAnalysis Workspace間のデータの不一致を把握する

{{release-limited-testing}}

データフィードの書き出し内のデータが、Analysis Workspaceのデータと完全に一致するとは限りません。 このページの情報は、主な理由のいくつかを説明しています。

これらの違いの一部は、Workspace データが集計されるため、Workspace レポートだけでは確認しにくいWorkspace ビヘイビアーに起因します。 データフィードはイベントレベルのデータを提供するため、データフィードの出力とWorkspaceレポートを比較することで、これらの行動が明らかになります。

## 処理ウィンドウ（データフィード）とレポートウィンドウ（Analysis Workspace）の比較 {#processing-window}

各データフィード配信では、30日間のローリング処理ウィンドウを使用します。 処理ウィンドウには、データフィード配信のイベントを分類するために必要な履歴コンテキストが表示されます。 例を含む処理ウィンドウについて詳しくは、[処理ウィンドウについて](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window)を参照してください。

この意味で、処理ウィンドウはAnalysis Workspaceのレポートウィンドウ（レポート用に選択した日付範囲）と似ています。 しかし、両者には重要な違いがあります。

| 主な違い | レポートウィンドウ（Analysis Workspace） | 処理ウィンドウ（データフィード） |
|---------|---------|----------|
| **レポートまたはフィードに含まれるイベントの**<br/> レポートまでの期間 | レポート ウィンドウが開始する暦月の最初の日から開始し、レポート ウィンドウの最後で終了します。<p>例えば、レポート期間が10月6日から11月5日のレポートには、10月1日から10月5日までのイベントも含まれます。 Workspaceのデータは集約されているため、その他のイベントを確認するのは困難な場合があります。</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | 処理ウィンドウと同じではありません。 <p>レポートする時間枠は頻度ウィンドウで、処理ウィンドウの最後に1時間または1日を設定できます。</p> |
| **データ境界**<br/> ウィンドウ外のデータがレポートまたはフィードに含まれているか、または影響を与えているか | 柔軟な<p>レポート期間が開始される暦月の初日からのイベントは、レポート期間よりも前に発生した場合でも、Workspace レポートに含まれます。 詳しくは、上記の&#x200B;**に関するレポートの期間**&#x200B;を参照してください。</p><p>レポートウィンドウ以外のイベントは、次のいずれかの要因を通じてWorkspace レポートのデータに影響を与える可能性があります。</p><ul><li>**Dimensionの永続性**: セッション、カスタム時間、または指標[有効期限](/help/data-views/component-settings/persistence.md#expiration-settings)を使用する場合、レポート ウィンドウを超えて永続化できます。</li><li>**セグメントの選定**: セグメントは、デフォルトでレポートウィンドウを超えて拡張できます。<p>ユーザーは、セグメントを作成するときに、レポートウィンドウにセグメントを制限することができます。 さらに、セグメントの選定では、レポートウィンドウが開始される暦月の初日からのイベントが考慮されます。</p></li><li>**セッション計算**: セッションはレポートウィンドウを超えて拡張できます。 </li><li>**派生フィールド変換**: コンテナを参照する派生フィールド関数は、レポートウィンドウを使用します。<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | 固定<p>頻度ウィンドウ内のイベントのみがデータフィードに含まれます。 詳しくは、上記の&#x200B;**に関するレポートの期間**&#x200B;を参照してください。</p><p>頻度ウィンドウの外側にあるイベントのうち、処理ウィンドウ内にあるイベントは、データフィード内のデータに影響を与える可能性があります。 通常、処理ウィンドウより前に発生するイベントは処理できません。 処理ウィンドウでは、次の要素が制限されます。</p><ul><li>**Dimensionの永続性**: セッション、人物レポートウィンドウ、または指標[有効期限](/help/data-views/component-settings/persistence.md#expiration-settings)を使用する場合、処理ウィンドウを超えて永続化できません。 Workspaceとは異なり、ルックバックは月の最初の日には適用されません。 Workspaceと同じカスタム時間[有効期限](/help/data-views/component-settings/persistence.md#expiration-settings)を使用する場合、処理期間（最大90日）を超えて保持できます。 Workspaceとデータフィードの両方で、カスタム時間のルックバックは月の最初の日には及びません。<p>**メモ：**&#x200B;現在、カスタム時間の有効期限も処理ウィンドウに制限されています。 処理ウィンドウを超えて拡張するカスタム時間のサポートは、近日リリース予定です。</p></li><li>**セグメントの選定**：常に処理ウィンドウに限定されます。 Workspaceとは異なり、月の最初の日には適用されません。</li><li>**セッション計算**：常に処理ウィンドウに限定されます。</li><li>**派生フィールド変換**: コンテナを参照する派生フィールド関数は、データフィードの書き出しで処理ウィンドウを使用します。</li></ul> |

>[!BEGINSHADEBOX]

**例**

次の例は、レポートウィンドウと処理ウィンドウの違いが、Workspace レポートとデータフィードの配信の間にデータの相違が生じる可能性があることを示しています。

* **レポートの期間**: ユーザーには、ディメンション値を設定する10月1日のイベントがあり、10月後半にはさらに多くのイベントがあります。 10月6日に始まるレポート期間を含むWorkspace レポートには、10月1日のイベントが含まれます。これは、Workspaceには月の初日からのイベントが含まれるためです。 10月1日に設定した値は、レポートウィンドウ内のユーザーのイベントにも保持できます。 10月6日に始まる処理ウィンドウを持つデータフィード配信では、10月1日のイベントは考慮されないため、設定した値は配信内のユーザーのイベントに保持されません。

* **セグメントの選定**: 45日前に人物コンテナを持つセグメントに選定され、本日イベントが発生したユーザー。 30日間のレポートウィンドウを含むWorkspace レポートには、デフォルトでセグメントがレポートウィンドウを超えて拡張する可能性があるため、ユーザーのイベントが含まれます。 今日のデータフィード配信には、セグメントの選定は30日間の処理ウィンドウに制限されているため、イベントは含まれていません。

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## ステッチリプレイ

ステッチリプレイが実行されるたびに、過去のID データが過去にさかのぼって更新されます。

データフィードとAnalysis Workspaceでは、ステッチリプレイの扱いが次のように異なります。

* **データフィード**：書き出し時にのみステッチ IDを反映します。 再生結果は、書き出したファイルに過去にさかのぼって適用されません。

* **Analysis Workspace**：最新のステッチ済みデータを表示します。このデータは、リプレイが実行されるたびに過去にさかのぼって更新されます。 過去のデータはリプレイごとに変更されるため、Workspaceは常に最新のID解決を反映します。

## 遅刻イベント

データフィードでは、データフィードの書き出しウィンドウが閉じた後にイベントが発生する可能性があります。

データフィードとAnalysis Workspaceの機能は、過去の出来事ごとに次のように異なります。

* **データフィード**: イベントのタイムスタンプに基づいて、特定の時間枠（各配信の時間または日）内にデータを書き出します。

  各配信を処理する前に、Customer Journey Analyticsは、選択した[処理遅延](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay)を待機します。 処理遅延の間に発生したイベントは、配信に含まれます。 処理開始後に到着したイベントは、データフィードファイルに含まれません。

* **Analysis Workspace**: レポート時にデータを処理するので、イベントは、いつ受信したかに関係なくレポートに含まれます。

## データバッチ

データが長期間にわたるバッチで送信されることがあります。

データフィードとAnalysis Workspaceは、バッチ処理されたデータに関して次のように異なる機能を果たします。

* **データフィード**：元のタイムスタンプに基づいて、バッチ化されたデータを各日または時間に配信します。 たとえば、30日間のデータを含むバッチは30日間の書き出しに分散されるため、1回の書き出しでは小さなスライスのみが表示されます。

* **Analysis Workspace**: バッチに含まれる時間範囲に関係なく、完全に処理されるとすぐに、すべてのデータをバッチに表示します。

