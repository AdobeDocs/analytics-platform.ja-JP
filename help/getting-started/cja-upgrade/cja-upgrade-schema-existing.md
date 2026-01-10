---
title: Customer Journey Analytics のスキーマを選択
description: Customer Journey Analytics のスキーマを選択する際に使用できるオプションと、それぞれのメリットとデメリットについて説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# Customer Journey Analytics のスキーマを選択 {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="カスタムスキーマの使用"
>abstract="（推奨）スキーマをカスタマイズすると、組織は必要なもののみを追跡でき、乱雑で不要なフィールドに関連付けられたオーバーヘッドを回避できます。 このオプションには、Web SDK によって追加されたフィールドグループと、組織にカスタムのフィールドグループが含まれます。"

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="デフォルトのスキーマの使用"
>abstract="（非推奨）Adobe Analytics スキーマには 1,000 を超えるフィールドが含まれており、スキーマが乱雑で複雑になる場合があります。組織は、Customer Journey Analytics では使用されていない従来の概念である prop と eVar の概念に引き続き従わざるを得なくなります。 他の Adobe Experience Platform サービスとの統合はより困難です。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Customer Journey Analytics にアップグレードする場合、アドビでは、他のプラットフォームサービスの使用を開始する際に組織のニーズに合わせてカスタムエクスペリエンスデータモデル（XDM）スキーマを作成することをお勧めします。または、既存の Adobe Analytics スキーマを使用することもできます。

それぞれのメリットとデメリットを考慮します。

## 組織に合わせたカスタムスキーマの作成（推奨）

アドビでは、Customer Journey Analytics にアップグレードする際にカスタムスキーマを作成することをお勧めします。

| メリット | デメリット |
|----------|---------|
| <ul><p>独自のカスタムスキーマに更新すると、次のようなメリットがあります。</p><ul><li>組織のニーズと使用する特定の Platform アプリケーションに合わせて調整された効率化されたスキーマ。</li><p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要はありません。</p></ul> | <p>独自のカスタムスキーマに更新すると、次のようなデメリットがあります。</p><ul><li>スキーマの更新は、Platform へのデータの送信を開始する前に必要な時間のかかるプロセスです。</li></ul> |

## 既存の Adobe Analytics スキーマの使用

既存の Adobe Analytics スキーマを Customer Journey Analytics で使用するオプションは、Adobe Analytics 実装が Adobe Experience Platform Web SDK を使用して設定されている場合にのみ使用できます。<!-- correct? Or can you do this with an AppMeasurement implementation?-->

| メリット | デメリット |
|----------|---------|
| <p>Adobe Analytics スキーマを使用すると、次のようなメリットがあります。</p><ul><li>アップグレードのしやすさ<p>既にAdobe Experience Platform Web SDK を使用して Adobe Analytics にデータを送信している場合は、データストリームに追加サービスを追加して、Adobe Experience Platform にデータを送信できます（これは Customer Journey Analytics 設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用すると、次のようなデメリットがあります。</p><ul><li>Adobe Analytics スキーマを使用しても、他の Platform アプリケーションでの使用方法が制限されることはありませんが、スキーマは他の方法よりも複雑になります。これは、Adobe Analytics スキーマには、組織で使用される可能性が低い Adobe Analytics に固有のオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要があります。</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
