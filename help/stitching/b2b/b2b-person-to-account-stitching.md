---
title: B2Bの個人とアカウントの照合
description: Adobe Customer Journey Analyticsが提供するB2Bの個人とアカウントの結び付けにより、イベントデータセットをアカウント情報で強化し、B2B データ全体のジャーニー分析を可能にする方法をご確認ください。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2:
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: e3936b74ba4b4cf23e1b7235e545091a8cb546ed
workflow-type: tm+mt
source-wordcount: 2116
ht-degree: 15%

---

# B2B担当者とアカウントの連携

B2Bの個人と企業の結合により、イベントデータセットをアカウント IDで強化し、Customer Journey Analyticsのカスタマージャーニー全体を通じて包括的に分析できます。 Customer Journey Analytics B2B editionが取り込みに必要とするアカウント IDがイベントに含まれていない場合、個人とアカウントの結合は、ユーザーが指定した[個人とアカウントのマッピングデータセット &#x200B;](#prerequisites)を使用して自動的に導き出され、その情報が追加されます。

個人からアカウントへのステッチが行われない場合、アカウント IDを含まないイベントは取り込み中にドロップされます。 個人からアカウントへのステッチでは、各イベントで個人に関連付けられたアカウントを検索し、イベントが取り込まれる際と過去にさかのぼってアカウント IDを追加することで、この制限を解決します。

>[!NOTE]
>
>B2B ユーザーとアカウントのステッチを行うには、この機能を設定する前に、環境内の[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)の使用権限が必要です。

個人からアカウントへのステッチングでは、データセットに対して次の操作を実行します。

* **人物IDを昇格**: [B2C ステッチ アプローチ &#x200B;](/help/stitching/overview.md)と同様に、永続的な人物IDを保持するフィールドを設定します。 ID グラフを使用して、各イベントの永続的なユーザーIDを、設定されたユーザーID名前空間からユーザーIDに昇格します。
* **欠落しているアカウント IDを追加**: イベントの人物ID情報を取得した後、[人物とアカウントのマッピング &#x200B;](#prerequisites)を使用して、アカウント ID情報を取得して追加します。 イベント自体で使用可能なすべてのアカウント IDは、フォールバックメソッドとして使用されます。

## B2B バイヤーとアカウントの連携方法

B2Bの個人と企業のバイヤーズジャーニーのステッチングがどのように機能するのかを示すために、以下に示すデータセットをベースとして使用します。

### ベースイベントデータセット

Customer Journey Analytics B2B editionでは、このステッチされていないイベントデータセットの例にアカウント IDのないイベントは無視され、取り込まれません（![DeleteOutline](/help/assets/icons/DeleteOutline.svg)）。

| アクション | タイムスタンプ | 永続的 ID | アカウント ID | ユーザー ID | イベントタイプ |
|:---:|--:|--|---|---|---|
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 1/3/25 | 1234 | Adobe | matt@adobe.com | Page view |
| ![FilterDelete](/help/assets/icons/DeleteOutline.svg) | 1/3/25 | 5678 |  | | |
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 3/4/25 | 9012 | Ubiquity | cory@sky.com |  |
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 3/7/25 | 4321 | 空 | emily@sky.com | コールセンター |
| ![FilterDelete](/help/assets/icons/DeleteOutline.svg) | 5/5/25 | 6106 | | carmen@adobe.com |  |
| ![DataAdd](/help/assets/icons/DataAdd.svg) | 6/1/25 | 8989 | Ubiquity | cassidy@ubiquity.com | |
| ![FilterDelete](/help/assets/icons/DeleteOutline.svg) | 6/2/25 | 1111 |  | | |

B2B ユーザーからアカウントへのステッチングは、次の操作を使用してイベントが無視され、取り込まれないようにします。

* [人物IDを昇格](#elevate-person-identities)。
* [見つからないアカウント IDを追加](#add-missing-account-identitiers)。


### 個人IDの向上

+++ 詳細

B2Bの個人とアカウントの結合をサポートするには、個人とアカウントのマッピングデータセットを提供します。 次に例を示します。

| CRM ID | アカウント ID |
|---|---|
| 12hsd123 | Adobe |
| f82jsd32 | 空 |
| hg2023m2 | 空 |
| b978bbw9 | Ubiquity |
| fs453ghi | Adobe |

グラフベースの合成により、個人と企業のマッピングデータセットが向上します。 例えば、使用する名前空間としてメールを指定します。 その結果、昇格された人物IDを持つ更新された個人とアカウントのマッピングデータセットが得られます。

| CRM ID | 昇格されたユーザーID | アカウント ID |
|---|---|---|
| 12hsd123 | matt@adobe.com | Adobe |
| f82jsd32 | emily@sky.com | 空 |
| hg2023m2 | cory@sky.com | 空 |
| b978bbw9 | cassidy@ubiquity.com | Ubiquity |
| fs453ghi | carmen@adobe.com | Adobe |

グラフベースの合成は、エクスペリエンスイベントデータセットの人物IDを昇格するためにも使用されます。 例えば、**emily@adobe.com**&#x200B;の更新された値を参照してください。

グラフベースの合成は、エクスペリエンスイベントデータセットの人物IDを昇格するためにも使用されます。 例えば、[&#x200B; データセット &#x200B;](#enable-b2b-person-to-account-stitching-on-event-datasets)でステッチを有効にする際に、永続的なユーザーID （ECID）フィールドを永続的なユーザーIDとして使用するように設定します。 ECID値として`5678`、Email値として`emily@adobe.com`に基づいて、`emily@adobe.com`は関連イベントで昇格した人物IDとして設定されます。

| タイムスタンプ | 永続的 ID | 元のアカウント ID | 元のユーザーID | 昇格されたユーザーID |
|--|--|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | matt@adobe.com |
| 1/3/25 | 5678 |  | | **emily@adobe.com** |
| 3/4/25 | 9012 | Ubiquity | cory@sky.com | cory@sky.com |
| 3/7/25 | 4321 | 空 | emily@sky.com | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | carmen@adobe.com |
| 6/1/25 | 8989 | Ubiquity | cassidy@ubiquity.com | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 111 | 111 |


+++

### 見つからないアカウント IDを追加

+++ 詳細

個人からアカウントへのデータセットは、エクスペリエンスイベントデータセットのアカウント IDを昇格するために再度使用されます。 例えば、emily@sky.comの場合は&#x200B;**Sky**、carmen@adobe.comの場合は&#x200B;**Adobe**&#x200B;の付加値を参照してください。 cory@sky.comの値&#x200B;**Sky** （Ubiquityから）が更新されました。

| タイムスタンプ | 永続的 ID | 元のアカウント ID | 元のユーザーID | 昇格されたアカウント ID | 昇格されたユーザーID |
|---|---|---|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | Adobe | matt@adobe.com |
| 1/3/25 | 5678 | | | **空** | **emily@sky.com** |
| 3/4/25 | 9012 | Ubiquity | cory@sky.com | **空** | cory@sky.com |
| 3/7/25 | 4321 | 空 | emily@sky.com | 空 | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | **Adobe** | carmen@adobe.com |
| 6/1/25 | 8989 | Ubiquity | cassidy@ubiquity.com | Ubiquity | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 1111 |  | 1111 |

+++

### 結果

この例では、入力として指定した個人とアカウントのマッピングデータセットに基づいて、欠落している個人IDまたは欠落しているアカウント IDと正しくないアカウント IDを使用して、B2Bの個人とアカウントの結合がエクスペリエンスイベントデータを更新する方法を示します。


## 前提条件

B2B ユーザーによるアカウント結合を有効にする前に、Adobe Experience Platformで次のデータセットを準備します。

| データセット | 必須 | 説明 |
|---|---|---|
| **個人からアカウントへのデータセット** | 必須 | 少なくともユーザーID （名前空間を含む）とアカウント IDを含むルックアップ（レコード、非時系列）データセット。 これらのIDは、個人とアカウントの関係マップを導き出すために使用されます。 |

>[!IMPORTANT]
>
>**[!UICONTROL 人物からアカウント]** データセットの人物ID フィールドは、スキーマでIDとしてマークする必要があります。

## ユーザーとアカウントのステッチを有効にする {#enable-account-stitching}

まず、接続レベルでB2B ステッチを有効にして設定します。 接続用にB2B ステッチが設定されている場合、その接続内の個々のイベントデータセットに対して個人からアカウントへのステッチをアクティベートできます。

### アカウントのステッチ設定にB2B人物を設定する {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="B2B ステッチの設定"
>abstract="「**[!UICONTROL B2B ステッチ設定を開く]**」を選択して、B2B ユーザーをアカウント ステッチに設定します。 接続がまだ保存されていない場合、設定には「**[!UICONTROL _保存されていない変更_]**」というラベルが付けられます。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="ユーザー識別子の名前空間"
>abstract="レポートに最も関連性の高いユーザー ID 名前空間を選択します。 例：メール。 **[!UICONTROL 人物からアカウントへのステッチ]**&#x200B;が有効になっているイベントデータセットでは、永続的な人物IDがこの人物ID名前空間に昇格されます。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="ユーザーとアカウントをマッピングするデータセット"
>abstract="ユーザー ID をアカウント ID にマッピングする参照データセットを選択します。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="ユーザー ID"
>abstract="ユーザー ID を含むデータセット内のフィールドを選択します。 このフィールドの名前空間は、選択したユーザー識別子名前空間と異なるか、同じである場合があります。 異なる場合は、2 つの名前空間を ID グラフでリンクする必要があります。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="アカウント ID"
>abstract="一意のアカウント識別子の値を含むデータセットのフィールドを選択します。 アカウント ID情報は、**[!UICONTROL 人物とアカウントの結合]**&#x200B;が有効になっているイベントデータセットの行で利用できるようになります。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="開始時間"
>abstract="ユーザーとアカウントの関係がいつアクティブになったかを示す「タイムスタンプ」フィールドを選択します。"


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_mapping_creation_time"
>title="マッピング作成時間"
>abstract="オプションで、アカウントへの個人マッピングが作成された日時を表すフィールドを選択します。 人が複数のアカウントを時間をかけて切り替える場合に役立ちます。"


1. Customer Journey Analyticsで、**[!UICONTROL Connections]**&#x200B;に移動し、[新しい接続を作成](/help/connections/create-connection.md#create-a-connection)します。

1. **[!UICONTROL Connection settings]**&#x200B;で、**[!UICONTROL プライマリID]**&#x200B;を![Building](/help/assets/icons/Building.svg) **[!UICONTROL Account]**&#x200B;に設定します。

1. B2B接続で使用する&#x200B;**[!UICONTROL オプションのコンテナ]**&#x200B;を選択してください。 B2B ユーザーをアカウント ステッチ設定に保存した後は、これらのコンテナの選択を変更することはできません。

1. 「**[!UICONTROL B2B ステッチ設定を開く]**」を選択します。

   ![B2B アカウント結合設定](../assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >未保存の接続のステッチ設定を考慮するように以前に設定されたB2B ユーザーは、**[!UICONTROL _未保存の変更_]**&#x200B;と共に示されます。 以前に設定したB2B ユーザーの&#x200B;**[!UICONTROL オプションのコンテナ]**&#x200B;をアカウント ステッチ設定に変更することはできません。

1. **[!UICONTROL B2B ステッチ設定]** ダイアログで、次の操作を行います。

   ![B2Bの人物からアカウントへのステッチ設定](../assets/b2b-stitching-configuration.png)

   1. 「**[!UICONTROL ユーザー]**」セクションを設定します。

      * 電子メールなど、レポートに最も関連性の高い人物ID名前空間を選択します。 個人からアカウントへのステッチが有効になっているイベントデータセットでは、永続的な個人IDがこの個人ID名前空間に昇格されます。 このフィールドは必須です。

   1. 「**[!UICONTROL ユーザーからアカウント]**」の下の「**[!UICONTROL アカウント]**」セクションを設定します。

      | フィールド | 必須 | 説明 |
      |---|:---:|---|
      | **[!UICONTROL アカウント データセットへの人物]** | ![必須](/help/assets/icons/Required.svg) | 個人をアカウントにマッピングするルックアップ（レコードまたは非時系列データセット）を選択します。 |
      | **[!UICONTROL ユーザー ID]** | ![必須](/help/assets/icons/Required.svg) | ユーザー ID を含むデータセット内のフィールドを選択します。 このフィールドはIDとしてマークする必要があり、**[!UICONTROL アカウント ID]** フィールドまたは&#x200B;**[!UICONTROL 開始時間]** フィールドと同じにすることはできません。 |
      | **[!UICONTROL アカウント ID]** | ![必須](/help/assets/icons/Required.svg) | アカウント ID を含むデータセットのフィールドを選択します。 このフィールドは、**[!UICONTROL 人物ID]** フィールドまたは&#x200B;**[!UICONTROL 開始時間]** フィールドと同じにすることはできません。 |
      | **作成時間のマッピング** | | オプションで、アカウントへの個人マッピングが作成された日時を表すフィールドを選択します。 人が複数のアカウントを時間をかけて切り替える場合に役立ちます。<br/><br/>**例** （**update_date** フィールドが選択されている場合）:<table><thead><tr><th>update_date</th><th>ユーザー</th><th>account</th></tr></thead><tbody><tr><td>20260401</td><td>a@b.com</td><td>Apple</td></tr><tr><td>20260501</td><td>a@b.com</td><td>Adobe</td></tr></tbody></table><ul><li>2026年5月1日より前の&#x200B;**[!UICONTROL update_date]** フィールドにタイムスタンプを持つすべてのイベントの場合：a@b.comはAppleにマッピングされます。</li><li>2026年5月1日以降の&#x200B;**[!UICONTROL update_date]** フィールドにタイムスタンプを持つすべてのイベントの場合：a@b.comはAdobeにマッピングされます。</li></ul>マッピング時間が指定されていない場合は、字形の最初のアカウントが使用されます。 この同じアルゴリズムは、2つの異なるアカウント名がまったく同じ&#x200B;**[!UICONTROL update_date]**&#x200B;値を持ち、マッピング作成時間が指定されている場合にも使用されます。 |

      >[!NOTE]
      >
      >フィールドオプションの読み込み中にエラーが発生した場合、ドロップダウンメニューは空になり、影響を受ける各フィールドの下にエラーインジケーターが表示されます。 データセットスキーマを確認して、もう一度試してください。

   1. **[!UICONTROL 保存]**&#x200B;を選択して&#x200B;**[!UICONTROL B2B ステッチ設定]** ダイアログを閉じ、接続設定に戻ります。

   1. **[!UICONTROL _未保存の変更_]** インジケーターは、[接続を保存](#save)するまで、**B2B ステッチ設定を開く** ボタンの横に表示されます。

### イベントデータセットのアカウント合成をB2B人物に対して有効にする


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="ユーザーとアカウントのステッチを有効にする"
>abstract="有効にすると、このデータセットは B2B ユーザーとアカウントのステッチを使用します。 **[!UICONTROL 永続的な人物ID]**&#x200B;値は、設定された&#x200B;**[!UICONTROL 人物ID名前空間]**&#x200B;から値に昇格され、個人とアカウントのデータセットに基づいてアカウント IDを検索するために使用されます。<br/>無効にした場合、このデータセットではB2B ユーザーからアカウントへのステッチは使用されないので、代わりに必須の&#x200B;**[!UICONTROL アカウント ID]**&#x200B;を選択する必要があります。"
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/b2b/b2b-person-to-account-stitching#configure-b2b-stitching-settings" text="アカウントのステッチ設定にB2B人物を設定する"

接続レベルでB2B ステッチを設定した後、B2Bの人物がステッチを行うイベントデータセットごとに個別にステッチを考慮できるようにする必要があります。

1. 接続設定で、**[!UICONTROL データセットを追加]**&#x200B;を選択するか、既存のイベントデータセットの設定を開きます。<br/>詳細については、[&#x200B; データセットの追加](/help/connections/create-connection.md#add-datasets)または[&#x200B; データセットの編集](/help/connections/create-connection.md#edit-a-dataset)を参照してください。

1. B2B ユーザーをアカウント ステッチに設定する特定のイベント データセットの場合は、**[!UICONTROL ユーザーをアカウント ステッチに有効にする]**&#x200B;をオンに切り替えます。

>[!BEGINTABS]

>[!TAB Tab]

**[!UICONTROL 人物のアカウント合成を有効にする]**&#x200B;が&#x200B;**on**&#x200B;の場合、データセットのアカウント合成にB2B人物を設定しました。

* 人物IDの設定が必要です。 その人物IDは、[人物とアカウントのデータセット &#x200B;](#prerequisites)に基づいてアカウント IDを検索するために使用されます。
* アカウント IDの設定はオプションです。

![B2Bのユーザーが](../assets/b2b-event-dataset-stitching-on.png)のイベントデータセットを結合してアカウントを作成

>[!TAB  オフ ]

**[!UICONTROL 人物のアカウント結合を有効にする]**&#x200B;が&#x200B;**オフ**&#x200B;の場合、データセットの結合をアカウント化するように&#x200B;*not*&#x200B;がB2B人物に設定されています。

* アカウント IDの設定が必要です。
* 人物IDの設定はオプションです。

![B2Bのユーザーがイベントデータセットのステッチをアカウントに追加](../assets/b2b-event-dataset-stitching-off.png)

>[!ENDTABS]


### 保存

B2B ユーザーをアカウント ステッチ設定に設定し、データセットの追加または編集を完了したら、**[!UICONTROL 保存]**&#x200B;を選択して接続を保存します。

>[!IMPORTANT]
>
>接続が保存されると、B2Bの個人とアカウントのステッチ設定は不変になります。 保存後に設定を表示するには、**B2B ステッチ設定を開く**&#x200B;を選択します。 すべてのフィールドは読み取り専用の状態で表示されます。 さらに、[個人とアカウントのマッピング &#x200B;](#prerequisites)に使用されるデータセットがExperience Platformで削除された場合、ステッチ設定は削除され、接続は無効な状態になり、ユーザーインターフェイスに警告メッセージが表示されます。

## データ更新スケジュール

アカウントの結合は、毎日[個の個人とアカウントのデータセット &#x200B;](#prerequisites)からID マップを取得し、この情報を使用して、次のスケジュールで短期と長期の両方の結合が可能なデータセットを更新します。

| 再生 | 頻度 | データウィンドウ |
|---|---|---|
| 短期的 | 毎週 | 過去 7 日間 |
| 長期的 | 毎月 | 過去3か月間（Prime パッケージ） <br/>過去6か月間（Ultimate パッケージ） |

## プライバシーとデータの健全性

アカウントステッチングは、B2Cのステッチ行動と一致して、個人IDに対する標準的なプライバシーとハイジーンの要求を尊重します。 後でプライバシーリクエストまたはハイジーンリクエストを通じて個人IDが削除された場合、ID グラフを使用して実行された関連付けられたステッチは元に戻されます。

アカウント、アカウント ID、ステッチを介してイベントに追加されたグローバルアカウント IDなどのB2B エンティティは、プライバシーまたはハイジーンのリクエスト中に削除されません。 これらの価値には個人を特定できる情報が含まれていないため、これらの価値を削除する法的義務はありません。

>[!MORELIKETHIS]
>
>* [&#x200B; ステッチの概要](../overview.md)
>* [B2Bへの接続を設定](/help/connections/create-connection.md)
>* [&#x200B; ステッチに関するよくある質問](../faq.md)

