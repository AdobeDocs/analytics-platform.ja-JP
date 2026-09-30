---
title: Customer Journey Analytics レポート API
description: Reporting APIを使用してCustomer Journey Analytics データをプログラムで取得する方法を説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%
---

# レポート API

この記事では、[!DNL Customer Journey Analytics Reporting API]を使用して次の[&#x200B; データ書き出しの使用例](overview.md)を実装する方法について説明します。

- カスタムアプリケーション統合

## はじめに

[!DNL Customer Journey Analytics Reporting API]を使用すると、Analysis Workspaceで利用可能な処理済みのディメンションと指標をプログラムで取得できます。 [!DNL Reporting API]を使用して、カスタムアプリケーションを強化したり、内部ツールにレポートを埋め込んだり、手動エクスポートなしでCustomer Journey Analytics データを自動的に取得したりします。

## 詳細情報

[!DNL Reporting API]は、[!DNL Adobe Analytics] [!DNL Reporting API]と同じリクエストおよび応答の形式を使用していますが、異なるエンドポイントを使用しています。 [!DNL Adobe Analytics]からレポート統合を移行する場合は、[&#x200B; クイックスタートガイド &#x200B;](/help/getting-started/cja-getting-started.md)の移行ワークフローを参照して詳細を確認してください。

認証、使用可能なエンドポイント、および現在のリクエスト制限については、[Customer Journey Analytics API ドキュメント &#x200B;](https://developer.adobe.com/cja-apis/docs/)を参照してください。
