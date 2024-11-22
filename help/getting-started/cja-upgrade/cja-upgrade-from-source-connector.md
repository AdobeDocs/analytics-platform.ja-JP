---
title: Analytics ソースコネクタからCustomer Journey Analytics用の Web SDK への移行
description: Customer Journey Analyticsへのアップグレード時に Analytics ソースコネクタから Web SDK に移行する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Analytics ソースコネクタからCustomer Journey Analytics用の Web SDK への移行

>[!NOTE]
> 
>[Customer Journey Analytics アップグレード チェックリスト ](https://gigazelle.github.io/cja-ttv/) の質問に答える際は、このページの情報を使用してください。

Analytics ソースコネクタを、Customer Journey Analyticsの唯一の実装として使用する場合、固有の欠点があります。

Analytics ソースコネクタ実装のみを使用して、既にCustomer Journey Analyticsにアップグレードしている場合は、（履歴データを引き継ぐための） Analytics ソースコネクタを使用する実装に、（継続的なデータ収集のための） Web SDK の新しい実装を組み合わせて移行することを検討してください。

## Analytics ソースコネクタのみを使用する場合のメリットとデメリットについて

Analytics ソースコネクタを使用するメリットとデメリットについては、[Analytics ソースコネクタをCustomer Journey Analyticsにのみ使用してアップグレードする ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md) を参照してください。

## Analytics ソースコネクタから Web SDK への移行

以下は、Analytics ソースコネクタのみの使用から、Analytics ソースコネクタと Web SDK 実装の両方で構成される実装に移行するプロセスの概要です。

1. [Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) の記事の詳細な推奨アップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) の説明に従って、Web SDK 実装を作成 [ ます。

   Web SDK 実装を設定したら、次の手順を続行します。

1. [Analytics ソースコネクタ用の XDM スキーマを作成します ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

1. Analytics ソースコネクタの各Adobe Analytics ディメンションを、Web SDK スキーマのディメンションにマッピングします。

   1. 
      <!-- how do you get here -->

   1. 「**[!UICONTROL 標準フィールドをマッピング]**」セクションで、「**[!UICONTROL カスタム]**」タブを選択します。

   1. 「**[!UICONTROL 新しいマッピングを追加]**」を選択します。

      ![ スキーマフィールドのマッピング ](assets/schema-mapping.png)

   1. 「**[!UICONTROL Source フィールド]**」で、「Adobe Analytics ExperienceEvent テンプレート」フィールドグループからAdobe Analytics フィールドを選択します。 次に、**[!UICONTROL ターゲットフィールド]** で、マッピングする XDM フィールドを選択します。

   1. Adobe Analyticsでのデータ収集に使用するAdobe Analytics ExperienceEvent テンプレートフィールドグループのフィールドごとに、このプロセスを繰り返します。

1. 元の Analytics ソースコネクタで自動的に作成されたデータセットをCustomer Journey Analytics接続に追加します。

   詳しくは、[ 現在の Analytics ソースコネクタから接続へのデータセットの追加 ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md) を参照してください。

1. （条件付き）ルックアップデータセットを使用する場合、ルックアップデータセットを作成して接続に追加する必要があります。 詳しくは、[Customer Journey Analytics内のデータを分類するためのルックアップデータセットの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) を参照してください。

1. 元の Analytics ソースコネクタを削除します。<!-- need to add steps somewhere about how to do this -->

1. [ 新しい Analytics ソースコネクタを作成し、フィールドをマッピングします ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。
