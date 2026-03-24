---
title: Adobe Analytics データフィード列のCustomer Journey Analyticsへのマッピング
description: 特定のAdobe Analytics データフィード列を取得する方法を決定し、Customer Journey Analyticsの実装でそのラフ相当を決定します。
feature: Components
hide: true
hidefromtoc: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: b0be8b726c4fab1bf9bb5f9462be84f39bdf184a
workflow-type: tm+mt
source-wordcount: '3768'
ht-degree: 48%

---

# Adobe Analytics データフィード列のCustomer Journey Analyticsへのマッピング

Adobe AnalyticsとCustomer Journey Analytics データフィード列の真の1:1 マッピングは不可能です。 2つの製品は根本的に異なり、各組織の実装は大きく異なる可能性があります。

このリファレンスは、データエンジニアがAdobe Analytics データフィード列を評価し、ワークフローに最も近いCustomer Journey Analyticsの同等を特定するのに役立ちます。

>[!NOTE]
>
>この参照には、[Analytics データフィード列リファレンス &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference)に基づいて、Adobeが現在と見なす列のみが含まれます。 この表に記載されていないAnalytics データフィード列を積極的に使用している場合は、組織のソリューション設計文書を参照して、Customer Journey Analyticsでの最適な同等の値を判断してください。

+++**`accept_language`**

イメージリクエストの Accept-Language HTTP ヘッダーで指定されている受け入れ可能なすべての言語のリスト。

+++

+++**`adload`**

メディア広告の読み込み

{{cja-df-post}}

+++

+++**`aemassetid`**

一連の Adobe Experience Manager Assets のアセット ID（GUID）に対応する複数値の変数。インプレッションイベントを増分します。

{{cja-df-post}}

+++

+++**`aemassetsource`**

アセットイベントのソースを識別します。Adobe Experience Manager で使用されます。

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

Adobe Experience Manager アセットのアセット ID。クリックイベントを増分します。

{{cja-df-post}}

+++

+++**`amo_cid`**

Adobe Advertising統合で使用されるAMO ID ディメンション。

{{cja-df-post}}

+++

+++**`amo_ef_id`**

Adobe Advertising統合で使用されるAMO EF ID ディメンション。

{{cja-df-post}}

+++

+++**`browser`**

ブラウザーを表す数値ID。

{{cja-df-lookup}}

+++

+++**`browser_height`**

ブラウザーの高さディメンション。

{{cja-df-post}}

+++

+++**`browser_width`**

ブラウザーの幅

{{cja-df-post}}

+++

+++**`campaign`**

トラッキングコードディメンション。

{{cja-df-post}}

+++

+++**`carrier`**

携帯電話会社を指定します。

{{cja-df-lookup}}

{{cja-df-ua}}

+++

+++**`channel`**

サイトのセクションのディメンション：

{{cja-df-post}}

+++

+++**`ch_hdr`**

HTTP リクエストヘッダーを通じて収集されたクライアントヒント。

Adobe Analyticsでは、クライアントヒントがこの列に連結された文字列として含まれていました。 `user_agent`列よりも現代的なアプローチと見なされます。

{{cja-df-ua}}

+++

+++**`ch_js`**

User-Agent クライアントヒント JavaScript API を通じて収集されたクライアントヒント。

Adobe Analyticsでは、クライアントヒントがこの列に連結された文字列として含まれていました。 `user_agent`列よりも現代的なアプローチと見なされます。

Web SDKの設定時に[`highEntropyUserAgentHints`](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/commands/configure/context) コンテキスト文字列を使用して、このデータを収集できます。 1つの長い連結された文字列の代わりに、複数のXDM フィールドが入力されます。

* **オペレーティングシステムのバージョン**: `xdm.environment.browserDetails.userAgentClientHints.platformVersion`
* **アーキテクチャ**: `xdm.environment.browserDetails.userAgentClientHints.architecture`
* **デバイスモデル**: `xdm.environment.browserDetails.userAgentClientHints.model`
* **ビット数**: `xdm.environment.browserDetails.userAgentClientHints.bitness`
* **ブラウザーベンダー**: `xdm.environment.browserDetails.userAgentClientHints.vendor`
* **ブラウザー名**: `xdm.environment.browserDetails.userAgentClientHints.brand`
* **ブラウザーバージョン**: `xdm.environment.browserDetails.userAgentClientHints.version`

