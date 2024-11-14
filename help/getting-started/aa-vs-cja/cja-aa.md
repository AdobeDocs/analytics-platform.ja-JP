---
title: Customer Journey Analytics の機能のサポート
description: Customer Journey Analytics の機能と Adobe Analytics の機能セットの比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 1cf7ae6635f51f0ca06cbc235032525e3d9b3fec
workflow-type: tm+mt
source-wordcount: '2320'
ht-degree: 99%

---

# Customer Journey Analytics の機能のサポート

次の表に、Customer Journey Analytics に一意の機能と、Customer Journey Analytics でサポートされている、部分的にサポートされている、またはサポートされていない Adobe Analytics を示します。これらのリストは、Customer Journey Analytics に機能が追加されるにつれて変更されます。

## Adobe Customer Journey Analytics に一意の機能 {#cja-not-aa}

次の表に、Customer Journey Analyticsで使用できるが、Adobe Analytics ではサポートされていない機能を示します。

| 機能 | さらに詳細を表示 |
| --- | --- |
| **データセット（Adobe Analytics レポートスイートなど）を組み合わせる機能** | Customer Journey Analytics を使用すると、Adobe Analytics の単一のレポートスイートであるかのように、複数のレポートスイートの[データを組み合わせる](/help/connections/combined-dataset.md)ことができます。 |
| **あらゆる種類のデータへの対応** | Customer Journey Analytics は、あらゆる種類のデータスキーマとタイプを保持する Experience Platform の機能と組み合わされています。[エクスペリエンスデータモデル（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用すると、データを均等に表現および整理して、組み合わせや探索にすぐに使用できます。Adobe Analytics は、主に web およびモバイル分析データに焦点を当てており、[データを読み込む](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=ja)機能もいくつかあります。 |
| **クロスデバイス分析** | Customer Journey Analytics は、未認証セッションと認証済みセッションからのデバイス固有のデータセットのシームレスな組み合わせをサポートします。Customer Journey Analytics は、履歴データを既知のデバイスにバックフィルする機能を提供します。Adobe Analytics では、この機能は単一のレポートスイートとデバイスグラフの使用に制限されます。 |
| **ディメンションの機能強化** | Customer Journey Analytics では、次のディメンションを使用する際の柔軟性が向上します。 <ul><li>**カスタムの数値ベースのディメンション**：[データビュー内に独自の数値ベースのディメンションを作成します](/help/data-views/create-dataview.md#components)。</li><li>**文字列ベースのディメンションの並べ替え**：[フリーフォームテーブルで文字列ベースのディメンションをアルファベット順に並べ替えます。](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>Adobe Analytics では、少数の組み込みの数値ディメンションのみが使用でき、文字列ベースのディメンションによる並べ替えはできませんでした。</p> |
| **派生フィールド** | [派生フィールド](/help/data-views/derived-fields/derived-fields.md)を使用すると、レポート時にデータを変換できます。データは、その場で結合、修正、作成し、これらの変換は、すべてのレポートに対して遡って適用できます。 |
| **セキュリティとプライバシーに関するオプションの機能強化** - HIPAA 対応 | Customer Journey Analytics は HIPAA に対応しており、規制準拠に関する[追加のセキュリティオプション](/help/privacy/cmk.md)を提供します。Adobe Analytics は HIPAA に対応していません。 |
| **実験分析** | Customer Journey Analytics では、接続の一部として定義された任意のデータソースから、[任意の実験の上昇率と信頼性を評価](/help/analysis-workspace/c-panels/experimentation.md)できます。この評価により、あらゆるチャネルにわたる顧客インタラクション間の因果関係を把握できます。Analytics は、A4T による実験分析に制限されています。 |
| **予測** | [予測](/help/analysis-workspace/c-forecast/forecasting.md)は、Customer Journey Analytics に既に存在する履歴データに基づく時系列関連データの統計的予測を含む AI／ML 機能です。予測は、フリーフォームテーブルや折れ線グラフのビジュアライゼーションで表示できます。 |
| **ガイド付き分析** | [ガイド付き分析](/help/guided-analysis/overview.md)を使用すると、Customer Journey Analytics のクロスチャネルデータに基づいて構築されたガイド付きワークフローを通じて、カスタマージャーニーに関する高品質のデータとインサイトをセルフサービスで提供できます。 |
| **インテリジェントキャプション** | インテリジェントキャプションは、高度な機械学習と生成 AI を使用して、ワークスペースのビジュアライゼーションに貴重な自然言語のインサイトを提供します。最初のリリースでは、[折れ線グラフ](/help/analysis-workspace/visualizations/line.md)ビジュアライゼーションに関する自動生成された分析情報が提供されます。 |
| **レポート時の変換** | Customer Journey Analytics の[データビュー](/help/data-views/data-views.md)を使用すると、接続からのデータをさらに解釈できます。実装を変更せずにデータを変更または削除、部分文字列を使用してディメンションを操作、任意の値から指標を作成、またはサブイベントをフィルタリングできます。これらの変換はすべて非破壊的に行われます。Adobe Analytics は、仮想レポートスイートとカスタムセッションの長さを通じて限定された機能を提供します。 |
| **BI 拡張機能** | [BI 拡張機能](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-usecases/data-export/bi-extension)では、CJA を PowerBI や Tableau などの一般的な BI ビジュアライゼーションツールに直接接続できます。この拡張機能を使用すると、Analysis Workspace や他の CJA レポートインターフェイスで表示される内容と BI レポートを正確に一致させることができます。これは、生データからレポート／指標を再作成する必要なく、CJA の BI レポートを取得するはるかに簡単な方法です。 |
| **SQL アクセス** | 「Data Distiller」オプションを使用すると、Customer Journey Analytics では、アドビのバックエンド処理で収集されるデータの制限を削除できます。SQL を使用してデータを変更し、ビジネスに固有の値とデータセットを作成し、引き続き探索できます。Analytics は、データへのいかなる種類の SQL アクセスもサポートしていません。 |
| **ステッチ** | [ステッチ](/help/stitching/overview.md)は、クロスチャネル分析に対するイベントデータセットの適合性を高める強力な機能です。クロスチャネル分析は、Customer Journey Analytics で処理できる主なユースケースで、共通の ID（ユーザー ID）に基づいて、異なるチャネルの複数のデータセットに関するレポートをシームレスに組み合わせて実行できます。 |
| **無制限の顧客ディメンションと指標** | Customer Journey Analytics のディメンションは無制限です。値には、数値、テキスト、オブジェクト、リスト、すべての組み合わせを使用できます。ディメンションはネストまたは階層化できます。<br/>これに対して、Adobe Analytics は、最大 75 の prop と 250 の eVar をサポートします。 |
| **無制限の一意の値** | Customer Journey Analytics は、単一のディメンション内でレポートできる無制限の一意の値またはディメンション項目をサポートします。<p>[ディメンションには基数の制限](/help/components/dimensions/high-cardinality.md)がないので、あらゆる一意の値を表示してカウントできます。</p><p>このアプローチにより、大規模な Adobe Analytics の実装に存在する可能性があるレポートと分析の制限が解消され、その結果、[!UICONTROL 低トラフィック]ラベルが付けられます。</p><p>Customer Journey Analytics では、[!UICONTROL ユニーク数超過]ラベルが表示されることがありますが、発生する頻度ははるかに低いので、データにフィルターまたはセグメントを適用することで軽減できます。</p> |

## 完全にサポートされる Adobe Analytics 機能／コンポーネント {#full-support}

| Adobe Analytics 機能 | サポートに関するメモ |
| --- | --- |
| **異常値検出** | フルサポート |
| **Attribution IQ** | フルサポート |
| **ボット検出** | [フルサポート](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ja) |
| **計算指標** | フルサポート。従来の Analysis Workspace の既存の計算指標は、Customer Journey Analytics に移植されません。 |
| **カレンダーイベント** | フルサポート。カレンダーイベントは、ワークスペースの[注釈](/help/components/annotations/overview.md)として実装されています。 |
| **CSV のダウンロード** | フルサポート |
| **カスタムカレンダー** | フルサポート |
| **日付比較** | フルサポート |
| **日付範囲** | すべての日付範囲機能がサポートされています。 |
| **ディメンション** | フルサポート。Customer Journey Analytics は XDM を使用し、無制限のディメンションをサポートします。Customer Journey Analytics は、従来の Adobe Analytics のカスタム eVar や prop に関連付けられていません。 |
| **GDPR の削除** | フルサポート。GDPR は、[!UICONTROL Adobe Experience Platform] と連携して処理されるようになりました。Customer Journey Analytics は、[!UICONTROL Experience Platform] が基盤となるデータセットに対して行ったデータ変更をすべて継承します。 |
| **リフトおよび信頼性レポート** | [実験パネル](/help/analysis-workspace/c-panels/experimentation.md)を介したフルサポート |
| **リスト変数／リスト prop** | フルサポート。Customer Journey Analytics では XDM を使用し、listVars と同様に使用できる無制限の文字列配列をサポートします。 |
| **マーチャンダイジング eVar** | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)を介したフルサポート |
| **指標** | フルサポート。Customer Journey Analytics ではエクスペリエンスデータモデル（XDM）を使用し、無制限の指標をサポートします。Adobe Analytics のカスタム成功イベントには関連付けられません。一部の標準指標は、Adobe Analytics から名前が変更されました：訪問者数 = 人物、訪問数 = セッション、ヒット数 = イベント。 |
| **Adobe Analytics から Customer Journey Analytics へのプロジェクト、フィルター、計算指標の移行** | フルサポート。 |
| **モバイルスコアカード／ダッシュボード** | フルサポート |
| **パネル** | 次のパネルをフルサポート：空のパネル、属性、フリーフォーム、クイックインサイト、次または前の項目。 |
| **PDF への書き出し** | フルサポート |
| **プロジェクトのキュレーション** | フルサポート |
| **プロジェクトリンク** | フルサポート |
| **レポート時間処理** | フルサポート。Customer Journey Analytics は、レポート時の処理にのみ依存します。 |
| **レポート API へのアクセス** | フルサポート。[Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/) を通じて使用できます。 |
| **予定レポート／プロジェクト** | フルサポート |
| **セグメント** | フルサポート。現在は、「フィルター」と呼ばれています。従来の Analysis Workspace の既存のセグメントは Customer Journey Analytics に移植されません。 |
| **ストリーミングメディアコレクションアドオン** | ストリーミングメディアデータは、Workspace のメディア同時視聴者数パネルおよびメディア再生滞在時間パネルの一部として、Analytics ソースコネクタに使用できます。 |
| **概要レベルデータソース** | フルサポート |
| **仮想レポートスイート** | フルサポート。現在は、[データビュー](/help/data-views/create-dataview.md)と呼ばれます。 |
| **仮想レポートスイートコンポーネントのキュレーション** | フルサポート。データビューの一部になりました。 |
| **デバイス、ブラウザー、リファラー、技術の各ディメンション** | [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセットと WebSDK によって生成されたデータセットの両方でサポートされます。詳しくは、[ADC 経由でサポートされる Analytics 変数に関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ja)を参照してください。Experience Platform Web SDK データ収集を使用する場合、デバイスルックアップに基づくデバイスとディメンションは現在サポートされていません。将来的にサポートされる予定です。Web SDK データストリームにデバイスおよびブラウザー検索を追加する方法について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)を参照してください |

## 新しい方法でサポート {#new-support}

| 機能 | メモ |
| --- | --- |
| **Advertising Cloud** | [Adobe Customer Journey Analyticsで使用する AMO ID および EF ID の履歴データを収集 ](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/planning/rvars-to-evars) できます。 |
| **アラート** | [Customer Journey Analytics でアラートを使用](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)するプロセスは、Adobe Analytics でアラートを使用するプロセスとほとんど同じです。 <p>ただし、Customer Journey Analytics におけるデータ収集のタイミングにより、1 時間ごとのアラートは使用できません。Customer Journey Analytics では、アラートを日単位、週単位、月単位で設定できます。</p> |
| **Analytics for Target（A4T）** | [Customer Journey Analytics と Target の統合](https://experienceleague.adobe.com/ja/docs/target/using/integrate/cja/target-reporting-in-cja)では、組織の最適化プログラムに適した強力な分析および時間節約ツールを利用できます。 |
| **オーディエンスの公開** | アドビの Customer Data Platform または Journey Optimizer 製品のライセンスを持つ場合にサポートされます。[オーディエンス公開](/help/components/audiences/audiences-overview.md)は、Experience Platform のリアルタイム顧客プロファイルにオーディエンスを送信します。 |
| **分類** | 「ルックアップデータセット」という名称に変更されました。Analytics で使用される分類は、Analytics 分類ソースコネクタを使用して Experience Platform および Customer Journey Analytics に読み込むことができます。ルックアップデータセットは Experience Platform に直接アップロードして、Customer Journey Analytics で使用することもできます。 |
| **分類ルールビルダー** | Customer Journey Analytics で[部分文字列](/help/data-views/component-settings/substring.md)を使用してサポートされます。ルックアップデータセットではなく、レポート時に文字列操作を使用します。 |
| **カスタムセッションの長さ** | セッションの長さは、データビューの[セッション設定](../../data-views/create-dataview.md#session-settings)を介して設定できます。詳しくは、[セッション設定](../../data-views/session-settings.md)を参照してください。<br/>モバイルバックグラウンドイベントの処理は、Adobe Experience Platform Mobile SDK を介してサポートされます。詳しくは、[Edge Network のライフサイクル](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/)を参照してください。 |
| **通貨換算** | データビューの[指標コンポーネントの書式設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=ja#currency)の一部としてサポートされます。 |
| **顧客属性** | 現在は、「プロファイルデータセット」と呼ばれています。これらは Experience Cloud から自動的に読み込まれませんが、Customer Journey Analytics で使用できるようにするには、Experience Platform にアップロードする必要があります。 |
| **データフィード** | データセットの第 1 世代のデータ書き出しは、[Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=ja) および [Experience Platform の宛先](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja)を通じて利用できます。これらのオプションを使用すると、Experience Platform データレイクに収集または取り込まれるすべてのデータをイベント／行レベルで書き出すことができます。Post 列はクエリ時に計算されるので、後処理データ列は使用できません。Post 列の書き出しは、レポートを通じて使用できます。 |
| **Data Warehouse レポート** | [Customer Journey Analytics の完全なテーブルの書き出し](/help/analysis-workspace/export/export-cloud.md)は、Adobe Analytics のデータウェアハウスレポートの進化版で、現在のデータウェアハウスでは利用できない、リクエストの多い新機能が多数追加されています。 |
| **入口、出口、滞在時間の各ディメンションと指標** | サポート対象（現在、入口と出口は、「セッション開始」および「セッション終了」と呼ばれています）ですが、計算方法が多少異なります。 |
| **eVar の永続性設定** | eVar は Customer Journey Analytics の一部ではなくなりました。ただし、永続性設定はデータビューの一部になり、すべてのディメンションで使用できます。永続性は、データ収集処理ではなく、レポート時の処理に基づいていることに注意してください。データビュー内で設定されるディメンションの永続性は、最大 90 日間に制限されており、無制限の永続性はサポートされません。 |
| **地理特性ディメンション** | [フルサポート](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja) |
| **グラフベースのステッチ** | [グラフベースのステッチ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/stitching/overview#graph-based-stitching)を使用すると、[Adobe Experience Platform ID サービス](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home)の ID グラフの機能を活用して、データセットを優先 ID に昇格させることができます。 |
| **アラート** | Customer Journey Analytics で[アラート](/help/components/c-intelligent-alerts/intelligent-alerts.md)を使用するプロセスは、Adobe Analytics でアラートを使用するプロセスとほとんど同じです。ただし、[重要な違い](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/alerts/alerts-feature-comparison)があります。 |
| **IP の不明化** | Analytics ソースコネクタを使用している Customer Journey Analytics の顧客が Adobe Analytics から Customer Journey Analytics にデータを入力する場合：Adobe Analytics で適用された IP の不明化設定は、Customer Journey Analytics データを通じて送られます。必要に応じて、Adobe Analytics でこれらの設定を制御できます。<p>Customer Journey Analytics の顧客が Experience Platform Web SDK を使用して、Platform と Customer Journey Analytics にデータを直接入力する場合。Platform のデータ収集用のデータ準備を使用して、会社の要件に基づいて IP アドレスを不明化するルールを設定できます。 |
| **マーケティングチャネル** | Analytics ソースコネクタを使用すると、マーケティングチャネルデータがそのコネクタを通じて Customer Journey Analytics に送られます。従来の Adobe Analytics でマーケティングチャネルのルールを設定します。一部のルールはサポートされません。詳しくは、[Customer Journey Analytics マーケティングチャネル](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=ja)を参照してください。<br/>WebSDK 実装では、レポート時のマーケティングチャネル処理ルールは、[派生フィールド](../../data-views/derived-fields/derived-fields.md)を通じてサポートされます。 |
| **マーチャンダイジング変数の持続性** | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)によるフルサポート |
| **指標の重複排除** | データビュー内の指標に対して設定されるようになりました。指標の重複排除は、データセット、データビューまたは接続レベルではなく、ユーザーレベルまたはセッションレベルで行われます。 |
| **新規セッションレポートとリピートセッションレポート** | 以前は、訪問回数ディメンションを使用して達成されていました。新規セッションとリピートセッションは、[13 か月間のルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=ja)でサポートされています。 |
| **処理ルール、VISTA ルール、マーケティングチャネルの処理ルール** | WebSDK ベースのデータセットと Analytics ソースコネクタのデータの両方で、Adobe Experience Platform データ準備機能と[派生フィールド](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=ja)の使用がサポートされます。 |
| **Products 変数** | Experience Platform 内では、ユーザーはデータセットスキーマ内のオブジェクトの配列を使用して、このユースケースを満たすことができます。Customer Journey Analytics 内では、顧客は任意の数の製品変数を使用できます。Adobe Analytics のように 1 つの変数には制限されません。 |
| **プロジェクトの共有** | プロジェクトの共有は、Customer Journey Analytics のユーザー間でのみサポートされます。Customer Journey Analytics と従来の Analysis Workspace 間ではプロジェクトは共有されません。 |
| **Report Builder** | Excel 用の新しい Office 365 プラグインでサポートされます。 |
| **ユーザー権限／データアクセス制御** | Customer Journey Analytics は [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja) 製品管理者、製品プロファイル管理者およびユーザーを区別します。他のユーザーが作成した接続、プロジェクト、フィルターまたは計算指標を作成／更新／削除できるのは製品管理者のみで、製品管理者と製品プロファイル管理者は、データビューを編集できます。計算指標、フィルターまたは注釈などを作成するユーザー権限を追加できます。 |
| **ビジュアライゼーション** | マップビジュアライゼーションを除く、すべてのワークスペースビジュアライゼーションがサポートされます。 |
| **クロスデバイス／クロスチャネルのステッチ** | ID 情報を含むイベントデータセットに対してサポートされます。[ステッチ](../../stitching/overview.md)を参照してください。 |

## 部分的なサポート {#partial}

| 機能 | メモ |
| --- | --- |
| **パネル** | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。セグメント比較と Analytics for Target（A4T）パネルはサポートされていません。 |

## サポートなし、予定済み {#planned}

| 機能 | メモ |
| --- | --- |
| **貢献度分析** | サポートが予定されています。 |
| **プロジェクトテンプレート** | サポートが予定されています。 |
| **リアルタイムレポート** | サポートが予定されています。 |
| **Segment IQ** | サポートが予定されています。 |
| **トランザクション ID データソース** | サポートが予定されています。 |

## サポートなし、まだ未予定 {#not-planned}

| 機能 | メモ |
| --- | --- |
| **Activity Map** | まだサポートの予定はありません。 |

## サポートされません {#never}

* クロスデバイス Coop を使用した人物指標
