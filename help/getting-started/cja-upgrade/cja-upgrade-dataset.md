---
title: Customer Journey Analytics のスキーマの作成
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨されるパスについて説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '219'
ht-degree: 100%

---

# Customer Journey Analytics で使用するデータセットの作成 {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Adobe Experience Platform でデータセットを作成"
>abstract="データセットは、収集されたデータが存在する場所です。Adobe Experience Platform でこの場所を作成します。<br><br>スキーマを考慮したデータセットの作成には、わずか数分しかかかりません。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

データセットは、Adobe Experience Platform に収集するデータを保存および管理する構造です。

データセットを作成するには：

1. Adobe Experience Platform の左側のパネルで、[!UICONTROL データ管理]内の「**[!UICONTROL データセット]**」を選択します。

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

   データセットの表示、プレビュー、作成、削除の方法について詳しくは、[データセット UI ガイド](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja)を参照してください。また、リアルタイム顧客プロファイルのデータセットを有効にする方法についても説明します。

{{upgrade-final-step}}
