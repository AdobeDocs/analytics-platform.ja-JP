---
title: Customer Journey Analytics へのアップグレード後、Adobe Analytics が必要となる期間の評価
description: Customer Journey Analyticsへのアップグレード後、Adobe Analyticsが必要となる期間を評価する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 31%

---

# Customer Journey Analytics へのアップグレード後、Adobe Analytics を無効にするタイミングの評価 {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Customer Journey Analytics への完全な移行"
>abstract="（推奨）アドビでは、Adobe Analytics から Customer Journey Analytics に完全に移行することをお勧めします。移行期間中は、データを横に並べて比較するために、Adobe Analytics を Customer Journey Analytics と共に実行するよう計画する必要があります。データに問題がなければ、Adobe Analytics を無効にできます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="両方の分析製品の保持"
>abstract="（非推奨）このオプションを選択すると、アドビとの契約に Adobe Analytics と Customer Journey Analytics の両方が含まれるので、時間の経過と共に組織にとってコストが高くなる場合があります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Web SDK からのデータのみを使用する Analytics ソースコネクタを無効にする"
>abstract="Analytics ソースコネクタは、並べてデータを比較したり、履歴データを提供したり、Customer Journey Analytics では完全には使用できない一部の機能にアクセスしたりするのに使用されます。これらの目的で Adobe Analytics が不要になった場合は、Analytics ソースコネクタを無効にすることができます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

ほとんどの企業は、Customer Journey Analyticsへのアップグレード後に、最終的にAdobe Analyticsを無効にします。 これは、2 つの分析環境の維持に伴うコストと複雑さによるものです。

ただし、Adobeでは、Customer Journey Analyticsを実装した後の一定期間、Adobe Analytics環境を実行し続けることをお勧めします。 次の節では、そのような理由と、Adobe Analyticsを無効にするタイミングについて説明します。

## アップグレード中およびアップグレード後のAdobe Analyticsの使用

Customer Journey Analyticsを無効にするかどうかを判断する際や、無効にするタイミングを決める際には、Adobe Analyticsにアップグレードする際とその後にAdobe Analyticsを使用した次の点を考慮してください。

| アップグレード中およびアップグレード後のAdobe Analyticsの使用 | 説明 |
|---------|----------|
| 並列データ比較の実行 | Adobeでは、新しいAdobe Analytics環境が動作してデータを収集した後、一定期間Customer Journey Analytics環境を動作させ続けることをお勧めします。 これは、Customer Journey Analytics データをAdobe Analytics データと並べて比較するのに最適な方法です。<p>Customer Journey Analytics内のデータに慣れるまでは、Adobe Analyticsを無効にしないでください。</p><p>**メモ：** Adobeでは、履歴データ用の Analytics ソースコネクタと組み合わせて、Customer Journey Analytics環境に対応する新しい実装の web SDKを使用することをお勧めします。 [詳細情報](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Adobe Analyticsの履歴データを保持 | Adobeでは、新しいAdobe Analytics環境が動作してデータを収集した後、しばらくの間Customer Journey Analytics環境を Analytics ソースコネクタと共に保持することをお勧めします。 これは、Adobe Analyticsの履歴データをCustomer Journey Analyticsに取り込む最適な方法です。<p>新しい Web SDKの実装で、Customer Journey Analyticsに十分な履歴データを収集したら、Analytics ソースコネクタを完全に削除できます。 新しいCustomer Journey Analytics web SDKの実装で収集した履歴データのみを利用できる場合は、この方法を使用します。</p><p>**メモ：** Adobeでは、履歴データ用の Analytics ソースコネクタと組み合わせて、Customer Journey Analytics環境に対応する新しい実装の web SDKを使用することをお勧めします。 [詳細情報](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| データフィードまたはその他のAdobe Analytics機能の使用 | Customer Journey Analyticsでは、少数の機能はまだ完全には使用できません。 これらの機能にアクセスする必要がある場合は、これらの機能が使用可能になるまで、Adobe AnalyticsをCustomer Journey Analyticsと組み合わせて使用する必要がある可能性があります。 <p>Customer Journey Analyticsで完全には使用できない機能には、データフィードと貢献度分析が含まれます。 まだ利用できない機能の一覧については、[Customer Journey Analytics機能のサポート ](/help/getting-started/aa-vs-cja/cja-aa.md) を参照してください。</p> |

## Adobe Analytics を無効にするプロセスとタイムライン {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="サードパーティのタグ管理システムの無効化"
>abstract="Web SDK データが完全に機能したら、タグ管理者と協力してサードパーティのタグ管理システムから AppMeasurement ライブラリを削除します。<br><br>この手順を実行するのにかかる推定時間は、タグ管理製品から AppMeasurement を無効にする容易さと、組織がタグコードのデプロイと管理に導入しているリリースサイクルによって異なります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="タグの Analytics 拡張機能を無効にする"
>abstract=" Web SDK データが完全に機能したら、タグ管理者と協力して、タグプロパティから Adobe Analytics 拡張機能を削除します。これを実行する前に、ユーザーが Adobe Analytics から Customer Journey Analytics に移行していることを確認します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Adobe Analytics の API データ収集を無効にする"
>abstract="Web SDK データが完全に機能したら、該当するエンジニアリングチームと協力して、プロジェクトから Adobe Analytics コードを削除します。これを実行する前に、ユーザーが Adobe Analytics から Customer Journey Analytics に移行していることを確認します。"

<!-- markdownlint-enable MD034 -->

前述の節 [ アップグレード中およびアップグレード後のAdobe Analyticsの使用 ](#uses-of-adobe-analytics-during-and-after-an-upgrade) で説明しているように、既存のAdobe Analytics実装は、Customer Journey Analyticsへのアップグレードを成功させるための重要な部分です。

前述の節で説明した目的でAdobe Analyticsが不要になった場合は、次の情報を使用してAdobe Analyticsを削除します。

1. Adobe Analyticsでのデータ収集を停止します。

   Adobe Analytics データとCustomer Journey Analytics データの並列比較の設定が完了したら、Adobe Analyticsの実装を使用したデータ収集を停止できます。 新しいAdobe Analytics データは、Analytics ソースコネクタを介してCustomer Journey Analyticsに送られなくなります。

   ただし、この時点より前にAdobe Analytics環境から収集したデータは、Analytics ソースコネクタを通じてCustomer Journey Analyticsで履歴データとして引き続き使用できます。

   このプロセスは、Adobe Analyticsの実装に使用したデータ収集方法によって異なります。

+++ AppMeasurement

   [AppMeasurement データ収集を無効にします ](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)。

+++

+++ Analytics 拡張機能（タグ）

   タグの Analytics 拡張機能を無効にします。

+++

+++ API

   API データ収集を無効にします。

+++

+++ サードパーティ

   タグ管理者と協力して、サードパーティのタグ管理システムからAppMeasurement ライブラリを削除します。

+++

1. データストリームからAdobe Analytics as a service を削除します。

   Web SDKのデータがすべて機能するので、Platform 管理者と協力して、Adobe Analytics as a service をデータストリームから削除します。

   Adobe Analytics as a service を削除する前に、Analytics ユーザーがAdobe AnalyticsではなくCustomer Journey Analyticsを使用していることを確認してください。

1. Analytics ソースコネクタを完全に削除します。

   新しい Web SDKの実装で、Customer Journey Analyticsに十分な履歴データを収集したら、Analytics ソースコネクタを完全に削除できます。

   これは、Analytics ソースコネクタを使用してAdobe Analytics環境から履歴データを必要とせず、新しい web SDKの実装で収集した履歴データのみを使用できる場合に行います。

{{upgrade-final-step}}

