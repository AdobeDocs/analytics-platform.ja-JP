---
title: 顧客の遍歴分析のプライバシーの概要
description: Customer Jurney Analyticsでのプライバシー設定の仕組みを説明します。
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# 顧客の遍歴分析のプライバシーの概要

一般に、Customer Jeurney Analyticsのプライバシー関連の設定は、Adobe Experience Platformから継承されます。

## GDPR

Customer Jeurney Analyticsは、General Data Protection Regulation(GDPR)Central Serviceを直接登録せず、代わりにExperience Platformで行われたデータセットの変更をすべて継承します。 GDPRの削除リクエストを実施し、GDPRがパイプラインで完了したことを通知するには、Platform Data Lakeを使用します。 パイプラインをリッスンし、影響を受けるバッチに対するすべての変更をCustomer Jeurney Analyticsで同期して、イベントデータセットを取得します。 GDPRの削除要求の影響を受けるプロファイルと参照データセットは、削除要求のたびに完全に再取り込みされます。 Data Lakeでの削除イベントから7日以内に削除要求が実行されることを保証します。

## CCPA

カリフォルニア州消費者プライバシー法（CCPA）は、米国カリフォルニア州の居住者のプライバシー権と消費者保護を厳格化します。この法律は、2020 年 1 月 1 日に施行されます。CCPA は、カリフォルニア州の居住者に新しいプライバシー権を提供します。これには、自身の個人データにアクセスして削除する権利、自身の個人データが（誰に）販売または公開されているかどうかを知る権利、および自身の個人データの販売を拒否する権利が含まれます。CCPA を見越し、プライバシーサービスは個人データの販売のオプトアウトに対するリクエストをサポートします。
