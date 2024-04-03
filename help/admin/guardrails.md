---
title: Customer Journey Analyticsガードレール
description: Customer Journey Analyticsのガードレールの詳細
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: eca9b101cea489b77af0ec5287ff96907e637d1e
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 11%

---

# Customer Journey Analyticsガードレール

このドキュメントでは、Customer Journey Analyticsの様々なコンポーネントに対する制限を示します。 ガードレール、スコーピングパラメーターおよび権限については、 [Customer Journey Analyticsの製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html) または [Adobe Analytics Add-on の製品説明：Customer Journey Analytics](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## 上限のタイプ

このドキュメントでは、次の 2 種類のデフォルトの上限について説明します。

| ガードレールのタイプ | 説明 |
|----------|---------|
| **パフォーマンスガードレール（ソフト制限）** | パフォーマンスガードレールは、使用例の範囲に関連する使用制限です。 パフォーマンス Guardrail を超えると、パフォーマンスが低下し、待ち時間が発生する場合があります。 Adobeは、そのようなパフォーマンスの低下に対して責任を負いません。 パフォーマンスを常に上回るお客様 Guardrail は、パフォーマンスの低下を避けるために、追加の容量をライセンスする場合があります。 |
| **システムが適用するガードレール（ハード制限）** | システムが適用するガードレールは、Customer Journey AnalyticsUI または API によって適用されます。 これらの制限は、UI および API ブロックが超えたり、エラーが返されたりするので、これらの制限を超えることはできません。 |

{style="table-layout:auto"}

機能の一部と、その制限に関連する値は、使用権限のあるCustomer Journey Analyticsパッケージによって異なります。

>[!NOTE]
>
>このドキュメントで概要を説明する値は、製品の継続的な改善に基づいて変更される場合があります。 定期的に更新を確認してください。 カスタム制限の詳細については、カスタマーケア担当者にお問い合わせください。

## アドホック SQL クエリ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| もう一度タイムアウトを試す | 90 | システムが適用するガードレール | 結果を返すのに時間がかかりすぎる（他の同時リクエストが原因の場合もある）というレポートエンジンからの応答までの最大秒数。再度リクエストすることができます。 |
| 再試行しないタイムアウト | 600 | システムが適用するガードレール | Ad Hoc SQL クエリがタイムアウトするまでの最大秒数。 これ以外の場合は、リクエストが結果を返すのに時間がかかりすぎたとレポートエンジンがレポートを返すまでの最大秒数です。再試行しないでください。 リクエストは、バックグラウンドプロセスでの問題が原因で結果を返すことがほとんどありません。 |
| 指標 | 150 | システムが適用するガードレール | リクエストの指標の最大数。 |
| インタラクティブクエリ出力行 | 50,000 | システムが適用するガードレール | 特に指定のない限り、返されるデフォルトの行数。 |

{style="table-layout:auto"}

## Analysis Workspace projects

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| 表ごとに表示される行数 | 400 | システムが適用するガードレール | Analysis Workspaceプロジェクトの任意のフリーフォームテーブルに表示できる最大行数。 |
| 表ごとに書き出し可能な行数 | 50,000 | システムが適用するガードレール | 単一のディメンションごとにエクスポートできる最大行数。 |
| プロジェクトごとのパネル | 15 | システムが適用するガードレール | 最大数： [パネル](../analysis-workspace/home.md#panels) プロジェクトごと。 |
| パネルあたりのビジュアライゼーション数 | 25 | システムが適用するガードレール | 最大数： [ビジュアライゼーション](../analysis-workspace/home.md#visualizations) パネルごと。 |
| フリーフォームテーブルごとの派生フィールド | 5 | システムが適用するガードレール | 単一のフリーフォームテーブルでの様々な派生フィールドの最大数。 |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## オーディエンス

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| オーディエンスフィルター | 20 | システムが適用するガードレール | 最大数： [フィルター](../components/filters/filters-overview.md) オーディエンスごと。 |
| オーディエンス ID の数 | 2 千万 | システムが適用するガードレール | オーディエンスあたりの ID の最大数。 |
| オーディエンス更新頻度 | 4 | システムが適用するガードレール | 最大頻度（時間単位、1 時間単位） [audience](../components/audiences/audiences-overview.md) 更新される可能性があります。 |
| オーディエンス更新のルックバックウィンドウ | 90 | システムが適用するガードレール | 更新ルックバックウィンドウの最大日数。 |
| オーディエンスの有効期限を更新しています | 13 | システムが適用するガードレール | オーディエンスの最大月数は、作成日から更新されなくなります。 お客様は、この機能をさらに 13 ヶ月延長できます。 |
| 更新するオーディエンスの数 | 75, 100 | システムが適用するガードレール | オーディエンスの更新の最大数。値は、パッケージによって異なります（製品の説明を参照）。 |

{style="table-layout:auto"}

関連項目：Experience Platform [Real-time Customer Data Platform Guardrails](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=ja).


## データセットの有効期限の自動化

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|:---:|
| 作業指示 | 20 | システムが適用するガードレール | 1 ヶ月あたりの自動データセット有効期限作業指示の最大数。 |

{style="table-layout:auto"}



## 接続、データビュー、プロジェクト

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| プロジェクト | 50,000 | システムが適用するガードレール | 組織のプロジェクトの最大数。 |
| データビュー | 2,000 | システムが適用するガードレール | 最大数： [データビュー](../data-views/data-views.md) （組織の場合） |
| データビュー | 50 | システムが適用するガードレール | 接続の最大データビュー数 |
| データセット | 100 | システムが適用するガードレール | 最大数： [データセット](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja) 接続ごと。 |
| 接続 | 1000 | システムが適用するガードレール | 最大数： [接続](../connections/overview.md) （組織の場合） |
| 接続のタイトル | 500 | システムが適用するガードレール | 接続タイトルの最大文字数。 |
| 指標 | 5,000 | システムが適用するガードレール | データビューの最大指標数。 |
| ディメンション | 5,000 | システムが適用するガードレール | データビューの最大ディメンション数。 |
| 注釈タイトル | 100 | システムが適用するガードレール | 注釈タイトルの最大文字数。 |
| 注釈の説明 | 250 | システムが適用するガードレール | 注釈の説明の最大文字数。 |
| スキーマフィールド | 10 | システムが適用するガードレール | のルールを定義する際のスキーマフィールドの最大数（標準フィールドを除く） [派生フィールド](../data-views/derived-fields/derived-fields.md). |
| 参照/プロファイルフィールド | 3 | システムが適用するガードレール | 派生フィールドのルールを定義する際の、スキーマフィールド（標準フィールドを含まない）の最大数内でのルックアップまたはプロファイルスキーマフィールドの最大数。 |
| 派生フィールド | 100 | システムが適用するガードレール | 接続ごとの派生フィールドの最大数。 |

{style="table-layout:auto"}


## データ転送の制限

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| フィールド | 10,000 | システムが適用するガードレール | データセット内の 1 行あたりのプロパティまたはフィールドの最大数。 |
| 一意の文字列 | 1,000 万 | システムが適用するガードレール | ルックアップデータセットあたりの一意のキーの最大数。 |
| 行 | 100 万 | システムが適用するガードレール | 接続内の特定の月の一意のユーザー ID ごとの最大行数。 |
| 行サイズ | 2 | パフォーマンスガードレール/システムが適用するガードレール | Customer Journey Analyticsに取り込まれるデータの 1 行あたりの平均サイズ（キロバイト）（ソフト制限）。 行サイズの静的制限は、Guardrails で決定され、Experience Platformでのデータ取り込みに使用されます。 |

{style="table-layout:auto"}

関連項目：Experience Platform [データ取り込みのガードレール](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html).


## データランディングゾーン

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| サンドボックスごとのデータランディングゾーン | 1 | システムが適用するガードレール | サンドボックスあたりの最大データランディングゾーン数。 |
| データストレージ | 7 | システムが適用するガードレール | 削除される前にデータがデータランディングゾーンに保存される最大日数。 |

{style="table-layout:auto"}


## フィールドベースのステッチ

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| ステッチされたデータセット | 10 | システムが適用するガードレール | 顧客ごとのステッチ済みデータセットの最大数。値は、該当するCustomer Journey Analyticsパッケージに応じて異なります（該当する製品の説明を参照）。 |
| データのバックフィル | 60 | システムが適用するガードレール | バックフィルデータの最大日数。 |

{style="table-layout:auto"}


## フィルターと計算指標

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| フィルターごとのコンテナ | 50 | システムが適用するガードレール | フィルターあたりの最大コンテナ数。 |
| 計算指標あたりの指標 | 25 | システムが適用するガードレール | 計算指標あたりの最大指標数。 |
| フィルターごとの指標とDimension | 25 | システムが適用するガードレール | フィルターあたりの一意の指標およびディメンションの最大数。 |
| フィルターごとのネストされたコンテナ | 10 | システムが適用するガードレール | フィルターあたりのネストされたコンテナの最大数。 |
| フィルターごとのルール | 100 | システムが適用するガードレール | フィルターあたりのルールの最大数。 |
| 文字列フィルターごとのDimensionごとの比較 | 100 | システムが適用するガードレール | フィルターごとのディメンションごとの文字列比較の最大数。 |
| 計算指標  | 6,000 | システムが適用するガードレール | 組織の計算指標の最大数。 |
| フィルター | 50,000 | システムが適用するガードレール | 組織に対して定義できるフィルターの最大数。 |
| API 呼び出し | 120 | システムが適用するガードレール | 1 分あたりの API リクエスト数（6 秒ごとに 12 リクエスト）。 |

{style="table-layout:auto"}


## モバイルアプリケーション

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| タイル | 16 | システムが適用するガードレール | スコアカードあたりの最大タイル数。 |
| フィルター | 10 | システムが適用するガードレール | スコアカードあたりの最大フィルター数。 |
| ディメンション | 10 | システムが適用するガードレール | スコアカードあたりの最大ディメンション数。 |

{style="table-layout:auto"}

## Report Builder

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| ワークブックのファイルサイズ | 5 | システムが適用するガードレール | スケジュールされたワークブックの最大ファイルサイズ（MB 単位）。 |
| データブロック | 1000 | システムが適用するガードレール | 最大数： [データブロック](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=ja) ワークブックごと。 |
| 指標 | 20 | システムが適用するガードレール | データブロックあたりの最大指標数。 |
| 日付範囲の範囲の範囲 | 13 | システムが適用するガードレール | データブロックごとに日付範囲を設定できる最大月数。 |
| 行 | 50,000 | システムが適用するガードレール | データブロックあたりの最大行数。 |

{style="table-layout:auto"}


## 完全なテーブルの書き出し

| 名前 | 値 | 上限のタイプ | 説明 |
|---|--:|---|---|
| レポートあたりの行数 | 300 万～ 3 億 | システムが適用するガードレール | レポートあたりのレポート行の最大数。値は、該当するCustomer Journey Analyticsパッケージ（該当する製品の説明を参照）に応じて異なります。 |
| テーブルごとの分類 | 5 | システムが適用するガードレール | テーブルあたりの分類の最大数。 |
| テーブルあたりの指標 | 5 | システムが適用するガードレール | テーブルあたりの最大指標数。 |
| スケジュールの頻度 | 1 | システムが適用するガードレール | エクスポートは、1 日に 1 回、または長いスケジュール（2 日に 1 回、毎週など）でスケジュールできます。 |

{style="table-layout:auto"}

## 待ち時間

>[!NOTE]
>
>以下の処理時間は、契約上の SLA(Service Level Agreement) ではなく、Guardrail です。 遅延は、顧客の構成、データ量、消費者のアプリケーションによって異なります。 多くの場合、リアルタイム処理の時間が短くなります。 具体的な契約条件や SLA については、Customer Journey Analytics契約を参照してください。 Experience Platform [データ取り込みのガードレール](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html) を参照してください。

| データフロー | 予想遅延時間 |
|---|---|
| Adobe AnalyticsからAdobe Analyticsソースコネクタ（A4T 有効） | &lt; 30 分 |
| Adobe Analytics Source Connector to Real-time Customer Profile（A4T は無効） | &lt; 2 分 |
| Adobe Analytics Source Connector からリアルタイム顧客プロファイル（A4T 有効） | &lt; 30 分 |
| Edge ネットワークまたはストリーミング取り込みからデータレイクにデータを取り込む | &lt; 60 分 |
| Adobe Analytics Source Connector からデータレイクにデータを取り込む | &lt; 2.25 時間 |
| データレイクからCustomer Journey Analyticsへのデータ取り込み | &lt; 90 分 |
| ステッチ ( オプション機能： [ステッチの概要](../stitching/overview.md) （詳細情報） | &lt; 3.25 時間 |
| 100 億イベント未満のAdobe Analytics Source Connector バックフィル（最大 13 ヶ月の履歴データ） | &lt; 4 週間 |
| ストリーミングセグメントの自動作成や、セグメントがデータを受け取る準備ができている状態でのオーディエンスをリアルタイム顧客プロファイルに公開する機能。 | ≈ 60 分 |
| オーディエンスの頻度を更新 | 1 回の更新：5 分未満の待ち時間。<br/>4 時間ごと、日別、週別、月別に更新します（遅延は更新率と連携します）。 |

{style="table-layout:auto"}
