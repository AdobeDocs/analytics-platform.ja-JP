---
title: 製品使用状況のオプトアウト設定
description: 組織内の個々のユーザーのオプトアウト設定を管理します。
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 11%

---

# 製品使用状況のオプトアウト設定 {#product-usage-opt-out-settings}

_オプトアウト設定_ ページを使用すると、組織内のユーザーを製品の使用状況のトラッキングから除外または再含めることができます。 製品管理者にのみ表示されます。

**[!UICONTROL Customer Journey Analytics]** / **[!UICONTROL ツール]** / **[!UICONTROL 製品の使用状況]** / **[!UICONTROL オプトアウト設定]**

このページでは以下の設定を使用できます。

* **[!UICONTROL オプトアウトユーザー]**：組織内のすべてのCustomer Journey Analyticsユーザーを含むドロップダウンリスト。 このドロップダウンリストからユーザーを選択し、「**[!UICONTROL オプトアウト]**」を選択して、製品使用状況のトラッキングからそのユーザーを除外します。 このユーザーは、以下の [!UICONTROL  オプトアウトユーザーリスト ] テーブルに追加されます。
* **[!UICONTROL オプトアウトユーザーリスト]**：製品使用状況のトラッキングから現在オプトアウトされているすべてのユーザーを表示するテーブル。 ユーザーを製品使用状況トラッキングにオプトインするには、特定のユーザーの横にあるチェックボックスをオンにし、「**[!UICONTROL オプトイン]**」ボタンを選択します。

Adobeでは、クライアントサイドのトラッキングとサーバーサイドのトラッキングを組み合わせて、組織の商品使用状況データを収集します。 ユーザーが最初にオプトアウトすると、ログアウトしてCustomer Journey Analyticsに戻るまで、そのユーザーのデバッガーにクライアントサイドのトラッキングデータが表示される場合があります。 Adobeのサーバーサイド検証により、オプトアウトされたユーザーに対してクライアントサイドのトラッキングデータが破棄されるようにします。

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="オプトアウトユーザー"
>abstract="製品使用状況のトラッキングからユーザーを除外します。"

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="オプトアウトユーザー"
>abstract="製品使用状況のトラッキングからユーザーを除外します。"
