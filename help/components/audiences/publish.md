---
title: オーディエンスを作成してリアルタイム顧客プロファイルに公開する
description: Customer Journey Analytics からのオーディエンスの公開方法を学ぶ
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: d903745e105edb11ef6f43b6137e1e03d43e5e07
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 52%

---

# オーディエンスの作成と公開

このトピックでは、Customer Journey Analyticsで特定されたオーディエンスをAdobe Experience Platformの [ リアルタイム顧客プロファイル ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja) に作成して公開し、顧客のターゲティングやパーソナライズ機能を実現する方法について説明します。

この [ 概要 ](/help/components/audiences/audiences-overview.md) を参照して、Customer Journey Analyticsオーディエンスの概念を理解してください。

## オーディエンスの作成と公開 {#create}

1. オーディエンスの作成と公開を開始するには、次のいずれかの操作を行います。

   | 作成方法 | 詳細 |
   | --- | --- |
   | メイン&#x200B;**[!UICONTROL コンポーネント]／[!UICONTROL オーディエンス]**&#x200B;メニューから | Audiences Manager ページが開きます。「**[!UICONTROL オーディエンスを作成]**」をクリックすると、[!UICONTROL オーディエンスビルダー]が開きます。 |
   | フリーフォームテーブル内から | フリーフォームテーブルの項目を右クリックし、「**[!UICONTROL 選択からオーディエンスを作成]**」を選択します。 この方法を使用すると、フィルターに、テーブルで選択したディメンションまたはディメンション項目があらかじめ入力されます。 |
   | フィルターの作成／編集 UI から | 「**[!UICONTROL このフィルターからオーディエンスを作成]**」ボックスをオンにします。この方法を使用すると、フィルターが事前に設定されます。 |

   {style="table-layout:auto"}

   <!-- add beneath the Freeform table row above: | From within a Journey canvas visualization | Right-click a node in a Journey canvas visualization and select **[!UICONTROL Create audience]**. Using this method pre-populates the filter with the dimension or dimension item you selected in the table. | -->

1. オーディエンスを構築します。

   オーディエンスを公開する前に、これらの設定を行います。

   ![ 次の節で説明するオーディエンスの署名設定のスクリーンショット ](assets/create-audience.png)。

   | 設定 | 説明 |
   | --- | --- |
   | [!UICONTROL 名前] | オーディエンスの名前。 |
   | [!UICONTROL タグ] | 組織的な目的でオーディエンスに割り当てるタグ。既存のタグを使用するか、新しいタグを入力できます。 |
   | [!UICONTROL 説明] | 他のオーディエンスと区別するために、オーディエンスに関する適切な説明を追加します。 |
   | [!UICONTROL 更新頻度] | オーディエンスを更新する頻度。<ul><li>更新を必要としない 1 回限りのオーディエンス（デフォルト）の作成を選択できます。これは、特定の 1 回限りのキャンペーンなどに役立ちます。</li><li>その他の更新間隔を選択できます。4 時間の更新頻度の場合、Customer Journey Analyticsの使用権限に応じてオーディエンスの更新回数に 75 から 150 の制限があります。</li></ul> |
   | 有効期限 | オーディエンスが更新を停止したとき。デフォルトは作成日の 1 年後です。有効期限が近づいたオーディエンスは、予定レポートの有効期限が近づいた場合と同様に扱われます。管理者は、オーディエンスの期限が切れる 1 か月前にメールを受け取ります。 |
   | ルックバックウィンドウを更新 | このオーディエンスの作成時にデータウィンドウ内でどのくらい遡るかを指定します。最大 90 日です。 |
   | [!UICONTROL 1 回限りの日付範囲] | 1 回限りのオーディエンスを公開する日付範囲。 |
   | [!UICONTROL フィルター] | フィルターは、オーディエンスに対する主な入力です。最大 20 のフィルターを追加できます。これらのフィルターは、`And` または `Or` 演算子と結合させることができます。 |
   | [!UICONTROL サンプル ID を表示] | このオーディエンスの ID の例。サンプル ID を検索するには、検索バーを使用します。 |

   {style="table-layout:auto"}

