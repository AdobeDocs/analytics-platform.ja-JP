---
title: Customer Journey Analytics の機能のサポート
description: Customer Journey Analytics の機能と Adobe Analytics の機能セットの比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '1537'
ht-degree: 98%

---

# Customer Journey Analytics の機能のサポート

次の表は、Adobe Analytics の機能のうち、Customer Journey Analytics（CJA）でサポートされている、一部サポートされている、またはサポートされていないものを示しています。これらのリストは、時間が経過し、CJA に機能が追加されると変更されます。

## 完全にサポートされる機能／コンポーネント

| Adobe Analytics 機能 | サポートに関するメモ |
| --- | --- |
| 異常値検出 | フルサポート |
| Attribution IQ | フルサポート |
| 計算指標 | フルサポート。従来の Analysis Workspace 内の既存の計算指標は、CJA に移植されません。 |
| カレンダーイベント | フルサポート。カレンダーイベントは、ワークスペースの[注釈](/help/components/annotations/overview.md)として実装されています。 |
| CSV のダウンロード | フルサポート |
| カスタムカレンダー | フルサポート |
| 日付の比較 | フルサポート |
| 日付範囲 | すべての日付範囲機能がサポートされています。 |
| ディメンション | フルサポート。CJA は XDM を活用し、無制限のディメンションをサポートします。CJA は、従来の Adobe Analytics のカスタム eVar や prop には結び付けられません。 |
| GDPR の削除 | フルサポート。GDPR は、[!UICONTROL Adobe Experience Platform] と連携して処理されることに注意してください。CJA は、[!UICONTROL Experience Platform] が基盤となるデータセットに加えたデータの変更をすべて継承します。 |
| リフトおよび信頼性レポート | [実験パネル](/help/analysis-workspace/c-panels/experimentation.md)を介したフルサポート |
| リスト変数／リスト prop | フルサポート。CJA では XDM を活用し、listVars と同様に使用できる無制限の文字列配列をサポートしています。 |
| マーチャンダイジング eVar | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)によるフルサポート |
| 指標 | フルサポート。CJA は、エクスペリエンスデータモデル（XDM）を活用し、無制限の指標をサポートします。従来の Analytics のカスタム成功イベントとは関係ありません。一部の標準指標は、従来の Analytics から名前が変更されました。例：訪問者 = 人物、訪問 = セッション、ヒット = イベント。 |
| モバイルスコアカード／ダッシュボード | フルサポート |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。 |
| PDF の書き出し | フルサポート |
| プロジェクトのキュレーション | フルサポート |
| プロジェクトリンク | フルサポート |
| レポート時の処理 | フルサポート。CJA は、レポート時の処理にのみ依存します。 |
| レポート API へのアクセス | フルサポート。[CJA API](https://www.adobe.io/cja-apis/docs/) を通じて使用できます。 |
| 予定レポート／プロジェクト | フルサポート |
| セグメント | フルサポート。現在は「フィルター」と呼ばれています。従来の Analysis Workspace 内の既存のセグメントは CJA に移植されません。 |
| 仮想レポートスイート | フルサポート。現在は、[データビュー](/help/data-views/create-dataview.md) と呼ばれています。 |
| VRS コンポーネントのキュレーション | フルサポート。データビューの一部になりました。 |
| ストリーミングメディア分析 | メディアデータは、Analytics Data Connector を使用すると、Workspace のメディア同時視聴者数パネルおよびメディア再生滞在時間パネルの一部として使用できます。 |

{style=&quot;table-layout:auto&quot;}

## 新しい方法でサポート

| 機能 | メモ |
| --- | --- |
| オーディエンスの公開（セグメントの公開） | アドビの Customer Data Platform または Journey Optimizer 製品のライセンスを持つ場合にサポートされます。[オーディエンス公開](/help/components/audiences/audiences-overview.md)は、Experience Platform のリアルタイム顧客プロファイルにオーディエンスを送信します。 |
| 分類 | 「ルックアップデータセット」という名称に変更されました。Analytics で使用される分類は、Analytics Classifications Source Connector を使用して Experience Platform および CJA にインポートできます。ルックアップデータセットは AEP に直接アップロードして、CJA で使用することもできます。 |
| 分類ルールビルダー | CJA で[部分文字列](/help/data-views/component-settings/substring.md)を使用したサポート ルックアップデータセットではなく、レポート時に文字列操作を使用します。 |
| カスタムセッション | モバイルバックグラウンドヒット以外のすべてのカスタムセッション機能がサポートされます。 |
| マーチャンダイジング変数の持続性 | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension)によるフルサポート |
| 顧客属性 | 現在は「プロファイルデータセット」と呼ばれ、これらは Experience Cloud から自動的に読み込まれず、CJA で使用する前に AEP にアップロードする必要があります。 |
| 指標の重複排除 | データビュー内の指標に対して設定されるようになりました。指標の重複排除は、データセット、データビューまたは接続レベルではなく、ユーザーレベルまたはセッションレベルで行われます。 |
| 入口、出口、滞在時間の各ディメンションと指標 | サポート対象（現在、入口と出口は、「セッション開始」および「セッション終了」と呼ばれています）ですが、計算方法が多少異なります。 |
| eVar の永続性設定 | eVar は CJA に含まれなくなりました。ただし、永続性設定はデータビューの一部になり、すべてのディメンションで使用できます。永続性は、データ収集処理ではなく、レポート時の処理に基づいていることに注意してください。データ表示内で設定されるディメンションは、最大持続時間が 90 日に制限され、無制限の永続性はサポートされません。 |
| IP の不明化 | Analytics ソースコネクタを使用している CJA の顧客が Adobe Analytics から CJA にデータを入力する場合：Adobe Analytics で適用された IP の不明化設定は、CJA データを通じて送られます。 必要に応じて、Adobe Analytics でこれらの設定を制御できます。<p>Adobe Experience Platform Web SDK を使用する CJA の顧客がデータを Platform および CJA に直接入力する場合：Platform のデータ収集に関するデータの準備を使用し、会社の要件に基づいて IP アドレスを難読化するルールを設定できます。 |
| 新規セッションとリピートセッションレポート | 以前は、訪問回数ディメンションを使用して達成されていました。新規セッションとリピートセッションは、[13 か月間のルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ja#new-repeat)でサポートされています。 |
| products 変数 | Experience Platform から、データセットスキーマ内でオブジェクトタイプフィールドの配列を使用して、このユースケースを実現できます。CJA では、お客様は好きな数の製品変数を使用できます。Adobe Analytics のように 1 つの変数には制限されません。 |
| プロジェクトの共有 | プロジェクトの共有は、CJA のユーザー間でのみサポートされます。CJA と従来の Analysis Workspace 間ではプロジェクトは共有されません。 |
| ビジュアライゼーション | マップビジュアライゼーションを除く、すべてのビジュアライゼーションがサポートされます。 |
| Report Builder（Excel プラグイン） | Excel 用の新しい Office 365 プラグインでサポートされます。 |
| ユーザー権限／データアクセス制御 | CJA は [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja) 製品管理者、製品プロファイル管理者およびユーザーを区別します。他のユーザーが作成した接続、プロジェクト、フィルターまたは計算指標を作成／更新／削除できるのは製品管理者のみで、製品管理者と製品プロファイル管理者は、データビューを編集できます。計算指標、フィルターまたは注釈などを作成するためのユーザー権限を追加できます。 |
| 処理ルール、VISTA ルール、マーケティングチャネルの処理ルール | WebSDK ベースのデータセットと Analytics Data Connector のデータの両方で、Adobe Experience Platform データ準備機能の使用がサポートされます。 |

{style=&quot;table-layout:auto&quot;}

## 部分的なサポート

| 機能 | メモ |
| --- | --- |
| マーケティングチャネル | マーケティングチャネルのデータは、Analytics ソースコネクタを介して CJA に渡されます。従来の Adobe Analytics でも、引き続きマーケティングチャネルのルールを設定する必要があり、一部のルールはサポートされません。詳しくは、[CJA マーケティングチャネルのドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja#cja-usecases)を参照してください。さらに、WebSDK 実装の場合、プラグインはクライアントサイドのマーケティングチャネルを定義するために使用できます。今後、レポート時間マーケティングチャネル処理ルールのサポートが予定されています。 |
| クロスデバイス／クロスチャネルのステッチ | ID 情報を直接含むデータセット（「フィールドベースのステッチ」とも呼ばれます）でサポートされます。 グラフベースのステッチは、まだサポートされていませんが、予定されています。 [Cross-Channel Analytics](/help/cca/overview.md)を参照してください。 |
| ボットフィルタリング | [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセットには、ボットフィルタリングが適用されます。他のデータセットの一般的なボットフィルタリングロジックは、[!UICONTROL Experience Platform] または CJA では実行されません。 |
| デバイス、ブラウザー、リファラー、技術の各ディメンション | [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)ベースのデータセットでサポートされます。[ADC 経由でサポートされる Analytics 変数に関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ja)を参照してください。<p>Adobe ソースコネクタを使用して Adobe Analytics から CJA にデータを入力せず、代わりに Experience Platform Web SDK のデータ収集を使用する場合、デバイスルックアップに基づくデバイスとディメンションは、現在、サポートされていません。将来サポートされる予定です。 |
| 地理特性ディメンション | Adobe Analytics に収集されたすべての地理特性／地域情報は、[Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)を通じて CJA に送られます。デジタルデータ収集に AEP Web SDK を利用する実装など、Analytics ソースコネクタを使用しない実装では、自動的に実行される完全な地理的検索は行われません。国と州はグローバルにサポートされていますが、市区町村と郵便番号はサポートされていません。 |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。セグメント比較と Analytics for Target（A4T）パネルはサポートされていません。 |
| 処理ルール | Analytics ソースコネクタベースのデータセットの場合、処理ルールは引き続き適用されます。[Adobe Experience Platform のデータ準備機能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) は、Platform に直接送信されるデータの処理ルールの代わりに使用することもできます。 |
| A4T | [Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)のフィールドを通じて一部サポートされます。Target のアクティビティとエクスペリエンスでの A4T のわかりやすい名前のサポートが予定されています。 |

{style=&quot;table-layout:auto&quot;}

## 現在はサポートされていませんが、予定されています

| 機能 | メモ |
| --- | --- |
| アラート | サポートが予定されています。 |
| 貢献度分析 | サポートが予定されています。 |
| Data Warehouse レポート（全行エクスポート） | Analysis Workspace インターフェイスからのサポートが予定されています。また、Adobe Experience Platform [[!UICONTROL クエリサービス]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)でも、CJA におけるこれらのユースケースに対応するインターフェイスを提供しています。 |
| デバイスグラフでの ID のステッチ | サポートが予定されています。 |
| プロジェクトテンプレート | サポートが予定されています。 |
| リアルタイムレポート | サポートが予定されています。 |
| Segment IQ | サポートが予定されています。 |
| 通貨換算 | サポートが予定されています。 |
| データフィード | AEP の宛先を介したサポートが予定されています。 |
| トランザクション ID データソース | サポートが予定されています。 |
| AA から CJA へのプロジェクト／フィルター／計算指標の移行 | サポートが予定されています。 |
| 概要レベルデータソース | サポートが予定されています。 |

{style=&quot;table-layout:auto&quot;}

## サポートの予定はありません

| 機能 | メモ |
| --- | --- |
| Activity Map | まだサポートの予定はありません。 |
| Advertising Cloud | まだサポートの予定はありません。 |
| 概要データソース | まだサポートの予定はありません。 |

{style=&quot;table-layout:auto&quot;}

## サポートされません

* クロスデバイス Coop を使用した人物指標
* Reports &amp; Analytics のダッシュボード
* Reports &amp; Analytics のブックマーク
* Reports &amp; Analytics のターゲット
* Mobile Services
