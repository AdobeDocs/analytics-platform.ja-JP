---
title: データフィードでの派生フィールドの使用
description: データフィードで派生フィールドを使用する方法を説明します。
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# データフィードでの派生フィールドの使用

{{release-limited-testing}}

[派生フィールド &#x200B;](/help/data-views/derived-fields/derived-fields.md)を使用して、データフィードデータに対してデータ変換を実行できます。

派生フィールド関数の多くは、値の置き換え、フィールドの組み合わせ、フィールドのデータタイプの変換など、SQLを使用して適用できる変換を実行するため、選択する方法が優先される場合があります。

## 派生フィールドとSQLの比較

次の表に、派生フィールドまたはSQLを使用する利点と欠点を比較します。

| メソッド | メリット | デメリット |
| --- | --- | --- |
| **派生フィールド** | <ul><li>派生フィールドは、標準のディメンションと指標とともにデータフィードスキーマのコンポーネントとして含まれるため、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。</li><li>一部の変換、特にスコープ設定に依存する変換やURLを解析する変換は、SQLでレプリケートするのが困難です。</li></ul> | 処理オーバーヘッドが追加され、データフィード配信のパフォーマンスに影響を与える可能性があります。<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>派生フィールドに適用される関数と演算子の制限による制限はありません。</li><li>データフィード配信のパフォーマンスには影響しません。</li></ul> | <ul><li>ロジックはAnalysis Workspaceでは適用されないので、別の場所で複製する必要があります。</li><li>一部の変換、特にスコープ設定に依存する変換やURLを解析する変換は、レプリケートが困難または非現実的です。</li></ul> |

{style="table-layout:auto"}

## 派生フィールド関数

次の表では、派生フィールドとSQLのどちらに最適か、各派生フィールド関数について説明します。また、派生フィールドを使用する前に考慮すべき点を示します。

| 派生フィールド関数 | SQLを使用したレプリケートの困難 | 最適なフィールド（派生フィールドまたはSQL） | 注意点 |
| --- | --- | --- | --- |
| [**Case When**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/> 1つ以上のフィールドの条件に基づいて条件を適用し、条件が一致する場合に出力値を設定します。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 これは、マーケティングチャネル分類など、多数のルールが関与する場合に特に便利です。 |
| [**分類**](/help/data-views/derived-fields/derived-fields.md#classify)<br/>&#x200B;新しい派生フィールド内の対応する値に置き換えられる一連の値を定義します。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**連結**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/>&#x200B;定義された区切り記号（ページ名やマーケティングチャネルなど）を使用して、フィールド値を1つの新しい派生フィールドに結合します。 | 管理しやすい | いずれか | 複数のディメンション列をフリーフォームテーブルに追加する機能をミラーリングします。この機能は、テーブルの書き出し全体に限定されます。 派生フィールドを使用すると、データフィードで同様の出力を使用できるようになります。 |
| [**日付計算**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/> 2つの日付フィールドまたは日時フィールド間の差分（例えば、予約日とチェックイン日の間の日数）を、イベント、セッション、または人物の範囲で返します。 | 困難 | 派生フィールド | SQLでレプリケートするには複雑です。 この関数は、範囲の設定によって異なります。 詳しくは、[関数のスコープ設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| [**重複排除**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/>&#x200B;個人またはセッションの範囲を使用して、値を複数回数えるのを防ぎます（例えば、予約確認IDの重複排除）。 | 困難 | 派生フィールド | この関数は、範囲の設定によって異なります。 詳しくは、[関数のスコープ設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| [**深度**](/help/data-views/derived-fields/derived-fields.md#depth)<br/>&#x200B;標準のイベント深度ディメンション（内部検索の深度など）と同様に、フィールドの深度を返します。 | 困難 | 派生フィールド | スコープとしてセッションを使用し、設定できません。<!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> フィード配信の境界にまたがるセッションがエンジニアリングで確認されている場合のカウンターの動作。 この関数は、範囲の設定によって異なります。 詳しくは、[関数のスコープ設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| [**検索と置換**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/>&#x200B;選択したフィールド内のすべての値を検索し、別の値に置き換えます。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**検索**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/>&#x200B;一致するキーを使用して検索データセットから値を検索し、新しい派生フィールドに返します。 | 管理しやすい | いずれか | ルックアップテーブルが既に存在する場合は、SQLが機能します。 |
| [**小文字**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/> フィールドの値を小文字に変換します。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**数学**](/help/data-views/derived-fields/derived-fields.md#math)<br/>&#x200B;数値フィールドに基本的な数学的演算子（加算、減算、乗算、除算、昇算）を適用し、ヒットによるヒットを評価します。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**フィールドを結合**](/help/data-views/derived-fields/derived-fields.md#merge)<br/> 2つ以上のフィールドの最初のフィールドに値があるかどうかを確認します。値がない場合は、次のフィールドを使用します。 | 管理しやすい | いずれか | なし |
| [**次または前**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/>&#x200B;訪問またはイベント テーブル フィールドの次または前の値を、個人またはセッションの範囲で解決します。 | 困難 | 派生フィールド | この関数は、範囲の設定によって異なります。 詳しくは、[関数のスコープ設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| [**正規表現**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/>&#x200B;正規表現を使用して、フィールドの値を置換します。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**分割**](/help/data-views/derived-fields/derived-fields.md#split)<br/> フィールドの値を新しい派生フィールドに分割します（たとえば、区切りリストを配列に変換します）。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**要約**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/>&#x200B;集計関数（合計、数、最も一般的な関数など）を、イベント、セッション、人物の範囲を含むフィールドに適用します。 | 困難 | 派生フィールド | この関数は、範囲の設定によって異なります。 詳しくは、[関数のスコープ設定がデータフィードに与える影響](#scope-settings)を参照してください。 |
| [**トリミング**](/help/data-views/derived-fields/derived-fields.md#trim)<br/> フィールドの値の先頭または末尾から、空白、特殊文字、または一連の文字数をトリミングします。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/> フィールドのデータタイプを変更して、追加の変換に使用できるようにします。 | 管理しやすい | いずれか | SQLでは再現可能ですが、派生フィールドを使用すると、Analysis Workspaceとデータフィード出力の両方で同じロジックが一貫して適用されます。 |
| [**URL解析**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/> プロトコル、ホスト、パス、クエリ文字列パラメーター、ハッシュ値など、URLの一部を解析します。 | 困難 | 派生フィールド | SQLでは、同じコンポーネントを抽出するためにカスタム文字列解析が必要です。 |

{style="table-layout:auto"}

### 関数の範囲設定がデータフィードに与える影響 {#scope-settings}

[!UICONTROL **日付計算**]、[!UICONTROL **重複排除**]、[!UICONTROL **次または前**]、および&#x200B;[!UICONTROL **要約**]&#x200B;は、イベント、セッション、またはユーザーの&#x200B;[!UICONTROL **スコープ**]&#x200B;設定によって異なります（使用可能なオプションは関数によって異なります）。 [!UICONTROL **深度**]&#x200B;には設定可能なスコープ フィールドはありませんが、標準のイベント深度ディメンションと同様に、本質的にセッションに関連付けられています。 スコープを持つフィールドは、そのスコープ内のすべての行に同じ値を書き込み、その値はルックバック日付範囲内のデータによって異なります。
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

ルックバック日付範囲はデータフィード配信ごとに前にスライドするため、同じフィールドは、既に発生したイベントであっても、後の配信で異なる値を返すことができます。

スコープサイズに伴うリスクの増加：個人の履歴はフィード実行内に自然な時間境界がないので、個人のスコープはセッションのスコープよりもリスクが高くなります。

## 派生フィールド関数テンプレート

[派生フィールド関数テンプレート &#x200B;](/help/data-views/derived-fields/derived-fields.md#templates)を使用すると、マーケティングチャネルの作成、ボットの検出、URLからのUTM パラメーターの抽出など、特定のユースケース用の派生フィールドをすばやく作成できます。 テンプレートは事前定義済みのルールのチェーンから構築されているので、SQLで同じロジックをゼロから再現するよりも、テンプレートを使用する方がほとんどの場合に好まれます。

テンプレートにスコープ設定に依存する関数が含まれている場合、その関数のスコープの注意がテンプレートに継承されます。 [関数のスコープ設定がデータフィードに与える影響](#scope-settings)を参照してください。

