---
title: オーディエンスを作成してリアルタイム顧客プロファイルに公開する
description: Customer Journey Analytics からのオーディエンスの公開方法を学ぶ
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1565'
ht-degree: 63%

---

# オーディエンスの作成と公開

このトピックでは、にCustomer Journey Analyticsして識別されたオーディエンスを作成し、公開する方法について説明します。 [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja) Adobe Experience Platformの（顧客のターゲティングとパーソナライゼーションのため）

こちらを読む [概要](/help/components/audiences/audiences-overview.md) を参照して、Customer Journey Analyticsオーディエンスの概念を理解します。

## オーディエンスを作成 {#create}

1. オーディエンスを作成する際には、3 つの方法で開始できます。

   | 作成方法 | 詳細 |
   | --- | --- |
   | メイン&#x200B;**[!UICONTROL コンポーネント]／[!UICONTROL オーディエンス]**&#x200B;メニューから | Audiences Manager ページが開きます。「**[!UICONTROL オーディエンスを作成]**」をクリックすると、[!UICONTROL オーディエンスビルダー]が開きます。 |
   | フリーフォームテーブル内から | フリーフォームテーブルの項目を右クリックし、「**[!UICONTROL 選択範囲からオーディエンスを作成]**」を選択します。この方法を使用すると、フィルターに、テーブルで選択したディメンションまたはディメンション項目があらかじめ入力されます。 |
   | フィルターの作成／編集 UI から | 「**[!UICONTROL このフィルターからオーディエンスを作成]**」ボックスをオンにします。この方法を使用すると、フィルターが事前に設定されます。 |

   {style="table-layout:auto"}

1. オーディエンスを構築します。

   オーディエンスを公開する前に、これらの設定を行います。

   ![](assets/create-audience.png)

   | 設定 | 説明 |
   | --- | --- |
   | [!UICONTROL 名前] | オーディエンスの名前。 |
   | [!UICONTROL タグ] | 組織的な目的でオーディエンスに割り当てるタグ。既存のタグを使用するか、新しいタグを入力できます。 |
   | [!UICONTROL 説明] | 他のオーディエンスと区別するために、オーディエンスに関する適切な説明を追加します。 |
   | [!UICONTROL 更新頻度] | オーディエンスを更新する頻度。<ul><li>更新を必要としない 1 回限りのオーディエンス（デフォルト）の作成を選択できます。これは、特定の 1 回限りのキャンペーンなどに役立ちます。</li><li>その他の更新間隔を選択できます。4 時間の更新頻度の場合、Customer Journey Analyticsの使用権限に応じて、オーディエンスの更新回数は 75 ～ 150 までに制限されます。</li></ul> |
   | 有効期限 | オーディエンスが更新を停止したとき。デフォルトは作成日の 1 年後です。有効期限が近づいたオーディエンスは、予定レポートの有効期限が近づいた場合と同様に扱われます。管理者は、オーディエンスの期限が切れる 1 か月前にメールを受け取ります。 |
   | ルックバックウィンドウを更新 | このオーディエンスの作成時にデータウィンドウ内でどのくらい遡るかを指定します。最大 90 日です。 |
   | [!UICONTROL 1 回限りの日付範囲] | 1 回限りのオーディエンスを公開する日付範囲。 |
   | [!UICONTROL フィルター] | フィルターは、オーディエンスに対する主な入力です。最大 20 のフィルターを追加できます。これらのフィルターは、`And` または `Or` 演算子と結合させることができます。 |
   | [!UICONTROL サンプル ID を表示] | このオーディエンスの ID の例。サンプル ID を検索するには、検索バーを使用します。 |

   {style="table-layout:auto"}

