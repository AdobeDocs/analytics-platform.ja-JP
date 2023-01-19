---
title: コールセンターデータと web データの読み込み
description: コールセンターと web サイトのデータをリンクさせるデータセットの作成方法について説明します。
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 100%

---

# コールセンターデータと web データの読み込み

Customer Journey Analytics には、様々なソースのデータセットを 1 つのワークスペースプロジェクトに組み合わせるための、重要で堅牢な機能が用意されています。このガイドでは、貴社が Web サイトのデータをコールセンターのデータと組み合わせる方法を説明します。例えば、顧客がどのようなアクションを実行し、どのようなコンテンツを表示し、カスタマーサポートに連絡する前に検索する用語を理解できます。 その後、改善するコンテンツやセルフサービスツールを決定し、問い合わせなくても問題をより適切に解決できます。

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

データを Adobe Experience Platform に読み込みます。Adobe Experience Platform のドキュメントの[スキーマの作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja)と[データの取り込み](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja)に関するページを参照してください。

プラットフォームにデータを読み込む際に、次のヒントに従うことで、結果のレポートについてより深く理解することができます。

* コールセンターと web データのリンクに使用する識別情報が同じ形式になっていることを確認します。
* 各データセットにデータソースを含めます。例えば、各スキーマに `data_source` 列を含め、各イベントの値をそれぞれ `"Web"` または `"Call center"` に設定します。<!--mapper-->

## ユーザー ID のステッチ

CJA では、[結合データセット](/help/connections/combined-dataset.md)を生成する際に、共通の識別情報が必要です。

* データセットに、両方のデータセットの全イベントに共通の識別情報が既に存在する場合は、この手順をスキップして接続の作成に進むことができます。
* いずれかのデータセットに、一部のイベントにのみ共通する識別情報がある場合は、クロスチャネル分析を使用してデータを結合できます。これらの 2 つのデータセットに対してクロスチャネル分析を有効にする手順については、「[クロスチャネル分析の概要](/help/cca/overview.md)」を参照してください。

## Customer Journey Analytics（CJA）での接続の作成

CJA で[接続を作成](/help/connections/create-connection.md)します。

* クロスチャネル分析を使用している場合、新しいステッチ済みデータセットを利用できます。新しく作成したステッチ済み ID フィールドをユーザー ID として使用します。
* それ以外の場合は、元の web データセットとコールセンターデータセットの両方を選択して、接続に使用できます。

## データレイヤーの作成

接続の作成後、Analysis Workspace で使用する [データビューを作成](/help/data-views/create-dataview.md) できます。役立つコンポーネントは次のとおりです。

* ラストタッチとセッションの永続性を持つページディメンション。コールセンター指標を、顧客が問い合わせ前に表示した最後のページと結び付けることができます。
* 「コールセンターの理由」スキーマフィールドを使用して発生件数を増やす問い合わせ指標。 [指標の重複排除](/help/data-views/component-settings/metric-deduplication.md) を使用して、1 回のセッションで 1 回だけ増加させます。

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
1. 指標を、測定するコールセンター指標に置き換えます。
1. 指標のヘッダーの近くにある歯車のアイコンをクリックします。「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」をクリックします。
1. 目的の [アトリビューションモデル](/help/analysis-workspace/attribution/models.md) を設定します。例えば、半減期が 15 分のタイムディケイモデルと、セッションのルックバックウィンドウがあります。このアトリビューションモデルは、コールセンターへの問い合わせにつながるページにクレジットを付与します。

結果のレポートには、コールセンターへの問い合わせに最も貢献したページが表示されます。<!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

「問い合わせ」を理由またはカテゴリ別に分割することで、このテーブルからさらに多くのインサイトを得ることができます。

1. コンポーネントのリストで、「問い合わせ理由」ディメンションの下にある右の山括弧をクリックします。この操作により、個々のディメンション値が表示されます。
2. 「問い合わせ」指標の下に目的のディメンション値をドラッグします。この指標は、問い合わせの理由ごとにその指標をフィルタリングします。
3. ドリルダウンする各問い合わせ理由に対して同じ手順を繰り返します。「すべてのセッション」フィルターを使用して、総計を表示します。

<!-- screenshot -->

### フロービジュアライゼーション

顧客がコールセンターチャネルを使用する前に試みていた行動を把握できます。このフロービジュアライゼーションは、顧客がコールセンターに到達する際に最も頻繁にたどっていたジャーニーを理解するのに役立ちます。このインサイトを活用することで、顧客からの問い合わせ件数を減らすために実行できる、サイトへの最も効果的な改善点を特定できます。

1. 左側の「**[!UICONTROL ビジュアライゼーション]**」タブをクリックし、フロービジュアライゼーションをワークスペースキャンバスにドラッグします。
2. 左側の「**[!UICONTROL コンポーネント]**」タブをクリックし、「問い合わせ理由」ディメンションを見つけます。
3. このディメンションの横にある右の山括弧をクリックします。この操作により、個々のディメンション値が表示されます。
4. 目的の問い合わせ理由ディメンション項目を、フロービジュアライゼーションの中央の場所にドラッグします。
5. フロービジュアライゼーションでは、前回と次回の問い合わせ理由が自動的に入力されます。前回の問い合わせ理由を web サイトページディメンションに置き換えます。
6. フロービジュアライゼーションの右上にある歯車アイコンをクリックし、フローコンテナを「**[!UICONTROL セッション]**」に変更します。

### ヒストグラム

問い合わせを 1 回、2 回、または 6 回以上おこなった顧客の数。こうした人の中には、web サイトを訪れたことのない人もいます。ヒストグラムビジュアライゼーションを使用して、各グループに含まれる人数を特定します。Web サイトを訪れたことのない人々に対してセルフサービスを促す方法を見てみましょう。

1. 左側の「**[!UICONTROL ビジュアライゼーション]**」タブをクリックし、ヒストグラムビジュアライゼーションをワークスペースキャンバスにドラッグします。
2. 左側の「**[!UICONTROL コンポーネント]**」タブをクリックし、問い合わせ指標をヒストグラムビジュアライゼーションにドラッグします。
3. ビジュアライゼーションの中央にある「**[!UICONTROL 詳細設定を表示]**」をクリックし、目的のグループをカスタマイズします。
4. 「**[!UICONTROL 作成]**」をクリックします。

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
