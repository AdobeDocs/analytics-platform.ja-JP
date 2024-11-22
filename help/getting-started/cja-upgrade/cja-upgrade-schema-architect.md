---
title: Customer Journey Analyticsで使用するスキーマの構築
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 7%

---

# Customer Journey Analyticsで使用するスキーマの構築

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Adobeでは、Customer Journey Analyticsへのアップグレード時にエクスペリエンスデータモデル（XDM）スキーマを作成することをお勧めします。 XDM スキーマを使用すると、組織のニーズや使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマを提供できます。 スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。

XDM スキーマの設計を開始する際は、次の節を確認してください。

## XDM スキーマでのAdobe Analyticsの制限を回避する

Customer Journey Analyticsの基盤となるアーキテクチャは、Adobe Analyticsよりも柔軟です。 新しい XDM スキーマの作成は、その柔軟性を解き放つ重要な方法です。 スキーマにアップグレードする場合は、Customer Journey Analyticsに不要なAdobe Analytics制限を転送しないようにしてください。

| Adobe Analyticsのデータアーキテクチャ | XDM スキーマアーキテクチャ |
|---------|----------|
| 個々の指標が Analytics のデータアーキテクチャに追加されます。<br/> 例えば、Adobe Analyticsではイベントごとに異なるeVarが表示されます。 | XDM スキーマではなくデータビューで個々の指標を作成します。 これにより、後で変更を加える必要がある場合に、の柔軟性を高めることができます。<br/> 例えば、Customer Journey Analyticsに 1 つのイベントがあり、データビューで create events を使用しているとします。 |
| カスタム変数を作成するには、prop と eVar が必要です。 | B2 |
| A3 | B3 |

## データチームおよび組織全体のその他の関係者を特定する


## 組織で使用される他のAdobe Experience Platform アプリケーションの検討



1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