1. データのプレビューを解釈します。

   オーディエンスのプレビューが右側のパネルに表示されます。作成したオーディエンスの要約分析が可能になります。

   ![](assets/data-preview.png)

   | プレビュー設定 | 説明 |
   | --- | --- |
   | [!UICONTROL データのプレビュー]ウィンドウ | オーディエンスの日付範囲。 |
   | [!UICONTROL 人物合計] | このオーディエンスの合計人数の概要。人数は 2,000 万人になることもあります。オーディエンスが 2,000 万人を超える場合は、オーディエンスを公開する前にサイズを小さくする必要があります。 |
   | [!UICONTROL オーディエンスサイズの制限] | このオーディエンスが 2,000 万の上限からどの程度離れているかを示します。 |
   | [!UICONTROL オーディエンス再来訪の見込み] | この設定は、このオーディエンスでサイトを再来訪した顧客をリターゲティングする場合に役立ちます。（つまり、このデータセットに再び表示されます。） <p>ここでは、再来訪の可能性がある顧客の推定数に対して期間（7 日間、次の 2 週間、次の月）を選択できます。 |
   | [!UICONTROL 再来訪する見込み] | この数により、ドロップダウンリストから選択した期間内の再訪問者の推定数が表示されます。このオーディエンスの過去のチャーンレートを調べて、この数を予測します。 |
   | [!UICONTROL 指標をプレビュー] | この設定を使用すると、特定の指標を調べて、このオーディエンスがこの指標（「[!UICONTROL 売上高]または「[!UICONTROL サイトでの平均時間]」など）に対して不相応な貢献を行っているかどうかを確認できます。指標の集計数と、指標が表す合計のパーセンテージが表示されます。データ表示で使用できる任意の指標を選択できます。 |
   | [!UICONTROL 含まれる名前空間] | オーディエンス内のユーザーに関連付けられている特定の名前空間。例としては、ECID、CRM ID、メールアドレスなどがあります。 |
   | [!UICONTROL サンドボックス] | このオーディエンスが格納されている [Experience Platform サンドボックス](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)。このオーディエンスを Platform に公開すると、このサンドボックスの範囲内でのみ操作できます。 |

   {style="table-layout:auto"}

1. オーディエンスの設定を再度確認し、「**[!UICONTROL 公開]**」をクリックします。

   すべてが正常に動作した場合は、オーディエンスが公開されたことを示す確認メッセージが表示されます。このオーディエンスは、1 ～ 2 分で Experience Platform に表示されます。（何百万人ものメンバーを持つオーディエンスの場合でも、所要時間は 5 分未満です。）

1. 同じメッセージ内で「**[!UICONTROL AEP でのオーディエンスの表示]**」をクリックすると、Adobe Experience Platform の [セグメント UI](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja) に移動します。詳しくは、次を参照してください。

## オーディエンスを作成した後はどうなりますか？ {#after-audience-created}

オーディエンスを作成した後、Adobeは新しいExperience PlatformオーディエンスごとにCustomer Journey Analyticsストリーミングセグメントを作成します。 Adobe Experience Platformのストリーミングセグメントは、組織がストリーミングセグメント化用に設定されている場合にのみ作成されます。

* Adobe Experience Platformセグメントは、Customer Journey Analyticsオーディエンスと同じ名前/説明を共有しますが、一意であることを確認するために、名前にCustomer Journey Analyticsオーディエンス ID が追加されます。
* Customer Journey Analyticsのオーディエンスの名前や説明が変更されると、Adobe Experience Platformのセグメント名や説明にもその変更が反映されます。
* Customer Journey Analyticsオーディエンスがユーザーによって削除された場合、Adobe Experience Platformセグメントは削除されません。 理由は、後でCustomer Journey Analyticsオーディエンスが削除解除される可能性があるからです。

## 待ち時間に関する考慮事項 {#latency}

オーディエンスの公開前、公開中、公開後のいくつかの時点で、待ち時間が発生する可能性があります。 発生し得る待ち時間の概要は次のとおりです。

![Adobe Experience PlatformからCustomer Journey Analyticsへの遅延](assets/latency-diagram.png)

| # | 待ち時間の時点 | 待ち時間の継続時間 |
| --- | --- | --- |
| 未表示 | Adobe Analyticsから Analytics ソースコネクタ (A4T) | 最大 30 分 |
| 1 | Data Lake へのデータ取り込み（Analytics Source Connector または他のソースから） | 最大 90 分 |
| 2 | Experience PlatformデータレイクからCustomer Journey Analyticsへのデータ取り込み | 最大 90 分 |
| 3 | ストリーミングセグメントの自動作成やセグメントでのデータの受信準備など、リアルタイム顧客プロファイルへのオーディエンスの公開。 | 約 60 分 |
| 4 | オーディエンスの更新頻度 | <ul><li>1 回の更新（5 分未満の待ち時間）</li><li>4 時間ごと、日次、週次、月次の更新（待ち時間は更新率と密接に関連しています）。 |
| 5 | Adobe Experience Platformでの宛先の作成：新しいセグメントのアクティブ化 | 1～2 時間 |

