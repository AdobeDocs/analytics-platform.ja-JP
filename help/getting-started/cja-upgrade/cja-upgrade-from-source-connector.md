---
title: Analytics ソースコネクタから Customer Journey Analytics 向け Web SDK への移行
description: Customer Journey Analyticsにアップグレードする際に、Analytics ソースコネクタから web SDKに移行する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 15%

---

# Analytics ソースコネクタから Customer Journey Analytics 向け Web SDK への移行 {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Analytics ソースコネクタの実装"
>abstract="Analytics ソースコネクタを使用すると、Customer Journey Analytics から簡単に価値を得ることができますが、Adobe Analytics と Customer Journey Analytics の両方に対して料金を支払う必要があります。このガイドは、独立した Web SDK の実装に移行するのに役立ちます。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analyticsのアップグレードチェックリスト ](https://gigazelle.github.io/cja-ttv/) に関する質問に答える際は、このページの情報を使用してください。

Customer Journey Analyticsの唯一の実装として Analytics ソースコネクタを使用する場合、固有の欠点があります。

Analytics ソースコネクタ実装のみを使用して、既にCustomer Journey Analyticsにアップグレードしている場合、Adobeでは、（履歴データ用に） Analytics ソースコネクタを使用する実装に、（継続的なデータ収集用に） web SDKの新しい実装を組み合わせて移行することをお勧めします。

## Analytics ソースコネクタのみを使用する場合のメリットとデメリットについて

Analytics ソースコネクタを使用するメリットとデメリットについては、[Analytics ソースコネクタのみを使用してCustomer Journey Analyticsにアップグレードする ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md) を参照してください。

## Analytics ソースコネクタから Web SDKへの移行

以下は、Analytics ソースコネクタのみの使用から、Analytics ソースコネクタと Web SDK実装の両方で構成される実装に移行するプロセスの概要です。

1. [Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) の記事の詳細な推奨アップグレード手順 ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) の説明に従って、web SDKを実装 [ ます。

   Web SDKの実装が設定されたら、次の手順を続行します。

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

1. （条件付き）ルックアップデータセットを使用する場合、ルックアップデータセットを作成して接続に追加する必要があります。 詳しくは、[Customer Journey Analyticsでデータを分類するためのルックアップデータセットの作成 ](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) を参照してください。

1. 元の Analytics ソースコネクタを削除します。<!-- need to add steps somewhere about how to do this -->

1. [ 新しい Analytics ソースコネクタを作成し、フィールドをマッピングします ](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。
