---
title: Analyze Consent Policy Data in Customer Journey Analytics
description: Analysis Workspaceで同意ポリシーのディメンション、指標、テンプレートを使用して、訪問者の同意ポリシーメンバーシップをレポートする方法について説明します。
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 2%

---

# 同意ポリシーデータの分析

Experience Platform プロファイルデータセットからCustomer Journey Analytics接続に同意ポリシーデータを取り込むことができます。

[同意レポートとフィルタリング設定](/help/connections/consent-reporting-filtering/consent-configure.md)を作成すると、同意ポリシーデータは、設定済みの接続のデータビューで新しいコンポーネントとして使用できるようになります。 これらのコンポーネントは、データビューにアクセスできる場合は、Analysis Workspace内の任意の場所で使用できます。

## 同意ポリシーコンポーネント

同意レポートは、次のコンポーネントをデータビューに追加します。 これらのコンポーネントは、プロファイルデータセットの`consentPoliciesIDMap` フィールドから読み取られ、ポリシー名と説明は同意ポリシー参照データセットから取得されます。

### ディメンション

| ディメンション | 説明 |
|---------|----------|
| **[!UICONTROL 同意ポリシーID]** | 訪問者が一致する同意ポリシーの識別子。 |
| **[!UICONTROL ポリシー名]** | 同意ポリシー参照データセットからの同意ポリシーのわかりやすい名前。 |
| **[!UICONTROL ポリシーの説明]** | 同意ポリシー検索データセットからの同意ポリシーの説明。 |

### 指標

| 指標 | 説明 |
|---------|----------|
| **[!UICONTROL 同意を得た訪問者]** | 同意ポリシーに一致する訪問者の数。 |
| **[!UICONTROL 同意を得たイベント]** | 同意ポリシーに一致する訪問者に関連付けられたイベントの数。 |
| **[!UICONTROL 一意の同意ポリシー]** | レポートウィンドウで表される個別の同意ポリシーの数。 |

### 派生フィールド

派生フィールドは、同意ポリシーIDを抽出するために`consentPoliciesIDMap` フィールドを参照します。 この派生フィールドを、追加の同意ベースのディメンションのベースとして使用できます。 派生フィールドについて詳しくは、[派生フィールド &#x200B;](/help/data-views/derived-fields/derived-fields.md)を参照してください。

## Analysis Workspaceの同意ポリシーコンポーネントの使用

同意ポリシーメンバーシップについて報告するには：

1. Analysis Workspaceで、同意レポート用に設定されたデータビューを使用するプロジェクトを開きます。

1. コンポーネントパネルから、**[!UICONTROL ポリシー名]**&#x200B;などの同意ポリシーディメンションをフリーフォームテーブルにドラッグします。

1. 同意を持つ&#x200B;**[!UICONTROL 訪問者]**&#x200B;などの同意指標をテーブルに追加します。

1. ページやチャネルなどのほかのディメンションごとに結果を分類し、同意を得た訪問者が行動する仕組みを把握できます。

## 同意ポリシー分析テンプレートの使用

同意レポート用にデータビューが設定されている場合、Customer Journey Analyticsでは、Analysis Workspaceで同意ポリシー分析テンプレートが自動的に使用できるようになります。 このテンプレートは、訪問者の同意ポリシーメンバーシップに関するレポートの出発点を提供します。

テンプレートへのアクセス方法について詳しくは、[&#x200B; テンプレートへのアクセスと実行](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)を参照してください。
