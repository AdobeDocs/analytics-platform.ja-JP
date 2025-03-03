---
title: Customer Journey Analytics用のスキーマの作成
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 56%

---

# Customer Journey Analytics で使用するデータセットの作成 {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Adobe Experience Platform でのデータセットの作成"
>abstract="データセットは、収集されたデータが存在する場所です。Adobe Experience Platform でこの場所を作成します。<br><br>スキーマを念頭に置いたデータセットの作成には、わずか数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

データセットは、Adobe Experience Platformに収集するデータを保存および管理する構造です。

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

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
