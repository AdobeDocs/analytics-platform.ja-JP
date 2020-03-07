---
title: 顧客の遍歴分析 — はじめに
description: 顧客の遍歴分析の概要を参照してください。
translation-type: tm+mt
source-git-commit: 1aebe79040b6c8b9eb8a336e158f5ce6d2ea16a4

---


# 顧客の遍歴分析 — はじめに

顧客の遍歴分析を導入するには、このワークフローに従う必要があります。 一部の初期タスクはAdobe Experience Platformで実行され、一部はCustomer Jeurney Analyticsで実行されます。

## 前提条件

顧客の遍歴分析は、

* Adobe Analyticsのお客様は [、Select、PrimeまたはUltimateのお客様](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) か。
* Adobe Experience Platform用にプロビジョニン [グされている](https://www.adobe.com/experience-platform.html)
* 顧客の遍歴分析SKUを購入済み

## ワークフロー

| タスク | 実行場所 | 詳細 |
|---|---|---|
| **手順1:データスキーマの準備** | Adobe Experience Platform | Adobe Experience Data Model( [XDM)を使用して](https://www.adobe.io/apis/experienceplatform/home/xdm.html) 、顧客エクスペリエンスデータを標準化し、顧客エクスペリエンス管理のスキーマを定義します。 |
| **手順2:スキーマに基づくデータセットの作成** | Adobe Experience Platform | プラットフォームのデータは、電子メールデータセット、CRMデータセット、POSデータセット、Adobe Analyticsデータセットなどのデータセットで構成されます。 各データセットは、1つのスキーマと1つのデータのバッチで構成されます。 Experience Platformでデータセットを作 [成できます](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)。<br>Customer Jeurney Analyticsにインポートできるデータセットのスキーマは柔軟性が高く、いくつかの基本ルールに準拠する必要があります。 データをプラットフォームにアップロードする前に、データがこれらの要件を満たしていることを確認することをお勧めします。 （スキーマには指標とディメンションの両方が含まれます）。<br>Customer Jeurney Analyticsと互換性のあるデータには、次の3種類があります。<ul><li>**イベントデータ**:時間内のイベントを表すデータ（例：Web訪問、インタラクション、トランザクション、POSデータ、調査データ、広告インプレッションデータ）。 これは、顧客IDまたはcookie IDとタイムスタンプを持つ一般的なクリックストリームデータです。 イベントデータを使用すると、任意のIDを使用できます。</li><li>**参照データ**:このデータは、イベントデータまたはプロファイルデータ内の値やキーを参照するために使用されます。 例えば、イベントデータ内の数値IDを製品名にマップする参照データをアップロードできます。</li><li>**プロファイルデータ**:イベントデータ内の訪問者、ユーザーまたは顧客に適用されるデータ。 例えば、顧客に関するCRMデータをアップロードできます。</li></ul> |
| **手順3：プラットフォームデータセットとCustomer Jeurney Analytics間の接続を作成する** | カスタマージャーニー分析 | 接続の作 [成を参照してください](/help/connections/create-connection.md)。 |
| **手順4:データビューの作成** | カスタマージャーニー分析 | 詳しくは、 [データビューの作成を参照してくださ](/help/data-views/create-dataview.md)い。 |
| **手順5:Workspaceでのチャネル間データのレポート** | カスタマージャーニー分析 | 基本分析の [実行および詳細分析](/help/projects/perform-basic-analysis.md) の実行 [を参照してください](/help/projects/perform-adv-analysis.md)。 |

## データスキーマの準備

[スキーマエディターを使用したスキーマの作成](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)


