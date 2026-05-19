---
description: Customer Journey AnalyticsとAdobe Analyticsのデータフィード機能の比較方法について説明します
keywords: クリックストリーム;データフィード;データフィード;データフィード
title: Customer Journey AnalyticsとAdobe Analyticsのデータフィード機能の比較
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 934
ht-degree: 2%

---

# Customer Journey AnalyticsとAdobe Analyticsのデータフィードの比較

Customer Journey AnalyticsとAdobe Analyticsの両方のデータフィードでは、生データをサードパーティのプラットフォームに書き出すことができます。 以前にAdobe Analyticsでデータフィードを使用したことがある場合は、次の情報を使用して、使用可能な機能と概念の違いを把握します。

| **概念と設定オプション** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **データ入力**<br/>&#x200B;収集してデータフィードに含めることができるデータの種類。 | web データ、コールセンターデータ、POS データなどのクロスチャネルデータ入力に対応しています。 | 主にwebとモバイルのデータ入力をサポートしています。 その他のデータタイプ（コールセンターやPOS データなど）は、データソースを通じて取り込むことができますが、処理機能は非常に限られています。 |
| **データ処理**<br/>&#x200B;使用している製品に応じて、データは異なる段階で処理されます。 | データは&#x200B;**レポート時間**&#x200B;に処理されるため、ステッチ、派生フィールド、セグメント化など、多くのレポート機能を使用して履歴データを変更できます。 | データは&#x200B;**収集時間**&#x200B;に処理されるので、処理ルールやVISTA ルールなどのレポート機能は過去のデータに影響しません。 |
| **配信頻度**<br/> データフィードの送信頻度と、フィードに含まれる期間を決定します。 | **日単位** （データビューのタイムゾーンでは午前0時から午前0時）または&#x200B;**時間単位**。 | **日単位** （レポートスイートのタイムゾーンでは午前0時から午前0時）または&#x200B;**時間単位**。 15分間のフィードは可能ですが、デフォルトでは利用できません。 |
| **遅延ヒット**<br/> タイムスタンプが以前の配信頻度ウィンドウに属するが、そのウィンドウが既に経過した後に到着したヒット。 <p>たとえば、遅刻ヒットは、モバイルアプリから送信される可能性があります。モバイルアプリは、オフライン中のイベントをバッファリングし、再接続したときにイベントを送信します。</p> | **処理遅延**&#x200B;設定は、書き出しをトリガーする前に頻度ウィンドウが閉じた後にシステムが待機する時間を制御し、遅延データが到着するまでの時間を追加します。 | 遅延着信ヒットは、**遅延着信ヒット**&#x200B;設定オプションを使用して&#x200B;**含めることも除外することもできます**。 <p>**ルックバックウィンドウ**&#x200B;の設定により、システムが遅延データを含めるまでにどれくらい戻るかを制御します。</p> |
| **順序に合わないヒット**<br/> タイムスタンプが受信した順序と一致しないヒット。 | Customer Journey Analyticsはストリーミングデータとバッチデータの両方を受け入れるので、特定のユーザーのイベントがタイムスタンプ順に届く保証はありません。 Customer Journey Analyticsは、レポート時に1人あたりのタイムスタンプでデータを並べ替えます。 <p>**処理遅延**&#x200B;設定は、バッチデータがエクスポート前に到着するまでの時間を増やすことにより、データフィード出力の不規則なイベントを減らすのに役立ちます。 配信におけるイベントの順序は保証されません。</p><p>**重要**: データフィード配信でのヒットの順序が保証されていないため、データフィード データの最終的なコンシューマーは、1人あたり、順序が正しくないタイムスタンプを処理できなければなりません。</p> | Adobe Analyticsでは、データの収集時に、訪問者一人ひとりに対して順番にデータを届ける必要がありますが、データフィードの配信ではヒット順序は保証されません。</p> |
| **バックフィル ウィンドウ**<br/>&#x200B;過去2日間の履歴データを書き出します。 | 接続のローリングデータウィンドウに限定されます。 | デフォルトでは、レポートスイートデータ保持期間の制限&#x200B;**25か月**&#x200B;に制限されています。 |
| **セグメント化** | セグメントは、データビューセグメント、フィード固有のセグメント、またはその両方を介してデータフィードに適用できます。 | セグメントは適用できません。 |
| **ステッチ** | サポートされています。 クロスデバイス ID解決を有効にし、デバイス間のイベントを1人のユーザーにリンクします。 | サポートされていません。 結合されたデータは、Adobe Analytics データフィードを介して書き出すことはできません。 |
| **スキーマ**<br/> データフィードスキーマは、データフィードに含めることができる列を決定します。 | データフィードスキーマは、データビュー設定に基づいています。  データフィードスキーマに含めることができるコンポーネントは、データビュー設定で使用できるコンポーネントのサブセットです。</p> | 約1,100以上の変数があらかじめ定義された静的リスト。 多くの列は&#x200B;**前処理と後処理のペア**&#x200B;として書き出されます（例：`eVar1` / `post_eVar1`）。これは、列数の多くを占めています。 |
| **ルックアップ**<br/>&#x200B;動的ルックアップを使用すると、データフィードで追加のルックアップファイルを受信できます。それ以外の場合は使用できません。 | 参照と分類は、どちらもデータビューで直接キュレーションされたディメンションとして使用できるため、必要ありません。 ルックアップまたは分類をデータビューのディメンションとしてキュレートすると、解決された値は、イベントデータとインラインで同じ正規列として表示され、個別の参照ファイルとして表示されません。 | データフィード列の数値を実際の値に一致させるために使用します。 特定の一連の項目（ブラウザー、OS、モバイルデバイス、データフィードに付属する個別のファイルとして適用されます）に固有の情報を入力します。 |
| **セッション定義**<br/> <!--(could be included in the data processing section instead)--> | データビューで定義されます。 | コレクション時に定義されます。 |
| **計算指標**<br/> | 使用不可 | 使用不可 |
| **永続性モデル** | 柔軟性： データビューの永続性設定（割り当てと有効期限）は、フィードが生成されるレポート時に適用されます。 データビューで使用できるすべての割り当て設定をサポートします：**元**、**最新**、**すべて**、**最初の既知**、および&#x200B;**最後の既知**。 | **最新（ラストタッチ）**&#x200B;と&#x200B;**元の値（ファーストタッチ）**&#x200B;のアトリビューションモデルのみが表されます。 線形配分は、ラストタッチと同じように処理されます。 |
| **出力ファイル形式** | PARQUET<p>複雑なネスト化および構造化データをネイティブにサポート。 商品リストは、構造化配列やネストされたオブジェクトとして表されます。 </p><p>BigQuery、Snowflake、Apache Sparkなど、Parquetに対応したツールが必要です。</p> | TSV<p>人間が読むことができるフラットな行。 構造化データはネイティブにサポートされません。製品リストなどの複雑なフィールドは、カスタム解析ロジックを必要とする独自の区切り文字列としてエンコードする必要があります。</p> |
| **配信先** | Amazon S3、Azure RBAC、Azure SAS、Google Cloud Platform、Snowflake。 | Amazon S3、Azure RBAC、Azure SAS、Google Cloud Platform。 **SFTP**&#x200B;もサポートしています。 |