詳しくは、[&#x200B; ユーザーエージェントクライアントヒント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/use-cases/client-hints)を参照してください。

{{cja-df-ua}}

+++

+++**`clickmaplink`**

Activity Mapリンクディメンション：

{{cja-df-post}}

{{cja-df-na}}

Customer Journey AnalyticsはまだActivity Mapをサポートしていないため、この列は適用されません。

+++

+++**`clickmaplinkbyregion`**

Activity Mapのリンクをリージョンディメンションごとに示します。

{{cja-df-post}}

{{cja-df-na}}

Customer Journey AnalyticsはまだActivity Mapをサポートしていないため、この列は適用されません。

+++

+++**`clickmappage`**

Activity Mapのページディメンション：

{{cja-df-post}}

{{cja-df-na}}

Customer Journey AnalyticsはまだActivity Mapをサポートしていないため、この列は適用されません。

+++

+++**`clickmapregion`**

Activity Map地域のディメンション：

{{cja-df-post}}

{{cja-df-na}}

Customer Journey AnalyticsはまだActivity Mapをサポートしていないため、この列は適用されません。

+++

+++**`code_ver`**

イメージリクエストのコンパイルと送信に使用される API またはクライアント SDK のバージョン。

+++

+++**`color`**

`c_color`列の値に基づく色深度ID。

{{cja-df-lookup}}

+++

+++**`connection_type`**

接続タイプのディメンションを表す数値ID。

{{cja-df-lookup}}

+++

+++**`cookies`**

Cookie サポートディメンション：<br>Y：有効<br>N：無効<br>U：不明

{{cja-df-post}}

+++

+++**`country`**

訪問者の国を表す数値 ID。`country.tsv`ルックアップテーブルを参照します。

{{cja-df-lookup}}

+++

+++**`currency`**

取引で使用された通貨のコード。`currencyCode` を使用して設定します。

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

`connection_type` 列と関連しています。よく使用される値は LAN/Wi-Fi、Mobile Carrier、Modem です。

+++

+++**`curr_factor`**

通貨の小数点以下桁を指定します。 通貨変換に使用されます。 例えば、USD では小数点以下 2 桁が使用されるので、この列の値は `2` になります。

+++

+++**`curr_rate`**

取引が発生した際の為替レート。アドビは、XE と提携して、当日の為替レートを判定します。

+++

+++**`customer_perspective`**

ヒットがモバイルのバックグラウンドヒットかどうかを判断します。

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analyticsには、ヒットのコンテキストに基づいてヒットを自動的に含めたり除外したりするイベントタイプのネイティブコンセプトはありません。 `xdm.eventType`を使用して、ほとんどのレポートに含めるイベントと除外するイベントを決定できます。

+++

+++**`cust_hit_time_gmt`**

タイムスタンプに対応するレポートスイートの場合のみ。ヒットと共に送信されたタイムスタンプ（UNIX® 時間に基づく）。

Customer Journey Analyticsには、タイムスタンプと非タイムスタンプのレポートスイートの概念がありません。 代わりに`xdm.timestamp`を使用し、必要に応じてコンポーネント設定を調整してください。

{{cja-df-post}}

+++

+++**`cust_visid`**

`visitorID` を使用して設定されている場合のカスタム訪問者 ID。

Customer Journey Analyticsは、[`identityMap`](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/profile/identitymap)を使用して任意の数のIDをサポートします。 組織でカスタム IDを使用している場合は、ID マップ内にある可能性があります。

{{cja-df-post}}

+++

+++**`c_color`**

カラーパレットのビット深度。色深度ディメンションの計算の一環として使用されます。 AppMeasurement では JavaScript 関数 `screen.colorDepth()` が使用されます。

+++

+++**`daily_visitor`**

ヒットが新しい日別訪問者であるかどうかを判定するフラグ。

+++

+++**`dataprivacyconsentoptin`**

同意管理のオプトインディメンション。 ヒットごとに複数の値が存在する可能性があります（パイプ（`\|`）区切り）。有効な値には、`DMP` および `SELL` などがあります。

組織がデータ管理プラットフォームを持っている場合、このディメンションに目的のXDM フィールドが入力される可能性があります。

+++

+++**`dataprivacyconsentoptout`**

同意管理のオプトアウトディメンション。 ヒットごとに複数の値が存在する可能性があります（パイプ（`\|`）区切り）。有効な値には、`SSF`、`DMP`、`SELL` などがあります。

組織がデータ管理プラットフォームを持っている場合、このディメンションに目的のXDM フィールドが入力される可能性があります。

+++

+++**`date_time`**

レポートスイートのタイムゾーンに基づいて判読可能な形式で表現されたヒットの時刻。

`xdm.timestamp`を使用して、**[!UICONTROL 日付]**&#x200B;または&#x200B;**[!UICONTROL 日時]** [形式](/help/data-views/component-settings/format.md) コンポーネント設定を適用できます。

+++

+++**`domain`**

ドメイン ディメンション。 訪問者のインターネットアクセスポイントに基づいています。

**[!UICONTROL データストリームの設定]**&#x200B;時に[&#x200B; ネットワークルックアップ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)を有効にします。 スキーマに含まれている場合、XDM フィールドは`xdm.environment.domain`です。

+++

+++**`duplicated_from`**

ヒットコピー VISTA ルールを含んだレポートスイートでのみ使用されます。ヒットがどのレポートスイートからコピーされたかを示します。

{{cja-df-na}}

Customer Journey AnalyticsにはVISTA ルールの概念がないため、この列は適用されません。

+++

+++**`duplicate_events`**

重複としてカウントされた各イベントを一覧表示します。

{{cja-df-na}}

Customer Journey Analyticsには、すべての指標の重複排除フラグとして機能する単一のフィールドはありません。 代わりに、各指標には独自の[指標の重複排除コンポーネント設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication)が含まれます。 そのため、このAdobe Analytics データフィード列に対応するフィールドはCustomer Journey Analyticsにありません。

+++

+++**`duplicate_purchase`**

このヒットの購入イベントが重複しているので無視されるかどうかを判定するフラグ。

このAnalytics データフィード列への直接翻訳はありませんが、購入の重複を排除する機能は引き続き存在します。 [[!UICONTROL Commerce Details]](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/event/commerce-details) フィールドグループを使用している場合、[重複排除ID](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication)が&#x200B;**[!UICONTROL の]**&#x200B;指標の重複排除コンポーネント設定`xdm.commerce.purchases.id`を設定できます。

重複する購入のフラグを設定する場合に直接翻訳が必要な場合は、ルールセットの[Deduplicate](/help/data-views/derived-fields/derived-fields.md)関数を使用して&#x200B;**派生フィールド**&#x200B;を使用できます。

+++

+++**`ef_id`**

Adobe Advertising統合で使用されるEF ID。

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

カスタム変数 1 ～ 250。EVar ディメンションで使用されます。 eVar の使用方法は組織ごとに異なります。組織における各 eVar への値の設定方法について詳しくは、それぞれの組織に固有のソリューションデザインドキュメントを参照してください。

{{cja-df-post}}

+++

+++**`event_list`**

ヒット時にトリガーされたイベントを表す数値 ID のコンマ区切りリスト。コマースイベントとカスタムイベント 1 ～ 1000の両方が含まれます。 `event.tsv` ルックアップを使用します。

この列は、実装に応じて、何十種類もの指標にマッピングされる可能性があります。 Adobeでは、Customer Journey Analyticsの各指標をこのAnalytics データフィード列で表される数値にマッピングするために、次のプロセスをお勧めします。

1. `event.tsv` ルックアップを使用して、各数値をメトリック名にマッピングします。
1. ソリューションデザインドキュメントを使用して、各Analytics イベント名をCustomer Journey Analyticsの対応する指標名にマッピングします。
1. データビューUIでマッピングされたコンポーネントを選択し、そのコンポーネント IDをメモします。 コンポーネント IDが操作しにくい場合は、データフィードのエイリアス ID フィールドに入力し、代わりにそれを使用できます。
1. 組織が使用するあらゆる指標について、この手順を繰り返します。

{{cja-df-post}}

スキーマで[[!UICONTROL Commerceの詳細]](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/event/commerce-details) フィールドグループを使用している場合、一部の指標は次のXDM フィールドに直接マッピングされる場合があります。

* **チェックアウト**: `xdm.commerce.checkouts.value`
* **買い物かごに追加**: `xdm.commerce.productListAdds.value`
* **買い物かごが開きます**: `xdm.commerce.productListOpens.value`
* **買い物かごからの削除**: `xdm.commerce.productListRemovals.value`
* **カートビュー**: `xdm.commerce.productListViews.value`
* **製品ビュー**: `xdm.commerce.productViews.value`
* **注文**: `xdm.commerce.purchases.value`

一部の指標では、Adobe Analyticsで重複排除を完全に制御できるイベントのシリアル化を使用する場合があります。 [指標の重複排除](/help/data-views/component-settings/metric-deduplication.md) コンポーネント設定を使用して、重複排除パリティを実現できます。

* Adobe Analyticsで訪問別に指標の重複排除を行う場合は、その指標のコンポーネント設定で重複排除スコープをセッションに設定できます。
* 指標がAdobe Analyticsのイベント IDによって重複を排除する場合、その指標のXDM オブジェクトに`value`と`id` フィールドの両方が含まれている可能性があります。 スキーマで[[!UICONTROL Commerce Details]](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/event/commerce-details) フィールドグループを使用している場合、これらの指標はXDM フィールドに存在する可能性があります。指標のコンポーネント設定で&#x200B;**[!UICONTROL 重複排除ID]** フィールドを設定できます。

   * **チェックアウト**: `xdm.commerce.checkouts.id`
   * **買い物かごに追加**: `xdm.commerce.productListAdds.id`
   * **買い物かごが開きます**: `xdm.commerce.productListOpens.id`
   * **買い物かごからの削除**: `xdm.commerce.productListRemovals.id`
   * **カートビュー**: `xdm.commerce.productListViews.id`
   * **製品ビュー**: `xdm.commerce.productViews.id`

受注指標の重複を除外する場合は、`duplicate_purchase`を参照してください。

+++

+++**`exclude_hit`**

ヒットがレポートから除外されるかどうかを判定するフラグ。 除外されたヒットに対しては `visit_num` 列が増分されません。

Customer Journey Analyticsは、標準搭載の「除外されたヒット」を尊重しません。 ただし、特定のヒットを除外するようにフラグを付けるXDM フィールドがある場合は、この機能を再作成できます。

1. 除外されたヒットをフラグするXDM フィールドが、コンポーネント（ディメンションまたは指標）として含まれていることを確認します（このフラグの設定方法に応じて）。 レポート [で「](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/component-settings/overview)非表示」コンポーネントを選択すると、このフィールドに有益である可能性が高いです。
1. [&#x200B; データビュー設定](/help/data-views/session-settings.md)で、**[!UICONTROL セグメントを追加]** ドロップダウンメニューを選択し、**[!UICONTROL セグメントを作成]**&#x200B;を選択します。
1. 除外ヒットコンポーネントが存在するすべてのイベント、または除外する値を含むすべてのイベントを除外するセグメントを作成します。
1. セグメントとデータビューの両方で&#x200B;**[!UICONTROL 保存]**&#x200B;を選択します。

除外されたヒットは、Customer Journey Analytics レポートには存在しませんが、データフィードの書き出しでは引き続き使用できます。

+++

+++**`first_hit_pagename`**

入口ページの元のディメンション。 訪問者のオリジナルの入口ページ名。

+++

+++**`first_hit_page_url`**

訪問者の本当に最初の URL。

+++

+++**`first_hit_referrer`**

訪問者の本当に最初の参照 URL。

+++

+++**`first_hit_ref_domain`**

元の参照ドメインディメンション。 `first_hit_referrer` に基づきます。訪問者の本当に最初の参照ドメイン。

+++

+++**`first_hit_ref_type`**

訪問者の最初のリファラーのリファラータイプを表す数値ID。

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

訪問者の最初のヒットのタイムスタンプ（UNIX® 時間）。

+++

+++**`geo_city`**

ヒットが発生した市区町村の名前（IP アドレスに基づく）。Cities ディメンションで使用されます。

+++

+++**`geo_country`**

ヒットが発生した国の略称（IP アドレスに基づく）。国ディメンションで使用されます。

+++

+++**`geo_dma`**

ヒットが発生したデモグラフィック地域の数値 ID（IP アドレスに基づく）。米国のDMA ディメンションで使用されます。

+++

+++**`geo_region`**

ヒットが発生した州または地域の名前（IP アドレスに基づく）。「リージョン」ディメンションで使用されます。

+++

+++**`geo_zip`**

ヒットが発生した場所の郵便番号（IP アドレスに基づく）。Zip コードディメンションを入力するのに役立ちます。 関連トピック 「`zip`」を参照してください。

+++

+++**`hitid_high`**

`hitid_low` と共に使用し、ヒットを識別します。

+++

+++**`hitid_low`**

`hitid_high` と共に使用し、ヒットを識別します。

+++

+++**`hit_source`**

ヒットソース。ヒットソース 1と2は請求されます。 <br>1: タイムスタンプのない標準的な画像リクエスト <br>2: タイムスタンプ付きの標準的な画像リクエスト <br>3: タイムスタンプ付きのライブデータソースアップロード <br>4：未使用<br>5：汎用データソースアップロード <br>6：未使用、処理中データソースアップロード <br>7: TransactionID データソースのアップロード <br>8：未使用、以前のバージョンのAdobe Advertising データソース <br>9：未使用、Adobe Social サマリーメトリクス <br>10: Audience Manager サーバーサイド転送が使用

+++

+++**`hit_time_gmt`**

ヒットを受信したアドビデータ収集サーバーのタイムスタンプ（UNIX® 時間に基づく）。

+++

+++**`hourly_visitor`**

ヒットが新しい時間別訪問者であるかどうかを判定するフラグ。

+++

+++**`ip`**

イメージリクエストの HTTP ヘッダーに基づく IPv4 アドレス。`ipv6` とは相互排他的です。難読化されていない IP アドレスがこの列に含まれている場合、`ipv6` は空白になります。

+++

+++**`ipv6`**

圧縮された IPv6 アドレス（使用可能な場合）。`ip` とは相互排他的です。難読化されていない IP アドレスがこの列に含まれている場合、`ip` は空白になります。

+++

+++**`javascript`**

`j_jscript`に基づくJavaScript バージョンのルックアップ ID。

{{cja-df-lookup}}

+++

+++**`java_enabled`**

Java対応ディメンション。 <br>Y：有効<br>N：無効<br>U：不明

{{cja-df-post}}

+++

+++**`j_jscript`**

ブラウザーでサポートされている JavaScript のバージョン。

+++

+++**`language`**

訪問者の言語を表す数値ID。

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

前回のヒットのタイムスタンプ（UNIX® 時間）。前回の訪問からの日数ディメンションの計算に使用します。

+++

+++**`last_purchase_num`**

顧客ロイヤルティディメンション。 訪問者がこれまでに行った購入の回数。<br>0：過去に購入したことがない（顧客以外）<br>1：過去に 1 回購入したことがある（新規顧客）<br>2：過去に 2 回購入したことがある（リターン顧客）<br>3：過去に 3 回以上購入したことがある（常連客）

+++

+++**`last_purchase_time_gmt`**

前回の購入後の日数ディメンションで使用されます。 前回行った購入のタイムスタンプ（UNIX® 時間）。初回の購入やこれまでに購入を行っていない訪問者の場合、この値は `0` になります。

+++

+++**`latlon1`**

ロケーション（半径 10 km 以内）

+++

+++**`latlon23`**

ロケーション（半径 100 m 以内）

+++

+++**`latlon45`**

ロケーション（半径 1 m 以内）

+++

+++**`mcvisid`**

Experience Cloud 訪問者 ID。2 つの連結された 64 ビットの数値から構成され、19 桁にパディングされた 128 ビットの数値。

+++

+++**`mc_audiences`**

訪問者が属している Audience Manager セグメント ID のリスト。`post_mc_audiences` 列の区切り文字が `--**--` に変更されます。

{{cja-df-post}}

+++

+++**`mobileaction`**

モバイルアクション。モバイル実装で `trackAction` が呼び出されると、自動的に収集されます。アプリケーション内で自動的にアクションを渡すことができるようにします。

{{cja-df-post}}

+++

+++**`mobileappid`**

モバイルアプリケーション ID。アプリケーションの名前とバージョンを次の形式で格納します。`[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Apteligent データコネクタで使用されます。Apteligent で使用されるアプリケーション ID。

+++

+++**`mobileappperformancecrashid`**

Apteligent データコネクタで使用されます。Apteligent で使用されるクラッシュ ID。

+++

+++**`mobileappstoreobjectid`**

[!DNL Appfigures] データコネクタで使用されます。App Store オブジェクト ID。

+++

+++**`mobilebeaconmajor`**

Mobile Services ビーコンのメジャー番号

+++

+++**`mobilebeaconminor`**

Mobile Services ビーコンのマイナー番号

+++

+++**`mobilebeaconproximity`**

Mobile Services ビーコンの近接性

+++

+++**`mobilebeaconuuid`**

Mobile Services ビーコンの UUID

+++

+++**`mobilecampaigncontent`**

リンクを表示したコンテンツの名前または ID。モバイルアプリケーションの獲得によって設定されます。

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

マーケティングメディア（バナー、電子メールなど）。モバイルアプリケーションの獲得によって設定されます。

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

キャンペーンの名前。キャンペーン変数にも格納されます。モバイルアプリケーションの獲得によって設定されます。

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

オリジナルリファラー（ニュースレターやソーシャルメディアネットワークなど）。モバイルアプリケーションの獲得によって設定されます。

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

この獲得で追跡する有料キーワードまたはその他の用語。モバイルアプリケーションの獲得によって設定されます。

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

アプリが起動された曜日を表す数値。

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

アプリの初回実行時からの経過日数。

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

アプリの前回実行時からの経過日数。

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

コンテキストデータ変数 `a.deeplink.id` から収集します。獲得レポートで、モバイル獲得リンクの識別子として使用されます。

+++

+++**`mobiledevice`**

モバイルデバイス名。iOS の場合は、コンマ区切りの 2 桁の文字列として格納されます。最初の数字はデバイスの世代を表し、2 番目の数字はデバイスファミリーを表します。

{{cja-df-post}}

+++

+++**`mobilehourofday`**

アプリが起動された時刻を定義します。24 時間形式で示します。

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

モバイルインストール日。モバイルアプリをユーザーが最初に開いた日を示します。

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

モバイルアプリが起動されるたびに 1 ずつ増分されます。

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

コンテキストデータ変数 `a.message.button.id` から収集します。メッセージを閉じたボタンを識別するために、アプリ内メッセージで使用します。

{{cja-df-post}}

+++

+++**`mobilemessageid`**

アプリ内メッセージ ID

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

アプリ内メッセージオンライン

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

コンテキストデータ変数 `a.push.optin` から収集します。ユーザーがプッシュメッセージをオプトインする場合は「true」に設定します。それ以外の場合、値は「false」です。

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

コンテキストデータ変数 `a.push.payloadid` から収集します。ペイロード識別子としてプッシュメッセージで使用します。

{{cja-df-post}}

+++

+++**`mobileosversion`**

Mobile Services のオペレーティングシステムのバージョン。

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

コンテキストデータ変数 `a.loc.acc` から収集します。収集時の GPS の精度をメートル単位で示します。

+++

+++**`mobileplacecategory`**

コンテキストデータ変数 `a.loc.category` から収集します。特定の場所のカテゴリを示します。

+++

+++**`mobileplaceid`**

コンテキストデータ変数 `a.loc.id` から収集します。特定の対象地点の識別子。

+++

+++**`mobilepushoptin`**

Mobile Services Push オプトイン

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

Mobile Services Push ペイロード ID

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Mobile Services の起動コンテンツ

+++

+++**`mobilerelaunchcampaignmedium`**

Mobile Services の起動メディア

+++

+++**`mobilerelaunchcampaignsource`**

Mobile Services の起動ソース

+++

+++**`mobilerelaunchcampaignterm`**

Mobile Services の起動条件

+++

+++**`mobilerelaunchcampaigntrackingcode`**

コンテキストデータ変数 `a.launch.campaign.trackingcode` から収集します。キャンペーン立ち上げのトラッキングコードとして、獲得で使用します。

+++

+++**`mobileresolution`**

モバイルデバイスの解像度。`[Width] x [Height]` 画素数.

{{cja-df-post}}

+++

+++**`mobile_id`**
ユーザーがモバイルデバイスを使用している場合は、そのデバイスの数値 ID。

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

訪問者が当月固有であるかどうかを判定するフラグ。

+++

+++**`mvvar1`** - **`mvvar3`**

変数値をリストします。実装に応じたカスタム値の区切りリストを含んでいます。`post_mvvar1`〜`post_mvvar3` の列は元の区切り文字を `--**--` に置き換えます。

{{cja-df-post}}

+++

+++**`mvvar1_instances`**～**`mvvar3_instances`**

現在のヒットに設定されたリスト変数値。元の区切り文字を `--**--` に置き換えます。通常、`post` 列にはデータは含まれません。

{{cja-df-post}}

+++

+++**`new_visit`**

現在のヒットが新しい訪問であるかどうかを判定するフラグ。訪問後 30 分間非アクティブであった場合にアドビによって設定されます。

+++

+++**`os`**

訪問者のオペレーティングシステムを表す数値 ID。`user_agent` 列に基づきます。

{{cja-df-lookup}}

[&#x200B; データストリームを設定する場合](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)、**[!UICONTROL デバイス検索]**&#x200B;を有効にできます。 有効な場合は、**[!UICONTROL オペレーティングシステム]**&#x200B;のチェックボックスをオンにします。 これにより、スキーマにこれらのフィールドが含まれている場合、次のXDM フィールドが自動的に入力されます。

* **OS ベンダー**: `xdm.environment.operatingSystemVendor`
* **OS名**: `xdm.environment.operatingSystem`
* **OS バージョン**: `xdm.environment.operatingSystemVersion`

{{cja-df-ua}}

+++

+++**`pagename`**

ページディメンション： `pagename` 変数が空の場合、Analytics では代わりに `page_url` が使用されます。

{{cja-df-post}}

+++

+++**`pagename_no_url`**

`pagename` に似ていますが、`page_url` にフォールバックされません。`post` 列のみが使用できます。

{{cja-df-post}}

+++

+++**`page_event`**

画像リクエストで送信されるヒットのタイプ（標準ヒット、ダウンロードリンク、カスタムリンク、終了リンク）。

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

リンクトラッキングのイメージリクエストでのみ使用されます。 ダウンロードリンク、離脱リンクまたはクリックされたカスタムリンクの URL。

{{cja-df-post}}

+++

+++**`page_event_var2`**

リンクトラッキングのイメージリクエストでのみ使用されます。 リンクのカスタム名（指定した場合）。`page_event`の値に応じて、カスタムリンク、ダウンロードリンクまたは終了リンクを設定します。

{{cja-df-post}}

+++

+++**`page_type`**

「ページが見つかりません」ディメンション。通常、404 ページに使用されます。

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: ヒットのURL。 テキストのデータタイプを使用します。<br>**`post_page_url`**: リンクトラッキング画像要求（`tl()`）の対象から外されました。

{{cja-df-post}}

+++

+++**`paid_search`**

ヒットが有料検索の検出に一致するかどうかを判定するフラグ。

+++

+++**`persistent_cookie`**

永続的なCookie サポートディメンションで使用されます。 各ヒット後に破棄されない Cookie を訪問者がサポートしているかどうかを示します。

{{cja-df-post}}

+++

+++**`pointofinterest`**

Mobile Services 目標地点の名前

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

目標地点中心までの Mobile Services の距離

{{cja-df-post}}

+++

+++**`product_list`**

`products` ページ変数。 カテゴリ、製品、単位、収益など、複数のディメンションと指標を入力するのに役立ちます。

{{cja-df-post}}

+++

+++**`prop1`**～**`prop75`**

カスタムトラフィック変数 1 ～ 75。Prop ディメンションで使用されます。

{{cja-df-post}}

+++

+++**`purchaseid`**

購入の一意な識別子（`purchaseID` 変数を使用して設定）。`duplicate_purchase` 列で使用されます。

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

ヒットが新しい四半期別訪問者であるかどうかを判定するフラグ。

+++

+++**`referrer`**

リファラーディメンション： `referrer` のデータ型は varchar(255)、`post_referrer` のデータ型は varchar(244) です。

{{cja-df-post}}

+++

+++**`ref_domain`**

参照ドメインディメンション。 `referrer` 列に基づきます。

+++

+++**`ref_type`**


ヒットのリファラルのタイプを表す数値 ID。リファラータイプのディメンションで使用されます。<br>1: サイト内<br>2：その他のweb サイト <br>3：検索エンジン <br>4：ハードドライブ <br>5:USENET<br>6：入力/ブックマーク済み（リファラーなし） <br>7：電子メール <br>8：いいえJavaScript<br>9：ソーシャルネットワーク <br>10：対話型AI ツール

+++

+++**`resolution`**

モニターの解像度を表す数値 ID。解像度のモニターのディメンションで使用されます。

{{cja-df-lookup}}

+++

+++**`search_engine`**

サイトに訪問者を誘導した検索エンジンを表す数値 ID。検索エンジンのディメンションで使用されます。

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

「すべての検索ページのランク」ディメンションで使用されます。ユーザーがクリックスルーしてサイトに到達する前にサイトが表示された検索結果ページを示します。

+++

+++**`secondary_hit`**

ヒットがセカンダリヒットかどうかを判定するフラグ。 このフラグは通常、ヒットをコピーするマルチスイートタグ付けおよび VISTA ルールで発生します。

+++

+++**`sourceid`**

ソース ID

+++

+++**`stats_server`**

未使用。ヒットを処理したアドビの内部サーバー。

+++

+++**`s_kwcid`**

Adobe Advertising 統合で使用されるキーワード ID。

{{cja-df-post}}

+++

+++**`s_resolution`**

画面解像度の未処理の値。JavaScript 関数 `screen.width x screen.height` を使用して収集します。

+++

+++**`tnt`**

Adobe Target 統合で使用されます。現在認定されているすべてのテストを表します。形式は次のとおりです。`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`

{{cja-df-post}}

+++

+++**`tnt_action`**

Adobe Target 統合で使用されます。ヒットが認定されるすべてのテストを表します。

{{cja-df-post}}

+++

+++**`tnt_instances`**

Adobe Target 統合で使用されます。Target インスタンス変数。

+++

+++**`transactionid`**

後でデータソースを通じて様々なデータポイントをアップロードできる、一意のID。 `transactionID` 変数を使用して収集します。

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

画像リクエストが切り捨てられたことを示すフラグ（部分的なヒットを受け取りました）。 <br>Y：ヒットが切り捨てられました。ヒットの一部を受信しました。<br>N：ヒットが切り捨てられませんでした。すべてのヒットを受信しました。

+++

+++**`t_time_info`**

訪問者の現地時刻。形式：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

未使用。レポートスイート ID の数値 ID。代わりに、`username` を使用してください。

+++

+++**`username`**

ヒットのレポートスイート ID。

+++

+++**`user_agent`**

イメージリクエストの HTTP ヘッダーで送信されるユーザーエージェント文字列。

+++

+++**`user_hash`**

未使用。 レポートスイート ID のハッシュ。代わりに、`username` を使用してください。

+++

+++**`user_server`**

サーバーディメンションで使用されます。

{{cja-df-post}}

+++

+++**`va_closer_detail`**

ラストタッチの詳細ディメンション。

+++

+++**`va_closer_id`**

ラストタッチチャネルディメンションを識別する数値ID。

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

ファーストタッチの詳細ディメンション。

+++

+++**`va_finder_id`**

ファーストタッチチャネルのディメンションを識別する数値ID。

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

マーケティングチャネルインスタンスを識別するフラグ。

+++

+++**`va_new_engagement`**

マーケティングチャネルの新規エンゲージメントを特定するフラグ。

+++

+++**`video`**

コンテンツストリーミングメディアサービスディメンションです。

{{cja-df-post}}

+++

+++**`videoad`**

Ad streaming media services ディメンションです。

{{cja-df-post}}

+++

+++**`videoadinpod`**

ポッド位置の広告ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoadlength`**

広告の長さ（変数）ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoadname`**

広告名（変数）ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoadplayername`**

広告プレーヤー名のストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoadpod`**

広告ポッドストリーミングメディアサービスディメンションです。

{{cja-df-post}}

+++

+++**`videoadvertiser`**

広告主ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

アルバムストリーミングメディアサービスディメンション。

+++

+++**`videoaudioartist`**

アーティストストリーミングメディアサービスディメンション。

+++

+++**`videoaudioauthor`**

オーサーストリーミングメディアサービスディメンション。

+++

+++**`videoaudiolabel`**

Label streaming media services ディメンション。

+++

+++**`videoaudiopublisher`**

パブリッシャーストリーミングメディアサービスディメンション。

+++

+++**`videoaudiostation`**

Station ストリーミングメディアサービスディメンション。

+++

+++**`videocampaign`**

Campaign ID ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videochannel`**

コンテンツチャネルストリーミングメディアサービスディメンションです。

{{cja-df-post}}

+++

+++**`videochapter`**

Chapter ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videocontenttype`**

コンテンツタイプストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videodaypart`**

Day パートのストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoepisode`**

エピソードストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videofeedtype`**

メディアフィードの種類ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videogenre`**

ジャンル別ストリーミングメディアサービスディメンション。 このディメンションでは、コンマで区切られた複数の値が同じヒットに許可されます。

{{cja-df-post}}

+++

+++**`videolength`**

コンテンツ長（変数）ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videomvpd`**

MVPDストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoname`**

コンテンツ名（変数）ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videonetwork`**

ネットワークストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videopath`**

メディアパスストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoplayername`**

コンテンツプレーヤー名ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

平均ビットレートストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

ビットレートは、ストリーミングメディアサービスディメンションを変更します。

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

バッファーイベントストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

合計バッファ時間ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

Dropped frames streaming media services ディメンション。

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

Errors streaming media services ディメンション。

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

ストリーミングメディアサービスディメンションの外部エラーID。 このディメンションでは、複数の値が同じヒットに許可されます。

+++

+++**`videoqoeplayersdkerrors`**

Player SDK エラーID ストリーミングメディアサービスディメンション。 このディメンションでは、複数の値が同じヒットに許可されます。

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

「ストリーミングメディアサービスを開始する時間」ディメンション。

{{cja-df-post}}

+++

+++**`videoseason`**

季節限定のストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videosegment`**

コンテンツセグメントのストリーミングメディアサービス機能。

{{cja-df-post}}

+++

+++**`videosessionid`**

メディアセッション ID ストリーミングメディアサービスディメンション。

{{cja-df-post}}

+++

+++**`videoshow`**

「ストリーミングメディアサービスを表示」ディメンション。

{{cja-df-post}}

+++

+++**`videoshowtype`**

「Show type streaming media services」ディメンション。

{{cja-df-post}}

+++

+++**`videostreamtype`**

ストリームタイプのストリーミングメディアサービスディメンション。

+++

+++**`visid_high`**

`visid_low` と共に使用し、訪問者を一意に識別します。

{{cja-df-post}}

+++

+++**`visid_low`**

`visid_high` と共に使用し、訪問者を一意に識別します。

{{cja-df-post}}

+++

+++**`visid_new`**

ヒットに新しく生成された訪問者 ID が含まれているかどうかを判定するフラグ。

+++

+++**`visid_timestamp`**

訪問者 ID が新しく生成された場合は、訪問者 ID が生成された時刻の UNIX® 時間でのタイムスタンプを示します。

+++

+++**`visid_type`**

内部使用のみ。処理の最適化のためにアドビが内部的に使用します。訪問者の識別に使用された方法を表す数値 ID。<br>`0`：カスタム訪問者 ID または不明／該当なし<br>`1`：IP およびユーザーエージェントのフォールバック<br>`2`：HTTP モバイル加入者ヘッダー<br>`3`：従来の cookie 値（`s_vi`）<br>`4`：フォールバック cookie の値（`s_fid`）<br>`5`：ID サービス

{{cja-df-post}}

+++

+++**`visit_keywords`**

検索キーワードのディメンション： この列では、Adobeで使用されるバックエンドロジックに対応するために、varchar （244）という非標準の文字制限を使用します。 後処理列は`**post_keywords**`ではなく`**post_visit_keywords**`です。

{{cja-df-post}}

+++

+++**`visit_num`**

訪問番号ディメンション。 1 から始まり、各訪問者が新しい訪問を開始するたびに増分されます。

+++

+++**`visit_page_num`**

ヒットの深さディメンション。 訪問者が生成するヒットごとに 1 ずつ増加します。各訪問をリセットします。

+++

+++**`visit_referrer`**

訪問の最初のリファラー。

+++

+++**`visit_ref_domain`**

`visit_referrer` 列に基づきます。訪問の最初の参照ドメイン。

+++

+++**`visit_ref_type`**

訪問の最初のリファラーのリファラータイプを表す数値ID。

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

訪問の最初の検索エンジンを表す数値ID。

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

訪問の最初のヒットのページ。

+++

+++**`visit_start_page_url`**

訪問の最初のヒットのURL。

+++

+++**`visit_start_time_gmt`**

訪問の最初のヒットのタイムスタンプ（UNIX® 時間）。

+++

+++**`weekly_visitor`**

ヒットが新しい週別訪問者であるかどうかを判定するフラグ。

+++

+++**`yearly_visitor`**

ヒットが新しい年別訪問者であるかどうかを判定するフラグ。

+++

+++**`zip`**

Zip コードディメンションを入力するのに役立ちます。 関連トピック 「`geo_zip`」を参照してください。

{{cja-df-post}}

+++
