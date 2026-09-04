---
title: Content Analytics ガイド付き設定
description: オンボーディングガイド付き設定を使用してContent Analyticsを設定する方法を説明します。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hold: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
autotag-review: '2026-05-19T08:54:42.845Z'
TQID: 'https://experienceleague.adobe.com/kEqjocKd5pNypjQlF70HeF1bKuoG9Qi-AT6nJiIwuV0'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c18d9e03-ac7d-4811-9c92-3e92ddc70adeid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8490c4128ac906ba9421b91f9b9da433b91d084d
workflow-type: tm+mt
source-wordcount: 4806
ht-degree: 54%

---


# Content Analytics ガイド付き設定

ガイド付き設定を使用すると、Content Analytics をすばやく簡単に設定できます。 ガイド付き設定では、ウィザードを使用して、組織の Content Analytics を自動的に設定するための要件を設定します。 **[!UICONTROL 設定]**&#x200B;画面で、新しい設定を作成するか、既存の設定を編集できます。

>[!IMPORTANT]
>
>組織のサンドボックスごとに 1 つの Content Analytics 設定のみを持つことができます。

>[!NOTE]
>
>設定ウィザードでは、複数のデータビューとチャネルがサポートされており、単一のデータビューとweb チャネルのみをサポートしていた以前のバージョンとは異なります。 [ データビュー](#data-views) セクションで1つ以上のデータビューを選択する前に、サンドボックスと接続を選択する必要があります。 **[!UICONTROL Experience capture]**、**[!UICONTROL データ収集]**、**[!UICONTROL ヘッダーの上書き]**&#x200B;の設定はチャネルに依存しており、[ チャネル ](#channels) セクションで設定する各チャネルの一部です。

Content Analytics 設定にアクセスするには

* Customer Journey Analytics のメインメニューから&#x200B;**[!UICONTROL データ管理]**／**[!UICONTROL Content Analytics 設定]**&#x200B;を選択します。

**[!UICONTROL Content Analytics 設定]**&#x200B;画面に、既存の Content Analytics 設定のテーブルが表示されます。

![Content Analytics設定](../assets/aca-configuration-table.png)
各設定について、次の詳細を確認できます。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 名前]** | 設定の名前。 |
| **[!UICONTROL 作成者]** | 設定を作成したテクニカルアカウント。 |
| **[!UICONTROL 作成日]** | 設定が作成されたときのタイムスタンプ。 |
| **[!UICONTROL 変更日]** | 設定が最後に変更されたときのタイムスタンプ。 |
| **[!UICONTROL サンドボックス]** | Content Analytics が（予定されて）設定および実装される、組織内のサンドボックス。 |
| **[!UICONTROL ステータス]** | 設定のステータス。 ステータスは、設定が完了した有効なチャネルの数を示します。 ![InfoOutline](/help/assets/icons/InfoOutline.svg)を使用して、より詳細な情報を含むポップアップを開きます。 |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、テーブルをカスタマイズできます。 **[!UICONTROL テーブルをカスタマイズ]**&#x200B;ダイアログに表示する列を選択し、「**[!UICONTROL 適用]**」を選択して変更を適用します。

Content Analytics **[!UICONTROL 設定]**&#x200B;画面から、新しい設定を作成したり、既存の設定を編集したりできます。

新しい設定を作成するには：

