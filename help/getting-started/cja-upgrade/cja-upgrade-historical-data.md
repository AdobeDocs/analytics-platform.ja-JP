---
title: Customer Journey Analyticsへのアップグレード時に履歴データを保持
description: Customer Journey Analyticsへのアップグレード時に履歴データを保持する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# 手順 4：アップグレード時に履歴データを保持する

+++このセクションを展開すると、このページの情報が大きなアップグレードプロセスのどこに適合するかを確認できます。 以前のアップグレード手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のアップグレードタスクがすべて完了していることを確認してください。

このページの情報では、次の表で強調表示されている、アップグレードプロセスの手順 4 について説明します。

| アップグレードタスク | 詳細 |
|---------|----------|
| **手順 1: [アップグレードの概要](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analyticsへのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。 |
| **手順 2: [アップグレードパスの選択](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analyticsへのアップグレードには様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| <span class="preview">**手順 4：履歴データの保持**</span> | <span class="preview">ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。</span> |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからのアップグレードや、新しいCustomer Journey Analyticsの実装にも当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Adobe AnalyticsからCustomer Journey Analyticsに移行する際に履歴データを保持するには、次のいずれかのオプションを選択します。

>[!IMPORTANT]
>
>履歴データの保存方法を選択する場合は、Adobeアカウント担当者に問い合わせて価格を確認してください。

## Analytics ソースコネクタの使用

を使用できます [Analytics ソースコネクタ](/help/data-ingestion/analytics.md) 履歴データを保持する。 選択するアップグレードパスに関係なく（Web SDK を使用してアップグレードする場合でも）、Analytics ソースコネクタを使用して、Adobe Analytics環境からの履歴データを保持できます。

Analytics ソースコネクタを使用して、履歴データを現在のデータとは別の専用の場所に取り込むことで、履歴データを保持できます。

履歴データにアクセスする必要がある限り、Analytics ソースコネクタは機能している必要があります。

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 既存のAdobe Analytics実装の管理

既存のAdobe Analytics実装を、新しいCustomer Journey Analyticsの実装と一緒に、特定の期間（1 年など）だけ維持管理できます。 このオプションを選択する場合は、次の点を考慮してください。

* データは、Experience Platformでは使用できません。

* 十分なデータをCustomer Journey Analyticsしたら、Adobe Analyticsの実装を廃止する予定です。

## 次に、追加の実装タスクを実行します

アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々な実装作業を実行する必要があります。

これらの追加タスクは、Adobe Analyticsからのアップグレードや、新しいCustomer Journey Analyticsの実装にも当てはまります。

次のようなタスクがあります。

* 他のデータのExperience Platform化

* Platform データセットとCustomer Journey Analytics間の接続の作成

* データビューの作成

* レポート API の使用状況の移植

* データフィードとData Warehouseのユースケースの考慮

* プロジェクトとコンポーネントの移行

* ユーザーのオンボーディングの計画

詳細については、の手順 2 から開始してください。 [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md).
