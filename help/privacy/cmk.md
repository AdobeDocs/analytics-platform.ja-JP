---
title: 顧客管理キー
description: Customer Journey Analytics の顧客管理キーを設定する方法について説明します。
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
autotag-review: '2026-05-19T09:16:21.318Z'
TQID: 'https://experienceleague.adobe.com/jx1pw9U5sw42999O132esMBoUcQ8hWuUKzzN3WLAcyY'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: c5ed78d1-99be-42e1-b164-a20a3685241e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d095671a-1355-40aa-8b5f-06c33c68080bid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 561
ht-degree: 87%

---

# 顧客管理キー

Adobe Customer Journey Analytics は、[Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) およびプライバシーとセキュリティシールドのお客様が Customer Journey Analytics データに顧客管理キー（CMK）を使用するためのオプションを提供します。 このプロセスは、[Adobe Experience Platform CMK の設定](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview)とは別のものです。 顧客管理キーは、[Healthcare Shield またはプライバシーとセキュリティシールド](https://experienceleague.adobe.com/ja/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield)アドオンサービスを購入した組織のみが利用できます。

## Azure 上の Customer Journey Analytics 用の顧客管理キーの設定

Azure で実行されている Customer Journey Analytics の CMK を設定するには、次の手順に従います。

1. Adobe Customer Journey Analytics CMK の使用権限があり、組織が Azure で動作する Adobe Experience Platform を使用していることを確認します。 アドビのアカウントチームに問い合わせることで、これらの使用権限を確認できます。
1. Azure で、自分がアプリケーション管理者、クラウドアプリケーション管理者、グローバル管理者などの権限がある役割を持つ管理者であることを確認します。 詳しくは、[Microsoft Entra のビルトインの役割](https://learn.microsoft.com/ja-jp/entra/identity/role-based-access-control/permissions-reference)を参照してください。
1. Customer Journey Analytics でのみ使用する新しい Azure Key Vault を作成します。 詳しくは、[Microsoft Azure Key Vault ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/general/)を参照してください。
1. Key Vault 内のキーへのアクセス権を Adobe Azure アプリに付与します。 これには、次のいずれかの方法を使用します。
   * 次のURLを介した承認同意による権限の付与：[https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&amp;redirect_uri=https://experience.adobe.com&amp;scope=user.read](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&redirect_uri=https://experience.adobe.com&scope=user.read)

   * [既存のアカウントに対する顧客管理キーの設定](https://learn.microsoft.com/ja-jp/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)の手順に従います。 アドビアプリケーション ID は次のとおりです。

     **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. CMK 設定をリクエストするアドビカスタマーケアチケットを作成します。 チケットに Azure URI を含めます。 URI は、Azure キーの「**キー識別子**」フィールドにあります。

   ![https://cmkoberontest.vault.azure.net の URI を示すキー識別子フィールド](assets/key-identifier.png)

1. アドビカスタマーケアが、Customer Journey Analytics データに対する CMK アプリケーションの完了を確認します。

プラットフォームで使用されるすべてのデータは、顧客管理キーの有無にかかわらず、転送時および保管時に暗号化され、データのセキュリティを維持します。 Adobe Experience Platform の暗号化については、[Adobe Experience Platform でのデータ暗号化](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/governance-privacy-security/encryption)を参照してください。

## Amazon Web Services 上の Customer Journey Analytics 用の顧客管理キーの設定

>[!AVAILABILITY]
>
>この節の内容は、Amazon Web Services（AWS）上で動作する Experience Platform の実装に適用されます。 AWS 上で動作する Experience Platform は、現在、限られた数のお客様が利用できます。 サポートされる Experience Platform インフラストラクチャについて詳しくは、[Experience Platform マルチクラウドの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/multi-cloud)を参照してください。

組織が Amazon Web Services で動作する Adobe Experience Platform を使用する場合、CMK は既に設定されています。 追加の設定は必要ありません。
