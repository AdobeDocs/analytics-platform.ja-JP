---
title: サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード
description: サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
autotag-review: '2026-05-19T08:20:34.368Z'
TQID: 'https://experienceleague.adobe.com/fwYoa9oeIs2tujyDEWUj-GaAgpZQNBwup-YsHIe-TdU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 293
ht-degree: 89%

---

# サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Adobe Analytics 以外の製品"
>abstract="Google Analytics など、Adobe Analytics 以外の製品のデータを収集する実装。 このオプションを選択すると、Adobe Analytics 以外の製品から Customer Journey Analytics にアップグレードする際に適用されない、アップグレードガイドのいくつかのオプションが無効になります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics 以外の分析ソリューションから Customer Journey Analytics へのアップグレードでは、Customer Journey Analytics の推奨データ収集方法である Experience Platform Web SDK を新しく実装することをお勧めします。 アドビでは、Web SDK と併せて、履歴データをサードパーティの分析ソリューションから Adobe Experience Platform に取り込むこともお勧めします。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Google Analytics などのサードパーティ分析ソリューションから Customer Journey Analytics に移行する場合は、次の手順に従いします。

1. [推奨されるアップグレード手順の詳細](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)に従います。

   これらの手順は、Adobe Analytics からアップグレードする組織を対象としています。 これらの手順に従う場合は、次の点を理解します。

   * データストリームを作成する必要があります。

   * Adobe Analytics 以外のソリューションからプロジェクトやコンポーネントは移行できません。

   * 分析ソリューションによっては、履歴データを取り込むのにソースコネクタを使用できる可能性があります。 詳しくは、Experience Platform ドキュメントの[ソースコネクタの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/home)の[分析](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/home#analytics)を参照してください。


具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

特にGoogle Analytics 4からアクセスする場合は、[ レポートの等価性、データモデルの違い、指標の比較に関するアナリスト向けガイダンスについては、「Google Analytics 4からCustomer Journey Analyticsへの移行](../ga-to-cja/home.md)」を参照してください。

