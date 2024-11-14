---
title: Analytics ソースコネクタ用の XDM スキーマの作成
description: Analytics ソースコネクタ用の XDM スキーマを作成する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Analytics ソースコネクタ用の XDM スキーマの作成

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Experience PlatformWeb SDK 実装がCustomer Journey Analyticsで使用できるように、[ 新しい XDM スキーマを作成 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) しておく必要があります。 このスキーマには、データを収集するフィールドのフィールドグループを含める必要があります。

Web SDK 実装用に既に作成した XDM スキーマに加えて、2 つ目の XDM スキーマを作成し、Analytics ソースコネクタで使用して履歴データをCustomer Journey Analyticsに取り込む必要があります。

この 2 番目のスキーマには、次を含める必要があります。

* Web SDK 実装用に作成したスキーマに含まれるすべてのフィールドグループ（カスタムフィールドグループを含む）。 （デフォルトのフィールドグループに含まれないカスタムフィールドは、カスタムフィールドグループの一部として Web SDK スキーマに追加する必要があります）。

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

