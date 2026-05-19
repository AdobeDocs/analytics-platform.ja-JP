---
title: B2B アカウントの連携
description: Adobe Customer Journey AnalyticsのB2B アカウント合成を利用して、イベントデータセットをアカウント情報で強化し、B2B データ全体のジャーニー分析を可能にする方法をご確認ください。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
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
source-git-commit: ff99ee131e9bae9fc2815fb54e5b5c14577450f7
workflow-type: tm+mt
source-wordcount: 994
ht-degree: 2%

---

# B2B アカウントの連携

B2B アカウントをつなぎ合わせることで、イベントデータセットをアカウント情報で強化し、Customer Journey Analyticsのカスタマージャーニー全体を包括的に分析できます。 Customer Journey Analytics B2B editionが取り込みに必要とするアカウント IDがイベントに欠落している場合、アカウントの結合は、指定した[人物とアカウントのマッピングデータセット &#x200B;](#prerequisites)を使用して、その情報を自動的に導き出し、追加します。

アカウントをつなぎ合わせないと、アカウント IDを含まないイベントは取り込み中にドロップされます。 アカウントの結合は、イベントが取り込まれる際と過去にさかのぼってアカウント IDを追加することで、各イベントの人物に関連付けられたアカウントを検索することでこの障壁を排除します。

>[!NOTE]
>
>B2B アカウントの結合には、機能を設定する前に、お客様の環境で[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)の使用権限が必要です。

アカウントの結合では、データセットに対して次の操作が実行されます。

* **人物IDを昇格**：各イベントの人物IDは、ID グラフを使用して、目的のID名前空間に昇格されます。
* **欠落しているアカウント情報を追加**：人物IDを含むイベントの場合、[人物とアカウントのマッピング &#x200B;](#prerequisites)を使用して、アカウント情報を取得および追加します。 イベント自体のアカウント情報は、フォールバックメソッドとして使用されます。

## 前提条件

B2B アカウントの結合を有効にする前に、Adobe Experience Platformで次のデータセットを準備します。

| データセット | 必須 | 説明 |
|---|---|---|
| **個人からアカウントへのデータセット** | 必須 | 少なくともユーザーID （名前空間を含む）とアカウント IDを含むルックアップ（レコード、非時系列）データセット。 これらのIDは、個人とアカウントの関係マップを導き出すために使用されます。 |

>[!IMPORTANT]
>
>**[!UICONTROL 人物からアカウント]** データセットの人物ID フィールドは、スキーマでIDとしてマークする必要があります。

## アカウントの結合を有効にする

接続レベルでB2B アカウントステッチを有効にして設定し、その接続内の個々のイベントデータセットに対するアカウントステッチを有効にします。

### B2B ステッチ設定の設定

1. Customer Journey Analyticsで、**[!UICONTROL Connections]**&#x200B;に移動し、[新しい接続を作成](/help/connections/create-connection.md#create-a-connection)するか、[既存の接続を編集](/help/connections/create-connection.md#edit-a-connection)します。

1. **[!UICONTROL Connection settings]**&#x200B;で、**[!UICONTROL プライマリID]**&#x200B;を![Building](/help/assets/icons/Building.svg) **[!UICONTROL Account]**&#x200B;に設定します。

1. 「**[!UICONTROL B2B ステッチ設定を開く]**」を選択します。

   ![B2B アカウント結合設定](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >未保存の接続に対して以前に設定されたB2B ステッチ設定は、**[!UICONTROL _未保存の変更_]**&#x200B;と共に示されます。 以前に設定したB2B ステッチ設定の&#x200B;**[!UICONTROL オプションのコンテナ]**&#x200B;を変更することはできません。

1. **[!UICONTROL B2B ステッチ設定]** ダイアログで、次の操作を行います。

   ![B2B ステッチ設定](assets/b2b-stitching-configuration.png)

   1. 「**[!UICONTROL ユーザー]**」セクションを設定します。

      * 任意の人物IDを昇格させたい&#x200B;**[!UICONTROL 人物ID名前空間]** （例：**[!UICONTROL 電子メール]**）を選択します。 このフィールドは必須です。

   1. 「**[!UICONTROL ユーザーからアカウント]**」の下の「**[!UICONTROL アカウント]**」セクションを設定します。

      | フィールド | 必須 | 説明 |
      |---|:---:|---|
      | **[!UICONTROL アカウント データセットへの人物]** | ![必須](/help/assets/icons/Required.svg) | 個人をアカウントにマッピングするルックアップ（レコードまたは非時系列データセット）を選択します。 |
      | **[!UICONTROL 人物フィールド]** | ![必須](/help/assets/icons/Required.svg) | ユーザーIDを含むデータセット内のフィールドを選択します。 このフィールドはIDとしてマークする必要があり、**[!UICONTROL アカウント]** フィールドまたは&#x200B;**[!UICONTROL 開始時間]** フィールドと同じにすることはできません。 |
      | **[!UICONTROL アカウントフィールド]** | ![必須](/help/assets/icons/Required.svg) | アカウント IDを含むデータセットのフィールドを選択します。 このフィールドは、**[!UICONTROL 人物]** フィールドまたは&#x200B;**[!UICONTROL 開始時間]** フィールドと同じにすることはできません。 |
      | **開始時間フィールド** | | 個人とアカウントの関係がいつアクティブになったかを示すタイムスタンプフィールドを選択します。 |

      >[!NOTE]
      >
      >フィールドオプションの読み込み中にエラーが発生した場合、ドロップダウンメニューは空になり、影響を受ける各フィールドの下にエラーインジケーターが表示されます。 データセットスキーマを確認して、もう一度試してください。

   1. **[!UICONTROL 保存]**&#x200B;を選択して&#x200B;**[!UICONTROL B2B ステッチ設定]** ダイアログを閉じ、接続設定に戻ります。

   1. **[!UICONTROL _未保存の変更_]** インジケーターは、[接続を保存](#save)するまで、**B2B ステッチ設定を開く** ボタンの横に表示されます。


### イベントデータセットのB2B合成を有効にする

接続レベルでB2B ステッチを設定した後、ステッチするイベントデータセットごとに個別にB2B アカウントステッチを有効にする必要があります。

1. 接続設定で、**[!UICONTROL データセットを追加]**&#x200B;を選択するか、既存のイベントデータセットの設定を開きます。<br/>詳細については、[&#x200B; データセットの追加](/help/connections/create-connection.md#add-datasets)または[&#x200B; データセットの編集](/help/connections/create-connection.md#edit-a-dataset)を参照してください。

1. B2B アカウントのステッチを設定する特定のイベントデータセットの場合は、**[!UICONTROL 人物のアカウントへのステッチを有効にする]**&#x200B;に切り替えます。

>[!BEGINTABS]

>[!TAB Tab]

**[!UICONTROL 人物のアカウント結合を有効にする]**&#x200B;が&#x200B;**on**&#x200B;の場合、データセットのB2B アカウント結合を設定しました。

* 人物IDの設定が必要です。 その人物IDは、[人物とアカウントのデータセット &#x200B;](#prerequisites)に基づいてアカウント IDを検索するために使用されます。
* アカウント IDの設定はオプションです。

![&#128279;](assets/b2b-event-dataset-stitching-on.png)のイベントデータセットでB2B アカウントを結合しています

>[!TAB  オフ ]

**[!UICONTROL 人物のアカウント結合を有効にする]**&#x200B;が&#x200B;**off**&#x200B;の場合、データセットに対して&#x200B;*not*&#x200B;のB2B アカウント結合が設定されています。

* アカウント IDの設定が必要です。
* 人物IDの設定はオプションです。

![&#x200B; イベントデータセットでB2B アカウントを結合](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### 保存

B2B ステッチ設定を設定し、データセットの追加または編集を完了したら、**[!UICONTROL 保存]**&#x200B;を選択して接続を保存します。

>[!IMPORTANT]
>
>接続が保存されると、B2B ステッチ設定は不変になります。 保存後に設定を表示するには、**B2B ステッチ設定を開く**&#x200B;を選択します。 すべてのフィールドは読み取り専用の状態で表示されます。 さらに、[個人とアカウントのマッピング &#x200B;](#prerequisites)に使用されているデータセットがExperience Platformで削除された場合、この接続は削除されます。

## データ更新スケジュール

アカウントの結合は、毎日[個の個人とアカウントのデータセット &#x200B;](#prerequisites)からID マップを取得し、この情報を使用して、次のスケジュールで結合が有効なデータセットを更新します。

| 再生 | 頻度 | データウィンドウ |
|---|---|---|
| 短期的 | 毎週 | 過去 7 日間 |
| 長期的 | 毎月 | 最近の 3 か月間 |

## プライバシーとデータの健全性

アカウントステッチングは、B2Cのステッチ行動と一致して、個人IDに対する標準的なプライバシーとハイジーンの要求を尊重します。 後でプライバシーリクエストまたはハイジーンリクエストを通じて個人IDが削除された場合、ID グラフを使用して実行された関連付けられたステッチは元に戻されます。

アカウント、アカウント ID、グローバルアカウント IDなどのB2B エンティティは、ステッチを介してイベントに追加されても、プライバシーまたはハイジーン要求の一部として削除されません。 これらの価値には個人を特定できる情報が含まれていないため、これらの価値を削除する法的義務はありません。

>[!MORELIKETHIS]
>
>* [&#x200B; ステッチの概要](overview.md)
>* [B2Bへの接続を設定](../connections/create-connection.md)
>* [&#x200B; ステッチに関するよくある質問](faq.md)

