---
title: クロスチャネル分析に関する FAQ
description: クロスチャネル分析に関するよくある質問（FAQ）
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
source-git-commit: 2be442915587780ce41f33b13e27b8cf44e239a6
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 46%

---

# よくある質問

## クロスチャネル分析を使用して、ユーザーがチャネル間をどのように移動しているかを確認する方法を教えてください。

フロービジュアライゼーションを、データセット ID ディメンションと合わせて使用できます。

1. [analytics.adobe.com](https://analytics.adobe.com)にログインし、空のWorkspaceプロジェクトを作成します。
2. 左側の「ビジュアライゼーション」タブをクリックし、フロービジュアライゼーションを右側のキャンバスにドラッグします。
3. 左側の「コンポーネント」タブをクリックし、「データセット ID」ディメンションを、中央にある、「ディメンションまたは項目」というラベルが付いた場所にドラッグします。
4. このフローレポートはインタラクティブです。いずれかの値をクリックして、フローを展開し、後のページまたは前のページを開きます。右クリックメニューを使用して、列を展開または折りたたむことができます。同じフローレポート内で異なるディメンションを使用することもできます。

データセット ID ディメンションの項目の名前を変更する場合は、検索データセットを使用できます。

## クロスチャネル分析では訪問者のキーをどのくらい遡って更新しますか？

キー更新のルックバックウィンドウは、データ[再生](replay.md)の頻度に応じて異なります。例えば、データを毎週 1 回再生するようにクロスチャネル分析を設定した場合、キー更新のルックバックウィンドウは 7 日になります。データを毎日再生するようにクロスチャネル分析を設定した場合、キー更新のルックバックウィンドウは 1 日です。

## 共有デバイスはどのように処理されますか？

状況によっては、同じデバイスから複数のユーザーがログインすることがあります。例としては、自宅の共有デバイス、図書館の共有 PC、または小売アウトレットのキオスクなどがあります。

一時的な ID は永続 ID よりも優先されるので、共有デバイスは（同じデバイスから操作している場合でも）別のユーザーと見なされます。

## 1 人のユーザーが多数の永続 ID を持っている場合、クロスチャネル分析ではどのように処理されますか？

状況によっては、1 人のユーザーを多数の永続 ID に関連付けることができます。例えば、ブラウザーの Cookie を頻繁にクリアするユーザーや、ブラウザーのプライベート / 匿名モードを使用するユーザーなどです。

永続 ID の数は、一時的な ID には関係ありません。1 人のユーザーが任意の数のデバイスに属する場合でも、デバイス間でのクロスチャネル分析のステッチ機能に影響を与えることはありません。

## 必要な情報をアカウントマネージャーに連絡した後、キー更新されたデータセットを利用可能になるまでにどのくらいかかりますか？

ライブステッチは、アドビがクロスチャネル分析を有効にしてから約 1 週間後に使用可能になります。バックフィルの可用性は、既存のデータの量に応じて異なります。小規模なデータセット（1 日 あたり 100 万イベント未満）の処理には通常 2 ～ 3 日かかりますが、大規模なデータセット（1 日あたり 10 億イベント）では 1 週間以上かかる場合があります。

## クロスチャネル分析では、GDPR および CCPA のリクエストはどのように処理されますか？

アドビでは、現地の法律および国際法に従って、GDPR と CCPA のリクエストが処理されます。アドビは、データアクセスリクエストとデータ削除リクエストを送信するための [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja-JP) を提供しています。リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

## 1つ以上のイベントの「永続ID 」フィールドが空白の場合はどうなりますか。

フィールドベースのステッチでステッチされるデータセットのイベントで`Persistent ID`フィールドが空白の場合、クロスチャネル分析は次の2つの方法のいずれかでそのイベントの`Stitched ID`を入力します。
* `Transient ID`フィールドが空白でない場合、クロスチャネル分析では`Transient ID`の値が`Stitched ID`として使用されます。
* `Transient ID`フィールドが空白の場合、クロスチャネル分析では`Stitched ID`も空白のままになります。 この場合、 `Persistent ID`、 `Transient ID`および`Stitched ID`は、すべてイベントで空白になります。 `Stitched ID`が`Person ID`として選択されたステッチ対象のデータセットを使用して、このようなイベントは、CJA接続のCJAから削除されます。

## CJAステッチデータセットの指標は、CJA未ステッチデータセットの類似の指標と、従来のAdobe Analyticsとどのように比較しますか。

CJAの特定の指標は、従来のAnalyticsの指標に似ていますが、比較の内容に応じて、それ以外の指標はかなり異なります。 次の表では、一般的な指標をいくつか比較しています。

| **CJAステッチデータ** | **CJA未関連付けデータ** | **トラディショナルAdobe Analytics** | **CDAを使用したAnalytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **People**  =として選択さ `Person ID`れたユニ `Stitched ID` ークの数 `Person ID`。**** ステッチプロセスの結果に応じて、従来の **Adobe Analytics** の個別訪問者数よりも高いか低い訪問者数になります。 | **People**  =として選択された列 `Person ID`に基づくユニークの数 `Person ID`。**** Adobe Analyticsコネクタ(ADC)データセットのユーザーは、CJAで **が選択され** ている場合、従来のAdobe Analyticsの実訪問 `endUserIDs. _experience. aaid.id`  `Person ID` 者に似ています。 | **Unique Visitors**  =ユニーク訪問者IDの数。**個別訪問者数**&#x200B;は、個別の&#x200B;**ECID**&#x200B;の数と同じでない場合があります。 | [People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)を参照してください。 |
| **セッション**:CJAデータビューで指定されたセッション設定に基づいて定義されます。ステッチ処理は、複数のデバイスからの個々のセッションを1つのセッションに組み合わせることができます。 | **セッション**:CJAデータビューで指定されたセッション設定に基づいて定義されます。 | **訪問**&#x200B;数：訪問を参 [照してください](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)。 | **訪問**&#x200B;数：CDA仮想レポートスイートで指定されたセッション化設 [定に基づいて定義されます](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=en)。 |
| **Events**  = CJAでのステッチデータの行の数。一般に、これは、従来のAdobe Analyticsでは&#x200B;**回数**&#x200B;に近い値になります。 ただし、上記のFAQでは、行が空白の`Persistent ID`になっています。 | **Events**  = CJAで未関連付けデータの行の数。一般に、これは、従来のAdobe Analyticsでは&#x200B;**回数**&#x200B;に近い値になります。 ただし、AEPデータレイクの未関連付けデータに空白の`Person ID`が含まれるイベントがある場合は、これらのイベントはCJAにドロップされます（含まれません）。 | **発生件数**:回数を参 [照してください](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 | **発生件数**:回数を参 [照してください](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 |

その他の指標は、CJAや従来のAdobe Analyticsで似ている場合があります。 例えば、Adobe Analyticsの[カスタムイベント](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en)（イベント1 ～ 100）の合計カウントは、通常、従来のAdobe AnalyticsとCJA（ステッチされたか未ステッチかに関わらず）で非常に近い値になります。 ただし、CJAと従来のAdobe Analyticsの間のイベント重複除外など、機能](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=en)の[の違いが原因で、これが常に当てはまるとは限りません。
