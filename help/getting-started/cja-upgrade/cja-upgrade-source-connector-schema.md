---
title: Analytics ソースコネクタ用のカスタムスキーマの作成
description: Analytics ソースコネクタのカスタムスキーマを作成する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 23%

---

# Analytics ソースコネクタ用のカスタムスキーマの作成 {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Analytics ソースコネクタ用のスキーマの作成"
>abstract="このスキーマは、「Adobe Analytics ExperienceEvent」フィールドグループと、組織のカスタムスキーマを構成するすべてのフィールドグループを組み合わせたものです。これにより、Analytics ソースコネクタで使用されるフィールドを組織のスキーマにマッピングでき、履歴データにのみ使用されます。<br><br>本質的には技術的なものですが、このスキーマの作成は数時間で完了できます。組織のカスタムスキーマを構成するフィールドグループを正確に把握している場合は、さらに早く完了できる可能性があります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="履歴データ用の Analytics ソースコネクタを作成"
>abstract="Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータをAdobe Experience Platformに取り込むことができます。 その後、このデータをCustomer Journey Analyticsの履歴データとして使用できます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込む方法を説明します

Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータをAdobe Experience Platformに取り込むことができます。 その後、このデータをCustomer Journey Analyticsの履歴データとして使用できます。

ここでは、Customer Journey Analytics Web SDKの実装で使用する [ カスタムスキーマを作成する ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) ことを前提としています。これは、組織のニーズと使用する特定の Platform アプリケーションに合わせて調整される、合理化されたスキーマが必要なためです。

Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込むには、次の操作が必要です。

1. 以下に説明するように、Analytics ソースコネクタのカスタムスキーマを作成します。

1. Analytics ソースコネクタがまだない場合は [Analytics ソースコネクタを作成し、フィールドをカスタムスキーマにマッピングします ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   または

   既に Analytics ソースコネクタがある場合は、[ ソースコネクタのフィールドを XDM スキーマにマッピング ](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md) します。

1. [接続への Analytics ソースコネクタデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics ソースコネクタ用のカスタムスキーマの作成

Customer Journey Analyticsで使用するExperience Platform Web SDKの実装には、既に [ 新しいカスタムスキーマを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) している必要があります。 このスキーマには、データを収集するフィールドのフィールドグループを含める必要があります。

次に、Web SDK スキーマと同じフィールドグループを使用し、Analytics ソースコネクタで使用できる新しいスキーマに追加する必要があります。

Analytics ソースコネクタのこのスキーマには、次を含める必要があります。

* Web SDK実装用に作成したカスタムスキーマに含まれるすべてのフィールドグループ（作成したカスタムフィールドグループを含む）。 （デフォルトのフィールドグループに含まれないカスタムフィールドは、カスタムフィールドグループの一部として Web SDK スキーマに追加する必要があります）。

* 「Adobe Analytics ExperienceEvent テンプレート」フィールドグループ

Analytics ソースコネクタで使用するカスタムスキーマを作成するには：

1. Adobe Experience Platformで、[Customer Journey Analytics Web SDKの実装で使用するカスタムスキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) の説明に従って、新しいカスタムスキーマの作成を開始します。

1. Web SDK実装用に作成したスキーマに含まれるすべてのフィールドグループ（カスタムフィールドグループを含む）を追加します。

1. これらのフィールドグループの追加が完了したら、Adobe Analytics ExperienceEvent フィールドグループを追加します。

   「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL 追加]**」を選択してフィールドグループを追加します。

   ![ スキーマにフィールドグループを追加 ](assets/schema-add-field-group.png)

1. 「**[!UICONTROL Adobe Analytics ExperienceEvent テンプレート]**」フィールドグループを検索して選択します。

   ![Adobe Analytics ExperienceEvent フィールドグループの追加 ](assets/schema-experienceevent.png)

1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

{{upgrade-final-step}}
