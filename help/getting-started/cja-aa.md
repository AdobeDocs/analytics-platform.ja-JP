---
title: Customer Journey Analytics の機能のサポート
description: Customer Journey Analytics の機能と Adobe Analytics の機能セットの比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 100%

---

# Customer Journey Analytics の機能のサポート

次の表は、Adobe Analytics の機能のうち、Customer Journey Analytics（CJA）でサポートされている、一部サポートされている、またはサポートされていないものを示しています。これらのリストは、時間が経過し、CJA に機能が追加されると変更されます。

## 完全にサポートされる機能／コンポーネント

| Adobe Analytics 機能 | サポートに関するメモ |
| --- | --- |
| 異常値検出 | フルサポート |
| Attribution IQ | フルサポート |
| 計算指標 | 完全にサポートされます。従来の Analysis Workspace 内の既存の計算指標は、CJA に移植されません。 |
| クロスデバイス／クロスチャネルのステッチ | 完全にサポートされます。 [クロスチャネル分析](/help/connections/cca/overview.md) を参照してください。 |
| CSV のダウンロード | フルサポート |
| カスタムカレンダー | フルサポート |
| 日付の比較 | フルサポート |
| 日付範囲 | すべての日付範囲機能がサポートされています。 |
| 夏時間 | フルサポート |
| ディメンション | 完全にサポートされます。CJA は XDM を活用し、無制限のディメンションをサポートします。CJA は、従来の Adobe Analytics のカスタム eVar や prop には結び付けられません。 |
| 標準搭載の Analysis Workspace ディメンション（例：ブラウザータイプ、リファラータイプ、オペレーティングシステム） | ベース XDM フィールド（ユーザーエージェントやデバイス ID など）に値が入力されている限り、CJA はネイティブでこれらのディメンションを提供します。Analytics コネクタ（ADC）を使用するお客様は、これらのディメンションの一部のみを利用できます。[ADC 経由でサポートされる Analytics 変数に関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)を参照してください。 |
| GDPR の削除 | 完全にサポートされます。GDPR は、[!UICONTROL Adobe Experience Platform] と連携して処理されることに注意してください。CJA は、[!UICONTROL Experience Platform] が基盤となるデータセットに加えたデータの変更をすべて継承します。 |
| リスト変数／リスト prop | 完全にサポートされます。CJA では XDM を活用し、listVars と同様に使用できる無制限の文字列配列をサポートしています。 |
| マーチャンダイジング変数の持続性 | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#バインディング指標)によるフルサポート（2022 年 1 月） |
| マーチャンダイジング eVar | [バインディングディメンションとバインディング指標](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=en#binding-dimension)によるフルサポート（2022 年 1 月） |
| 指標 | 完全にサポートされます。CJA は、エクスペリエンスデータモデル（XDM）を活用し、無制限の指標をサポートします。従来の Analytics のカスタム成功イベントとは関係ありません。一部の標準指標は、従来の Analytics から名前が変更されました。例：訪問者 = 人、訪問 = セッション、ヒット = イベント。 |
| 指標の重複排除 | フルサポート |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。 |
| PDF の書き出し | フルサポート |
| プロジェクトのキュレーション | フルサポート |
| プロジェクトリンク | フルサポート |
| Report Builder（Excel プラグイン） | フルサポート |
| レポート時間処理 | 完全にサポートされます。CJA は、レポート時間処理にのみ依存します。 |
| レポート API へのアクセス | 完全にサポートされます。[CJA API](https://www.adobe.io/cja-apis/docs/) を通じて使用できます。 |
| 予定レポート／プロジェクト | フルサポート |
| セグメント | 完全にサポートされます。現在は「フィルター」と呼ばれています。従来の Analysis Workspace 内の既存のセグメントは CJA に移植されません。 |
| ユーザー権限／データアクセス制御 | 完全にサポートされます。CJA は、[Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja) の製品管理者とユーザーを区別します。製品管理者のみが次のことを行うことができます。 <ul><li>接続またはデータ表示の作成／更新／削除をおこなう</li><li>他のユーザーが作成したプロジェクト、フィルターまたは計算指標の更新／削除、および</li><li>Workspace プロジェクトをすべてのユーザーと共有する。</li></ul> |
| 仮想レポートスイート | 完全にサポートされます。現在は、 [データビュー](/help/data-views/create-dataview.md) と呼ばれています。 |
| VRS コンポーネントのキュレーション | 完全にサポートされます。データビューの一部になりました。 |

## サポート（注意が必要）

| 機能 | メモ |
| --- | --- |
| A4T | [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja) のフィールドを通じてサポートが提供されます。 |
| 分類 | 「参照データセット」という名称に変更されました。 Analytics で使用される分類は、Analytics Classifications Data Connector を使用して Experience Platform および CJA にインポートできます。 参照データセットは AEP に直接アップロードして、CJA で使用することもできます。 |
| カスタムセッション | モバイルバックグラウンドヒット以外のすべてのカスタムセッション機能がサポートされます。 |
| 顧客属性 | 現在は「プロファイルデータセット」と呼ばれ、これらは Experience Cloud から自動的に読み込まれず、CJA で使用する前に AEP にアップロードする必要があります。 |
| デバイス、ブラウザー、テクノロジーのディメンション | AEP データセットに特定の XDM スキーマフィールドが含まれ、XDM エクスペリエンスイベントクラスに準拠している場合、これらのディメンションは自動的に含まれます。 |
| 入口、出口、滞在時間の各ディメンションと指標 | サポート対象（現在、入口と出口は、「セッション開始」および「セッション終了」と呼ばれています）ですが、計算方法が多少異なります。 |
| eVar の永続性設定 | eVar は CJA に含まれなくなりました。ただし、永続性設定はデータビューの一部になり、すべてのディメンションで使用できます。永続性は、データ収集処理ではなく、レポートの時間処理に基づいていることに注意してください。データ表示内で設定されるディメンションは、最大持続時間が 90 日に制限され、無制限の永続性はサポートされません。 |
| 地理特性ディメンション | Adobe Analytics で収集されたすべての地理特性／地域情報は、Analytics Data Connector を通じて CJA に送られます。デジタルデータ収集に AEP Web SDK を使用する実装など、Analytics Data Connector を使用しない実装では、自動的に実行される完全な地理的検索は行われません（国と州はサポートされていますが、市区町村と郵便番号はサポートされていません）。 |
| マーケティングチャネル | マーケティングチャネルのデータは、Analytics Data Connector を介して CJA に渡されます。従来の Adobe Analytics では、引き続きマーケティングチャネルのルールを設定する必要があります。一部のルールはサポートされていません。詳しくは、[CJA マーケティングチャネルのドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja#cja-usecases)を参照してください。 |
| products 変数 | Experience Platform から、データセットスキーマ内でオブジェクトタイプフィールドの配列を使用して、この使用例を実現できます。 CJA では、お客様は好きな数の製品変数を使用できます。Adobe Analytics のように 1 つの変数には制限されません。 |
| プロジェクトの共有 | プロジェクトの共有は、CJA のユーザー間でのみサポートされます。CJA と従来の Analysis Workspace 間ではプロジェクトは共有されません。 |
| ビジュアライゼーション | マップビジュアライゼーションを除く、すべてのビジュアライゼーションがサポートされます。 |

## 部分的なサポート

| 機能 | メモ |
| --- | --- |
| ボットフィルタリング | [Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en)ベースのデータセットには、ボットフィルタリングが適用されます。他のデータセットの一般的なボットフィルタリングロジックは、[!UICONTROL Experience Platform] または CJA では実行されません。 |
| Media Analytics | メディアデータは、Analytics ソースコネクタの一部として使用できます。 |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。セグメントの比較、Analytics for Target（A4T）およびメディアの同時ビューアのパネルはサポートされていません。 |
| 処理ルール | Analytics Data Connector ベースのデータセットの場合、処理ルールは引き続き適用されます。[Adobe Experience Platform のデータ準備機能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) は、Platform に直接送信されるデータの処理ルールの代わりに使用することもできます。 |

## 現在はサポートされていませんが、予定されています

| 機能 | メモ |
| --- | --- |
| アラート | サポートが予定されています。 |
| カレンダーイベント | Workspace では「注釈」と呼ばれます。 |
| 分類ルールビルダー | CJA での動作（ルックアップデータセットではなく、レポート時に文字列操作を使用する）とは少し異なります。 |
| 貢献度分析 | サポートが予定されています。 |
| Data Warehouse レポート（全行エクスポート） | Analysis Workspace インターフェイスからのサポートが予定されています。 また、Adobe Experience Platform [[!UICONTROL クエリサービス]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)でも、CJA におけるこれらのユースケースに対応するインターフェイスを提供しています。 |
| デバイスグラフでの ID のステッチ | サポートが予定されています。 |
| リフトおよび信頼性レポート | サポートが予定されています。 |
| 処理ルール、VISTA ルール、マーケティングチャネルの処理ルール | サポートは計画的におこなわれていますが、より柔軟で遡及的かつ非破壊的なデータ操作のために、データ収集時ではなくクエリ時に動作します。 |
| プロジェクトテンプレート | サポートが予定されています。 |
| リアルタイムレポート | サポートが予定されています。 |
| Segment IQ | サポートが予定されています。 |
| セグメントの公開（ワークスペースから Experience Cloud へのセグメントの送信） | サポートが予定されています。CJA では「Audience パブリッシング」と呼ばれます。 |
| 新規セッションレポートとリピートセッションレポート | 予定されているサポートには、いくつかの注意事項があります。 |

## サポートの予定はありません

| 機能 | メモ |
| --- | --- |
| Activity Map | まだサポートの予定はありません。 |
| Advertising Cloud | まだサポートの予定はありません。 |
| 通貨換算 | まだサポートの予定はありません。 |
| データフィード | まだサポートの予定はありません。 |
| 概要データソース | まだサポートの予定はありません。 |
| トランザクション ID データソース | まだサポートの予定はありません。 |

## サポートされません

* クロスデバイス Coop を使用した人指標
* Reports &amp; Analytics のダッシュボード
* Reports &amp; Analytics のブックマーク
* Reports &amp; Analytics のターゲット
* Mobile Services
