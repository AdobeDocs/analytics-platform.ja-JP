---
title: データセットへの標準検索の追加
description: 標準検索を使用して、Customer Journey Analytics の便利なディメンションでのレポートを拡張します。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 73%

---

# データセットへの標準検索の追加

>[!IMPORTANT]
>標準検索は、Customer Journey Analyticsの Analytics ソースコネクタデータソースでのみ使用できます。 これらは、標準の Adobe Analytics 実装、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)、または Experience Platform Data Collection API で使用できます。

標準検索（アドビ提供の検索とも呼ばれる）は、Customer Journey Analytics の機能を強化して、単体では役に立たなくても、他のデータと結合すると役立つディメンションや属性についてレポートします。例としては、モバイルデバイスの属性、OS ディメンションおよびブラウザーディメンションの属性（ブラウザーのバージョン番号など）があります。「標準ルックアップ」は、ルックアップデータセットに似ています。 標準検索は Experience Cloud 組織をまたいで適用できます。これらは、特定の XDM スキーマフィールドを含むすべてのイベントデータセットに自動的に適用されます（特定のフィールドについては、以下を参照してください）。標準の検索データセットは、アドビが分類しているスキーマの場所ごとに存在します。

従来のAdobe Analyticsでは、これらのディメンションは単独で表示されますが、Customer Journey Analyticsでは、データビューを作成する際に、これらのディメンションを積極的に含める必要があります。 接続ワークフローでは、標準検索用のキーを持つデータセットとしてフラグが付けられたデータセットを選択します。データビュー UI は、すべての標準検索ディメンションを自動的に認識し、レポートに使用可能として含めます。すべての地域およびすべてのアカウントにおいて、検索ファイルは自動的に最新の状態に保たれ、使用可能になります。これらは、顧客に関連付けられた地域固有の組織に保存されます。

## Analytics ソースコネクタデータセットで標準検索を使用する

標準検索データセットは、レポート時に自動的に適用されます。Analytics ソースコネクタを使用し、Adobeが標準参照を提供するディメンションを取り込む場合、この標準参照は自動的に適用されます。 イベントデータセットに XDM フィールドが含まれている場合は、標準検索を適用できます。

<!--
### Specific IDs that need to be populated

The following IDs need to be populated in the specific XDM mixins for this functionality to work:

* Environment Details Mixin – device/typeID value populated - Must match Device Atlas IDs and will populate device data.
* Adobe Analytics ExperienceEvent Template Mixin or Adobe Analytics ExperienceEvent Full Extension Mixin with analytics/environment/browserIDStr and analytics/environment/operatingSystemIDStr. Both must match the Adobe IDs and  populate browser and OS data, respectively.

You need these mixins with the three IDs populated (device/typeID, environment/browserIDStr, and environment/operatingSystemIDStr). The lookup dimensions will then be pulled automatically by Customer Journey Analytics and will be available in the Data View.

The catch here is that they can only populate those IDs today if they have a direct relationship with Device Atlas. They are Device Atlas IDs, and they provide an API to allow a customer to look them up. This is a significant hurdle, and we may just want to take the reference to this capability out of the product documentation until we have a productized way to expose the Device Atlas ID lookup functionality.
-->

### 使用可能な標準検索フィールド

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

## 標準検索ディメンションに関するレポート

標準検索ディメンションについてレポートするには、Customer Journey Analytics でデータビューを作成する際にそれらのディメンションを追加する必要があります。

![コンポーネントを追加リストを示すデータビューを作成する](assets/global-lookup.png)

そうすると、ワークスペースで検索データを確認できるようになります。

![データを表示するフリーフォームテーブル](assets/gl-reporting.png)
