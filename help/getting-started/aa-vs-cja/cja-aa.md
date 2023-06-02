---
title: Customer Journey Analytics の機能のサポート
description: Customer Journey Analytics の機能と Adobe Analytics の機能セットの比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 683ac8b741ed73eb301364331cebf187c8c91cd2
workflow-type: tm+mt
source-wordcount: '1953'
ht-degree: 54%

---

# Customer Journey Analytics の機能のサポート

次の表に、Adobe Analytics(AA) のどの機能がCustomer Journey Analytics(CJA) でサポートされている、一部がサポートされている、またはサポートされていない、および CJA のどの機能が AA でサポートされていない、または使用できないかを示します。 これらのリストは、時間が経過し、CJA に機能が追加されると変更されます。

## 完全にサポートされる機能／コンポーネント {#full-support}

| Adobe Analytics 機能 | サポートに関するメモ |
| --- | --- |
| 異常値検出 | フルサポート |
| Attribution IQ | フルサポート |
| 計算指標 | フルサポート。従来のAnalysis Workspaceの既存の計算指標は、CJA に移植されません。 |
| カレンダーイベント | フルサポート。カレンダーイベントは、ワークスペースの[注釈](/help/components/annotations/overview.md)として実装されています。 |
| CSV のダウンロード | フルサポート |
| カスタムカレンダー | フルサポート |
| 日付の比較 | フルサポート |
| 日付範囲 | すべての日付範囲機能がサポートされています。 |
| ディメンション | フルサポート。CJA は XDM を使用し、無制限のディメンションをサポートします。 CJA は、従来の Adobe Analytics のカスタム eVar や prop には結び付けられません。 |
| GDPR の削除 | フルサポート。GDPR は、[!UICONTROL Adobe Experience Platform] と連携して処理されることに注意してください。CJA は、[!UICONTROL Experience Platform] が基盤となるデータセットに加えたデータの変更をすべて継承します。 |
| リフトおよび信頼性レポート | [実験パネル](/help/analysis-workspace/c-panels/experimentation.md)を介したフルサポート |
| リスト変数／リスト prop | フルサポート。CJA は XDM を使用し、listVars と同様に使用できる無制限の文字列配列をサポートします。 |
| マーチャンダイジング eVar | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)によるフルサポート |
| 指標 | 完全なサポートCJA は、エクスペリエンスデータモデル (XDM) を使用し、無制限の指標をサポートします。従来の Analytics のカスタム成功イベントとは関係ありません。 一部の標準指標の名前が従来の Analytics から変更されました。訪問者=人、訪問=セッション、ヒット=イベント。 |
| モバイルスコアカード／ダッシュボード | フルサポート |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。 |
| PDF の書き出し | フルサポート |
| プロジェクトのキュレーション | フルサポート |
| プロジェクトリンク | フルサポート |
| レポート時の処理 | フルサポート。CJA は、レポート時の処理にのみ依存します。 |
| レポート API へのアクセス | フルサポート。[CJA API](https://developer.adobe.com/cja-apis/docs/) を通じて使用できます。 |
| 予定レポート／プロジェクト | フルサポート |
| セグメント | フルサポート。現在は「フィルター」と呼ばれています。従来のAnalysis Workspace内の既存のセグメントは CJA に移植されません。 |
| 仮想レポートスイート | フルサポート。現在の呼び出し [データビュー](/help/data-views/create-dataview.md). |
| 仮想レポートスイートコンポーネントのキュレーション | フルサポート。データビューの一部になりました。 |
| ストリーミングメディア分析 | メディアデータは、Analytics Data Connector を使用すると、Workspace のメディア同時視聴者数パネルおよびメディア再生滞在時間パネルの一部として使用できます。 |

{style="table-layout:auto"}

## 新しい方法でサポート {#new-support}

| 機能 | メモ |
| --- | --- |
| オーディエンスの公開（セグメントの公開） | アドビの Customer Data Platform または Journey Optimizer 製品のライセンスを持つ場合にサポートされます。[オーディエンス公開](/help/components/audiences/audiences-overview.md)は、Experience Platform のリアルタイム顧客プロファイルにオーディエンスを送信します。 |
| 分類 | 「ルックアップデータセット」という名称に変更されました。Analytics で使用される分類は、Analytics Classifications Source Connector を使用して Experience Platform および CJA にインポートできます。参照データセットは、Experience Platformに直接アップロードし、CJA で使用できるようにすることもできます。 |
| 分類ルールビルダー | CJA で[部分文字列](/help/data-views/component-settings/substring.md)を使用したサポートルックアップデータセットではなく、レポート時に文字列操作を使用します。 |
| カスタムセッション | モバイルバックグラウンドイベントを除く、すべてのカスタムセッション機能がサポートされます。 |
| マーチャンダイジング変数の持続性 | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)によるフルサポート |
| 顧客属性 | 現在は「プロファイルデータセット」と呼ばれ、Experience Cloudから自動的に読み込まれませんが、CJA で使用する前にExperience Platformにアップロードする必要があります。 |
| データフィード | データセットの第 1 世代のデータエクスポートは、 [Experience Platformデータアクセス API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) そして [Experience Platform先](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja). これらのオプションを使用すると、Experience Platformデータレイクに収集または取り込まれるすべてのデータを、イベント/行レベルで書き出すことができます。 POST 列はクエリ時に計算されるので、後処理のデータ列は使用できません。 投稿列のエクスポートは、レポートを通じて使用できます。 |
| 指標の重複排除 | データビュー内の指標に対して設定されるようになりました。指標の重複排除は、データセット、データビューまたは接続レベルではなく、ユーザーレベルまたはセッションレベルで行われます。 |
| 入口、出口、滞在時間の各ディメンションと指標 | サポート対象（現在、入口と出口は、「セッション開始」および「セッション終了」と呼ばれています）ですが、計算方法が多少異なります。 |
| eVar の永続性設定 | eVar は CJA に含まれなくなりました。ただし、永続性設定はデータビューの一部になり、すべてのディメンションで使用できます。永続性は、データ収集処理ではなく、レポート時の処理に基づいていることに注意してください。データビュー内で設定されるDimensionは、90 日間の最大永続性に制限され、無制限の永続性はサポートされません。 |
| IP の不明化 | Analytics ソースコネクタを使用している CJA の顧客が Adobe Analytics から CJA にデータを入力する場合：Adobe Analytics で適用された IP の不明化設定は、CJA データを通じて送られます。必要に応じて、Adobe Analytics でこれらの設定を制御できます。<p>Experience PlatformWeb SDK を使用してデータを Platform および CJA に直接入力する CJA のお客様向けです。 Platform の Data Prep for Data Collection を使用して、会社の要件に基づいて IP アドレスを難読化するルールを設定できます。 |
| 新規セッションとリピートセッションレポート | 以前は、訪問回数ディメンションを使用して達成されていました。新規セッションとリピートセッションは、[13 か月間のルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=ja)でサポートされています。 |
| products 変数 | Experience Platform から、データセットスキーマ内でオブジェクトタイプフィールドの配列を使用して、このユースケースを実現できます。CJA 内では、顧客は任意の数の製品変数を使用でき、Adobe Analyticsと同様に 1 つの変数に制限されません。 |
| プロジェクトの共有 | プロジェクトの共有は、CJA のユーザー間でのみサポートされます。CJA と従来の Analysis Workspace 間ではプロジェクトは共有されません。 |
| ビジュアライゼーション | マップビジュアライゼーションを除く、すべてのビジュアライゼーションがサポートされます。 |
| Report Builder（Excel プラグイン） | Excel 用の新しい Office 365 プラグインでサポートされます。 |
| ユーザー権限／データアクセス制御 | CJA は [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja) 製品管理者、製品プロファイル管理者およびユーザーを区別します。他のユーザーが作成した接続、プロジェクト、フィルターまたは計算指標を作成／更新／削除できるのは製品管理者のみで、製品管理者と製品プロファイル管理者は、データビューを編集できます。計算指標、フィルター、注釈の作成などに対する追加のユーザー権限を使用できます。 |
| 処理ルール、VISTA ルール、マーケティングチャネルの処理ルール | WebSDK ベースのデータセットと Analytics Data Connector からのデータの両方に対するAdobe Experience Platform Data Prep 機能の使用がサポートされます。 |
| マーケティングチャネル | Analytics Source Connector を使用する場合、マーケティングチャネルのデータは、そのコネクタを介して CJA に送られます。 マーケティングチャネルのルールは、従来のAdobe Analyticsで設定され、一部のルールはサポートされていません。 詳しくは、[CJA マーケティングチャネルのドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html)を参照してください。<br/>WebSDK の実装では、レポート時のマーケティングチャネルの処理ルールは、 [派生フィールド](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## 部分的なサポート {#partial}

| 機能 | メモ |
| --- | --- |
| クロスデバイス／クロスチャネルのステッチ | ID 情報を直接含むデータセット（「フィールドベースのステッチ」とも呼ばれます）でサポートされます。グラフベースのステッチは、まだサポートされていませんが、今後予定されています。[クロスチャネル分析](/help/cca/overview.md)を参照してください。 |
| ボットフィルタリング | [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセットには、ボットフィルタリングが適用されます。他のデータセットの一般的なボットフィルタリングロジックは、[!UICONTROL Experience Platform] または CJA では実行されません。 |
| デバイス、ブラウザー、リファラー、技術の各ディメンション | [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセットでサポートされます。参照： [ADC 経由でサポートされる Analytics 変数に関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ja).<p>Experience PlatformWeb SDK のデータ収集を使用する場合、デバイス参照に基づくデバイスとディメンションは、現在サポートされていません。 将来サポートされる予定です。 |
| 地理特性ディメンション | Adobe Analytics に収集されたすべての地理特性／地域情報は、[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を通じて CJA に送られます。Analytics ソースコネクタを使用せず、デジタルデータ収集にExperience PlatformWeb SDK を使用する実装では、 [Experience Edge Geo Lookup サービス](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja). |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。セグメント比較と Analytics for Target（A4T）パネルはサポートされていません。 |
| 処理ルール | Analytics ソースコネクタベースのデータセットの場合、処理ルールは引き続き適用されます。[Adobe Experience Platform のデータ準備機能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) は、Platform に直接送信されるデータの処理ルールの代わりに使用することもできます。 |
| A4T | [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)のフィールドを通じて一部サポートされます。Target のアクティビティとエクスペリエンスで、A4T のわかりやすい名前をサポートする予定です。 |

{style="table-layout:auto"}

## サポートなし、計画済み {#planned}

| 機能 | メモ |
| --- | --- |
| アラート | サポートが予定されています。 |
| 貢献度分析 | サポートが予定されています。 |
| Data Warehouseレポート | Analysis Workspace インターフェイスからのサポートが予定されています。また、Adobe Experience Platform [[!UICONTROL クエリサービス]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja>)でも、CJA におけるこれらのユースケースに対応するインターフェイスを提供しています。 |
| デバイスグラフでの ID のステッチ | サポートが予定されています。 |
| プロジェクトテンプレート | サポートが予定されています。 |
| リアルタイムレポート | サポートが予定されています。 |
| Segment IQ | サポートが予定されています。 |
| 通貨換算 | サポートが予定されています。 |
| トランザクション ID データソース | サポートが予定されています。 |
| AA から CJA へのプロジェクト／フィルター／計算指標の移行 | サポートが予定されています。 |
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

## CJA 機能は、Adobe Analyticsでは使用できません {#cja-not-aa}

次の表に、Customer Journey Analytics(CJA) で使用できる機能のうち、Adobe Analytics(AA) ではサポートされない機能を示します。

| 機能 | さらに詳細を表示 |
| --- | --- |
| あらゆる種類のデータの宿泊施設 | CJA は、あらゆる種類のExperience Platformスキーマやデータタイプを保持するデータの機能と組み合わされています。 使用 [エクスペリエンスデータモデル (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用すると、データを均等に表示および整理し、組み合わせや調査に対応できます。 Adobe Analyticsは、主に、Web およびモバイルの分析データに焦点を当て、 [データをインポート](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=ja). |
| 無制限の顧客Dimensionと指標 | CJA ディメンションは無制限です。値には、数値、テキスト、オブジェクト、リスト、またはすべての組み合わせを指定できます。 Dimensionは、ネストすることも、階層化することもできます。 Analytics は、最大 75 個の prop および 250 個の eVar をサポートします。 |
| 基数/一意の値は無制限 | CJA は、単一のディメンション内でレポートできる、無制限の一意の値またはディメンション項目をサポートします。 AA の一意の値は 500.000 個に制限されています。 一意の値やディメンションは無制限なので、現在大規模な Analytics の実装に存在しているレポートや分析の制限を取り除くことができます。 |
| レポート時間変換 | CJA のレポート時間変換（データビューと呼ばれる）を使用すると、接続からのデータをさらに解釈できます。 再実装せずにデータを変更または削除できます。サブ文字列を使用してディメンションを操作する。任意の値から指標を作成する。サブイベントをフィルターします。 変換はすべて非破壊的に行われます。 Adobe Analyticsは、仮想レポートスイートとセッション化を通じて、限られた機能を提供します。 |
| 実験分析 | CJA は、接続の一部として定義された任意のデータソースから、任意の実験の上昇率と信頼性を評価できます。 この評価により、あらゆるチャネルにまたがる顧客インタラクション間の原因と効果の関係を把握できます。 Analytics は、Analytics for Target(A4T) 統合を通じて、実験分析に制限されます。 |
| クロスデバイス分析 | CJA は、未認証セッションと認証済みセッションのデバイス固有のデータセットのシームレスな組み合わせをサポートします。 CJA オファーは、既知のデバイスに履歴データをバックフィルします。 Analytics では、この機能は 1 つのレポートスイートに制限され、デバイスグラフの使用に制限されます。 |
| SQL アクセス | CJA は、「 Data Distiller 」オプションを使用して、Adobeのバックエンド処理で収集されるデータの制限を削除できます。 SQL を使用してデータを変更し、ビジネスに固有の値とデータセットを作成し、引き続き調査できます。 Analytics は、データへの SQL アクセスをサポートしていません。 |
| セキュリティとプライバシーに関するオプションの強化 — HIPAA 対応 | CJA は HIPAA に対応しており、規制への準拠に関する追加のセキュリティオプションを提供します。 Adobe Analyticsは HIPAA に対応していません。 |

{style="table-layout:auto"}
