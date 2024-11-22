---
title: Analytics ソースコネクタ用の XDM スキーマの作成
description: Analytics ソースコネクタ用の XDM スキーマを作成する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 8%

---

# Analytics ソースコネクタ用の XDM スキーマの作成

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

## Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込む方法を理解する

Analytics ソースコネクタを使用して、Adobe Analytics レポートスイートデータをAdobe Experience Platformに取り込むことができます。 その後、このデータをCustomer Journey Analyticsの履歴データとして使用できます。

ここでは、Customer Journey Analyticsのニーズと使用する特定の Platform アプリケーションに合わせて調整される合理化されたスキーマが必要なので、](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)Platform へのアップグレード時に XDM スキーマを作成 [ できることを前提としています。

Analytics ソースコネクタを使用して履歴データをCustomer Journey Analyticsに取り込むには、次の操作が必要です。

1. 以下に説明するように、Analytics ソースコネクタ用の XDM スキーマを作成します。

1. Analytics ソースコネクタがない場合は [Analytics ソースコネクタを作成し、フィールドを XDM スキーマにマッピングします ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   または

   既に Analytics ソースコネクタがある場合は、[ ソースコネクタのフィールドを XDM スキーマにマッピング ](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md) します。

1. [接続への Analytics ソースコネクタデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics ソースコネクタ用の XDM スキーマの作成

Experience PlatformWeb SDK 実装がCustomer Journey Analyticsで使用できるように、[ 新しい XDM スキーマを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) しておく必要があります。 このスキーマには、データを収集するフィールドのフィールドグループを含める必要があります。

次に、Web SDK スキーマから同じフィールドグループを使用し、Analytics ソースコネクタで使用できる新しいスキーマに追加する必要があります。

Analytics ソースコネクタのこのスキーマには、次を含める必要があります。

* Web SDK 実装用に作成したカスタムスキーマに含まれるすべてのフィールドグループ（作成したカスタムフィールドグループを含む）。 （デフォルトのフィールドグループに含まれないカスタムフィールドは、カスタムフィールドグループの一部として Web SDK スキーマに追加する必要があります）。

* 「Adobe Analytics ExperienceEvent テンプレート」フィールドグループ

Analytics ソースコネクタで使用する XDM スキーマを作成するには、次の手順を実行します。

1. Adobe Experience Platformで、[Customer Journey Analyticsで使用する XDM スキーマの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) の説明に従って、新しい XDM スキーマの作成を開始します。

1. Web SDK 実装用に作成したスキーマに含まれるすべてのフィールドグループ（カスタムフィールドグループを含む）を追加します。

1. これらのフィールドグループの追加が完了したら、Adobe Analytics ExperienceEvent フィールドグループを追加します。

   「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL 追加]**」を選択してフィールドグループを追加します。

   ![ スキーマにフィールドグループを追加 ](assets/schema-add-field-group.png)

1. 「**[!UICONTROL Adobe Analytics ExperienceEvent テンプレート]**」フィールドグループを検索して選択します。

   ![Adobe Analytics ExperienceEvent フィールドグループの追加 ](assets/schema-experienceevent.png)

1. 「**[!UICONTROL フィールドグループを追加]**」を選択します。

1. 「**[!UICONTROL 保存]**」を選択してスキーマを保存します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
