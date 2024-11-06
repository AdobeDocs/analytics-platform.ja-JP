---
title: Customer Journey Analytics用スキーマの作成
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Customer Journey Analytics内のデータを分類するルックアップデータセットの作成

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Adobe Analyticsのデータの分類と同様に、ルックアップデータセットは、Customer Journey Analyticsでデータを分類するための手法です。

Analytics ソースコネクタを使用する場合、一部の標準検索データセットは、レポート時に自動的に適用されます。 詳しくは、[ データセットへの標準検索の追加 ](/help/connections/standard-lookups.md) を参照してください。

Experience Platform Web SDK の新しい実装でデータを分類するには、分類するデータを含むディメンションごとにルックアップデータセットを作成する必要があります。

Customer Journey Analyticsで使用するルックアップデータセットを作成するには、次の手順に従います。

1. AEP で、新しいスキーマを作成します。 これは、ルックアップデータセットに固有の新しいスキーマです。 既存のスキーマは使用できません。

1. ルックアップ用の新しいスキーマクラスを作成する必要があります。

1. それをもとにルックアップデータセットを作成します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
