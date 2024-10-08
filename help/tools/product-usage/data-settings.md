---
title: 製品使用状況データの設定
description: 製品の使用設定を有効化、無効化または構成します。
hide: true
hidefromtoc: true
source-git-commit: 40b761928697d1d55e1177aa7b2b3c056739ecc9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# 製品使用状況データの設定 {#product-usage-data-settings}

{{release-limited-testing}}

_データ設定_ ページでは、製品の使用設定を処理します。 このページを使用して、組織での製品の使用を有効または無効にできます。 また、データセットを作成するAdobe Experience Platform サンドボックスを設定し、必要に応じて、データ保持ウィンドウを上書きすることもできます。 製品管理者にのみ表示されます。

**Customer Journey Analytics**/**ツール**/**製品の使用状況**/**データ設定**

>[!IMPORTANT]
>
>この機能を有効にする場合は、使用条件に同意してから使用する必要があります。 これらの条件に同意する場合は、組織全体を代表して同意します。

このページでは以下の設定を使用できます。

* **製品の使用状況を有効にする**：製品の使用状況データ収集の可用性を切り替えます。 製品の使用を有効にしてから、後で無効にしても、データセット、接続、データビューは削除されません。 トラッキングは、オフに切り替えると、組織に対してグローバルに無効になります。
* **サンドボックス**：スキーマとデータセットが作成されるAdobe Experience Platform サンドボックスを決定します。 選択するサンドボックスは、製品使用状況データ収集に影響を与えません。 このサンドボックス設定を変更すると、既存のデータはすべて削除されます。 選択したサンドボックスに、新しいデータセット、接続、データビューが作成されます。
* **データ保持ウィンドウを上書き**：すべてのデータセットには、デフォルトのデータ保持ウィンドウがあります。 この設定を無効にした場合、製品の使用状況はデフォルトの期間に従います。 この設定を有効にすると、データを保持する時間を短縮できます。 データ保持期間を短縮し、コストを削減し、従業員固有のプライバシーガイドラインに準拠できるようにします。 データセットのデフォルトのデータ保持期間を超えてデータ保持を拡張することはできません。

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform サンドボックス"
>abstract="スキーマとデータセットが作成されたAdobe Experience Platform サンドボックスを特定します。"

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="データ保持ウィンドウを上書き"
>abstract="製品使用データの可用性を短縮して、コストの削減やプライバシーガイドラインへの準拠に役立てます。"
