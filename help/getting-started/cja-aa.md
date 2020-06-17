---
title: Customer Journey Analytics の機能のサポート
description: Customer Journey Analytics の機能と Adobe Analytics の機能セットの比較。
translation-type: tm+mt
source-git-commit: 7d2abfb2cd91ee7574fce10847abb89f14b5388e
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 85%

---


# Customer Journey Analytics の機能のサポート

次の表は、Adobe Analytics の機能のうち、Customer Journey Analytics（CJA）でサポートされている、一部サポートされている、またはサポートされていないものを示しています。これらのリストは、時間が経過し、CJA に機能が追加されると変更されます。

## 完全にサポートされる機能／コンポーネント

| 機能 | メモ |
| --- | --- |
| 指標 | CJA は、エクスペリエンスデータモデル（XDM）を活用し、無制限の指標をサポートします。従来の Analytics のカスタム成功イベントとは関係ありません。一部の標準指標は、従来の Analytics から名前が変更されました。例：訪問者 = 人、訪問 = セッション、ヒット = イベント。 |
| ディメンション | CJA は XDM を活用し、無制限のディメンションをサポートします。従来の Analytics のカスタム成功イベントとは関係ありません。 |
| リスト変数／リスト prop | CJA は XDM を活用し、無制限のリスト変数をサポートします。 |
| 日付範囲 | カスタムカレンダーに対するサポートが予定されています。 |
| 計算指標 | 従来の Analysis Workspace 内の既存の計算指標は、CJA に移植されません。 |
| セグメント | 現在は「フィルター」と呼ばれています。従来の Analysis Workspace 内の既存のセグメントは CJA に移植されません。 |
| 異常値検出 | 2020年6月現在の完全サポート |
| Attribution IQ | 完全にサポートされます。 |
| プロジェクトのキュレーション | 完全にサポートされます。 |
| プロジェクトリンク | 完全にサポートされます。 |
| 日付の比較 | 完全にサポートされます。 |
| 仮想レポートスイート | 現在は、[データビュー](/help/data-views/create-dataview.md)と呼ばれます。 |
| VRS コンポーネントのキュレーション | データビューの一部になりました。 |
| レポート時間処理 | CJA は、レポートの時間処理にのみ依存しています。 |
| GDPR の削除 | Note that GDPR is now handled in coordination with [!UICONTROL Experience Platform] - CJA inherits whatever data changes [!UICONTROL Experience Platform] makes to underlying datasets. |

## サポート（注意が必要）

| 機能 | メモ |
| --- | --- |
| products 変数 | エクスペリエンスイベントスキーマに準拠したデータのレポートに現在使用できる product 変数（特に productListItems オブジェクトを使用したもの）。 |
| ビジュアライゼーション | マップビジュアライゼーションを除く、すべてのビジュアライゼーションがサポートされます。 |
| AAM Audiences | If customers are using [!UICONTROL Analytics Data Connector] datasets, this data will be part of the ADC data. |
| プロジェクトの共有 | プロジェクトの共有は、CJA のユーザー間でのみサポートされます。CJA と従来の Analysis Workspace 間ではプロジェクトは共有されません。 |
| カスタムセッション | モバイルバックグラウンドヒット以外のすべてのカスタムセッション機能がサポートされます。 |
| eVar の永続性設定 | eVar は CJA に含まれなくなりました。ただし、永続性設定はデータビューの一部になり、すべてのディメンションで使用できます。永続性は、データ収集処理ではなく、レポートの時間処理に基づいていることに注意してください。つまり、すべての永続性は、データ全体ではなく、レポートの日付範囲に基づきます。 |
| 分類 | 現在は、「ルックアップデータセット」と呼ばれ、従来の Analytics からは自動的に読み込まれません。CJA で使用するには、AEP にアップロードする必要があります。 |
| 顧客属性 | 名前が「プロファイルデータセット」に変わり、Experience Cloud から自動的に読み込まれませんが、CJA で使用する前に AEP にアップロードする必要があります。 |

