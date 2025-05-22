---
title: コンテンツ分析データ収集
description: コンテンツ分析でデータを収集する方法の概要
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 63c6a5d6148c1562b7f6ac8e4a1cac5919e2dd2e
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 80%

---

# コンテンツ分析データ収集

この記事では、コンテンツ分析でデータを収集する方法について詳しく説明します。

## 定義

この記事のコンテキストでは、次の定義を使用します。

* **エクスペリエンス**：エクスペリエンスは、web ページ全体のテキストコンテンツとして定義されます。データ収集の場合、コンテンツ分析は、ページ URL に基づいたエクスペリエンス ID を記録します。その後、ページ上のテキストが取得サービスを通じて取得されます。
* **エクスペリエンス ID**：関連する URL（ベース URL と、ページ上のコンテンツを制御するパラメーター）と[エクスペリエンスバージョン](manual.md#versioning)の一意の組み合わせ。
   * [設定](configuration.md)の一部として、特定の完全な URL に関連するパラメーターを指定します。
   * 使用する[バージョン識別子](manual.md#versioning)を定義して、エクスペリエンスに対する変更を適切に収集します。
* **アセット**：画像。コンテンツ分析では、アセット URL を記録します。
* **アセット ID**：アセットの URL。
* **関連 URL**：ベース URL と、ページ上のコンテンツを駆動するパラメーター。


## 機能

Content Analyticsでコンテンツイベントデータを収集するには、Experience Platform Edge Network Web SDKが必要です。 このイベントデータ収集は、Experience Platform Edge Network（Web SDK、Server API）や Analytics ソースコネクタ（例えば、AppMeasurementを使用）などのメカニズムを通じて、行動イベントデータの（既存の）データ収集と組み合わされます。

コンテンツ分析ライブラリでは、次の場合にデータを収集します。

* コンテンツ分析は、ページに読み込まれるタグライブラリに含まれます。
* ページ URL は、含まれるタグライブラリの一部である[コンテンツ分析拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}で設定されます。


## コンテンツ分析イベント

コンテンツ分析イベントは、以下で構成されます。

* 標準フィールド
   * タイムスタンプ
   * ID
* エクスペリエンスビュー数（存在する場合と設定されている場合）
* エクスペリエンスクリック数（存在する場合と設定されている場合）
* アセットビュー数（存在する場合と設定されている場合）
* アセットクリック数（存在する場合と設定されている場合）

コンテンツ分析イベントは、次のシーケンスとして収集されます。

1. [記録されたビューまたはクリック](#recorded-view-or-click)。
1. [Content Analytics イベントを送信するトリガー](#trigger-to-send-a-content-analytics-event)。

コンテンツ分析では、ビューまたはクリックを個別に収集し、そのビューまたはクリックの直後のイベントを収集する代わりに、シーケンスを反映するのにこの方法でデータを収集します。また、コンテンツ分析データを収集するこの方法では、収集されるデータの量も削減されます。

### 記録されたビューまたはクリック

アセットビューは、次の場合に記録されます。

* コンテンツ分析拡張機能の設定ごとにアセットが除外されていない。
* アセットの 75％が表示される。
* そのアセットがこのページにまだ記録されていない。

アセットクリックは、次の場合に記録されます。

* アセットが表示される。
* コンテンツ分析拡張機能の設定ごとにアセットが除外されていない。
* リンクであるアセットを直接クリックすると、別のページに移動する。

エクスペリエンスビューは、次の場合に記録されます。

* エクスペリエンスが、コンテンツ分析設定で有効になっている。

エクスペリエンスクリックは、次の場合に記録されます。

* エクスペリエンスが有効になっているページ上のリンクでクリックが発生する。


### Content Analytics イベントを送信するためのトリガー

Content Analyticsは、ページからの呼び出し数を減らすために情報を収集しますが、その情報をすぐには送信しません。 コンテンツインタラクション情報が収集され、その情報を含むイベントが、次のいずれかのトリガーが発生した場合にのみ送信されます。

* Web SDKまたは AppMeasurements がイベントを送信します。 このイベントのタイムスタンプは
* 表示が非表示に変更される。例：
   * ページのアンロード
   * タブを切り替え
   * ブラウザーを最小化
   * ブラウザーを閉じる
   * 画面をロック
* URL が変更され、関連する URL が変更される。
* 記録され、送信準備が整ったアセットビュー数が 32 を超えている。


## スキーマ

コンテンツ分析データは、特定のコンテンツ分析スキーマに基づいて、Experience Platform のデータセットに収集されます。参照スキーマは、次の記事で公開されています。

* [デジタルアセットスキーマ](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [デジタルエクスペリエンススキーマ](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [エクスペリエンスイベントコンテンツスキーマ](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
