---
title: Customer Journey Analytics BI 拡張機能
description: BI拡張機能を使用して、独自のBI ツールまたはデータレイクにデジタルデータを取り込み、追加のデータセットで使用する方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 669a1305-3e37-4ca2-8178-a89a27958e5d
autotag-review: '2026-05-19T08:00:39.048Z'
TQID: 'https://experienceleague.adobe.com/BgO7hQlR2J3o-nD38ZIg2ILUTwDKGfSXu-i-bEo5SJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 25%
---
# BI 拡張機能

この記事では、[!DNL Customer Journey Analytics BI extension]を使用して次の[ データ書き出しの使用例](overview.md)を実装する方法について説明します。

* データレイク、Data Warehouse、BI ツール

## はじめに

[!DNL Customer Journey Analytics BI extension]を使用してデータをエクスポートすると、Customer Journey Analytics データビューからデータをエクスポートできます。

![BI拡張機能](../assets/bi-extension.png)

## 詳細情報

[!DNL Customer Journey Analytics BI extension] を使用すると、Customer Journey Analytics で定義した[データビュー](/help/data-views/data-views.md)への SQL アクセスが可能になります。 データエンジニアやアナリストは、Power BIやTableauなどのBI ツール（BI ツールとも呼ばれます）に精通しています。 Customer Journey Analytics ユーザーが Analysis Workspace プロジェクトを作成する際に使用しているものと同じデータビューに基づいて、レポートおよびダッシュボードを作成できるようになりました。

BI拡張機能は、生のイベントレベルの行ではなく、集計データを返します。 デフォルトでは、各クエリは30日間の日付範囲に対して50行を返しますが、行制限を最大50,000行に、日付範囲を独自のカスタム範囲に上書きできます。 詳しくは、[ デフォルトと制限事項](../../data-views/bi-extension.md#defaults-and-limitations)を参照してください。

詳しくは、[BI拡張機能](../../data-views/bi-extension.md)の詳細なドキュメントを参照してください。
