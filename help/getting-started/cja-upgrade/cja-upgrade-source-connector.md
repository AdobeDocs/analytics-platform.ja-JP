---
title: Analytics ソースコネクタの作成とフィールドのマッピング
description: Analytics ソースコネクタを作成しフィールドをマッピングする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 0a47796a8b673ef7074a4f9fe865ff59fcf50aab
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 8%

---

# Analytics ソースコネクタの作成とフィールドのマッピング

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

## Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込む方法を理解する

Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータをAdobe Experience Platformに取り込むことができます。 その後、このデータをCustomer Journey Analyticsの履歴データとして使用できます。

ここでは、Customer Journey Analyticsのニーズと使用する特定の Platform アプリケーションに合わせて調整される合理化されたスキーマが必要なので、](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)Platform へのアップグレード時に XDM スキーマを作成 [ できることを前提としています。

Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込むには、次の操作が必要です。

1. [Analytics ソースコネクタ用の XDM スキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Analytics ソースコネクタがまだない場合は、以下に説明するように、Analytics ソースコネクタを作成し、フィールドを XDM スキーマにマッピングします。

   または

   既に Analytics ソースコネクタがある場合は、[ ソースコネクタのフィールドを XDM スキーマにマッピング ](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md) します。

1. [接続への Analytics ソースコネクタデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics ソースコネクタの作成とフィールドのマッピング

XDM スキーマを作成したら、履歴データに使用するAdobe Analytics ソースコネクタを作成する必要があります。 （ソースコネクタの作成に関する、より包括的な一般的なガイドラインについては、[UI でのAdobe Analytics ソース接続の作成 ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) を参照してください。

履歴データに使用するAdobe Analytics ソースコネクタを作成するには：

1. Platform UI の左パネルの「**[!UICONTROL 接続]**」セクションで、「**[!UICONTROL ソース]**」を選択します。

1. [!UICONTROL カテゴリ]のリストから、**[!UICONTROL Adobe アプリケーション]**&#x200B;を選択します。

1. Adobe Analytics タイル内で「**[!UICONTROL データを追加]**」を選択します。

   ![ 選択したソースを含むAdobe Experience Platform ウィンドウと、Adobeアプリケーション、「データを追加」がハイライト表示されています。](./assets/sources-overview.png)

1. **[!UICONTROL レポートスイート]** を選択し、レポートスイートのリストからCustomer Journey Analyticsで使用する履歴データを含むレポートスイートを選択します。

   ![ レポートスイートリストを表示するAdobe Experience Platform ウィンドウ ](./assets/report-suites.png)

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. **[!UICONTROL カスタムスキーマ]** を選択し、[Adobe Analytics フィールドグループを含む XDM スキーマを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md) で作成したスキーマを選択します。<!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 各Adobe Analytics ディメンションをカスタム XDM スキーマディメンションにマッピングします。

   1. 「**[!UICONTROL 標準フィールドをマッピング]**」セクションで、「**[!UICONTROL カスタム]**」タブを選択します。

   1. 「**[!UICONTROL 新しいマッピングを追加]**」を選択します。

   ![ スキーマフィールドのマッピング ](assets/schema-mapping.png)

   1. 「**[!UICONTROL Source フィールド]**」で、「Adobe Analytics ExperienceEvent テンプレート」フィールドグループからAdobe Analytics フィールドを選択します。 次に、**[!UICONTROL ターゲットフィールド]** で、マッピングする XDM フィールドを選択します。

      AppMeasurementと XDM のアーキテクチャには固有の違いがあるので、すべてのAdobe Analytics フィールドに XDM の対応するフィールドがあるわけではありません。

   1. Adobe Analyticsでのデータ収集に使用するAdobe Analytics ExperienceEvent テンプレートフィールドグループのフィールドごとに、このプロセスを繰り返します。

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. データフローに名前を付け、（オプションで）説明を入力します。

   ![ データフローの詳細セクションを強調表示したAdobe Experience Platform ウィンドウ ](./assets/dataflow-detail.png)

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. 接続を確認し、「**[!UICONTROL 終了]**」を選択します。

   ![ レビュー用に「接続」セクションと「データタイプ」セクションがハイライト表示されたAdobe Experience Platform ウィンドウ ](./assets/review.png)

   接続が作成されると、レポートスイートのAdobe Analytics データをデータセットに入力するデータフローが自動的に作成されます。 データフローは、実稼動用サンドボックスに対して最大 13 か月分の履歴データを取り込みます。 非実稼動用サンドボックスでのバックフィルは、3 か月に制限されています。

   Analytics ソースコネクタを使用して履歴データをCustomer Journey AnalyticsWeb SDK 実装に取り込む場合は、自動作成されたデータセットを、Web SDK 実装用に作成した接続に追加する必要があります。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
