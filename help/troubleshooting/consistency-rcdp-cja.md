---
description: Real-time Customer Data Platform（Real-time CDP）と Customer Journey Analytics の間の指標とオーディエンスメンバーシップのカウントの一貫性に影響する要因について説明します。
title: 指標とオーディエンスメンバーシップの一貫性
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 7c906e30d54362713f5013c8661ee523938d4b0f
workflow-type: ht
source-wordcount: '625'
ht-degree: 100%

---


# 指標とオーディエンスメンバーシップの一貫性

実際のシナリオでは、Real-time Customer Data Platform（Real-time CDP）と Customer Journey Analytics 全体で指標とオーディエンスメンバーシップのカウントの一貫性を保証することはできません。このドキュメントでは、その理由を説明します。

Real-time CDP と Customer Journey Analytics の間でオーディエンスのメンバーシップカウントを比較する場合、これら 2 つのツールが持つ異なる目的に注意する必要があります。Real-time CDP は、顧客プロファイルデータを使用して個々の消費者にデジタルエクスペリエンスをターゲティングする一方で、Customer Journey Analytics は、主要なビジネス指標やセグメントのパターンの理解に役立ちます。Customer Journey Analytics から Real-time CDP へのオーディエンスの公開では、これらのツールのユーザーは、Customer Journey Analytics で得られた知識を活用し、インサイトを簡単かつ自然に「アクティベート」できますが、これらのツールは根本的に異なる目的を持っています。

## ID 設定の違い

Real-time CDP と Customer Journey Analytics は、現在、同じユーザーの定義を共有していません。Real-time CDP は、[ID グラフ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=ja)内の情報に完全に依存して、結合されたプロファイルを作成します。

Customer Journey Analytics は、[ステッチ](../stitching/overview.md)を使用するように設定できます。ステッチメカニズムとして[フィールドベースのステッチ](/help/stitching/fbs.md)を使用する場合は、データレイクのデータセットから識別子を指定して、そのデータセットのデータをステッチし、改善された結合プロファイルでデータセットを向上させます。ステッチメカニズムとして[グラフベースのステッチ](/help/stitching/gbs.md)を使用する場合は、同様のプロセスで、指定した ID 名前空間に基づいて ID グラフを使用します。


## データセット設定の違い

一部のデータを Real-time CDP に、一部を Customer Journey Analytics に配置できます。ユーザーは大抵の場合、Real-time CDP に関連するデータよりも多くの履歴データを Customer Journey Analytics に配置することを選択します。他のデータセットは、Customer Journey Analytics よりも Real-time CDP に関連している場合があります。

## 処理設定の違い

Customer Journey Analytics を使用すると、フィールドの結合、フィールドの分割のほか、包含／除外、部分文字列、値の重複排除、セッション化、行レベルのフィルタリングといった操作など、クエリ時に大幅なデータ変更を行うことができます。

Real-time CDP は、様々なデータ操作ツールのセットを提供します。[結合ポリシー](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=ja)を適用し、データの優先順位付けおよびデータの組み合わせを決定し、ユーザーの統一されたビューを作成します。

## TTL（Time to Live）とデータ取り込みの違い

Real-time CDP と Customer Journey Analytics のデータセットが同じであっても、Real-time CDP は限られた期間の履歴のみを保持する場合があります。それに対して、Customer Journey Analytics には数年分のデータが存在する可能性があります。追加事項：

* Customer Journey Analytics と Real-time CDP のユーザーは、データのカスタム保持期間を互いに独立して設定できます。

* Real-time CDP と Customer Journey Analytics は、データ取り込みの異なるロジックを持っています。Customer Journey Analytics は、ユーザー ID やタイムスタンプのないレコードを無視し、単一のプロファイル／ユーザーが持つレコードの数に厳密な制限を設けています。

* Real-time CDP のユーザーは、主にプロファイルへのデータのオンボーディングとアドホックなクエリを促進するために、レイク内のデータに 7 日間アクセスできます。

* Customer Journey Analytics のユーザーの場合、レイク内のデータに対して TTL はありません。ただし、Customer Journey Analytics ユーザーは、接続の作成時に Customer Journey Analytics でカスタム保持期間を自分で設定できます。

* Real-time CDP のプロファイルストアでは、ユーザーが設定可能な TTL を提供します。ユーザーは、この TTL を、ライセンスの使用権限の範囲内で必要なものに変更できます。

## データ取り込み待ち時間の違い

Customer Journey Analytics にはまだ Real-time CDP のリアルタイム機能がないので、Customer Journey Analytics レポートには、レポートやオーディエンス作成のためにデータが利用可能になるまでに多少の待ち時間が発生します。Real-time CDP は、待ち時間の異なる様々なシステムを介してデータを処理します。
