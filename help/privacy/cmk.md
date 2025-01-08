---
title: 顧客管理キー
description: Customer Journey Analytics用の顧客管理キーの設定方法を説明します。
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 15%

---

# 顧客管理キー

Adobe Customer Journey Analyticsは、[Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) およびプライバシーとセキュリティシールドのお客様が、Customer Journey Analyticsデータに顧客管理キー（CMK）を使用するためのオプションを提供します。 このプロセスは、[Adobe Experience Platform CMK の設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview) とは別のものです。 顧客管理キーは、[Healthcare Shield またはプライバシーとセキュリティシールド ](https://experienceleague.adobe.com/ja/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield) アドオンサービスを購入した組織のみが利用できます。

## Azure でのCustomer Journey Analytics用の顧客管理キーの設定

Azure で実行されているCustomer Journey Analytics用に CMK を設定するには、次の手順に従います。

1. Adobe Customer Journey Analytics CMK の使用権限があり、組織が Azure で動作するAdobe Experience Platformを使用していることを確認します。 Adobeアカウントチームに問い合わせることで、これらの資格を確認できます。
1. Azure で、自分がアプリケーション管理者、クラウドアプリケーション管理者、グローバル管理者などの権限がある役割を持つ管理者であることを確認します。詳しくは、[Microsoft Entra の組み込みの役割 ](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference) を参照してください。
1. Customer Journey Analyticsでのみ使用する新しい Azure Key Vault を作成します。 詳しくは、[Microsoft Azure Key Vault ドキュメント ](https://learn.microsoft.com/ja-jp/azure/key-vault/general/) を参照してください。
1. Key Vault 内のキーへのアクセス権を Adobe Azure アプリに付与します。詳しくは [ 既存アカウントの顧客管理キーの設定 ](https://learn.microsoft.com/ja-jp/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault) を参照してください。 Adobeアプリケーション ID は次のとおりです。

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. CMK 設定をリクエストするアドビカスタマーケアチケットを作成します。チケットに Azure URI を含めます。URI は、Azure キーの「**キー識別子**」フィールドにあります。

   ![https://cmkoberontest.vault.azure.netの URI を示すキー識別子フィールド ](assets/key-identifier.png)

1. Adobeカスタマーケアが、Customer Journey Analyticsデータに対する CMK アプリケーションの完了を確認します。

Platform で使用されるすべてのデータは、顧客が管理するキーの有無にかかわらず、転送時および保存時に暗号化され、データのセキュリティを維持します。 Adobe Experience Platformの暗号化については、[Adobe Experience Platformでのデータ暗号化 ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption) を参照してください。

## Amazon Web ServicesでのCustomer Journey Analytics用の顧客管理キーの設定

>[!AVAILABILITY]
>
>この節の内容は、Amazon Web Services（AWS）上で動作するExperience Platformの実装に適用されます。 AWSで実行されるExperience Platformは、現在、限られた数のお客様が利用できます。 サポートされるExperience Platformインフラストラクチャについて詳しくは、[Experience Platformマルチクラウドの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud) を参照してください。

Amazon Web Servicesで動作するAdobe Experience Platformを使用する場合、CMK は既に設定されています。 追加の設定は必要ありません。
