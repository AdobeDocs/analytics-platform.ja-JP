---
title: Customer Journey Analytics用スキーマの作成
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 30%

---

# Customer Journey Analyticsで使用するデータセットの作成

>[!NOTE]
>
>このドキュメントは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) に回答した後で使用してください。
> 
>このページの手順は、組織に対して動的に生成された以前のすべての手順を完了した後でのみ実行します。
>
>このページの手順を完了した後も、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で動的に生成されたアップグレード手順を引き続き実行してください。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

XDM スキーマを作成したら、そのデータを保存および管理するための構造を定義する必要があります。この処理は、データセットを使用してAdobe Experience Platformで行われます。

データセットを作成するには：

1. Adobe Experience Platformの左パネルの「**[!UICONTROL DATA MANAGEMENT]**」で「[!UICONTROL  データセット ]」を選択します。

1. 「**[!UICONTROL データセットを作成]**」を選択します。

   ![データセットの作成](assets/create-dataset.png)

1. 「**[!UICONTROL スキーマからデータセットを作成]**」をクリックします。

   ![スキーマからのデータセットの作成](assets/create-dataset-from-schema.png)

1. 作成したスキーマを選択し、「**[!UICONTROL 次へ]**」を選択します。

1. データセットに名前を付け、（オプション）説明を入力します。

   ![名前データセット](assets/name-your-datatest.png)

1. 「**[!UICONTROL 完了]**」を選択します。

1. 「**[!UICONTROL プロファイル]**」スイッチを選択します。

   プロファイルのデータセットを有効にするよう求められます。有効にすると、データセットは、取り込んだデータを使用してリアルタイム顧客プロファイルを強化します。

   >[!IMPORTANT]
   >
   >    プロファイルのデータセットを有効にできるのは、データセットが準拠するスキーマがプロファイルに対しても有効になっている場合のみです。

   ![プロファイルでスキーマを有効にする](assets/aepwebsdk-dataset-profile.png)

   データセットの表示、プレビュー、作成、削除の方法について詳しくは、[ データセット UI ガイド ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja) を参照してください。 リアルタイム顧客プロファイルのデータセットを有効にする方法についても説明します。

1. [Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で動的に生成されたアップグレード手順を引き続き実行します。

