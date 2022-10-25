---
title: 顧客管理キー
description: CJA 用の顧客管理キーの設定方法について説明します。
hide: true
hidefromtoc: true
source-git-commit: eba2eb71ca434e0306c018b80209caf52266ee15
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# 顧客管理キー

>[!NOTE]
>
>この機能は、2022 年 11 月に提供されます。

Customer Journey Analytics(CJA) は、Healthcare Shield および Privacy &amp; Security Shield のお客様が CJA データに適用する Azure Customer Managed Key(CMK) を利用できるようにするオプションを提供します。  このプロセスは、Adobe Experience Platform CMK の設定（従うリンク）とは別のものです。

>[!NOTE]
>
>顧客管理キーは、現在、 [ヘルスケアシールドまたはプライバシーとセキュリティシールド](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) アドオンの機能。

CJA 用の CMK を設定するには、次の手順に従います。

1. CMK を使用する権利があることを確認するには、Adobeアカウントチームに問い合わせます。
1. CJA でのみ使用する新しい Azure Key Vault を作成します。
1. Azure キー値を Azure CJA CMK アプリに結び付けます（リンクをたどってください）。
1. CMK 設定をリクエストするAdobeカスタマーケアチケットを作成します。 チケットに Azure URI を含めます。
1. Adobeカスタマーケアが、CJA データに対する CMK アプリケーションの完了を確認します。
