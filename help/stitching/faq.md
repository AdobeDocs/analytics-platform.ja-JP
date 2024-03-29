---
title: ステッチに関する FAQ
description: ステッチに関するよくある質問 (FAQ)
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 34%

---

# よくある質問

ステッチに関するよくある質問を次に示します。

+++**ステッチを使用して、ユーザーがチャネル間をどのように移動しているかを確認する方法を教えてください。**

フロービジュアライゼーションを、データセット ID ディメンションと合わせて使用できます。

1. にログインします。 [Customer Journey Analytics](https://analytics.adobe.com) 空の Workspace プロジェクトを作成します。
2. を選択します。 **[!UICONTROL **&#x200B;ビジュアライゼーション&#x200B;**]** タブをクリックし、 **[!UICONTROL **&#x200B;流量&#x200B;**]** ビジュアライゼーションを右側のキャンバスにドラッグします。
3. を選択します。 **[!UICONTROL **&#x200B;コンポーネント&#x200B;**]** タブをクリックし、寸法をドラッグします。 **[!UICONTROL **&#x200B;データセット ID **]** ラベル付きの中央の位置に **[!UICONTROL ** Dimensionまたは項目&#x200B;**]**.
4. このフローレポートはインタラクティブです。フローを後続のページまたは前のページに展開するには、任意の値を選択します。 右クリックメニューを使用して、列を展開または折りたたむことができます。同じフローレポート内で異なるディメンションを使用することもできます。

データセット ID ディメンションの項目の名前を変更する場合は、検索データセットを使用できます。

+++

+++**訪問者を結び付けると、どのくらい遡って再生しますか？**

キー更新のルックバックウィンドウは、データ[再生](explained.md)の頻度に応じて異なります。例えば、データを週に 1 回再生するようにステッチを設定した場合、キー更新のルックバックウィンドウは 7 日間になります。 データを毎日再生するようにステッチを設定した場合、キー更新のルックバックウィンドウは 1 日です。

+++

+++**共有デバイスはどのように処理されますか？**

状況によっては、同じデバイスから複数のユーザーがログインすることがあります。例としては、自宅の共有デバイス、図書館の共有 PC、小売アウトレットのキオスクなどがあります。

一時的な ID は永続 ID よりも優先されるので、共有デバイスは（同じデバイスから操作している場合でも）別のユーザーと見なされます。

+++

+++**1 人のユーザーが多数の永続的な ID を持っている場合、ステッチはどのように処理しますか。**

状況によっては、1 人のユーザーを多数の永続 ID に関連付けることができます。例としては、ブラウザーの cookie を頻繁にクリアしたり、ブラウザーのプライベート/匿名モードを使用したりする個人などがあります。

永続 ID の数は、一時的な ID には関係ありません。1 人のユーザーが任意の数のデバイスに属する場合でも、デバイス間でのCustomer Journey Analyticsのステッチ機能に影響を与えることはありません。

+++

+++**必要な情報をAdobeアカウントチームに連絡した後、キーが更新されたデータセットが利用可能になるまでにどれくらいかかりますか？**

ライブステッチは、Adobeがステッチを有効にしてから約 1 週間後に使用できます。 バックフィルの可用性は、既存のデータの量に応じて異なります。小規模なデータセット（1 日あたり 100 万イベント未満）の処理には通常 2 ～ 3 日かかりますが、大規模なデータセット（1 日あたり 10 億イベント）では 1 週間以上かかる場合があります。

+++

+++**クロスデバイス分析（従来の Analytics の機能）とクロスチャネル分析の違いは何ですか。**

[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja) は、デバイスをまたいでのユーザーの動作を理解できる、従来のAdobe Analyticsに固有の機能です。 デバイスデータを互いにリンクするために、フィールドベースのステッチとデバイスグラフの 2 つのワークフローを提供します。

クロスチャネル分析は、Customer Journey Analyticsに固有の使用例で、デバイスとチャネルの両方でユーザーがどのように操作するかを理解できます。 これにより、データセットのユーザー ID が結合され、そのデータセットを他のデータセットとシームレスに組み合わせることができます。 この機能は、クロスデバイス分析のフィールドベースのステッチと同様に設計で動作しますが、従来の Analytics とCustomer Journey Analyticsではデータアーキテクチャが異なるので、実装は異なります。 詳しくは、 [ステッチ](overview.md) そして [クロスチャネル分析](../use-cases/cross-channel/cross-channel.md) 使用例を参照してください。

+++

+++**ステッチでプライバシーリクエストはどのように処理されますか？**

Adobeは、現地法および国際法に従ってプライバシーリクエストを処理します。 アドビは、データアクセスリクエストとデータ削除リクエストを送信するための [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja) を提供しています。リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

+++

+++**1 つ以上のイベントの「永続 ID 」フィールドが空白の場合はどうなりますか？**

結び付けられるデータセットのイベントで「永続的 ID 」フィールドが空白の場合、そのイベントの結び付け ID は次の 2 つの方法のいずれかで決定されます。

* 「一時的な ID 」フィールドが空白でない場合、Customer Journey Analyticsは一時的な ID の値をステッチ ID として使用します。
* 「一時的な ID 」フィールドが空白の場合、Customer Journey Analyticsは「ステッチされた ID 」も空白のままにします。 この場合、イベントでは、永続 ID、一時的な ID、ステッチされた ID はすべて空白になります。 これらのタイプのイベントは、ステッチされた ID がユーザー ID として選択された場合、ステッチされるCustomer Journey Analyticsセットを使用して、あらゆるイベント接続から削除されます。

+++


+++**1 つ以上のイベントの「一時的な ID 」フィールドにプレースホルダー値（「未定義」など）がある場合はどうなりますか？**

一時的な ID にプレースホルダー値を使用するデータにステッチが適用される場合に発生する「人物の折りたたみ」は、注意してください。 次の表の例では、CRM システムからのデータセットから生成された未定義のユーザー ID に値「未定義」が設定されているので、個人が正しく表示されません。

| イベント | タイムスタンプ | 永続 ID (Cookie ID) | 一時的な ID（ログイン ID） | ステッチ済み ID（再生後） |
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
| | | **4 台のデバイス** | **2 人**:<br/>イベント 1、4、7、9、10 が削除されました | **2 人**:<br/>Cory、Unauthenticated（1 人のユーザーに折りたたまれた状態） |

+++

+++**Customer Journey Analytics関連付けデータセットの指標を、Customer Journey Analytics未関連付けデータセットの類似の指標と、Adobe Analyticsと比較するには、どうすればよいですか？**

Customer Journey Analyticsの特定の指標は、従来の Analytics の指標に似ていますが、比較する指標に応じて異なります。 下の表では、一般的な指標をいくつか比較しています。

| **Customer Journey Analytics ステッチデータ** | **Customer Journey Analytics 未ステッチデータ** | **Adobe Analytics** | **CDA を使用した Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **People** =ステッチ済み ID がユーザー ID として選択されたユニークユーザー ID の数。 **人物**&#x200B;は、ステッチプロセスの結果に応じて、従来の **Adobe Analytics** のユニーク訪問者よりも多くなったり少なくなったりする場合があります。 | **People** =ユーザー ID として選択された列に基づくユニークユーザー ID の数。 **People** Analytics ソースコネクタのデータセットは、 **実訪問者数** 従来のAdobe Analyticsで `endUserIDs._experience.aaid.id` は、ユーザー ID としてCustomer Journey Analyticsで使用されます。 | **ユニーク訪問者** = 個別の訪問者 ID の数。**ユニーク訪問者**&#x200B;は、個別の **ECID** の数と同じにならない場合があります。 | [人物](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=ja)を参照してください。 |
| **セッション数**：Customer Journey Analytics データビューのセッション設定に基づいて定義されます。ステッチ処理では、複数のデバイスからの個々のセッションを 1 つのセッションにまとめることができます。 | **セッション数**：Customer Journey Analytics データビューで指定されたセッション設定に基づいて定義されます。 | **訪問数**：[訪問数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ja)を参照してください。 | **訪問**：[CDA 仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=ja)で指定されたセッション設定に基づいて定義されます。 |
| **イベント数** = Customer Journey Analytics でのステッチデータの行数。この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、空の永続 ID を持つ行に関する上記の FAQ に注意してください。 | **イベント数** = Customer Journey Analytics での未ステッチデータの行数。この指標は、通常、従来の Adobe Analytics の&#x200B;**回数**&#x200B;に近い値になります。ただし、Experience Platformデータレイクの未関連付けデータに空のユーザー ID が含まれるイベントがある場合、これらのイベントはCustomer Journey Analyticsには含まれません。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)を参照してください。 | **発生回数**：[発生回数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ja)を参照してください。 |

その他の指標は、「Customer Journey Analytics」と「Adobe Analytics」で似ています。 例えば、Adobe Analyticsの合計数です。 [カスタムイベント](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=ja) 1 ～ 100 は、従来のAdobe AnalyticsとCustomer Journey Analytics（ステッチされているか未ステッチかに関わらず）に匹敵します。 [機能の違い](/help/getting-started/aa-vs-cja/cja-aa.md)) 例えば、Customer Journey AnalyticsとAdobe Analyticsの間のイベント重複除外は、2 つの製品間で矛盾を引き起こす可能性があります。

+++

+++**Customer Journey Analyticsは ID マップフィールドを使用できますか？**

いいえ。Customer Journey Analyticsは現在、ID マップフィールドをステッチに使用できません。

+++
