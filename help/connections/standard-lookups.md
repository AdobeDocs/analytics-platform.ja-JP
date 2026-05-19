---
title: データセットへの標準参照の追加
description: Customer Journey Analyticsで標準参照を使用して、有用なディメンションでレポートを拡張する方法を説明します。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
feature: Connections
role: Admin
TQID: https://experienceleague.adobe.com/QSgHLiPoLQyr0DzEvWfSt535YR6Kch-XhWUyPXOO6gU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 42%

---

# データセットへの標準検索の追加

>[!IMPORTANT]
>
>標準ルックアップは、Customer Journey AnalyticsのAnalytics ソースコネクタのデータソースでのみ使用できます。 これらは、標準の Adobe Analytics 実装、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)、または Experience Platform Data Collection API で使用できます。
>

標準検索（アドビ提供の検索とも呼ばれる）は、Customer Journey Analytics の機能を強化して、単体では役に立たなくても、他のデータと結合すると役立つディメンションや属性についてレポートします。 例としては、モバイルデバイスの属性、OS ディメンションおよびブラウザーディメンションの属性（ブラウザーのバージョン番号など）があります。 「標準検索」は、ルックアップデータセットに似ています。 標準参照は、CX Enterprise組織全体に適用されます。 特定のXDM スキーマフィールドを含むすべてのイベントデータセットに自動的に適用されます（特定のフィールドについては、以下を参照）。 Adobeで分類するスキーマの場所ごとに、標準的なルックアップデータセットが存在します。

従来のAdobe Analyticsでは、これらのディメンションは個別に表示されますが、Customer Journey Analyticsでは、データビューを作成する際にこれらのディメンションをアクティブに含める必要があります。 接続ワークフローでは、標準検索用のキーを持つデータセットとしてフラグが付けられたデータセットを選択します。 データビュー UI は、すべての標準検索ディメンションを自動的に認識し、レポートに使用可能として含めます。 すべての地域およびすべてのアカウントにおいて、検索ファイルは自動的に最新の状態に保たれ、使用可能になります。 これらは、顧客に関連付けられた地域固有の組織に保存されます。

## Analytics ソースコネクタデータセットでの標準参照の使用

標準検索データセットは、レポート時に自動的に適用されます。 Analytics ソースコネクタを使用し、Adobeが標準ルックアップを提供するディメンションを取り込んだ場合、この標準ルックアップが自動的に適用されます。 イベントデータセットに XDM フィールドが含まれている場合は、標準検索を適用できます。

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
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
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

Adobe標準参照ディメンションについてレポートするには、Customer Journey Analyticsで[&#x200B; データビュー](/help/data-views/data-views.md)を作成する際に、これらのディメンションを1つ以上追加する必要があります。 **[!UICONTROL データビュー]** > **[!UICONTROL コンポーネント]**&#x200B;で：

1. 左側のパネルのドロップダウンメニューから「**[!UICONTROL スキーマフィールド]**」を選択します。
1. スキーマフィールドコンテナのリストから「**[!UICONTROL Adobe lookups]**」を選択します。
1. 追加するディメンションが見つかるまで、**[!UICONTROL ブラウザー]**、**[!UICONTROL モバイル]**、または&#x200B;**[!UICONTROL オペレーティングシステム]**&#x200B;にドリルダウンします。
1. ディメンションを&#x200B;**[!UICONTROL 含まれるコンポーネント]**&#x200B;内の&#x200B;**[!UICONTROL 指標]**&#x200B;または&#x200B;**[!UICONTROL ディメンション]** テーブルにドラッグします。

   ![&#x200B; コンポーネントの追加リストを表示するデータビューを作成する](assets/add-standard-lookup-dimension.gif)

その後、Workspaceでルックアップデータを使用できます。

データを表示する![&#x200B; フリーフォームテーブル &#x200B;](assets/gl-reporting.png)
