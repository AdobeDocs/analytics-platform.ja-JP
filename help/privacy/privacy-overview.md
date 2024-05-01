---
title: Customer Journey Analytics とデータガバナンス
description: Customer Journey Analytics でのデータガバナンスの仕組みについて説明します。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 56%

---

# Adobe Customer Journey Analyticsとデータガバナンス

一般に、Customer Journey Analytics のデータガバナンス関連の設定は、Adobe Experience Platform から継承されます。

## データガバナンス

Adobe Customer Journey Analyticsとの統合 [Adobe Experience Platformのデータガバナンス](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=ja) では、機密Customer Journey Analyticsデータのラベル付けとプライバシーポリシーの実施が可能です。

Experience Platform で使用されるデータセットに関して作成されたプライバシーラベルとポリシーは、 Customer Journey Analytics データビューワークフローで表示できます。これらのラベルにより、ユーザーが機密性の高いフィールドから指標やディメンションを作成しようとしても、それができなかったり警告が表示されたりします。

また、データがCustomer Journey Analyticsから（レポート、書き出し、API などを介して）書き出されると、警告またはラベルが追加されて、特定の方法で扱う必要のある機密情報がレポートに含まれていることをユーザーに知らせます。

この統合により、コンプライアンスを管理しやすくなります。組織のデータ管理人は、使用を制限するポリシーを設定できます。その結果、Customer Journey Analyticsユーザーは、データ管理人が定義したポリシーにデータが準拠していることを認識したうえで、より自信を持ってデータを使用できます。

[詳細情報](/help/data-views/data-governance.md)

## GDPR

Customer Journey Analytics は、EU 一般データ保護規則（GDPR）中央サービスを直接登録せず、代わりに Experience Platform でおこなわれたデータセットの変更をすべて継承します。Customer Journey Analyticsは、GDPR の削除リクエストを実施し、リクエストが完了したときにCustomer Journey Analyticsに通知するために、Platform Data Lake に依存します。 イベントデータセットのCustomer Journey Analyticsで影響を受けるバッチに対して行われたすべての変更は、Platform データと同期されます。 GDPR の削除リクエストの影響を受けたプロファイルおよびルックアップデータセットは、削除リクエストのたびに完全に再取り込みされます。 削除リクエストは、通常、データレイクの削除イベントから 7 日以内に完了します。

## CCPA

カリフォルニア州消費者プライバシー法（CCPA）は、米国カリフォルニア州の居住者のプライバシー権と消費者保護を厳格化します。この法律は 2020年1月1日（PT）に施行されました。CCPA は、カリフォルニア州の居住者に新しいプライバシー権を提供します。これには、自身の個人データにアクセスして削除する権利、自身の個人データが（誰に）販売または公開されているかどうかを知る権利、および自身の個人データの販売を拒否する権利が含まれます。CCPA に従い、プライバシーサービスは個人データの販売のオプトアウトに対するリクエストをサポートします。
