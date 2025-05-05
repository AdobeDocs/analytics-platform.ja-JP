---
title: Customer Journey Analyticsへの Quantum Metric データの追加
description: Quantum Metric を使用してユーザージャーニーと行動のデータ収集を行い、収集したデータからCJAを強化して、より豊富なインサイトを引き出します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Customer Journey Analyticsへの Quantum Metric データの追加

>[!IMPORTANT]
>
>現時点では、Quantum Metric ソースコネクタはまだ使用できません。

CJAを使用すると、QM データ、シーケンシャルデータ分析、リッチ属性、その他の高度なレポートに関するレポート時間制御が可能になります。  QM は、QM ソースコネクタまたは Quantum Metrics Tags 拡張機能を使用して、AEPに送信できます。

## 手順 1:Quantum Metric ソースコネクタの作成

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. [!UICONTROL Experience Platform]/[!UICONTROL Connections]/[!UICONTROL Sources] に移動します。
1. Quantum Metric ソースコネクタを追加し、プロンプトに従って完了します。

詳しくは、[Adobe Experience Platform ソースコネクタ ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home) を参照してください。

## 手順 2:Customer Journey Analyticsでの接続の作成

Quantum Metric データのソースコネクタを作成すると、Adobe Experience Platformにデータセットが自動的に作成されます。 このデータセットをCustomer Journey Analyticsの新規または既存の [ 接続 ](/help/connections/overview.md) に追加します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、必要に応じて **データ管理** から「**[!UICONTROL 接続]**」を選択します。
1. 接続に名前を付け、その接続に Quantum Metric データセットを追加します。
1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>Quantum Metric データは、残りのCustomer Journey Analytics データと同じ接続に追加できますが、そのデータは、2 つのデータセット間で共通の人物 ID がない限り、ステッチできません。 Adobeこの動作が必要な場合は、ソースコネクタの代わりに [ タグ拡張機能 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) を使用することをお勧めします。

## 手順 3:Customer Journey Analyticsでのデータビューの作成

[ データビュー ](/help/data-views/data-views.md) を作成して、ディメンションと指標の設定を行います。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、必要に応じて **データ管理** から **[!UICONTROL データビュー]** を選択します。
1. 目的のデータビューを選択するか、データビューを作成します。
1. 右側のスキーマフィールドリストで目的の Quantum Metric ディメンションと指標を見つけて、中央のディメンションと指標領域にドラッグします。
1. 右側のパネルを使用して、目的のディメンションと指標をそれぞれ設定します。

## 手順 4:Customer Journey Analyticsでのレポートおよび分析の開始

データがCustomer Journey Analyticsで使用できるようになったので、データのレポートを開始できます。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、上部のメニューで **0&rbrace;Workspace&rbrace; を選択します。**
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. 目的の Quantum Metric ディメンションまたは指標をWorkspace キャンバスにドラッグして、データを分析します。
