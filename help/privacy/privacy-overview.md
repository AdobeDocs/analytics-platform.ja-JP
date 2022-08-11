---
title: Customer Journey Analyticsとデータガバナンス
description: Customer Journey Analyticsでのデータガバナンスの仕組みについて説明します。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 1e2c5d79059a4804416288188ea4740dd94ca33d
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 51%

---

# Customer Journey Analyticsとデータガバナンス

一般に、データガバナンス関連の設定は、Adobe Experience PlatformからCustomer Journey Analyticsされます。

## データガバナンス

CJA との統合 [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) では、機密性の高い CJA データのラベル付けとプライバシーポリシーの実施を可能にします。

Experience Platformが使用するデータセットで作成されたプライバシーラベルとポリシーは、 CJA データビューワークフローで表示できます。 これらのラベルは、機密性の高いフィールドから指標やディメンションを作成するユーザーに対して、停止または警告を出します。

また、データが CJA から（レポート、書き出し、API などを介して）書き出されると、警告またはラベルが追加され、特定の方法で処理する必要のある機密情報がレポートに含まれていることをユーザーに通知します。

この統合により、コンプライアンスをより簡単に管理できます。 組織のデータ管理人は、使用を制限するポリシーを設定できます。 その結果、CJA ユーザーは、データ管理人が定義したポリシーに準拠していることを知り、より自信を持ってデータを使用できます。

[詳細情報](/help/data-views/data-governance.md)

## GDPR

Customer Journey Analytics は、EU 一般データ保護規則（GDPR）中央サービスを直接登録せず、代わりに Experience Platform でおこなわれたデータセットの変更をすべて継承します。アドビでは、GDPR の削除リクエストの実施や、パイプラインでそれらが完了したことを通知するために、Platform Data Lake を使用しています。パイプラインをリッスンし、影響を受けるバッチに加えられたすべての変更を Customer Journey Analytics で同期して、イベントデータセットを取得します。GDPR の削除要求による影響を受けるプロファイルと参照データセットは、削除要求のたびに、再度完全に取り込まれます。削除要求は、Data Lake での削除イベントから 7 日以内に必ず実行されます。

## CCPA

カリフォルニア州消費者プライバシー法（CCPA）は、米国カリフォルニア州の居住者のプライバシー権と消費者保護を厳格化します。この法律は、2020 年 1 月 1 日に施行されます。CCPA は、カリフォルニア州の居住者に新しいプライバシー権を提供します。これには、自身の個人データにアクセスして削除する権利、自身の個人データが（誰に）販売または公開されているかどうかを知る権利、および自身の個人データの販売を拒否する権利が含まれます。CCPA を見越し、プライバシーサービスは個人データの販売のオプトアウトに対するリクエストをサポートします。
