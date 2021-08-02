---
title: Customer Journey Analytics の機能のサポート
description: Customer Journey Analytics の機能と Adobe Analytics の機能セットの比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
source-git-commit: 58627fd11c4031449f156e70cbfa41dac143ac90
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 98%

---

# Customer Journey Analytics の機能のサポート

次の表は、Adobe Analytics の機能のうち、Customer Journey Analytics（CJA）でサポートされている、一部サポートされている、またはサポートされていないものを示しています。これらのリストは、時間が経過し、CJA に機能が追加されると変更されます。

## 完全にサポートされる機能／コンポーネント

| Adobe Analytics 機能 | サポートに関するメモ |
| --- | --- |
| 異常値検出 | 完全にサポートされます。 |
| Attribution IQ | 完全にサポートされます。 |
| 計算指標 | 従来の Analysis Workspace 内の既存の計算指標は、CJA に移植されません。 |
| クロスデバイス／クロスチャネルのステッチ | 「[クロスチャネル分析](/help/connections/cca/overview.md)」を参照してください。 |
| 日付の比較 | 完全にサポートされます。 |
| 日付範囲 | カスタムカレンダーに対するサポートが予定されています。 |
| ディメンション | CJA では XDM を活用し、無制限のディメンションをサポートしています。従来の Analytics のカスタム eVar や prop とは関係ありません。 |
| 標準搭載の Analysis Workspace ディメンション（例：ブラウザータイプ、リファラータイプ、オペレーティングシステム） | ベース XDM フィールド（ユーザーエージェントやデバイス ID など）に値が入力されている限り、CJA はネイティブでこれらのディメンションを提供します。Analytics コネクタ（ADC）を使用するお客様は、これらのディメンションの一部のみを利用できます。[ADC 経由でサポートされる Analytics 変数に関するドキュメント](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)を参照してください。 |
| GDPR の削除 | GDPR は [!UICONTROL Adobe Experience Platform] と連携して処理されることに注意してください。CJA は、[!UICONTROL Experience Platform] が基盤となるデータセットに加えたデータ変更をすべて継承します。 |
| リスト変数／リスト prop | CJA では XDM を活用し、listVar と同様に使用できる無制限の文字列配列をサポートしています。 |
| 指標 | CJA は、エクスペリエンスデータモデル（XDM）を活用し、無制限の指標をサポートします。従来の Analytics のカスタム成功イベントとは関係ありません。一部の標準指標は、従来の Analytics から名前が変更されました。例：訪問者 = 人、訪問 = セッション、ヒット = イベント。 |
| PDF の書き出し | 完全にサポートされます。 |
| プロジェクトのキュレーション | 完全にサポートされます。 |
| プロジェクトリンク | 完全にサポートされます。 |
| レポート時間処理 | CJA は、レポートの時間処理にのみ依存しています。 |
| レポート API へのアクセス | [CJA API](https://www.adobe.io/cja-apis/docs/) で利用できるようになりました。 |
| 予定レポート／プロジェクト | 完全にサポートされます。 |
| セグメント | 現在は「フィルター」と呼ばれています。従来の Analysis Workspace 内の既存のセグメントは CJA に移植されません。 |
| ユーザー権限／データアクセス制御 | CJA は、Adobe Admin Console の製品管理者とユーザーを区別します。1）接続またはデータ表示の作成／更新／削除、2）他のユーザーが作成したプロジェクト、フィルターまたは計算指標の更新／削除、3）Workspace プロジェクトをすべてのユーザーと共有できるのは製品管理者のみです。 |
| 仮想レポートスイート | 現在は、[データビュー](/help/data-views/create-dataview.md)と呼ばれます。 |
| VRS コンポーネントのキュレーション | データビューの一部になりました。 |
| A4T | [Analytics Data Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en)のフィールドを通じてサポートが提供されます。 |

## サポート（注意が必要）

| 機能 | メモ |
| --- | --- |
| 分類 | 「参照データセット」という名称に変更されました。 Analytics で使用される分類は、Analytics Classifications Data Connector を使用して Experience Platform および CJA にインポートできます。 参照データセットは AEP に直接アップロードして、CJA で使用することもできます。 |
| カスタムセッション | モバイルバックグラウンドヒット以外のすべてのカスタムセッション機能がサポートされます。 |
| 顧客属性 | 名前が「プロファイルデータセット」に変わり、Experience Cloud から自動的に読み込まれませんが、CJA で使用する前に AEP にアップロードする必要があります。 |
| デバイス、ブラウザー、テクノロジーのディメンション | AEP データセットに特定の XDM スキーマフィールドが含まれ、XDM エクスペリエンスイベントクラスに準拠している場合、これらのディメンションは自動的に含まれます。 |
| 入口、出口、滞在時間の各ディメンションと指標 | サポート対象（現在、入口と出口は、「セッション開始」および「セッション終了」と呼ばれています）ですが、計算方法が多少異なります。 |
| eVar の永続性設定 | eVar は CJA に含まれなくなりました。ただし、永続性設定はデータビューの一部になり、すべてのディメンションで使用できます。永続性は、データ収集処理ではなく、レポートの時間処理に基づいていることに注意してください。データ表示内で設定されるディメンションは、最大持続時間が 90 日に制限され、無制限の永続性はサポートされません。 |
| マーケティングチャネル | マーケティングチャネルのデータは、Analytics Data Connector を介して CJA に渡されます。従来の Adobe Analytics では、引き続きマーケティングチャネルのルールを設定する必要があります。一部のルールはサポートされていません。詳しくは、[CJA マーケティングチャネルのドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja#cja-usecases)を参照してください。 |
| products 変数 | Experience Platform から、データセットスキーマ内でオブジェクトタイプフィールドの配列を使用して、この使用例を実現できます。 CJA では、お客様は好きな数の製品変数を使用できます。Adobe Analytics のように 1 つの変数には制限されません。 |
| プロジェクトの共有 | プロジェクトの共有は、CJA のユーザー間でのみサポートされます。CJA と従来の Analysis Workspace 間ではプロジェクトは共有されません。 |
| ビジュアライゼーション | マップビジュアライゼーションを除く、すべてのビジュアライゼーションがサポートされます。 |

## 部分的なサポート

| 機能 | メモ |
| --- | --- |
| ボットフィルタリング | Analytics コネクタ（ADC）ベースのデータセットの場合、ボットフィルターが適用されます。他のデータセットの一般的なボットフィルタリングロジックは、[!UICONTROL Experience Platform] または CJA では実行されません。 |
| Media Analytics | メディアデータは、Analytics Data Connector の一部として使用できます。 |
| マーチャンダイジング eVar | マーチャンダイジング eVar の動作は、マーチャンダイジング eVar が永続性を使用するように設定されていない場合、オブジェクト配列内のディメンションを使用して達成できます。 現在、マーチャンダイジングディメンションは使用できません。 |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。セグメントの比較、Analytics for Target（A4T）およびメディアの同時ビューアのパネルはサポートされていません。 |
| 処理ルール | Analytics Data Connector ベースのデータセットの場合、処理ルールは引き続き適用されます。[Adobe Experience Platform のデータ準備機能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja) は、Platform に直接送信されるデータの処理ルールの代わりに使用することもできます。 |

## 現在はサポートされていませんが、予定されています

| 機能 | メモ |
| --- | --- |
| アラート | サポートが予定されています。 |
| 貢献度分析 | サポートが予定されています。 |
| CSV のダウンロード | サポートが予定されています。 |
| カスタムカレンダー | サポートが予定されています。 |
| Data Warehouse レポート（全行エクスポート） | Analysis Workspace インターフェイスからのサポートが予定されています。 また、[!UICONTROL Experience Platform クエリサービス]でも、CJA におけるこれらの使用例に対応するインターフェイスを提供しています。 |
| デバイスグラフでの ID のステッチ | サポートが予定されています。 |
| 指標の重複排除 | サポートが予定されています。 |
| マーチャンダイジング変数の持続性 | サポートが予定されています。 |
| リアルタイムレポート | サポートが予定されています。 |
| Report Builder（Excel プラグイン） | サポートが予定されています。 |
| Segment IQ | サポートが予定されています。 |
| セグメントの公開（Workspace から Experience Cloud へのセグメントの送信） | サポートが予定されています。 |

## サポートの予定はありません。

| 機能 | メモ |
| --- | --- |
| Activity Map | まだサポートの予定はありません。 |
| Advertising Cloud | まだサポートの予定はありません。 |
| 分類ルールビルダー | まだサポートの予定はありません。 |
| データフィード | まだサポートの予定はありません。 |
| 概要データソース | まだサポートの予定はありません。 |

## サポートされません

* クロスデバイス Coop を使用した人指標
* Reports &amp; Analytics のダッシュボード
* Reports &amp; Analytics のブックマーク
* Reports &amp; Analytics のターゲット
* Reports &amp; Analytics のカレンダーイベント
* Mobile Services
