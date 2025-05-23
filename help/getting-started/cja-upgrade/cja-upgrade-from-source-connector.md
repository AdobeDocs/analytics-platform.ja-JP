---
title: Analytics ソースコネクタから Customer Journey Analytics 向け Web SDK への移行
description: Customer Journey Analytics にアップグレードする際に、Analytics ソースコネクタから Web SDK に移行する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '538'
ht-degree: 100%

---

# Analytics ソースコネクタから Customer Journey Analytics 向け Web SDK への移行 {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Analytics ソースコネクタの実装"
>abstract="Analytics ソースコネクタを使用すると、Customer Journey Analytics から簡単に価値を得ることができますが、Adobe Analytics と Customer Journey Analytics の両方に対して料金を支払う必要があります。このガイドは、独立した Web SDK の実装に移行するのに役立ちます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="既存の Analytics ソースコネクタの削除"
>abstract="現在使用している Analytics ソースコネクタは、組織のカスタムスキーマと互換性がありません。ただし、データは Analytics レポートスイートにまだ存在しています。この手順では、現在の Analytics ソースコネクタを削除するので、後続の手順で正しいスキーマを使用して再作成できます。<br><br>ソースコネクタを削除する前に、組織内の他のユーザーと調整して、ソースコネクタの削除が組織内のレポートに影響を与えないことを確認することをお勧めします。この調整が完了するまでに数週間かかる可能性があります。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Analytics ソースコネクタを Customer Journey Analytics の唯一の実装として使用する際に、固有のデメリットがあります。

組織が Analytics ソースコネクタ実装のみを使用して Customer Journey Analytics に既にアップグレードしている場合、アドビでは継続的なデータ収集用に Web SDK の新しい実装に移行し、履歴データ用に Analytics ソースコネクタのみを使用することをお勧めします。

## Analytics ソースコネクタのみを使用する場合のメリットとデメリットについて

Analytics ソースコネクタを使用するメリットとデメリットについて詳しくは、[Analytics ソースコネクタのみを使用した Customer Journey Analyticsへのアップグレード](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)を参照してください。

## Analytics ソースコネクタから Web SDK への移行

次に、Analytics ソースコネクタのみの使用から、Analytics ソースコネクタと Web SDK 実装の両方で構成される実装に移行する高レベルのプロセスを示します。

1. Web SDK 実装の作成について詳しくは、[Adobe Analytics から Customer Journey Analytics へのアップグレード](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)の記事の[推奨されるアップグレード手順の詳細](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)を参照してください。

   Web SDK 実装を設定したら、次の手順に進みます。

1. [Analytics ソースコネクタの XDM スキーマを作成します](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

1. Analytics ソースコネクタからの各 Adobe Analytics ディメンションを Web SDK スキーマのディメンションにマッピングします。

   1. &#x200B;
      <!-- how do you get here -->

   1. 「**[!UICONTROL 標準フィールドをマッピング]**」セクションで、「**[!UICONTROL カスタム]**」タブを選択します。

   1. 「**[!UICONTROL 新しいマッピングを追加]**」を選択します。

      ![スキーマフィールドをマッピング](assets/schema-mapping.png)

   1. **[!UICONTROL 「ソース」フィールド]**&#x200B;で、Adobe Analytics ExperienceEvent テンプレートフィールドグループから Adobe Analytics フィールドを選択します。次に、**[!UICONTROL 「ターゲット」フィールド]**&#x200B;で、マッピング先の XDM フィールドを選択します。

   1. Adobe Analytics でデータを収集するために使用している Adobe Analytics ExperienceEvent テンプレートフィールドグループの各フィールドに対して、このプロセスを繰り返します。

1. 元の Analytics ソースコネクタで自動的に作成されたデータセットを Customer Journey Analytics 接続に追加します。

   詳しくは、[現在の Analytics ソースコネクタから接続へのデータセットの追加](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)を参照してください。

1. （条件付き）ルックアップデータセットを使用する場合、ルックアップデータセットを作成して接続に追加する必要があります。詳しくは、[Customer Journey Analytics でルックアップデータセットを作成してデータを分類](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)を参照してください。

1. 元の Analytics ソースコネクタを削除します。<!-- need to add steps somewhere about how to do this -->

1. [新しい Analytics ソース コネクタを作成し、フィールドをマッピングします](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

{{upgrade-final-step}}
