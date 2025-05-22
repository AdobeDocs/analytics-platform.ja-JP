---
title: Analytics ソースコネクタの作成とフィールドのマッピング
description: Analytics ソースコネクタの作成とフィールドのマッピング方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '745'
ht-degree: 100%

---

# Analytics ソースコネクタの作成とフィールドのマッピング {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="Analytics ソースコネクタを作成"
>abstract="Analytics ソースコネクタを使用して、Customer Journey Analytics で使用するレポートスイートデータを取り込みます。<br><br>デフォルト設定を使用すると、Analytics ソースコネクタの作成には数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="Analytics ソースコネクタの作成とスキーマフィールドのマッピング"
>abstract="ソースコネクタを使用する場合は、Adobe Analytics フィールドを組織のスキーマにマッピングする方法を知っている必要があります。このインターフェイスを使用して、ソースコネクタにそのマッピングを提供します。この手順は、Customer Journey Analytics に履歴データを追加する手順の一部です。<br><br>この手順にかかる時間は、マッピングする必要があるディメンションと指標の数に大きく依存します。この手順は、退屈で反復的な作業ですが、それほど難しいものではありません。データストリームマッピングが完了するまでに約 1 週間の作業がかかると予想されます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Analytics ソースコネクタを使用して、履歴データを Customer Journey Analytics に取り込む方法について

Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータを Adobe Experience Platform に取り込むことができます。 その後、このデータは、Customer Journey Analytics で履歴データとして使用できます。

このプロセスでは、組織のニーズと使用する特定のプラットフォームアプリケーションに合わせて調整された効率化されたスキーマが必要なので、[Customer Journey Analytics Web SDK 実装で使用するカスタムスキーマを作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)することを前提としています。

Analytics ソースコネクタを使用して履歴データを Customer Journey Analytics に取り込むには、次の操作を行う必要があります。

1. [Analytics ソースコネクタ用のカスタムスキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Analytics ソースコネクタがまだない場合は、以下の説明に従って、Analytics ソースコネクタを作成し、フィールドをカスタム Web SDK スキーマにマッピングします。

   または

   Analytics ソースコネクタが既にある場合は、[ソースコネクタのフィールドをカスタム Web SDK スキーマにマッピングします](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [接続への Analytics ソースコネクタデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics ソースコネクタの作成とフィールドのマッピング

カスタムスキーマを作成したら、履歴データに使用する Adobe Analytics ソースコネクタを作成する必要があります（ソースコネクタの作成に関するより包括的で一般的なガイドラインについて詳しくは、[UI でのAdobe Analytics ソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を参照してください）。

履歴データに使用する Adobe Analytics ソースコネクタを作成するには：

1. Platform UI の左側のパネルにある「**[!UICONTROL 接続]**」セクションで、「**[!UICONTROL ソース]**」を選択します。

1. [!UICONTROL カテゴリ]のリストから、**[!UICONTROL Adobe アプリケーション]**&#x200B;を選択します。

1. Adobe Analytics タイルで「**[!UICONTROL データを追加]**」を選択します。

   ![ソースが選択され、アドビアプリケーションと「データを追加」がハイライト表示されている Adobe Experience Platform ウィンドウ。](./assets/sources-overview.png)

1. 「**[!UICONTROL レポートスイート]**」を選択し、レポートスイートのリストから、Customer Journey Analytics で使用する履歴データを含むレポートスイートを選択します。

   ![レポートスイートリストを表示する Adobe Experience Platform ウィンドウ](./assets/report-suites.png)

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. 「**[!UICONTROL カスタムスキーマ]**」を選択し、[Adobe Analytics フィールドグループを含むカスタムスキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)で作成したスキーマを選択します。<!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 各 Adobe Analytics ディメンションをカスタムスキーマディメンションにマッピングします。

   1. 「**[!UICONTROL 標準フィールドをマッピング]**」セクションで、「**[!UICONTROL カスタム]**」タブを選択します。

   1. 「**[!UICONTROL 新しいマッピングを追加]**」を選択します。

   ![スキーマフィールドをマッピング](assets/schema-mapping.png)

   1. **[!UICONTROL 「ソース」フィールド]**&#x200B;で、Adobe Analytics ExperienceEvent テンプレートフィールドグループから Adobe Analytics フィールドを選択します。次に、**[!UICONTROL 「ターゲット」フィールド]**&#x200B;で、マッピング先の XDM スキーマ内のカスタムフィールドを選択します。

      AppMeasurement と XDM の間には固有のアーキテクチャの違いがあるので、Adobe Analytics フィールドのすべてが XDM 内に対応するフィールドがあるわけではありません。

   1. Adobe Analytics でデータを収集するために使用している Adobe Analytics ExperienceEvent テンプレートフィールドグループの各フィールドに対して、このプロセスを繰り返します。

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. データフローに名前を付け、（オプションで）説明を入力します。

   ![「データフローの詳細」セクションをハイライト表示する Adobe Experience Platform ウィンドウ](./assets/dataflow-detail.png)

1. 画面の右上隅にある「**[!UICONTROL 次へ]**」を選択します。

1. 接続を確認し、「**[!UICONTROL 終了]**」を選択します。

   ![確認のために 「接続」および「データタイプ」セクションをハイライト表示する Adobe Experience Platform ウィンドウ](./assets/review.png)

   接続を作成すると、データフローが自動的に作成され、レポートスイートからの Adobe Analytics データがデータセットに入力されます。データフローでは、実稼動用サンドボックスの最大 13 か月分の履歴データを取り込みます。非実稼動用サンドボックスのバックフィルは、3 か月に制限されています。

   Analytics ソースコネクタを使用して履歴データを Customer Journey Analytics Web SDK 実装に取り込む場合は、この自動的に作成されたデータセットを、Web SDK 実装用に作成した接続に追加する必要があります。

{{upgrade-final-step}}
