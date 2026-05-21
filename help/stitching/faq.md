---
title: ステッチに関する FAQ
description: ステッチに関するよくある質問について説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
TQID: https://experienceleague.adobe.com/0y2eqwQxkHefcODFhxXCuioMnL-YCXm21335Z2upPB0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 19cf20236196ab9c2518bf299a36d32f65210227
workflow-type: tm+mt
source-wordcount: 2373
ht-degree: 71%

---

# よくある質問

ステッチに関するよくある質問を以下に示します。

## チャネル間の移動

**質問**：合成を使用して、ユーザーがあるチャネルから別のチャネルに移動する方法を確認するにはどうすればよいですか？

+++回答

フロービジュアライゼーションを、データセット ID ディメンションと合わせて使用できます。

1. [Customer Journey Analytics](https://analytics.adobe.com) にログインし、空の Workspace プロジェクトを作成します。
2. 左側の「**[!UICONTROL **&#x200B;ビジュアライゼーション&#x200B;**]**」タブを選択し、**[!UICONTROL **&#x200B;フロー&#x200B;**]**&#x200B;ビジュアライゼーションを右側のキャンバスにドラッグします。
3. 左側の「**[!UICONTROL **&#x200B;コンポーネント&#x200B;**]**」タブを選択し、**[!UICONTROL **&#x200B;データセット ID **]** ディメンションを&#x200B;**[!UICONTROL **&#x200B;ディメンションまたは項目&#x200B;**]**&#x200B;というラベルが付いた中央の場所にドラッグします。
4. このフローレポートはインタラクティブです。 後続または前のページにフローを展開するには、いずれかの値を選択します。 右クリックメニューを使用して、列を展開または折りたたむことができます。 同じフローレポート内で異なるディメンションを使用することもできます。

データセット ID ディメンションの項目の名前を変更する場合は、検索データセットを使用できます。

+++

## 再生

**質問**：合成で再生プロファイルを再生する距離を指定します。

+++回答

キー更新のルックバックウィンドウは、データ再生の頻度に応じて異なります。 例えば、データを毎週 1 回再生するようにステッチを設定した場合、キー更新のルックバックウィンドウは 7 日になります。 データを毎日再生するようにステッチを設定した場合、キー更新のルックバックウィンドウは 1 日になります。

+++

**質問**：再生プロセスが正確に実行されるのはいつですか？

+++回答

* **週次**&#x200B;のリプレイは、毎週土曜日&#x200B;**の夜（お客様のタイムゾーン）に開始され、Customer Journey Analytics レポートで月曜日の朝までにデータが更新されます。**
* **日次**&#x200B;の再生は&#x200B;**3 A.M.** （顧客のタイムゾーン）頃に実行され、Customer Journey Analytics レポートでは朝までにデータが更新されます。

>[!IMPORTANT]
>
>毎週のリプレイの日と毎日のリプレイの時間は、カスタムリクエストを通じて変更することはできません。
>

+++

## 共有デバイス

**質問**：共有デバイスはどのように処理されますか？

+++回答

状況によっては、同じデバイスから複数のユーザーがログインすることがあります。 例としては、自宅の共有デバイス、図書館の共有 PC、小売アウトレットのキオスクなどがあります。

ユーザー ID は永続 ID よりも優先されるので、共有デバイスは（同じデバイスから操作している場合でも）別のユーザーと見なされます。

詳しくは、[共有デバイス](/help/use-cases/stitching/shared-devices.md)ユースケースを参照してください。

+++

## 多数の永続 ID

**質問**：ステッチは、1人のユーザーが多数の永続的IDを持つ場合、どのように処理しますか？

+++回答

状況によっては、1 人のユーザーを多数の永続 ID に関連付けることができます。 例えば、個人がブラウザーのCookieを頻繁に消去したり、ブラウザーのプライベートモードやシークレットモードを使用したりすることです。

フィールドベースのステッチの場合、永続 ID の数は、ユーザー ID に優先されるので関係ありません。 1 人のユーザーが任意の数のデバイスに属する場合でも、デバイス間での Customer Journey Analytics のステッチ機能に影響を与えることはありません。

グラフベースの合成の場合、1人のユーザーがID グラフに多数の永続的IDを持つことができます。 グラフベースのステッチでは、指定した名前空間に基づいて永続 ID が使用されます。 同じ名前空間に対してより多くの永続的IDがある場合は、レキシグラフィックの最初の永続的IDが使用されます。

+++

## ステッチプロセス

**質問**：必要な情報をAdobe アカウントチームに問い合わせると、再入力されたデータセットが使用可能になるまでにどのくらいの時間がかかりますか？

+++回答

ライブステッチは、アドビがステッチを有効にしてから約 1 週間後に使用可能になります。 バックフィルの可用性は、既存のデータの量に応じて異なります。 小規模なデータセット（1 日あたり 100 万イベント未満）の処理には通常 2 ～ 3 日かかりますが、大規模なデータセット（1 日あたり 10 億イベント）では 1 週間以上かかる場合があります。

+++

## クロスデバイス分析とクロスチャネル分析の比較

**質問**: クロスデバイス分析（従来のAnalyticsの機能）とクロスチャネル分析の違いは何ですか？

+++回答

[クロスデバイス分析](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview)は、人物がどのようにデバイスをまたいで操作するかを把握できる、従来の Adobe Analytics 専用の機能です。 デバイスデータを互いにリンクするために、フィールドベースのステッチとデバイスグラフの 2 つのワークフローを提供します。

クロスチャネル分析は、人物がどのようにデバイスとチャネルの両方をまたいで操作するかを把握できる、Customer Journey Analytics 専用のユースケースです。 データセットのユーザー ID をステッチすることで、そのデータセットを他のデータセットとシームレスに組み合わせることができます。 この機能は、クロスデバイス分析のフィールドベースのステッチと同様の設計で動作しますが、従来の Analytics と Customer Journey Analytics ではデータアーキテクチャが異なるので、実装は異なります。 詳しくは、[ステッチ](overview.md)および[クロスチャネル分析](../use-cases/cross-channel/cross-channel.md)ユースケースを参照してください。

+++

## プライバシー

**質問**: ステッチでプライバシー要求をどのように処理しますか？

+++回答

アドビでは、現地の法律と国際法に従ってプライバシーリクエストを処理します。 アドビは、データアクセスリクエストとデータ削除リクエストを送信するための [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/home) を提供しています。 リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

>[!IMPORTANT]
>
>未ステッチプロセスは、プライバシーリクエストの一環として、2025年の初めに変更されます。 現在の未ステッチプロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 このイベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を解消するために、2025年以降、新しい未ステッチプロセスでは、プライバシーリクエストの対象となるイベントが永続 ID を使用して更新されます。
> 

ステッチ前とステッチ後の ID およびイベントについて詳しくは、次のデータを例として参照してください。

| ID マップ | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| イベントデータセット | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| ステッチされたデータセット | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 | 結果のID | ステッチ名前空間 |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**プライバシー要求の現在のプロセス**

CustID Bob を持つ顧客に対するプライバシーリクエストを受信すると、取り消し線エントリを含む行が削除されます。 その他のイベントは、ID マップを使用して再ステッチされます。 例えば、ステッチされたデータセット内の最初のステッチ ID は、**Alex** に更新されます。

| ID マップ | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| イベントデータセット | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| ステッチされたデータセット | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 | 結果のID | ステッチ名前空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**プライバシーリクエストの新しいプロセス**

CustID Bob を持つ顧客に対するプライバシーリクエストを受信すると、取り消し線エントリを含む行が削除されます。 その他のイベントは、永続 ID を使用して再ステッチされます。 例えば、ステッチされたデータセット内の最初のステッチ ID は、**123** に更新されます。

| ID マップ | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| イベントデータセット | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| ステッチされたデータセット | ID | タイムスタンプ | 永続 ID | 永続名前空間 | ユーザー ID | ユーザー名前空間 | 結果のID | ステッチ名前空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## 空白の永続 ID 値

**質問**: 1つ以上のイベントの永続ID フィールドが空白の場合はどうなりますか？

+++回答

永続的ID フィールドがステッチされるデータセット内のイベントで空白の場合、そのイベントの結果IDは、次の2つの方法のいずれかで決定されます。

* 人物ID フィールドが空白でない場合、Customer Journey Analyticsは人物IDの値を結果のIDとして使用します。
* 人物ID フィールドが空白の場合、Customer Journey Analyticsでは結果のIDも空白のままになります。 この場合、永続的ID、人物ID、および結果のIDはすべてイベントで空白になります。 これらの種類のイベントは、結果のIDが人物IDとして選択されたデータセットをステッチして、任意のCustomer Journey Analytics接続からドロップされます。

+++


## 未定義のユーザー ID 値

**質問**: 1つ以上のイベントのユーザーID フィールドに`Undefined`などのプレースホルダー値がある場合、どうなりますか？

+++回答

一時 ID のプレースホルダー値を使用するデータにステッチを適用する際に発生する「ユーザーの折りたたみ」に注意してください。 次の表の例では、CRM システムをソースとするデータセットから取得した未定義のユーザー ID に「Undefined」という値が設定されるので、ユーザーが誤って表示されています。

| イベント | タイムスタンプ | 永続 ID（cookie ID） | 一時 ID | 結果のID （リプレイ後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Undefined | **Undefined** |
| 4 | 2023-05-12 12:04 | 456 | - | **Undefined** |
| 5 | 2023-05-12 12:05 | 789 | Undefined | **Undefined** |
| 6 | 2023-05-12 12:06 | 012 | Undefined | **Undefined** |
| 7 | 2023-05-12 12:07 | 012 | - | **Undefined** |
| 8 | 2023-05-12 12:03 | 789 | Undefined | **Undefined** |
| 9 | 2023-05-12 12:09 | 456 | - | **Undefined** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 デバイス** | **2 人**：<br/>イベント 1、4、7、9、10 がドロップされました | **2 人**：<br/>Cory、未認証（1 ユーザーに折りたたまれました） |

+++

## 指標の比較

**質問**: Customer Journey Analyticsのステッチ済みデータセットの指標を、Customer Journey AnalyticsのステッチされていないデータセットやAdobe Analyticsの同様の指標と比較する方法を教えてください。

+++回答

Customer Journey Analytics の特定の指標は、従来の Analytics の指標に似ていますが、比較する対象によっては、それ以外の指標は異なります。 下の表では、一般的な指標をいくつか比較しています。

| **Customer Journey Analytics ステッチデータ** | **Customer Journey Analytics 未ステッチデータ** | **Adobe Analytics** | **CDA を使用した Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人物** =結果IDが人物IDとして選択されている個別の人物IDの数。 **人物**&#x200B;は、ステッチプロセスの結果に応じて、従来の **Adobe Analytics** のユニーク訪問者よりも多くなったり少なくなったりする場合があります。 | **人物** = ユーザー ID として選択された列に基づく個別のユーザー ID の数。 Analytics ソースコネクタデータセットの&#x200B;**人物**&#x200B;は、（Customer Journey Analytics で `endUserIDs._experience.aaid.id` をユーザー ID として使用した場合）従来の Adobe Analytics の&#x200B;**ユニーク訪問者**&#x200B;に似ています。 | **ユニーク訪問者** = 個別の訪問者 ID の数。 **ユニーク訪問者**&#x200B;は、個別の **ECID** の数と同じにならない場合があります。 | [人物](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/people)を参照してください。 |
| **セッション数**：Customer Journey Analytics データビューのセッション設定に基づいて定義されます。 ステッチ処理では、複数のデバイスからの個々のセッションを 1 つのセッションにまとめることができます。 | **セッション数**：Customer Journey Analytics データビューで指定されたセッション設定に基づいて定義されます。 | **訪問数**：[訪問数](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/visits)を参照してください。 | **訪問**：[CDA 仮想レポートスイート](https://experienceleague.adobe.com/en/docs/analytics/components/cda/setup)で指定されたセッション設定に基づいて定義されます。 |
| **イベント数** = Customer Journey Analytics でのステッチデータの行数。 この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。 ただし、空白の一時 ID がある行については、上記の FAQ に注意してください。 | **イベント数** = Customer Journey Analytics での未ステッチデータの行数。 この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。 ただし、Experience Platform データレイクの未ステッチデータに空白のユーザー ID が含まれているイベントがある場合、これらのイベントは Customer Journey Analytics に含まれません。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences)を参照してください。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences)を参照してください。 |

その他の指標は、Customer Journey Analytics と Adobe Analytics で似ている場合があります。 例えば、Adobe Analytics の[カスタムイベント](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/custom-events) 1～100 の合計数は、従来の Adobe Analytics と Customer Journey Analytics（ステッチか未ステッチかに関わらず）で非常に近い値になります。 Customer Journey Analytics と Adobe Analytics のイベントの重複排除などの[機能の違い](/help/getting-started/aa-vs-cja/cja-aa.md)により、2 つの製品間で不一致が生じることがあります。

+++

## ID マップ

**質問**: Customer Journey AnalyticsではID マップフィールドを使用できますか？

+++回答

はい、Customer Journey Analytics では、[フィールドベース](/help/stitching/fbs.md#identitymap)と[グラフベース](/help/stitching/gbs.md#identitymap)の両方のステッチに「 ID マップ」フィールドを使用できます。

+++

## グラフベースのステッチへの切り替え

**質問**: フィールドベースのステッチングからグラフベースのステッチングに切り替えるには、データを再取り込みする必要がありますか？

+++回答

データは、Experience Platformに再インポートする必要はありません。 ただし、データはCustomer Journey Analyticsで再設定する必要があります。 次の手順に従ってください。

1. グラフベースのステッチを使用して、新しいグラフベースのステッチされたデータセットを設定します。
1. 非常に短い時間枠のデータで新しい一時接続を作成します。
1. この一時接続の一部として、新しいグラフベースのデータセットを設定します。
1. この新しい一時接続で、グラフベースのステッチが正しく機能するかどうかを確認します。
1. グラフベースのステッチが期待どおりに機能する場合は、グラフベースのデータセットの追加のバックフィルをリクエストし、元の接続のフィールドベースのデータセットを新しいグラフベースのデータセットとスワップします。
1. 一時接続を削除します。

+++

## レポートの中断

**質問**：既存のレポートに中断はありますか？

+++回答

上記の手順に従う限り、中断は発生しません。 それ以外の場合、その他のサポートについて詳しくは、Adobe Consulting にお問い合わせください。

+++

## ID サービスのデータセットの有効化

**質問**: ID サービスのデータセットのみを有効にする方法を教えてください。

+++回答

ID サービスがグラフベースのステッチでデータセットを使用できるように、データセットが有効になっていることを確認します。

グラフベースのステッチを利用するために、Real-Time Customer Data Platform のライセンスを取得する必要はありません。 グラフベースのステッチは、リアルタイム顧客プロファイルではなく、使用可能な ID グラフに基づいています。

既存のデータセットを確認し、ID サービスのデータセットのみを有効にするには、`unifiedIdentity` タグのみを使用する`/datasets` エンドポイントに`PATCH` リクエストを使用します。 例：

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedIdentity", "value": ["enabled:true"] }
      ]'
```

リアルタイム顧客データプロファイルのライセンスを取得していない場合、リクエストで `unifiedProfile` タグを使用すると、エラーが返されます。

詳しくは、[プロファイルおよび ID 対応データセットの作成](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset)を参照してください。

+++


## ステッチされた名前空間値

**質問**：ステッチされた名前空間値が、CJA接続内の別のデータセット内で使用する可能性のあるID名前空間値と必ずしも一致しないのはなぜですか？

+++回答

デフォルトでは、ステッチされた名前空間の値は小文字です。 したがって、`custEmail`は`custemail`になります。 ID名前空間値`custEmail`を持つ別のデータセットがある場合、2つの値が一致しません。 レポートでこの動作を回避するには、[lowercase （） &#x200B;](/help/data-views/derived-fields/derived-fields.md#lowercase)派生フィールド関数を使用して、ID名前空間値を一致させることができます。

+++
