---
title: Customer Journey AnalyticsでのExperience Platform オーディエンスの分析
description: Customer Journey AnalyticsでExperience Platformのオーディエンスを分析する方法について説明します。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 095cae34-1337-464a-9682-3c899295c0a8
autotag-review: '2026-05-19T10:44:54.802Z'
TQID: 'https://experienceleague.adobe.com/ljj9CIUW58m27w8Mo9HlRJ0kgYXGIgqwuarPR2wNUjw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 0%

---

# Customer Journey AnalyticsでのExperience Platform オーディエンスの分析 {#analyze-audiences-RTCDP}

オーディエンス分析設定[を作成すると、作成するように設定したデータビューで、新しいディメンションとしてオーディエンスデータが使用できるようになります](/help/connections/audience-analysis/audience-analysis-configure.md)。 オーディエンス分析ディメンションが追加されたデータビューにアクセスできる場合は、Analysis Workspaceの任意の場所で新しいオーディエンスディメンションを使用できます。

## オーディエンスの概要テンプレートの使用

オーディエンスの概要テンプレートは、Customer Journey Analyticsで利用できます。

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

オーディエンス概要テンプレートへのアクセス方法について詳しくは、[ テンプレートを使用](/help/analysis-workspace/templates/use-templates.md)の「[ テンプレートにアクセスして実行](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)」を参照してください。

オーディエンスの概要テンプレートには、次のパネルが含まれています。

## 使用状況の概要パネル

選択したデータビューに関連付けられている使用状況イベントを持つすべてのオーディエンスのデータを表示します。 オーディエンスのメンバーシップデータは、Experience Platformから毎日更新されます。 データは常に昨日に表示されるため、パネルの日付範囲を変更すると、データが不正確になります。

オーディエンスの行動をより深く理解するには、このパネルの表を使用します。 選択したデータビューから「オーディエンスの説明」ディメンションをドラッグし、分類として追加します。 または、その他のインタラクションディメンション（ページ、アクションなど）を分類として使用します。

## 最上位オーディエンスの生成元パネル

RTCDPやCustomer Journey Analyticsなど、オーディエンスがどこで作成されたかを示します。

このパネルの表を使用すると、オーディエンスの出所が他の要因にどのように影響するのかをより詳細に把握できます。 選択したデータビューからオーディエンス名ディメンションをドラッグし、分類として追加します。 または、その他のインタラクションディメンション（ページ、アクションなど）を分類として使用します。

## オーディエンス重複パネル

選択したデータビューに関連付けられている使用状況イベントを持つすべてのオーディエンスのデータを表示します。 データは常に昨日に表示されるため、パネルの日付範囲を変更すると、データが不正確になります。

このパネルのテーブルで最大3つのオーディエンスを選択して、対応するベン図でどのように重なるかを確認します。

## オーディエンス使用パネルを終了しました

選択したデータビューに関連付けられている使用状況イベントを含む、既存のすべてのオーディエンスのデータを表示します。 データは常に昨日に表示されるため、パネルの日付範囲を変更すると、データが不正確になります。 「離脱したオーディエンス」は、使用状況イベントを持つユーザーが昨日離脱したオーディエンスです。

オーディエンスの行動をより深く理解するには、このパネルの表を使用します。 選択したデータビューから「離脱したオーディエンスの説明」ディメンションをドラッグし、分類として追加します。 または、その他のインタラクションディメンションや指標（ページ、アクションなど）を分類として使用します。

## 一番上の離脱したオーディエンスの生成元パネル

RTCDPやCustomer Journey Analyticsなど、離脱した各オーディエンスが最初に作成された場所を示します。

このパネルの表を使用すると、オーディエンスの出所が他の要因にどのように影響するのかをより詳細に把握できます。 選択したデータビューから「離脱したオーディエンス名」ディメンションをドラッグし、分類として追加します。 または、その他のインタラクションディメンションや指標（ページ、アクションなど）を分類として使用します。
