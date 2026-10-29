---
description: 管理者がデータビューまたはデータディクショナリを使用してコンポーネントに説明を追加する方法について説明します。
title: コンポーネントの説明の追加
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# コンポーネントの説明の追加

説明は、Analysis Workspaceでプロジェクトを構築する際やレポートを表示する際に、様々なコンポーネントを使用する方法をユーザーが理解するのに役立ちます。

Customer Journey Analytics管理者は、データビュー内またはデータディクショナリを使用して、コンポーネント（ディメンション、指標、セグメント、日付範囲）に説明を追加できます。

## データビュー

データビューに追加したコンポーネントに説明を追加できます。 [&#x200B; コンポーネント設定](/help/data-views/component-settings/overview.md)を参照してください。

## データ辞書

Analysis Workspaceのデータディクショナリは、ユーザーと管理者の両方がCustomer Journey Analytics環境のコンポーネントを追跡し、より深く理解するのに役立ちます。 データディクショナリを使用すると、管理者はAnalysis Workspace内で直接コンポーネントの説明を追加できます。

データディクショナリでのコンポーネント説明の編集について詳しくは、[&#x200B; データディクショナリでのコンポーネントエントリの編集](/help/components/data-dictionary/edit-entries-data-dictionary.md)を参照してください。

データディクショナリの一般的な情報については、[&#x200B; データディクショナリの概要](/help/components/data-dictionary/data-dictionary-overview.md)を参照してください。

>[!MORELIKETHIS]
>
>[&#x200B; データビューコンポーネント設定](/help/data-views/component-settings/overview.md)
>[データ ディクショナリ コンポーネント エントリ &#x200B;](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## 説明の自動生成

{{release-limited-testing-section}}

Customer Journey Analyticsでは、各説明を手作業で記述する代わりに、生成AIを使用して説明を記述できます。 1つのコンポーネントの説明を生成したり、同時に多くのコンポーネントの説明を生成したりできます。

生成された説明：

* 3つ以下の文章です。
* AI **を使用してAdobeによって生成されたテキスト**&#x200B;で終わると、説明が生成されたことがユーザーに分かります。
* 生成後に編集することもできます。

### 前提条件

説明を生成する前に、生成AIに関する特定の法的条件に同意する必要があります。 組織がこれらの条件に同意していない場合、説明を生成するオプションはグレー表示されます。 オプションの横にある情報アイコン ![情報](/help/assets/icons/InfoOutline.svg)を選択して、この機能を有効にする方法を確認するか、組織の管理者またはAdobe アカウントチームにお問い合わせください。

### 説明の生成方法

生成される説明は、コンポーネントの定義と、コンポーネントがデータビューでどのように使用されるかについての追加のコンテキストに基づいています。例えば、次のようなものがあります。

* ディメンションの上位アイテム
* コンポーネントとともに頻繁に使用されるコンポーネント

計算指標またはセグメントが別のセグメントを参照する場合、生成された説明は、参照されるセグメントの定義を説明します。

### 様々な場所から説明を生成する

Customer Journey Analyticsの次の領域で説明を生成できます。 一部の場所では、複数のコンポーネントの説明を生成できますが、他の場所では生成できません。

場所を選択して、そこに説明を生成する方法を学習します。

| 場所 | サポートされているコンポーネント | 単一コンポーネント | 複数のコンポーネント |
| --- | --- | --- | --- |
| [&#x200B; データディクショナリ &#x200B;](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>ディメンション</li><li>指標</li><li>計算指標</li><li>セグメント</li><li>日付範囲</li></ul> | はい | はい |
| [データビュー](/help/data-views/component-settings/overview.md) | <ul><li>ディメンション</li><li>指標</li><li>派生フィールド</li><li>共有指標とディメンション （詳細については、[共有指標とディメンション &#x200B;](#generate-descriptions-for-shared-metrics-and-dimensions)を参照してください）。</li></ul> | はい | はい |
| [セグメントビルダー](/help/components/segments/seg-builder.md) | セグメント | はい | いいえ |
| [&#x200B; セグメントマネージャー](/help/components/segments/seg-manage.md#action-bar) | セグメント | いいえ | はい |
| [計算指標ビルダー](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | 計算指標 | はい | いいえ |
| [計算指標マネージャー](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | 計算指標 | いいえ | はい |
| [日付範囲ビルダー](/help/components/date-ranges/create.md#date-range-builder) | 日付範囲 | はい | いいえ |
| [日付範囲マネージャー](/help/components/date-ranges/manage.md#action-bar) | 日付範囲 | いいえ | はい |

{style="table-layout:auto"}

### 共有指標とディメンションの説明を生成します

[さまざまな場所から説明を生成する](#generate-descriptions-from-various-locations)の表に示すように、共有された指標とディメンションの説明は、データビュー内からのみ生成できます。 [Shared Metrics &amp; Dimensions マネージャー](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager)から説明を生成することはできません。

データビュー内の共有指標またはディメンションの説明を生成する場合は、次の点を考慮してください。

* この説明は、コンポーネントが共有されているすべてのデータビューに適用され、そのコンポーネントの既存の説明は、他のすべてのデータビューおよび共有指標とディメンションマネージャーで置き換えられます。

* 説明は、それを生成するデータビューのコンテキスト（データビューの最上位ディメンション項目など）に基づいています。


