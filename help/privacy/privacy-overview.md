---
title: Customer Journey Analytics のプライバシーの概要
description: Customer Journey Analytics でのプライバシー設定の仕組みを説明します。
translation-type: ht
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Customer Journey Analytics のプライバシーの概要

一般に、Customer Journey Analytics のプライバシー関連の設定は、Adobe Experience Platform から継承されます。

## GDPR

Customer Journey Analytics は、EU 一般データ保護規則（GDPR）中央サービスを直接登録せず、代わりに Experience Platform でおこなわれたデータセットの変更をすべて継承します。アドビでは、GDPR の削除リクエストの実施や、パイプラインでそれらが完了したことを通知するために、Platform Data Lake を使用しています。パイプラインをリッスンし、影響を受けるバッチに加えられたすべての変更を Customer Journey Analytics で同期して、イベントデータセットを取得します。GDPR の削除要求による影響を受けるプロファイルと参照データセットは、削除要求のたびに、再度完全に取り込まれます。削除要求は、Data Lake での削除イベントから 7 日以内に必ず実行されます。

## CCPA

カリフォルニア州消費者プライバシー法（CCPA）は、米国カリフォルニア州の居住者のプライバシー権と消費者保護を厳格化します。この法律は、2020 年 1 月 1 日に施行されます。CCPA は、カリフォルニア州の居住者に新しいプライバシー権を提供します。これには、自身の個人データにアクセスして削除する権利、自身の個人データが（誰に）販売または公開されているかどうかを知る権利、および自身の個人データの販売を拒否する権利が含まれます。CCPA を見越し、プライバシーサービスは個人データの販売のオプトアウトに対するリクエストをサポートします。
