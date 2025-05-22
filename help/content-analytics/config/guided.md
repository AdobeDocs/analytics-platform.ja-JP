---
title: コンテンツガイド付き設定
description: オンボーディングガイド付き設定を使用したコンテンツ分析の設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 4c426b206cf4de06cbf0262f4d89787af060bb30
workflow-type: tm+mt
source-wordcount: '2653'
ht-degree: 96%

---

# コンテンツガイド付き設定

ガイド付き設定を使用すると、コンテンツ分析をすばやく簡単に設定できます。ガイド付き設定では、ウィザードを使用して、組織のコンテンツ分析を自動的に設定するための要件を設定します。**[!UICONTROL 設定]**&#x200B;画面で、新しい設定を作成するか、既存の設定を編集できます。

>[!IMPORTANT]
>
>組織のサンドボックスごとに 1 つのコンテンツ分析設定のみを持つことができます。

コンテンツ分析設定にアクセスするには

* Customer Journey Analytics のメインメニューから&#x200B;**[!UICONTROL データ管理]**／**[!UICONTROL コンテンツ分析設定]**&#x200B;を選択します。

**[!UICONTROL コンテンツ分析設定]**&#x200B;画面に、既存のコンテンツ分析設定のテーブルが表示されます。

![コンテンツ分析設定](../assets/aca-configuration-table.png)
各設定で、次の詳細を使用できます。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 名前]** | 設定の名前。 |
| **[!UICONTROL 作成者]** | 設定を作成したテクニカルアカウント。 |
| **[!UICONTROL 作成日]** | 設定が作成されたときのタイムスタンプ。 |
| **[!UICONTROL 変更日]** | 設定が最後に変更されたときのタイムスタンプ。 |
| **[!UICONTROL サンドボックス]** | コンテンツ分析が（予定されて）設定および実装される、組織内のサンドボックス。 |
| **[!UICONTROL ステータス]** | 設定のステータス。ステータスは次のようになります。<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Draft]**：設定は後で使用するのに保存され、デプロイされていません。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**：設定に失敗しました。「**[!UICONTROL 編集]**」を選択すると、失敗に関する情報を取得できます。アドビでは、失敗した実装に積極的に対処します。詳しくは、カスタマーケアにお問い合わせください。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**：設定が完了し、正常に実装されました。 |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、テーブルをカスタマイズできます。**[!UICONTROL テーブルをカスタマイズ]**&#x200B;ダイアログに表示する列を選択し、「**[!UICONTROL 適用]**」を選択して変更を適用します。

コンテンツ分析&#x200B;**[!UICONTROL 設定]**&#x200B;画面から、新しい設定を作成したり、既存の設定を編集したりできます。

新規フォルダーを作成するには：

