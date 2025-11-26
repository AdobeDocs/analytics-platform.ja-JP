---
title: Customer Journey Analyticsの設定
description: Customer Journey Analytics用Experience Platform Data MirrorのCustomer Journey Analytics接続、データビュー、プロジェクトを設定する方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b2a13524760f9d466696534bc8b9691f3b4dfb8a
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---

# Customer Journey Analyticsの設定

{{release-limited-testing}}

{{relational-model-based}}

Customer Journey AnalyticsでExperience Platform Data Mirror機能を使用するには、リレーショナルデータを使用する接続、データビュー、ワークスペースプロジェクトを作成または更新する必要があります。

## 接続

接続で、Data Warehouse ネイティブソリューションのデータを表すリレーショナルデータセットを追加します。 これらのデータセットには、リレーショナルデータセットタイプがあります。

データウェアハウスネイティブソリューションのミラーデータを含むリレーショナルデータセットを追加する場合、そのデータは通常、イベントデータです。 データセットに対して正しい設定を選択していることを確認します。 例えば、正しいデータセットタイプ、ID のフィールド、タイムスタンプのフィールドを選択します。


## データビュー

リレーショナルスキーマのフィールドを、データビューのコンポーネント（指標とディメンション）として定義します。 データミラーフィールドは、**[!UICONTROL イベントデータセット]** フォルダーの **[!UICONTROL アドホックおよびリレーショナルフィールド]** サブフォルダーで使用できます。 [ 派生フィールド ](/help/data-views/derived-fields/derived-fields.md) または [ コンポーネント設定 ](/help/data-views/component-settings/overview.md) などの機能を使用して、リレーショナルフィールドに基づくコンポーネントを変更します。


## ワークスペースプロジェクト

リレーショナルデータの指標とディメンションを使用するWorkspace プロジェクトを設定します。 最終的にデータウェアハウスネイティブソリューションのデータに基づくコンポーネント。 およびは、設定したデータミラー機能に基づいて更新されます。

>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：relationald データのミラーリングと使用 ](relational.md)
>
