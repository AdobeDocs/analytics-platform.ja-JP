---
title: Adobe Customer Journey Analytics へのアップグレード後、Adobe Analytics が必要な期間の評価
description: Adobe Customer Journey Analytics へのアップグレード後、Adobe Analytics が必要な期間を評価する方法について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 100%

---

# Customer Journey Analytics へのアップグレード後、Adobe Analytics を無効にするタイミングの評価 {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Adobe Customer Journey Analytics への完全な移行"
>abstract="（推奨）アドビでは、Adobe Analytics から Customer Journey Analytics に完全に移行することをお勧めします。移行期間中は、データを横に並べて比較するために、Adobe Analytics を Customer Journey Analytics と共に実行するよう計画する必要があります。データに問題がなければ、Adobe Analytics を無効にできます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="両方の分析製品の保持"
>abstract="（非推奨）このオプションを選択する場合、アドビとの契約には Adobe Analytics と Adobe Customer Journey Analytics の両方が含まれるので、時がたつにつれて組織にとってよりコストが高くなる可能性があります。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Web SDK からのデータのみを使用する Analytics ソースコネクタを無効にする"
>abstract="Analytics ソースコネクタは、並べてデータを比較したり、履歴データを提供したり、Customer Journey Analytics では完全には使用できない一部の機能にアクセスしたりするのに使用されます。これらの目的で Adobe Analytics が不要になった場合は、Analytics ソースコネクタを無効にすることができます。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

ほとんどの組織では、Adobe Customer Journey Analytics へのアップグレード後、最終的に Adobe Analytics を無効にします。これは、2 つの分析環境の維持に伴うコストと複雑さに起因します。

ただし、アドビでは、Adobe Customer Journey Analytics を実装した後、一定期間 Adobe Analytics 環境を実行したままにしておくことをお勧めします。以下の節では、そうすることの理由と、Adobe Analytics を無効にするタイミングについて説明します。

## アップグレード中およびアップグレード後の Adobe Analytics の使用

組織で Adobe Analytics を無効にするかどうか、およびそのタイミングを決定する際には、Adobe Customer Journey Analytics へのアップグレード中とアップグレード後に Adobe Analytics を次のように使用することを検討してください。

| アップグレード中およびアップグレード後の Adobe Analytics の使用 | 説明 |
|---------|----------|
| データの並列比較の実行 | アドビでは、新しい Adobe Customer Journey Analytics 環境が稼動してデータを収集するようになった後も、一定期間 Adobe Analytics 環境の稼動を維持することをお勧めします。これは、Adobe Customer Journey Analytics データを Adobe Analytics データと並べて比較するのに最適な方法です。<p>Adobe Customer Journey Analytics 環境のデータに慣れるまでは、Adobe Analytics を無効にしないでください。</p><p>**メモ：**&#x200B;アドビでは、履歴データ用の Analytics ソースコネクタと組み合わせて、Adobe Customer Journey Analytics 環境用に Web SDK の新しい実装を使用することをお勧めします。[詳細情報](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Adobe Analytics の履歴データの保持 | アドビでは、新しい Adobe Customer Journey Analytics 環境が稼動してデータを収集するようになった後も、一定期間 Adobe Analytics 環境を Analytics ソースコネクタと共に保持することをお勧めします。これは、Adobe Analytics の履歴データを Adobe Customer Journey Analytics に取り込む最適な方法です。<p>新しい Web SDK 実装を使用して Customer Journey Analytics で十分な履歴データを収集したら、Analytics ソースコネクタを完全に削除できます。これを行うのは、Adobe Customer Journey Analytics Web SDK の新しい実装で収集した履歴データのみに頼ることができる場合です。</p><p>**メモ：**&#x200B;アドビでは、履歴データ用の Analytics ソースコネクタと組み合わせて、Adobe Customer Journey Analytics 環境用に Web SDK の新しい実装を使用することをお勧めします。[詳細情報](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| データフィードまたはその他の Adobe Analytics 機能の使用 | Adobe Customer Journey Analytics では、一部の機能はまだ完全には利用できません。これらの機能を利用する必要がある場合は、これらの機能が利用可能になるまで、Adobe Analytics を Adobe Customer Journey Analytics と組み合わせて使用することが必要になる可能性があります。 <p>Customer Journey Analytics で完全に使用できない機能には、データフィードと貢献度分析が含まれます。まだ使用できない機能の完全なリストについては、[Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を参照してください。</p> |

## Adobe Analytics を無効にする手順とタイムライン {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="サードパーティの Tag Management システムを無効にする"
>abstract="Web SDK のデータがすべて機能するので、サードパーティの Tag Management システムから AppMeasurement ライブラリを削除します。<br><br>この手順を実行するのにかかる推定時間は、Tag Management 製品から AppMeasurement を無効にする容易さと、組織がタグコードのデプロイと管理に採用しているリリースサイクルによって異なります。"

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

上記の[アップグレード中およびアップグレード後の Adobe Analytics の使用](#uses-of-adobe-analytics-during-and-after-an-upgrade)の節で説明したように、既存の Adobe Analytics 実装は、Customer Journey Analytics へのアップグレードを成功させるための重要な部分です。

上記の節で説明した目的で Adobe Analytics が不要になった場合は、次の情報を使用して Adobe Analytics を削除してください。

1. Adobe Analytics を使用したデータの収集を停止します。

   Adobe Analytics データと Customer Journey Analytics データの並列比較が完了したら、Adobe Analytics 実装を使用したデータの収集を停止できます。Analytics ソースコネクタを通じた Customer Journey Analytics への新しい Adobe Analytics データのフローは行われなくなります。

   ただし、この時点より前に Adobe Analytics 環境から収集したデータは、Analytics ソースコネクタを通じて Customer Journey Analytics の履歴データとして引き続き利用できます。

   このプロセスは、Adobe Analytics の実装に使用したデータ収集方法によって異なります。

   +++ AppMeasurement

   [AppMeasurement データ収集を無効にする](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)。

   +++

   +++ Analytics 拡張機能（タグ）

   タグで Analytics 拡張機能を無効にします。

   +++

   +++ API

   API データ収集を無効にします。

   +++

   +++ サードパーティ

   タグ管理者と協力して、サードパーティの Tag Management システムから AppMeasurement ライブラリを削除します。

   +++

1. Adobe Analytics をサービスとしてデータストリームから削除します。

   Web SDK のデータがすべて機能するので、Platform 管理者と協力して、Adobe Analytics をサービスとしてデータストリームから削除します。

   Adobe Analytics をサービスとして削除する前に、Analytics ユーザーが Adobe Analytics ではなく Customer Journey Analytics を使用していることを確認します。

1. Analytics ソースコネクタを完全に削除します。

   新しい Web SDK 実装を使用して Customer Journey Analytics で十分な履歴データを収集したら、Analytics ソースコネクタを完全に削除できます。

   Adobe Analytics 環境からの Analytics ソースコネクタ経由の履歴データが不要になり、新しい Web SDK 実装で収集した履歴データのみに依存できる場合に、これを実行します。

{{upgrade-final-step}}

