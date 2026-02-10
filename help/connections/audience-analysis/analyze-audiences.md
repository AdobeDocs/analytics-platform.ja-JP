---
title: Customer Journey AnalyticsでのExperience Platform オーディエンスの分析
description: Customer Journey AnalyticsでExperience Platform オーディエンスを分析する方法を説明します。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 095cae34-1337-464a-9682-3c899295c0a8
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Customer Journey AnalyticsでのExperience Platform オーディエンスの分析 {#analyze-audiences-RTCDP}

[ オーディエンス分析設定を作成 ](/help/connections/audience-analysis/audience-analysis-configure.md) すると、オーディエンスデータは、作成するように設定したデータビューで新しいディメンションとして使用できるようになります。 オーディエンス分析ディメンションが追加されたデータビューにアクセスできる場合は、Analysis Workspaceの任意の場所で新しいオーディエンスディメンションを使用できます。

## オーディエンスの概要テンプレートの使用

オーディエンスの概要テンプレートは、Customer Journey Analyticsで使用できます。

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

オーディエンスの概要テンプレートへのアクセス方法について詳しくは、[ テンプレートの使用 ](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) の [ テンプレートへのアクセスと実行 ](/help/analysis-workspace/templates/use-templates.md) を参照してください。

オーディエンスの概要テンプレートには、次のパネルが含まれています。

## 使用状況の概要パネル

選択したデータビューに関連付けられている使用イベントを含むすべてのオーディエンスのデータを表示します。 オーディエンスメンバーシップデータは、Experience Platformから毎日更新されます。 昨日のデータは常に表示されるので、パネルの日付範囲を変更すると、データが不正確になります。

このパネルの表を使用すると、オーディエンスの行動をより深く理解できます。 選択したデータビューからオーディエンスの説明ディメンションをドラッグし、分類として追加します。 または、他のインタラクションディメンション（ページ、アクションなど）を分類として使用します。

## 上位のオーディエンスの接触チャネル パネル

RTCDPやCustomer Journey Analyticsなど、オーディエンスが作成された場所を示します。

このパネルの表を使用すると、オーディエンスの接触チャネルが他の要因にどのように影響するかを把握しやすくなります。 選択したデータビューからオーディエンス名ディメンションをドラッグし、分類として追加します。 または、他のインタラクションディメンション（ページ、アクションなど）を分類として使用します。

## オーディエンスの重複パネル

選択したデータビューに関連付けられている使用イベントを含むすべてのオーディエンスのデータを表示します。 昨日のデータは常に表示されるので、パネルの日付範囲を変更すると、データが不正確になります。

このパネルのテーブルで最大 3 つのオーディエンスを選択して、対応するベン図でそれらが重なるのを確認します。

## オーディエンスの使用パネルを終了しました

選択したデータビューに関連付けられている使用イベントを持つ、退出したすべてのオーディエンスのデータを表示します。 昨日のデータは常に表示されるので、パネルの日付範囲を変更すると、データが不正確になります。 「退出したオーディエンス」は、使用イベントを持つユーザーが昨日退出したオーディエンスです。

このパネルの表を使用すると、オーディエンスの行動をより深く理解できます。 選択したデータビューから離脱オーディエンスの説明ディメンションをドラッグし、分類として追加します。 または、他のインタラクションディメンションまたは指標（ページ、アクションなど）を分類として使用します。

## 上位の除外されたオーディエンスの接触チャネル パネル

RTCDPやCustomer Journey Analyticsなど、離脱した各オーディエンスが最初に作成された場所を示します。

このパネルの表を使用すると、オーディエンスの接触チャネルが他の要因にどのように影響するかを把握しやすくなります。 選択したデータビューから離脱オーディエンス名ディメンションをドラッグし、分類として追加します。 または、他のインタラクションディメンションまたは指標（ページ、アクションなど）を分類として使用します。
