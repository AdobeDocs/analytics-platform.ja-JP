---
title: Customer Journey Analyticsでのデータビューの作成
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 23%

---

# Customer Journey Analyticsでのデータビューの作成

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

データビューを作成するには、スキーマ要素から指標やディメンションを作成するか、標準コンポーネントを使用する必要があります。ほとんどのスキーマ要素は、ビジネスの要件に応じて、ディメンションまたは指標のいずれかになります。 スキーマ要素をデータビューにドラッグすると、右側にオプションが表示され、Customer Journey Analytics でのディメンションや指標の動作を調整できます。

データビューを作成するには：

1. [Customer Journey Analytics](https://analytics.adobe.com) にログインし、「**[!UICONTROL データビュー]**」タブに移動します。

1. **[!UICONTROL 新しいデータビューを作成]** を選択します。 または、データビューのリストから既存のデータビューを選択して編集することもできます。

1. 「[!UICONTROL **設定**]」タブで、データビューの名前を指定し、その基本設定、コンポーネントおよびカレンダーオプションを設定します。

   各フィールドについて詳しくは、[ データビューの作成または編集 [ の ](/help/data-views/create-dataview.md#configure) 設定 ](/help/data-views/create-dataview.md) を参照してください。

   ![データビューの設定](assets/dataview-configure.png)

1. 「[!UICONTROL **コンポーネント**]」タブを選択します。

   [!UICONTROL **コンポーネント**] タブでは、データビューのコンポーネントを設定できます。つまり、スキーマ要素から指標とディメンションを作成できます。 また、標準コンポーネントも使用できます。

   ![「コンポーネント」タブ](assets/dataview-components.png)

1. 「[!UICONTROL **コンポーネント**]」タブで、左側のパネルから「{Metrics **]」セクションまたは[!UICONTROL ** 4}Dimension **]セクションにスキーマ要素をドラッグします。[!UICONTROL **&#x200B;追加するスキーマ要素は、データビューの指標またはディメンションになります。

   データビューにコンポーネントを追加する際に使用できるオプションについて詳しくは、[ データビューの作成または編集 [ の ](/help/data-views/create-dataview.md#components) コンポーネント ](/help/data-views/create-dataview.md) を参照してください。

1. 「[!UICONTROL **設定**]」タブを選択します。ここから、データビュー全体に適用するフィルターを設定したり、セッションタイムアウトと指標を設定したりできます。

   データビューの設定を指定する際に使用できるオプションについて詳しくは、[ データビューの作成または編集 [ の ](/help/data-views/create-dataview.md#settings) 設定 ](/help/data-views/create-dataview.md) を参照してください。

1. 「**[!UICONTROL 保存]**」を選択して、データビューの設定を保存します。

1. 必要な設定をすべて指定したら、「**[!UICONTROL 保存して終了]**」を選択します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。

