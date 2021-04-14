---
title: コールセンターデータと web データの読み込み
description: コールセンターと web サイトのデータをリンクさせるデータセットの作成方法について説明します。
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
translation-type: tm+mt
source-git-commit: f9fae62af3d57b2b700c26a402c7232c0255806b
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 100%

---

# コールセンターデータと web データの読み込み

Customer Journey Analytics には、様々なソースのデータセットを 1 つの Workspace プロジェクトに組み合わせるための、重要で堅牢な機能が用意されています。このガイドでは、貴社が Web サイトのデータをコールセンターのデータと組み合わせる方法を説明します。

## 前提条件

* この 2 つのデータセットを組み合わせる上で最も重要な要素は、各データソースに共通する識別情報です。例として、顧客 ID、ハッシュ化された電子メール、ログインユーザー名、電話番号などがあります。
* Adobe Experience Platform と Customer Journey Analytics の両方にアクセス可能であること。
* データセットにインタラクティブな音声応答システムのログが含まれる場合、データを Platform にインポートする前に、プロンプトインタラクションのみが含まれるようにデータを処理することをお勧めします。
* データセットに通話記録が含まれる場合、次の列を含めることをお勧めします。
   * 通話の開始日時
   * 通話理由
   * コールセンター ID
   * コールセンターエージェント ID
   * 通話時間
   * 通話の結果
   * 通話コスト（可能な場合）
   * 組織が含める追加の通話メタデータ

## Platform への web データおよびコールセンターデータの読み込み

データを Adobe Experience Platform に読み込みます。Adobe Experience Platform のドキュメントの[スキーマの作成](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/tutorials/create-schema-ui.html)と[データの取り込み](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.html)に関するページを参照してください。

プラットフォームにデータを読み込む際に、次のヒントに従うことで、結果のレポートについてより深く理解することができます。

* コールセンターと web データのリンクに使用する識別情報が同じ形式になっていることを確認します。
* 各データセットにデータソースを含めます。例えば、各スキーマに `data_source` 列を含め、各イベントの値をそれぞれ `"Web"` または `"Call center"` に設定します。<!--mapper-->

## ユーザー ID のステッチ

CJA では、[結合データセット](../connections/combined-dataset.md)を生成する際に、共通の識別情報が必要です。

* データセットに、両方のデータセットの全イベントに共通の識別情報が既に存在する場合は、この手順をスキップして接続の作成に進むことができます。
* いずれかのデータセットに、一部のイベントにのみ共通する識別情報がある場合は、クロスチャネル分析を使用してデータを結合できます。これらの 2 つのデータセットに対してクロスチャネル分析を有効にする手順については、「[クロスチャネル分析の概要](/help/connections/cca/overview.md)」を参照してください。

## Customer Journey Analytics（CJA）での接続の作成

CJA で[接続を作成](/help/connections/create-connection.md)します。

* クロスチャネル分析を使用している場合、新しいステッチ済みデータセットを利用できます。新しく作成したステッチ済み ID フィールドをユーザー ID として使用します。
* それ以外の場合は、元の web データセットとコールセンターデータセットの両方を選択して、接続に使用できます。

## データレイヤーの作成

接続の作成後、Analysis Workspace で使用する[データビューを作成](/help/data-views/create-dataview.md)できます。<!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## ビジュアライゼーションの作成

次のビジュアライゼーションを使用して、結合データセットからインサイトを得ることができます。

### データセットの重複

このビジュアライゼーションは、クロスチャネル分析がデータをどの程度適切にステッチしているかを理解するのに役立ちます。

1. 2 つのフィルターを作成します。これら 2 つのフィルターで使用される変数は、各イベントのデータソースを反映する、前述の変数と同じです。詳しくは、[フィルターの作成](/help/components/filters/create-filters.md)に関するページを参照してください。
   * データセット ID と web データが同じユーザーコンテナ
   * データセット ID とコールセンターデータが同じユーザーコンテナ
2. Analysis Workspace で、[Venn](/help/analysis-workspace/visualizations/venn.md) ビジュアライゼーションをワークスペースキャンバスにドラッグします。
3. 新しく作成した 2 つのフィルターを「**[!UICONTROL フィルターを追加]**」領域にドラッグし、人物指標を「**[!UICONTROL 指標を追加]**」領域にドラッグします。

結果のベン図ビジュアライゼーションは、web データとコールセンターデータの両方を含むデータセット内の人数を示します。重複が大きいほど、より多くの人が適切にステッチされたことになります。重複しない領域は、いずれかのデータセットにのみ存在する人を表します。

### コールセンターのイベントを web ページに関連付ける

このフリーフォームテーブルでは、コールセンターのイベントに貢献しているトップページを確認できます。まず、目的のディメンションと指標に正しいアトリビューションモデルがあることを確認します。

1. web ページ名を保持しているディメンションをフリーフォームテーブルのビジュアライゼーションにドラッグします。
1. 指標を、コンバージョンを測定する目的のコールセンター指標に置き換えます。
1. 指標のヘッダーの近くにある歯車のアイコンをクリックします。「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」をクリックします。
1. 目的の[アトリビューションモデル](/help/data-views/create-dataview.md)を設定します。

結果のレポートには、コールセンターデータの上位の指標が示されます。<!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
