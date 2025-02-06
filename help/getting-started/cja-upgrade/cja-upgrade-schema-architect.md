---
title: Customer Journey Analyticsで使用するスキーマの構築
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Customer Journey Analyticsで使用するスキーマの構築 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="スキーマのアーキテクト"
>abstract="組織内でデータ収集の要件について話し合い、Adobe Experience Platformで使用するスキーマを作成する方法を決定します。 この手順は、組織に合わせてカスタマイズされたスキーマを推奨されるプロセスを使用する場合に表示されます。 組織内のすべてのチームが連携するスキーマにより、データの取り込みが大幅に容易になるので、この手順を正しく実行することが極めて重要です。<br><br> 組織内のすべての関係者を統合スキーマ上で足並みをそろえるための推定時間は 1～2 か月です。 この時間枠は、調整に必要なチームの数、および調整するディメンションと指標の数に大きく依存します。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>このページの手順は、以前のアップグレード手順をすべて完了した後でのみ実行してください。 [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) に従うか、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関するアンケート ](https://gigazelle.github.io/cja-ttv/) で組織用に動的に生成されたアップグレード手順に従うことができます。
>
>このページの手順を完了した後、推奨されるアップグレード手順または動的に生成されるアップグレード手順に従って続行します。

Adobeは、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に、web SDKで使用するカスタムエクスペリエンスデータモデル（XDM）スキーマを作成することをお勧めします。 または、デフォルトのAdobe Analytics スキーマを使用することもできます。この場合は、Adobe Analytics ExperienceEvent フィールドグループを使用します。

カスタム XDM スキーマを使用すると、組織のニーズや使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマが可能になります。 Adobe Analytics ExperienceEvent フィールドグループを使用するデフォルトのAdobe Analytics スキーマとは異なり、カスタム XDM スキーマへの変更が必要な場合は、更新が必要なフィールドを見つけるために何千もの未使用フィールドを選別する必要はありません。

これらのスキーマオプションについて詳しくは、[Customer Journey Analyticsするスキーマの選択 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) を参照してください。

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
