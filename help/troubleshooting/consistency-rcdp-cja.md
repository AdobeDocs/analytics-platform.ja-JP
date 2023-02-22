---
description: Real-time Customer Data Platform（Real-time CDP）と CJA の間の指標とオーディエンスメンバーシップのカウントの一貫性に影響する要因について説明します。
title: Real-time CDP と CJA の間における指標とオーディエンスメンバーシップのカウントの一貫性
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 34ee7954329d7dc8520031a977bb83d6e1bf3d3d
workflow-type: ht
source-wordcount: '577'
ht-degree: 100%

---


# Real-time CDP と CJA の間における指標とオーディエンスメンバーシップのカウントの一貫性

実際のシナリオでは、Real-time Customer Data Platform（Real-time CDP）と Customer Journey Analytics（CJA）全体で指標とオーディエンスメンバーシップのカウントの一貫性を保証することはできません。このドキュメントでは、その理由を説明します。

Real-time CDP と CJA の間でオーディエンスのメンバーシップカウントを比較する場合、これら 2 つのツールが持つ異なる目的に注意する必要があります。Real-time CDP は、顧客プロファイルデータを使用して個々の消費者にデジタルエクスペリエンスを対象とする一方で、CJA は、主要なビジネス指標やセグメントのパターンを理解することに役立ちます。CJA から Real-time CDP のオーディエンスの公開では、これらのツールのユーザーは、CJA で得られた知識を活用し、インサイトを簡単かつ自然に「アクティベート」できますが、これらのツールは根本的に異なる目的を持っています。

## ID 設定の違い

Real-time CDP と CJA は、現在、同じ人物の定義を共有していません。Real-time CDP は、[ID グラフ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=ja)内の情報に完全に依存して、結合されたプロファイルを作成します。

CJA は、データレイク内のデータセットから識別子を抽出し、カスタムロジックを適用してデータセットをリンクする[クロスチャネル分析](/help/cca/overview.md)を使用するように設定できます。

今後、CJA は ID グラフを使用できるようになります。

## データセット設定の違い

一部のデータを Real-time CDP に、一部を CJA に配置できます。ユーザーは大抵の場合、Real-time CDP に関連するデータよりも多くの履歴データを CJA に配置することを選択します。他のデータセットは、CJA よりも、Real-time CDP により関連性が高い場合があります。

## 処理設定の違い

CJA を使用すると、フィールドの結合、フィールドの分割、包含／除外、部分文字列、値の重複排除、セッション化、行レベルのフィルタリングといった操作など、クエリ時に大幅なデータ変更を行うことができます。

Real-time CDP は、様々なデータ操作ツールのセットを提供します。[結合ポリシー](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=ja)を適用し、データの優先順位付けおよびデータの組み合わせを決定し、ユーザーの統一されたビューを作成します。

## TTL（Time to Live）とデータ取り込みの違い

Real-time CDP と CJA のデータセットが同じであっても、Real-time CDP は限られた期間の履歴のみを保持します。それに対して、CJA には数年分のデータが存在する可能性があります。それに加えて：

* CJA と Real-time CDP のユーザーは、データの保存期間カスタムウィンドウをそれぞれ独立して設定できます。

* Real-time CDP と CJA は、データ取り込みの異なるロジックを持っています。CJA は、人物 ID やタイムスタンプのないレコードを無視し、単一のプロファイル／人物が持つレコードの数に厳密な制限があります。

* Real-time CDP のユーザーは、主にプロファイルへのデータのオンボーディングとアドホックなクエリを促進するために、レイク内のデータに 7 日間アクセスできます。

* CJA のユーザーの場合、レイク内のデータに対して TTL はありません。ただし、CJA ユーザー自身が、接続作成時に CJA で保持期間を設定できます。

* Real-time CDP のプロファイルストアでは、ユーザーが設定可能な TTL を提供します。ユーザーは、この TTL を、ライセンスの使用権限の範囲内で必要なものに変更できます。

## データ取り込み待ち時間の違い

CJA にはまだ Real-Time CDP のリアルタイム機能がないので、CJA レポートには、レポートやオーディエンス作成のためにデータが利用可能になるまでに多少の待ち時間が発生します。Real-Time CDP は、待ち時間の異なる様々なシステムを介してデータを処理します。
