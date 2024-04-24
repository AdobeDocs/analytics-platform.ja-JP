---
title: Customer Journey Analyticsへの移行時にレポート API の使用状況を移植
description: API の使用状況をAdobe AnalyticsからCustomer Journey Analyticsに移植する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# 手順 7:Customer Journey Analyticsへの移行時にレポート API の使用状況を移植する

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている手順 7 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行パスを選択](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択した移行パスによって異なります。 |
| **手順 4: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | Customer Journey Analyticsプロセスのこの時点では、移行に使用する準備が整う前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからの移行と、新しいCustomer Journey Analytics実装に当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。

Customer Journey Analyticsレポート API は同じフォーマットですが、異なるサブドメインを使用しています。

Adobe AnalyticsとCustomer Journey Analyticsのエンドポイントガイドを参照してください。

ほとんどの API 呼び出しは、Adobe AnalyticsからCustomer Journey Analyticsに簡単に翻訳できます。

Customer Journey AnalyticsAPI を API プロジェクトに追加します。

IMS 組織 ID を API 呼び出しのヘッダーに追加します。

cja.adobe.io と analytics.adobe.io の比較

追加のヘッダー

## 次に、データフィードとData Warehouseを置き換えます

以下を行うために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します [データフィードとData Warehouse機能を置き換える](/help/getting-started/cja-migration/cja-migration-export-options.md) をAdobe Analyticsで使用していた。
