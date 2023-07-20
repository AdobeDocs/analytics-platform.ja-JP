---
title: Cross-Channel Analytics に関する FAQ
description: Cross-Channel Analytics に関するよくある質問（FAQ）
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
hide: true
hidefromtoc: true
source-git-commit: c87aaefdd15e02b7fe2cf8e638830aa278d46b92
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 66%

---

# よくある質問

## クロスチャネル分析を使用して、ユーザーがチャネル間をどのように移動しているかを確認する方法を教えてください。

フロービジュアライゼーションを、データセット ID ディメンションと合わせて使用できます。

1. [analytics.adobe.com](https://analytics.adobe.com) にログインし、空のワークスペースプロジェクトを作成します。
2. 左側の「ビジュアライゼーション」タブをクリックし、フロービジュアライゼーションを右側のキャンバスにドラッグします。
3. 左側の「コンポーネント」タブをクリックし、「データセット ID」ディメンションを、中央にある、「ディメンションまたは項目」というラベルが付いた場所にドラッグします。
4. このフローレポートはインタラクティブです。いずれかの値をクリックして、フローを展開し、後のページまたは前のページを開きます。右クリックメニューを使用して、列を展開または折りたたむことができます。同じフローレポート内で異なるディメンションを使用することもできます。

データセット ID ディメンションの項目の名前を変更する場合は、検索データセットを使用できます。

## クロスチャネル分析では、ユーザーのキーをどのくらい遡って更新しますか？

キー更新のルックバックウィンドウは、データ[再生](replay.md)の頻度に応じて異なります。例えば、データを毎週 1 回再生するようにクロスチャネル分析を設定した場合、キー更新のルックバックウィンドウは 7 日になります。データを毎日再生するようにクロスチャネル分析を設定した場合、キー更新のルックバックウィンドウは 1 日です。

## 共有デバイスはどのように処理されますか？

状況によっては、同じデバイスから複数のユーザーがログインすることがあります。例としては、自宅の共有デバイス、図書館の共有 PC、小売アウトレットのキオスクなどがあります。

一時的な ID は永続 ID よりも優先されるので、共有デバイスは（同じデバイスから操作している場合でも）別のユーザーと見なされます。

## 1 人のユーザーが多数の永続 ID を持っている場合、クロスチャネル分析ではどのように処理されますか？

状況によっては、1 人のユーザーを多数の永続 ID に関連付けることができます。例えば、ブラウザーの Cookie を頻繁にクリアするユーザーや、ブラウザーのプライベート / 匿名モードを使用するユーザーなどです。

永続 ID の数は、一時的な ID には関係ありません。1 人のユーザーが任意の数のデバイスに属する場合でも、デバイス間でのクロスチャネル分析のステッチ機能に影響を与えることはありません。

## 必要な情報をAdobeアカウントチームに連絡した後、キーが更新されたデータセットが利用可能になるまでにどれくらいかかりますか？

ライブステッチは、アドビが Cross-Channel Analytics を有効にしてから約 1 週間後に使用可能になります。バックフィルの可用性は、既存のデータの量に応じて異なります。小規模なデータセット（1 日あたり 100 万イベント未満）の処理には通常 2 ～ 3 日かかりますが、大規模なデータセット（1 日あたり 10 億イベント）には 1 週間以上かかる場合があります。

## クロスデバイス分析 (Adobe Analyticsの機能 ) とクロスチャネル分析の違いは何ですか。

[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja)は、人がどのようにデバイスをまたいで操作するかを把握できる、従来の Adobe Analytics 専用の機能です。デバイスデータを互いにリンクするために、フィールドベースのステッチとデバイスグラフの 2 つのワークフローを提供します。

[クロスチャネル分析](/help/cca/overview.md) は、デバイスに固有の機能で、Customer Journey Analyticsとチャネルの両方をまたいでユーザーがどのように動作するかを理解できます。 データセットの人物 ID を再入力することで、そのデータセットを他のデータセットとシームレスに組み合わせることができます。この機能は、CDA のフィールドベースのステッチと同様に設計で動作しますが、Adobe AnalyticsとCustomer Journey Analyticsではデータアーキテクチャが異なるので、実装は異なります。

## Cross-Channel Analytics では、GDPR および CCPA のリクエストはどのように処理されますか？

アドビでは、現地の法律および国際法に従って、GDPR と CCPA のリクエストが処理されます。アドビは、データアクセスリクエストとデータ削除リクエストを送信するための [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja) を提供しています。リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

## 1 つ以上のイベントの「永続 ID」フィールドが空白の場合はどうなりますか？

フィールドベースのステッチでステッチされているデータセット内のイベントで `Persistent ID` フィールドが空白の場合、クロスチャネル分析は次の 2 つの方法のいずれかでそのイベントの `Stitched ID` を入力します。

* `Transient ID` フィールドが空白でない場合、クロスチャネル分析では `Transient ID` の値が `Stitched ID` として使用されます。
* `Transient ID` フィールドが空白の場合、クロスチャネル分析では `Stitched ID` も空白のままになります。この場合、`Persistent ID`、`Transient ID` および `Stitched ID` は、イベントですべて空白になります。このようなイベントは、ステッチされるCustomer Journey Analyticsセットを使用するあらゆるイベント接続から削除され、 `Stitched ID` が次のように選択されました： `Person ID`.

## Customer Journey Analytics関連付けデータセットの指標は、Customer Journey Analytics未関連付けデータセットの類似の指標と、従来のAdobe Analyticsとどのように比較されますか。

Customer Journey Analyticsの特定の指標はAdobe Analyticsの指標に似ていますが、比較する指標によって異なります。 下の表では、一般的な指標をいくつか比較しています。

| **Customer Journey Analytics結合データ** | **Customer Journey Analytics未関連付けデータ** | **従来の Adobe Analytics** | **CDA を使用した Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **People** = `Stitched ID` が `Person ID` として選択された場合の個別の `Person ID`の数。**人物**&#x200B;は、ステッチプロセスの結果に応じて、従来の **Adobe Analytics** のユニーク訪問者よりも多くなったり少なくなったりする場合があります。 | **People** = `Person ID` として選択された列に基づく個別の `Person ID` の数。**人** Analytics ソースコネクタのデータセットは、 **実訪問者数** 従来のAdobe Analyticsで `endUserIDs._experience.aaid.id` 次の項目が選択されています： `Person ID` Customer Journey Analytics | **実訪問者数** =ユニークユーザー ID の数。 **ユニーク訪問者**&#x200B;は、個別の **ECID** の数と同じにならない場合があります。 | [人物](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=ja)を参照してください。 |
| **セッション**:セッションデータビューのセッション設定に基づいてCustomer Journey Analyticsされます。 ステッチ処理では、複数のデバイスからの個々のセッションを 1 つのセッションにまとめることができます。 | **セッション**:セッションのデータビューで指定されたCustomer Journey Analytics設定に基づいて定義されます。 | **訪問数**：[訪問数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ja)を参照してください。 | **訪問**：[CDA 仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=ja)で指定されたセッション設定に基づいて定義されます。 |
| **イベント** =Customer Journey Analyticsのステッチ済みデータの行数。 この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、空白の `Persistent ID` がある行については、上記の FAQ に注意してください。 | **イベント** =Customer Journey Analyticsの未関連付けデータの行数。 この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、いずれかのイベントの `Person ID` Experience Platformデータレイクの未関連付けデータでは、これらのイベントはCustomer Journey Analyticsに含まれません。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)を参照してください。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)を参照してください。 |

その他の指標は、Customer Journey Analyticsや従来のAdobe Analyticsで似ています。 例えば、Adobe Analyticsの合計数 [カスタムイベント](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=ja) 1 ～ 100 は、通常、従来のAdobe AnalyticsとCustomer Journey Analytics（ステッチされているか未ステッチかに関わらず）の間で同等です。 [機能の違い](/help/getting-started/aa-vs-cja/cja-aa.md)) 例えば、Customer Journey Analyticsと従来のAdobe Analyticsの間のイベント重複除外は、2 つの製品間で矛盾を引き起こす可能性があります。

## CCA では「ID マップ」フィールドを使用できますか？

いいえ。CCA は、現在、「ID マップ」フィールドを使用できません。
