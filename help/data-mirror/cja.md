---
title: Customer Journey Analyticsの設定
description: Customer Journey Analytics用Experience Platform Data MirrorのCustomer Journey Analytics接続、データビュー、プロジェクトの設定方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
TQID: https://experienceleague.adobe.com/1LArX1cyRWpEY8O9xMwTcgwc0aUTjMrniFiDXtpkCNY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 2%

---

# Customer Journey Analyticsの設定

{{relational-model-based}}

Customer Journey AnalyticsでExperience Platform Data Mirror機能を使用するには、リレーショナルデータを使用するように、接続、データビュー、ワークスペースプロジェクトを作成または更新する必要があります。

## 接続

接続で、データウェアハウスネイティブソリューションのデータを表すリレーショナルデータセットを追加します。 これらのデータセットには、リレーショナルデータセットのタイプがあります。

データウェアハウスネイティブソリューションからのミラーデータを含むリレーショナルデータセットを追加する場合、そのデータは通常イベントデータです。 データセットの正しい設定を選択していることを確認します。 例えば、正しいデータセットタイプ、IDのフィールド、タイムスタンプのフィールドを選択します。


## データビュー

リレーショナルスキーマのフィールドを、データビューのコンポーネント（指標とディメンション）として定義します。 データミラーフィールドは、**[!UICONTROL イベントデータセット]** フォルダーの&#x200B;**[!UICONTROL アドホックおよびリレーショナルフィールド]** サブフォルダーで使用できます。 [派生フィールド &#x200B;](/help/data-views/derived-fields/derived-fields.md)または[&#x200B; コンポーネント設定](/help/data-views/component-settings/overview.md)などの機能を使用して、リレーショナルフィールドに基づくコンポーネントを変更します。


## Workspace プロジェクト

リレーショナルデータの指標とディメンションを使用するWorkspace プロジェクトを設定します。 データウェアハウスネイティブソリューションのデータに基づくコンポーネント。 設定したデータミラー機能に基づいて更新されます。

>[!MORELIKETHIS]
>
>[Data Mirror クイックスタートガイド：関係データのミラーと使用](relational.md)
>
