---
title: データセットへの標準検索の追加
description: 標準の検索を使用して、Customer Journey Analyticsの便利なディメンションでレポートを拡張します。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: 067502a0d69bd0b085ecb5e6cbd3ae062f33daef
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 29%

---

# データセットへの標準検索の追加

>[!IMPORTANT]
>標準検索は、CJA の Analytics Data Connector データソースでのみ使用できます。 これらは、 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) またはExperience Platformデータ収集 API

標準の検索 (Adobeが提供する検索とも呼ばれます ) は、Customer Journey Analyticsが、自分では役に立たないが他のデータと結合する場合に役立つ、一部のディメンションや属性に関するレポートを作成できる機能を強化します。 例としては、モバイルデバイスの属性、OS ディメンションとブラウザーディメンションの属性（ブラウザーのバージョン番号など）があります。「標準参照」は、参照データセットに似ています。 標準の参照は、組織全体でExperience Cloud可能です。 グローバル検索は、特定の XDM スキーマフィールドを含んだすべてのイベントデータセットに自動的に適用されます（具体的なフィールドについては、以下を参照してください）。分類するスキーマの各場所に、標準の検索データセットがAdobeされます。

従来の Adobe Analytics では、これらのディメンションは単独で表示されます。一方、CJA では、データビューを作成する際に、これらのディメンションを積極的に含める必要があります。接続ワークフローで、標準検索のキーを持つデータセットとしてフラグ付けされたデータセットを選択します。 データビュー UI は、レポートで使用できるすべての標準参照ディメンションを自動的に含めることを認識します。 すべての地域およびすべてのアカウントにおいて、検索ファイルは自動的に最新の状態に保たれ、使用可能になります。これらは、顧客に関連付けられた地域固有の組織に保存されます。

## AdobeData Connector データセットで標準検索を使用する

標準参照データセットは、レポート時に自動的に適用されます。 Analytics Data Connector を使用し、Adobeが標準参照を提供するディメンションを取り込む場合、この標準参照が自動的に適用されます。 イベントデータセットに XDM フィールドが含まれている場合は、それに対して標準検索を適用できます。

### 使用可能な標準ルックアップフィールド

* `browser`
   * `browser`、`group_id`、`id`
* `browser_group`
   * `browser_group`、`id`
* `os`
   * `os`、`group_id`、`id`
* `os_group`
   * `os_group`、`id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## 標準ルックアップディメンションのレポート

標準参照ディメンションに関するレポートを作成するには、Customer Journey Analyticsでデータビューを作成する際にディメンションを追加する必要があります。

![](assets/global-lookup.png)

これで、Workspace で検索データを確認できます。

![](assets/gl-reporting.png)
