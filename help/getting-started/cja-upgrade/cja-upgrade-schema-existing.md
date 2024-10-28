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
source-wordcount: '242'
ht-degree: 59%

---

# Adobe Analytics スキーマをCustomer Journey Analyticsで使用

>[!NOTE]
>
>このドキュメントは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードアンケート ](https://gigazelle.github.io/cja-ttv/) の一部として使用してください。

<!-- this page exists as the "Learn more" link in the info icon for the option "I am comfortable using my Adobe Analytics schema as a basis" -->

Customer Journey Analyticsで既存のAdobe Analytics スキーマを使用するオプションは、Adobe Analytics実装がAdobe Experience Platform Web SDK で設定されている場合にのみ使用できます。<!-- correct? Or can you do this with an AppMeasurement implementation?-->

Adobe Analytics スキーマをCustomer Journey Analyticsで使用する場合の次のメリットとデメリットを検討します。

| メリット | デメリット |
|----------|---------|
| <p>Adobe Analytics スキーマを使用すると、次のようなメリットがあります。</p><ul><li>アップグレードが容易<p>既にAdobe Experience Platform Web SDK を使用して Adobe Analytics にデータを送信している場合は、データストリームに追加サービスを追加して、Adobe Experience Platform にデータを送信できます（これは Customer Journey Analytics 設定で使用できます）。</p></li></ul> | <p>Adobe Analytics スキーマを使用すると、次のようなデメリットがあります。</p><ul><li>Adobe Analytics スキーマを使用しても、他の Platform アプリケーションでの使用方法が制限されることはありませんが、スキーマは他の方法よりも複雑になります。これは、Adobe Analytics スキーマには、組織で使用される可能性が低い Adobe Analytics に固有のオブジェクトが多数含まれているからです。<p>スキーマの変更が必要な場合は、数千もの未使用フィールドを調べて、更新が必要なフィールドを見つける必要があります。</p></li></ul> |

<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->