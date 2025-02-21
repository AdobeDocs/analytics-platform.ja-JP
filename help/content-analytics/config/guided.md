---
title: Content Analytics ガイド付き設定
description: オンボーディングガイド付き設定を使用した Content Analytics の設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: ec0ea74df83bbd07b7e026d7b9d7114c7dc595ab
workflow-type: tm+mt
source-wordcount: '1991'
ht-degree: 9%

---

# Content Analytics ガイド付き設定

>[!WARNING]
>
>この記事は、今後の最終バージョンの非公式ドラフトバージョンであり、コンテンツ分析ドキュメントの一部です。 すべてのコンテンツは変更される可能性があり、この記事の現在のバージョンから法的義務を引き出すことはできません。
>

{{release-limited-testing}}

ガイド付き設定を使用すると、コンテンツ分析をすばやく簡単に設定できます。 ガイド付き設定では、ウィザードを使用して、組織のコンテンツ分析を自動的に設定するための要件を設定します。 **[!UICONTROL 設定]** 画面で、新しい設定を作成するか、既存の設定を編集できます。

>[!IMPORTANT]
>
>組織のサンドボックスごとに 1 つの Content Analytics 設定のみを持つことができます。


コンテンツ分析設定にアクセスするには

* Customer Journey Analyticsのメインメニューから **[!UICONTROL データ管理]**/**[!UICONTROL コンテンツ分析]** を選択します。

コンテンツ分析設定画面に、既存のコンテンツ分析設定のテーブルが表示されます。

![Content Analytics 設定 ](../assets/aca-configuration-table.png)
各設定で、次の詳細を使用できます。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 名前]** | 設定の名前。 |
| **[!UICONTROL 作成者]** | 設定を作成したテクニカルアカウント。 |
| **[!UICONTROL 作成日]** | 設定が作成されたときのタイムスタンプ。 |
| **[!UICONTROL 変更日]** | 設定が最後に変更されたときのタイムスタンプ。 |
| **[!UICONTROL サンドボックス]** | コンテンツ分析が（予定されて）設定および実装される、組織内のサンドボックス。 |
| **[!UICONTROL ステータス]** | 設定のステータス。 ステータスは次のようになります。<br/>![StatusGray](/help/assets/icons/StatusGray.svg)**[!UICONTROL Draft]**：設定は後で使用するために保存され、デプロイされていません。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**：設定に失敗しました。 設定を編集し、必要な変更を加える必要があります。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg)**[!UICONTROL Complete]**：設定が完了し、正常に実装されました。 |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、テーブルをカスタマイズできます。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログに表示する列を選択し、「**[!UICONTROL 適用]** を選択して変更を適用します。

コンテンツ分析 **[!UICONTROL 設定]** 画面から、新しい設定を作成したり、既存の設定を編集したりできます。

新しい設定を作成するには：

* **[!UICONTROL 設定を作成]** を選択します。 このアクションにより、ガイド付き設定ウィザードが開きます。

既存の設定を編集するには：

* 既存のコンテンツ分析設定に対して、![ 詳細 ](/help/assets/icons/More.svg) を選択してから ![ 編集 ](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]** を選択します。 このアクションにより、ガイド付き設定ウィザードが開きます。

## ガイド付き設定ウィザード

ガイド付き設定ウィザードは、4 つのセクション（[ 詳細 ](#details)、[ データ表示 ](#data-view)、[ エクスペリエンスの取得と定義 ](#experience-capture-and-definition)、[ データ収集 ](#data-collection)）で構成され、それぞれが適切に設定してコンテンツ分析を設定するために必要な詳細を求めます。 セクション内の一部の設定は、前のセクションの設定値に依存する場合があるので、次のセクションに進む前に各セクションを完了してください。

### 詳細 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="詳細"
>abstract="接続の名前を指定します。**[!UICONTROL データビュー]**、**[!UICONTROL エクスペリエンスの取得と定義]**、および **[!UICONTROL データ収集]** の各セクションでは、コンテンツ分析を正しく設定できるようにするための詳細情報を指定します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="詳細"
>abstract="このガイドでは、コンテンツ分析を設定するために必要な要件を設定します。この設定の名前を指定してください"

<!-- markdownlint-enable MD034 -->

各設定には、一意の名前が必要です。 例：`Example Content Analytics configuration`。

![Content Analytics 設定の詳細 ](../assets/aca-configuration-details.png)


### データビュー {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="データビュー"
>abstract="コンテンツ分析を設定するには、既存のデータビューを選択する必要があります。 そのため、コンテンツ分析データを他のデータと結合できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="データビュー"
>abstract="コンテンツ分析データの結合先となるCustomer Journey Analyticsの既存のデータビューを選択します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="データビュー"
>abstract="コンテンツ分析データの結合先となるCustomer Journey Analyticsの既存のデータビューを選択します。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change"
>title="データ表示を選択"
>abstract="新しいデータビューを選択すると、そのデータビューが更新され、コンテンツ分析指標およびディメンションが含まれます。 必要に応じて、関連する接続も更新され、コンテンツ分析データセットが含まれます。 コンテンツ分析用に現在設定されている接続とデータビューは変更されません。"

<!-- markdownlint-enable MD034 -->

設定では、[ データビュー ](/help/data-views/data-views.md) を選択する必要があります。

![ データビューの Content Analytics 設定 ](../assets/aca-configuration-dataview.png)

データ表示を選択するには：

1. ![ データ ](/help/assets/icons/Data.svg)**[!UICONTROL データビューを選択]** を使用します。 **[!UICONTROL データビュー]** ダイアログが表示され、設定用のデータビューを選択できます。

   新しい設定を作成した場合、リストには、アクティブな設定がないサンドボックスに関連付けられているデータビューのみが表示されます。
既存の設定を編集すると、リストには、既存の設定に既に関連付けられているサンドボックス内で使用可能なデータビューのみが表示されます。

   * 使用可能なデータビューのリストをフィルタリングするには、「![ フィルターを表示 ](/help/assets/icons/Filter.svg)」を選択します。 接続、所有者、サンドボックスのリストをフィルタリングできます。<br/> フィルターウィンドウを非表示にするには、![ 非表示 ](/help/assets/icons/Filter.svg)**[!UICONTROL フィルターを非表示]** を使用します。
   * テーブルに表示する列を定義するには、「![ 列設定 ](/help/assets/icons/ColumnSetting.svg)」を選択します。 **[!UICONTROL テーブルをカスタマイズ]** ダイアログに表示する列を選択し、「**[!UICONTROL 適用]** を選択して変更を適用します。
1. 「**[!UICONTROL 保存]**」を選択して、選択したデータビューを確定します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

データビューはCustomer Journey Analyticsに関連付けられています [ 接続 ](/help/connections/overview.md)。 また、接続は組織内のサンドボックスに基づいています。 設定を保存すると、選択したデータビューに基づいて、サンドボックスの適切な名前が **[!UICONTROL サンドボックス]** に自動入力されます。


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
>id="aca_onboarding_experiences_url_header"
>title="エクスペリエンスのキャプチャと定義"
>abstract="以下のパラメーターを適用する URL を指定します"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_edit_button"
>title="エクスペリエンスのキャプチャと定義"
>abstract="選択した設定に関連付けられている、タグプロパティのAdobe Content Analytics 拡張機能の設定を編集できます。"

<!-- markdownlint-enable MD034 -->

このセクションでは、コンテンツ分析で収集するデータにエクスペリエンスを含めるように選択できます。  エクスペリエンスとは、web ページにアクセスした最初のユーザーが使用する URL を使用して再現可能な、web ページ上のすべてのテキストです。

デフォルトでは、**[!UICONTROL エクスペリエンスを含める]** はオフになっています。 選択した場合、エクスペリエンスを含める URL を定義する必要があります。

エクスペリエンスは、次のいずれかに該当する場合にのみ含めるようにしてください。

* サイト上のコンテンツは、URL でのみ駆動されます。
* ページ URL を使用して、サイト上のページを再現できる必要があります。

新しい設定や実装されていない設定にエクスペリエンスを含めるには：

![Content Analytics 設定のエクスペリエンスキャプチャと定義 ](../assets/aca-configuration-experience.png)

1. **[!UICONTROL エクスペリエンスを含める]** を有効にします。
1. Web サイトでのコンテンツのレンダリング方法を決定するパラメーターを指定します。 パラメーターは、0 個以上の **[!UICONTROL ドメイン正規表現]** と **[!UICONTROL クエリパラメーター]** の組み合わせです。
   1. **[!UICONTROL ドメイン正規表現]** を入力します（例：`(?!.*\b(store|help|admin)\b)`）。
   1. **[!UICONTROL クエリパラメーター]** のコンマ区切りリスト（例：`outdoors, patio, kitchen`）を指定します。
1. ドメイン正規表現とクエリパラメーターの組み合わせを削除する場合は、「**[!UICONTROL 削除]**」を選択します。
1. 正規表現とクエリパラメーターの別の組み合わせを追加する場合は、「**[!UICONTROL さらに追加]**」を選択します。

既存のエクスペリエンスを編集するか、実装された設定に新しいエクスペリエンスを含めるには：

![Content Analytics 設定のエクスペリエンスキャプチャと定義 ](../assets/aca-configuration-experience-edit.png)

* 「![ 編集 ](/help/assets/icons/Edit.svg) 編集」を選択して、選択した設定に関連付けられた、タグプロパティのAdobe Content Analytics 拡張機能のパラメーターを編集します。


### データ収集 {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="データ収集"
>abstract="使用するタグプロパティを定義するか、新しいタグプロパティを作成します。また、正規表現を使用して、含めるページや除外するアセットを定義します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="データ収集"
>abstract="タグプロパティの指定"

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
>abstract="選択した設定に関連付けられている、タグプロパティのAdobe Content Analytics 拡張機能のページの設定を編集できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="データ収集"
>abstract="選択した設定に関連付けられている、タグプロパティのAdobe Content Analytics 拡張機能のアセットの設定を編集できます。"

<!-- markdownlint-enable MD034 -->

#### 新しい設定

新しい設定では、使用するタグプロパティを定義するか、新しいタグプロパティを作成する必要があります。 また、正規表現を使用して、含めるか除外するページとアセットを定義する必要があります。

* 既存のタグプロパティを使用するには：

  ![Content Analytics データ収集既存のタグ ](../assets/aca-configuration-datacollection-existingtag.png)

   * **[!UICONTROL 既存]** を選択します。
   * **[!UICONTROL タグプロパティ]** ドロップダウンメニューから既存のプロパティを選択します。

* 新しいタグプロパティを作成するには：

  ![Content Analytics データ収集の新しいタグ ](../assets/aca-configuration-datacollection-newtag.png)

   1. **[!UICONTROL 新規作成]** を選択します。
   2. **[!UICONTROL タグ名]** を指定します（例：`ACA Test`）。
   3. **[!UICONTROL Domains]** を指定します（例：`example.com`）。

* エクスペリエンスを含めることを選択した場合は、コンテンツ分析用のデータを収集するときに、どのページを含めるか除外するかを指定します。

   * **[!UICONTROL エクスペリエンス]** の正規表現を指定します。 例：`(?!.*\b(store|help|admin)\b)`。

* コンテンツ分析用のデータを収集する際に含める、または除外するアセットを指定します。

   * **[!UICONTROL Asset]** の正規表現を指定します。 例：`(?!.*\b(store|help|admin)\b)`。


#### 既存の設定

既存の設定では、タグプロパティは編集できません。 ただし、含めるか除外するページとアセットを編集することはできます。

* コンテンツ分析用のデータを収集する際に含める、または除外するページを編集するには、「**[!UICONTROL エクスペリエンス]** の下の「![ 編集 ](/help/assets/icons/Edit.svg)**[!UICONTROL 編集]** を選択します。

* コンテンツ分析用のデータを収集する際に含める、または除外するアセットを編集するには、「**[!UICONTROL アセット]** の下の「![ 編集 ](/help/assets/icons/Edit.svg)**[!UICONTROL 編集]** を選択します。

### 概要 {#summary}

必要な詳細をすべて入力すると、作成または変更されたアーティファクトの詳細が概要に表示されます。

* 新しい設定を実装すると、**[!UICONTROL コンテンツ分析の _設定名_ の概要を実装する準備がほぼ整いました]** というメッセージが表示されます。

* 既存の実装済み設定の場合、**[!UICONTROL Content Analytics 用に _設定名_ を実装しました]** という概要が表示されます。

![Content Analytics 設定の概要 ](../assets/aca-configuration-summary.png)

### アクション {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning"
>title="オンボーディング実装の警告"
>abstract="**[!UICONTROL 実装]** を選択した場合は、このワークフローで指定した入力に基づいてコンテンツ分析を設定します。 いくつかの設定は、デフォルトでコンテンツ分析に一般的に役立つ内容に基づいて選択されますが、ユーザー（データ管理者）は、各アーティファクトの設定を確認して、プライバシーポリシー、契約上の権利と義務、適用法に基づく同意要件に従って設定が実装されていることを確認する必要があります。<br/><br/> この設定に関連付けられているタグライブラリを手動で公開するまで、データは収集されないことに注意してください。<br/><br/> 画像とテキストの属性を取得するために、Adobeは次を使用して属性を取得します。<ol><li>設定したデータ収集設定に従って、ユーザーサイト訪問時に取得された URL。</li><li>画像がホストされる URL。</li></ol>サードパーティのサイトでホストされている画像にタグを付けてはいけません。"

<!-- markdownlint-enable MD034 -->


設定を作成または編集すると、次のアクションを使用できます。

* **[!UICONTROL 破棄]**：新しい設定の作成または既存の設定の編集の一環として行われたすべての変更は破棄されます。
* **[!UICONTROL 後で使用するために保存]**：新しい設定または既存の実装されていない設定に対する変更が保存されます。 後から設定を再度参照して、さらに変更を加えたり、設定を実装したりできます。
* **[!UICONTROL 実装]**：新しい設定または既存の設定に対する設定や変更、まだ実装されていない設定は保存されて実装されます。 実装は次で構成されます。
   * **[!UICONTROL Adobe Experience Platform]** 設定：
      * Content Analytics イベント、アセット属性、（設定されている場合は）エクスペリエンス属性をモデル化するスキーマの作成。
      * Content Analytics イベント、アセット属性および（設定されている場合は）エクスペリエンス属性を収集するデータセットの作成。
      * 機能サービスを使用して Content Analytics イベントからコンテンツ属性を生成および更新するデータフローの作成。
   * **[!UICONTROL データ収集]** 設定：
      * 新しいタグプロパティまたは既存のタグプロパティは、コンテンツ分析データ収集をサポートするように設定されます。 この設定は、Tags 用のAdobe Content Analytics 拡張機能を含めることを意味します。
      * Content Analytics イベント用にデータストリームが作成されます。
      * Adobe Content Analytics 拡張機能は、Content Analytics イベントが Content Analytics 用のデータストリームに確実に送信されるように設定されています。
      * Web SDKがタグプロパティ用に設定されていない場合、コンテンツ分析イベントのみを送信する新しい web SDK設定が作成されます。
      * Web SDKがこのタグプロパティ用に設定されている場合、既存の web SDKの設定は変更されません。
   * **[!UICONTROL Customer Journey Analytics]** 設定：
      * 選択したデータビューが更新され、Content Analytics のディメンションと指標が表示されます。
      * 選択したデータビューに結び付けられた接続が変更され、コンテンツ分析イベントと属性データセットが含まれるようになりました。
      * コンテンツ分析レポートテンプレートがWorkspaceに追加されます。
* **[!UICONTROL 保存]**：実装された設定に対する変更が保存され、実装が更新されます。
* **[!UICONTROL 終了]**。 ガイド付き設定を終了します。 実装された設定に対して行われた変更はすべて破棄されます。

>[!MORELIKETHIS]
>
>[ 手動設定 ](manual.md)
>
