---
title: Data Mirrorに関する検討事項
description: データウェアハウスネイティブソリューションとCustomer Journey Analytics間でデータを同期する場合は、追加の考慮事項を考慮する必要があります。
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 832
ht-degree: 1%

---

# Experience Platform Data Mirrorに関する検討事項

この記事では、Data Mirror データセットを設定する際に考慮すべき要素について説明します。

## ソーステーブルへの新しい列

CDC対応データミラーデータセットのソーステーブルに新しい列が追加されると、その変更により、既存のすべての行の更新がトリガーされる可能性があります。 これらの更新は、次のようなCDCを通じて変更として処理されます。

* 進行状況の観点からテーブル全体の書き換えのように動作する可能性があります。
* 取り込み量が大幅に増加する可能性があります。これにより、更新が取り込み権限を超える可能性があります。

ソーステーブルの列に推奨される戦略：

* 関連するすべての列が最初に定義されていることを確認します。
* 最初に必要だと思われる列をすべてマッピングします。

新しい列を追加する場合は、遡及的なバックフィルが必要かどうかに応じて、次の2つのオプションがあります。

* 遡及的なバックフィル：

   * 現在のデータセットを削除します。
   * 更新された列でコネクタを再設定します。

  これにより、データがより効率的かつタイムリーにバックフィルされます。

* 遡及的なバックフィルなし：

   * ソーステーブルに列を追加します。
   * ターゲットデータセットスキーマに列を追加します。
   * ソーステーブルからターゲットデータセットへの新しいフィールド（列）を含めるようにマッピングを更新します。

この戦略：

* 後でコストのかかるスキーマの進化（列を追加する際の一括更新）を回避します。
* 列が後で追加または変更されるときよりも、変更量を予測可能に保ちます。
* データウェアハウスが新しい列をすべての行に対する更新として解釈する可能性があるため、外部データベース側の潜在的な計算コストを制限するのに役立ちます。


## Privacy Service

プライバシー要求は、データの構造化の方法に関係ないため、今日は非関係スキーマに対してプライバシー要求が処理されるのと同じ方法で処理する必要があります。

外部リレーショナルスキーマからミラーリングされたデータは、Adobe エコシステムの一部となり、Customer Journey Analytics Audience Publishingを通じてエコシステム全体で共有できます。 プライバシーリクエストを送信すると、Adobe エコシステム全体でIDと関連データが適切に処理されます。

したがって、プライバシー要求はミラーリングされたデータセットに限定するのではなく、外部データベース内のソースデータの更新も含める必要があります。

## 衛生行動

ハイジーンサービスは&#x200B;*プライマリ ID*&#x200B;で動作しますが、ミラー化された外部データベース内のテーブルには、プライマリ IDではなく&#x200B;*プライマリキー*&#x200B;が含まれています。

プライマリ IDとプライマリ キーの違いの結果は、ハイジーン削除をこれらのリレーショナル テーブルに対して直接実行できないことです。 その結果、次のことが必要になります。

* データウェアハウスソリューション内の独自のソーステーブル内のデータを削除し、削除操作がCDC （または手動の変更列）を経由することを確認します。
* ID情報（Customer Journey Analytics ビュー、Real-Time Customer Data Platform データセット、Adobe Journey Optimizer固有のデータセットなど）を使用して、下流のXDM ベースのデータセットに対するハイジーンおよびプライバシーの要求をAdobeに送信します。

プライマリ IDとプライマリ キーの違いは、共有の責任モデルを導入します。

* Adobeは、IDが存在する場合にハイジーンを処理します。
* お客様は、Adobeに送信されるハイジーンリクエストとソースデータベース内の独自のハイジーンプロセスを整合させる責任があります。

## ガバナンスの違い

XDM [&#x200B; スキーマ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition)と[&#x200B; フィールドグループ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#field-group)などの基本概念では、フィールドグループ内の定義された[&#x200B; フィールド &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition#field)が、フィールドグループが使用されるすべてのデータセットにラベルを反映します。 例えば、フィールドグループ `identities`の電子メールフィールド `emailID`は、フィールドグループ `identities`が使用されているすべてのデータセットで同じラベルが付けられます。

リレーショナルスキーマでは、列名は独立しています。 テーブル `customers`の`email`という名前の列は、テーブル `prospects`の`email`という名前の列とは独立しており、異なります。 この動作は、ラベル（DULE使用ラベルやポリシーなど）をミラーデータセットのフィールドに個別に適用する必要があることを意味します。 上記の例に基づいて、`customers` データセットの`email` フィールドと`prospects` データセットの`email` フィールドの両方にラベルを適用する必要があります。

ガバナンスの違いは、次のような影響を与えます。

* 顧客は、より多くの手作業によるガバナンスと設定に取り組む必要があります。
* 明示的なガイダンスが必要な場合があるため、フィールドグループを介した1回限りのラベル付けが適切なガバナンスに十分であると仮定しないでください。

## ステッチ

関係スキーマには、ステッチに関連する次の考慮事項があります。

* グラフベースのステッチングは部分的にサポートされています。 プロファイルまたはグラフに貢献するリレーショナルスキーマを有効にできません。
* フィールドベースの合成は完全にサポートされています。


## システムキーとフィールド

システムキーとフィールドには、次の考慮事項が適用されます。

* プライマリキー、バージョン記述子、およびタイムスタンプ記述子は、リレーショナル XDM スキーマのルートレベルのフィールドである必要があります。 取り込み中に[&#x200B; フィールドマッピング &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema)を使用して、この要件をサポートします。
* [&#x200B; マッピングフェーズ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema)中に、適切なソースフィールドを省略できます。
