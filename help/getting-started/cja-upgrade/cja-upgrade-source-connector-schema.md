---
title: Analytics ソースコネクタ用のカスタムスキーマの作成
description: Analytics ソースコネクタのカスタムスキーマを作成する方法を学ぶ
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
autotag-review: '2026-05-19T08:17:31.632Z'
TQID: 'https://experienceleague.adobe.com/ov6cr-MF9OeH8OU23Km0KdD2l0LirVpVor4nndHpqo8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 587
ht-degree: 100%

---

# Analytics ソースコネクタ用のカスタムスキーマの作成 {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Analytics ソースコネクタ用のスキーマの作成"
>abstract="このスキーマは、Adobe Analytics ExperienceEvent フィールドグループと、組織のカスタムスキーマを構成するすべてのフィールドグループの組み合わせです。 これにより、Analytics ソースコネクタで使用されるフィールドを組織のスキーマにマッピングでき、履歴データにのみ使用されます。<br><br>本質的に技術的ですが、このスキーマの作成は数時間で完了します。組織のカスタムスキーマを構成するフィールドグループを正確に把握している場合は、より早く完了できるでしょう。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="履歴データ用の Analytics ソースコネクタの作成"
>abstract="Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータを Adobe Experience Platform に取り込むことができます。 その後、このデータは、Customer Journey Analytics で履歴データとして使用できます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Analytics ソースコネクタを使用して、履歴データを Customer Journey Analytics に取り込む方法について

Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータを Adobe Experience Platform に取り込むことができます。 その後、このデータは、Customer Journey Analytics で履歴データとして使用できます。

このプロセスでは、組織のニーズと使用する特定のプラットフォームアプリケーションに合わせて調整された効率化されたスキーマが必要なので、[Customer Journey Analytics Web SDK 実装で使用するカスタムスキーマを作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)することを前提としています。

Analytics ソースコネクタを使用して履歴データを Customer Journey Analytics に取り込むには、次の操作を行う必要があります。

1. 以下に説明するように、Analytics ソースコネクタのカスタムスキーマを作成します。

1. Analytics ソースコネクタがまだない場合は、[Analytics ソースコネクタを作成し、フィールドをカスタムスキーマにマッピングします](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   または

   既に Analytics ソースコネクタがある場合は、[ ソースコネクタのフィールドを XDM スキーマにマッピングします](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [接続への Analytics ソースコネクタデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics ソースコネクタ用のカスタムスキーマの作成

Customer Journey Analytics で使用するには、Experience Platform Web SDK 実装用の[新しいカスタムスキーマを作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)しておく必要があります。 このスキーマには、データを収集するフィールドのフィールドグループを含める必要があります。

次に、Web SDK スキーマと同じフィールドグループを使用し、Analytics ソースコネクタで使用できる新しいスキーマに追加する必要があります。

Analytics ソースコネクタのこのスキーマには、を含める必要があります。

* Web SDK 実装用に作成したカスタムスキーマに含まれるすべてのフィールドグループ（作成したカスタムフィールドグループを含む）。 （デフォルトのフィールドグループに含まれないカスタムフィールドは、カスタムフィールドグループの一部として Web SDK スキーマに追加する必要があります。）

* Adobe Analytics ExperienceEvent テンプレートフィールドグループ

Analytics ソースコネクタで使用するカスタムスキーマを作成するには：

1. Adobe Experience Platform で、[Customer Journey Analytics Web SDK の実装で使用するカスタムスキーマの作成](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)の説明に従って、新しいカスタムスキーマの作成を開始します。

1. Web SDK 実装用に作成したスキーマに含まれるすべてのフィールドグループ（カスタムフィールドグループを含む）を追加します。

1. これらのフィールドグループの追加が完了したら、Adobe Analytics ExperienceEvent フィールドグループを追加します。

   「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL 追加]**」を選択してフィールドグループを追加します。

   ![スキーマにフィールドグループを追加](assets/schema-add-field-group.png)

1. **[!UICONTROL Adobe Analytics ExperienceEvent テンプレート]**&#x200B;フィールドグループを検索して選択します。

   ![Adobe Analytics ExperienceEvent フィールドグループの追加](assets/schema-experienceevent.png)

1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

{{upgrade-final-step}}
