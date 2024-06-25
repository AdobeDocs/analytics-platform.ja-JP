---
title: ステッチに関する FAQ
description: ステッチに関するよくある質問
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 80d5a864e063911b46ff248f2ea89c1ed0d14e32
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 29%

---

# よくある質問

ステッチに関するよくある質問を以下に示します。

+++**ステッチを使用して、ユーザーがチャネル間を移動する様子を確認するにはどうすればよいですか？**

フロービジュアライゼーションを、データセット ID ディメンションと合わせて使用できます。

1. へのログイン [Customer Journey Analytics](https://analytics.adobe.com) 空のワークスペースプロジェクトを作成します。
2. 「」を選択します **[!UICONTROL **&#x200B;ビジュアライゼーション&#x200B;**]** tab キーを押しながら **[!UICONTROL **&#x200B;フロー&#x200B;**]** 右側のキャンバスへのビジュアライゼーション。
3. 「」を選択します **[!UICONTROL ** Components **]** tab キーを押しながらディメンションをドラッグします **[!UICONTROL **&#x200B;データセット ID **]** 中心の位置にラベル付け **[!UICONTROL ** Dimensionまたは品目&#x200B;**]**.
4. このフローレポートはインタラクティブです。後続または前のページにフローを展開するには、いずれかの値を選択します。 右クリックメニューを使用して、列を展開または折りたたむことができます。同じフローレポート内で異なるディメンションを使用することもできます。

データセット ID ディメンションの項目の名前を変更する場合は、検索データセットを使用できます。

+++

+++**再生訪問者をステッチするのにどのくらい遡りますか？**

キー更新のルックバックウィンドウは、データ再生の希望頻度によって異なります。 例えば、データを毎週 1 回再生するステッチを設定した場合、キー更新のルックバックウィンドウは 7 日になります。 データを毎日再生するステッチを設定した場合、キー更新のルックバックウィンドウは 1 日です。

+++

+++**共有デバイスはどのように扱われますか？**

状況によっては、同じデバイスから複数のユーザーがログインすることがあります。例としては、自宅の共有デバイス、図書館の共有 PC、小売アウトレットのキオスクなどがあります。

一時的な ID は永続 ID よりも優先されるので、共有デバイスは（同じデバイスから操作している場合でも）別のユーザーと見なされます。

+++

+++**1 人のユーザーが多数の永続 ID を持っている場合、ステッチはどのように処理されますか？**

状況によっては、1 人のユーザーを多数の永続 ID に関連付けることができます。例えば、頻繁にブラウザーの Cookie をクリアするユーザーや、ブラウザーのプライベート/匿名モードを使用するユーザーです。

フィールドベースのステッチの場合、永続 ID の数は関係なく、一時的な ID が優先されます。 1 人のユーザーが任意の数のデバイスに属することができますが、Customer Journey Analyticsのデバイス間のステッチ機能に影響を与えることはありません。

グラフベースのステッチの場合、1 人のユーザーが ID グラフに多数の永続 ID を持っている可能性があります。 グラフベースのステッチでは、指定した名前空間に基づいて永続 ID を使用します。 同じ名前空間により多くの永続 ID がある場合は、辞書的な最初の永続 ID が使用されます。

+++

+++**必要な情報をAdobeアカウントチームに連絡したら、キーを更新したデータセットが使用可能になるまで、どのくらい時間がかかりますか？**

ライブステッチは、Adobeがステッチを有効にしてから約 1 週間後に使用可能になります。 バックフィルの可用性は、既存のデータの量に応じて異なります。小規模なデータセット（1 日あたり 100 万イベント未満）の処理には通常 2 ～ 3 日かかりますが、大規模なデータセット（1 日あたり 10 億イベント）では 1 週間以上かかる場合があります。

+++

+++**クロスデバイス分析（従来の Analytics の機能）とクロスチャネル分析の違いは何ですか。**

[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja) は、人がどのようにデバイスをまたいで操作するかを把握できる、従来のAdobe Analytics専用の機能です。 デバイスデータを互いにリンクするために、フィールドベースのステッチとデバイスグラフの 2 つのワークフローを提供します。

Cross-channel analysis は、人がどのようにデバイスとチャネルの両方をまたいで操作するかを把握できる、Customer Journey Analytics専用のユースケースです。 データセットの人物 ID をステッチし、そのデータセットを他のデータセットとシームレスに組み合わせることができます。 この機能は、クロスデバイス分析のフィールドベースのステッチと同様の設計で動作しますが、従来の Analytics とCustomer Journey Analyticsではデータアーキテクチャが異なるので、実装は異なります。 参照： [ステッチ](overview.md) および [クロスチャネル分析](../use-cases/cross-channel/cross-channel.md) ユースケースを参照してください。

+++

+++**ステッチではプライバシーリクエストをどのように処理しますか？**

Adobeは、地域および国際法に従ってプライバシーリクエストを処理します。 アドビは、データアクセスリクエストとデータ削除リクエストを送信するための [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja) を提供しています。リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

+++

+++**1 つ以上のイベントの「永続 ID」フィールドが空白の場合はどうなりますか？**

ステッチされるデータセット内のイベントで「永続 ID」フィールドが空白の場合、そのイベントのステッチ ID は次の 2 つの方法のいずれかで決定されます。

* 一時的な ID フィールドが空白でない場合、Customer Journey Analyticsは一時的な ID の値をステッチされた ID として使用します。
* 「一時的な ID」フィールドが空白の場合、Customer Journey Analyticsではステッチされた ID も空白のままになります。 この場合、永続 ID、一時 ID、ステッチ ID はすべてイベントで空白になります。 これらのタイプのイベントは、ステッチされた ID がユーザー ID として選択されたステッチ対象のデータセットを使用しているどのCustomer Journey Analytics接続でもドロップされます。

+++


+++**1 つ以上のイベントの「一時的な ID」フィールドに「未定義」などのプレースホルダー値が含まれている場合、どうなりますか？**

一時的な ID にプレースホルダー値を使用するデータにステッチが適用される場合は、「人物を折りたたむ」ことに注意してください。 次の表の例では、CRM システムをソースとするデータセットから取得された未定義の人物 ID に値「Undefined」が設定されているため、人物が誤って表現されています。

| イベント | タイムスタンプ | 永続 ID （Cookie ID） | 一時 ID （ログイン ID） | ステッチ ID （再生後） |
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
| | | **4 デバイス** | **2 人**:<br/>イベント 1、4、7、9、10 が削除されました | **2 人**:<br/>Cory、未認証（1 人のユーザーに限定） |

+++

+++**Customer Journey Analyticsでステッチされたデータセットの指標は、Customer Journey Analyticsでステッチされていないデータセットの同様の指標およびAdobe Analyticsと比較してどうでしょうか？**

Customer Journey Analyticsの特定の指標は、従来の Analytics の指標に似ていますが、比較する対象によっては、それ以外の指標は異なります。 下の表では、一般的な指標をいくつか比較しています。

| **Customer Journey Analytics ステッチデータ** | **Customer Journey Analytics 未ステッチデータ** | **Adobe Analytics** | **CDA を使用した Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人物** =ステッチ ID がユーザー ID として選択された場合の個別のユーザー ID の数。 **人物**&#x200B;は、ステッチプロセスの結果に応じて、従来の **Adobe Analytics** のユニーク訪問者よりも多くなったり少なくなったりする場合があります。 | **人物** =人物 ID として選択された列に基づく個別の人物 ID の数。 **人物** Analytics のソースコネクタデータセットは、に似ています **ユニーク訪問者** 従来のAdobe Analyticsでは、次の場合 `endUserIDs._experience.aaid.id` は、Customer Journey Analyticsでユーザー ID として使用されます。 | **ユニーク訪問者** = 個別の訪問者 ID の数。**ユニーク訪問者**&#x200B;は、個別の **ECID** の数と同じにならない場合があります。 | [人物](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=ja)を参照してください。 |
| **セッション数**：Customer Journey Analytics データビューのセッション設定に基づいて定義されます。ステッチ処理では、複数のデバイスからの個々のセッションを 1 つのセッションにまとめることができます。 | **セッション数**：Customer Journey Analytics データビューで指定されたセッション設定に基づいて定義されます。 | **訪問数**：[訪問数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ja)を参照してください。 | **訪問**：[CDA 仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=ja)で指定されたセッション設定に基づいて定義されます。 |
| **イベント数** = Customer Journey Analytics でのステッチデータの行数。この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、空白の永続 ID を持つ行については、上記の FAQ に注意してください。 | **イベント数** = Customer Journey Analytics での未ステッチデータの行数。この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、Experience Platformデータレイクの未ステッチデータに空白の人物 ID が含まれているイベントがある場合、これらのイベントはCustomer Journey Analyticsに含まれません。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)を参照してください。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)を参照してください。 |

その他の指標は、Customer Journey AnalyticsとAdobe Analyticsで似ている場合があります。 例えば、Adobe Analyticsの合計数などです [カスタムイベント](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=ja) 1 ～ 100 は、従来のAdobe AnalyticsとCustomer Journey Analytics（ステッチか未ステッチかに関わらず）で同等です。 [機能の違い](/help/getting-started/aa-vs-cja/cja-aa.md)）の場合、Customer Journey AnalyticsとAdobe Analyticsの間でイベントの重複排除が行われ、2 つの製品間で不一致が生じることがあります。

+++

+++**Customer Journey Analyticsは ID マップフィールドを使用できますか。**

いいえ。Customer Journey Analyticsは現在、ステッチに ID マップのフィールドを使用できません。

+++

+++**フィールドベースのステッチからグラフベースのステッチに切り替えるには、データを取り込む必要がありますか？**
データはExperience Platformに取り込む必要はありませんが、Customer Journey Analyticsで再設定する必要があります。 次の手順に従ってください。

1. 新しいグラフベースのステッチされたデータセットを設定します。
1. Customer Journey Analyticsの新しい接続の一部として新しいデータセットを設定します。
1. 新しい接続（および新しいグラフベースのステッチされたデータセット）を使用するように、既存のデータビューを切り替えます
1. フィールドベースのステッチされたデータセットを使用していた古い接続を削除します。

+++

+++**既存のレポートに何らかの中断はありますか？**

上記の手順に従う場合は、できません。 それ以外の場合は、Adobeのコンサルティングに問い合わせて、追加サポートを依頼してください。

+++


