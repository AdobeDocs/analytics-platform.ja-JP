---
title: Analytics ソースコネクタの作成とフィールドのマッピング
description: Analytics ソースコネクタを作成しフィールドをマッピングする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 24%

---

# Analytics ソースコネクタの作成とフィールドのマッピング {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="Analytics ソースコネクタの作成"
>abstract="Analytics ソースコネクタを使用して、Customer Journey Analytics で使用するレポートスイートデータを取り込みます。<br><br>デフォルト設定を使用すると、Analytics ソースコネクタの作成には数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="Analytics ソースコネクタの作成とスキーマフィールドのマッピング"
>abstract="ソースコネクタは、Adobe Analytics フィールドを組織のスキーマにマッピングする方法を理解している必要があります。このインターフェイスを使用して、ソースコネクタにそのマッピングを提供します。 この手順は、Customer Journey Analytics に履歴データを追加する手順の一部です。<br><br>この手順にかかる時間は、マッピングする必要があるディメンションと指標の数に大きく依存します。この手順は、退屈で反復的な作業ですが、それほど難しいものではありません。データストリームマッピングが完了するまでに約 1 週間の作業がかかると予想されます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込む方法を説明します

Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータをAdobe Experience Platformに取り込むことができます。 その後、このデータをCustomer Journey Analyticsの履歴データとして使用できます。

ここでは、Customer Journey Analytics Web SDKの実装で使用する [ カスタムスキーマを作成する ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) ことを前提としています。これは、組織のニーズと使用する特定の Platform アプリケーションに合わせて調整される、合理化されたスキーマが必要なためです。

Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込むには、次の操作が必要です。

1. [Analytics ソースコネクタ用のカスタムスキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Analytics ソースコネクタがない場合は、以下に示すように、Analytics ソースコネクタを作成し、フィールドをカスタム web SDK スキーマにマッピングします。

   または

   既に Analytics ソースコネクタがある場合は、[ ソースコネクタのフィールドをカスタム web SDK スキーマにマッピング ](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md) します。

1. [接続への Analytics ソースコネクタデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics ソースコネクタの作成とフィールドのマッピング

カスタムスキーマを作成したら、履歴データに使用するAdobe Analytics ソースコネクタを作成する必要があります。 （ソースコネクタの作成に関する、より包括的な一般的なガイドラインについては、[UI でのAdobe Analytics ソース接続の作成 ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) を参照してください。

履歴データに使用するAdobe Analytics ソースコネクタを作成するには：

1. Platform UI の左パネルの「**[!UICONTROL 接続]**」セクションで、「**[!UICONTROL ソース]**」を選択します。

1. [!UICONTROL カテゴリ]のリストから、**[!UICONTROL Adobe アプリケーション]**&#x200B;を選択します。

1. Adobe Analytics タイル内で「**[!UICONTROL データを追加]**」を選択します。

   ![ 選択されたソースを含むAdobe Experience Platform ウィンドウと、Adobe アプリケーションおよび「データを追加」がハイライト表示されている様子。](./assets/sources-overview.png)

1. **[!UICONTROL レポートスイート]** を選択し、レポートスイートのリストからCustomer Journey Analyticsで使用する履歴データを含むレポートスイートを選択します。

   ![ レポートスイートリストを表示するAdobe Experience Platform ウィンドウ ](./assets/report-suites.png)

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. **[!UICONTROL カスタムスキーマ]** を選択し、[Adobe Analytics フィールドグループを含むカスタムスキーマを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md) で作成したスキーマを選択します。<!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 各Adobe Analytics ディメンションをカスタムスキーマディメンションにマッピングします。

   1. 「**[!UICONTROL 標準フィールドをマッピング]**」セクションで、「**[!UICONTROL カスタム]**」タブを選択します。

   1. 「**[!UICONTROL 新しいマッピングを追加]**」を選択します。

   ![ スキーマフィールドのマッピング ](assets/schema-mapping.png)

   1. 「**[!UICONTROL Source フィールド]**」で、「Adobe Analytics ExperienceEvent テンプレート」フィールドグループからAdobe Analytics フィールドを選択します。 次に、**[!UICONTROL ターゲットフィールド]** で、マッピングする XDM スキーマのカスタムフィールドを選択します。

      AppMeasurementと XDM の間のアーキテクチャの違いにより、すべてのAdobe Analytics フィールドに XDM の対応するフィールドがあるわけではありません。

   1. Adobe Analyticsでのデータ収集に使用するAdobe Analytics ExperienceEvent テンプレートフィールドグループのフィールドごとに、このプロセスを繰り返します。

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. データフローに名前を付け、（オプションで）説明を入力します。

   ![ データフローの詳細セクションを強調表示したAdobe Experience Platform ウィンドウ ](./assets/dataflow-detail.png)

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. 接続を確認し、「**[!UICONTROL 終了]**」を選択します。

   ![ レビュー用に「接続」セクションと「データタイプ」セクションがハイライト表示されたAdobe Experience Platform ウィンドウ ](./assets/review.png)

   接続が作成されると、レポートスイートのAdobe Analytics データをデータセットに入力するデータフローが自動的に作成されます。 データフローは、実稼動用サンドボックスに対して最大 13 か月分の履歴データを取り込みます。 非実稼動用サンドボックスでのバックフィルは、3 か月に制限されています。

   Analytics ソースコネクタを使用して履歴データをCustomer Journey Analytics web SDK実装に取り込む場合は、自動作成されたデータセットを、web SDK実装用に作成した接続に追加する必要があります。

{{upgrade-final-step}}
