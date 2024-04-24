---
title: Customer Journey Analyticsへの移行時に履歴データを保持
description: Customer Journey Analyticsへの移行時に履歴データを保持する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 2d35e49ca9afe37ed53d7c5da5aafd31dd2da632
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# 手順 4：移行時に履歴データを保持する

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報は、の手順 4 について説明しています。 **移行**&#x200B;次の表でハイライト表示されています。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行パスを選択](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択した移行パスによって異なります。 |
| <span class="preview">**手順 4：履歴データの保持**</span> | <span class="preview">ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。</span> |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | Customer Journey Analyticsプロセスのこの時点では、移行に使用する準備が整う前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからの移行と、新しいCustomer Journey Analytics実装に当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Adobe AnalyticsからCustomer Journey Analyticsに移行する際に履歴データを保持するには、次のいずれかのオプションを選択します。

>[!IMPORTANT]
>
>履歴データの保存方法を選択する場合は、Adobeアカウント担当者に問い合わせて価格を確認してください。

## Analytics ソースコネクタの使用

を使用できます [Analytics ソースコネクタ](/help/data-ingestion/analytics.md) 履歴データを保持する。 どの移行パスを選択した場合でも（Web SDK を使用して移行する場合でも）、Analytics ソースコネクタを使用してAdobe Analytics環境からの履歴データを保持できます。

Analytics ソースコネクタを使用して、履歴データを現在のデータとは別の専用の場所に取り込むことで、履歴データを保持できます。

履歴データにアクセスする必要がある限り、Analytics ソースコネクタは機能している必要があります。

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 既存のAdobe Analytics実装の管理

既存のAdobe Analytics実装を、新しいCustomer Journey Analyticsの実装と一緒に、特定の期間（1 年など）だけ維持管理できます。 このオプションを選択する場合は、次の点を考慮してください。

* データは、Experience Platformでは使用できません。

* 十分なデータをCustomer Journey Analyticsしたら、Adobe Analyticsの実装を廃止する予定です。

## 次に、追加の実装タスクを実行します

Customer Journey Analyticsプロセスのこの時点で、移行環境を使用する準備を整える前に、様々な導入タスクを実行する必要があります。

これらの追加タスクは、Adobe Analyticsからの移行と、新しいCustomer Journey Analytics実装に当てはまります。

次のようなタスクがあります。

* 他のデータのExperience Platform化

* Platform データセットとCustomer Journey Analytics間の接続の作成

* データビューの作成

* レポート API の使用状況の移植

* データフィードとData Warehouseのユースケースの考慮

* プロジェクトとコンポーネントの移行

* ユーザーのオンボーディングの計画

詳細については、の手順 2 から開始してください。 [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md).
