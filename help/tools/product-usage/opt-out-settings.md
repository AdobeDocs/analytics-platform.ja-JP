---
title: 製品使用のオプトアウト設定
description: 組織内の個々のユーザーのオプトアウト設定を管理します。
hide: true
hidefromtoc: true
source-git-commit: 8f2a340f59d8cdf97a5309ec20dc36f49b8f1129
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# 製品使用のオプトアウト設定 {#product-usage-opt-out-settings}

{{release-limited-testing}}

_オプトアウト設定_ ページを使用すると、組織内のユーザーを製品の使用状況のトラッキングから除外または再含めることができます。 製品管理者にのみ表示されます。

**Customer Journey Analytics** / **[!UICONTROL ツール]** / **[!UICONTROL 製品の使用状況]** / **[!UICONTROL オプトアウト設定]**

このページでは以下の設定を使用できます。

* **[!UICONTROL オプトアウトユーザー]**：組織内のすべてのCustomer Journey Analyticsユーザーを含むドロップダウンリスト。 このドロップダウンリストからユーザーを選択し、「**[!UICONTROL オプトアウト]**」を選択して、製品使用状況のトラッキングからそのユーザーを除外します。 このユーザーは、以下の [!UICONTROL  オプトアウトユーザーリスト ] テーブルに追加されます。
* **[!UICONTROL オプトアウトユーザーリスト]**：製品使用状況のトラッキングから現在オプトアウトされているすべてのユーザーを表示するテーブル。 ユーザーを製品使用状況トラッキングにオプトインするには、特定のユーザーの横にあるチェックボックスをオンにし、「**[!UICONTROL オプトイン]**」ボタンを選択します。

Adobeでは、クライアントサイドのトラッキングとサーバーサイドのトラッキングを組み合わせて、組織の商品使用状況データを収集します。 ユーザーが最初にオプトアウトすると、ログアウトしてCustomer Journey Analyticsに戻るまで、そのユーザーのデバッガーにクライアントサイドのトラッキングデータが表示される場合があります。 Adobeのサーバーサイド検証により、オプトアウトされたユーザーに対してクライアントサイドのトラッキングデータが破棄されるようにします。

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="オプトアウトユーザー"
>abstract="製品使用状況のトラッキングからユーザーを除外します。"
