---
title: Customer Journey Analytics テーブルの書き出し
description: テーブルの書き出し機能を使用してデータを検証する方法、またはAI/マシンラーニングにデータを使用する方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: ee004948-3025-434b-a90b-8aa185800820
autotag-review: '2026-05-19T09:39:35.989Z'
TQID: 'https://experienceleague.adobe.com/5lP3PKpCpxkeyH34327gieZ48KFkEai4DF2SC0H4E2U'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 4%
---
# フルテーブルの書き出し

この記事では、[!DNL Export full table]機能を使用して、次の[&#x200B; データ書き出しの使用例](overview.md)を実装する方法について説明します。

* データの検証
* AI/マシンラーニングへの対応

## はじめに

[!DNL Customer Journey Analytics Full Table Export]を使用してデータを書き出すと、Customer Journey Analytics Analysis Workspaceのフリーフォームテーブルからデータを書き出すことができます。

![BI拡張機能](../assets/export-full-table.png)

## 詳細情報

Analysis Workspaceで作成したフリーフォームテーブルの完全なコンテンツを、指定されたクラウドの宛先に直接書き出すには、テーブルの書き出し機能を使用します。

テーブルの書き出しは、レポートごとに最大10個のディメンションと10個の指標をサポートし、計算指標とセグメント化が含まれます。 ライセンス層に応じて、書き出しごとに300万行、3000万行、1億5000万行、または3億行を書き出すことができ、他の書き出し方法の50,000行の制限を超えます。 サポートされている宛先には、Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflakeなどがあります。 詳しくは、[&#x200B; テーブルの書き出しの利点](/help/analysis-workspace/export/export-cloud.md#advantages)を参照してください。

詳しくは、[Customer Journey Analytics レポートのクラウドへの書き出し](/help/analysis-workspace/export/export-cloud.md)に関する詳細なドキュメントを参照してください。
