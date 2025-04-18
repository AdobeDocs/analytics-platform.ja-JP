---
title: 製品の使用状況オプトアウト設定
description: 組織内の個々のユーザーのオプトアウト設定を管理します。
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '222'
ht-degree: 100%

---

# 製品の使用状況オプトアウト設定 {#product-usage-opt-out-settings}

_オプトアウト設定_&#x200B;ページでは、組織内のユーザーを製品の使用状況のトラッキングから除外したり、再び含めたりすることができます。 これは、製品管理者にのみ表示されます。

**[!UICONTROL Customer Journey Analytics]**／**[!UICONTROL ツール]**／**[!UICONTROL 製品の使用状況]**／**[!UICONTROL オプトアウト設定]**

このページでは、次の設定を使用できます。

* **[!UICONTROL オプトアウトユーザー]**：組織内のすべての Customer Journey Analytics ユーザーを含むドロップダウンリスト。このドロップダウンリストからユーザーを選択し、「**[!UICONTROL オプトアウト]**」を選択して、そのユーザーを製品の使用状況のトラッキングから除外します。このユーザーは、以下の[!UICONTROL オプトアウトユーザーリスト]のテーブルに追加されます。
* **[!UICONTROL オプトアウトユーザーリスト]**：現在、製品の使用状況のトラッキングからオプトアウトされているすべてのユーザーを表示するテーブル。ユーザーを製品の使用状況のトラッキングに再びオプトインするには、特定のユーザーの横にあるチェックボックスをオンにして、「**[!UICONTROL オプトイン]**」ボタンを選択します。

アドビでは、クライアントサイドとサーバーサイドのトラッキングを組み合わせて、組織の製品の使用状況データを収集します。ユーザーが最初にオプトアウトすると、ログアウトして Customer Journey Analytics に再びログインするまで、このユーザーのデバッガーにクライアントサイドのトラッキングデータが表示される可能性があります。アドビ のサーバーサイド検証により、オプトアウトしたユーザーのクライアントサイドのトラッキングデータが破棄されます。

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="オプトアウトユーザー"
>abstract="製品使用状況のトラッキングからユーザーを除外します。"

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="オプトアウトユーザー"
>abstract="製品使用状況のトラッキングからユーザーを除外します。"
