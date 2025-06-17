---
title: Customer Journey Analytics とデータガバナンス
description: Customer Journey Analytics でのデータガバナンスの仕組みについて説明します。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 40706e3118cbaf7582d8625d307358b16f1836ac
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 90%

---

# Adobe Customer Journey Analytics とデータガバナンス

一般に、Customer Journey Analytics のデータガバナンス関連の設定は、Adobe Experience Platform から継承されます。

## データガバナンス

Adobe Customer Journey Analytics と [Adobe Experience Platform のデータガバナンス](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=ja)の統合により、機密性の高い Adobe Customer Journey Analytics データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platform で使用されるデータセットに関して作成されたプライバシーラベルおよびポリシーは、Adobe Customer Journey Analytics データビューワークフローで表示できます。これらのラベルにより、ユーザーが機密性の高いフィールドから指標やディメンションを作成しようとしても、それができなかったり警告が表示されたりします。

また、データが Adobe Customer Journey Analytics から（レポート、書き出し、API などを介して）書き出されると、特定の方法で処理する必要がある機密情報がレポートに含まれていることをユーザーに知らる警告またはラベルが付加されます。

この統合により、コンプライアンスを管理しやすくなります。組織のデータ管理人は、使用を制限するポリシーを設定できます。その結果、Adobe Customer Journey Analytics ユーザーは、データ管理人により定義されたポリシーにデータが準拠していることを認識したうえで、より自信を持ってデータを使用できます。

[詳細情報](/help/data-views/data-governance.md)

## プライバシーリクエスト

Adobeは、適用される各国および国際法に従ってプライバシーリクエストを処理します。

Customer Journey AnalyticsはAdobe Experience Platformで使用可能なデータを使用するので、Adobeはデータアクセスおよび削除要求を送信するために [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja)0&rbrace;Adobe Experience Platform Privacy Service&rbrace; を提供します。 リクエストは、元のデータセットとキーが更新されたデータセットの両方に適用されます。

## GDPR

Customer Journey Analytics は、EU 一般データ保護規則（GDPR）中央サービスを直接登録せず、代わりに Experience Platform でおこなわれたデータセットの変更をすべて継承します。Adobe Customer Journey Analytics では、GDPR 削除要求の実施と要求完了時の Adobe Customer Journey Analytics への通知に、Experience Platform Data Lake を利用します。イベントデータセットについて Customer Journey Analytics で影響を受けるバッチへのあらゆる変更は、Experience Platform データと同期されます。GDPR の削除要求による影響を受けるプロファイルおよび参照データセットは、削除要求が完了するたびに、完全に再取り込みされます。削除要求は、通常、データレイクでの削除イベントから 7 日以内に完了します。

## CCPA

カリフォルニア州消費者プライバシー法（CCPA）は、米国カリフォルニア州の居住者のプライバシー権と消費者保護を厳格化します。この法律は 2020年1月1日（PT）に施行されました。CCPA は、カリフォルニア州の居住者に新しいプライバシー権を提供します。これには、自身の個人データにアクセスして削除する権利、自身の個人データが（誰に）販売または公開されているかどうかを知る権利、および自身の個人データの販売を拒否する権利が含まれます。CCPA に従い、プライバシーサービスは個人データの販売のオプトアウトに対するリクエストをサポートします。

>[!MORELIKETHIS]
>
>* [ブログ：Adobe Customer Journey Analytics で効果的なガバナンスを維持する方法](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4)
