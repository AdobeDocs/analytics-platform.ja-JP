---
title: 顧客管理キー
description: 顧客管理キーを設定する方法について説明します。Customer Journey Analytics
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 57%

---

# 顧客管理キー

Adobe Customer Journey Analyticsは [医療用盾](https://www.adobe.com/trust/compliance/hipaa-ready.html) およびプライバシーとセキュリティシールドをご利用のお客様は、Azure Customer Managed Key(CMK) を利用してCustomer Journey Analyticsデータに適用できます。  このプロセスは、[Adobe Experience Platform CMK の設定](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=ja)とは別のものです。

>[!NOTE]
>
>顧客管理キーは現在、[Healthcare Shield またはプライバシーとセキュリティシールド](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html)アドオンサービスを購入した組織のみが利用できます。

## Customer Journey Analytics用の CMK の設定

次の手順に従って、Customer Journey Analytics用に CMK を設定します。

1. Adobe Customer Journey Analytics CMK を使用する権利があることを確認するには、Adobeアカウントチームに問い合わせます。
1. Azure で、自分がアプリケーション管理者、クラウドアプリケーション管理者、グローバル管理者などの権限がある役割を持つ管理者であることを確認します。[Microsoft の詳細情報](https://learn.microsoft.com/ja-jp/azure/active-directory/roles/permissions-reference)
1. Customer Journey Analyticsでのみ使用する新しい Azure Key Vault を作成します。 [Microsoft の詳細情報](https://learn.microsoft.com/ja-jp/azure/key-vault/general/)
1. Key Vault 内のキーへのアクセス権を Adobe Azure アプリに付与します。これは、Adobe アプリケーション ID：251e3919-1940-4296-bb8b-6b9a5e8a4805 です。[Microsoft の詳細情報](https://learn.microsoft.com/ja-jp/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. CMK 設定をリクエストするアドビカスタマーケアチケットを作成します。チケットに Azure URI を含めます。URI は、Azure キーの「**キー識別子**」フィールドにあります。

   ![https://cmkoberontest.vault.azure.netの URI を表示するキー識別子フィールド](assets/key-identifier.png)

1. Adobeカスタマーケアが、お客様のCustomer Journey Analyticsデータで CMK アプリケーションが完了したことを確認します。

Platform で使用されるすべてのデータは、CMK の有無にかかわらず、転送時および保管時に暗号化され、データのセキュリティを維持します。Adobe Experience Platform の暗号化について詳しくは、[こちら](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=ja)を参照してください。
