---
title: 製品の使用状況データ設定
description: 製品の使用設定を有効化、無効化または構成します。
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 23%

---

# 製品の使用状況データ設定 {#product-usage-data-settings}

_データ設定_ ページでは、製品の使用設定を処理します。 このページを使用して、組織での製品の使用を有効または無効にできます。 また、データセットを作成するAdobe Experience Platform サンドボックスを設定し、必要に応じて、データ保持ウィンドウを上書きすることもできます。 製品管理者にのみ表示されます。

**[!UICONTROL Customer Journey Analytics]**/**[!UICONTROL ツール]**/**[!UICONTROL 製品の使用状況]**/**[!UICONTROL データ設定]**

>[!IMPORTANT]
>この機能を有効にする場合は、使用条件に同意してから使用する必要があります。 これらの条件に同意する場合は、組織全体を代表して同意します。

このページでは以下の設定を使用できます。

* **[!UICONTROL 製品の使用状況を有効にする]**：製品の使用状況データ収集の可用性を切り替えます。 製品の使用を有効にした後、後で無効にしても、データセット、接続およびデータビューは削除されません。 トラッキングは、オフに切り替えると、組織に対してグローバルに無効になります。
* **[!UICONTROL サンドボックス]**：スキーマとデータセットが作成されるAdobe Experience Platform サンドボックスを決定します。 選択するサンドボックスは、製品使用状況データ収集に影響を与えません。 このサンドボックス設定を変更すると、既存のデータはすべて削除されます。 選択したサンドボックスに、新しいデータセット、接続、データビューが作成されます。
* **[!UICONTROL データ保持ウィンドウを上書き]**：すべてのデータセットには、デフォルトのデータ保持ウィンドウがあります。 この設定を無効にした場合、製品の使用状況はデフォルトの期間に従います。 この設定を有効にすると、データを保持する時間を短縮できます。 データ保持期間を短縮し、コストを削減し、従業員固有のプライバシーガイドラインに準拠できるようにします。 データセットのデフォルトのデータ保持期間を超えてデータ保持を拡張することはできません。

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform サンドボックス"
>abstract="スキーマとデータセットが作成された Adobe Experience Platform サンドボックスを特定します。"

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="データ保持ウィンドウの上書き"
>abstract="製品の使用状況データの可用性を短縮して、コストの削減やプライバシーガイドラインへの準拠に役立てます。"

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Adobe Experience Platform サンドボックス"
>abstract="スキーマとデータセットが作成された Adobe Experience Platform サンドボックスを特定します。"

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="データ保持ウィンドウの上書き"
>abstract="製品の使用状況データの可用性を短縮して、コストの削減やプライバシーガイドラインへの準拠に役立てます。"
