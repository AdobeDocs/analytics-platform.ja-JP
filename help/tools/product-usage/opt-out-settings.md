---
title: 製品の使用状況オプトアウト設定
description: 組織内の個々のユーザーのオプトアウト設定を管理します。
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
autotag-review: '2026-05-19T09:31:49.294Z'
TQID: 'https://experienceleague.adobe.com/O67EiLS9ltB20iQ3d4mxlDcrwR06-r9SmbXZJ37slJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
  - id: cc5596a7-18f9-4e6c-87eb-ce3d0a9efb66
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 85%

---

# 製品の使用状況オプトアウト設定 {#product-usage-opt-out-settings}

_オプトアウト設定_&#x200B;ページでは、組織内のユーザーを製品の使用状況のトラッキングから除外したり、再び含めたりすることができます。 これは、製品管理者にのみ表示されます。

**[!UICONTROL Customer Journey Analytics]**／**[!UICONTROL ツール]**／**[!UICONTROL 製品の使用状況]**／**[!UICONTROL オプトアウト設定]**

このページでは、次の設定を使用できます。

* **[!UICONTROL オプトアウトユーザー]**：組織内のすべてのCustomer Journey Analytics ユーザーを含むドロップダウンメニュー。 このドロップダウンメニューからユーザーを選択し、**[!UICONTROL オプトアウト]**&#x200B;を選択して、そのユーザーを製品使用状況の追跡から除外します。 このユーザーは、以下の[!UICONTROL オプトアウトユーザーリスト]のテーブルに追加されます。
* **[!UICONTROL オプトアウトユーザーリスト]**：現在、製品の使用状況のトラッキングからオプトアウトされているすべてのユーザーを表示するテーブル。 ユーザーを製品の使用状況のトラッキングに再びオプトインするには、特定のユーザーの横にあるチェックボックスをオンにして、「**[!UICONTROL オプトイン]**」ボタンを選択します。

アドビでは、クライアントサイドとサーバーサイドのトラッキングを組み合わせて、組織の製品の使用状況データを収集します。 ユーザーが最初にオプトアウトすると、ログアウトして Customer Journey Analytics に再びログインするまで、このユーザーのデバッガーにクライアントサイドのトラッキングデータが表示される可能性があります。 アドビ のサーバーサイド検証により、オプトアウトしたユーザーのクライアントサイドのトラッキングデータが破棄されます。

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="オプトアウトユーザー"
>abstract="製品使用状況のトラッキングからユーザーを除外します。"

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="オプトアウトユーザー"
>abstract="製品使用状況のトラッキングからユーザーを除外します。"
