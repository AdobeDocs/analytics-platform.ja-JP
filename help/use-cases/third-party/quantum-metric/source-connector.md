---
title: Customer Journey Analyticsへの量子指標データの追加
description: 量子指標を使用してユーザーの行動や行動を収集し、収集したデータからCJAを実行して、より詳細なインサイトを引き出します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
TQID: https://experienceleague.adobe.com/LLrYpPlbagFAIeuD9TMgA3E8lrcUrMxMSWLC-8SiiIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 4%

---

# Customer Journey Analyticsへの量子指標データの追加

>[!IMPORTANT]
>
>Quantum Metric ソースコネクタは、現時点ではまだ利用できません。

CJAなら、QM データ、シーケンシャルデータ分析、リッチアトリビューションなどの高度なレポート機能をレポート時にリアルタイムで利用できます。  QMは、QM ソースコネクタまたはQuantum Metrics Tags拡張機能を使用してAEPに送信できます。

## 手順1：量子指標ソースコネクタの作成

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. [!UICONTROL Experience Platform] > [!UICONTROL Connections] > [!UICONTROL Sources]に移動します。
1. Quantum Metric ソースコネクタを追加し、プロンプトに従って完了します。

詳しくは、[Adobe Experience Platform ソースコネクタ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/home)を参照してください。

## 手順2:Customer Journey Analyticsでのコネクションの作成

Quantum Metric Dataのソースコネクタを作成すると、Adobe Experience Platformでデータセットが自動的に作成されます。 このデータセットを、Customer Journey Analyticsの新規または既存の[接続](/help/connections/overview.md)に追加します。

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. Customer Journey Analyticsに移動し、上部メニューの&#x200B;**[!UICONTROL Data management]**&#x200B;から&#x200B;**[!UICONTROL Connections]**&#x200B;を選択します（オプション）。
1. 接続に名前を付け、量子指標データセットを接続に追加します。
1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>量子指標データを、他のCustomer Journey Analytics データと同じ接続に追加することはできますが、2つのデータセット間で共通の個人IDがなければ、そのデータを結合することはできません。 このビヘイビアーが望ましい場合は、ソースコネクタの代わりに[&#x200B; タグ拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/catalog/analytics/quantum-metric)を使用することをお勧めします。

## 手順3:Customer Journey Analyticsでのデータビューの作成

ディメンションと指標の設定を行うには、[&#x200B; データビュー](/help/data-views/data-views.md)を作成します。

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. Customer Journey Analyticsに移動し、上部メニューの&#x200B;**[!UICONTROL Data management]**&#x200B;から&#x200B;**[!UICONTROL Data views]**&#x200B;を選択します（オプション）。
1. 目的のデータビューを選択するか、データビューを作成します。
1. 右側のスキーマフィールドリストで、目的の量子指標のディメンションと指標を見つけ、中央のディメンションと指標エリアにドラッグします。
1. 適切なペインを使用して、目的の各ディメンションと指標を設定します。

## ステップ 4:Customer Journey Analyticsでのレポートと分析の開始

データがCustomer Journey Analyticsで使用できるようになったので、データのレポートを開始できます。

1. [experience.adobe.com](https://experience.adobe.com)にログインします。
1. Customer Journey Analyticsに移動し、上部メニューの&#x200B;**[!UICONTROL Workspace]**&#x200B;を選択します。
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. 任意の量子指標ディメンションまたは指標をWorkspace キャンバスにドラッグして、データを分析します。
