---
title: コールセンターとWebデータのインポート
description: コールセンターとWebサイトのデータをリンクするデータセットを作成する方法について説明します。
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 3%

---


# コールセンターとWebデータのインポート

Customer Journey Analyticsは、様々なソースのデータセットを1つのWorkspaceプロジェクトに組み合わせるための、価値のある堅牢な機能を提供します。 このガイドでは、貴社がWebサイトのデータをコールセンターのデータと組み合わせる方法を説明します。

## 前提条件

* この2つのデータセットを組み合わせる上で最も重要な要素は、各データソース間の共通識別子です。 例としては、顧客ID、ハッシュ化された電子メール、ログインユーザー名、電話番号などがあります。
* Adobe Experience PlatformとCustomer Journey Analyticsの両方へのアクセス
* データセットにインタラクティブな音声応答システムのログが含まれる場合、Adobeでは、データをPlatformにインポートする前に、プロンプトな対話操作のみを含めてデータを処理することを推奨します。
* データセットに呼び出しログが含まれる場合、Adobeでは次の列を含めることを推奨します。
   * 呼び出しが開始された日時
   * 呼び出し理由
   * コールセンターID
   * コールセンターエージェントID
   * 呼び出しの時間
   * 通話の結果
   * 呼び出しのコスト（可能な場合）
   * 組織が含めたい追加の呼び出しメタデータ

## Webおよびコールセンターのデータをプラットフォームにインポート

データをAdobe Experience Platformにインポートします。 Adobe Experience Platformのドキュメントの[スキーマ](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/tutorials/create-schema-ui.html)と[取り込むデータ](https://docs.adobe.com/content/help/ja-JP/experience-platform/ingestion/home.html)を参照してください。

プラットフォームにデータを読み込む場合、次のヒントに従うと、結果のレポートのインサイトを向上できます。

* コールセンターとWebデータをリンクするために使用する識別子が、同じ形式になっていることを確認します。
* 各データセットにデータソースを含めます。 例えば、各スキーマに`data_source`列を含め、各イベントの値をそれぞれ`"Web"`または`"Call center"`に設定します。<!--mapper-->

## 個人IDを一緒にステッチする

CJAでは、[組み合わされたデータセット](../connections/combined-dataset.md)を生成する際に、共通の識別子が必要です。

* データセットに、両方のデータセットのすべてのイベントに共通の識別子が既に存在する場合は、この手順をスキップして接続の作成に進むことができます。
* 一部のイベントにのみ共通のIDが設定されているデータセットがある場合は、クロスチャネル分析を使用してデータを結合できます。 これらの2つのデータセットに対してCCAを有効にする手順については、[チャネル間分析の概要](/help/connections/cca/overview.md)を参照してください。

## CJAでの接続の作成

[CJAでの](/help/connections/create-connection.md) 接続の作成を参照してください。

* CCAを使用する場合は、新しいステッチデータセットを利用できます。 新しく作成したステッチIDフィールドを個人IDとして使用します。
* それ以外の場合は、元のWebデータセットとコールセンターデータセットの両方を選択して、接続に使用できます。

## データレイヤーの作成

接続を作成した後、Analysis Workspaceで使用するデータ表示[を作成できます。<!-- page dimension last touch, session persistence -->](/help/data-views/create-dataview.md)
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## ビジュアライゼーションの作成

次のビジュアライゼーションを使用して、ステッチデータセットからインサイトを取得できます。

### データセットの重複

このビジュアライゼーションは、CCAがデータをどの程度まとめるかを理解するのに役立ちます。

1. 2つのフィルターを作成します。 これらの2つのフィルターで使用される変数は、上述の変数と同じで、各イベントのデータソースを反映しています。 詳しくは、[フィルターの作成](/help/components/filters/create-filters.md)を参照してください。
   * データセットIDがWebデータと等しい個人コンテナ
   * データセットIDがコールセンターデータと等しい個人コンテナ
2. Analysis Workspaceで、[ベン](/help/analysis-workspace/visualizations/venn.md)のビジュアライゼーションをワークスペースキャンバスにドラッグします。
3. 新しく作成した2つのフィルターーを&#x200B;**[!UICONTROL 追加フィルター]**&#x200B;領域にドラッグし、人物指標を&#x200B;**[!UICONTROL 追加指標]**&#x200B;領域にドラッグします。

結果のベン図のビジュアライゼーションには、データセット内でWebデータとコールセンターデータの両方を含む人の数が表示されます。 重なりが大きいほど、ステッチに成功した人が多くなります。 重ならない領域は、1つのデータセットのみに存在する人を表します。

### コールセンターイベントをWebページに属性付け

このフリーフォームテーブルでは、コールセンターのイベントに貢献するトップページを確認できます。 最初に、目的のディメンションと指標に正しいアトリビューションモデルがあることを確認します。

1. Webページ名を保持するディメンションをフリーフォームテーブルのビジュアライゼーションにドラッグします。
1. この指標を、コンバージョンを測定する目的のコールセンター指標に置き換えます。
1. 指標ヘッダーの近くにある歯車アイコンをクリックします。 「**[!UICONTROL デフォルト以外のアトリビューションモデル]**&#x200B;を使用」をクリックします。
1. 目的の[アトリビューションモデル](/help/data-views/configure-dataviews.md#Attribution-model)を設定します。

結果のレポートには、コールセンターデータからの上位の指標が表示されます。<!-- Complement with donut visualization -->

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

use sequential segmentation, but you lose the ability to use attribution IQ

## What to do when you've found insight -->

