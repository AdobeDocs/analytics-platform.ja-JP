---
title: データセットへのグローバル検索の追加
description: グローバル検索を使用して、Customer Journey Analytics の便利なディメンションでレポートを拡張します。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
translation-type: tm+mt
source-git-commit: 26ee2b61fb80b55a7982d90941ec121547423cfc
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 63%

---

# データセットへのグローバル検索の追加

グローバル検索を使用すると、Customer Journey Analytics の機能が強化され、単体では役に立たないけれど他のデータと結合すると便利なディメンションや属性の一部を報告できるようになります。例としては、モバイルデバイスの属性、OS ディメンションとブラウザーディメンションの属性（ブラウザーのバージョン番号など）があります。「グローバル参照」は、参照データセットに似ています。 グローバル検索は、Experience Cloud組織全体に適用できます。 特定のXDMスキーマフィールドを含むすべてのイベントデータセットに自動的に適用されます（以下で特定のフィールドについて説明します）。 グローバルルックアップデータセットは、Adobeが分類するスキーマの場所ごとに存在します。

従来の Adobe Analytics では、これらのディメンションは単独で表示されます。一方、CJA では、データビューを作成する際に、これらのディメンションを積極的に含める必要があります。接続ワークフローでは、グローバル参照のキーを持つデータセットとしてフラグ付けされたデータセットを選択します。 データ表示UIでは、レポート可能なすべてのグローバル参照ディメンションが含まれることを自動的に認識します。 すべての地域およびすべてのアカウントにおいて、検索ファイルは自動的に最新の状態に保たれ、使用可能になります。これらは、顧客に関連付けられた地域固有の組織に保存されます。

## Adobe Data Connector データセットでグローバル検索を使用する

グローバル検索データセットは、レポート時に自動的に適用されます。Analytics Data Connectorを使用し、Adobeがグローバル参照を提供するディメンションを取り込む場合、このグローバル参照が自動的に適用されます。 イベントデータセットに XDM フィールドが含まれている場合は、それに対してグローバル検索を適用できます。

## 使用可能なグローバル検索フィールド

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

## グローバル検索ディメンションに関する報告

グローバル検索ディメンションについて報告するには、Customer Journey Analytics でデータビューを作成する際にそれらのディメンションを追加する必要があります。

![](assets/global-lookup.png)

これで、Workspace で検索データを確認できます。

![](assets/gl-reporting.png)
