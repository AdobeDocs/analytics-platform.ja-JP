---
title: Content Analyticsのデータ収集
description: Content Analyticsでのデータ収集方法の概要です
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 02d24416bd1f56417005dfa1b693964073fb8a59
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 1%

---

# Content Analyticsのデータ収集

{{release-limited-testing}}

この記事では、コンテンツ分析でデータを収集する方法について詳しく説明します


## 定義

この記事のコンテキストでは、次の定義を使用します。

* **エクスペリエンス**：エクスペリエンスは、web ページ全体のテキストコンテンツとして定義されます。 データ収集の場合、Content Analyticsは、ページ URL に基づいたエクスペリエンス ID を記録します。 その後、ページ上のテキストが取得サービスを介して取得されます。
* **エクスペリエンス ID**：関連する URL （ベース URL に加えて、ページ上でコンテンツを駆動するパラメーター）と [ エクスペリエンスバージョン ](manual.md#versioning) の一意の組み合わせ。
   * [ 設定 ](configuration.md) の一部として、特定の完全な URL に関連するパラメーターを指定します。
   * 使用する [ バージョン識別子 ](manual.md#versioning) を定義できます。
* **アセット**：画像。 Content Analyticsはアセット URL を記録します。
* **アセット ID**：アセットの URL です。
* **関連する URL**：ベース URL と、ページ上でコンテンツを駆動するパラメーター。


## 機能

Content Analytics ライブラリは、次の場合にデータを収集します。

* Content Analyticsは、ページに読み込まれるタグライブラリに含まれています。
* ページ URL は、付属のタグライブラリの一部である ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}0}Content Analytics拡張機能 } で設定されます。[


## Content Analytics イベント

Content Analytics イベントは、次の要素で構成されます。

* 標準フィールド
   * タイムスタンプ
   * ID
* エクスペリエンスビュー（存在する場合は、設定されている場合は）
* エクスペリエンスクリック数（存在する場合、および設定されている場合）
* アセット表示（存在する場合、および設定されている場合）
* アセットクリック数（存在する場合、および設定されている場合）


Content Analytics イベントは、次のシーケンスとして収集されます。

1. [ 記録ビューまたはクリック ](#recorded-view-or-click)。
1. [ 通常または特定の（行動）イベント ](#regular-or-specific-behaviorial-event)。

Content Analyticsでは、ビューやクリックを収集するのではなく、ビューやクリックの直後のイベントを個別に収集して、そのシーケンスを反映させるためにデータを収集します。 この方法でコンテンツ分析データを収集すると、収集されるデータの量も削減されます。

### 記録されたビューまたはクリック

アセット表示は、次の場合に記録されます。

* アセットは、Content Analytics拡張機能の設定に従って除外されていません。
* アセットは 75% 表示されます。
* そのアセットは、このページにまだ記録されていません。

アセットのクリックは、次の場合に記録されます。

* アセットが表示されました。
* アセットは、Content Analytics拡張機能の設定に従って除外されていません。
* 別のページに誘導されるアセット（リンク）を直接クリック。

エクスペリエンスの表示は、次の場合に記録されます。

* エクスペリエンスは、Content Analytics設定で有効になっています。

エクスペリエンスのクリックは、次の場合に記録されます。

* エクスペリエンスが有効になっているページ上のリンクで、クリックが発生します。


### 通常の、または特定の（行動）イベント

Content Analyticsのコンテキストで通常または特定の（行動）イベントを発生させるトリガーは次のとおりです。

* Web SDKまたは AppMeasurements がイベントを送信します。
* 表示が非表示に変わります。次に例を示します。
   * ページのアンロード
   * 「切り替え」タブ
   * ブラウザーを最小化
   * ブラウザーを閉じる
   * ロック画面
* URL が変更されるので、関連する URL が変更されます。
* 記録され、送信準備が整ったアセットの表示数が 32 を超えています。


## スキーマ

Content Analytics データは、特定のContent Analytics スキーマに基づいて、Experience Platformのデータセットで収集されます。 参照スキーマは、次の場所で公開されています。

* [ デジタルアセットスキーマ ](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [ デジタルエクスペリエンススキーマ ](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [ エクスペリエンスイベントコンテンツスキーマ ](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
