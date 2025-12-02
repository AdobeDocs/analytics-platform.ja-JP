---
title: Customer Journey Analytics ガードレール
description: Customer Journey Analyticsのガードレールについて学ぶ
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '2087'
ht-degree: 10%

---

# Customer Journey Analytics ガードレール

このドキュメントでは、Customer Journey Analyticsの様々なコンポーネントに対して制限を提供します。 ガードレール、スコーピングパラメーター、使用権限については、[Customer Journey Analyticsの製品説明 &#x200B;](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html)、[Adobe Analytics アドオンの製品説明：Customer Journey Analytics](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html)、[Customer Journey Analytics B2B editionの製品説明 &#x200B;](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics-b2b.html) を参照してください。

## 上限のタイプ

このドキュメントでは、次の 2 種類のデフォルトの上限について説明します。

| ガードレール タイプ | 説明 |
|----------|---------|
| **パフォーマンスガードレール（ソフトリミット）** | パフォーマンスガードレールは、ユースケースのスコーピングに関連する使用制限です。 パフォーマンスのガードレールを超えると、パフォーマンスの低下や待ち時間が発生する場合があります。 Adobeは、このようなパフォーマンス低下に対する責任を負いません。 パフォーマンスのガードレールを一貫して超えるお客様は、パフォーマンスの低下を避けるために、追加容量のライセンスを選択できます。 |
| **システム適用ガードレール（ハードリミット）** | システムで適用されるガードレールは、Customer Journey Analytics UI または API で適用されます。 これらは、UI および API によってブロックされるか、エラーが返されるので、を超えることはできません。 |

{style="table-layout:auto"}

一部の機能とそれに関連する制限値は、使用資格のあるCustomer Journey Analytics パッケージに応じて異なります。

>[!NOTE]
>
>このドキュメントで説明されている値は、製品で継続的に改善された場合、変更される可能性があります。 定期的にアップデートを確認してください。 カスタムの上限について知りたい場合は、カスタマーケア担当者にお問い合わせください。

## アドホック SQL クエリ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| Try Again Timeout | 90 | システム強制ガードレール | （他のリクエストの同時実行が原因で）結果を返すのにリクエストの応答に時間がかかりすぎている場合の、レポートエンジンが応答するまでの最大秒数。再びリクエストする可能性があります。 |
| 再試行しないタイムアウト | 600 | システム強制ガードレール | アドホック SQL クエリがタイムアウトするまでの最大秒数。 そうでない場合は、レポートエンジンが、リクエストが結果を返すまでに時間がかかりすぎたとレポートを返す最大秒数を指定し、この秒数は再試行しないようにします。 バックグラウンドプロセスの問題が原因で、リクエストが結果を返さない可能性が高くなります。 |
| 指標 | 150 | システム強制ガードレール | リクエスト内の指標の最大数。 |
| 対話型クエリの出力行 | 50,000 | システム強制ガードレール | 特に指定しない限り、返されるデフォルトの行数です。 |

{style="table-layout:auto"}

## Analysis Workspace プロジェクト

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| テーブルごとに表示される行 | 400 | システム強制ガードレール | Analysis Workspace プロジェクトのフリーフォームテーブルに表示される行の最大数。 |
| テーブルごとのエクスポート可能な行 | 50,000 | システム強制ガードレール | 単一のディメンションごとにエクスポートできる行の最大数。 |
| プロジェクトごとのパネル数 | 15 | システム強制ガードレール | プロジェクトあたりの最大 [&#x200B; パネル &#x200B;](../analysis-workspace/home.md#panels) 数。 |
| パネルごとのビジュアライゼーション | 25 | システム強制ガードレール | パネルあたりの [&#x200B; ビジュアライゼーション &#x200B;](../analysis-workspace/home.md#visualizations) の最大数。 |
| フリーフォームテーブルごとの派生フィールド | 5 | システム強制ガードレール | 1 つのフリーフォームテーブルでの異なる派生フィールドの最大数。 |
| プロジェクトごとのコメント | 1,000 | システム強制ガードレール | プロジェクトごとの最大コメント数。 |
| プロジェクトごとのコメント | 1,000 | システム強制ガードレール | プロジェクトごとの最大コメント数。 |
| コメントごとの返信 | 100 | システム強制ガードレール | コメントあたりの最大返信数。 |
| コメントあたりの画像の数 | 5 | システム強制ガードレール | コメントあたりの最大画像数。 |
| 画像サイズ | 2 | システム強制ガードレール | 画像あたりの最大アップロードサイズ （MB 単位）。 |
| コメントごとの返信 | 100 | システム強制ガードレール | コメントあたりの最大返信数。 |
| コメントあたりの画像の数 | 5 | システム強制ガードレール | コメントあたりの最大画像数。 |
| 画像サイズ | 2 | システム強制ガードレール | 画像あたりの最大アップロードサイズ （MB 単位） |

{style="table-layout:auto"}


<!-- at flatview GA, add: - Dimension columns per freeform table - 5 - System-enforced Guardrail - Maximum number of dimensions per freeform table. -->

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
| オーディエンスセグメント | 20 | システム強制ガードレール | オーディエンスあたりの最大 [&#x200B; セグメント &#x200B;](../components/segments/seg-overview.md) 数。 |
| オーディエンス ID の数 | 20 百万 | システム強制ガードレール | オーディエンスあたりの最大 ID 数。 |
| オーディエンスの更新頻度 | 4 | システム強制ガードレール | [&#x200B; オーディエンス &#x200B;](../components/audiences/audiences-overview.md) が更新される最大頻度（時間単位）です。 |
| オーディエンス更新ルックバックウィンドウ | 90 | システム強制ガードレール | 更新ルックバックウィンドウの最大日数です。 |
| オーディエンスの有効期限を更新中 | 13 | システム強制ガードレール | オーディエンスが作成日から更新されなくなる最大月数。 お客様は、この機能をさらに 13 か月間延長できます。 |
| オーディエンスの更新数 | 75、150 | システム強制ガードレール | 更新するオーディエンスの最大数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |

{style="table-layout:auto"}

Experience Platform[Real-time Customer Data Platform ガードレール &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/guardrails/overview) も参照してください。


## データセットの自動有効期限

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|:---:|
| 作業指示 | 20 | システム強制ガードレール | 1 か月あたりの自動データセット有効期限作業指示の最大数。 |

{style="table-layout:auto"}



## 接続、データビュー、プロジェクト

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| プロジェクト | 50,000 | システム強制ガードレール | 組織のプロジェクトの最大数。 |
| データビュー | 2,000 | システム強制ガードレール | 組織の [&#x200B; データビュー &#x200B;](../data-views/data-views.md) の最大数。 |
| データビュー | 500-1000 | システム強制ガードレール | 接続のデータビューの最大数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |
| データセット | 100 | システム強制ガードレール | 接続あたりの最大 [&#x200B; データセット &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja) 数。 |
| 接続 | 1000 | システム強制ガードレール | 組織の [&#x200B; 接続 &#x200B;](../connections/overview.md) の最大数。 |
| 接続タイトル | 500 | システム強制ガードレール | 接続タイトルの最大文字数。 |
| 指標 | 5,000 | システム強制ガードレール | データビュー内の指標の最大数。 |
| ディメンション | 5,000 | システム強制ガードレール | データビューの最大ディメンション数。 |
| 注釈のタイトル | 100 | システム強制ガードレール | 注釈タイトルの最大文字数。 |
| 注釈の説明 | 250 | システム強制ガードレール | 注釈の説明の最大文字数。 |
| スキーマフィールド | 10 | システム強制ガードレール | [&#x200B; 派生フィールド &#x200B;](../data-views/derived-fields/derived-fields.md) のルールを定義する際のスキーマフィールドの最大数（標準フィールドを除く）。 |
| ルックアップ/プロファイルフィールド | 3 | システム強制ガードレール | 派生フィールドのルールを定義する際の、スキーマフィールドの最大数（標準フィールドを除く）内の参照またはプロファイルスキーマフィールドの最大数。 |
| 派生フィールド | 100～500 | システム強制ガードレール | 接続あたりの派生フィールドの最大数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |

{style="table-layout:auto"}


## データ転送の制限

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| フィールド | 10,000 | システム強制ガードレール | データセットの 1 行あたりのプロパティまたはフィールドの最大数。 |
| 一意の文字列 | 1,000 万～ 10 億 | システム強制ガードレール | ルックアップデータセットあたりの一意のキーの最大数。 Customer Journey Analytics パッケージに依存します（製品説明を参照）。<ul><li>基礎：1,000 万。</li><li>1 億を選択します。</li><li>Prime: 5 億。</li><li>Ultimate: 10 億</li><ul> |
| ユーザーあたりの行数 | 100 万 | システム強制ガードレール | 接続内の特定の月における一意のユーザー ID あたりの最大行数。 |
| 1 日あたりの行数 | 25 億 | パフォーマンスガードレール | 接続の 1 日あたりの最大平均行数。 |
| 行サイズ | 2 | パフォーマンスガードレール/システム適用ガードレール | Customer Journey Analyticsに取り込まれるデータの行あたりの平均サイズ（キロバイト単位）です（ソフトリミット）。 行サイズの静的制限は、Experience Platformでのデータ取り込みのガードレールによって決定されます。 |

{style="table-layout:auto"}

Experience Platform[&#x200B; データ取り込みのガードレール &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=ja) も参照してください。


## 宛先データの書き出し

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| データの書き出し | 許可された Data Lake ストレージの合計 | パフォーマンスガードレール | お客様は、宛先データセットの書き出しを使用して、許可されたデータレイクストレージの合計に達するまで、データレイクの顧客データを書き出すことができます。 |
| 使用可能なデータセット | プロファイルとイベント | システム強制ガードレール | ソース、Web SDK、Mobile SDK、Analytics Data Connector およびAudience Managerを使用してデータを取り込みまたは収集した後、Experience Platform UI で作成されたイベント、プロファイルまたは参照データセット。 |

{style="table-layout:auto"}

Experience Platform[&#x200B; データセット書き出しガードレール &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/guardrails#dataset-exports) も参照してください。


## データランディングゾーン

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| サンドボックスごとのデータランディングゾーン | 1 | システム強制ガードレール | サンドボックスあたりのデータランディングゾーンの最大数。 |
| データストレージ | 7 | システム強制ガードレール | データがデータランディングゾーンに保存されてから削除されるまでの最大日数。 |

{style="table-layout:auto"}


## フィールドベースのステッチ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| ステッチされたデータセット | 5～50 | システム強制ガードレール | 顧客あたりのステッチされたデータセットの最大数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |
| バックフィルの長さ | 6 - 25 | システム強制ガードレール | バックフィルデータの最大月数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |
| ルックバックウィンドウ/再生頻度 | 1/1 ～ 30/7 | システム強制ガードレール | 日間/再生頻度の最大ルックバックウィンドウ。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |

{style="table-layout:auto"}


## グラフベースのステッチ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| ステッチされたデータセット | 15～50 | システム強制ガードレール | 顧客あたりのステッチされたデータセットの最大数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |
| バックフィルの長さ | 6 - 25 | システム強制ガードレール | バックフィルデータの最大月数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |
| ルックバックウィンドウ/再生頻度 | 1/1 ～ 30/7 | システム強制ガードレール | 日間/再生頻度の最大ルックバックウィンドウ。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |


## セグメントと計算指標

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| セグメントごとのコンテナ | 50 | システム強制ガードレール | セグメントあたりの最大コンテナ数。 |
| 計算指標あたりの指標 | 25 | システム強制ガードレール | 計算指標あたりの最大指標の数。 |
| セグメントごとの指標とディメンション | 25 | システム強制ガードレール | セグメントごとの一意の指標とディメンションの最大数。 |
| セグメントごとのネストされたコンテナ | 10 | システム強制ガードレール | セグメントあたりのネストされたコンテナの最大数。 |
| セグメントごとのルール数 | 100 | システム強制ガードレール | セグメントごとの最大ルール数。 |
| セグメントごとのDimensionごとの文字列比較 | 100 | システム強制ガードレール | セグメントごとのディメンションごとの最大文字列比較数。 |
| 計算指標 | 6,000 | システム強制ガードレール | 組織の計算指標の最大数。 |
| セグメント | 50,000 | システム強制ガードレール | 組織に対して定義できるセグメントの最大数。 |
| API 呼び出し | 120 | システム強制ガードレール | 1 分あたりの API リクエスト数（6 秒ごとに 12 件のリクエスト）。 |

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
| ワークブックのファイルサイズ | 5 | システム強制ガードレール | スケジュールされたワークブックの最大ファイルサイズ（MB 単位）。 |
| データブロック | 1000 | システム強制ガードレール | ワークブックあたりの最大 [&#x200B; データブロック &#x200B;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=ja) 数。 |
| 指標 | 20 | システム強制ガードレール | データブロックあたりの最大指標の数。 |
| 日付範囲スパン | 13 | システム強制ガードレール | 日付範囲がデータブロックごとに適用できる最大月数。 |
| 行 | 50,000 | システム強制ガードレール | データブロックあたりの最大行数。 |

{style="table-layout:auto"}


## 完全なテーブルの書き出し

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| レポートあたりの行数 | 300 万～ 3 億 | システム強制ガードレール | レポートあたりのレポート行の最大数。 値は、Customer Journey Analytics パッケージによって異なります（製品説明を参照）。 |
| テーブルごとの分類 | 5 | システム強制ガードレール | テーブルあたりの分類の最大数。 |
| テーブルあたりの指標 | 5 | システム強制ガードレール | テーブルあたりの最大指標の数。 |
| スケジュール頻度 | 1 | システム強制ガードレール | 書き出しは、1 日に 1 回（1）または長いスケジュール（例：2 日ごとに 1 回、毎週）でスケジュールできます。 |

{style="table-layout:auto"}


## 共有指標と共有ディメンション

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| 共有ライブラリ | 1 | システム強制ガードレール | 接続の共有ライブラリの最大数。 |
| 共有指標 | 10,000 | システム強制ガードレール | 共有ライブラリごとの共有指標の最大数。 |
| 共有ディメンション | 10,000 | システム強制ガードレール | 共有ライブラリごとの共有次元の最大数。 |

{style="table-layout:auto"}


## Data Insights エージェント

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| データビュー | 50 | システム強制ガードレール | Data Insights Agentに対して有効にできるデータビューの最大数。 その他のデータビューが有効になっている場合、Data Insights Agentで使用できるのは最も使用されているデータビューのみです。 このガードレールは、[&#x200B; 接続または組織内に定義できるデータビューの最大数を定義するガードレール &#x200B;](#connections-data-views-projects) には影響しません。 |


## Customer Journey Analytics B2B Edition

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| レポート可能なビジネスユーザープロファイル （BPP） レポート可能な行 | 100 万 | パフォーマンスガードレール | レポート可能なビジネスユーザープロファイル 1000 件あたりのレポート可能な平均行数。 |




## 待ち時間

>[!NOTE]
>
>以下の処理時間は、契約上のサービスレベル契約（SLA）ではなく、ガードレールです。 待ち時間は、お客様の構成、データ量、および消費者アプリケーションによって異なります。 多くの場合、実際の処理時間は短縮されます。 具体的な契約条件と SLA については、Customer Journey Analytics契約を参照してください。 詳しくは、Experience Platform[&#x200B; データ取り込みのガードレール &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=ja) を参照してください。

| データフロー | 予想遅延時間 |
|---|---|
| Adobe Analytics/Adobe Analytics Source コネクタ（A4T 対応） | &lt; 30 分 |
| Adobe Analytics Source Connector からリアルタイム顧客プロファイルへ（A4T が無効） | &lt; 2 分 |
| Adobe Analytics Source Connector からリアルタイム顧客プロファイルへ（A4T 対応） | &lt; 30 分 |
| Edge Networkまたはストリーミング取り込みからのデータレイクへのデータ取り込み | &lt; 60 分 |
| Adobe Analytics Source コネクタからのデータレイクへのデータ取り込み | &lt; 2.25 時間 |
| Data Lake からCustomer Journey Analyticsへのデータ取り込み | &lt; 90 分 |
| ステッチ（オプション機能。詳しくは [&#x200B; ステッチの概要 &#x200B;](../stitching/overview.md) を参照してください） | &lt; 4 時間 |
| Adobe Analytics Source コネクタのバックフィルが 100 億未満のイベント（最大 13 か月分の履歴データ） | &lt; 4 週間 |
| ストリーミングセグメントの自動作成やセグメントでのデータの受信準備など、リアルタイム顧客プロファイルへのオーディエンスの公開。 | ≈ 60 分 |
| オーディエンスの更新頻度 | 1 回限りの更新：5 分未満の待ち時間。<br/>4 時間ごと、日次、週次、月次の更新（待ち時間は更新率と密接に関連しています）。 |

| リアルタイムレポートの待ち時間 | 予想遅延時間 |
|---|---|
| Edge NetworkへのEdge Network SDK/API | &lt; 7 分 |
| ストリーミングコネクタ | &lt; 17 分 |
| Adobe Analytics ソースコネクタ | &lt; 17 分 |
| その他のソースコネクタ（バッチデータを含む） | &lt; 25 時間 |

{style="table-layout:auto"}
