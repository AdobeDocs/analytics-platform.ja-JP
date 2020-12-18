---
title: データセットに対する追加グローバル参照
description: グローバル検索を使用して、Customer Journey Analyticsで役立つディメンションを使用してレポートを拡張します。
translation-type: tm+mt
source-git-commit: b3c9757421537d2d84a78a4d37e9bfc362438d40
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---


# データセットに対する追加グローバル参照

グローバル検索を使用すると、Customer Journey Analyticsが自分では役に立たないが他のデータと結合する場合に役立つディメンションや属性の一部をレポートできるようになります。 例としては、モバイルデバイスの属性、ブラウザーのバージョン番号など、OSディメンションとブラウザーディメンションの属性が含まれます。 「グローバルルックアップ」は、ルックアップデータセット(従来のAdobe Analyticsでは分類と呼ばれています)に非常に似ています。 ただし、グローバル検索はExperience Cloud組織全体に適用できます。 グローバル検索は、特定のXDMスキーマフィールドを含むすべてのイベントデータセットに自動的に適用されます（以下で、各フィールドについて説明します）。
Adobeが分類するスキーマの場所ごとに、グローバルルックアップデータセットが存在します。 グローバル参照データセットは、Analyticsソースコネクターで使用することも、グローバル参照データセットを受け入れる他のカスタムデータセットと共に使用することもできます。

従来のAdobe Analyticsでは、これらのディメンションはそれぞれ表示されますが、CJAでは、データ表示を作成する際に、これらのディメンションを積極的に含める必要があります。 Connectionsワークフローで、グローバル検索のキーを持つデータセットとしてフラグ付けされたデータセットを選択すると、レポートに使用できるすべてのグローバル参照ディメンションがデータ表示UIに含まれます。 データ表示ワークフローでは、データ表示に使用できるグローバルルックアップディメンションが含まれています。 すべての地域およびすべてのアカウントで、ルックアップファイルは自動的に最新の状態に保たれ、使用可能になります。 顧客に関連付けられた地域固有の組織に保存されます。

## AdobeData Connectorデータセットに対するグローバル検索の使用

グローバル参照データセットは、レポート時に自動的に適用されます。 [Analytics Data Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#connectors)を使用し、Adobeがグローバル参照を提供するディメンションを取り込む場合、このグローバル参照が自動的に適用されます。 イベントデータセットに[XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en)フィールドが含まれている場合は、それに対してグローバル検索を適用できます。

## カスタムデータセットを使用したグローバル検索の使用

イベントデータセットには、グローバル参照データセットと互換性のあるキーが必要です。 標準の[Adobe Experience Platformスキーマミックスイン](https://experienceleague.adobe.com/docs/experience-platform/xdm/mixins/event/environment-details.html?lang=en#mixins)を追加して、適切なXDMフィールドにデータを入力する限り、カスタムデータセットをグローバルルックアップで動作させることができます。

## 使用可能なグローバルルックアップフィールド

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

## グローバル参照ディメンションに関するレポート

グローバル参照ディメンションに関するレポートを作成するには、Customer Journey Analyticsでデータ表示を作成する際にディメンションを追加する必要があります。

![](assets/global-lookup.png)

その後、Workspaceで参照データを表示できます。

![](assets/gl-reporting.png)