1. データのプレビューを解釈します。

   オーディエンスのプレビューが右側のパネルに表示されます。作成したオーディエンスの要約分析が可能になります。

   ![ オーディエンスの要約分析を示すデータプレビューのスクリーンショット。](assets/data-preview.png)

   | プレビュー設定 | 説明 |
   | --- | --- |
   | [!UICONTROL データのプレビュー]ウィンドウ | オーディエンスの日付範囲。 |
   | [!UICONTROL 人物合計] | このオーディエンスの合計人数の概要。人数は 2,000 万人になることもあります。オーディエンスが 2,000 万人を超える場合は、オーディエンスを公開する前にサイズを小さくする必要があります。 |
   | [!UICONTROL オーディエンスサイズの制限] | このオーディエンスが 2,000 万の上限からどの程度離れているかを示します。 |
   | [!UICONTROL オーディエンス再来訪の見込み] | この設定は、サイト、モバイルアプリまたはその他のチャネル（つまり、このデータセットに再び表示される）に戻る、このオーディエンスの顧客をリターゲティングする場合に役立ちます。 <p>ここでは、再来訪の可能性がある顧客の推定数に対して期間（7 日間、次の 2 週間、次の月）を選択できます。 |
   | [!UICONTROL 再来訪する見込み] | この数により、ドロップダウンリストから選択した期間内の再訪問者の推定数が表示されます。このオーディエンスの過去のチャーンレートを調べて、この数を予測します。 |
   | [!UICONTROL 指標をプレビュー] | この設定を使用すると、特定の指標を調べて、このオーディエンスがこの指標（「[!UICONTROL 売上高]または「[!UICONTROL サイトでの平均時間]」など）に対して不相応な貢献を行っているかどうかを確認できます。指標の集計数と、指標が表す合計のパーセンテージが表示されます。データ表示で使用できる任意の指標を選択できます。 |
   | [!UICONTROL 含まれる名前空間] | オーディエンス内のユーザーに関連付けられている特定の名前空間。例としては、ECID、CRM ID、メールアドレスなどがあります。 |
   | [!UICONTROL サンドボックス] | このオーディエンスが格納されている [Experience Platform サンドボックス](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)。このオーディエンスを Platform に公開すると、このサンドボックスの範囲内でのみ操作できます。 |

   {style="table-layout:auto"}

1. オーディエンスの設定を再度確認し、「**[!UICONTROL 公開]**」をクリックします。

   すべてが正常に動作した場合は、オーディエンスが公開されたことを示す確認メッセージが表示されます。このオーディエンスは、1 ～ 2 分で Experience Platform に表示されます。（何百万人ものメンバーを持つオーディエンスの場合でも、所要時間は 5 分未満です。）

1. 同じメッセージ内で「**[!UICONTROL AEP でのオーディエンスの表示]**」をクリックすると、Adobe Experience Platform の [セグメント UI](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja) に移動します。詳しくは、次を参照してください。

## オーディエンスを作成して公開した後はどうなりますか。 {#after-audience-created}

Customer Journey Analyticsでオーディエンスを作成して公開すると、そのオーディエンスをExperience Platformで使用できるようになります。 Adobe Experience Platform ストリーミングセグメントは、組織がストリーミングセグメント化用に設定されている場合にのみ作成されます。

* Platform のオーディエンスは、Customer Journey Analyticsオーディエンスと同じ名前/説明を共有しますが、一意になるように、名前にCustomer Journey Analyticsオーディエンス ID が追加されます。
* Customer Journey Analyticsでオーディエンスの名前や説明に加えられた変更は、すべて Platform に反映されます。
* Platform でオーディエンスが削除されても、そのオーディエンスはCustomer Journey Analyticsで引き続き使用できます。

## 待ち時間に関する考慮事項 {#latency}

オーディエンスの公開前、公開中および公開後の複数の時点で、待ち時間が発生する可能性があります。 発生し得る待ち時間の概要は次のとおりです。

![ この節で説明しているように、オーディエンスの公開に待ち時間が発生します。](assets/latency-diagram.svg)

| # | 待ち時間の時点 | 待ち時間の継続時間 |
| --- | --- | --- |
| 表示しない | Adobe Analyticsから Analytics ソースコネクタ（A4T） | 最大 30 分 |
| 1 | （Analytics ソースコネクタまたはその他のソースから）データレイクへのデータ取り込み | 最大 90 分 |
| 2 | Experience PlatformデータレイクからCustomer Journey Analyticsへのデータ取り込み | 最大 90 分 |
| 3 | ストリーミングセグメントの自動作成やセグメントでのデータの受信準備など、リアルタイム顧客プロファイルへのオーディエンスの公開。 | 数秒 |
| 4 | オーディエンスの更新頻度 | <ul><li>1 回の更新（5 分未満の待ち時間）</li><li>4 時間ごと、日次、週次、月次の更新（待ち時間は更新率と密接に関連しています）。 |
| 5 | Adobe Experience Platformでの宛先の作成：新しいセグメントのアクティブ化 | 1～2 時間 |

{style="table-layout:auto"}

## Experience PlatformでのCustomer Journey Analyticsオーディエンスの使用 {#audiences-aep}

