---
title: Customer Journey Analytics ガードレール
description: Customer Journey Analyticsのガードレールについて説明します
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
TQID: https://experienceleague.adobe.com/vNCqAk1-4e34AJrXqzHJgrTDtly-FZTqOGRISjkX5Q8
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: df1ab1af7757ef012b4c233e6206ee6c6cde6686
workflow-type: tm+mt
source-wordcount: 2441
ht-degree: 12%

---

# Customer Journey Analyticsのガードレール

このドキュメントでは、Customer Journey Analyticsの様々なコンポーネントに関する制限について説明します。 ガードレール、スコープパラメーター、および使用権限については、[Customer Journey Analyticsの商品説明](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html)、Adobe Analytics アドオンの[商品説明：Customer Journey Analytics](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html)、または[Customer Journey Analytics B2B editionの商品説明](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics-b2b.html)を参照してください。

## 上限のタイプ

このドキュメントでは、次の 2 種類のデフォルトの上限について説明します。

| ガードレール型 | 説明 |
|----------|---------|
| **パフォーマンスガードレール （ソフト制限）** | パフォーマンスガードレールは、ユースケースの範囲に関連する使用制限です。 パフォーマンスのガードレールを超えると、パフォーマンスの低下や遅延が発生する場合があります。 Adobeはこのようなパフォーマンス低下の責任を負いません。 パフォーマンスのガードレールを常に超えているお客様は、パフォーマンスの低下を回避するために、追加の容量のライセンスを取得できます。 |
| **システムが適用するガードレール （ハード制限）** | システムによって適用されるガードレールは、Customer Journey Analytics UIまたはAPIによって適用されます。 UIおよびAPIによってブロックされたり、エラーが返されたりすると、これらの制限を超えることはできません。 |

{style="table-layout:auto"}

制限に対する機能とその関連値の一部は、使用権限のあるCustomer Journey Analytics パッケージによって異なります。

>[!NOTE]
>
>このドキュメントに記載されている値は、製品の継続的な改善に基づいて変更される場合があります。 定期的にチェックして、更新を確認してください。 カスタム制限について詳しくは、カスタマーケア担当者にお問い合わせください。

## アドホック SQL クエリ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| 再試行のタイムアウト | 90 | システム強制ガードレール | レポートエンジンが、リクエストが結果を返すのに時間がかかりすぎたことを返す前の最大秒数（他の同時リクエストが原因の場合もあります）。もう一度リクエストすることができます。 |
| 再試行しないタイムアウト | 600 | システム強制ガードレール | アドホック SQL クエリのタイムアウト前の最大秒数。 それ以外の場合は、レポートエンジンがリクエストの結果を返すのに時間がかかりすぎたことを報告する前の最大秒数が返されます。再試行しないでください。 バックグラウンド処理の問題により、リクエストが結果を返さない可能性が高くなります。 |
| 指標 | 150 | システム強制ガードレール | リクエスト内の指標の最大数。 |
| インタラクティブ クエリの出力行 | 50,000 | システム強制ガードレール | 特に指定しない限り、返されるデフォルトの行数。 |

{style="table-layout:auto"}

