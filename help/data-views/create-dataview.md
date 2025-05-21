---
title: データビューの作成または編集
description: データビューの作成や編集を行うために調整できるすべての設定。
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 07f9a224d43658a58779abecd6473fceb7109ef4
workflow-type: tm+mt
source-wordcount: '2125'
ht-degree: 85%

---

# データビューの作成または編集

データビューを作成するには、スキーマ要素から指標やディメンションを作成するか、標準コンポーネントを使用する必要があります。ほとんどのスキーマ要素は、ビジネスの要件に応じて、ディメンションまたは指標のいずれかになります。スキーマ要素をデータビューにドラッグすると、右側にオプションが表示され、Customer Journey Analytics でのディメンションや指標の動作を調整できます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [データビューの作成または編集](https://video.tv.adobe.com/v/35110/?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


データビューを作成または編集するには：

1. [Customer Journey Analytics](https://analytics.adobe.com) にログインし、必要に応じて **[!UICONTROL データ管理]** から **[!UICONTROL データビュー]** を選択します。
1. データビューを作成するには、「**[!UICONTROL 新しいデータビューを作成]**」を選択します。または、データビューのリストから既存のデータビューを選択して編集することもできます。


## 設定 {#configure}

新規または既存のデータビューを設定するには：

>[!BEGINTABS]

>[!TAB 標準 ]

![データビューの設定](assets/dataview-configure.png)

>[!TAB B2B edition]

![ データビュー B2B の設定 ](assets/dataview-configure-b2b.png)

>[!ENDTABS]


1. 「**[!UICONTROL 設定]**」タブを選択します（まだアクティブでない場合）。


1. [!UICONTROL 設定]、[!UICONTROL コンテナ]、[!UICONTROL カレンダー]の詳細を指定します（以下を参照）。
1. 「**[!UICONTROL 保存して続行]**」を選択して、新規または既存のデータ ビューの設定を続行します。「**[!UICONTROL 保存]**」を選択して、既存のデータビューの設定を保存します。


### 設定 {#configure-settings}


>[!CONTEXTUALHELP]
>id="dataview_externalid"
>title="外部 ID"
>abstract="外部 ID を変更すると、外部ソース（ビジネスインテリジェンスツールなど）でのデータビュー名の表示に影響する可能性があります。"


データビューの包括的な設定を提供します。

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 接続]** | このフィールドは、データビューを、1 つ以上の Adobe Experience Platform データセットを含む、以前確立した接続にリンクします。 |
| **[!UICONTROL 名前]** | 必須。データビューの名前。この値は、Analysis Workspaceの右上のドロップダウンメニューに表示されます。 |
| **[!UICONTROL 外部 ID]** | 必須。ビジネスインテリジェンスツールなどの外部ソースで使用できる、データビューの名前。デフォルトは `unspecified` です。外部 ID を指定しない場合、名前はデータビューの名前から生成され、スペースはアンダースコアに置き換えられます。 |
| **[!UICONTROL 説明]** | （オプション。アドビは、データビューの存在理由や対象者をユーザーが理解できるよう、詳細な説明を使用することを推奨します。 |

{style="table-layout:auto"}

### 互換性 {#compatibility}


>[!CONTEXTUALHELP]
>id="dataview_dataviewsinadobejourneyoptimizer"
>title="Journey Optimizer のデータビュー"
>abstract="Customer Journey Analytics には、Adobe Journey Optimizer と互換性のある接続とデータビューを使用する必要があります。デフォルトでは、この目的のために接続とデータビューが自動的に作成されます。<br/>または、このオプションを有効にして、これを Adobe Journey Optimizer レポートで使用されるデフォルトのデータビューにすることもできます。有効にすると、Journey Optimizer に必要なすべてのコンポーネントがこのデータビューに追加され、必要な Journey Optimizer データセットがすべてこのデータビューに関連付けた接続に追加されます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/integrations/ajo#connection" text="追加されるコンポーネントとデータセット。"


Customer Journey Analytics だけでなく、Adobe Journey Optimizer を使用する際に適用できる設定を提供します。

このセクションは、Journey Optimizer がプロビジョニングされている管理者にのみ表示されます。

| 設定 | 説明 |
| --- | --- |
| [!UICONTROL **Adobe Journey Optimizer のデフォルトのデータビューとして設定**] | この設定オプションは、Journey Optimizer と Customer Journey Analytics 全体のレポートを標準化します。また、Customer Journey Analytics で Adobe Journey Optimizer データのアドバンス分析を実行することもできます（Journey Optimizer で![開く](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) [!UICONTROL **CJA で分析**]&#x200B;を選択）。<p>このタイプの分析を実行するには、Journey Optimizer で Customer Journey Analytics データビューにアクセスする必要があります。<p>このオプションを有効にすると、サンドボックスの Journey Optimizer レポートで使用されるデフォルトのデータビューになります。</p><p>この設定オプションでは、自動的に次の操作を行います。</p><ul><li>Journey Optimizer で使用するために、Customer Journey Analytics の関連接続で必要なすべての Journey Optimizer データセットを設定する。</li><li>データビューに Journey Optimizer の指標とディメンションのセットを作成する（派生フィールドと計算指標を含む）。これらすべての指標とディメンションにコンテキストラベルが自動的に設定されます。</li></ul><p><p>このオプションを有効にする際は、次の点を考慮してください。 <ul><li>デフォルトのデータビューは後で変更できますが、変更すると Journey Optimizer レポートデータが変更される可能性があります。このオプションを有効にした後に無効にすることを選択した場合は、新しいデフォルトのデータビューを選択するように求められます。</li><li>Customer Journey Analytics データビューでデータセット、ディメンションまたは指標を既に手動でカスタマイズしている場合は、この設定オプションを有効にしても、手動カスタマイズはそのまま保持されます。このオプションでは、Journey Optimizer と Customer Journey Analytics 全体のレポートをさらに標準化する追加のカスタマイズを行います。また、このオプションを有効にした後に、手動でカスタマイズすることもできます。</li><li>このオプションを選択した際、データビューに関連付けられた接続は削除できません。</li></ul>詳しくは、[Adobe Journey Optimizer と Adobe Customer Journey Analytics の統合](/help/integrations/ajo.md)を参照してください。 |

{style="table-layout:auto"}

### コンテナ

データビューのコンテナの名前を指定します。コンテナ名は、[ セグメント ](/help/components/filters/filters-overview.md#Filter-containers) でよく使用されます。

| 設定 | 説明 |
| --- | --- |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL &#x200B; グローバルアカウントコンテナ名 &#x200B;]** | `Global Account` （デフォルト）。 [!UICONTROL &#x200B; グローバルアカウント &#x200B;] コンテナには、指定した期間内のグローバルアカウントのすべてのセッションとイベントが含まれます。 組織で別の用語を使用している場合は、ここでコンテナの名前を変更できます。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL &#x200B; アカウントコンテナ名 &#x200B;]** | `Account` （デフォルト）。 [!UICONTROL &#x200B; アカウント &#x200B;] コンテナには、指定した期間内のアカウントのすべてのセッションとイベントが含まれます。 組織で別の用語を使用している場合は、ここでコンテナの名前を変更できます。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL &#x200B; 商談コンテナ名 &#x200B;]** | `Opportunity` （デフォルト）。 [!UICONTROL Opportunity] コンテナには、指定した期間内の商談に関するすべてのセッションとイベントが含まれます。 組織で別の用語を使用している場合は、ここでコンテナの名前を変更できます。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}<br/>**[!UICONTROL &#x200B; 購入グループコンテナ名 &#x200B;]** | `Buying Group` （デフォルト）。 [!UICONTROL &#x200B; 購入グループ &#x200B;] コンテナには、指定した期間内の購入グループに対するすべてのセッションとイベントが含まれます。 組織で別の用語を使用している場合は、ここでコンテナの名前を変更できます。 |
| **[!UICONTROL 人物コンテナ名]** | `Person` （デフォルト）。 [!UICONTROL ユーザー]コンテナには、指定した期間内の訪問者に対するすべてのセッションとイベントが含まれます。組織で別の用語（「訪問者」や「ユーザー」など）を使用している場合は、ここでコンテナの名前を変更できます。 |
| **[!UICONTROL セッションのコンテナ名]** | `Session` （デフォルト）。 [!UICONTROL セッション]コンテナでは、特定のセッションのページインタラクション、キャンペーンまたはコンバージョンを識別できます。このコンテナの名前は、「訪問」または組織が指定したその他の用語に変更できます。 |
| **[!UICONTROL イベントのコンテナ名]** | `Event` （デフォルト）。 [!UICONTROL イベント] コンテナは、データセット内の個々のイベントを定義します。組織で異なる用語（「ヒット数」や「ページビュー数」など）を使用している場合は、ここでコンテナの名前を変更できます。 |

{style="table-layout:auto"}

### カレンダー

データビューで使用するカレンダーの形式を示します。同じ [接続](/help/connections/create-connection.md) に基づいて複数のデータビューを作成し、異なるカレンダータイプやタイムゾーンを設定できます。これらのデータビューを使用すると、異なるカレンダータイプを使用するチームが、同じ基データを使用して、それぞれのニーズに対応できます。

| 設定 | 説明 |
| --- | --- |
| [!UICONTROL **タイムゾーン**] | データを表示するタイムゾーンを選択します。夏時間を実施中のタイムゾーンを選択すると、それに合わせてデータが自動的に調整されます。時計が 1 時間前に調整される春には、1 時間の間隔があります。時計を 1 時間遅く調整する秋には、DST シフト中に 1 時間が繰り返されます。 |
| [!UICONTROL **カレンダータイプ**] | 月の週をグループ化する方法を指定します。<br>**西暦：** 標準のカレンダー形式です。四半期は月ごとにグループ化されます。<br>**4-5-4 小売：** 標準化された 4-5-4 小売カレンダー。四半期の最初の月と最後の月は 4 週間、四半期の 2 番目の月は 5 週間になります。<br>**カスタム (4-5-4)：** 4-5-4 カレンダーと同様に、年の最初の日と、「追加」週を含む年を選択できる点が異なります。<br>**カスタム (4-4-5)：**&#x200B;各四半期の最初の月と 2 番目の月は 4 週間、各四半期の最後の週は 5 週間になります。<br>**カスタム (5-4-4)：** 各四半期の最初の月は 5 週で、2 番目と 3 番目の月は 4 週で構成されます。 |
| [!UICONTROL **年の最初の月**] と [!UICONTROL **週の最初の曜日**] | 西暦カレンダータイプに対して表示されます。暦年の開始月と、各週の開始日を指定します。 |
| [!UICONTROL **現在の年の最初の日**] | カスタムのカレンダータイプに対して表示されます。現在の年の開始日を指定します。カレンダーでは、この値に基づいて各週の最初の曜日が自動的に書式設定されます。 |
| [!UICONTROL **「余分な」週が発生する年**] | ほとんどの 364 日間カレンダー（各 7 日からなる 52 週）では、毎年、余分な 1 週間が加算されるまで残りの日数が蓄積されます。この追加の週は、その年の最後の月に追加されます。余分な週を追加する年を指定します。 |

{style="table-layout:auto"}

## コンポーネント

次に、データビューのコンポーネントを設定できます。つまり、スキーマ要素から指標とディメンションを作成できます。また、標準コンポーネントも使用できます。

>[!IMPORTANT]
>
>1 つのデータビューに最大 5,000 個の指標と 5,000 個のディメンションを追加できます。

1. 「**[!UICONTROL コンポーネント]**」タブを選択します。

   ![「コンポーネント」タブ](assets/dataview-components.png)

   データセットを含む「[!UICONTROL 接続]」が左上に、その「[!UICONTROL スキーマフィールド]」が下に表示されます。既に含まれているコンポーネントは、すべてのデータビュー（イベント、人物、セッション指標、分、四半期、週のディメンションなど）に必要な（システム生成）標準コンポーネントです。アドビでは、デフォルトで&#x200B;**[!UICONTROL データを含む]**&#x200B;フィルターと&#x200B;**[!UICONTROL 非推奨ではない]**&#x200B;フィルターを適用するので、データを含み、非推奨ではないスキーマフィールドのみが表示されます。

1. ![検索アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)「**[!UICONTROL 検索スキーマ]**」フィールドを使用してスキーマ フィールドを検索するか、![フォルダーアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg) **[!UICONTROL イベントデータセット]**&#x200B;などのデータセットコレクションに移動してフィールドを検索します。<br/>または、![データアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **派生フィールドを作成**&#x200B;を使用して派生フィールドを作成することもできます。詳しくは、[派生フィールド](./derived-fields/derived-fields.md)を参照してください。

1. 特定のスキーマフィールドを見つけた場合や、派生フィールドを定義した場合は、![ハンドルアイコン](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL ページ名]**&#x200B;などのそのフィールドを左側のパネルから「指標」セクションまたは「ディメンション」セクションにドラッグします。
同じスキーマフィールドをディメンションまたは指標セクションに複数回ドラッグし、同じディメンションまたは指標を異なる方法で設定できます。例えば、右側の別の[コンポーネント設定](component-settings/overview.md)を使用して、pageName フィールドから「製品ページ」というディメンションと、「エラーページ」という別のディメンションを作成できます。
スキーマフィールドフォルダーを左パネルからドラッグすると、通常のセクションに自動的に並べ替えられます。文字列フィールドは [!UICONTROL ディメンション] セクションで終わり、数値スキーマタイプは [!UICONTROL 指標] セクションで終わります。「**[!UICONTROL すべてを追加]**」をクリックして、すべてのスキーマフィールドをそれぞれの場所に追加することもできます。

1. コンポーネントを選択します。右側に設定が表示されます。

   ![データビューコンポーネントの選択](assets/dataview-component-pagename.png)

   [コンポーネント設定](component-settings/overview.md) を使用してコンポーネントを設定します。使用可能なコンポーネント設定は、コンポーネントがディメンション／指標であるかどうか、およびスキーマデータタイプであるかどうかによって異なります。「設定」には次の項目が含まれます。

   * [[!UICONTROL アトリビューション]](component-settings/attribution.md)
   * [[!UICONTROL 動作]](component-settings/behavior.md)
   * [[!UICONTROL 書式]](component-settings/format.md)
   * [[!UICONTROL 値を含める / 除外]](component-settings/include-exclude-values.md)
   * [[!UICONTROL 指標の重複排除]](component-settings/metric-deduplication.md)
   * [[!UICONTROL 値オプションなし]](component-settings/no-value-options.md)
   * [[!UICONTROL 永続性]](component-settings/persistence.md)
   * [[!UICONTROL 値のバケット化]](component-settings/value-bucketing.md)

1. 「**[!UICONTROL 保存して続行]**」を選択して、新規または既存のデータビューの設定を続行します。「**[!UICONTROL 保存]**」を選択して、既存のデータビューの設定を保存します。

**指標またはディメンションの複製**

指標またはディメンションを複製し、特定の設定を変更することで、単一のスキーマフィールドから複数の指標またはディメンションを簡単に作成できます。右上にある指標またはディメンションの名前の下にある「[!UICONTROL 複製]」設定を選択します。新しいディメンションまたは指標を変更し、わかりやすい名前で保存します。

**スキーマフィールドまたはデータセットをフィルタリング**

左側のパネルの![フィルターアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)スキーマフィールドは、[!UICONTROL データタイプ]、[!UICONTROL データセット]、[!UICONTROL データガバナンス]、[!UICONTROL その他]の条件（[!UICONTROL データを含む]、[!UICONTROL ID である]、[!UICONTROL 非推奨ではない]）によってフィルタリングできます。

![フィールドのフィルタリング](assets/dataview-components-filter.png)

>[!TIP]
>
>コンポーネントがデータビューに適切に読み込まれず、代わりにエラーメッセージが表示される場合は、[権限の不足](../troubleshooting/lack-of-permissions.md)を参照して解決してください。



## 設定 {#dataview-settings}

1. 「**[!UICONTROL 設定]**」タブを選択します。
1. データビュー全体に適用するセグメントを設定します。 以下の [ 設定（セグメント） ](#settings-filters) を参照してください。
1. セッションのタイムアウトと指標を設定します。 以下の[セッション設定](#session-settings)を参照してください。
1. 「**[!UICONTROL 保存して続行]**」を選択して、新規または既存のデータビューの設定を続行します。「**[!UICONTROL 保存]**」を選択して、既存のデータビューの設定を保存します。

### 設定（セグメント） {#segment-settings}

データビュー全体に適用するセグメントを追加できます。 このセグメントは、Workspaceで実行するすべてのレポートに適用されます。 左側のパネルのリストから「**[!UICONTROL セグメントを追加]**」フィールドにセグメントをドラッグします。

### セッション設定

セッションの有効期限が切れてから新しいセッションが開始されるまでの間に無操作状態が続く期間を指定します。期間を指定する必要があります。オプションで、イベントに特定の指標が含まれる場合は新しいセッションを強制的に開始することもできます。詳しくは、[セッション設定](session-settings.md)を参照してください。

### データのプレビュー

データプレビューでは、（様々なコンテナについて）このデータビューのデータと接続のデータを比較します。 プレビューの割合は、過去 90 日間の接続の合計数に基づきます。

プレビューが読み込まれない場合、接続はまだバックフィル中の可能性があります。

必要な設定をすべて指定したら、「**[!UICONTROL 保存して終了]**」をクリックします。
