---
title: サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード
description: サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '238'
ht-degree: 100%

---

# サードパーティの分析ソリューションから Customer Journey Analytics へのアップグレード {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Adobe Analytics 以外の製品"
>abstract="Google Analytics など、Adobe Analytics 以外の製品のデータを収集する実装。このオプションを選択すると、Adobe Analytics 以外の製品から Customer Journey Analytics にアップグレードする際に適用されない、アップグレードガイドのいくつかのオプションが無効になります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics 以外の分析ソリューションから Customer Journey Analytics へのアップグレードでは、Customer Journey Analytics の推奨データ収集方法である Experience Platform Web SDK を新しく実装することをお勧めします。アドビでは、Web SDK と併せて、履歴データをサードパーティの分析ソリューションから Adobe Experience Platform に取り込むこともお勧めします。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Google Analytics などのサードパーティ分析ソリューションから Customer Journey Analytics に移行する場合は、次の手順に従いします。

1. [推奨されるアップグレード手順の詳細](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)に従います。

   これらの手順は、Adobe Analytics からアップグレードする組織を対象としています。これらの手順に従う場合は、次の点を理解します。

   * データストリームを作成する必要があります。

   * Adobe Analytics 以外のソリューションからプロジェクトやコンポーネントは移行できません。

   * 分析ソリューションによっては、履歴データを取り込むのにソースコネクタを使用できる可能性があります。詳しくは、Experience Platform ドキュメントの[ソースコネクタの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/home)の[分析](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/home#analytics)を参照してください。


具体的なアドバイス、ガイダンス、サポートが必要な場合は、アドビ担当者にお問い合わせください。

