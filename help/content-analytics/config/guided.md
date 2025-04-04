---
title: Content Analytics ガイド付き設定
description: オンボーディングガイド付き設定を使用した Content Analytics の設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 6f077ada9df1604b86fde21aa6b11b12160aeaa7
workflow-type: tm+mt
source-wordcount: '2493'
ht-degree: 24%

---

# Content Analytics ガイド付き設定

{{release-limited-testing}}


ガイド付き設定を使用すると、コンテンツ分析をすばやく簡単に設定できます。 ガイド付き設定では、ウィザードを使用して、組織のコンテンツ分析を自動的に設定するための要件を設定します。 **[!UICONTROL 設定]** 画面で、新しい設定を作成するか、既存の設定を編集できます。

>[!IMPORTANT]
>
>組織のサンドボックスごとに 1 つの Content Analytics 設定のみを持つことができます。

コンテンツ分析設定にアクセスするには

* Customer Journey Analyticsのメインメニューから **[!UICONTROL データ管理]**/**[!UICONTROL Content Analytics設定]** を選択します。

**[!UICONTROL Content Analytics設定]** 画面に、既存のContent Analytics設定のテーブルが表示されます。

![Content Analytics 設定 ](../assets/aca-configuration-table.png)
各設定で、次の詳細を使用できます。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 名前]** | 設定の名前。 |
| **[!UICONTROL 作成者]** | 設定を作成したテクニカルアカウント。 |
| **[!UICONTROL 作成日]** | 設定が作成されたときのタイムスタンプ。 |
| **[!UICONTROL 変更日]** | 設定が最後に変更されたときのタイムスタンプ。 |
| **[!UICONTROL サンドボックス]** | コンテンツ分析が（予定されて）設定および実装される、組織内のサンドボックス。 |
| **[!UICONTROL ステータス]** | 設定のステータス。 ステータスは次のようになります。<br/>![StatusGray](/help/assets/icons/StatusGray.svg)**[!UICONTROL Draft]**：設定は後で使用するために保存され、デプロイされていません。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**：設定に失敗しました。 「**[!UICONTROL 編集]**」を選択すると、エラーに関する情報を取得できます。 Adobeは、失敗した実装にプロアクティブに対処します。 詳しくは、カスタマーケアにお問い合わせください。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg)**[!UICONTROL Complete]**：設定が完了し、正常に実装されました。 |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、テーブルをカスタマイズできます。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログに表示する列を選択し、「**[!UICONTROL 適用]** を選択して変更を適用します。

コンテンツ分析 **[!UICONTROL 設定]** 画面から、新しい設定を作成したり、既存の設定を編集したりできます。

新しい設定を作成するには：

* **[!UICONTROL 設定を作成]** を選択します。 このアクションにより、[ ガイド付き設定ウィザード ](#guided-configuration-wizard) が開きます。

既存の設定を編集するには：

* 既存のコンテンツ分析設定に対して、![ 詳細 ](/help/assets/icons/More.svg) を選択してから ![ 編集 ](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。 このアクションにより、[ ガイド付き設定ウィザード ](#guided-configuration-wizard) が開きます。

## ガイド付き設定ウィザード

ガイド付き設定ウィザードは、4 つのセクション（[ 詳細 ](#details)、[ データビュー ](#data-view)、[ エクスペリエンスキャプチャと定義 ](#experience-capture-and-definition)、[ データ収集 ](#data-collection)）で構成され、それぞれがContent Analyticsの適切な設定に必要な詳細を求めます。 セクション内の一部の設定は、前のセクションの設定値に依存する場合があるので、次のセクションに進む前に各セクションを完了してください。

### 詳細 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="詳細"
>abstract="接続の名前を指定します。**[!UICONTROL データビュー]**、**[!UICONTROL エクスペリエンスのキャプチャと定義]**、**[!UICONTROL データ収集]**&#x200B;の各セクションでは、コンテンツ分析が正しく設定されるように詳細を指定します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="詳細"
>abstract="このガイドでは、コンテンツ分析を設定するために必要な要件を設定します。この設定の名前を指定してください"

<!-- markdownlint-enable MD034 -->

各設定には、一意の名前が必要です。 たとえば、`Example Content Analytics configuration` のように設定します。設定を保存または実装するには、この名前が必要です。

![Content Analytics 設定の詳細 ](../assets/aca-configuration-details.png)


### データビュー {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="データビュー"
>abstract="コンテンツ分析の設定には、既存のデータビューを選択する必要があります。 そのため、コンテンツ分析データを他のデータと結合できます。"

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
>title="新しいデータビュー"
>abstract="新しいデータビューを選択すると、そのデータビューが更新され、コンテンツ分析指標およびディメンションが含まれます。必要に応じて、関連付けられた接続も更新され、コンテンツ分析データセットが含まれます。コンテンツ分析用に現在設定されている接続とデータビューは変更されません。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="選択したデータビューのクリーンアップ"
>abstract="コンテンツ分析用に既にプロビジョニングしているデータビューが選択されました。この既存のコンテンツ分析設定は削除され、データビューが新しい設定でプロビジョニングされます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="以前のデータビューのクリーンアップ"
>abstract="新しいデータビューが選択されました。以前に選択したデータビューのコンテンツ分析設定は削除されます。"

<!-- markdownlint-enable MD034 -->

設定では、[ データビュー ](/help/data-views/data-views.md) を選択する必要があります。

1. データビューを選択

   * 設定用に新しいデータビューを選択するには、![ データ ](/help/assets/icons/Data.svg) **[!UICONTROL データビューを選択]** を使用します。

     ![ データビューの Content Analytics 設定 ](../assets/aca-configuration-dataview.png)

   * 設定のデータビューを変更するには、![ 編集 ](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。

     ![ データビューの Content Analytics 設定 ](../assets/aca-configuration-dataview-edit.png)


   どちらのシナリオでも、**[!UICONTROL データビュー]** ダイアログが表示され、設定用のデータビューを選択できます。

   ![ データビューのContent Analytics設定 – データビューテーブル ](../assets/aca-configuration-dataview-dialog.png)

   新しい設定の場合、リストには、アクティブな設定がないサンドボックスに関連付けられたデータビューのみが表示されます。 また、自分がアクセス権を持つサンドボックスと、変更する権限を持つ接続に関連付けられたデータビューのみが表示されます。

   既存の設定を編集すると、リストには、既存の設定に既に関連付けられているサンドボックス内で使用可能なデータビューのみが表示されます。

   次のアクションを実行できます。

   * 特定のデータビューを検索するには、「![ 検索 ](/help/assets/icons/Search.svg)」フィールドを使用します。
   * 使用可能なデータビューのリストをフィルタリングするには、「![ フィルターを表示 ](/help/assets/icons/Filter.svg)」を選択します。 [!UICONTROL  接続 ]、[!UICONTROL  所有者 ]、[!UICONTROL  サンドボックス ] でリストをフィルタリングできます。<br/> フィルターウィンドウを非表示にするには、![ 非表示 ](/help/assets/icons/Filter.svg)**[!UICONTROL フィルターを非表示]** を使用します。
   * テーブルに表示する列を定義するには、「![ 列設定 ](/help/assets/icons/ColumnSetting.svg)」を選択します。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログに表示する列を選択し、「**[!UICONTROL 適用]** を選択して変更を適用します。

1. 使用するデータビューの ![SelectBox](/help/assets/icons/SelectBox.svg) を選択します。
1. 「**[!UICONTROL 保存]**」を選択して、選択したデータビューを確定します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。


Customer Journey Analyticsでは、データビューはCustomer Journey Analytics[ 接続 ](/help/connections/overview.md) に関連付けられています。 また、接続は組織内のサンドボックスに基づいています。 設定を保存すると、選択したデータビューに基づいて、サンドボックスの名前が **[!UICONTROL サンドボックス]** に自動入力されます。


### エクスペリエンスのキャプチャと定義 {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="エクスペリエンスのキャプチャと定義"
>abstract="コンテンツ分析で収集するデータにエクスペリエンスを含めるように選択できます。選択した場合、エクスペリエンスを含める URL を定義するために、正規表現とクエリパラメーターの 1 つ以上の組み合わせを定義する必要があります。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="エクスペリエンスのキャプチャと定義"
>abstract="コンテンツ分析でのエクスペリエンスの収集"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="エクスペリエンスのキャプチャと定義"
>abstract="Web サイトでのコンテンツのレンダリング方法を決定するパラメーターを指定します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="エクスペリエンスのキャプチャと定義"
>abstract="現在の設定に関連付けられたタグプロパティの Adobe コンテンツ分析拡張機能の設定を編集できます。"

<!-- markdownlint-enable MD034 -->

このセクションでは、コンテンツ分析で収集するデータにエクスペリエンスを含めるように選択できます。  エクスペリエンスとは、web ページにアクセスした最初のユーザーが使用する URL を使用して再現可能な、web ページ上のすべてのテキストです。

デフォルトでは、**[!UICONTROL エクスペリエンスを含める]** はオフになっています。 選択した場合、エクスペリエンスを含める URL を定義する必要があります。

次に該当する場合にのみ、エクスペリエンスを含めることを検討してください。

* ページ URL を使用して、サイト上のページを再現できる必要があります。
* 特定のユーザーで表示されるテキストコンテンツは、ページ URL を使用して再生でき、Cookie やその他のパーソナライゼーションメカニズムには依存しません。

新しい設定や実装されていない設定にエクスペリエンスを含めるには：

![Content Analytics 設定のエクスペリエンスキャプチャと定義 ](../assets/aca-configuration-experience.png)

1. **[!UICONTROL エクスペリエンスを含める]** を有効にします。 エクスペリエンスを有効にする切り替えは、次の影響を受けます。

   * Content Analytics拡張機能でのデータ収集
   * Content Analytics イベントデータからエクスペリエンス属性を生成するプロセス
   * Customer Journey Analyticsのレポートテンプレート。

1. Web サイト上でコンテンツをレンダリングする方法のパラメーターを指定します。 パラメーターは、0 個以上の **[!UICONTROL ドメイン正規表現]** と **[!UICONTROL クエリパラメーター]** の組み合わせです。 クエリパラメーターは、ページ上のコンテンツに影響を与えるパラメーターを示します。 この入力により、Content Analyticsは、一意のエクスペリエンスを定義する際に、ページ上のコンテンツに影響を与えないパラメーターを無視することができます。
   1. **[!UICONTROL ドメイン正規表現]** を入力します（例：`/^(?!.*\b(store|help|admin)\b)/`）。 `/` を使用して、正規表現をエスケープする必要があります。 ドメインの正規表現は、これらのパラメーターが適用される URL を示します。 例えば、複数のサイトがあり、サイトごとに異なるパラメーターがコンテンツを駆動する場合があります。 クエリパラメーターがすべてのページに適用される場合は、`.*` を使用してすべてのページを指定できます。
   1. **[!UICONTROL クエリパラメーター]** のコンマ区切りリスト（例：`outdoors, patio, kitchen`）を指定します。
1. ドメイン正規表現とクエリパラメーターの組み合わせを削除する場合は、「**[!UICONTROL 削除]**」を選択します。
1. 正規表現とクエリパラメーターの別の組み合わせを追加する場合は、「**[!UICONTROL 正規表現を追加]**」を選択します。

既存のエクスペリエンスを編集するか、実装された設定に新しいエクスペリエンスを含めるには：

![Content Analytics 設定のエクスペリエンスキャプチャと定義 ](../assets/aca-configuration-experience-edit.png)

* Analysis Workspaceのエクスペリエンスコンポーネント、ビジュアライゼーション、パネル、テンプレートを有効または無効にするには、**[!UICONTROL エクスペリエンスを含める]** を切り替えます。

* ![Edit](/help/assets/icons/Edit.svg)**[!UICONTROL Edit]** を選択して、Content Analyticsのエクスペリエンスのデータ収集の設定をさらに編集します。 現在の設定に関連付けられているタグプロパティの ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)0}Adobe Content Analytics拡張機能 } にリダイレクトされます。[


### データ収集 {#onboarding-data-collection}

この節では、コンテンツ分析データの収集方法を設定します。

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
>abstract="Content Analytics拡張機能は既にアクティブです。"

<!-- markdownlint-enable MD034 -->

#### 新しい設定 {#new-configuration}

新しい設定では、既存のタグプロパティを使用するか、新しいタグプロパティを作成するかを定義する必要があります。 また、正規表現を使用して、含めるか除外するページとアセットを定義する必要があります。

* 既存のタグプロパティを使用するには：

  ![Content Analytics データ収集既存のタグ ](../assets/aca-configuration-datacollection-existingtag.png)

   1. 「**[!UICONTROL 既存を選択]**」を選択します。
   2. **[!UICONTROL タグプロパティ]** ドロップダウンメニューから既存のプロパティを選択します。 入力を開始して、使用可能なオプションを検索し制限することができます。 別の実装済みContent Analytics設定で既に使用されているタグプロパティは選択できません。


* 新しいタグプロパティを作成するには：

  ![Content Analytics データ収集の新しいタグ ](../assets/aca-configuration-datacollection-newtag.png)

   1. **[!UICONTROL 新規作成]** を選択します。
   1. **[!UICONTROL タグ名]** を指定します（例：`ACA Test for Documentation`）。
   1. **[!UICONTROL Domains]** を指定します（例：`example.com`）。

* Content Analyticsのデータを収集する際に含める、または除外するページを指定します。

  **[!UICONTROL 含める/除外するページ]** の正規表現文字列を指定します。 <br/> 例：すべてのドキュメントページをContent Analyticsから除外する `^(?!.*documentation).*`。

* コンテンツ分析用のデータを収集する際に含める、または除外するアセットを指定します。

  含める/除外する **[!UICONTROL Assetsの正規表現文字列を指定し]** す。 <br/> 例：Content Analyticsからすべてのロゴ JPEGとSVG画像を除外する `^(?!.*(logo\.jpg|\.svg)).*$`。

>[!IMPORTANT]
>
>タグを使用せずに Javascript を使用して既存の web SDK実装がある場合は、新しく作成したタグプロパティから、自動で組み込まれる Web SDK拡張機能を手動で削除する必要があります。



#### 既存の設定 {#existing-configuration}

既存の設定では、タグプロパティは編集できません。 ただし、含めるか除外するページとアセットを編集することはできます。

* コンテンツ分析用のデータを収集する際に含める、または除外するページを編集するには、「**[!UICONTROL エクスペリエンス]** の下の「![ 編集 ](/help/assets/icons/Edit.svg)**[!UICONTROL 編集]** を選択します。 現在のContent Analytics設定のタグプロパティに関連付けられている ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)0}Adobe Content Analytics拡張機能にリダイレクトされます。 [正規表現を編集して、ページを含めたり除外したりできます。 変更を必ず [ 公開 ](#publish) します。

* コンテンツ分析用のデータを収集する際に含める、または除外するアセットを編集するには、「**[!UICONTROL アセット]** の下の「![ 編集 ](/help/assets/icons/Edit.svg)**[!UICONTROL 編集]** を選択します。 現在のContent Analytics設定のタグプロパティに関連付けられている ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)0}Adobe Content Analytics拡張機能にリダイレクトされます。 [正規表現を編集して、アセットを含めたり除外したりできます。 変更を必ず [ 公開 ](#publish) します。

### 概要 {#summary}

必要な詳細をすべて入力すると、作成または変更されたアーティファクトの詳細が概要に表示されます。

* 新しい設定を実装すると、**[!UICONTROL コンテンツ分析の _設定名_ の概要を実装する準備がほぼ整いました]** というメッセージが表示されます。

* 既存の実装済み設定の場合、**[!UICONTROL Content Analytics 用に _設定名_ を実装しました]** という概要が表示されます。

![Content Analytics 設定の概要 ](../assets/aca-configuration-summary.png)

### アクション {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="実装の確認"
>abstract="「**[!UICONTROL 実装]**」を選択した場合は、このワークフローで指定した入力に基づいてコンテンツ分析を設定します。コンテンツ分析に一般的に役立つ内容に基づいて、いくつかの設定がデフォルトで選択されていますが、ユーザー（データ管理者）は各アーティファクトの設定を確認し、プライバシーポリシー、契約上の権利と義務、適用法に基づく同意要件に従って設定が実装されていることを確認する必要があります。<br/><br/>この設定に関連付けられたタグライブラリを手動で公開するまで、データは収集されません。<br/><br/>画像やテキストの属性を取得するために、アドビでは、次を使用して属性を取得します。<ol><li>設定したデータ収集設定に従って、ユーザーのサイト訪問時に取得される URL。</li><li>画像がホストされる URL。</li></ol>サードパーティのサイトでホストされている画像にタグを付けることはできません。"

<!-- markdownlint-enable MD034 -->

設定を作成または編集する際には、次のオプションがあります。

* **[!UICONTROL 破棄]**：設定の一部として行われたすべての変更は破棄されます。
* **[!UICONTROL 後で使用するために保存]**：設定に対する変更は保存されます。 後から設定を再度参照して、さらに変更を加えたり、設定を実装したりできます。 設定を保存するには、[!UICONTROL  名前 ] の値のみが必要です。
* **[!UICONTROL 実装]**：設定または設定に加えた変更を保存して実装します。 ![ 必須 ](/help/assets/icons/Required.svg) とマークされたすべてのフィールドに適切な値が必要です。 実装は次で構成されます。

   * **[!UICONTROL Customer Journey Analytics]** 設定：
      * 選択したデータビューが更新され、Content Analytics のディメンションと指標が表示されます。
      * 選択したデータビューに結び付けられた接続が変更され、Content Analytics イベントと属性データセットが含まれるようになりました。
      * コンテンツ分析レポートテンプレートがWorkspaceに追加されます。


   * **[!UICONTROL Adobe Experience Platform]** 設定：
      * Content Analytics イベント、アセット属性、（設定されている場合は）エクスペリエンス属性をモデル化するスキーマの作成。
      * Content Analytics イベント、アセット属性および（設定されている場合は）エクスペリエンス属性を収集するデータセットの作成。
      * 機能サービスを使用して Content Analytics イベントからコンテンツ属性を生成および更新するデータフローの作成。


   * **[!UICONTROL データ収集]** 設定：
      * 新しいタグプロパティまたは既存のタグプロパティは、Content Analyticsのデータ収集をサポートするように設定されます。 この設定は、Tags 用のAdobe Content Analytics 拡張機能を含めることを意味します。
      * Content Analytics イベント用にデータストリームが作成されます。
      * Adobe Content Analytics 拡張機能は、Content Analytics イベントが Content Analytics 用のデータストリームに確実に送信されるように設定されています。
      * Web SDKがタグプロパティ用に設定されていない場合、コンテンツ分析イベントのみを送信する新しい web SDK設定が作成されます。
      * Web SDKがこのタグプロパティ用に設定されている場合、既存の web SDKの設定は変更されません。


* **[!UICONTROL 保存]**：実装された設定に対する変更が保存され、実装が更新されます。
* **[!UICONTROL 終了]**。 ガイド付き設定を終了します。 実装された設定に対して行われた変更はすべて破棄されます。


## 公開 {#publish}

Content Analytics設定のデータの収集を開始するには、[ 実装 ](manual.md) を選択した後に作成されたタグプロパティを **[!UICONTROL 手動で]** 公開する必要があります。


>[!MORELIKETHIS]
>
>[ 手動設定 ](manual.md)
>
