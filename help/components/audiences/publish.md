---
title: オーディエンスの作成と公開
description: Customer Journey Analytics からのオーディエンスの公開方法を学ぶ
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 1f21bec36f4c7d30940ed4bb95b097665a45b8ad
workflow-type: tm+mt
source-wordcount: '2320'
ht-degree: 15%

---

# オーディエンスの作成と公開 {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="更新頻度"
>abstract="オーディエンスのメンバーシップが再評価される頻度を確認します。<br/>1 回のみのオーディエンスは、1 回だけ評価されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="オーディエンスの制限"
>abstract="更新対象のオーディエンスは更新頻度に基づいて制限されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="ルックバックウィンドウを更新"
>abstract="オーディエンスの評価を行うルックバック期間（今日を基点としてカウントした日数）を定義します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="オーディエンスサイズの制限"
>abstract="オーディエンスのサイズは 2,000 万人を超えてはなりません。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="含まれる名前空間"
>abstract="このオーディエンスの ID は、以下の名前空間で構成されています。"

<!-- markdownlint-enable MD034 -->




このトピックでは、顧客のターゲティングやパーソナライゼーションのために、Customer Journey Analyticsで特定されたオーディエンスを作成してAdobe Experience Platformの [ リアルタイム顧客プロファイル ](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/home) に公開する方法について説明します。

この [ 概要 ](/help/components/audiences/audiences-overview.md) を参照して、Customer Journey Analytics オーディエンスの概念を理解してください。

## オーディエンスの作成と公開 {#create}

