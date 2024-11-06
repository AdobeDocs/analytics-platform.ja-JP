---
title: Customer Journey Analyticsで使用するスキーマの構築
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 11%

---

# Customer Journey Analyticsで使用するスキーマの構築

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Adobeでは、Customer Journey Analyticsへのアップグレード時にエクスペリエンスデータモデル（XDM）スキーマを作成することをお勧めします。 XDM スキーマを使用すると、組織のニーズや使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマを提供できます。 スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。

XDM スキーマの作成を開始する前に、次の手順を実行します。

1. データチームおよび組織全体のその他の関係者を特定します。

1. 組織で使用されている他のAdobe Experience Platform アプリケーションを考慮に入れながら、Customer Journey Analyticsに対する組織の理想的なスキーマデザインを決定します。

1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。

