---
description: Real-time Customer Data Platform（リアルタイム CDP）とCustomer Journey Analyticsの間の指標とオーディエンスメンバーシップのカウントの一貫性に影響する要因について説明します。
title: リアルタイム CDP とCustomer Journey Analyticsの間の指標とオーディエンスメンバーシップ数の一貫性
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 25%

---


# リアルタイム CDP とAdobe Customer Journey Analyticsの間で、指標とオーディエンスメンバーシップのカウントの一貫性

実際のシナリオでは、Real-time Customer Data Platform（リアルタイム CDP）とCustomer Journey Analytics全体で指標とオーディエンスメンバーシップのカウントの一貫性を保証することはできません。 このドキュメントでは、その理由を説明します。

リアルタイム CDP とCustomer Journey Analyticsの間でオーディエンスメンバーシップ数を比較する場合、これら 2 つのツールの異なる目的に注意する必要があります。 リアルタイム CDP は、顧客プロファイルデータを使用して個々の消費者にデジタルエクスペリエンスをターゲット設定し、Customer Journey Analyticsは、主要ビジネス指標やセグメントのパターンを理解するのに役立ちます。 Customer Journey Analyticsからリアルタイム CDP にオーディエンスを公開すると、これらのツールのユーザーは、Customer Journey Analyticsで得られた知識を活用し、インサイトを簡単かつネイティブに「アクティブ化」できますが、これらのツールは根本的に異なる目的を果たします。

## ID 設定の違い

リアルタイム CDP とCustomer Journey Analyticsは、現在の人物と同じ定義を共有していません。 Real-time CDP は、[ID グラフ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=ja)内の情報に完全に依存して、結合されたプロファイルを作成します。

Customer Journey Analyticsは、 [ステッチ](../stitching/overview.md) は、データレイクのデータセットから識別子を抽出し、それらをリンクするカスタムロジックを適用します。

今後、Customer Journey Analyticsは ID グラフを使用できるようになります。

## データセット設定の違い

一部のデータをリアルタイム CDP に、一部のデータをCustomer Journey Analyticsに配置できます。多くの場合、お客様は、リアルタイム CDP に関連するよりも多くの履歴データをCustomer Journey Analyticsに入れることを選択します。 他のデータセットは、Customer Journey Analyticsよりもリアルタイム CDP に関連性が高い場合があります。

## 処理設定の違い

Customer Journey Analyticsを使用すると、フィールドの結合、フィールドの分割、含む/除外、サブ文字列、値の重複排除、セッション化、行レベルのフィルタリングなどの他の操作など、クエリ時に大幅なデータ変更が可能です。

Real-time CDP は、様々なデータ操作ツールのセットを提供します。[結合ポリシー](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=ja)を適用し、データの優先順位付けおよびデータの組み合わせを決定し、ユーザーの統一されたビューを作成します。

## TTL（Time to Live）とデータ取り込みの違い

リアルタイム CDP とCustomer Journey Analyticsのデータセットが同じであっても、リアルタイム CDP は履歴の限られた期間のみを保持できます。 一方、Customer Journey Analyticsには数年分のデータが存在する可能性が高くなります。 それに加えて：

* Customer Journey Analyticsとリアルタイム CDP のお客様は、互いに関係なく、データのカスタム保存期間を設定できます。

* リアルタイム CDP とCustomer Journey Analyticsは、データを取り込むための異なるロジックを持ちます。 Customer Journey Analyticsは、ユーザー ID やタイムスタンプのないレコードを無視し、1 人のプロファイルまたはユーザーが持つレコードの数に厳密な制限を設けます。

* Real-time CDP のユーザーは、主にプロファイルへのデータのオンボーディングとアドホックなクエリを促進するために、レイク内のデータに 7 日間アクセスできます。

* Customer Journey Analyticsのお客様の場合、レイク内のデータに TTL がありません。 Customer Journey Analyticsユーザー自身は、接続を作成する際に、カスタムのリテンションウィンドウをCustomer Journey Analyticsで設定することはできます。

* Real-time CDP のプロファイルストアでは、ユーザーが設定可能な TTL を提供します。ユーザーは、この TTL を、ライセンスの使用権限の範囲内で必要なものに変更できます。

## データ取り込み待ち時間の違い

Customer Journey Analyticsにはまだリアルタイム CDP のリアルタイム機能がなく、その結果、Customer Journey Analyticsレポートには、データをレポートまたはオーディエンス作成に使用する前の遅延が含まれます。 Real-Time CDP は、待ち時間の異なる様々なシステムを介してデータを処理します。