## 部分的なサポート

| 機能 | メモ |
| --- | --- |
| 標準搭載の Analysis Workspace ディメンション（例：ブラウザータイプ、リファラータイプ、マーケティングチャネル、訪問回数など） | CJA は、これらのディメンションをネイティブでは提供しません。Analytics Data Connector（ADC）を使用するお客様は、これらのディメンションの一部のみを利用できます。[ADC 経由でサポートされる Analytics 変数に関するドキュメント](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)を参照してください。 |
| パネル | 空のパネル、アトリビューションパネル、フリーフォームパネル、クイックインサイトが完全にサポートされます。 セグメント比較とTarget用のAnalytics(A4T)パネルはサポートされていません。 |
| マーチャンダイジング eVar | マーチャンダイジング eVar は、ADC ベースのデータセットでのみ機能します。ただし、これらのデータが同じ XDM スキーマに厳密に準拠している場合を除きます（前述の製品リストの制限と同様）。 |
| ボットフィルタリング | Analytics Data Connector（ADC）ベースのデータセットの場合、ボットフィルターが適用されます。General bot filtering logic for other datasets is not performed by the [!UICONTROL Experience Platform] or CJA. |
| 処理ルール | ADC ベースのデータセットの場合、処理ルールは引き続き適用されます。 |
| デバイス間での ID のステッチ | Customers are limited to &quot;one-time&quot; stitches of the data via Query Service, or currently must apply this logic to data prior to [!UICONTROL Experience Platform] data ingestion. |

## 現在はサポートされていませんが、予定されています

| 機能 | メモ |
| --- | --- |
| 貢献度分析 | サポートが予定されています。 |
| Segment IQ | サポートが予定されています。 |
| セグメントの公開（Workspace から Experience Cloud へのセグメントの送信） | サポートが予定されています。 |
| ユーザー権限／データアクセス制御 | CJA のすべてのユーザーは同じアクセス制御を持っています。つまり、すべてのユーザーがすべての接続、データビューなどにアクセスできます。基本的に、すべてのユーザーは CJA の管理者レベルのユーザーです。2020 年にサポートが予定されています。 |
| CSV のダウンロード | サポートが予定されています。 |
| 予定レポート／プロジェクト | サポートが予定されています。 |
| アラート | サポートが予定されています。 |
| カスタムカレンダー | サポートが予定されています。 |
| マーケティングチャネル | サポートが予定されています。 |
| PDF の書き出し | サポートが予定されています。 |
| レポート API へのアクセス | サポートが予定されています。API 2.0 でのみ利用できるようになる予定です。 |
| デバイスグラフでの ID のステッチ | サポートが予定されています。 |

## サポートの予定はありません。

| 機能 | メモ |
| --- | --- |
| A4T | まだサポートの予定はありません。 |
| ビデオ分析 | まだサポートの予定はありません。 |
| Advertising Cloud | まだサポートの予定はありません。 |
| Report Builder（Excel プラグイン） | まだサポートの予定はありません。 |
| Activity Map | まだサポートの予定はありません。 |
| 分類ルールビルダー | まだサポートの予定はありません。 |
| 概要データソース | まだサポートの予定はありません。 |
| リアルタイムレポート | まだサポートの予定はありません。 |

## サポートされません

| 機能 | メモ |
| --- | --- |
| クロスデバイス Coop を使用した人指標 |  |
| Reports &amp; Analytics のダッシュボード |  |
| Reports &amp; Analytics のブックマーク |  |
| Reports &amp; Analytics のターゲット |  |
| Reports &amp; Analytics のカレンダーイベント |  |
| Ad Hoc Analysis |  |
| Data Warehouseレポート | [!UICONTROL Experience Platformクエリサービス] (CJA)は、これらの使用例の新しいインターフェイスとなります。 |
| Mobile Services |  |
| データフィード |  |
