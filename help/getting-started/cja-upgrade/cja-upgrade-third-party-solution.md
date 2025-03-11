---
title: サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード
description: サードパーティの分析ソリューションからCustomer Journey Analyticsにアップグレードする方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 32%

---

# サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Adobe Analytics 以外の製品"
>abstract="Google Analytics など、Adobe Analytics 以外の製品のデータを収集する実装。このオプションを選択すると、Adobe Analytics 以外の製品から Customer Journey Analytics にアップグレードする際に適用されない、アンケートのいくつかのオプションが無効になります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics以外の分析ソリューションからCustomer Journey Analyticsにアップグレードする場合は、Customer Journey Analyticsに推奨されるデータ収集方法であるExperience Platform Web SDKの新規実装を使用することをお勧めします。 Adobeでは、Web SDKと組み合わせて、履歴データをサードパーティの分析ソリューションからAdobe Experience Platformに取り込むこともお勧めします。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Google Analyticsなどのサードパーティの分析ソリューションからCustomer Journey Analyticsに移行する場合は、次の手順を実行します。

1. [ 詳細な推奨アップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) に従います。

   これらの手順は、Adobe Analyticsからアップグレードする組織を対象としています。 これらの手順に従う場合、次の点を理解する必要があります。

   * データストリームを作成する必要があります。

   * Adobe Analytics以外のソリューションからプロジェクトやコンポーネントを移行することはできません。

   * Analytics ソリューションによっては、ソースコネクタを使用して履歴データを取り込める場合があります。 詳しくは、Experience Platform ドキュメントの [Source コネクタの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) にある [Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics) を参照してください。


具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