{style="table-layout:auto"}

<!-- Is this useful info to accompany the table? Not sure... **Hits**<br/>  | Only Hit 5 is in the data feed window. However, because the reporting window also includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window.<p>Hits are reordered in the data feed according to their timestamp, as follows: Hit 3, Hit 4, Hit 5.</p> | Only Hit 5 is in the data feed window. However, because a lookback is configured and it includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window. (If a lookback was not configured, only Hit 5 would be included in the data feed.) <p>Hits are shown in the data feed in the order they were received, as follows: Hit 4, Hit 3, Hit 5.</p> -->

<!-- Is all of this info redundant?  **Late-arriving hits**<br/> (If you send us data that is out of order per person would be if you are setting the timestamp. You can set the timestamp in 2 ways: you can have Adobe set the timestamp, based on when we received the data. Or you can set it yourself. If you're setting the timestamps and you sending us data that is out of order, it messes things up in AA. In AA, data needs to come in order per visitor. We need the right order of events. But in CJA, it doesn't matter what timestamps are on the data. CJA doesn't assign a timestamp to a hit. That is done upstream. CJA reorders the data once it arrives, so that everything is in the proper time sequence. Then we can do the report-time processing. That means you can have both streaming data and batch data. It doesn't matter. At the time it arrives, we reorder it and it becomes in order per person as a result. So in CJA we'll give you all the data we received in the last day or hour, but it's limited to the beginning of the reporting window. Most likely a huge chunk of the data you get in a day or hour belongs to that day or hour. If all you did was batch data from a call center, then that is what you would get out. In CJA, data can come in and it doesn't matter when it came in. So the data feed ustomer has to be able to handle this on their side. So wherever they're putting the data, it needs to handle the fact that timestamps could potentially be all over the place. This might be a challenge for some customers. They need to know this. Needs to be able to handle out of order data per person. It doesn't matter across people. ) Hits that should have been included in a previous data feed, but for some reason they arrived late (such as through timestamped hits or data sources). <p>These late-arriving hits are included in the current data feed at the time they arrive, even though their timestamps are within a previous data feed window. Every time a data feed processes data, it looks at any late hits that have arrived and batches them in the next data feed file that is sent.</p>  | Late-arriving hits that occur within the **[!UICONTROL Reporting window]** are always included. <p>The lookback window for these late-arriving hits is controlled through the **[!UICONTROL Reporting window]** configuration option.</p><p>Hits are automatically reordered based on timestamps; original values are persisted (no change feed).</p> | Can be included or excluded. Configurable with the **[!UICONTROL Late-arriving hits]** configuration option.<p>The lookback window for these hits is configured through the **[!UICONTROL Lookback window]** configuration option that is available for this specific purpose.</p><p>Hits are shown in the order in which they are received; they are not reordered according to timestamp.</p>   -->
