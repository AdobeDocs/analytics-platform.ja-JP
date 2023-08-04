---
title: Customer Journey Analytics の機能のサポート
description: Customer Journey Analytics の機能と Adobe Analytics の機能セットの比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 264b5a3d3793ab6531f570d83cbd4fd96bfbd67a
workflow-type: tm+mt
source-wordcount: '2089'
ht-degree: 37%

---

# Adobe Customer Journey Analyticsの機能サポート

次の表に、Adobe Analyticsのどの機能がCustomer Journey Analyticsでサポートされ、一部がサポートされている、またはサポートされていない、およびAdobe Analyticsでサポートされていない、または使用できないCustomer Journey Analyticsの機能を示します。 これらのリストは、時間の経過と共に、機能がCustomer Journey Analyticsに追加されると変化します。

## 完全にサポートされる機能／コンポーネント {#full-support}

| Adobe Analytics 機能 | サポートに関するメモ |
| --- | --- |
| 異常値検出 | フルサポート |
| Attribution IQ | フルサポート |
| 計算指標 | フルサポート。従来のAnalysis Workspaceの既存の計算指標は、Customer Journey Analyticsに移植されません。 |
| カレンダーイベント | フルサポート。カレンダーイベントは、ワークスペースの[注釈](/help/components/annotations/overview.md)として実装されています。 |
| CSV のダウンロード | フルサポート |
| カスタムカレンダー | フルサポート |
| 日付の比較 | フルサポート |
| 日付範囲 | すべての日付範囲機能がサポートされています。 |
| ディメンション | フルサポート。Customer Journey Analyticsは XDM を使用し、無制限のディメンションをサポートします。 Customer Journey Analyticsは、従来のAdobe Analyticsのカスタム eVar や prop とは結び付けられません。 |
| GDPR の削除 | フルサポート。GDPR は、[!UICONTROL Adobe Experience Platform] と連携して処理されることに注意してください。Customer Journey Analyticsは、データの変更をすべて継承します [!UICONTROL Experience Platform] は基盤となるデータセットに対してを実行します。 |
| リフトおよび信頼性レポート | [実験パネル](/help/analysis-workspace/c-panels/experimentation.md)を介したフルサポート |
| リスト変数／リスト prop | フルサポート。Customer Journey Analyticsは XDM を使用し、listVars と同様に使用できる無制限の文字列配列をサポートします。 |
| マーチャンダイジング eVar | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)によるフルサポート |
| 指標 | フルサポート。Customer Journey Analyticsはエクスペリエンスデータモデル (XDM) を使用し、無制限の指標をサポートします。Adobe Analyticsのカスタム成功イベントとは関係ありません。 一部の標準指標の名前がAdobe Analyticsから変更されました。訪問者=人、訪問=セッション、ヒット=イベントです。 |
| モバイルスコアカード／ダッシュボード | フルサポート |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。 |
| PDF の書き出し | フルサポート |
| プロジェクトのキュレーション | フルサポート |
| プロジェクトリンク | フルサポート |
| レポート時の処理 | フルサポート。Customer Journey Analyticsは、レポート時間処理にのみ依存します。 |
| レポート API へのアクセス | 完全なサポート。 [Customer Journey AnalyticsAPI](https://developer.adobe.com/cja-apis/docs/). |
| 予定レポート／プロジェクト | フルサポート |
| セグメント | フルサポート。現在は「フィルター」と呼ばれています。従来のAnalysis Workspace内の既存のセグメントは、Customer Journey Analyticsに移植されません。 |
| 仮想レポートスイート | 完全なサポート。現在の呼び出し [データビュー](/help/data-views/create-dataview.md). |
| 仮想レポートスイートコンポーネントのキュレーション | フルサポート。データビューの一部になりました。 |
| ストリーミングメディア分析 | メディアデータは、Analytics ソースコネクタを Workspace のメディア同時ビューアパネルおよびメディア再生時間パネルの一部として使用できます。 |

{style="table-layout:auto"}

## 新しい方法でサポート {#new-support}

| 機能 | メモ |
| --- | --- |
| オーディエンスの公開（セグメントの公開） | アドビの Customer Data Platform または Journey Optimizer 製品のライセンスを持つ場合にサポートされます。[オーディエンス公開](/help/components/audiences/audiences-overview.md)は、Experience Platform のリアルタイム顧客プロファイルにオーディエンスを送信します。 |
| 分類 | 「ルックアップデータセット」という名称に変更されました。Analytics で使用される分類は、Analytics Classifications Source Connector を使用して、Experience PlatformおよびCustomer Journey Analyticsにインポートできます。 参照データセットは、Experience Platformに直接アップロードし、Customer Journey Analyticsで使用できるようにすることもできます。 |
| 分類ルールビルダー | を使用してサポート [substrings](/help/data-views/component-settings/substring.md) Customer Journey Analytics。 ルックアップデータセットではなく、レポート時に文字列操作を使用します。 |
| カスタムセッション | カスタムセッションは、 [セッション設定](../../data-views/create-dataview.md#session-settings) を選択します。 詳しくは、  [コンテキスト対応セッション](../../data-views/context-aware-sessions.md) を参照してください。 <br/>モバイルバックグラウンドイベントの処理は、Adobe Experience Platform Mobile SDK を通じてサポートされます。 詳しくは、 [Edge Network のライフサイクル](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) を参照してください。 |
| 通貨換算 | の一部としてサポート [指標コンポーネントのフォーマット](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) を選択します。 |
| マーチャンダイジング変数の持続性 | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)によるフルサポート |
| 顧客属性 | 現在は「プロファイルデータセット」と呼ばれ、Experience Cloudから自動的に読み込まれませんが、Customer Journey Analyticsに使用する前にExperience Platformにアップロードする必要があります。 |
| データフィード | データセットの第 1 世代のデータエクスポートは、 [Experience Platformデータアクセス API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) そして [Experience Platform先](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja). これらのオプションを使用すると、Experience Platformデータレイクに収集または取り込まれるすべてのデータを、イベント/行レベルで書き出すことができます。 POST 列はクエリ時に計算されるので、後処理のデータ列は使用できません。 投稿列のエクスポートは、レポートを通じて使用できます。 |
| 指標の重複排除 | データビュー内の指標に対して設定されるようになりました。指標の重複排除は、データセット、データビューまたは接続レベルではなく、ユーザーレベルまたはセッションレベルで行われます。 |
| 入口、出口、滞在時間の各ディメンションと指標 | サポート対象（現在、入口と出口は、「セッション開始」および「セッション終了」と呼ばれています）ですが、計算方法が多少異なります。 |
| eVar の永続性設定 | eVar はCustomer Journey Analyticsに含まれなくなりました。 ただし、永続性設定はデータビューの一部になり、すべてのディメンションで使用できます。永続性は、データ収集処理ではなく、レポート時の処理に基づいていることに注意してください。データビュー内で設定されるDimensionは、90 日間の最大永続性に制限され、無制限の永続性はサポートされません。 |
| IP の不明化 | Customer Journey Analyticsのお客様が Analytics ソースコネクタを使用してAdobe AnalyticsからCustomer Journey Analyticsにデータを入力する場合：Adobe Analyticsで適用される IP 難読化設定は、Customer Journey Analyticsデータをフロースルーします。 必要に応じて、Adobe Analytics でこれらの設定を制御できます。<p>Customer Journey Analyticsのお客様がExperience PlatformWeb SDK を使用してデータを Platform およびCustomer Journey Analyticsに直接入力する場合。 Platform の Data Prep for Data Collection を使用して、会社の要件に基づいて IP アドレスを難読化するルールを設定できます。 |
| 新規セッションとリピートセッションレポート | 以前は、訪問回数ディメンションを使用して達成されていました。新規セッションとリピートセッションは、[13 か月間のルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=ja)でサポートされています。 |
| products 変数 | Experience Platform から、データセットスキーマ内でオブジェクトタイプフィールドの配列を使用して、このユースケースを実現できます。Customer Journey Analytics内では、お客様は任意の数の製品変数を使用でき、Adobe Analyticsと同様に、1 つの変数に制限されません。 |
| プロジェクトの共有 | プロジェクトの共有は、Customer Journey Analyticsのユーザー間でのみサポートされます。Customer Journey Analyticsと従来のAnalysis Workspace間ではプロジェクトを共有しません。 |
| ビジュアライゼーション | マップビジュアライゼーションを除く、すべてのビジュアライゼーションがサポートされます。 |
| Report Builder（Excel プラグイン） | Excel 用の新しい Office 365 プラグインでサポートされます。 |
| ユーザー権限／データアクセス制御 | Customer Journey Analyticsは～を区別する [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja) 製品管理者、製品プロファイル管理者、ユーザー。 他のユーザーが作成した接続、プロジェクト、フィルターまたは計算指標を作成／更新／削除できるのは製品管理者のみで、製品管理者と製品プロファイル管理者は、データビューを編集できます。計算指標、フィルター、注釈の作成などに対する追加のユーザー権限を使用できます。 |
| 処理ルール、VISTA ルール、マーケティングチャネルの処理ルール | WebSDK ベースのデータセットと Analytics ソースコネクタのデータの両方に対するAdobe Experience Platform Data Prep 機能の使用がサポートされます。 |
| マーケティングチャネル | Analytics ソースコネクタを使用する場合、マーケティングチャネルのデータは、そのコネクタを介してCustomer Journey Analyticsに流れ込みます。 マーケティングチャネルのルールは、従来のAdobe Analyticsで設定され、一部のルールはサポートされていません。 詳しくは、 [Customer Journey Analyticsマーケティングチャネルドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>WebSDK の実装では、レポート時のマーケティングチャネルの処理ルールは、 [派生フィールド](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## 部分的なサポート {#partial}

| 機能 | メモ |
| --- | --- |
| クロスデバイス／クロスチャネルのステッチ | ID 情報を直接含むデータセット（「フィールドベースのステッチ」とも呼ばれます）でサポートされます。グラフベースのステッチは、まだサポートされていませんが、今後予定されています。詳しくは、 [ステッチ](../../stitching/overview.md). |
| ボットフィルタリング | の場合 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセットの場合、ボットフィルタリングが適用されます。 他のデータセットの一般的なボットフィルタリングロジックは、 [!UICONTROL Experience Platform] またはCustomer Journey Analytics。 |
| デバイス、ブラウザー、リファラー、技術の各ディメンション | サポート対象 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja) — ベースのデータセット。 参照： [ADC 経由でサポートされる Analytics 変数に関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ja).<p>Experience PlatformWeb SDK のデータ収集を使用する場合、デバイス参照に基づくデバイスとディメンションは、現在サポートされていません。 将来サポートされる予定です。 |
| 地理特性ディメンション | Adobe Analyticsで収集されるすべての地理特性/地理的機能は、 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja). Analytics ソースコネクタを使用せず、デジタルデータ収集にExperience PlatformWeb SDK を使用する実装では、 [Experience Edge Geo Lookup サービス](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja). |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。セグメント比較と Analytics for Target（A4T）パネルはサポートされていません。 |
| 処理ルール | Analytics ソースコネクタベースのデータセットの場合、処理ルールは引き続き適用されます。 [Adobe Experience Platform のデータ準備機能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) は、Platform に直接送信されるデータの処理ルールの代わりに使用することもできます。 |
| A4T | 部分的なサポートは、 [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja). Target のアクティビティとエクスペリエンスで、A4T のわかりやすい名前をサポートする予定です。 |

{style="table-layout:auto"}

## サポートなし、計画済み {#planned}

| 機能 | メモ |
| --- | --- |
| アラート | サポートが予定されています。 |
| 貢献度分析 | サポートが予定されています。 |
| Data Warehouseレポート | Analysis Workspace インターフェイスからのサポートが予定されています。Adobe Experience Platform [[!UICONTROL クエリサービス]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja>) には、Customer Journey Analyticsでのこれらの使用例に対するインターフェイスも用意されています。 |
| デバイスグラフでの ID のステッチ | サポートが予定されています。 |
| プロジェクトテンプレート | サポートが予定されています。 |
| リアルタイムレポート | サポートが予定されています。 |
| Segment IQ | サポートが予定されています。 |
| トランザクション ID データソース | サポートが予定されています。 |
| Adobe AnalyticsからCustomer Journey Analyticsへのプロジェクト/フィルター/計算指標の移行 | サポートが予定されています。 |
| 概要レベルデータソース | サポートが予定されています。 |

{style="table-layout:auto"}

## サポートはありません。まだ予定されていません {#not-planned}

| 機能 | メモ |
| --- | --- |
| Activity Map | まだサポートの予定はありません。 |
| Advertising Cloud | まだサポートの予定はありません。 |

{style="table-layout:auto"}

## サポートなし {#never}

* クロスデバイス Coop を使用した人物指標
* Reports &amp; Analytics のダッシュボード
* Reports &amp; Analytics のブックマーク
* Reports &amp; Analytics のターゲット

## Adobe Customer Journey Analyticsの機能はAdobe Analyticsでは使用できません {#cja-not-aa}

次の表に、Customer Journey Analyticsで使用できるが、Adobe Analyticsではサポートされていない機能を示します。

| 機能 | さらに詳細を表示 |
| --- | --- |
| あらゆる種類のデータの宿泊施設 | Customer Journey Analyticsは、Experience Platformがあらゆる種類のデータスキーマやデータタイプを保持する機能と組み合わされています。 使用 [エクスペリエンスデータモデル (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用すると、データを均等に表示および整理し、組み合わせや調査に対応できます。 Adobe Analyticsは、主に、Web およびモバイルの分析データに焦点を当て、 [データをインポート](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=ja). |
| 無制限の顧客Dimensionと指標 | Customer Journey Analyticsの寸法は無制限です。値は、数値、テキスト、オブジェクト、リスト、またはすべての組み合わせです。 Dimensionは、ネストすることも、階層化することもできます。 Analytics は、最大 75 個の prop および 250 個の eVar をサポートします。 |
| 基数/一意の値は無制限 | Customer Journey Analyticsは、単一のディメンション内でレポートできる、無制限の一意の値またはディメンション項目をサポートします。 Adobe Analyticsの一意の値は 500.000 個に制限されています。 一意の値やディメンションは無制限なので、現在大規模な Analytics の実装に存在しているレポートや分析の制限を取り除くことができます。 |
| レポート時間変換 | Customer Journey Analyticsのレポート時間変換（データビューとも呼ばれます）を使用すると、接続からのデータをさらに解釈できます。 再実装せずにデータを変更または削除できます。サブ文字列を使用してディメンションを操作し、任意の値から指標を作成します。サブ文字列を使用して、サブイベントをフィルタリングします。 変換はすべて非破壊的に行われます。 Adobe Analyticsは、仮想レポートスイートとセッション化を通じて、限られた機能を提供します。 |
| 実験分析 | Customer Journey Analyticsは、接続の一部として定義された任意のデータソースから、任意の実験の上昇率と信頼性を評価できます。 この評価により、あらゆるチャネルにまたがる顧客インタラクション間の原因と効果の関係を把握できます。 Analytics は、Analytics for Target(A4T) 統合を通じて、実験分析に制限されます。 |
| クロスデバイス分析 | Customer Journey Analyticsは、未認証セッションと認証済みセッションのデバイス固有のデータセットをシームレスに組み合わせることをサポートします。 Customer Journey Analyticsオファーでは、既知のデバイスに履歴データをバックフィルできます。 Analytics では、この機能は 1 つのレポートスイートに制限され、デバイスグラフの使用に制限されます。 |
| SQL アクセス | Customer Journey Analyticsは、「 Data Distiller 」オプションを使用して、Adobeのバックエンド処理で収集されるデータの制限を削除できます。 SQL を使用してデータを変更し、ビジネスに固有の値とデータセットを作成し、引き続き調査できます。 Analytics は、データへの SQL アクセスをサポートしていません。 |
| セキュリティとプライバシーに関するオプションの強化 — HIPAA 対応 | Customer Journey Analyticsは HIPAA に対応しており、規制への準拠に関する追加のセキュリティオプションを提供します。 Adobe Analyticsは HIPAA に対応していません。 |

{style="table-layout:auto"}
