---
title: Customer Journey Analyticsの設定
description: Customer Journey Analytics用Experience Platform Data MirrorのCustomer Journey Analytics接続、データビュー、プロジェクトを設定する方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="ベータ版"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---

# Customer Journey Analyticsの設定

{{release-limited-testing}}

Customer Journey AnalyticsのExperience Platform Data Mirror機能を使用するには、接続、データビュー、ワークスペースプロジェクトを作成または更新して、モデルベースのデータを使用できるようにする必要があります。

## 接続

接続で、Data Warehouse ネイティブソリューションのデータを表すモデルベースのデータセットを追加します。 これらのデータセットには、モデルデータセットタイプがあります。

Data Warehouse ネイティブソリューションのミラーデータを含んだモデルベースのデータセットを追加した場合、そのデータは通常、イベントデータです。 データセットに対して正しい設定を選択していることを確認します。 例えば、正しいデータセットタイプ、ID のフィールド、タイムスタンプのフィールドを選択します。


## データビュー

データビューで、モデルベースのスキーマのフィールドをコンポーネント（指標とディメンション）として定義します。 データがミラーしたフィールドは、**[!UICONTROL イベントデータセット]** フォルダーの **[!UICONTROL アドホックおよびモデルベースのフィールド]** サブフォルダーで使用できます。 [&#x200B; 派生フィールド &#x200B;](/help/data-views/derived-fields/derived-fields.md) または [&#x200B; コンポーネント設定 &#x200B;](/help/data-views/component-settings/overview.md) などの機能を使用して、モデルベースのフィールドに基づくコンポーネントを変更します。


## ワークスペースプロジェクト

モデルベースのデータの指標とディメンションを使用するWorkspace プロジェクトを設定します。 最終的にデータウェアハウスネイティブソリューションのデータに基づくコンポーネント。 およびは、設定したデータミラー機能に基づいて更新されます。

>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：モデルベースのデータをミラーリングして使用する &#x200B;](model-based.md)
>
