---
title: 顧客管理キー
description: CJA 用の顧客管理キーの設定方法について説明します。
source-git-commit: 903c1423c91b220524174fa900a9ec13cd2051c6
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 83%

---

# 顧客管理キー

>[!NOTE]
>
>この機能は、2022年11月に提供されます。

Customer Journey Analytics (CJA) は、[Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) およびプライバシーとセキュリティシールドのお客様が Azure 顧客管理キー（CMK）を利用して CJA データに適用するためのオプションを提供します。このプロセスは、[Adobe Experience Platform CMK の設定](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=ja)とは別のものです。

>[!NOTE]
>
>顧客管理キーは現在、[Healthcare Shield またはプライバシーとセキュリティシールド](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den)アドオンサービスを購入した組織のみが利用できます。

## CJA 用の CMK の設定

CJA 用の CMK を設定するには、次の手順に従います。

1. Adobe アカウントチームに確認して、Adobe CJA CMK の使用権限があることを確認します。
1. Azure で、自分がアプリケーション管理者、クラウドアプリケーション管理者、グローバル管理者などの権限がある役割を持つ管理者であることを確認します。[Microsoft の詳細情報](https://learn.microsoft.com/ja-jp/azure/active-directory/roles/permissions-reference)
1. CJA でのみ使用する新しい Azure Key Vault を作成します。[Microsoft の詳細情報](https://learn.microsoft.com/ja-jp/azure/key-vault/general/)
1. Key Vault 内のキーへのアクセス権を Adobe Azure アプリに付与します。これは、Adobe アプリケーション ID：251e3919-1940-4296-bb8b-6b9a5e8a4805 です。[Microsoft の詳細情報](https://learn.microsoft.com/ja-jp/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. CMK 設定をリクエストするアドビカスタマーケアチケットを作成します。チケットに Azure URI を含めます。URI は、 **キー識別子** Azure キーのフィールドに入力します。

   ![](assets/key-identifier.png)

1. アドビカスタマーケアが、CJA データに対する CMK アプリケーションの完了を確認します。

Platform で使用されるすべてのデータは、CMK の有無に関わらず、送信時および保存時に暗号化され、データのセキュリティを維持します。 Adobe Experience Platform暗号化の詳細については、 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=en).