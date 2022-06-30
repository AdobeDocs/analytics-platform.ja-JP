---
title: Cross-Channel Analytics に関する FAQ
description: Cross-Channel Analytics に関するよくある質問（FAQ）
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 5eede8eeb5d7e8632dc0d7d580f01ccc7ac8106c
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 59%

---

# よくある質問

## クロスチャネル分析を使用して、ユーザーがチャネル間をどのように移動しているかを確認する方法を教えてください。

フロービジュアライゼーションを、データセット ID ディメンションと合わせて使用できます。

1. [analytics.adobe.com](https://analytics.adobe.com) にログインし、空のワークスペースプロジェクトを作成します。
2. 左側の「ビジュアライゼーション」タブをクリックし、フロービジュアライゼーションを右側のキャンバスにドラッグします。
3. 左側の「コンポーネント」タブをクリックし、「データセット ID」ディメンションを、中央にある「Dimensionまたは項目」というラベルの付いた場所にドラッグします。
4. このフローレポートはインタラクティブです。いずれかの値をクリックして、フローを展開し、後のページまたは前のページを開きます。右クリックメニューを使用して、列を展開または折りたたむことができます。同じフローレポート内で異なるディメンションを使用することもできます。

データセット ID ディメンションの項目の名前を変更する場合は、検索データセットを使用できます。

## クロスチャネル分析では訪問者のキーをどのくらい遡って更新しますか？

キー更新のルックバックウィンドウは、データ[再生](replay.md)の頻度に応じて異なります。例えば、データを毎週 1 回再生するようにクロスチャネル分析を設定した場合、キー更新のルックバックウィンドウは 7 日間になります。 データを毎日再生するようにクロスチャネル分析を設定した場合、キー更新のルックバックウィンドウは 1 日です。

## 共有デバイスはどのように処理されますか？

状況によっては、同じデバイスから複数のユーザーがログインする可能性があります。 例としては、自宅の共有デバイス、図書館の共有 PC、または小売アウトレットのキオスクなどがあります。

一時的な ID は永続 ID よりも優先されるので、共有デバイスは（同じデバイスから操作している場合でも）別のユーザーと見なされます。

## 1 人のユーザーが多数の永続的な ID を持っている場合、クロスチャネル分析ではどのように処理されますか。

状況によっては、1 人のユーザーを多数の永続 ID に関連付けることができます。 例えば、ブラウザーの Cookie を頻繁にクリアするユーザーや、ブラウザーのプライベート / 匿名モードを使用するユーザーなどです。

永続 ID の数は、一時的な ID には関係ありません。1 人のユーザーが任意の数のデバイスに属する場合でも、デバイス間でのクロスチャネル分析のステッチ機能に影響を与えることはありません。

## 必要な情報をアカウントマネージャーに連絡した後、キー更新されたデータセットを利用可能になるまでにどのくらいかかりますか？

ライブステッチは、Adobeがクロスチャネル分析を有効にしてから約 1 週間後に使用可能になります。 バックフィルの可用性は、既存のデータの量に応じて異なります。小規模なデータセット（1 日 あたり 100 万イベント未満）の処理には通常 2 ～ 3 日かかりますが、大規模なデータセット（1 日あたり 10 億イベント）では 1 週間以上かかる場合があります。

## クロスデバイス分析（従来の Analytics の機能）とクロスチャネル分析の違いは何ですか。

[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja) は、デバイスをまたいでのユーザーの動作を理解できる、従来のAdobe Analyticsに固有の機能です。 次の 2 つのワークフローを使用して、デバイスデータを相互にリンクできます。フィールドベースのステッチとデバイスグラフ。

[クロスチャネル分析](../overview.md) は、CJA に固有の機能で、デバイスとチャネルの両方でのユーザーの動作を理解できます。 データセットのユーザー ID のキーを変更することで、そのデータセットを他のデータセットとシームレスに組み合わせることができます。 この機能は、CDA のフィールドベースのステッチと同様に設計で動作しますが、従来の Analytics と CJA とでは、データアーキテクチャが異なるので、実装は異なります。

## Cross-Channel Analytics では、GDPR および CCPA のリクエストはどのように処理されますか？

アドビでは、現地の法律および国際法に従って、GDPR と CCPA のリクエストが処理されます。アドビは、データアクセスリクエストとデータ削除リクエストを送信するための [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja) を提供しています。リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

## 1 つ以上のイベントの「永続 ID」フィールドが空白の場合はどうなりますか？

フィールドベースのステッチでステッチされているデータセット内のイベントで `Persistent ID` フィールドが空白の場合、クロスチャネル分析は次の 2 つの方法のいずれかでそのイベントの `Stitched ID` を入力します。

* `Transient ID` フィールドが空白でない場合、クロスチャネル分析では `Transient ID` の値が `Stitched ID` として使用されます。
* `Transient ID` フィールドが空白の場合、クロスチャネル分析では `Stitched ID` も空白のままになります。この場合、 `Persistent ID`, `Transient ID`、および `Stitched ID` イベントではすべて空白です。 これらのタイプのイベントは、ステッチされるデータセットを使用する CJA 接続から削除され、 `Stitched ID` が次のように選択されました： `Person ID`.

## CJA ステッチデータセットの指標は、CJA 未ステッチデータセットの類似の指標および従来の Adobe Analytics と比較してどうでしょうか？

CJA の特定の指標は、従来の Analytics の指標に似ていますが、比較する対象によっては、それ以外の指標はまったく異なります。下の表では、一般的な指標をいくつか比較しています。

| **CJA ステッチデータ** | **CJA 未ステッチデータ** | **従来の Adobe Analytics** | **CDA を使用した Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **People** = `Stitched ID` が `Person ID` として選択された場合の個別の `Person ID`の数。**People** は、ステッチプロセスの結果に応じて、従来の **Adobe Analytics** のユニーク訪問者よりも多くなったり少なくなったりする場合があります。 | **People** = `Person ID` として選択された列に基づく個別の `Person ID` の数。**人** Adobeソースコネクタのデータセットは、 **実訪問者数** 従来のAdobe Analyticsで `endUserIDs._experience.aaid.id` 次の項目が選択されています： `Person ID` （CJA 内） | **ユニーク訪問者** = 個別の訪問者 ID の数。**実訪問者数** ユニークの数と同じでない可能性があります **ECID** s. | [People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=ja) を参照してください。 |
| **セッション**:CJA データビューのセッション設定に基づいて定義されます。 ステッチ処理では、複数のデバイスからの個々のセッションを 1 つのセッションにまとめることができます。 | **セッション**:CJA データビューで指定されたセッション設定に基づいて定義されます。 | **訪問数**：[訪問数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ja)を参照してください。 | **訪問回数**:セッション設定に基づいて定義されます。 [CDA 仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=ja). |
| **イベント数** = CJA でのステッチデータの行数。この指標は通常、 **発生件数** 従来のAdobe Analyticsの ただし、空白の `Persistent ID` がある行については、上記の FAQ に注意してください。 | **イベント数** = CJA 未ステッチデータの行数。この指標は通常、 **発生件数** 従来のAdobe Analyticsの ただし、いずれかのイベントの `Person ID` Experience Platformデータレイクの未関連付けデータでは、これらのイベントは CJA には含まれません。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)を参照してください。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html)を参照してください。 |

他の指標は、CJA や従来のAdobe Analyticsで似ています。 例えば、Adobe Analyticsの合計数 [カスタムイベント](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=ja) 1 ～ 100 は、通常、従来のAdobe Analyticsと CJA（結び付けるか未結び付けか）に匹敵します。 [機能の違い](/help/getting-started/aa-vs-cja/cja-aa.md)) 例えば、CJA と従来のAdobe Analyticsの間のイベント重複除外は、2 つの製品間で不一致を引き起こす可能性があります。

## CCA 「ID マップ」フィールドを使用できますか？

いいえ。クロスチャネル分析は、現在 ID マップフィールドを使用できません。