## Analysis Workspace プロジェクト

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| テーブルごとの表示行 | 400 | システム強制ガードレール | Analysis Workspace プロジェクト内の任意のフリーフォームテーブルに表示される最大行数。 |
| テーブルごとのエクスポート可能な行 | 50,000 | システム強制ガードレール | 1つのディメンションごとに書き出すことができる最大行数。 |
| プロジェクトごとのパネル | 15 | システム強制ガードレール | プロジェクトごとの最大数[ パネル ](../analysis-workspace/home.md#panels)。 |
| パネルごとのビジュアライゼーション | 25 | システム強制ガードレール | パネルあたりのビジュアライゼーションの最大数[個](../analysis-workspace/home.md#visualizations)。 |
| フリーフォームテーブルごとの派生フィールド | 5 | システム強制ガードレール | 1つのフリーフォームテーブル内の異なる派生フィールドの最大数。 |
| プロジェクトごとのコメント | 1,000 | システム強制ガードレール | プロジェクトごとの最大コメント数。 |
| プロジェクトごとのコメント | 1,000 | システム強制ガードレール | プロジェクトごとの最大コメント数。 |
| コメントあたりの返信 | 100 | システム強制ガードレール | コメントあたりの返信の最大数。 |
| コメントあたりの画像 | 5 | システム強制ガードレール | コメントあたりの最大画像数。 |
| 画像サイズ | 2 | システム強制ガードレール | 画像あたりの最大アップロードサイズ （MB単位）。 |
| コメントあたりの返信 | 100 | システム強制ガードレール | コメントあたりの返信の最大数。 |
| コメントあたりの画像 | 5 | システム強制ガードレール | コメントあたりの最大画像数。 |
| 画像サイズ | 2 | システム強制ガードレール | 画像あたりの最大アップロードサイズ （MB単位） |

{style="table-layout:auto"}


<!-- at flatview GA, add: - Dimension columns per freeform table - 5 - System-enforced guardrail - Maximum number of dimensions per freeform table. -->

<!--

## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

-->

## オーディエンス

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| Audience segments | 20 | システム強制ガードレール | オーディエンスあたりの最大[ セグメント数](../components/segments/seg-overview.md)です。 |
| オーディエンス IDの数 | 20百万 | システム強制ガードレール | オーディエンスあたりの最大ID数。 |
| オーディエンスの更新頻度 | 4 | システム強制ガードレール | [ オーディエンス ](../components/audiences/audiences-overview.md)の最大頻度（時間単位）を更新できます。 |
| オーディエンス更新ルックバックウィンドウ | 90 | システム強制ガードレール | 更新ルックバックウィンドウの最大日数。 |
| オーディエンス有効期限の更新 | 13 | システム強制ガードレール | 作成日からオーディエンスが更新しなくなった最大月数。 お客様は、さらに13か月間これを延長できます。 |
| 更新オーディエンスの数 | 75, 150 | システム強制ガードレール | 更新オーディエンスの最大数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |

{style="table-layout:auto"}

Experience Platform [Real-time Customer Data Platform ガードレール ](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/guardrails/overview)も参照してください。


## データセットに自動有効期限を設定

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|:---:|
| 作業指示 | 20 | システム強制ガードレール | 1か月あたりの自動データセット有効期限の最大作業注文数。 |

{style="table-layout:auto"}



## 接続、データビュー、プロジェクト

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| プロジェクト | 50,000 | システム強制ガードレール | 組織のプロジェクトの最大数。 |
| データビュー | 2,000 | システム強制ガードレール | 組織の最大[ データビュー](../data-views/data-views.md)数。 |
| データビュー | 500-1000 | システム強制ガードレール | 接続のデータビューの最大数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |
| データセット | 100 | システム強制ガードレール | 接続あたりの最大数[ データセット ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja)。 |
| 接続 | 1000 | システム強制ガードレール | 組織の最大接続数[個](../connections/overview.md)です。 |
| 接続タイトル | 500 | システム強制ガードレール | 接続タイトルの最大文字数。 |
| 指標 | 5,000 | システム強制ガードレール | データビュー内の指標の最大数。 |
| ディメンション | 5,000 | システム強制ガードレール | データビュー内のディメンションの最大数。 |
| 注釈タイトル | 100 | システム強制ガードレール | 注釈タイトルの最大文字数。 |
| 注釈の説明 | 250 | システム強制ガードレール | 注釈の説明の最大文字数。 |
| スキーマフィールド | 10 | システム強制ガードレール | [派生フィールド ](../data-views/derived-fields/derived-fields.md)のルールを定義する際のスキーマフィールドの最大数（標準フィールドを含まない）。 |
| ルックアップ / プロファイルフィールド | 3 | システム強制ガードレール | 派生フィールドのルールを定義する際の検索またはプロファイルスキーマフィールドの最大数（標準フィールドを含まない）スキーマフィールドの最大数。 |
| 派生フィールド | 100 - 500 | システム強制ガードレール | 接続あたりの派生フィールドの最大数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |

{style="table-layout:auto"}


## データ転送の制限

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| フィールド | 10,000 | システム強制ガードレール | データセットの行あたりのプロパティまたはフィールドの最大数。 |
| 一意の文字列 | 1000万～ 10億 | システム強制ガードレール | ルックアップデータセットごとの一意のキーの最大数。 Customer Journey Analytics パッケージによって異なります（詳しくは、製品説明を参照）。<ul><li>財団：1000万。</li><li>選択：1億人。</li><li>Prime:2億5000万</li><li>Ultimate:10億</li><ul> |
| 1人あたりの行 | 100 万 | システム強制ガードレール | 接続内の特定の月の一意のユーザーIDあたりの最大行数。 |
| 1日あたりの行数 | 25億 | パフォーマンスガードレール | 接続の1日あたりの最大平均行数。 |
| 1年あたりの接続あたりの行数 | 割り当てられたデータセンターによって異なります（詳しくは説明を参照） | パフォーマンスガードレール | 接続の年間行数の制限。 以下に示す制限は、2026年1月20日（PT）に有効になり、時間の経過に伴い増加して1接続あたりの行が増える可能性があります。 <p>行制限は、割り当てられたデータセンターによって次のように異なります。</p><ul><li>**米国。Azure（米国のお客様のデフォルト）**：約5,000億（月あたり約420億）</li><li>**米国。AWS（米国のお客様向け利用申請）**：約300億（月間約25億）</li><li>**アムステルダム**：約2,000億（月に約165億）</li><li>**その他のすべてのデータセンター**: 250億（月に約20億）</li></ul><p>これらの制限を超える可能性があり、パフォーマンスの低下の問題を回避したい場合は、Adobeのアカウントチームに連絡して、別の設定について話し合ってください。</p><p>企業は、AEP+Appsを導入する際に、データセンターを選択することができます。 通常、この決定は、各顧客のデータレジデンシー要件にもとづいて行われます。 データセンターを選択する際には、すべてのAEP+アプリのユースケース（Customer Journey Analyticsの行ボリュームだけでなく）を考慮する必要があります。</p><p>割り当てられたデータセンターの表示方法について詳しくは、[Customer Journey Analytics ホスティング場所](/help/technotes/data-centers.md)を参照してください。</p> |
| 行サイズ | 2 | パフォーマンスガードレール / システムに従ったガードレール | Customer Journey Analyticsに取り込まれたデータの行あたりの平均サイズ（キロバイト単位）（ソフト制限）。 行サイズの静的制限は、Experience Platformでのデータ取り込みのガードレールによって決まります。 |

{style="table-layout:auto"}

データ取り込み用のExperience Platform [ ガードレール ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html)も参照してください。


## 宛先データの書き出し

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| データの書き出し | 許可されたデータレイクストレージの合計数 | パフォーマンスガードレール | お客様は、宛先データセットの書き出しを使用して、データレイク内の顧客データを合計承認済みデータレイクストレージまで書き出すことができます。 |
| 利用可能なデータセット | プロファイルとイベント | システム強制ガードレール | Experience Platform UIで、ソース、Web SDK、Mobile SDK、Analytics Data Connector、およびAudience Managerを通じてデータを取り込むか収集した後に作成されたイベント、プロファイルまたはルックアップデータセット。 |

{style="table-layout:auto"}

Experience Platform [ データセット書き出しガードレール ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports)も参照してください


## データランディングゾーン

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| サンドボックスごとのデータランディングゾーン | 1 | システム強制ガードレール | サンドボックスあたりのデータランディングゾーンの最大数。 |
| データストレージ | 7 | システム強制ガードレール | データが削除される前に、データランディングゾーンに保存される最大日数。 |

{style="table-layout:auto"}


## フィールドベースのステッチ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| ステッチされたデータセット | 5 - 50 | システム強制ガードレール | 顧客1人あたりのステッチされたデータセットの最大数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |
| バックフィルの長さ | 6 - 25 | システム強制ガードレール | バックフィルデータの最大月数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |
| ルックバックウィンドウ/再生頻度 | 1/1 - 30/7 | システム強制ガードレール | 日数/再生頻度の最大ルックバックウィンドウ。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |

{style="table-layout:auto"}


## グラフベースのステッチ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| ステッチされたデータセット | 15 - 50 | システム強制ガードレール | 顧客1人あたりのステッチされたデータセットの最大数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |
| バックフィルの長さ | 6 - 25 | システム強制ガードレール | バックフィルデータの最大月数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |
| ルックバックウィンドウ/再生頻度 | 1/1 - 30/7 | システム強制ガードレール | 日数/再生頻度の最大ルックバックウィンドウ。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |


## セグメントと計算指標

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| セグメントごとのコンテナ | 50 | システム強制ガードレール | セグメントあたりのコンテナの最大数。 |
| 計算指標ごとの指標 | 25 | システム強制ガードレール | 計算された指標ごとの指標の最大数。 |
| セグメントごとの指標とディメンション | 25 | システム強制ガードレール | セグメントあたりの一意の指標とディメンションの最大数。 |
| セグメントごとのネストされたコンテナ | 10 | システム強制ガードレール | セグメントあたりのネストされたコンテナの最大数。 |
| セグメントあたりのルール | 100 | システム強制ガードレール | セグメントあたりのルールの最大数。 |
| 文字列はDimensionごとにセグメントごとに比較されます | 100 | システム強制ガードレール | セグメントごとのディメンションごとの文字列比較の最大数。 |
| 計算指標 | 50,000 | システム強制ガードレール | 組織の計算指標の最大数。 |
| セグメント | 50,000 | システム強制ガードレール | 組織に定義できるセグメントの最大数。 |
| API 呼び出し | 120 | システム強制ガードレール | 1分あたりのAPI リクエスト数（6秒ごとに12件）。 |

{style="table-layout:auto"}


## モバイルアプリケーション

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| タイル | 16 | システム強制ガードレール | スコアカードあたりの最大タイル数。 |
| セグメント | 10 | システム強制ガードレール | スコアカードあたりの最大セグメント数。 |
| ディメンション | 10 | システム強制ガードレール | スコアカードあたりの最大ディメンション数。 |

{style="table-layout:auto"}

## Report Builder

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| ワークブックのファイルサイズ | 5 | システム強制ガードレール | スケジュールされたワークブックの最大ファイルサイズ （MB）。 |
| データ ブロック | 1000 | システム強制ガードレール | ワークブックあたりの最大[ データブロック ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=ja)数。 |
| 指標 | 20 | システム強制ガードレール | データブロックあたりの指標の最大数。 |
| 日付範囲スパン | 13 | システム強制ガードレール | 日付範囲がデータブロックごとに使用できる最大月数。 |
| 行 | 50,000 | システム強制ガードレール | データブロックごとの最大行数。 |

{style="table-layout:auto"}


## 完全なテーブルの書き出し

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| レポートごとの行 | 3百万 – 3億 | システム強制ガードレール | レポートごとのレポート行の最大数。 値はCustomer Journey Analytics パッケージによって異なります（商品説明を参照）。 |
| テーブルごとの分類 | 5 | システム強制ガードレール | テーブルあたりの分類の最大数。 |
| テーブルあたりの指標 | 5 | システム強制ガードレール | テーブルあたりの指標の最大数。 |
| スケジュール頻度 | 1 | システム強制ガードレール | 書き出しは、1日に1回、またはより長いスケジュールでスケジュールできます（例：2日に1回、または毎週）。 |

{style="table-layout:auto"}


## 共有指標と共有ディメンション

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| 共有ライブラリ | 1 | システム強制ガードレール | 接続の共有ライブラリの最大数。 |
| 共有指標 | 10,000 | システム強制ガードレール | 共有ライブラリあたりの共有メトリクスの最大数。 |
| 共有ディメンション | 10,000 | システム強制ガードレール | 共有ライブラリあたりの共有ディメンションの最大数。 |

{style="table-layout:auto"}


## Data Insights Agent

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| データビュー | 50 | システム強制ガードレール | Data Insights Agentに対して有効にできるデータビューの最大数。 より多くのデータビューが有効になっている場合、Data Insights Agentで使用できるのは、最も使用されているデータビューのみです。 このガードレールは、接続または組織内で定義できるデータビューの最大数を定義する[ ガードレールには影響しません](#connections-data-views-projects)。 |


## Customer Journey Analytics B2B Edition

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| 報告可能なビジネスパーソン プロファイル（BPP）報告可能な行 | 100 万 | パフォーマンスガードレール | レポート可能なビジネスパーソンのプロファイル 1000件あたりの平均行。 |




## 待ち時間

>[!NOTE]
>
>以下の処理時間は、SLA （サービスレベル契約）ではなく、ガードレールです。 待ち時間は、顧客設定、データボリューム、コンシューマアプリケーションによって異なります。 実際の処理時間は、多くの場合、より高速です。 具体的な契約条件およびSLAについては、Customer Journey Analyticsとの契約を参照してください。 詳しくは、Experience Platform [ データ取り込み用ガードレール ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html)を参照してください。

| データフロー | 予想遅延時間 |
|---|---|
| Adobe AnalyticsからAdobe Analytics Sourceへのコネクタ（A4T対応） | &lt; 30分 |
| Adobe Analytics Source Connectorからリアルタイム顧客プロファイルへ（A4Tは有効になっていません） | &lt; 2 分 |
| Adobe Analytics Source Connectorからリアルタイム顧客プロファイルへ（A4T対応） | &lt; 30分 |
| Edge Networkからのデータレイクへのデータ取り込みまたはストリーミング取り込み | &lt; 60 分 |
| Adobe Analytics Source Connectorからのデータレイクへのデータ取り込み | &lt; 2.25時間 |
| データレイクからCustomer Journey Analyticsへのデータ取り込み | &lt; 90分 |
| 結合（オプション機能。詳細は[結合概要](../stitching/overview.md)を参照） | 4時間未満 |
| Adobe Analytics Source Connector バックフィルの100億件未満のイベント（最大13か月間の履歴データ） | &lt; 4 週間 |
| リアルタイム顧客プロファイルへのオーディエンスの公開（ストリーミングセグメントの自動作成、データを受信するためのセグメントの準備など）。 | ≈ 60分 |
| オーディエンスの更新頻度 | 1回限りの更新：5分未満の待ち時間。<br/>4時間ごとに、毎日、毎週、毎月ごとに更新します（更新レートとレイテンシが連動します）。 |

| リアルタイムのレポート作成の遅延 | 予想遅延時間 |
|---|---|
| Edge Network SDK / APIをEdge Networkに接続 | &lt; 7分 |
| ストリーミングコネクタ | &lt; 17分 |
| Adobe Analytics ソースコネクタ | &lt; 17分 |
| その他のソースコネクタ（バッチデータを含む） | &lt; 25時間 |

{style="table-layout:auto"}
