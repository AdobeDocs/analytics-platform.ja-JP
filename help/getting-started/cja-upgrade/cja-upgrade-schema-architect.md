---
title: Customer Journey Analytics で使用するスキーマの設計
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に推奨されるパスについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 28%

---

# Customer Journey Analytics で使用するスキーマの設計 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="スキーマの設計"
>abstract="組織内でデータ収集の要件について話し合い、Adobe Experience Platform で使用するスキーマの作成方法を決定します。この手順は、組織に合わせて調整されたスキーマを使用する推奨プロセスを使用するために表示されます。組織内のすべてのチームが調整するスキーマにより、データ取り込みが大幅に容易になるので、この手順を正しく実行することは極めて重要です。<br><br>組織内のすべての関係者を集めて統一スキーマに合わせて調整するまでにかかる推定時間は 1 ～ 2 か月です。この時間枠は、調整が必要なチームの数と、調整するディメンションと指標の数に大きく依存します。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobeでは、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時に、web SDKで使用するカスタム Experience Data Model （XDM）スキーマを作成することをお勧めします。 または、デフォルトのAdobe Analytics スキーマを使用することもできます。この場合は、Adobe Analytics ExperienceEvent フィールドグループを使用します。

カスタム XDM スキーマを使用すると、組織のニーズや使用する特定の Platform アプリケーションに合わせてカスタマイズされた、合理化されたスキーマが可能になります。 Adobe Analytics ExperienceEvent フィールドグループを使用するデフォルトのAdobe Analytics スキーマとは異なり、カスタム XDM スキーマへの変更が必要な場合は、更新が必要なフィールドを見つけるために何千もの未使用フィールドを選別する必要はありません。

これらのスキーマオプションについて詳しくは、[Customer Journey Analytics用のスキーマを選択 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) を参照してください。

XDM スキーマの設計を開始する際は、次の節を確認してください。

## XDM スキーマでのAdobe Analyticsの制限を回避する

Customer Journey Analyticsの基盤となるアーキテクチャは、Adobe Analyticsよりも柔軟です。 新しい XDM スキーマの作成は、その柔軟性を解き放つ重要な方法です。 Customer Journey Analyticsにアップグレードする場合は、不要なAdobe Analytics制限をスキーマに転送しないようにしてください。

| Adobe Analyticsのデータアーキテクチャ | XDM スキーマアーキテクチャ |
|---------|----------|
| 個々の指標が Analytics のデータアーキテクチャに追加されます。<br/> 例えば、Adobe Analyticsではイベントごとに異なるeVarが使用されています。 | XDM スキーマではなくデータビューで個々の指標を作成します。 これにより、後で変更を加える必要がある場合に、の柔軟性を高めることができます。<br/> 例えば、Customer Journey Analyticsではスキーマに 1 つのイベントがあり、データビューでは create events を使用します。 |
| カスタム変数を作成するには、prop と eVar が必要です。 | B2 |
| A3 | B3 |

## データチームおよび組織全体のその他の関係者を特定する


## 組織で使用される他のAdobe Experience Platform アプリケーションの検討



1. [ 推奨されるアップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または [ 動的に生成されるアップグレード手順 ](https://gigazelle.github.io/cja-ttv/) に従って続行します。
