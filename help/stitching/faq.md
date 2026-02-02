---
title: ステッチに関する FAQ
description: ステッチに関するよくある質問について説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '2149'
ht-degree: 22%

---

# よくある質問

ステッチに関するよくある質問を以下に示します。

## チャネル間を移動

+++ ステッチを使用して、ユーザーがチャネル間を移動する様子を確認するにはどうすればよいですか？

フロービジュアライゼーションを、データセット ID ディメンションと合わせて使用できます。

1. [Customer Journey Analytics](https://analytics.adobe.com) にログインし、空のWorkspace プロジェクトを作成します。
2. 左側の **[!UICONTROL ** ビジュアライゼーション **]** タブを選択し、**[!UICONTROL **&#x200B; フロー &#x200B;**]** ビジュアライゼーションを右側のキャンバスにドラッグします。
3. 左側の **[!UICONTROL ** コンポーネント **]** タブを選択し、ディメンション **[!UICONTROL ** データセット ID **]** を、中央にある、**[!UICONTROL **&#x200B; Dimensionまたは Item &#x200B;**]** というラベルが付いた場所にドラッグします。
4. このフローレポートはインタラクティブです。後続または前のページにフローを展開するには、いずれかの値を選択します。 右クリックメニューを使用して、列を展開または折りたたむことができます。同じフローレポート内で異なるディメンションを使用することもできます。

データセット ID ディメンションの項目の名前を変更する場合は、検索データセットを使用できます。

+++

## 再生

+++ 再生プロファイルをステッチしてどのくらい遡るか。

キー更新のルックバックウィンドウは、データ再生の希望頻度によって異なります。 例えば、データを毎週 1 回再生するステッチを設定した場合、キー更新のルックバックウィンドウは 7 日になります。 データを毎日再生するステッチを設定した場合、キー更新のルックバックウィンドウは 1 日です。

+++

## 共有デバイス

+++ 共有デバイスはどのように処理されますか？

状況によっては、同じデバイスから複数のユーザーがログインすることがあります。例としては、自宅の共有デバイス、図書館の共有 PC、小売アウトレットのキオスクなどがあります。

ユーザー ID が永続 ID を上書きするので、共有デバイスは、（同じデバイスから作成された場合でも）別の人物と見なされます。

詳しくは、[&#x200B; 共有デバイス &#x200B;](/help/use-cases/stitching/shared-devices.md) のユースケースを参照してください。

+++

## 多くの永続 ID

+++ 1 人のユーザーが多数の永続 ID を持っている場合、ステッチはどのように処理されますか？

状況によっては、1 人のユーザーを多数の永続 ID に関連付けることができます。例えば、頻繁にブラウザーの Cookie をクリアしたり、ブラウザーのプライベート/匿名モードを使用したりする個人です。

フィールドベースのステッチの場合、永続 ID の数は関係なく、人物 ID が優先されます。 1 人のユーザーが任意の数のデバイスに属することができますが、その際にCustomer Journey Analyticsのデバイス間ステッチ機能は影響を受けません。

グラフベースのステッチの場合、1 人のユーザーが ID グラフに多数の永続 ID を持っている可能性があります。 グラフベースのステッチでは、指定した名前空間に基づいて永続 ID を使用します。 同じ名前空間に対してより多くの永続 ID がある場合、辞書編集用の最初の永続 ID が使用されます。

+++

## ステッチプロセス

+++ 必要な情報をアドビのアカウントチームに連絡した後、キー更新されたデータセット利用可能になるまでにどのくらいかかりますか？

ライブステッチは、Adobeがステッチを有効にしてから約 1 週間後に使用可能になります。 バックフィルの可用性は、既存のデータの量に応じて異なります。小規模なデータセット（1 日あたり 100 万イベント未満）の処理には通常 2 ～ 3 日かかりますが、大規模なデータセット（1 日あたり 10 億イベント）では 1 週間以上かかる場合があります。

+++

## クロスデバイス分析とクロスチャネル分析の比較

+++ クロスデバイス分析（従来の Analytics の機能）とクロスチャネル分析の違いは何ですか。

[&#x200B; クロスデバイス分析 &#x200B;](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview) は、人がどのようにデバイスをまたいで操作するかを把握できる、従来のAdobe Analytics専用の機能です。 デバイスデータを互いにリンクするために、フィールドベースのステッチとデバイスグラフの 2 つのワークフローを提供します。

Cross-channel analysis は、人がどのようにデバイスとチャネルの両方をまたいで操作するかを把握できる、Customer Journey Analytics専用のユースケースです。 データセットの人物 ID をステッチし、そのデータセットを他のデータセットとシームレスに組み合わせることができます。 この機能は、クロスデバイス分析のフィールドベースのステッチと同様の設計で動作しますが、従来の Analytics とCustomer Journey Analyticsではデータアーキテクチャが異なるので、実装は異なります。 詳しくは、[&#x200B; ステッチ &#x200B;](overview.md) および [&#x200B; クロスチャネル分析 &#x200B;](../use-cases/cross-channel/cross-channel.md) ユースケースを参照してください。

+++

## プライバシー

+++ ステッチではプライバシーリクエストをどのように処理しますか？

Adobeでは、各国および国際法に従ってプライバシーリクエストを処理します。 アドビは、データアクセスリクエストとデータ削除リクエストを送信するための [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/home) を提供しています。リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

>[!IMPORTANT]
>
>ステッチ解除プロセスは、プライバシーリクエストの一環として、2025 年の初めに変更されます。 現在のステッチ解除プロセスでは、既知の ID の最新バージョンを使用してイベントが再ステッチされます。 イベントを別の ID に再割り当てすると、望ましくない法的結果が生じる可能性があります。 これらの懸念を修正するために、2025 年以降、新しいステッチプロセスにより、プライバシーリクエストの対象となるイベントが永続 ID で更新されます。
> 

説明するために、ID の次のデータを想定します。つまり、ステッチの前と後のイベントです。

| ID マップ | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | 人物 IO | 人物の名前空間 |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | ボブ | CustId |
|  | 2 | ts2 | 123 | ecid | アレックス | CustId |


| イベントデータセット | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | ボブ | CustId |
| | 3 | ts2 | 123 | ecid | アレックス | CustId |


| ステッチされたデータセット | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 | ステッチ ID | ステッチされた名前空間 |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | ボブ | CustId |
| | 2 | ts1 | 123 | ecid | ボブ | CustId | ボブ | CustId |
| | 3 | ts2 | 123 | ecid | アレックス | CustId | アレックス | CustId |


**プライバシーリクエストの現在のプロセス**

CustID Bob を持つ顧客に対するプライバシーリクエストを受信すると、取り消し線エントリを含む行が削除されます。 その他のイベントは、ID マップを使用して再タイトルされます。 例えば、ステッチされたデータセット内の最初のステッチ ID は **Alex** に更新されます。

| ID マップ | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~ボブ~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | アレックス | CustId |


| イベントデータセット | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~ボブ~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | アレックス | CustId |


| ステッチされたデータセット | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 | ステッチ ID | ステッチされた名前空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **アレックス** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~ボブ~~ | ~~CustId~~ | ~~ボブ~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | アレックス | CustId | アレックス | CustId |


**プライバシーリクエストの新しいプロセス**

CustID Bob を持つ顧客に対するプライバシーリクエストを受信すると、取り消し線エントリを含む行が削除されます。 その他のイベントは、永続 ID を使用して再タイトルされます。 例えば、ステッチされたデータセット内の最初のステッチ ID は **123** に更新されます。

| ID マップ | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~ボブ~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | アレックス | CustId |


| イベントデータセット | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~ボブ~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | アレックス | CustId |


| ステッチされたデータセット | Id | タイムスタンプ | 永続 ID | 永続的な名前空間 | ユーザー ID | 人物の名前空間 | ステッチ ID | ステッチされた名前空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~ボブ~~ | ~~CustId~~ | ~~ボブ~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | アレックス | CustId | アレックス | CustId |

+++

## 空白の永続 ID 値

+++ 1 つ以上のイベントの「永続 ID」フィールドが空白の場合はどうなりますか？

ステッチされるデータセット内のイベントで永続 ID フィールドが空白の場合、そのイベントのステッチ ID は次の 2 つの方法のいずれかで決定されます。

* 人物 ID フィールドが空白でない場合、Customer Journey Analyticsは人物 ID の値をステッチされた ID として使用します。
* ユーザー ID フィールドが空白の場合、Customer Journey Analyticsではステッチされた ID も空白のままになります。 この場合、永続 ID、人物 ID、ステッチ ID はすべてイベントで空白になります。 これらのタイプのイベントは、ステッチされた ID が人物 ID として選択されたステッチ対象のデータセットを使用しているどのCustomer Journey Analytics接続でもドロップされます。

+++


## 未定義のユーザー ID 値

+++ 1 つ以上のイベントのユーザー ID フィールドに `Undefined` のようなプレースホルダー値がある場合はどうなりますか？

一時的な ID にプレースホルダー値を使用するデータにステッチが適用される場合は、「人物を折りたたむ」ことに注意してください。 次の表の例では、CRM システムをソースとするデータセットから取得された未定義の人物 ID に値「Undefined」が設定されているため、人物が誤って表現されています。

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID | ステッチ ID （再生後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **コリー** |
| 2 | 2023-05-12 12:02 | 123 | コリー | **コリー** |
| 3 | 2023-05-12 12:03 | 456 | 未定義 | **未定義** |
| 4 | 2023-05-12 12:04 | 456 | - | **未定義** |
| 5 | 2023-05-12 12:05 | 789 | 未定義 | **未定義** |
| 6 | 2023-05-12 12:06 | 012 | 未定義 | **未定義** |
| 7 | 2023-05-12 12:07 | 012 | - | **未定義** |
| 8 | 2023-05-12 12:03 | 789 | 未定義 | **未定義** |
| 9 | 2023-05-12 12:09 | 456 | - | **未定義** |
| 10 | 2023-05-12 12:02 | 123 | - | **コリー** |
| | | **4 デバイス** | **2 人**:<br/> イベント 1、4、7、9、10 がドロップされました | **2 人**:<br/>Cory、未認証（1 人のユーザーに折りたたまれた状態） |

+++

## 指標の比較

+++ Customer Journey Analyticsでステッチされたデータセットの指標は、Customer Journey Analyticsの未ステッチデータセットの同様の指標およびAdobe Analyticsと比較してどうですか？

Customer Journey Analyticsの特定の指標は、従来の Analytics の指標に似ていますが、比較する対象によっては、それ以外の指標は異なります。 下の表では、一般的な指標をいくつか比較しています。

| **Customer Journey Analytics ステッチデータ** | **Customer Journey Analytics 未ステッチデータ** | **Adobe Analytics** | **CDA を使用した Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **People** = ステッチされた ID が人物 ID として選択された場合の個別の人物 ID の数。 **人物**&#x200B;は、ステッチプロセスの結果に応じて、従来の **Adobe Analytics** のユニーク訪問者よりも多くなったり少なくなったりする場合があります。 | **People** = ユーザー ID として選択された列に基づく個別のユーザー ID の数。 Analytics ソースコネクタデータセットの **人物** は、Customer Journey Analyticsでユーザー ID として使用される場合、従来のAdobe Analyticsの **ユニーク訪問者** に似 `endUserIDs._experience.aaid.id` います。 | **ユニーク訪問者** = 個別の訪問者 ID の数。**ユニーク訪問者**&#x200B;は、個別の **ECID** の数と同じにならない場合があります。 | [人物](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/people)を参照してください。 |
| **セッション数**：Customer Journey Analytics データビューのセッション設定に基づいて定義されます。ステッチ処理では、複数のデバイスからの個々のセッションを 1 つのセッションにまとめることができます。 | **セッション数**：Customer Journey Analytics データビューで指定されたセッション設定に基づいて定義されます。 | **訪問数**：[訪問数](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/visits)を参照してください。 | **訪問**：[CDA 仮想レポートスイート](https://experienceleague.adobe.com/en/docs/analytics/components/cda/setup)で指定されたセッション設定に基づいて定義されます。 |
| **イベント数** = Customer Journey Analytics でのステッチデータの行数。この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、空白の永続 ID を持つ行については、上記の FAQ に注意してください。 | **イベント数** = Customer Journey Analytics での未ステッチデータの行数。この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、Experience Platform データレイクの未ステッチデータに空白の人物 ID が含まれているイベントがある場合、これらのイベントはCustomer Journey Analyticsに含まれません。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences)を参照してください。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences)を参照してください。 |

その他の指標は、Customer Journey AnalyticsとAdobe Analyticsで似ている場合があります。 例えば、Adobe Analytics[&#x200B; カスタムイベント &#x200B;](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/custom-events) の合計数は、従来のAdobe AnalyticsとCustomer Journey Analytics（ステッチか未ステッチかに関わらず）で 1～100 が比較可能です。 Customer Journey AnalyticsとAdobe Analyticsのイベントの重複排除などの [&#x200B; 機能の違い &#x200B;](/help/getting-started/aa-vs-cja/cja-aa.md)）により、2 つの製品間で不一致が生じることがあります。

+++

## ID マップ

+++ Customer Journey Analyticsで「ID マップ」フィールドを使用できますか？

はい。Customer Journey Analyticsでは、[&#x200B; フィールドベース」と &#x200B;](/help/stitching/fbs.md#identitymap) グラフベース [&#x200B; の両方のステッチに ID マップフィールドを使用 &#x200B;](/help/stitching/gbs.md#identitymap) きます。

+++

## グラフベースのステッチに切り替える

+++ フィールドベースのステッチからグラフベースのステッチに切り替えるには、データを取り込む必要がありますか？

データをExperience Platformに取り込む必要はありません。 ただし、Customer Journey Analyticsでデータを再設定する必要があります。 次の手順に従ってください。

1. グラフベースのステッチを使用して、新しいグラフベースのステッチされたデータセットを設定します。
1. データの非常に短い時間枠で新しい一時接続を作成します。
1. この一時的な接続の一部として、新しいグラフベースのデータセットを設定します。
1. この新しい一時的な接続で、グラフベースのステッチが正しく機能するかどうかを確認します。
1. グラフベースのステッチが期待どおりに機能する場合は、グラフベースのデータセットの追加のバックフィルをリクエストし、元の接続のフィールドベースのデータセットを新しいグラフベースのデータセットとスワップします。
1. 一時的な接続を削除します。

+++

## レポートの中断

+++ 既存のレポートに何らかの中断はありますか？

上記の手順に従う場合は、できません。 それ以外の場合は、Adobe Consultingに追加のサポートを依頼してください。

+++

## ID サービスのデータセットを有効にする

+++ ID サービスのみのデータセットを有効にする方法を教えてください。 

グラフベースのステッチでデータセットを使用するために、ID サービスでデータセットが有効になっていることを確認します。

グラフベースのステッチを利用するために、Real-Time Customer Data Platformのライセンスを取得する必要はありません。 グラフベースのステッチは、リアルタイム顧客プロファイルではなく、使用可能な ID グラフに基づいています。

既存のデータセットを確認し、ID サービスのみのデータセットを有効にするには、`PATCH` タグのみを使用する `/datasets` エンドポイントへの `unifiedIdentity` リクエストを使用します。 次に例を示します。

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedProfile", "value": ["enabled:true"] }
      ]'
```

リクエストで `unifiedProfile` タグを使用すると、リアルタイム顧客データプロファイルのライセンスを取得していなくても、エラーが返されます。

詳しくは、[&#x200B; プロファイルおよび ID 対応データセットの作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset) を参照してください。

+++ 


## ステッチされた名前空間値

+++ ステッチされた名前空間値が、CJA接続内の別のデータセット内で使用する可能性のある ID 名前空間値と常に一致するとは限らないのはなぜですか？

デフォルトでは、ステッチされた名前空間の値は小文字です。 だから、`custEmail` は `custemail` になります。 ID 名前空間値が `custEmail` の別のデータセットがある場合、2 つの値は一致しません。 レポートでこの動作を回避するには、派生フィールド関数 [lowercase （） &#x200B;](/help/data-views/derived-fields/derived-fields.md#lowercase) を使用して、ID 名前空間の値に一致させることができます。