Customer Journey Analyticsは、公開済みのオーディエンスから名前空間と ID のすべての組み合わせを取得して、それらをリアルタイム顧客プロファイル（RTCP）にストリーミングします。 Customer Journey Analyticsは、Experience Platformの設定時に [!UICONTROL  ユーザー ID] として何が選択されたかに応じてプライマリ ID を設定したうえで、オーディエンスを接続に送信します。

次に、RTCP は、各名前空間／ID の組み合わせを調べ、その組み合わせが含まれている可能性のあるプロファイルを探します。プロファイルは、基本的に、リンクされた名前空間、ID およびデバイスのクラスターです。プロファイルが見つかると、名前空間と ID がこのプロファイル内の他の ID にセグメントメンバーシップ属性として追加されます。 例えば、すべてのデバイス <user@adobe.com> チャネルにわたってターゲットを設定できます。 プロファイルが見つからない場合は、新しく作成されます。

Platform でCustomer Journey Analyticsオーディエンスを表示するには：

>[!AVAILABILITY]
>
>次の手順で説明されている機能は、リリースの限定的テスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 これらの手順が環境に表示される手順と一致しない場合は、代わりに次の手順を使用します。[!UICONTROL **セグメント**]/[!UICONTROL **セグメントの作成**]/[!UICONTROL **オーディエンス**] タブ/[!UICONTROL **CJA オーディエンス**] に移動します。
>
>機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsリリースプロセスについて詳しくは、[Customer Journey Analytics機能リリース ](/help/release-notes/releases.md) を参照してください。

1. 左側のパネルで [!UICONTROL **顧客**] を展開し、「[!UICONTROL **オーディエンス**]」を選択します。<!-- is there a folder called "Customer Journey Analytics? -->

1. 「[!UICONTROL **参照**] タブを選択します。

   ![ 左パネルの「オーディエンス」オプション ](assets/audiences-aep.png)

1. Customer Journey Analyticsから公開したオーディエンスを見つけるには、次のいずれかの操作を行います。

   * [!UICONTROL **オリジン**] 列でテーブルを並べ替えると、[!UICONTROL **Customer Journey Analytics**] をオリジンとして示すオーディエンスが表示されます。

   * フィルターアイコンを選択します。

   * 検索フィールドを使用します。

Platform でのオーディエンスの使用について詳しくは、Experience Platformドキュメントの [ セグメントビルダー UI ガイド [ の ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=ja) オーディエンス ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#audiences) の節を参照してください。


## よくある質問（FAQ） {#faq}

オーディエンスの投稿に関するよくある質問です。

+++**Customer Journey Analyticsでユーザーがオーディエンスのメンバーでなくなった場合はどうなりますか？**

この場合、exit イベントがCustomer Journey AnalyticsからExperience Platformに送信されます。

+++

+++**Customer Journey Analyticsでオーディエンスを削除するとどうなりますか？**

Customer Journey Analyticsオーディエンスが削除されると、そのオーディエンスはExperience PlatformUI に表示されなくなります。 ただし、そのオーディエンスに関連付けられたプロファイルは、実際には Platform では削除されません。

+++

+++**対応するプロファイルが RTCDP に存在しない場合は、新しいプロファイルが作成されますか？**

はい、作成されます。

+++

+++**Customer Journey Analyticsは、オーディエンスデータをパイプラインイベント、またはデータレイクにも送られるフラットファイルとして送信しますか？**

Customer Journey Analyticsはパイプラインを介してデータを RTCP にストリーミングし、このデータもデータレイクのシステムデータセットに収集されます。

+++

+++**Customer Journey Analyticsはどのような ID を送信しますか？**

[ 接続設定 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja#create-connection) で指定された ID/名前空間ペアのいずれかです。 特に、「ユーザー ID」として使用するフィールドをユーザーが選択する際の手順で使用されたペアです。

+++

+++**プライマリ ID として選択されるのはどの ID ですか？**

上記を参照してください。Customer Journey Analytics「ユーザー」ごとに 1 つの ID のみを送信します。

+++

+++**RTCP はCustomer Journey Analyticsメッセージも処理しますか？ Customer Journey Analyticsでは、オーディエンス共有を通じて ID をプロファイル ID グラフに追加できますか？**

いいえ。「ユーザー」ごとに送信される ID は 1 つだけなので、RTCP はグラフエッジを使用しません。

+++

+++**毎日、毎週、毎月の更新は何時に行われますか？ 毎週更新は何曜日に実行されますか？**

更新のタイミングは、元のオーディエンスが公開された日時と、その日時（および曜日または月）に固定されます。

+++

+++**日別、週別、月別の更新時間をユーザーが設定できますか？**

いいえ。ユーザーが設定することはできません。

+++


## 次の手順

* このオーディエンスを管理するには、[管理 UI](/help/components/audiences/manage.md) に移動します。