* 「**[!UICONTROL 設定を作成]**」を選択します。このアクションにより、[ガイド付き設定ウィザード](#guided-configuration-wizard)が開きます。

既存の設定を編集するには：

* 既存のコンテンツ分析設定に対して、「![詳細](/help/assets/icons/More.svg)」を選択してから![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**&#x200B;を選択します。このアクションにより、[ガイド付き設定ウィザード](#guided-configuration-wizard)が開きます。

## ガイド付き設定ウィザード

ガイド付き設定ウィザードは、4 つのセクション（[詳細](#details)、[データ表示](#data-view)、[エクスペリエンスのキャプチャと定義](#experience-capture-and-definition)、[データ収集](#data-collection)）で構成され、それぞれ、コンテンツ分析を適切に設定および構成するのに必要な詳細情報の入力を求められます。セクション内の一部の設定は、前のセクションの設定値に依存する場合があるので、次のセクションに進む前に各セクションを完了してください。

### 詳細 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="詳細"
>abstract="接続の名前を指定します。**[!UICONTROL データビュー]**、**[!UICONTROL エクスペリエンスのキャプチャと定義]**、**[!UICONTROL データ収集]**&#x200B;の各セクションでは、コンテンツ分析が正しく設定されるように詳細を指定します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="詳細"
>abstract="このガイドでは、コンテンツ分析を設定するために必要な要件を設定します。この設定の名前を指定してください。"

<!-- markdownlint-enable MD034 -->

各設定には、一意の名前が必要です。例えば、`Example Content Analytics configuration` のように設定します。設定を保存または実装するには、名前が必須です。

![コンテンツ分析設定の詳細](../assets/aca-configuration-details.png)


### データビュー {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="データビュー"
>abstract="コンテンツ分析を設定するには、既存のデータビューを選択する必要があります。そのため、コンテンツ分析データを他のデータと結合できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="データビュー"
>abstract="コンテンツ分析データを結合する Customer Journey Analytics の既存のデータビューを選択します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="データビュー"
>abstract="コンテンツ分析データを結合する Customer Journey Analytics の既存のデータビューを選択します。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="新規データビュー"
>abstract="新しいデータビューを選択すると、そのデータビューが更新され、コンテンツ分析指標およびディメンションが含まれます。必要に応じて、関連する接続も更新され、コンテンツ分析データセットが含まれます。コンテンツ分析用に現在設定されている接続とデータビューは変更されません。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="選択したデータビューのクリーンアップ"
>abstract="コンテンツ分析用に既にプロビジョニングしているデータビューが選択されました。この既存のコンテンツ分析設定は削除され、データビューが新しい設定でプロビジョニングされます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="以前のデータビューのクリーンアップ"
>abstract="新しいデータビューが選択されました。以前に選択したデータビューのコンテンツ分析設定は削除されます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="新規データビュー"
>abstract="この設定に対して新しいデータビューを選択しました。 新しいデータビューが更新され、Content Analyticsの指標とディメンションが含まれるようになりました。 同様の指標とディメンションは、既存のデータビューから削除されます。<br/> 新しいデータビューに別の接続が関連付けられている場合、接続が更新され、Content Analytics データセットが含まれます。 なお、Content Analytics データセットは、既存の設定から削除されません。"

<!-- markdownlint-enable MD034 -->

設定では、[データビュー](/help/data-views/data-views.md)を選択する必要があります。

1. データビューを選択

   * 設定の新しいデータビューを選択するには、![データ](/help/assets/icons/Data.svg) **[!UICONTROL データビューを選択]** を使用します。

     ![データビューのコンテンツ分析設定](../assets/aca-configuration-dataview.png)

   * 設定のデータビューを変更するには、![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。

     ![データビューのコンテンツ分析設定](../assets/aca-configuration-dataview-edit.png)


   両方のシナリオで、**[!UICONTROL データビュー]**&#x200B;ダイアログが表示され、設定用のデータビューを選択できます。

   ![データビューのコンテンツ分析設定 - データビューテーブル](../assets/aca-configuration-dataview-dialog.png)

   新しい設定の場合、リストには、アクティブな設定がないサンドボックスに関連付けられているデータビューのみが表示されます。また、アクセス権を持つサンドボックスと変更する権限を持つ接続に関連付けられたデータビューのみが表示されます。

   既存の設定を編集すると、リストには、既存の設定に既に関連付けられているサンドボックス内で使用可能なデータビューのみが表示されます。

   次のアクションを実行できます。

   * 特定のデータビューを検索するには、![検索](/help/assets/icons/Search.svg) フィールドを使用します。
   * 使用可能なデータビューのリストをフィルタリングするには、「![ フィルターを表示 ](/help/assets/icons/Filter.svg)」を選択します。 [!UICONTROL 接続]、[!UICONTROL 所有者]、[!UICONTROL サンドボックス]のリストをフィルタリングできます。セグメントペインを非表示にするには、<br/>![ 非表示 ](/help/assets/icons/Filter.svg)**[!UICONTROL セグメントを非表示]** を使用します。
   * テーブルに表示する列を定義するには、「![列設定](/help/assets/icons/ColumnSetting.svg)」を選択します。**[!UICONTROL テーブルをカスタマイズ]**&#x200B;ダイアログに表示する列を選択し、「**[!UICONTROL 適用]**」を選択して変更を適用します。

1. ![SelectBox](/help/assets/icons/SelectBox.svg) で、使用するデータビューを選択します。
1. 「**[!UICONTROL 保存]**」を選択して、選択したデータビューを確定します。「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。


Customer Journey Analytics では、[データビュー](/help/data-views/data-views.md)は Customer Journey Analytics [接続](/help/connections/overview.md)に関連付けられています。また、接続は組織内のサンドボックスに基づいています。設定を保存すると、選択したデータビューに基づいて、サンドボックスの名前が「**[!UICONTROL サンドボックス]**」フィールドに自動入力されます。


### エクスペリエンスのキャプチャと定義 {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="エクスペリエンスのキャプチャと定義"
>abstract="コンテンツ分析で収集するデータにエクスペリエンスを含めるように選択できます。選択した場合、エクスペリエンスを含める URL を定義するために、正規表現とクエリパラメーターの 1 つ以上の組み合わせを定義する必要があります。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="エクスペリエンスのキャプチャと定義"
>abstract="コンテンツ分析でエクスペリエンスを収集"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="エクスペリエンスのキャプチャと定義"
>abstract="Web サイトでのコンテンツのレンダリング方法を決定するパラメーターを指定します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="エクスペリエンスのキャプチャと定義"
>abstract="有効にすると、エクスペリエンスデータが収集され、エクスペリエンス属性が生成されて、エクスペリエンスレポートが使用可能になります。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="エクスペリエンスのキャプチャと定義"
>abstract="有効にすると、エクスペリエンスデータが収集され、エクスペリエンス属性が生成されて、エクスペリエンスレポートが使用可能になります。<br><br/>現在の設定に関連付けられているタグプロパティ内のエクスペリエンスのデータ収集設定を変更するには、![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** を使用します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="エクスペリエンスのキャプチャと定義"
>abstract="Adobe Content Analytics 拡張機能でエクスペリエンスデータ収集の設定を編集する必要があります。"

<!-- markdownlint-enable MD034 -->

このセクションでは、コンテンツ分析で収集するデータにエクスペリエンスを含めるように選択できます。エクスペリエンスとは、web ページを最初に訪問したユーザーが使用した URL を使用して再現可能な、web ページ上のすべてのテキストです。

デフォルトでは、**[!UICONTROL エクスペリエンスを含める]**&#x200B;はオフになっています。選択した場合、エクスペリエンスを含める URL を定義する必要があります。

次に該当する場合にのみ、エクスペリエンスを含めることを検討します。

* ページ URL を使用して、サイト上のページを再現できる必要があります。
* 特定のユーザーが表示するテキストコンテンツは、ページ URL を使用して再現でき、Cookie やその他のパーソナライゼーションメカニズムに依存しません。

>[!IMPORTANT]
>
>[コンテンツ分析のバージョン管理](manual.md#versioning)を実装して、コンテンツ分析の対象となるエクスペリエンス（ページ）に行った変更を収集します。



#### 新しい設定 {#new-experiences-configuration}

新しい設定や実装されていない設定にエクスペリエンスを含めるには：

![コンテンツ分析設定エクスペリエンスの取り込みと定義](../assets/aca-configuration-experience.png)

1. 「**[!UICONTROL エクスペリエンスを含める]**」を有効にします。エクスペリエンスを有効にする切替スイッチは、次の影響を受けます。

   * コンテンツ分析拡張機能でのデータ収集
   * コンテンツ分析イベントデータからエクスペリエンス属性を生成するプロセス
   * Customer Journey Analytics のレポートテンプレート。

1. Web サイトでのコンテンツのレンダリング方法のパラメーターを指定します。パラメーターは、**[!UICONTROL ドメイン正規表現]**&#x200B;と&#x200B;**[!UICONTROL クエリパラメーター]**&#x200B;の 0 個以上の組み合わせです。クエリパラメーターは、ページ上のコンテンツに影響を与えるパラメーターを示します。この入力により、コンテンツ分析では、一意のエクスペリエンスを定義する際に、ページ上のコンテンツに影響を与えないパラメーターを無視できます。
   1. **[!UICONTROL ドメイン正規表現]**（例：`/^(?!.*\b(store|help|admin)\b)/`）を入力します。`/` を使用して、正規表現をエスケープする必要があります。ドメイン正規表現は、これらのパラメーターが適用される URL を示します。例えば、複数のサイトがあり、サイトごとに異なるパラメーターによってコンテンツが駆動される場合があります。クエリパラメーターがすべてのページに適用される場合、`.*` を使用してすべてのページを示すことができます。
   1. **[!UICONTROL クエリパラメーター]**&#x200B;のコンマ区切りリスト（例：`outdoors, patio, kitchen`）を指定します。
1. ドメイン正規表現とクエリパラメーターの組み合わせを削除する場合は、「**[!UICONTROL 削除]**」を選択します。
1. 正規表現とクエリパラメーターの別の組み合わせを追加する場合は、「**[!UICONTROL 正規表現を追加]**」を選択します。


#### 実装された設定 {#implemented-experiences-configuration}

実装された設定に対して、既存のエクスペリエンスを編集するか新しいエクスペリエンスを含めるには：

![コンテンツ分析設定エクスペリエンスの取り込みと定義](../assets/aca-configuration-experience-edit.png)

* 「**[!UICONTROL エクスペリエンスを含める]**」を切り替えて有効または無効にします。

   * コンテンツ分析イベントデータからエクスペリエンス属性を生成するプロセス
   * Customer Journey Analytics のレポートテンプレート。

* コンテンツ分析でのエクスペリエンスのデータ収集の設定をさらに編集するには、![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。現在の設定に関連付けられたタグプロパティの [Adobe コンテンツ分析拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)にリダイレクトされます。


### データ収集 {#onboarding-data-collection}

このセクションでは、コンテンツ分析データの収集方法を設定します。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="データ収集"
>abstract="使用するタグプロパティを定義するか、新しいタグプロパティを作成します。また、正規表現を使用して、含めるまたは除外するページとアセットを定義します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="データ収集"
>abstract="**タグプロパティの指定**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="データ収集"
>abstract="**含める／除外するページ**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="データ収集"
>abstract="コンテンツ分析のデータを収集する際に、**含める**&#x200B;または&#x200B;**除外する**&#x200B;ページを指定します"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="データ収集"
>abstract="**含める／除外するアセット**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="データ収集"
>abstract="コンテンツ分析のデータを収集する際に、**含める**&#x200B;または&#x200B;**除外する**&#x200B;アセットを指定します"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="データ収集"
>abstract="現在の設定に関連付けられたタグプロパティの Adobe コンテンツ分析拡張機能のページの設定を編集できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="データ収集"
>abstract="現在の設定に関連付けられたタグプロパティの Adobe コンテンツ分析拡張機能のアセットの設定を編集できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="タグプロパティが無効"
>abstract="コンテンツ分析拡張機能は既にアクティブです。"

<!-- markdownlint-enable MD034 -->

#### 新しい設定 {#new-configuration}

新しい設定では、既存のタグプロパティを使用するか、新しいタグプロパティを作成するかを定義する必要があります。また、正規表現を使用して、含めるまたは除外するページとアセットを定義する必要があります。

* 既存のタグプロパティを使用するには：

  ![コンテンツ分析のデータ収集の既存タグ](../assets/aca-configuration-datacollection-existingtag.png)

   1. 「**[!UICONTROL 既存のものを選択]**」を選択します。
   2. **[!UICONTROL タグプロパティ]** ドロップダウンメニューから既存のプロパティを選択します。 入力を開始して検索し、使用可能なオプションを制限できます。既に実装されている別のコンテンツ分析設定で使用されているタグプロパティは選択できません。


* 新しいタグプロパティを作成するには：

  ![コンテンツ分析のデータ収集の新しいタグ](../assets/aca-configuration-datacollection-newtag.png)

   1. 「**[!UICONTROL 新規作成]**」を選択します。
   1. 「**[!UICONTROL タグ名]**」を指定します（例：`ACA Test for Documentation`）。
   1. 「**[!UICONTROL ドメイン]**」を指定します（例：`example.com`）。

* コンテンツ分析用のデータを収集する際に、どのページを含めるか除外するかを指定します。

  **[!UICONTROL 含める／除外するページ]**&#x200B;の正規表現文字列を指定します。<br/>例：コンテンツ分析からすべてのドキュメントページを除外する `^(?!.*documentation).*`。

* コンテンツ分析用のデータを収集する際に、どのアセットを含めるか除外するかを指定します。

  **[!UICONTROL 含める／除外するアセット]**&#x200B;の正規表現文字列を指定します。<br/>例：コンテンツ分析からすべてのロゴ JPEG と SVG 画像を除外する `^(?!.*(logo\.jpg|\.svg)).*$`。

>[!IMPORTANT]
>
>[タグ拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)の代わりに [JavaScript ライブラリ](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/install/library)を使用する既存の Web SDK 実装がある場合は、新しく作成したタグプロパティから自動的に含まれる Web SDK 拡張機能を手動で削除します。
>



#### 既存の設定 {#existing-configuration}

既存の設定では、タグプロパティを編集できません。ただし、含めるまたは除外するページとアセットを編集することはできます。

* コンテンツ分析用のデータを収集する際に含めるページまたは除外するページを編集するには、**[!UICONTROL エクスペリエンス]**&#x200B;の下にある ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。現在のコンテンツ分析設定のタグプロパティに関連付けられた [Adobe コンテンツ分析拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)にリダイレクトされます。正規表現を編集して、ページを含めたり除外したりできます。変更を[公開](#publish)する必要があります。

* コンテンツ分析用のデータを収集する際に含めるアセットまたは除外するアセットを編集するには、**[!UICONTROL アセット]**&#x200B;の下にある ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。現在のコンテンツ分析設定のタグプロパティに関連付けられた [Adobe コンテンツ分析拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)にリダイレクトされます。正規表現を編集して、アセットを含めたり除外したりできます。変更を[公開](#publish)する必要があります。

### 概要 {#summary}

必要な詳細をすべて入力すると、作成または変更されたアーティファクトの詳細が概要に表示されます。

* 新しい設定を実装すると、**[!UICONTROL コンテンツ分析用の&#x200B;_設定名_を実装する準備がほとんど整いました]**&#x200B;という概要が表示されます。

* 既に実装されている設定の場合は、**[!UICONTROL コンテンツ分析用の&#x200B;_設定名_を実装しました]**&#x200B;という概要が表示されます。

![コンテンツ分析設定の概要](../assets/aca-configuration-summary.png)

### アクション {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="実装の確認"
>abstract="「**[!UICONTROL 実装]**」を選択した場合は、このワークフローで指定した入力に基づいてコンテンツ分析を設定します。コンテンツ分析に一般的に役立つ内容に基づいて、いくつかの設定がデフォルトで選択されていますが、ユーザー（データ管理者）は各アーティファクトの設定を確認し、プライバシーポリシー、契約上の権利と義務、適用法に基づく同意要件に従って設定が実装されていることを確認する必要があります。<br/><br/>この設定に関連付けられたタグライブラリを手動で公開するまで、データは収集されません。<br/><br/>画像やテキストの属性を取得するために、アドビでは、次を使用して属性を取得します。<ol><li>設定したデータ収集設定に従って、ユーザーのサイト訪問時に取得される URL。</li><li>画像がホストされる URL。</li></ol>サードパーティのサイトでホストされる画像にタグを付けないでください。"

<!-- markdownlint-enable MD034 -->

設定を作成または編集する際には、次のオプションがあります。

* **[!UICONTROL 破棄]**：設定の一環として行ったすべての変更は破棄されます。
* **[!UICONTROL 後のために保存]**：設定に行った変更が保存されます。後のステージで設定を再度参照して、さらに変更を行ったり、設定を実装したりすることができます。設定を保存するには、[!UICONTROL 名前]の値のみが必要です。
* **[!UICONTROL 実装]**：設定に行った設定または変更が保存および実装されます。![必須](/help/assets/icons/Required.svg) 必須とマークされているすべてのフィールドには適切な値を指定する必要があります。実装は次で構成されます。

   * **[!UICONTROL Customer Journey Analytics]** 設定：
      * 選択したデータビューを更新すると、コンテンツ分析のディメンションと指標が含まれます。
      * 選択したデータビューに関連付けられた接続を変更すると、コンテンツ分析イベントと属性データセットが含まれます。
      * コンテンツ分析レポートテンプレートが Workspace に追加されます。


   * **[!UICONTROL Adobe Experience Platform]** 設定：
      * コンテンツ分析イベント、アセット属性および（設定した場合）エクスペリエンス属性をモデル化するスキーマの作成。
      * コンテンツ分析イベント、アセット属性および（設定した場合）エクスペリエンス属性を収集するデータセットの作成。
      * 機能サービスを使用してコンテンツ分析イベントからコンテンツ属性を生成および更新するデータフローの作成。


   * **[!UICONTROL データ収集]**&#x200B;設定：
      * 新しいまたは既存のタグプロパティを設定すると、コンテンツ分析データ収集がサポートされます。つまり、この設定には、タグ用の Adobe コンテンツ分析拡張機能が含まれます。
      * コンテンツ分析イベント用のデータストリームが作成されます。
      * Adobe コンテンツ分析拡張機能を設定すると、コンテンツ分析イベントがコンテンツ分析用のデータストリームに送信されます。
      * タグプロパティに対して Web SDK を設定していない場合、コンテンツ分析イベントのみを送信する新しい Web SDK 設定が作成されます。
      * このタグプロパティに対して Web SDK を設定している場合、既存の Web SDK 設定は変更されません。


* **[!UICONTROL 保存]**：実装した設定に行った変更は保存され、実装が更新されます。
* **[!UICONTROL 終了]**。ガイド付き設定を終了します。実装した設定に行ったすべての変更は破棄されます。


## 公開 {#publish}

コンテンツ分析設定のデータ収集を開始するには、「**[!UICONTROL 実装]**」を選択した後に作成されたタグプロパティを[手動](manual.md)で公開する必要があります。


>[!MORELIKETHIS]
>
>[手動設定](manual.md)
>
