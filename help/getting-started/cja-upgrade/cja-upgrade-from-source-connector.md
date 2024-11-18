---
title: Analytics ソースコネクタから Web SDK に移動してCustomer Journey Analyticsする
description: Customer Journey Analyticsへのアップグレード時に Analytics ソースコネクタから Web SDK に移行する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Analytics ソースコネクタから Web SDK に移動してCustomer Journey Analyticsする

>[!NOTE]
> 
>[Customer Journey Analytics アップグレード チェックリスト ](https://gigazelle.github.io/cja-ttv/) の質問に答える際は、このページの情報を使用してください。

Analytics ソースコネクタを、Customer Journey Analyticsの唯一の実装として使用する場合、固有の欠点があります。 Analytics ソースコネクタの実装のみを使用して、既にCustomer Journey Analyticsにアップグレードしている場合は、Web SDK の実装への移行を検討する必要があります。

Adobeでは、履歴データを取り込むための Analytics ソースコネクタを、継続的なデータ収集のための Web SDK の新しい実装と組み合わせて使用することをお勧めします。

## Analytics ソースコネクタのみを使用する場合のメリットとデメリットについて

Analytics ソースコネクタを使用するメリットとデメリットについては、[Analytics ソースコネクタをCustomer Journey Analyticsにのみ使用してアップグレードする ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md) を参照してください。

## Analytics ソースコネクタから Web SDK に移動します

Analytics ソースコネクタから、Analytics ソースコネクタと Web SDK 実装の両方で構成される実装に移行するプロセスの概要を次に示します。

1. [Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) の記事の詳細な推奨アップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) の説明に従って、Web SDK 実装を作成 [ ます。

   Web SDK 実装が設定されたら、次の手順を続行します。

1. Web SDK 実装でAdobe Analytics スキーマと XDM スキーマのどちらを使用するかを決定します。

   詳しくは、[Customer Journey Analyticsするスキーマの選択 ](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) を参照してください。

1. （条件付き）Adobe Analytics スキーマを使用する予定の場合は、Analytics ソースコネクタによって自動的に作成されたデータセットをCustomer Journey Analytics接続に追加します。

   詳しくは、[ 接続への Analytics ソースコネクタデータセットの追加 ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md) を参照してください。

1. （条件付き） XDM スキーマを作成する予定の場合：

   1. [Analytics ソースコネクタ用の XDM スキーマを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

   1. 元の Analytics ソースコネクタで自動的に作成されたデータセットをCustomer Journey Analytics接続に追加します。

      詳しくは、[ 現在の Analytics ソースコネクタから接続へのデータセットの追加 ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md) を参照してください。

   1. 元の Analytics ソースコネクタを削除します。<!-- need to add steps somewhere about how to do this -->

   1. [ 新しい Analytics ソースコネクタを作成し、フィールドをマッピングします ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。








