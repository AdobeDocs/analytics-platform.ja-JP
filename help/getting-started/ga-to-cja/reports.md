---
title: CUSTOMER JOURNEY ANALYTICSのGA4 レポート
description: 各GA4 レポートセクションで同等のCustomer Journey Analyticsを見つけます。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# CUSTOMER JOURNEY ANALYTICSのGA4 レポート

このページは、Analysis WorkspaceでどのGA4 レポートを確認し、それに相当する概算を再作成する場合のルックアップリファレンスとして使用します。 レポートは、GA4のナビゲーションセクションによって整理されています。 GA データをCustomer Journey Analyticsに移行した後に使用できる高度なクロスチャネルレポートのシナリオについては、[Google Analytics データに関するレポート &#x200B;](/help/use-cases/third-party/ga/report.md)を参照してください。

## Realtime

+++Realtime

GA4のリアルタイムレポートでは、過去30分間のアクティビティ（アクティブユーザー、イベントの発生、ユーザーの位置、トラフィックの要因、アクセスしているページなど）が表示されます。

Customer Journey Analyticsには、個別のリアルタイムレポートエリアはありません。 代わりに、Analysis Workspaceでパネルを作成し、**[!UICONTROL リアルタイム更新]**&#x200B;切り替えスイッチ（**Ultimate** パッケージの一部）を有効にして、ビジュアライゼーションが毎分更新されるようにします。

1. 監視するディメンションと指標を含む[&#x200B; フリーフォーム &#x200B;](/help/analysis-workspace/c-panels/freeform-panel.md) パネルを作成します（このトグルは[空白](/help/analysis-workspace/c-panels/blank-panel.md)、[属性](/help/analysis-workspace/c-panels/attribution.md)、および[次または前の項目](/help/analysis-workspace/c-panels/next-previous.md) パネルでも機能します）。 GA4のリアルタイムカードをミラーリングするには、**[!UICONTROL セッション]**&#x200B;を指標として、**[!UICONTROL ページ]**、**[!UICONTROL イベントタイプ]**、**[!UICONTROL 参照ドメイン]**、または&#x200B;**[!UICONTROL 国]**&#x200B;をディメンションとして使用します。
2. **[!UICONTROL リアルタイム更新]** トグルを有効にし、**[!UICONTROL 過去15分]**&#x200B;から&#x200B;**[!UICONTROL 過去24時間]**&#x200B;までの期間を選択します。 データは24時間のローリングウィンドウに制限され、パネルは毎分30分まで更新されます。

リアルタイムのレポートでは、イベントレベルおよびセッションレベルのデータが優先され、ステッチを使用できないため、**[!UICONTROL 人]**&#x200B;よりも&#x200B;**[!UICONTROL セッション]**&#x200B;を優先します。 完全な手順については、[&#x200B; リアルタイム レポートの使用](/help/components/real-time/use-real-time.md)を参照し、使用権限と待ち時間の詳細については、[&#x200B; リアルタイム レポートの概要](/help/components/real-time/real-time.md)を参照してください。

+++

## 獲得

+++ユーザー獲得（ファーストタッチ）

GA4のユーザー獲得レポートでは、ファーストタッチアトリビューションを使用して、各ユーザーを初めてサイトに誘導したチャネル、ソース、メディアに属性が割り当てられます。

Analysis Workspaceで、**[!UICONTROL ファーストタッチ]** アトリビューションモデルを&#x200B;**[!UICONTROL マーケティングチャネル]** ディメンションに適用します。 マーケティングチャネルは、使用する前に設定する必要があります。 [&#x200B; マーケティングチャネル派生フィールドの作成](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)を参照してください。

1. **[!UICONTROL マーケティングチャネル]** ディメンションを[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)にドラッグします。
2. 指標の列ヘッダーを右クリックし、**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**&#x200B;を選択します。
3. 分析に適したルックバックウィンドウで&#x200B;**[!UICONTROL ファーストタッチ]**&#x200B;を選択します。

または、[[!UICONTROL &#x200B; アトリビューション &#x200B;] パネル &#x200B;](/help/analysis-workspace/c-panels/attribution.md)を使用して、ファーストタッチとラストタッチのチャネルのパフォーマンスを並べて比較することもできます。

+++

+++トラフィック獲得（セッションベース）

GA4のトラフィック獲得レポートでは、セッションベースのアトリビューションを使用して、各セッションをそのセッションを開始したチャネル、ソース、メディアに起因させています。 デフォルトのチャネルグループ、ソース/メディア、リファラー、キャンペーンごとに分類できます。

Analysis Workspaceでは、デフォルトの&#x200B;**[!UICONTROL ラストタッチ]** アトリビューションモデルを持つ&#x200B;**[!UICONTROL マーケティングチャネル]** ディメンションにより、セッションベースのチャネルレポートが提供されます。

1. **[!UICONTROL マーケティングチャネル]** ディメンションを[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)にドラッグします。
2. 目的の指標をデフォルトの&#x200B;**[!UICONTROL イベント]**&#x200B;指標と一緒にドラッグします。

GA4の分類は、次のCustomer Journey Analyticsのディメンションに対応しています。

* **チャネル**: **[!UICONTROL マーケティングチャネル]**。 Customer Journey Analyticsにはチャネルグループが組み込まれていません。Analytics ソースコネクタを使用する場合は、**[!UICONTROL マーケティングチャネル]**&#x200B;関数テンプレートを使用して[派生フィールド &#x200B;](/help/data-views/derived-fields/derived-fields.md)として定義するか、Adobe Analyticsからルールを引き継ぎます（[&#x200B; マーケティングチャネルディメンションを使用](/help/use-cases/aa-data/marketing-channels.md)を参照）。
* **Source/中およびリファラー**: **[!UICONTROL 参照ドメイン]**&#x200B;および&#x200B;**[!UICONTROL リファラータイプ]**。
* **Campaign**: GA4の`utm_*` パラメーターは自動的に収集されません。各パラメーターは、ディメンションとして表示される前に、実装中にXDM フィールドにマッピングする必要があります。 キャンペーンの値がトラッキングコードとして届く場合は、**[!UICONTROL トラッキングコード]** ディメンションを使用します。

+++

+++アトリビューションとコンバージョンのパス

ADVERTISINGのアトリビューションレポートでは、さまざまなチャネルがコンバージョンにどのように貢献しているのかを明らかにし、モデル比較やコンバージョンパス分析を可能にします。

Analysis Workspaceで、[[!UICONTROL &#x200B; アトリビューション &#x200B;] パネル &#x200B;](/help/analysis-workspace/c-panels/attribution.md)を使用します。

1. パネルアイコンを選択し、**[!UICONTROL アトリビューション]** パネルをキャンバスにドラッグします。
2. **[!UICONTROL マーケティングチャネル]** ディメンションを&#x200B;**[!UICONTROL Dimensionを追加]** ボックスにドラッグします。
3. コンバージョン指標（購入イベントなど）を「**[!UICONTROL 指標を追加]**」ボックスにドラッグします。
4. 「**[!UICONTROL 作成]**」を選択します。

[!UICONTROL &#x200B; アトリビューションパネル &#x200B;]は、モデル比較テーブルと、訪問者がコンバージョンに至る前に辿った上位パスを示す[!UICONTROL &#x200B; チャネルフロー] ビジュアライゼーションを生成します。 **[!UICONTROL モデルを追加]**&#x200B;を選択して、複数のアトリビューションモデルを同時に比較します。

+++

## エンゲージメント

+++ページと画面

個々のページやアプリの画面に対するパフォーマンス指標を示す、GA4のページと画面レポート。

Analysis Workspaceで、**[!UICONTROL Page]** ディメンションを[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)にドラッグし、目的の指標を追加します。 一般的な指標には、**[!UICONTROL セッション]**、**[!UICONTROL 人]**、**[!UICONTROL 直帰率]**、および&#x200B;**[!UICONTROL セッションあたりの滞在時間]**&#x200B;が含まれます。

URL パス構造（例：`/blog/`または`/products/`）でページをグループ化するには、実装で定義されている&#x200B;**[!UICONTROL サイトセクション]** ディメンションを使用するか、**[!UICONTROL URL解析]**&#x200B;関数を使用してページ URLを解析する[派生フィールド &#x200B;](/help/data-views/derived-fields/derived-fields.md)を作成します。 明示的なページとセクションのマッピングを管理する場合、[&#x200B; ルックアップデータセット &#x200B;](/help/connections/standard-lookups.md)が代わりにグループ化を提供できます。

+++

+++ランディングページ

ユーザーがセッションを開始した際に到達するページを示す、GA4のランディングページレポート。

Analysis Workspaceで、**[!UICONTROL 入口ページ]** ディメンションを[[!UICONTROL 自由形式テーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)にドラッグします。 **[!UICONTROL セッション]**&#x200B;は、このディメンションに最も関連する指標です。

+++

+++イベント

各イベントが発生した回数と、イベントレベルの指標を示すGA4のイベントレポート。

GA4では、イベントには名前とオプションのパラメーターが含まれています（例えば、パラメーター`video_title`を持つイベント `video_play`）。 Customer Journey Analyticsでは、イベント名の標準ディメンションは&#x200B;**[!UICONTROL イベントタイプ]** （`xdm.eventType`から取得）です。 イベントパラメーターは、名前が実装に依存する他のXDM フィールドにマッピングされます。

**[!UICONTROL イベントタイプ]** ディメンションを[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)にドラッグすると、すべてのイベントタイプが&#x200B;**[!UICONTROL イベント]**&#x200B;指標とともに一覧表示されます。

+++

+++主要イベント（コンバージョン）

GA4のキーイベントレポート（旧コンバージョン）では、各キーイベントが名前ごとにカウント（GA4 プロパティ設定でビジネスに不可欠なフラグが付けられたイベント）で一覧表示されます。

Customer Journey Analyticsには「キーイベント」フラグがありません。すべてのインタラクションはイベントであるため、開くコンバージョンのプリセットリストはありません。

名前でGA4のコンバージョンのリストを再作成するには、**セグメントを行**&#x200B;として使用します。 [[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)は、指標を行の位置に配置することはできませんが、セグメントをそこに配置することはできます。

1. コンバージョンごとに、イベントを分離するセグメント（例：`xdm.eventType`が`commerce.purchases`に等しいイベント範囲のセグメント）を作成します。 各セグメントには、表すコンバージョンの後に名前を付けます（例：**Purchases**）。
2. 各コンバージョンセグメントを、行ごとに1つの[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]の行領域にドラッグします。
3. **[!UICONTROL イベント]**&#x200B;指標を列として追加します。 各行には、GA4のキーイベントリストが反映され、コンバージョンのカウントが表示されます。 代わりに&#x200B;**[!UICONTROL People]**&#x200B;を使用して、一意のコンバーターをカウントしてください。

コンバージョン率を追加するには、**[!UICONTROL セッション]**&#x200B;または&#x200B;**[!UICONTROL 人]**&#x200B;で割ったコンバージョン指標として定義された計算指標（指標リストの近くにある&#x200B;**+** アイコンを選択）を作成します。

ここで分離する各コンバージョンは、データビューでの再利用可能な指標として定義することもできます。 設定の方法については、[共通指標](#common-metrics)の下の&#x200B;**カスタムイベント指標→主要イベント**&#x200B;のエントリを参照してください。

+++

## 収益化

+++コマースで購入

GA4のe コマース購入レポートには、商品、収益、数量などの商品レベルの購入データが表示されます。

Customer Journey Analyticsのe コマースレポートでは、購入指標と共に&#x200B;**[!UICONTROL 商品]** ディメンションが使用されます。 このレポートでは、実装がXDM コマースデータ （`xdm.commerce.purchases`、`xdm.commerce.order`、`xdm.productListItems`など）を送信する必要があります。

1. **[!UICONTROL 製品]** ディメンションを[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)にドラッグします。
2. **[!UICONTROL Orders]**、**[!UICONTROL Revenue]**、**[!UICONTROL Units]**&#x200B;などのe コマース指標を、デフォルトの&#x200B;**[!UICONTROL Events]**&#x200B;指標と一緒にドラッグします。

+++

+++購買ジャーニー（funnel）

GA4の購入ジャーニーレポートでは、利用者がショッピングfunnelをどのように利用しているのか（追加からカート、チェックアウトを開始して購入するなど）、そして離脱した場所などが示されます。

Analysis Workspaceで、[**[!UICONTROL &#x200B; フォールアウト &#x200B;]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) ビジュアライゼーションを使用します。

1. ビジュアライゼーションアイコンを選択し、**[!UICONTROL フォールアウト]** ビジュアライゼーションをキャンバスにドラッグします。
2. **[!UICONTROL ページ]** ディメンションを見つけて展開し、個々のページ値を表示します。
3. 最初のfunnel ステップ（商品ページなど）を最初の&#x200B;**[!UICONTROL Add Touchpoint]** スロットにドラッグします。
4. 各ステップごとに顧客接点を追加し続けます。

フォールアウトビジュアライゼーションでは、ページだけでなく、あらゆるディメンション、指標、セグメントをタッチポイントとして受け入れることができるため、GA4のイベントベースのファネルと一致し、イベント、ページ、セグメントを組み合わせたシーケンスにも拡張できます。

+++

+++プロモーション

GA4のプロモーションレポートでは、内部プロモーション（バナー、おすすめの配置）が製品インタラクションをどのように促進するかを示しています。

Customer Journey Analyticsのプロモーションデータでは、XDM スキーマフィールドでプロモーションインプレッション数とクリック数を取得する必要があります。 収集したら、インプレッションとクリック指標を含むプロモーション名ディメンションを含む[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)を作成します。 Customer Journey Analytics管理者と協力して、データビューで使用可能なプロモーションデータを確認します。

+++

+++発行者の広告

GOOGLE Ad ManagerまたはAdMobを利用して、メディア企業が収益化したコンテンツを提供している場合の広告収入を示す、GA4の「メディア企業の広告レポート」。

Customer Journey Analyticsには、パブリッシャーと売上のネイティブな連携がありません。 このデータをレポートするには、ソースコネクタまたはダイレクトデータ取り込みを使用して、広告収益化プラットフォーム（Google Ad ManagerやAdMobなど）からAdobe Experience Platformにデータセットとして取り込みます。 取り込まれたデータは、Customer Journey Analyticsでレポートに使用できます。

+++

## リテンション

+++顧客維持の概要

GA4のリテンションの概要レポートには、複数のリテンションビュー（新規ユーザーとリピートユーザーの比較）と、時間の経過とともに何人のユーザーがリターンするかを示すコホートチャートが含まれています。

**新規ユーザーと再ユーザーの比較**: **[!UICONTROL 最初のセッション]**&#x200B;と&#x200B;**[!UICONTROL リターンセッション]** セグメントを[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)の行として使用します。

1. コンポーネントパネルから&#x200B;**[!UICONTROL 最初のセッション]** セグメントをテーブルの行領域にドラッグし、その下に&#x200B;**[!UICONTROL リターンセッション]** セグメントをドラッグします。
2. 目的の指標をデフォルトの&#x200B;**[!UICONTROL イベント]**&#x200B;指標と一緒に追加します。
3. 時間の経過に伴ってトレンドを作成するには、テーブルの上に[**[!UICONTROL 行]**](/help/analysis-workspace/visualizations/line.md)のビジュアライゼーションをドラッグし、ctrl キー（Windows）またはcmd キー（Mac）を押しながら各行をクリックして両方のセグメントをハイライト表示します。

**一定期間のリテンション**: [**[!UICONTROL &#x200B; コホートテーブル &#x200B;]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) ビジュアライゼーションを使用します。

1. ビジュアライゼーションアイコンを選択し、**[!UICONTROL コホートテーブル]**&#x200B;をキャンバスにドラッグします。
2. **[!UICONTROL 人物]**&#x200B;指標を包含フィールドと返品条件フィールドの両方にドラッグし、**[!UICONTROL ビルド]**&#x200B;を選択します。

[!UICONTROL &#x200B; コホートテーブル &#x200B;]は、最初の期間でユーザーをグループ化し、その後の期間のリターン動作を追跡します。インクルージョン、リターン、および粒度の条件はすべて設定可能です。

+++

## ユーザー

+++デモグラフィック情報

GA4のデモグラフィックの詳細レポートでは、年齢、性別、興味関心などの利用者の特徴（Google Signalsを利用。これには、パーソナライゼーションが有効になっているGoogleアカウントにユーザーがログインする必要があります）と、場所（国、地域、都市）および言語が含まれます。

**場所**&#x200B;はCustomer Journey Analytics ディメンションに直接マッピングします。[[!UICONTROL 自由形式テーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)で&#x200B;**[!UICONTROL 国]**、**[!UICONTROL 地域]**、または&#x200B;**[!UICONTROL 都市]**&#x200B;を使用するか、地理的概要の[[!UICONTROL 地図]](/help/analysis-workspace/visualizations/map.md) ビジュアライゼーションを使用します（**[!UICONTROL 人物]**&#x200B;指標を&#x200B;**[!UICONTROL 指標を]** スロットにドラッグし、**[!UICONTROL ビルド]**&#x200B;を選択します）。

**年齢、性別、興味関心**&#x200B;は、ファーストパーティデータが必要です。 組織がCRM、登録フォーム、または同意ベースの調査を通じてデモグラフィック データを収集する場合は、[&#x200B; プロファイルデータセット &#x200B;](/help/connections/create-connection.md#profile-dataset)として取り込み、イベントデータに結合します。 このアプローチは、同意したファーストパーティ属性を使用するため、GA4の推定Googleシグナルモデルよりも信頼性の高いデータを生成します。

+++

+++技術情報

ブラウザー、オペレーティングシステム、画面解像度、デバイスのカテゴリーが表示されたGA4の技術レポート。

Analysis Workspaceでは、次のディメンションがGA4のテクノロジーディメンションにマッピングされ、各ディメンションは標準のXDM フィールドから取得されます。

| GA4の技術的ディメンション | Analysis Workspace ディメンション | XDM フィールド |
|---|---|---|
| ブラウザー | **[!UICONTROL ブラウザー]** | `xdm.environment.browserDetails.name` |
| オペレーティングシステム | **[!UICONTROL オペレーティングシステム]** | `xdm.environment.operatingSystem` |
| 画面解像度 | **[!UICONTROL 画面の解像度]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| デバイスカテゴリ（モバイル、デスクトップ、タブレット） | **[!UICONTROL モバイルデバイスタイプ]** | `xdm.device.type` |
| デバイスモデル | **[!UICONTROL モバイルデバイス]** | `xdm.device.model` |

これらのディメンションのいずれかをコンポーネントパネルから[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)にドラッグします。

>[!NOTE]
>
>最新のブラウザーでは、User-Agent文字列の詳細が減少しているため、完全で正確な値は、Web SDK設定で[User-Agent Client Hints](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints)を収集することによります。

+++

## 探索

+++フリーフォーム探索

GA4のフリーフォーム探索は、設定可能な行、列、オプションのチャートオーバーレイを備えた空白のキャンバステーブルです。

Analysis Workspaceの[**[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)は、ほとんどのWorkspace プロジェクトに直接対応し、基盤となります。 任意のディメンションを行に、任意の指標を列に、任意のセグメントをテーブルの上のセグメントドロップゾーンにドラッグします。

GA4 ExploreとWorkspaceの用語マッピングについては、[Analysis Workspaceの概要](home.md#getting-started-in-analysis-workspace)を参照してください。

+++

+++Funnel探索

GA4のFunnel探索では、一連のステップを定義し、各ステップの完了と離脱を測定します。

Analysis Workspaceで、[**[!UICONTROL &#x200B; フォールアウト &#x200B;]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) ビジュアライゼーションを使用します。

1. ビジュアライゼーションアイコンを選択し、**[!UICONTROL フォールアウト]** ビジュアライゼーションをキャンバスにドラッグします。
2. 最初のステップを表すディメンション、指標、またはセグメントを、最初の&#x200B;**[!UICONTROL タッチポイントを追加]** スロットにドラッグします。
3. シーケンス内の後続の各ステップに対して、引き続きタッチポイントを追加します。

あらゆるディメンション、指標、セグメントがタッチポイントとして機能するため、[!UICONTROL &#x200B; フォールアウト &#x200B;]はGA4のイベントベースのファネルに一致し、イベント、ページ、セグメントを組み合わせたクロスチャネルシーケンスに拡張されます。

+++

+++パス探索

GA4のパス探索（ユニバーサル分析では、このユーザーフローと呼ばれます）は、利用者が移動するページやイベントのシーケンスを視覚化します。

Analysis Workspaceで、[**[!UICONTROL Flow]**](/help/analysis-workspace/visualizations/c-flow/flow.md) ビジュアライゼーションを使用します。

1. ビジュアライゼーションアイコンを選択し、**[!UICONTROL フロー]** ビジュアライゼーションをキャンバスにドラッグします。
2. パスするディメンションから値（例：**[!UICONTROL Page]**&#x200B;または&#x200B;**[!UICONTROL Event type]**&#x200B;の値）をフローの中心にドラッグします。
3. ビジュアライゼーションには、ユーザーがそのポイントの前後に何をしたかが示されます。

[!UICONTROL &#x200B; フロー]のビジュアライゼーションはインタラクティブです。任意のノードを選択して、パスをいずれかの方向にさらに展開します。 あらゆるディメンションを利用できるため、ページ、イベント、マーケティングチャネル、カスタムリンクをパスできます。

+++

+++セグメントの重複

GA4のセグメント重複の分析では、複数のユーザーセグメントがどのように交差しているかを示し、ベン図として視覚化されています。

Analysis Workspaceで、[**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md) ビジュアライゼーションを使用します。

1. ビジュアライゼーションアイコンを選択し、**[!UICONTROL ベン]** ビジュアライゼーションをキャンバスにドラッグします。
2. コンポーネントパネルから最大3つのセグメントをビジュアライゼーションにドラッグします。

ベン図には積集合サイズが表示され、その下の[[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)には基礎データが表示されます。

+++

+++コホート探索

GA4のコホート探索では、共通の特徴（通常は獲得日）によって利用者をグループ化し、経時的な行動を追跡します。

Analysis Workspaceで、[**[!UICONTROL &#x200B; コホートテーブル &#x200B;]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) ビジュアライゼーションを使用します。

1. ビジュアライゼーションアイコンを選択し、**[!UICONTROL コホートテーブル]**&#x200B;をキャンバスにドラッグします。
2. **[!UICONTROL 人物]**&#x200B;指標を「包含」フィールドと「返品条件」フィールドの両方にドラッグします。
3. 「**[!UICONTROL 作成]**」を選択します。

[!UICONTROL &#x200B; コホートテーブル &#x200B;]は、最初の期間でユーザーをグループ化し、その後の期間にわたって行動を追跡します。 デフォルトでは、取得日にコホートされますが、含める条件、返す条件、粒度の条件はすべて設定可能です。

+++

+++ユーザーエクスプローラー

GA4のユーザーエクスプローラーには、個々のユーザー、セッション履歴、イベントのタイムラインが表示されます。

Customer Journey Analyticsは、次の2つの方法で個人レベルの分析をサポートしています。

* **ステッチが有効になっている**：特定の人物ID値に対するセグメントスコープを作成し、任意のWorkspace プロジェクトに適用します。 **[!UICONTROL Person]** コンテナは、個人のステッチされたアクティビティをセッションおよびチャネル間で分離します。
* **生のイベントデータ**: Adobe Experience Platform UIの&#x200B;**データセットのプレビュー**&#x200B;を使用して、生のXDM イベントレコードを調べます。 このビューは、個々のイベントの実装検証とデバッグに役立ちます。

+++

+++ユーザーのライフタイム

GA4のユーザー生涯調査は、固定された日付範囲内ではなく、ビジネスとの関係全体にわたって各ユーザーの累積価値とエンゲージメントを測定します。 過去の顧客生涯価値の指標と、Googleのマシンラーニング予測を組み合わせることで、購入の可能性、解約の可能性、売上予測を高めることができます。

これらのマップは、次の2つの部分でCustomer Journey Analyticsにマッピングされます。

**過去のライフタイム値**&#x200B;はネイティブで達成可能です。 Adobe Customer Journey Analyticsでは、データの保持ウィンドウ全体でレポートを作成するため、長い日付範囲を設定し、そのルックバック全体にわたって各個人が累積した売上とエンゲージメントを集計することができます。 ステッチまたは永続的な人物IDを使用すると、**[!UICONTROL 人物]** コンテナはそのアクティビティを1人の個人に関連付け、計算指標は1人あたりの値を表します。 結果は無制限のライフタイムではなく、1に近い長い設定可能なルックバックです。

**予測生涯値**&#x200B;は組み込まれていません。 Customer Journey Analyticsには、製品内の購入確率、解約、予測収益モデルはありません。 予測スコアを使用するには、それをCRMやデータサイエンスのワークフローなどの外部で計算し、Customer Journey Analyticsにプロファイルデータセットとして取り込んで、ディメンションや指標として表示します。 Adobeでは、実装コンサルタントと協力して、このアプローチを設計することをお勧めします。

+++

## 一般的な指標

+++アクティブなユーザー→人物

GA4の&#x200B;**アクティブユーザー**&#x200B;は、日付範囲内に少なくとも1つのエンゲージメントセッションがあったユーザーをカウントします。

Customer Journey Analyticsでは、最も近い同等の値は&#x200B;**[!UICONTROL People]**&#x200B;です。これは、日付範囲内の一意の人物IDの数です。 [!UICONTROL &#x200B; ユーザー]には、エンゲージメントレベルに関係なく、すべての識別されたユーザーが含まれるため、通常、パッシブトラフィックが大きいサイトの場合は、GA4のアクティブユーザーよりも高くなります。

より詳細な行動比較を行うには、[&#x200B; エンゲージメントセッションセグメント &#x200B;](compare-data.md#engaged-sessions)を適用して、[!UICONTROL 人物]指標を、エンゲージメント基準を満たすユーザーにスコープします。

+++

+++エンゲージメントセッション→計算指標

GA4の&#x200B;**エンゲージメントセッション**&#x200B;では、10秒以上続いたセッション、2つ以上のページビューを持つセッション、または少なくとも1つの重要なイベントを含むセッションをカウントします。

Customer Journey Analyticsにはエンゲージメントセッション指標が組み込まれていません。エンゲージメント基準をキャプチャするセグメントとして定義し、**[!UICONTROL セッション]**&#x200B;指標と一緒に使用します。 推奨されるアプローチとそのエンゲージメント率を導き出す方法については、[&#x200B; エンゲージメントセッション &#x200B;](compare-data.md#engaged-sessions)を参照してください。

+++

+++エンゲージメント率→計算指標

GA4の&#x200B;**エンゲージメント率**&#x200B;は、エンゲージメントしたセッションの割合です。エンゲージメントしたセッションを合計セッションで割ったものです。

Customer Journey Analyticsでは、エンゲージメントセッションの定義から計算指標として構築します。 ステップバイステップの手順については、[&#x200B; エンゲージメントセッション &#x200B;](compare-data.md#engagement-rate)を参照してください。

+++

+++セッションあたりの平均エンゲージメント時間→滞在時間

GA4の&#x200B;**平均エンゲージメント時間**&#x200B;は、エンゲージメントセッション中にブラウザーまたはアプリがフォアグラウンドにあった平均時間を測定します。

Customer Journey Analyticsでは、**[!UICONTROL セッション時間（秒）]**&#x200B;を使用します。これは、セッションの最初のイベントから最後のイベントまでの経過時間を測定します。 このコンポーネントには、ユーザーが積極的にエンゲージしていない可能性のある期間が含まれているため、値がGA4の測定と異なる場合があります。 これは最も近いビルトインの等価です。

+++

+++イベント→イベント数

GA4の&#x200B;**イベント数**&#x200B;は、任意のイベントが記録された合計回数です。

Customer Journey Analyticsでは、同等の指標は&#x200B;**[!UICONTROL イベント]**&#x200B;です。選択した日付範囲と適用されたセグメントのデータセット内のイベントレコードの合計数です。

+++

+++Sessions → Sessions

GA4の&#x200B;**セッション**&#x200B;とCustomer Journey Analyticsの&#x200B;**[!UICONTROL セッション]**&#x200B;はどちらも、日付範囲のセッション数を測定します。 セッション定義ルールが異なるため、カウントが異なる場合があります。 詳しくは、[GA4とCustomer Journey Analyticsのデータが異なる理由](compare-data.md#sessions)を参照してください。

+++

+++新規ユーザー→最初のセッションセグメントを人物に適用

GA4の&#x200B;**新規ユーザー**&#x200B;は、選択した日付範囲で初めてのセッションを行ったユーザーをカウントします。

Analysis Workspaceで：

1. コンポーネントパネルで&#x200B;**[!UICONTROL First Session]** セグメントを探します。
2. [[!UICONTROL &#x200B; フリーフォームテーブル &#x200B;]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)の上にあるセグメントドロップゾーンにドラッグします。
3. **[!UICONTROL 人物]**&#x200B;指標を使用して、一意の新規ユーザーをカウントします。

+++

+++直帰率→直帰率（注意事項あり）

GA4の&#x200B;**バウンス率**&#x200B;は、エンゲージしなかったセッションの割合です（10秒未満、主要イベントなし、2 ページビュー未満）。 これはエンゲージメント率の逆です。

Customer Journey Analyticsの&#x200B;**[!UICONTROL バウンス率]**&#x200B;指標は、デフォルトで異なる定義を使用し、データビューごとに設定可能です。 こうした違いにより、異なる行動を測定する数値が大きく異なります。

Customer Journey AnalyticsでGA4のバウンス率を近似するには、「エンゲージメント率」指標を構築し、`1 - Engagement Rate`として定義された2番目の計算指標で反転させます。 ステップバイステップのビルドについては、[&#x200B; エンゲージメントセッション &#x200B;](compare-data.md#engagement-rate)を参照してください。

決定的な違いについて詳しくは、[GA4とCustomer Journey Analyticsのデータが異なる理由](compare-data.md#bounce-rate)を参照してください。

+++

+++主要イベント → カスタムイベント指標

GA4の&#x200B;**キーイベント** （旧称コンバージョン）は、GA4 プロパティ設定で重要なビジネス成果として指定されたイベントです。

Customer Journey Analyticsでは、コンバージョンとは、データビューで設定されたカスタムイベント指標です。 任意のXDM イベントを指標として公開でき、指標をXDM フィールド値に条件付きで増分するように設定できます。例えば、`xdm.eventType`が`commerce.purchases`に等しい場合に増分する&#x200B;**[!UICONTROL 購入数]**&#x200B;指標を設定できます。 Analysis Workspaceのコンポーネントパネルで、関連する指標のラベルを探します。この名前は、管理者が設定した方法を反映しています。

GA4の主要イベント *レポート* （すべてのコンバージョンとそのカウントのリスト）を再現するには、このページの[&#x200B; エンゲージメント &#x200B;](#engagement)の&#x200B;**主要イベント（コンバージョン）** エントリを参照してください。

+++

>[!MORELIKETHIS]
>
>* [Google Analytics データに関するレポート &#x200B;](/help/use-cases/third-party/ga/report.md)
