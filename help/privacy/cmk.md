---
title: 顧客管理キー
description: CJA 用の顧客管理キーの設定方法について説明します。
hide: true
hidefromtoc: true
source-git-commit: 3aa5d9e1b426e67f27ef1909a2640f335719502a
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# 顧客管理キー

>[!NOTE]
>
>この機能は、2022 年 11 月に提供されます。

Customer Journey Analytics(CJA) は、 [医療用盾](https://www.adobe.com/trust/compliance/hipaa-ready.html) およびプライバシーとセキュリティシールドのお客様は、CJA データに適用する Azure Customer Managed Key(CMK) を利用できます。  このプロセスは、 [Adobe Experience Platform CMK の設定](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>顧客管理キーは、現在、 [ヘルスケアシールドまたはプライバシーとセキュリティシールド](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) アドオンの機能。

## CJA 用の CMK の設定

CJA 用の CMK を設定するには、次の手順に従います。

1. CJA CMK をAdobeする権利があることを確認するには、Adobeアカウントチームに問い合わせます。
1. Azure では、アプリケーション管理者、クラウドアプリケーション管理者、グローバル管理者などの特権ロールを持つ管理者であることを確認してください。 [Microsoftの詳細情報](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. CJA でのみ使用する新しい Azure Key Vault を作成します。 [Microsoftの詳細情報](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Key Vault のキーにAdobeAzure App のアクセス権を付与します。 これは、Adobeアプリケーション ID です。251e3919-1940-4296-bb8b-6b9a5e8a4805。 [Microsoftの詳細情報](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. CMK 設定をリクエストするAdobeカスタマーケアチケットを作成します。 チケットに Azure URI を含めます。
1. Adobeカスタマーケアが、CJA データに対する CMK アプリケーションの完了を確認します。
