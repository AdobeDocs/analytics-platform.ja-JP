---
title: Customer Journey Analyticsへのアップグレード時に履歴データを保持
description: Customer Journey Analyticsへのアップグレード時に履歴データを保持する方法を説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 39%

---

# 手順 4：アップグレード時に履歴データを保持する

+++このセクションを展開すると、このページの情報が大きなアップグレードプロセスのどこに適合するかを確認できます。 以前のアップグレード手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のアップグレードタスクがすべて完了していることを確認してください。

このページの情報では、次の表で強調表示されている、アップグレードプロセスの手順 4 について説明します。

| アップグレードタスク | 詳細 |
|---------|----------|
| **手順 1:[ アップグレードの概要](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analyticsへのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。 |
| **手順 2:[ アップグレードパスを選択する](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analyticsへのアップグレードには、様々な方法があります。 組織の現在の Adobe Analytics 環境と長期的な目標に応じて、組織に最適な方法を選択してください。 |
| **手順 3：[データを Adobe Experience Platform に送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| <span class="preview">**手順 4：履歴データを保持**</span> | <span class="preview">ほとんどの組織では、Adobe Analytics の履歴データを一定期間保持する必要があります。これを実現するために様々なオプションが利用できます。</span> |
| **手順 5：[追加の実装タスクを実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々なタスクを実行する必要があります。<p>これらの追加作業は、Adobe Analyticsからのアップグレードと、Customer Journey Analyticsの新規実装に当てはまります。</p><p>これらのタスクには次のものが含まれます。</p><ul><li>他のデータを Experience Platform に取り込む</li><li>手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとデータウェアハウスの考慮</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーオンボーディングの計画</li></ul> <p>詳しくは、[Customer Journey Analytics の概要](/help/getting-started/cja-getting-started.md)を参照してください。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>このページの情報は、次のより包括的なアップグレード情報に置き換えられています。 <ul><li>**推奨されるアップグレード手順**<p>詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード時の推奨パス ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) を参照してください。</p></li><li>**Customer Journey Analytics アップグレードガイド**<p>新しいアップグレードガイドは、組織と独自の状況に合わせたアップグレード手順を動的に生成するものです。</p><p>Customer Journey Analyticsからガイドにアクセスするには、「**[!UICONTROL Workspace]**」タブを選択し、左パネルで「**[!UICONTROL Customer Journey Analyticsにアップグレード]**」を選択します。 画面の指示に従います。</p></li></ul>

Adobe Analytics から Customer Journey Analytics に移行する際に履歴データを保持するには、次のオプションのいずれかを選択します。

>[!IMPORTANT]
>
>履歴データの保持方法を選択する場合は、アドビアカウント担当者に問い合わせて価格を確認してください。

## Analytics ソースコネクタの使用

[Analytics ソースコネクタ ](/help/data-ingestion/analytics.md) を使用して、履歴データを保持できます。 選択するアップグレードパスに関係なく（Web SDKを使用してアップグレードした場合でも）、Analytics ソースコネクタを使用して、Adobe Analytics環境からの履歴データを保持できます。

Analytics ソースコネクタを使用して、履歴データを現在のデータとは別の専用の場所に取り込むことで、履歴データを保持できます。

履歴データにアクセスする必要がある限り、Analytics ソースコネクタは機能している必要があります。

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 既存の Adobe Analytics 実装の保持

新しい Customer Journey Analytics 実装と並行して、既存の Adobe Analytics 実装を特定の期間（例えば、1 年間）保持できます。このオプションを選択する場合は、次の点を考慮します。

* データは Experience Platform では利用できません。

* Customer Journey Analytics に十分なデータが得られたら、Adobe Analytics 実装の廃止を計画する必要があります。

## 次に、追加の実装タスクを実行します

アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々な実装作業を実行する必要があります。

これらの追加作業は、Adobe Analyticsからのアップグレードと、Customer Journey Analyticsの新規実装に当てはまります。

これらのタスクには次のものが含まれます。

* 他のデータを Experience Platform に取り込む

* 手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成

* データビューの作成

* レポート API の使用状況の移植

* データフィードとデータウェアハウスの考慮に関するユースケース

* プロジェクトとコンポーネントの移行

* ユーザーオンボーディングの計画

詳しくは、[Customer Journey Analytics の概要](/help/getting-started/cja-getting-started.md)の手順 2 から開始してください。