{style="table-layout:auto"}

## Experience PlatformでのCustomer Journey Analyticsオーディエンスの使用 {#audiences-aep}

Customer Journey Analyticsは、公開済みのオーディエンスからすべての名前空間と ID の組み合わせを取得し、それらをリアルタイム顧客プロファイル (RTCP) にストリーミングします。 Customer Journey Analyticsは、 [!UICONTROL 人物 ID] 接続が設定された時点で。

次に、RTCP は、各名前空間／ID の組み合わせを調べ、その組み合わせが含まれている可能性のあるプロファイルを探します。プロファイルは、基本的に、リンクされた名前空間、ID およびデバイスのクラスターです。プロファイルが見つかると、名前空間と ID がこのプロファイル内の他の ID にセグメントメンバーシップ属性として追加されます。現在は、例えば、「user@adobe.com」をすべてのデバイスおよびチャネルにわたってターゲットに設定できます。プロファイルが見つからない場合は、新しく作成されます。

Platform でCustomer Journey Analyticsオーディエンスを表示するには、次に移動します。 **[!UICONTROL セグメント]** > **[!UICONTROL セグメントの作成]** > **[!UICONTROL オーディエンス]** タブ/ **[!UICONTROL CJA オーディエンス]**.

Customer Journey Analyticsオーディエンスは、Adobe Experience Platformセグメントのセグメント定義にドラッグできます。

![](assets/audiences-aep.png)

## よくある質問（FAQ） {#faq}

オーディエンスの投稿に関するよくある質問です。

+++**ユーザーがオーディエンスのメンバーでなくなった場合はどうなりますか？Customer Journey Analytics**

この場合、終了イベントはイベントからExperience Platformに送信されます。

+++

+++**Customer Journey Analyticsでオーディエンスを削除するとどうなりますか？**

Customer Journey Analyticsオーディエンスが削除されると、そのオーディエンスはExperience PlatformUI に表示されなくなります。 ただし、そのオーディエンスに関連付けられたプロファイルは、実際には Platform では削除されません。

+++

+++**対応するプロファイルが RTCDP に存在しない場合は、新しいプロファイルが作成されますか？**

はい、作成されます。

+++

+++**Customer Journey Analyticsは、オーディエンスデータをパイプラインイベントとして、またはデータレイクにも送信するフラットファイルとして送信しますか？**

Customer Journey Analyticsは、パイプラインを介してデータを RTCP にストリーミングし、このデータもデータレイクのシステムデータセットに収集されます。

+++

+++**Customer Journey Analyticsは何の ID を送信しますか？**

どの ID/名前空間ペアも [接続の設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#create-connection). 特に、「ユーザー ID」として使用するフィールドをユーザーが選択する際の手順で使用されたペアです。

+++

+++**プライマリ ID として選択されるのはどの ID ですか？**

上記を参照してください。Customer Journey Analytics「person」ごとに 1 つの ID のみを送信します。

+++

+++**RTCP はCustomer Journey Analytics・メッセージも処理するか Customer Journey Analyticsは、オーディエンス共有を通じて ID をプロファイル ID グラフに追加できますか？**

いいえ。「ユーザー」ごとに送信される ID は 1 つだけなので、RTCP はグラフエッジを使用しません。

+++

+++**毎日、毎週および毎月の更新は、何時におこなわれますか？ 毎週の更新は何曜日におこなわれますか？**

更新のタイミングは、元のオーディエンスが公開された日時に基づき、その時刻（および曜日または月曜日）に関連付けられます。

+++

+++**ユーザーは、毎日、毎週、毎月の更新時間を設定できますか？**

いいえ、ユーザーが設定することはできません。

+++


## 次の手順

* このオーディエンスを管理するには、[管理 UI](/help/components/audiences/manage.md) に移動します。