1. オーディエンスを作成して公開するには、次のいずれかの操作を行います。

   | 作成方法 | 詳細 |
   | --- | --- |
   | **[!UICONTROL オーディエンス]** インターフェイス内から | メイン Customer Journey Analytics メニューから **[!UICONTROL コンポーネント]**/**[!UICONTROL オーディエンス]** を選択します。 オーディエンス インターフェイスが表示されます。 「**[!UICONTROL オーディエンスを作成]**」を選択すると、[!UICONTROL  オーディエンスビルダー ] が開きます。 |
   | Analysis Workspaceのビジュアライゼーションから | Analysis Workspaceの多くのビジュアライゼーションでは、コンテキストメニューを使用してオーディエンスを作成できます。 例えば、**[!UICONTROL フリーフォームテーブル]** の項目のコンテキストメニューから [ オーディエンスを作成 ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) を選択したり、[ジャーニーキャンバス ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) のノードを選択したりできます。<p>この方法を使用すると、オーディエンスビルダーのフィルターに、選択したディメンションまたはディメンション項目があらかじめ入力されます。</p><p>次のビジュアライゼーションでは、右クリックメニューを使用してオーディエンスを作成できます。</p><ul><li>[コホートテーブル](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[フォールアウト](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[フロー](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[フリーフォームテーブル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[ジャーニー キャンバス ](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[ベン図](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**注意：** オーディエンスに計算指標を含めることはできません。 計算指標を含むオーディエンスを作成しようとしても、計算指標はオーディエンスの定義に含まれません。</p> |
   | フィルターの作成／編集 UI から | 「**[!UICONTROL このフィルターからオーディエンスを作成]**」ボックスをオンにします。この方法を使用すると、フィルターが事前に設定されます。 詳しくは、[ フィルターの作成 ](/help/components/filters/create-filters.md) を参照してください。 |

   {style="table-layout:auto"}

1. [ オーディエンスビルダー ](#audience-builder) を使用してオーディエンスを作成します。

1. [ 日付プレビュー ](#data-preview) パネルを使用してデータを解釈します。

1. 「**[!UICONTROL [!UICONTROL サンプル ID を表示]]**」を選択して、このオーディエンスの ID のサンプルを表示します。 **[!UICONTROL サンプル ID]** ダイアログでは、![ 検索 ](/help/assets/icons/Search.svg)[!UICONTROL *サンプル ID を検索*] を使用してサンプル ID を検索できます。

1. オーディエンスの設定を再度確認し、「**[!UICONTROL 公開]**」を選択します。
オーディエンスが公開されたことを示す確認メッセージが表示されます。 このオーディエンスは、1 ～ 2 分でExperience Platformに表示されます。

1. 同じメッセージ内で **[!UICONTROL AEPでオーディエンスを表示]** を選択すると、Adobe Experience Platformの [ セグメント UI](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/overview) に移動します。 詳しくは、次を参照してください。

## Audience builder

これらの設定を構成して、オーディエンスを定義または更新します。

![ 次の節で説明するオーディエンスの署名設定のスクリーンショット ](assets/create-audience.png)。

| 設定 | 説明 |
| --- | --- |
| ![データ](/help/assets/icons/Data.svg) | オーディエンスの作成に使用するデータビューを選択します。 |
| **[!UICONTROL 名前]** | オーディエンスの名前。 例：`Really Interested in Potential Car Buyers` |
| **[!UICONTROL タグ]** | 組織的な目的でオーディエンスに割り当てるタグ。 1 つ以上の既存のタグを選択するか、新しいタグを入力できます。 |
| **[!UICONTROL 説明]** | 他のオーディエンスと区別するための、オーディエンスの説明。 例：`Build an audience of really interested potential car buyers` |
| **[!UICONTROL 更新頻度]** | オーディエンスを更新する頻度。<p/>以下から選択できます <ul><li>**[!UICONTROL 1 回だけ]** オーディエンス：更新を必要としないオーディエンス（デフォルト）。 例えば、このオプションは、特定の 1 回限りのキャンペーンに役立ちます。<br/>1 回限りの日付範囲 **[!UICONTROL を指定する必要があり]** す。 ![ カレンダー ](/help/assets/icons/Calendar.svg) を使用して日付範囲を入力できます。</li><li>爽やかなオーディエンス。 選択できる項目は次のとおりです。<ul><li>**[!UICONTROL 4 時間ご]**: 4 時間ごとに更新されるオーディエンス。</li><li>**[!UICONTROL 毎日]**：毎日更新されるオーディエンス</li><li>**[!UICONTROL 毎週]**：毎週更新されるオーディエンス。</li><li>**[!UICONTROL 毎月]**：毎月更新するオーディエンス</li></ul></li>オーディエンスを更新する場合は、次を指定する必要があります。<ul><li>**[!UICONTROL ルックバックウィンドウを更新]**. オーディエンスが評価される、今日からのルックバック日数を定義します。 オプションから選択するか、カスタム時間を定義できます。 最大 90 日です。</li><li>**[!UICONTROL 有効期限]**：オーディエンスが更新を停止するタイミングを定義します。 ![ カレンダー ](/help/assets/icons/Calendar.svg) を使用して日付を選択できます。 デフォルトは作成日の 1 年後です。有効期限が切れるオーディエンスは、予定レポートの有効期限が切れる場合と同様に扱われます。 管理者は、オーディエンスの有効期限が切れる 1 か月前にメールを受け取ります。</li></ul> Customer Journey Analyticsの使用権限に応じて、オーディエンスの更新回数には 75 から 150 の制限があります。</li></ul> |
| **[!UICONTROL フィルター]** | フィルターは、オーディエンスに対する主な入力です。左側の ![ セグメント化 ](/help/assets/icons/Segmentation.svg)**[!UICONTROL フィルター]** パネルから 1 つ以上のフィルターをフィルター領域にドラッグ&amp;ドロップします。 ![ 検索 ](/help/assets/icons/Search.svg)[!UICONTROL *検索フィルター*] を使用して、フィルターを検索できます。 最大 20 のフィルターを追加できます。フィルターは、**[!UICONTROL And]** または **[!UICONTROL Or]** 演算子と結合させることができます。<p>Analysis Workspaceのビジュアライゼーション（フリーフォームテーブルやジャーニーキャンバスなど）からオーディエンスを作成する場合、パネルや列に適用されているフィルターはすべて保持されます。 自動的に適用されたフィルターを削除できます。</p> |
| **[!UICONTROL データのプレビュー]** | 「![ 情報 ](/help/assets/icons/Info.svg)」を選択すると、選択した日付範囲の [ データプレビュー ](#data-preview) の表示/非表示が切り替わります。 |

## データのプレビュー

データのプレビューパネルには、次の情報が表示されます。

| 要素 | 説明 |
| --- | --- |
| **[!UICONTROL 人物合計]** | このオーディエンスの合計人数の概要。最大サイズは 2,000 万人です。 オーディエンスが 2,000 万人を超える場合は、公開する前にオーディエンスサイズを小さくする必要があります。 |
| **[!UICONTROL オーディエンスサイズの制限]** | このオーディエンスが 2,000 万の上限からどの程度離れているかを示すビジュアライゼーション。 |
| **[!UICONTROL オーディエンス再来訪の見込み]** | この値を使用して、サイト、モバイルアプリまたは他のチャネルに戻ってくる、このオーディエンスのユーザーを再ターゲットに設定できます。<p>再来訪の可能性がある顧客の推定数に対して、期間 ]****[!UICONTROL  次の 7 日間 **[!UICONTROL 、次の 2 週間]** または **[!UICONTROL 次の月]**）を選択できます。 |
| **[!UICONTROL 再来訪する見込み]** | この数により、選択した期間内の再訪問者の推定数が表示されます。 この数は、このオーディエンスの過去のチャーンレートを使用して予測されます。 |
| **[!UICONTROL 指標をプレビュー]** | 特定の指標を選択して、定義したオーディエンスに基づいて、その指標のデータがどのように生成されているかを確認できます。  各プレビュー指標には、オーディエンスに基づく指標の合計が表示されます。 データビューで定義された、指標の全体的な合計に対するオーディエンスベースの指標の割合。 例えば、381 人（選択した指標）は、オーディエンス定義の結果であり、データビューで使用可能な合計ユーザーの 5% になります。 データ表示で使用できる任意の指標を選択できます。 |
| **[!UICONTROL 含まれる名前空間]** | オーディエンス内のユーザーに関連付けられている特定の名前空間。例としては、ECID、CRM ID、メールアドレスなどがあります。 |
| **[!UICONTROL サンドボックス]** | このオーディエンスが格納されている [Experience Platform サンドボックス](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home)。このオーディエンスを Platform に公開すると、このサンドボックスの範囲内でのみオーディエンスを操作できます。 |

{style="table-layout:auto"}

## オーディエンスを作成して公開した後はどうなりますか。 {#after-audience-created}

Customer Journey Analyticsでオーディエンスを作成して公開すると、そのオーディエンスをExperience Platformで使用できるようになります。 Adobe Experience Platform ストリーミングセグメントは、組織がストリーミングセグメント化用に設定されている場合にのみ作成されます。

* Platform のオーディエンスは、Customer Journey Analytics オーディエンスと同じ名前および説明を共有します。 オーディエンスが一意になるように、名前にCustomer Journey Analytics オーディエンス ID が追加されます。
* Customer Journey Analyticsでオーディエンスの名前や説明に加えられた変更は、すべてExperience Platformに反映されます。
* Customer Journey Analyticsでオーディエンスを削除しても、オーディエンスのプロファイルメンバーシップが期限切れになるまで、オーディエンスは引き続きExperience Platformで使用できます。 プロファイルメンバーシップは、1 回限りのオーディエンスの場合は 420 日後、繰り返しオーディエンスの場合は 16 日後に有効期限が切れます。

## 待ち時間に関する考慮事項 {#latency}

オーディエンスの公開前、公開中および公開後の複数の時点で、待ち時間が発生する可能性があります。 発生し得る待ち時間の概要は次のとおりです。

![ この節で説明しているように、オーディエンスの公開に待ち時間が発生します。](assets/latency-diagram.svg)

|  | 待ち時間の時点 | 待ち時間の継続時間 |
| --- | --- | --- |
| 表示しない | Adobe Analyticsから Analytics ソースコネクタ（A4T） | 最大 30 分 |
| 1 | （Analytics ソースコネクタまたはその他のソースから）データレイクへのデータ取り込み | 最大 90 分 |
| 2 | Experience Platform Data Lake からCustomer Journey Analyticsへのデータ取り込み | 最大 90 分 |
| 3 | ストリーミングセグメントの自動作成やセグメントでのデータの受信準備など、リアルタイム顧客プロファイルへのオーディエンスの公開。 | 数秒 |
| 4 | オーディエンスの更新頻度 | <ul><li>1 回の更新（5 分未満の待ち時間）</li><li>4 時間ごと、日次、週次、月次の更新（待ち時間は更新率と密接に関連しています）。 |
| 5 | Adobe Experience Platformでの宛先の作成：新しいセグメントのアクティブ化 | 1～2 時間 |

{style="table-layout:auto"}

## Experience PlatformでのCustomer Journey Analytics オーディエンスの使用 {#audiences-aep}

Customer Journey Analyticsは、公開済みのオーディエンスから名前空間と ID のすべての組み合わせを取得して、Real-Time Customer Data Platformにストリーミングします。 Customer Journey Analyticsは、接続設定時に [!UICONTROL  ユーザー ID] として何が選択されたかに応じてプライマリ ID を設定したうえで、オーディエンスをExperience Platformに送信します。

次に、Real-Time Customer Data Platformは、各名前空間/ID の組み合わせを調べ、その組み合わせが含まれている可能性のあるプロファイルを探します。 プロファイルは、基本的に、リンクされた名前空間、ID およびデバイスのクラスターです。プロファイルが見つかると、名前空間と ID がこのプロファイル内の他の ID にセグメントメンバーシップ属性として追加されます。 例えば、すべてのデバイス <user@adobe.com> チャネルにわたってターゲットを設定できます。 プロファイルが見つからない場合は、新しく作成されます。

Platform でCustomer Journey Analytics オーディエンスを表示するには：

1. 左側のパネルで **[!UICONTROL 顧客]** を展開し、「**[!UICONTROL オーディエンス]**」を選択します。<!-- is there a folder called "Customer Journey Analytics? -->

1. 「**[!UICONTROL 参照]** タブを選択します。

1. Customer Journey Analyticsから公開したオーディエンスを見つけるには、次のいずれかの操作を行います。

   ![ 左パネルの「オーディエンス」オプション ](assets/aep-audiences.png)

   * **[!UICONTROL オリジン]** 列でテーブルを並べ替えると、[!UICONTROL **Customer Journey Analytics**] をオリジンとして示すオーディエンスが表示されます。

   * ![ 接触チャネル ](/help/assets/icons/Filter.svg) に対して **[!UICONTROL フィルター]** を適用し、**[!UICONTROL Customer Journey Analytics]** を選択します。

   * ![ 検索 ](/help/assets/icons/Search.svg) 検索フィールドを使用します。

Platform でのオーディエンスの使用について詳しくは、Experience Platform ドキュメントの [ セグメントビルダー UI ガイド [ の ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) オーディエンス ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) の節を参照してください。

### オーディエンス数の不一致について

Customer Journey AnalyticsとReal-Time Customer Data Platformの間では、オーディエンス数の不一致が発生する場合があります。

<!--
![Infographic on audience differences between Customer Journey Analytics and Real-Time CDP.](/help/components/audiences/assets/infographic-cja-rtcdp.png)
-->

#### 推定数と決定論的数

以下に説明するように、オーディエンスメンバーシップ番号の計算方法は 2 つのアプリで異なります。

* **Customer Journey Analytics**: Customer Journey Analyticsの **[!UICONTROL 合計人数]** 指標は推定値です。 つまり、カウントはオーディエンスのルールに基づく予測であり、更新間隔によって変わる可能性があります。
* **Real-Time Customer Data Platform**: Real-Time Customer Data Platformの数は、毎日の評価ジョブに基づいて決定的であり、オーディエンスがオーディエンスポータルへの公開を完了した時点で固定されます。

#### 公開間隔と公開率

オーディエンスは、1 秒あたり 1,500 レコード（RPS）の割合でReal-Time Customer Data Platformに公開されます。 例えば、2,000 万人のオーディエンスが完全に公開されるまでに約 3.7 時間かかります（20M/1500 RPS/1 時間あたり 3,600 秒）。 この間、2 つのアプリ間でオーディエンスメンバーシップに違いが生じる可能性があります。

#### プロファイルの断片化

Customer Journey Analyticsから読み込まれたプロファイルが既にReal-Time Customer Data Platformに存在する場合、それらは新しいプロファイルとしてカウントされません。 これにより、Real-Time Customer Data Platformでプロファイル数が予想より少なくなる可能性があります。

#### バッチとストリーミングオーディエンスの比較

Customer Journey Analytics オーディエンスは毎日のバッチ評価ジョブに含まれず、次の公開間隔まで固定されます。 これに対し、Real-Time Customer Data Platformの他のバッチオーディエンスは、24 時間ごとに再評価されます。

### 重要な留意点

* **Customer Journey Analyticsの推定カウント**:Customer Journey Analyticsの **[!UICONTROL 合計人数]** カウントは推定値であり、ストリーミングデータや ID の動作によって異なる可能性があることを理解しておきます。
* **Real-Time Customer Data Platformにおける決定論的なカウント**:Real-Time Customer Data Platformのカウントは固定されており、次の公開間隔まで変化しません。
* **プロファイルの断片化**:Customer Journey Analyticsから読み込む際、Real-Time Customer Data Platform内の既存のプロファイルが新しいプロファイル数の要因となっている可能性があることに注意してください。

これらの側面を明確に区別することで、Customer Journey AnalyticsとReal-Time Customer Data Platform全体でオーディエンスデータをより深く理解し管理できます。—>

## よくある質問（FAQ） {#faq}

オーディエンスの投稿に関するよくある質問です。

+++**Customer Journey Analyticsでユーザーがオーディエンスのメンバーでなくなった場合はどうなりますか？**

この場合、exit イベントがCustomer Journey AnalyticsからExperience Platformに送信されます。

+++

+++**Customer Journey Analyticsでオーディエンスを削除するとどうなりますか？**

Customer Journey Analytics オーディエンスが削除されると、そのオーディエンスはExperience Platform UI に表示されなくなります。 ただし、そのオーディエンスに関連付けられたプロファイルは、Experience Platformでは削除されません。

+++

+++**対応するプロファイルがReal-Time Customer Data Platformに存在しない場合、新しいプロファイルは作成されますか？**

はい、作成されます。

+++

+++**Customer Journey Analyticsは、オーディエンスデータをパイプラインイベントとして送信しますか、それともデータレイクにも送られるフラットファイルとして送信しますか？**

Customer Journey Analyticsは、パイプラインを介してデータをReal-Time Customer Data Platformにストリーミングし、このデータもデータレイクのシステムデータセットに収集されます。

+++

+++**Customer Journey Analyticsはどのような ID を送信しますか？**

[ 接続設定 ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection) で指定された ID/名前空間ペアのいずれかです。 特に、ユーザーがユーザー ID として使用するフィールドを選択する手順で使用されたペアです。

+++

+++**プライマリ ID として選択されるのはどの ID ですか？**

上記を参照してください。Customer Journey Analytics ユーザーごとに 1 つの ID のみが送信されます。

+++

+++**Real-Time Customer Data PlatformはCustomer Journey Analytics メッセージも処理しますか？ Customer Journey Analyticsでは、オーディエンス共有を通じて ID をプロファイル ID グラフに追加できますか？**

いいえ。1 人のユーザーにつき 1 つの ID のみが送信されるので、Real-Time Customer Data Platformが使用するグラフエッジはありません。

+++

+++**毎日、毎週、毎月の更新は何時に行われますか？ 毎週更新は何曜日に実行されますか？**

更新のタイミングは、元のオーディエンスが公開された日時と、その日時（および曜日または月）に固定されます。

+++

+++**日次、週次、月次の更新時間を設定できますか？**

いいえ。ユーザーは更新時間を設定できません。

+++


## 次の手順

* このオーディエンスを管理するには、[管理 UI](/help/components/audiences/manage.md) に移動します。
