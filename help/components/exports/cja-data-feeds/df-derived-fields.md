---
title: データフィードのデータ変換の適用
description: コンポーネント設定、派生フィールド、SQLを使用して、データフィードデータを変換する様々な方法について説明します。
hide: true
feature: Components
source-git-commit: 082927c1d511ba0831beba08aaaac0e2d0d9fbf6
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 5%
---
# データフィードにデータ変換を適用する

{{release-limited-testing}}

次のいずれかの方法を使用して、データフィードデータを変換できます。

* [&#x200B; データビューコンポーネント設定](/help/data-views/component-settings/overview.md)、を使用

* [派生フィールド](/help/data-views/derived-fields/derived-fields.md)

* SQL

選択する方法は時には好みの問題です。 次の表は、トレードオフを比較したものです。

## データ変換方法の比較

次の表に、一般的な各方法の利点と欠点を比較します。

| メソッド | メリット | デメリット |
| --- | --- | --- |
| **コンポーネント設定** | <ul><li>データフィードが配信される前に、レポート時に適用されます。</li><li>Analysis Workspaceとデータフィード出力の両方に、同じロジックが一貫して適用されます。</li><li>アカウントの限定的な派生フィールドを使用しないでください。</li><li>永続性や指標の重複排除などの一部の変換はSQLでレプリケートするのが困難で、現在は派生フィールドでも永続性は不可能です。</li></ul> | <ul><li>各コンポーネントがサポートする特定の設定セットでのみ使用できます。派生フィールドを使用してカスタムロジックを構築するような柔軟性はありません。</li><li>設定がデータフィード出力にまったく影響するかどうかについては、いくつかの設定で確認されています。 以下の表を参照してください。</li></ul> |
| **派生フィールド** | <ul><li>データフィードが配信される前に、レポート時に適用されます。</li><li>Analysis Workspaceとデータフィード出力の両方に、同じロジックが一貫して適用されます。</li><li>チェーン付きの条件付きルールなど、単一のコンポーネント設定よりも柔軟なカスタムロジックをサポートします。</li><li>一部の変換、特にスコープ設定に依存する変換やURLを解析する変換は、SQLでレプリケートするのが困難です。</li></ul> | <ul><li>処理オーバーヘッドが追加され、データフィード配信のパフォーマンスに影響を与える可能性があります。<!--Under a future usage-based pricing model, this could also add cost.--></li><li>アカウントの限定的な派生フィールドのいずれかを使用します。 コンポーネント設定で同じジョブを実行できる場合は、代わりにそれを優先します。</li></ul> |
| **SQL** | <ul><li>派生フィールドに適用される関数と演算子の制限による制限はありません。</li><li>データフィード配信のパフォーマンスには影響しません。</li></ul> | <ul><li>データフィードが既に配信された後に適用されます。</li><li>ロジックはAnalysis Workspaceでは適用されないので、別の場所で複製する必要があります。</li><li>一部の変換、特にスコープ設定に依存する変換、URLを解析する変換、またはスコープ全体で値を重複排除または永続化する変換は、複製が困難または非現実的です。</li></ul> |

{style="table-layout:auto"}

## データ変換

次の表に、特定のデータ変換のリストを示します。それぞれのメソッド（またはメソッド）を実行できるメソッド、SQLでのレプリケートが困難なメソッド、および使用するメソッドを示します。<!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| 変換 | コンポーネント設定 | 派生フィールド | SQLの難しさ | 最適なフィット | 注意点 |
| --- | --- | --- | --- | --- | --- |
| **条件ロジックの適用または条件による値のフィルタリング** | [値を含める / 除外](/help/data-views/component-settings/include-exclude-values.md) | [&#128279;](/help/data-views/derived-fields/derived-fields.md#casewhen)の場合 ケース | 文字列の場合は簡単、指標の場合は中程度から難しい | 文字列の場合は、どちらか、指標の場合はコンポーネント設定 | 文字列値の場合は、3つすべて比較できます。主に優先されます。 指標の場合、SQLには`CASE` ステートメントと`COUNT`を組み合わせる必要があります。これは実現可能ですが、より複雑であるため、コンポーネント設定の方がパスが簡単です。 |
| **成功イベントの属性クレジット** | [アトリビューション](/help/data-views/component-settings/attribution.md) | 使用不可 | 該当なし | 該当なし | データフィードの指標には適用されません。 SQLなどを使用して、データフィードをレプリケートする必要はありません。 |
| **数値を範囲にバケット化** | [値のバケット化](/help/data-views/component-settings/value-bucketing.md) | ケース ケース ケース ケース ケース （手動） | 困難 | コンポーネント設定 | 複雑さは、コンポーネントの設定（最も簡単）から派生フィールド（中程度、手動のCase Whenを使用）からSQL （最も複雑）へと増加します。 |
| **参照スタイルのマッピングを使用して値を分類** | 使用不可 | [分類](/help/data-views/derived-fields/derived-fields.md#classify) | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| **フィールド値を区切り記号と組み合わせる** | 使用不可 | [連結](/help/data-views/derived-fields/derived-fields.md#concatenate) | 管理しやすい | いずれか | 複数のディメンション列をフリーフォームテーブルに追加する機能をミラーリングします。この機能は、テーブルの書き出し全体に限定されます。 派生フィールドを使用すると、データフィードで同様の出力を使用できるようになります。 |
| **フィールドのデータ型を変換** | 使用不可 | [Typecast](/help/data-views/derived-fields/derived-fields.md#typecast) | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| **指標の出現回数（値とインスタンスの比較）** | [動作](/help/data-views/component-settings/behavior.md) | カスタム数学ベースの回避策 | 管理しやすい | いずれか | 3つのアプローチはすべて機能します。Customer Journey Analyticsがネイティブで提供しているのであれば、それを実現しない理由はほとんどありません。 |
| **スコープ内の値の重複排除** | [指標の重複排除](/help/data-views/component-settings/metric-deduplication.md) | [重複排除](/help/data-views/derived-fields/derived-fields.md#dedup) | 困難 | コンポーネント設定または派生フィールド | 範囲の設定によって異なります。 [範囲の設定がデータフィードに与える影響](#scope-settings)を参照してください。 コンポーネント設定と派生フィールドは大まかに同等ですが、制限付きの派生フィールドは使用されないので、コンポーネント設定を優先します。 |
| **セッション内のフィールドの深さを決定** | 使用不可 | [深度](/help/data-views/derived-fields/derived-fields.md#depth) | 困難 | 派生フィールド | スコープとしてセッションを使用し、設定できません。<!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> フィード配信の境界にまたがるセッションがエンジニアリングで確認されている場合のカウンターの動作。 範囲の設定によって異なります。 [範囲の設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| **リテラル値を検索して置換** | 使用不可 | [検索と置換](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| **表示用の値の書式設定** | [書式](/help/data-views/component-settings/format.md) | 使用不可 | 困難 | コンポーネント設定 | 日付時刻の書式設定はまだデータフィード出力に反映されていません。現在、フィードにはこの設定に関係なく標準のタイムスタンプが表示されますが、Adobeでは一般提供に対応する予定です。 指標に関する数値形式（10進数、通貨、パーセント）がデータフィード出力に影響するかどうか、チームはまだ確認しています。 |
| **概要データセットからディメンションをグループ化** | [概要データグループ &#x200B;](/help/data-views/component-settings/summary-data-group.md) | 使用不可 | 質問を開く | 質問を開く | まだチームと話し合っていない。 確認するまで、これがデータフィード出力に影響すると仮定しないでください。 |
| **空白（「値なし」フィールド）を処理** | [値オプションなし](/help/data-views/component-settings/no-value-options.md) | 使用不可 | 質問を開く | 質問を開く | これがデータフィードの出力に影響するかどうか（空白の値がnullとして送信されるかどうか、および「値として扱う」が基礎データを変更するかどうかなど）は、まだチームでレビュー中です。 |
| **参照データセットから値を検索** | 使用不可 | [ルックアップ](/help/data-views/derived-fields/derived-fields.md#lookup) | 管理しやすい | いずれか | ルックアップテーブルが既に存在する場合は、SQLが機能します。 |
| **文字列を小文字にする** | [動作](/help/data-views/component-settings/behavior.md) | [小文字](/help/data-views/derived-fields/derived-fields.md#lowercase) | 管理しやすい | コンポーネント設定または派生フィールド | どちらも同等ですが、制限付きの派生フィールドは使用されないため、コンポーネント設定を優先します。 |
| **複数のフィールドを1つに結合** | 使用不可 | [&#x200B; フィールドを結合](/help/data-views/derived-fields/derived-fields.md#merge) | 管理しやすい | いずれか | — |
| **URLをコンポーネントに解析** | [部分文字列](/help/data-views/component-settings/substring.md) （URL解析メソッド） | [URL解析](/help/data-views/derived-fields/derived-fields.md#urlparse) | 困難 | コンポーネント設定または派生フィールド | SQLでは、同じコンポーネントを抽出するためにカスタム文字列解析が必要です。<!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **数値フィールドに対して基本的な計算を実行** | 使用不可 | [数学](/help/data-views/derived-fields/derived-fields.md#math) | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| **ディメンション値をイベント全体で保持** | [永続性](/help/data-views/component-settings/persistence.md) | 現在利用できません<!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> | 困難 | コンポーネント設定 | SQLでこのロジックをレプリケートするよりも、コンポーネント設定を使用する方がはるかに簡単です。 スコープに依存する派生フィールド関数と同じように、ルックバック日付範囲を操作することが既に確認されています。 [&#x200B; ルックバック日付範囲について](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)を参照してください。 |
| **正規表現を使用して値を置き換える** | [部分文字列](/help/data-views/component-settings/substring.md) （Regex メソッド） | [正規表現の置換](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 管理しやすい | いずれか | この3つのアプローチはすべて同じ結果を生み出します。それは好みの問題です。 |
| **セッション内の次または前の値を解決** | 使用不可 | [次または前](/help/data-views/derived-fields/derived-fields.md#next-previous) | 困難 | 派生フィールド | 範囲の設定によって異なります。 [範囲の設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| **2つの日付の差分を返す** | 使用不可 | [日付計算](/help/data-views/derived-fields/derived-fields.md#datemath) | 困難 | 派生フィールド | SQLでレプリケートするには複雑です。 範囲の設定によって異なります。 [範囲の設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| **指標をイベントベース、プロファイルベース、または合計ベースとしてスコープ付け** | [範囲](/help/data-views/component-settings/scope.md) | 使用不可 | 質問を開く | 質問を開く | まだチームと話し合っていない。 確認するまで、これがデータフィード出力に影響すると仮定しないでください。 |
| **区切り値を分割** | [部分文字列](/help/data-views/component-settings/substring.md) （区切り文字または左/右メソッドから） | [分割](/help/data-views/derived-fields/derived-fields.md#split) | 管理しやすい | いずれか | この3つのアプローチはすべて同じ結果を生み出します。それは好みの問題です。 |
| **スコープ全体で値を要約または集計する** | 使用不可 | [要約](/help/data-views/derived-fields/derived-fields.md#summarize) | 困難 | 派生フィールド | 範囲の設定によって異なります。 [範囲の設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| **文字列から文字をトリミング** | [部分文字列](/help/data-views/component-settings/substring.md) （Trim メソッド） | [&#x200B; トリミング &#x200B;](/help/data-views/derived-fields/derived-fields.md#trim) | 管理しやすい | いずれか | この3つのアプローチはすべて同じ結果を生み出します。それは好みの問題です。 |

{style="table-layout:auto"}

### 範囲の設定がデータフィードに与える影響 {#scope-settings}

日付計算、重複排除、次または前、および各要約は、イベント、セッション、または人物の&#x200B;[!UICONTROL **スコープ**]&#x200B;設定によって異なります（使用可能なオプションは機能によって異なります）。 深度には設定可能な範囲フィールドはありませんが、標準のイベント深度ディメンションと同様に、本質的にセッションに関連付けられています。 スコープを持つフィールドは、そのスコープ内のすべての行に同じ値を書き込み、その値はルックバック日付範囲内のデータによって異なります。
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

[&#x200B; ルックバック日付範囲](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)はデータフィード配信ごとに前にスライドするため、同じフィールドは、既に発生したイベントであっても、後の配信で異なる値を返すことができます。

スコープサイズに伴うリスクの増加：個人の履歴はフィード実行内に自然な時間境界がないので、個人のスコープはセッションのスコープよりもリスクが高くなります。

## 派生フィールド関数テンプレート

[派生フィールド関数テンプレート &#x200B;](/help/data-views/derived-fields/derived-fields.md#templates)を使用すると、マーケティングチャネルの作成、ボットの検出、URLからのUTM パラメーターの抽出など、特定のユースケース用の派生フィールドをすばやく作成できます。 テンプレートは事前定義済みのルールのチェーンから構築されているので、SQLで同じロジックをゼロから再現するよりも、テンプレートを使用する方がほとんどの場合に好まれます。

テンプレートにスコープ設定に依存する関数が含まれている場合、その関数のスコープの注意がテンプレートに継承されます。 [範囲の設定がデータフィードに与える影響](#scope-settings)を参照してください。