* 「**[!UICONTROL 設定を作成]**」を選択します。 このアクションにより、[ガイド付き設定ウィザード](#guided-configuration-wizard)が開きます。

既存の設定を編集するには：

* 既存のコンテンツ分析設定に対して、「![詳細](/help/assets/icons/More.svg)」を選択してから![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**&#x200B;を選択します。 このアクションにより、[ガイド付き設定ウィザード](#guided-configuration-wizard)が開きます。

## ガイド付き設定ウィザード

ガイド付き設定ウィザードには、[詳細](#details)、[接続](#connection)、[ データビュー](#data-view)、および[ チャネル ](#channels)の4つのセクションが含まれています。 各セクションでは、Content Analyticsの設定に必要な詳細を確認するプロンプトが表示されます。 一部の設定は以前のセクションの設定値に依存するため、次のセクションに移動する前に各セクションを完了してください。

### 詳細 {#onboarding-details}

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="詳細"
>abstract="接続の名前を指定します。 設定の名前を指定し、分析するコンテンツ分析データを含むサンドボックスを選択します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="詳細"
>abstract="このガイドでは、Content Analyticsを設定するための要件を設定します。 この設定の名前を指定し、分析するコンテンツ分析データを含むサンドボックスを選択します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_boldheader"
>title="接続"
>abstract="**接続**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_header"
>title="接続"
>abstract="Customer Journey Analyticsから既存の接続を選択して、Content Analytics データを結合します。"

各設定には、一意の名前が必要です。 例えば、`Example Content Analytics configuration` のように設定します。 設定を保存または実装するには、名前が必須です。

また、設定ごとに、Content Analyticsを設定するサンドボックスを選択する必要があります。

![Content Analytics 設定の詳細](../assets/aca-configuration-details.png)

* **[!UICONTROL 名前]**：各設定には一意の名前が必要です。 例えば、`Example Content Analytics configuration` のように設定します。 設定を保存または実装するには、名前が必須です。

* **[!UICONTROL サンドボックス]**：設定にはサンドボックスが必要です。 アクセス権があり、Content Analyticsに使用するデータが収集されるサンドボックスのリストから、サンドボックスを選択します。

  接続とオプションでデータビューを定義した設定サンドボックスを変更すると、接続とデータビューを再設定する必要があることが通知されます。

### 接続

Content Analytics data collectionを追加する接続を選択する必要があります。

設定の接続を選択していない場合：

1. ![ データ ](/help/assets/icons/Data.svg) **[!UICONTROL 接続を選択]**&#x200B;して、サンドボックスで使用可能なすべての接続を一覧表示する&#x200B;**[!UICONTROL 接続を選択]** ダイアログを開きます。
1. **[!UICONTROL 接続を選択]** ダイアログで、使用する接続を![SelectBox](/help/assets/icons/SelectBox.svg)選択します。 1つの接続のみを選択できます。
1. 「**[!UICONTROL 接続を使用]**」を選択します。

すでに接続を選択しているが、その接続を変更したい場合：

1. ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**&#x200B;を選択します。
1. **[!UICONTROL 接続を選択]** ダイアログで、使用する接続を変更します。
1. 「**[!UICONTROL 接続を使用]**」を選択します。


### データビュー {#onboarding-data-view}

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="データビュー"
>abstract="Content Analytics を設定するには、既存のデータビューを選択する必要があります。 そのため、Content Analytics データを他のデータと結合できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="データビュー"
>abstract="Customer Journey Analyticsから既存のデータビューを選択して、Content Analytics データを結合します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="データビュー"
>abstract="コンテンツ分析データを結合する Customer Journey Analytics の既存のデータビューを選択します。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="新規データビュー"
>abstract="この設定用に新しいデータビューが選択されました。 新しいデータビューが更新され、Content Analytics の指標とディメンションが含まれます。 これらの指標とディメンションは、最初に選択したデータビューから削除されます。<br/><br/>新しいデータビューに別の接続が関連付けられている場合、接続が更新され、コンテンツ分析データセットが含まれます。 コンテンツ分析データセットは、最初に選択した接続から削除されません。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="選択したデータビューのクリーンアップ"
>abstract="Content Analytics 用に既にプロビジョニングしているデータビューが選択されました。 この既存の Content Analytics 設定は削除され、データビューが新しい設定でプロビジョニングされます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="以前のデータビューのクリーンアップ"
>abstract="新しいデータビューが選択されました。 以前に選択したデータビューの Content Analytics 設定は削除されます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="新規データビュー"
>abstract="この設定用に新しいデータビューが選択されました。 新しいデータビューが更新され、Content Analytics の指標とディメンションが含まれます。 同様の指標とディメンションは、既存のデータビューから削除されます。<br/>新しいデータビューに別の接続が関連付けられている場合、接続が更新され、コンテンツ分析データセットが含まれます。 なお、Content Analytics データセットは、既存の設定から削除されません。"


>[!CONTEXTUALHELP]
>id="ac_onboarding_dataviews_button"
>title="データビュー"
>abstract="Content Analytics を設定するには、1 つ以上のデータビューを選択する必要があります。 そのため、Content Analytics データを他のデータと結合できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header"
>title="データビュー"
>abstract="Content Analytics データを結合するために、Customer Journey Analytics の 1 つ以上の既存のデータビューを選択します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header_alt"
>title="データビュー"
>abstract="コンテンツ分析データを結合する Customer Journey Analytics の 1 つ以上の既存のデータビューを選択します。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_new_dialog"
>title="選択したデータビュー"
>abstract="この設定用に選択したデータビューが変更されました。 選択したデータビューが更新され、Content Analytics の指標とディメンションが含まれます。 これらの指標とディメンションは、選択されなくなった以前の選択したデータビューから削除されます。<br/><br/>選択したデータビューに別の接続が関連付けられている場合、接続が更新され、コンテンツ分析データセットが含まれます。 コンテンツ分析データセットは、最初に選択した接続から削除されません。<br/><br/>選択したすべてのデータビューでは、この設定の一部であるチャネルが継承されます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_change_dialog"
>title="選択したデータビュー"
>abstract="この設定用に選択したデータビューが変更されました。 選択したデータビューが更新され、Content Analytics の指標とディメンションが含まれます。 これらの指標とディメンションは、選択されなくなった以前の選択したデータビューから削除されます。<br/><br/>選択したデータビューに別の接続が関連付けられている場合、接続が更新され、コンテンツ分析データセットが含まれます。 Content Analytics データセットは、最初に選択した接続から削除されません。<br/><br/>選択したすべてのデータビューでは、この設定の一部であるチャネルが継承されます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_current_cleanup_labels_dialog"
>title="選択したデータビュー"
>abstract="この設定用に選択したデータビューが変更されました。 選択したデータビューが更新され、Content Analytics の指標とディメンションが含まれます。 これらの指標とディメンションは、選択されなくなった以前のデータビューから削除されます。<br/><br/>選択したデータビューに別の接続が関連付けられている場合、接続が更新され、コンテンツ分析データセットが含まれます。 Content Analytics データセットは、最初に選択した接続から削除されません。<br/><br/>選択したすべてのデータビューでは、この設定の一部であるチャネルが継承されます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_prev_cleanup_labels_dialog"
>title="選択したデータビュー"
>abstract="この設定用に選択したデータビューが変更されました。 選択したデータビューが更新され、Content Analytics の指標とディメンションが含まれます。 これらの指標とディメンションは、選択されなくなった以前のデータビューから削除されます。<br/><br/>選択したデータビューに別の接続が関連付けられている場合、接続が更新され、コンテンツ分析データセットが含まれます。 Content Analytics データセットは、最初に選択した接続から削除されません。<br/><br/>選択したすべてのデータビューでは、この設定の一部であるチャネルが継承されます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_button"
>title="チャネル"
>abstract="設定用に 1 つ以上のチャネルを有効にして設定します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_header"
>title="チャネル"
>abstract="設定用に 1 つ以上のチャネルを有効にして設定します。 設定の一部であるすべてのデータビューでは、有効なチャネルが継承されます。"


設定には、1つ以上の[ データビュー](/help/data-views/data-views.md)を選択する必要があります。

設定にデータビューを選択していない場合：

1. ![Data](/help/assets/icons/Data.svg) **[!UICONTROL Select data view]**&#x200B;を使用して、**[!UICONTROL Data view]** ダイアログを開きます。このダイアログには、Content Analytics用に設定した接続で使用可能なすべてのデータビューが一覧表示されます。
1. **[!UICONTROL データビュー]** ダイアログで、使用する1つ以上のデータビューを![SelectBox](/help/assets/icons/SelectBox.svg)選択します。
1. 「**[!UICONTROL 保存]**」を選択します。

既に1つ以上のデータビューを選択しているが、その選択を変更する場合：

1. ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL データビューの選択を編集]**&#x200B;を選択します。
1. **[!UICONTROL データビュー]** ダイアログで、使用するデータビューの選択![SelectBox](/help/assets/icons/SelectBox.svg)を変更します。
1. 「**[!UICONTROL 保存]**」を選択します。

**[!UICONTROL Save]**&#x200B;を選択すると、**[!UICONTROL Selected data views]** ダイアログが表示され、選択したデータビューにContent Analyticsを含めることの意味について通知されます。 続行するには&#x200B;**[!UICONTROL 続行]**&#x200B;を選択し、キャンセルするには&#x200B;**[!UICONTROL キャンセル]**&#x200B;を選択します。

**[!UICONTROL データビュー]** ダイアログでは、次のアクションを使用できます。

* 特定のデータビューを検索するには、![検索](/help/assets/icons/Search.svg) フィールドを使用します。
* 使用可能なデータビューのリストをフィルタリングするには、「![フィルターを表示](/help/assets/icons/Filter.svg)」を選択します。 [!UICONTROL 所有者]でリストをフィルタリングできます。<br/>使用![非表示](/help/assets/icons/Filter.svg) **[!UICONTROL フィルターを非表示]** セグメント ペインを非表示にします。
* テーブルに表示する列を定義するには、「![列設定](/help/assets/icons/ColumnSetting.svg)」を選択します。 **[!UICONTROL テーブルをカスタマイズ]**&#x200B;ダイアログに表示する列を選択し、「**[!UICONTROL 適用]**」を選択して変更を適用します。

### チャネル

「**[!UICONTROL チャネル]**」セクションで、Content Analyticsに対して有効にするチャネルを選択します。 **[!UICONTROL Mobile]**、**[!UICONTROL Web]**、**[!UICONTROL 有料メディア]**&#x200B;のいずれかを選択できます。

* まだ設定していないチャネルを選択するには、**[!UICONTROL 有効]**&#x200B;を選択します。
* 既に設定されているものの、設定を変更するチャネルを選択するには、**[!UICONTROL 設定を編集]**&#x200B;を選択します。

その後、チャンネルをより詳細に設定できます。 この設定は、[mobile](#mobile)、[web](#web)、[ ペイドメディア ](#paid-media) チャネルの設定を有効にするか、または編集するかによって異なります。

#### モバイル

+++ 詳細

<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_boldheader"
>title="モバイルエクスペリエンスの場所のデータ収集"
>abstract="**除外するエクスペリエンスの場所**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_header"
>title="モバイルエクスペリエンスの場所のデータ収集"
>abstract="コンテンツ分析のデータを収集する際に、**除外する**&#x200B;エクスペリエンスの場所を指定します。 個人を特定できるエクスペリエンスの場所を除外していることを確認します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_boldheader"
>title="モバイルアセットの場所のデータ収集"
>abstract="**除外するアセットの場所**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_header"
>title="モバイルアセットの場所のデータ収集"
>abstract="コンテンツ分析のデータを収集する際に、**除外する**&#x200B;アセットの場所を指定します。 個人を特定できるアセットの場所を除外していることを確認します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_boldheader"
>title="モバイルアセットの URL のデータ収集"
>abstract="**除外するアセットの URL**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_header"
>title="モバイルアセットの URL のデータ収集"
>abstract="コンテンツ分析のデータを収集する際に、**除外する** URL の場所を指定します。 個人を特定できるアセットの URL を除外していることを確認します。"

モバイルチャネルの場合、[ エクスペリエンスキャプチャと定義](#experience-capture-and-definition)、[ データ収集](#data-collection)、[ ヘッダーの上書き](#header-overrides)を設定できます。

### エクスペリエンスのキャプチャと定義 {#mobile-experience-capture-and-definition}

このセクションでは、Content Analyticsで収集したモバイルデータにエクスペリエンスを含めるように選択できます。  モバイルチャネルのエクスペリエンスは、Adobe Experience Platform SDK Content Analytics版を使用してエクスペリエンスとして登録したものです。

デフォルトでは、**[!UICONTROL エクスペリエンスを含める]**&#x200B;は無効になっています。

モバイルアプリを実装してエクスペリエンスを登録し、エクスペリエンスビューとエクスペリエンスクリックを追跡する場合にのみ、エクスペリエンスを含めることを検討してください。

### データ収集 {#mobile-data-collection}

Data Collection Settingsを使用すると、Content Analyticsで収集するデータ（エクスペリエンスの場所、アセットの場所、アセットのURL）を定義できます。 データ収集の一環として、個人を特定できる情報を収集しないようにします。

データ収集を設定するには：

* 既存のモバイルタグプロパティを使用するか、新しいモバイルタグプロパティを作成します。

  * 既存のモバイルタグプロパティを使用するには：

    1. 「**[!UICONTROL 既存のものを選択]**」を選択します。
    2. **[!UICONTROL タグプロパティ]**&#x200B;ドロップダウンメニューから既存のプロパティを選択します。 入力を開始して検索し、使用可能なオプションを制限できます。 別の実装されたContent Analytics設定で既に使用されているTags プロパティを選択することはできません。


  * 新しいモバイルタグプロパティを作成するには：

    1. 「**[!UICONTROL 新規作成]**」を選択します。
    1. 「**[!UICONTROL タグ名]**」を指定します（例：`ACA Test for Documentation`）。
    1. 「**[!UICONTROL ドメイン]**」を指定します（例：`example.com`）。

* Content Analyticsのデータを収集する際に除外するエクスペリエンスの場所を指定します。 個人を特定できるエクスペリエンスの場所を除外していることを確認します。

  ]**を除外する**[!UICONTROL  エクスペリエンスの場所に&#x200B;**[!UICONTROL 正規表現の文字列]**&#x200B;を指定します。 <br/>例：`^(?!.*documentation).*`：すべてのドキュメント エクスペリエンスの場所をContent Analyticsから除外します。

* Content Analyticsのデータを収集する際に除外するアセットの場所を指定します。 個人を特定できるアセットの場所を除外していることを確認します。

  **[!UICONTROL アセットの場所]**&#x200B;を除外する&#x200B;**[!UICONTROL 正規表現の文字列]**&#x200B;を指定します。 <br/>例：`^(?!.*(logo\.jpg)).*$`：ロゴ付きのアセットの場所をすべてContent Analyticsから除外する場合。JPEGの画像を含むアセットの場所は除外されます。

* Content Analyticsのデータを収集する際に除外するアセット URLを指定します。 個人を特定できるアセットの URL を除外していることを確認します。

  ]**を除外する**[!UICONTROL  アセット URLの&#x200B;**[!UICONTROL 正規表現の文字列]**&#x200B;を指定します。 <br/>例：`^(?!.*(logo\.jpg)).*$`:Content Analyticsからロゴ JPEG画像を参照するすべてのアセット URLを除外する


### ヘッダーの上書き {#mobile-header-overrides}

<!-- needs modification for mobile channel -->

オプションとして、**[!UICONTROL ヘッダーの上書き]** セクションで、ヘッダー名とシークレットヘッダーの値を指定できます。  このヘッダーが設定を上書きすると、Content Analyticsがカスタム HTTP ヘッダーを送信して、ボット検出やトラフィックゲートテクノロジをバイパスしてモバイルアプリアセットを取得できるようになります。

![ ヘッダーがセクション ](/help/content-analytics/assets/aca-configuration-header-overrides.png)を上書きします

1. **[!UICONTROL ヘッダーオーバーライドの設定]**&#x200B;を有効にします。
1. **[!UICONTROL ヘッダー名]**&#x200B;を入力します。 例：`x-asset-service`。
1. **[!UICONTROL ヘッダー値]**&#x200B;を入力します。 指定した内容は秘密鍵であり、ユーザーインターフェイスには表示されません（入力時に![表示](/help/assets/icons/Visibility.svg)値を明示的に開示することを選択しない限り）。

### 保存 {#mobile-save}

モバイルチャネルを設定したら、**[!UICONTROL 保存]**&#x200B;を選択して設定を保存します。 設定をキャンセルするには、**[!UICONTROL キャンセル]**&#x200B;を選択します。

+++

#### Web {#web}

+++ 詳細

Web チャネルの場合、[ エクスペリエンスキャプチャと定義](#experience-capture-and-definition-1)、[ データ収集](#data-collection-1)、[ ヘッダーの上書き](#header-overrides-1)を設定できます。

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="エクスペリエンスのキャプチャと定義"
>abstract="Content Analytics で収集するデータにエクスペリエンスを含めるように選択できます。 選択した場合、エクスペリエンスを含める URL を定義するために、正規表現とクエリパラメーターの 1 つ以上の組み合わせを定義する必要があります。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="エクスペリエンスのキャプチャと定義"
>abstract="Content Analytics でエクスペリエンスを収集"

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
>abstract="有効にすると、エクスペリエンスデータが収集され、エクスペリエンス属性が生成されて、エクスペリエンスレポートが使用可能になります。 <br><br/>現在の設定に関連付けられているタグプロパティ内のエクスペリエンスのデータ収集設定を変更するには、![編集](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編集]** を使用します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="エクスペリエンスのキャプチャと定義"
>abstract="Adobe Content Analytics 拡張機能でエクスペリエンスデータ収集の設定を編集する必要があります。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="データ収集"
>abstract="使用するタグプロパティを指定するか、新しいタグプロパティを作成します。 また、正規表現を使用して、含めるまたは除外するページとアセットを定義します。<br/>タグに依存しない実装の場合は、「**[!UICONTROL 新規作成]**」を選択します。  タグプロパティが作成されますが、使用する必要はありません。"
>additional-url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/content-analytics/configuration/tags-agnostic" text="コンテンツ分析のための JavaScript ライブラリ"


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
>abstract="コンテンツ分析のデータを収集する際に、**含める**&#x200B;または&#x200B;**除外する**&#x200B;ページを指定します。 個人を特定できるページを除外していることを確認します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="データ収集"
>abstract="**含める／除外するアセット**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="データ収集"
>abstract="コンテンツ分析のデータを収集する際に、**含める**&#x200B;または&#x200B;**除外する**&#x200B;アセットを指定します。 個人を特定できるアセットを除外していることを確認します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="データ収集"
>abstract="現在の設定に関連付けられたタグプロパティの Adobe コンテンツ分析拡張機能のページの設定を編集できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="データ収集"
>abstract="現在の設定に関連付けられたタグプロパティの Adobe Content Analytics 拡張機能で、アセットの設定を編集できます。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="タグプロパティが無効"
>abstract="Content Analytics 拡張機能は既にアクティブです。"


<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_boldheader"
>title="Web ページのデータ収集"
>abstract="**含める／除外するページ**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_header"
>title="Web ページのデータ収集"
>abstract="コンテンツ分析のデータを収集する際に、**含める**&#x200B;または&#x200B;**除外する**&#x200B;ページを指定します。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_boldheader"
>title="Web アセットのデータ収集"
>abstract="**含める／除外するアセット**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_header"
>title="Web アセットのデータ収集"
>abstract="コンテンツ分析のデータを収集する際に、**含める**&#x200B;または&#x200B;**除外する**&#x200B;アセットを指定します。 個人を特定できるアセットを除外していることを確認します。"


### エクスペリエンスのキャプチャと定義 {#web-experience-capture-and-definition}

このセクションでは、Content Analyticsで収集したweb データにエクスペリエンスを含めるように選択できます。  エクスペリエンスは、最初のユーザー訪問のURLを使用して再現可能なweb ページ上のすべてのテキストで構成されます。

デフォルトでは、**[!UICONTROL エクスペリエンスを含める]**&#x200B;はオフになっています。 選択したら、エクスペリエンスを含めるURLを定義します。

次に該当する場合にのみ、エクスペリエンスを含めることを検討します。

* ページ URL を使用して、サイト上のページを再現できる必要があります。
* 特定のユーザーが表示するテキストコンテンツは、ページ URL を使用して再現でき、Cookie やその他のパーソナライゼーションメカニズムに依存しません。

>[!IMPORTANT]
>
>[Content Analytics のバージョン管理](manual.md#versioning)を実装して、Content Analytics の対象となるエクスペリエンス（ページ）に行った変更を収集します。

#### 新しい設定 {#new-experiences-configuration}

新しい設定や実装されていない設定にエクスペリエンスを含めるには：

![Content Analytics 設定エクスペリエンスの取り込みと定義](../assets/aca-configuration-experience.png)

1. 「**[!UICONTROL エクスペリエンスを含める]**」を有効にします。 エクスペリエンスを有効にする切替スイッチは、次の影響を受けます。

   * Content Analytics 拡張機能でのデータ収集
   * Content Analytics イベントデータからエクスペリエンス属性を生成するプロセス
   * Customer Journey Analytics のレポートテンプレート。

1. 「**[!UICONTROL 正規表現を追加]**」を選択して、ドメイン正規表現とクエリパラメーターの組み合わせを追加します。
1. ページのコンテンツに影響を与える&#x200B;**[!UICONTROL ドメインの正規表現]**&#x200B;と&#x200B;**[!UICONTROL クエリパラメーター]**&#x200B;の組み合わせを定義することで、web サイトでのコンテンツのレンダリング方法を指定します。
   1. **[!UICONTROL ドメイン正規表現]**（例：`/^(?!.*\b(store|help|admin)\b)/`）を入力します。 `/` を使用して、正規表現をエスケープする必要があります。 ドメイン正規表現は、これらのパラメーターが適用される URL を示します。 たとえば、複数のサイトがあり、各サイトのコンテンツを異なるパラメーターが駆動します。 クエリパラメーターがすべてのページに適用される場合、`.*` を使用してすべてのページを示すことができます。
   1. **[!UICONTROL クエリパラメーター]**&#x200B;のコンマ区切りリスト（例：`outdoors, patio, kitchen`）を指定します。
1. ドメイン正規表現とクエリパラメーターの組み合わせを削除する場合は、「**[!UICONTROL 削除]**」を選択します。
1. 正規表現とクエリパラメーターの別の組み合わせを追加する場合は、「**[!UICONTROL 正規表現を追加]**」を選択します。


#### 実装された設定 {#implemented-experiences-configuration}

実装された設定に対して、既存のエクスペリエンスを編集するか新しいエクスペリエンスを含めるには：

![Content Analytics 設定エクスペリエンスの取り込みと定義](../assets/aca-configuration-experience-edit.png)

* 「**[!UICONTROL エクスペリエンスを含める]**」を切り替えて有効または無効にします。

  * Content Analytics イベントデータからエクスペリエンス属性を生成するプロセス
  * Customer Journey Analytics のレポートテンプレート。

* ![編集](/help/assets/icons/Edit.svg) **[!UICONTROL 編集]**&#x200B;を選択して、Content Analyticsでのエクスペリエンスのデータ収集の設定をさらに編集します。 現在の設定に関連付けられたタグプロパティの [Adobe Content Analytics 拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)にリダイレクトされます。

### データ収集 {#web-data-collection}

Data Collection Settingsを使用すると、Content Analyticsで収集するデータ（ページ、アセット）を定義できます。 個人を特定できる情報をデータ収集の一環として収集しないでください。

データ収集を設定するには：

* 既存のweb タグプロパティを使用するか、新しいweb タグプロパティを作成します。

  * 既存のweb タグプロパティを使用するには：

    1. 「**[!UICONTROL 既存のものを選択]**」を選択します。
    2. **[!UICONTROL タグプロパティ]**&#x200B;ドロップダウンメニューから既存のプロパティを選択します。 入力を開始して検索し、使用可能なオプションを制限できます。 別の実装されたContent Analytics設定で既に使用されているTags プロパティを選択することはできません。


  * 新しいweb タグプロパティを作成するには：

    1. 「**[!UICONTROL 新規作成]**」を選択します。
    1. 「**[!UICONTROL タグ名]**」を指定します（例：`ACA Test for Documentation`）。
    1. 「**[!UICONTROL ドメイン]**」を指定します（例：`example.com`）。

    [Content Analytics JavaScript ライブラリ ](/help/content-analytics/config/tags-agnostic.md)を使用して、web チャネルに対してタグに依存しない実装を作成する場合は、新しいTags プロパティを使用します。 Tags プロパティが作成されますが、非依存の実装ではプロパティを使用しません。 ただし、ガイド付き設定ウィザードを少なくとも1回実行する必要があります。

* Content Analytics 用のデータを収集する際に、どのページを含めるか除外するかを指定します。 個人を特定できるページを除外していることを確認します。

  **[!UICONTROL ページに対して**[!UICONTROL &#x200B;正規表現の文字列&#x200B;]**を指定して、含める/除外します]**。 <br/>例：Content Analytics からすべてのドキュメントページを除外する `^(?!.*documentation).*`。

* Content Analytics 用のデータを収集する際に、どのアセットを含めるか除外するかを指定します。 個人を特定できるアセットを除外していることを確認します。

  **[!UICONTROL アセットに含める/除外]**&#x200B;する&#x200B;**[!UICONTROL 正規表現の文字列]**&#x200B;を指定します。 <br/>例：`^(?!.*(logo\.jpg)).*$`コンテンツ分析からすべてのロゴ JPEG 画像を除外する。


### ヘッダーの上書き {#web-header-overrides}

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_header_overrides_boldheader"
>title="ヘッダーの上書き"
>abstract="**ヘッダーの上書き**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_header_overrides_header"
>title="ヘッダーの上書き"
>abstract="ボット検出またはゲートトラフィックをバイパスする高度な機能。 Content Analytics は、エンドポイントを呼び出す際にカスタム HTTP ヘッダーを含めます。"

<!-- needs modification for mobile channel -->

オプションとして、**[!UICONTROL ヘッダーの上書き]** セクションで、ヘッダー名とシークレットヘッダーの値を指定できます。  このヘッダーの上書き設定により、Content Analyticsがカスタム HTTP ヘッダーを送信して、実装したボット検出やトラフィックゲーティングテクノロジーをバイパスできるようになります。

![ ヘッダーがセクション ](/help/content-analytics/assets/aca-configuration-header-overrides.png)を上書きします

1. **[!UICONTROL ヘッダーオーバーライドの設定]**&#x200B;を有効にします。
1. **[!UICONTROL ヘッダー名]**&#x200B;を入力します。 例：`x-asset-service`。
1. **[!UICONTROL ヘッダー値]**&#x200B;を入力します。 指定した内容は秘密鍵であり、ユーザーインターフェイスには表示されません（入力時に![表示](/help/assets/icons/Visibility.svg)値を明示的に開示することを選択しない限り）。




### 保存 {#web-save}

Web チャネルの詳細を指定したら、**[!UICONTROL 保存]**&#x200B;を選択して設定を保存します。 設定をキャンセルするには、**[!UICONTROL キャンセル]**&#x200B;を選択します。

+++

#### 有料メディア {#paid-media}

>[!CONTEXTUALHELP]
>id="aca_onboarding_paidmedia_adplatforms_nosourceconnectors"
>title="ソースコネクタなし"
>abstract="有料メディアには、広告パブリッシャー向けの Experience Platform ソースコネクタが必要です。 このサンドボックスでは、Google 広告または Meta 広告のコネクタは使用できません。 **[!UICONTROL Experience Platform]**／**[!UICONTROL ソース]**&#x200B;インターフェイスでこれらのコネクタを 1 つ以上設定し、この手順に戻ってコンテンツ分析の有料メディアの設定を続行します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/advertising/ads" text="Google 広告ソース"

+++ 詳細

>[!NOTE]
>
>有料メディアチャネルは、AWS上のCustomer Journey AnalyticsおよびExperience Platformのデプロイメントでは使用できません。


有料メディアチャネルの場合、設定されたサンドボックスに接続されているすべてのサポート対象[ad platforms](#paidmedia-adplatforms)がContent Analyticsに自動的に含まれます。

### 広告プラットフォーム {#paidmedia-adplatforms}

ペイドメディアでは、Experience Platform ソースコネクタを広告パブリッシャーに設定する必要があります。

**[!UICONTROL サポートされているソースコネクタが見つからない]**&#x200B;と表示される場合は、設定したサンドボックスで使用可能な広告プラットフォームのソースコネクタを設定していません。

![ ソースコネクタが設定されていません](/help/content-analytics/assets/aca-paid-media-no-source-connectors.png)

広告プラットフォームのソースコネクタを設定するには、**[!UICONTROL AEP ソースに移動]**&#x200B;を選択します。 Experience Platformの&#x200B;**[!UICONTROL Sources]** インターフェイスにリダイレクトされます。

Google AdsとMeta Ads ソースコネクタの設定方法の例については、以下を参照してください。

>[!BEGINTABS]

>[!TAB Google 広告]

1. Experience Platform > **[!UICONTROL ソース]**&#x200B;で、**[!UICONTROL Google Ads]** カードの&#x200B;**[!UICONTROL 設定]**&#x200B;を選択して、セットアップウィザードを開始します。

   >[!WARNING]
   >
   >**Google Ads （ベータ版）** カードで&#x200B;**[!UICONTROL Setup]**&#x200B;を使用しないでください。


1. ウィザードの➊ **[!UICONTROL 認証]** ステップで、**[!UICONTROL 新しいアカウント]**&#x200B;を選択し、**[!UICONTROL アカウント名]**&#x200B;を入力します。

   ![Google Ads ソースコネクタ認証手順1](../assets/paid-media-google-authentication-1.png)

1. **[!UICONTROL Googleでログイン]** ダイアログで、Google Ads Manager アカウントとGoogle Ads アカウントを保持するアカウントを選択します。

   ![Google Ads ソースコネクタ認証手順2](../assets/paid-media-google-authentication-2.png)

1. パスキーまたはその他の認証メカニズムを使用して、資格情報を確認します。

   ![Google Ads ソースコネクタ認証手順3](../assets/paid-media-google-authentication-3.png)

1. ダイアログ **[!UICONTROL Adobe Experience PlatformがGoogle アカウント]**&#x200B;へのアクセスを求めている場合は、**[!UICONTROL 続行]**&#x200B;を選択します。

   ![Google Ads ソースコネクタ認証手順4](../assets/paid-media-google-authentication-4.png)

1. 認証が成功すると、ウィザードの➊ **[!UICONTROL 認証]** ステップに![CheckmarkCircle](/help/assets/icons2/CheckmarkCircle.svg) **[!UICONTROL Connected]**&#x200B;が表示されます。

   ![Google Ads ソースコネクタ認証手順5](../assets/paid-media-google-authentication-5.png)

   「**[!UICONTROL 次へ]**」を選択します。

1. ウィザードの➋ **[!UICONTROL データフローの詳細]** ステップで、**[!UICONTROL データフロー]**&#x200B;の名前を入力します。 また、アラートを購読するオプションを確認することもできます。

   ![Google Ads ソースコネクタデータフローの詳細](../assets/paid-media-google-dataflow-1.png)

   「**[!UICONTROL 次へ]**」を選択します。

1. ウィザードの➌ **[!UICONTROL レビュー]** ステップで、ソースコネクタの詳細を確認します。

   ![Google Ads ソースコネクタのレビュー](../assets/paid-media-google-review-1.png)

   「**[!UICONTROL 完了]**」を選択します。

1. 正常に設定されたGoogle ソースコネクタの詳細が表示されます。

   ![Google Ads ソースコネクタの最終版](../assets/paid-media-google-final.png)


>[!TAB Meta Ads]

1. Experience Platform > **[!UICONTROL ソース]**&#x200B;で、**[!UICONTROL Meta Ads]** カードの&#x200B;**[!UICONTROL 設定]**&#x200B;を選択して、セットアップウィザードを開始します。

1. ウィザードの➊ **[!UICONTROL 認証]** ステップで、**[!UICONTROL 新しいアカウント]**&#x200B;を選択し、**[!UICONTROL アカウント名]**&#x200B;を入力します。

   ![Meta Ads ソースコネクタ認証手順1](../assets/paid-media-meta-authentication-1.png)

1. Ads Managerを設定したFacebook アカウントにログインします。 既にログインしている場合は、ログインしているユーザーとしてダイアログが表示されます。

   ![Meta Ads ソースコネクタ認証手順2](../assets/paid-media-meta-authentication-2.png)

1. 認証が成功すると、ウィザードの➊ **[!UICONTROL 認証]** ステップに![CheckmarkCircle](/help/assets/icons2/CheckmarkCircle.svg) **[!UICONTROL Connected]**&#x200B;が表示されます。

   ![Meta Ads ソースコネクタ認証手順3](../assets/paid-media-meta-authentication-3.png)

   「**[!UICONTROL 次へ]**」を選択します。

1. ウィザードの➋ **[!UICONTROL アカウントの選択]**&#x200B;手順で、設定するアカウントを選択します。

   ![Meta Ads ソースコネクタでアカウントを選択](paid-media-meta-select-account.png)

   「**[!UICONTROL 次へ]**」を選択します。

1. ウィザードの➌ **[!UICONTROL データフローの詳細]** ステップで、**[!UICONTROL データフロー]**&#x200B;の名前を入力します。 また、アラートを購読するオプションを確認することもできます。

   ![Meta Ads ソースコネクタデータフロー](../assets/paid-media-meta-dataflow-1.png)

   「**[!UICONTROL 次へ]**」を選択します。

1. ウィザードの➍ **[!UICONTROL レビュー]** ステップで、ソースコネクタの詳細を確認します。

   ![Meta Ads ソースコネクタのレビュー](../assets/paid-media-meta-review-1.png)

1. 正常に設定されたGoogle ソースコネクタの詳細が表示されます。

   ![Meta Ads ソースコネクタの最終版](../assets/paid-media-meta-final.png)

>[!ENDTABS]

有料メディアチャネルでサポートされているソースコネクタについて詳しくは、[Source コネクタの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/home)を参照してください。

Experience Platformでソースコネクタを設定したら、「![更新](/help/assets/icons/Refresh.svg) **[!UICONTROL 更新]**」を選択して、ソースコネクタのリストを更新します。

使用可能な広告プラットフォームのリストと、これらのプラットフォームのうち![StatusGreen](/help/assets/icons/StatusGreen.svg) **Connected**&#x200B;と![StatusGray](/help/assets/icons/StatusGray.svg) **設定なし**&#x200B;が表示されます。

![Google コネクタが設定されました](/help/content-analytics/assets/aca-paid-media-google-source-connectors.png)


### データの動作 {#paidmedia-databehavior}

**[!UICONTROL Save]**&#x200B;を選択すると、Content Analyticsは自動的に次の操作を行います。

* Customer Journey Analytics接続を更新して、このサンドボックスに接続されているすべてのソースコネクタからの有料メディアデータセットを含めます。
* 選択したすべてのデータビューで有料メディアのディメンションと指標を有効にします。
* Workspace レポートで有料メディアチャネルをフィルタリング可能なディメンションとして表示します。

### 保存 {#paidmedia-save}

**[!UICONTROL 保存]**&#x200B;を選択して、**[!UICONTROL 有料メディア]**&#x200B;設定を保存します。


+++

### 概要 {#summary}

必要な詳細をすべて入力すると、作成または変更されたアーティファクトの詳細が概要に表示されます。

* 新しいコンフィギュレーションを実装する際に、**[!UICONTROL Content Analytics]**&#x200B;のコンフィギュレーション名&#x200B;_を実装する準備ができました。_

* 既に実装されている設定の場合は、**[!UICONTROL Content Analytics 用の&#x200B;_設定名_を実装しました]**&#x200B;という概要が表示されます。

![Content Analytics 設定の概要](../assets/aca-configuration-summary.png)

### アクション {#actions}

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="実装の確認"
>abstract="「**[!UICONTROL 実装]**」を選択した場合は、このワークフローで指定した入力に基づいて Content Analytics を設定します。 Content Analytics に一般的に役立つ内容に基づいて、いくつかの設定がデフォルトで選択されていますが、データ管理者であるあなたは、各アーティファクトの設定を見直し、プライバシーポリシー、契約上の権利と義務、適用法に基づく同意要件に従って設定が実装されていることを確認する必要があります。<br/><br/>この設定に関連付けられたタグライブラリを手動で公開するまで、データは収集されません。<br/><br/>画像やテキストの属性を取得するために、アドビでは、次を使用して属性を取得します。<ol><li>設定したデータ収集設定に従って、ユーザーのサイト訪問時に取得されるページの URL。</li><li>画像がホストされる URL。</li></ol>サードパーティのサイトでホストされる画像にタグを付けないでください。"

設定を作成または編集する際には、次のオプションがあります。

* **[!UICONTROL 破棄]**：設定の一環として行ったすべての変更は破棄されます。
* **[!UICONTROL 後のために保存]**：設定に行った変更が保存されます。 さらに変更を加えたり、設定を実装したりするには、後の段階で再検討してください。 設定を保存するには、[!UICONTROL 名前]の値のみが必要です。
* **[!UICONTROL 実装]**：設定に行った設定または変更が保存および実装されます。 ![必須](/help/assets/icons/Required.svg)としてマークされたすべてのフィールドには、適切な値が必要です。 実装は次で構成されます。

  * **[!UICONTROL Customer Journey Analytics]** 設定：
    * 選択したデータビューが更新され、Content Analytics ディメンションと指標が含まれます。
    * 選択したデータビューに関連付けられた接続を変更すると、Content Analytics イベントと属性データセットが含まれます。
    * Content Analytics レポートテンプレートが Workspace に追加されます。


  * **[!UICONTROL Adobe Experience Platform]** 設定：
    * Content Analytics イベント、アセット属性および（設定した場合）エクスペリエンス属性をモデル化するスキーマの作成。
    * Content Analytics イベント、アセット属性および（設定した場合）エクスペリエンス属性を収集するデータセットの作成。
    * フィーチャライゼーションサービスを使用して Content Analytics イベントからコンテンツ属性を生成および更新するデータフローの作成。


  * **[!UICONTROL データ収集]**&#x200B;設定：
    * Content Analytics データ収集をサポートするように構成された、新規または既存のタグプロパティ。 つまり、この設定には、タグ用の Adobe Content Analytics 拡張機能が含まれます。
    * Content Analytics イベント用のデータストリームが作成されます。
    * Adobe Content Analytics 拡張機能を設定すると、Content Analytics イベントが Content Analytics 用のデータストリームに送信されます。
    * Web SDKまたはMobile SDKがTags プロパティ用に設定されていない場合は、新しいWeb SDKまたはMobile SDK設定が作成され、Content Analytics イベントのみが送信されます。
    * Web SDKまたはMobile SDKがTags プロパティ用に設定されている場合、既存のWeb SDKまたはMobile SDK設定は変更されません。


* **[!UICONTROL 保存]**：実装した設定に行った変更は保存され、実装が更新されます。
* **[!UICONTROL 終了]**。 ガイド付き設定を終了します。 実装した設定に行ったすべての変更は破棄されます。


## 公開 {#publish}

Content Analytics設定のデータ収集を開始するには、有効にしたチャネルの作成されたタグプロパティを[手動で](manual.md)公開する必要があります。


>[!MORELIKETHIS]
>
>[手動設定](manual.md)
>

