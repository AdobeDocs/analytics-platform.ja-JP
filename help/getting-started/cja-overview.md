---
title: 顧客の遍歴分析の概要
description: 顧客の遍歴分析の概要
translation-type: tm+mt
source-git-commit: 7afdf490d0a63b1286a1a646a487ee96d4b6ed8f

---


# 顧客の遍歴分析の概要

顧客の遍歴分析は、Analysis Workspaceの機能をAdobe Experience Platformのデータと共に使用できるAnalytics機能です。 データの分類、フィルタリング、クエリ、視覚化を行うことができ、また、プラットフォームのあらゆる種類のデータスキーマやデータタイプを保持する機能と組み合わせて使用できます。 エクスペリエ **ンスデータモデル(XDM)を使用すると**、データを均等に表現し、整理し、組み合わせや調査に備えることができます。 **Experience Query Servicesを使用すると** 、SQL互換のツールおよびフレームワークを使用して、すべてのデータのクエリーや操作を行うことができます。

## CJAとAnalysis Workspaceの比較

顧客の遍歴分析は、使いやすいクロスチャネル機能を提供し、以前のバージョンのAdobe Analyticsの制限を取り除くことで、Analyticsの範囲を拡張します。 主な改善点を次に示します。

* **無制限の変数とイベント**:eVar、propおよびeventの概念は存在しなくなりました。 データは主にディメンションと指標に焦点を当てています。 データセットには、一意のディメンションや指標を無制限に含めることができます。
* **ユニーク数の制限**:Adobe Experience Platformは、従来のレポートスイートの500,000個のユニーク値など、一意の制限を受けません。
* **履歴データの変更**:Adobe Experience Platformを使用して、データを削除または修正できます。
* **クロスレポートスイートデータ**:複数のデータセットからの既存の実装は、プラットフォームで組み合わせることができます。

Customer Jeurney Analyticsの最初のリリースには、Analysis Workspaceに含まれる多くの機能が含まれています。 完全なリストについては、「顧客の遍歴分析 [機能のサポート」を参照してくださ](cja-aa.md)い。

### 用語の更新

CJAのいくつかの機能は、業界標準に合わせて名前が変更されました。 更新された名前には、次のものがあります。

* セグメントは「フィルター」と呼ばれるようになりました。
* 仮想レポートスイートが「ビュー」と呼ばれるようになりました。
* 分類は、「参照データセット」と呼ばれるようになりました。
* 顧客属性が「プロファイルデータセット」と呼ばれるようになりました。
* ヒットコンテナは、「イベント」コンテナと呼ばれるようになりました。
* 訪問コンテナは、「セッション」コンテナとして知られるようになりました。
* 訪問者コンテナは、「個人」コンテナと呼ばれるようになりました。

## 主な使用例

顧客の遍歴分析を使用すると、次のことができます。

* **遍歴の中で顧客を見る**:複数のチャネルにまたがるデータを順番に表示および分析できます。 コールセンター、POSシステム、およびオンラインプロパティのデータは、単一のレポートビューに結合できます。
* **インサイトを全員に提供**:データアクセスを民主化し、より多くの人がデータから得た洞察を使ってビジネス上の意思決定を行えるようにします。 顧客体験のあらゆる側面に責任を負う組織内の誰でも、より完全なデータに基づいて、真の意思決定を迅速に行うことができます。
* **分析者のデータ科学の力を活用**:顧客の遍歴分析を使用すると、通常の人間はデータ科学を使用して、深い洞察と分析を解き放つことができます。
* **アドホックレポートを使用して、データセットを視覚化し、操作します**。Workspaceは、Adobe Experience Platformのデータセットの中で、基本的なルールに準拠するものを使用できます。
* **非Webデータの表示**:Workspaceが、「ヒット」または「イベント」の厳密な定義に制限されなくなりました。 カスタムスキーマを使用すると、データと定義を完全に制御できます。
* **データ操作をより詳細に制御**:アップロードしたデータの変更、新しいデータセットの作成、Workspaceへの読み込みを行います。 Adobe Experience Platformは、Experience Cloud Query Serviceを通じて、ツールのクエリ、抽出、変換、読み込みを行います。

## 前提条件

Customer Jeurney Analyticsの使用を開始する前に、次の手順を完了する必要があります。

* 組織は、Customer Jaurney Analyticsアドオンを使用して、Select、PrimeまたはUltimateに関するアクティブな契約を結んでいます。 契約の種類が不明な場合や、CJAアドオンをお持ちかどうか不明な場合は、組織のアカウントマネージャーにお問い合わせください。
* 組織はAdobe Experience Platform用にプロビジョニングされました。

## ユーザーアクセス権限

接続を作成したり、データセットを追加したりするには、管理コンソールで次の権限が [必要です](https://adminconsole.adobe.com/enterprise/)。

* Experience Platformでデータセットを管理するには、「データセットを管理」権限を持つプラットフォーム製品プロファイルの一部である必要があります。 詳しくは、「Adobe Experience Platformでのア [クセス制御」を参照してください](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)。
* プラットフォームデータセットへの接続を作成するには、次の権限を持つプラットフォーム製品プロファイルに属している必要があります。
   * スキーマの表示
   * データセットの表示
   * ID名前空間の管理
   * サンドボックスを表示
* 顧客の遍歴分析にアクセスする、または接続するには、管理コンソールで顧客の遍歴分析製品プロファイルに追加する必要 [があります](https://adminconsole.adobe.com/enterprise/)。

## Adobe Experience Platformで構築されたその他の機能

顧客の遍歴分析は、Adobe Experience Platformを利用する多くの機能の1つです。 他にも、プラットフォーム上で構築されたいくつかの機能を使用して、データを最大限に活用できます。

Adobe Experience Platformを使用すると、顧客データとコンテンツを任意のシステムから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を改善できます。 プラットフォームの顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。 プラットフォームについて詳しくは、 [Adobe Experience Platform Architecture Overviewを参照してください](https://www.adobe.io/apis/experienceplatform/home/overview.html)。

データの取り込みからSQLへの直接アクセスに至るまで、エクスペリエンスプラットフォームのいくつかのコンポーネントは、顧客の遍歴分析の中心となり、これと連携して動作します。

* [Query Service](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html):標準のSQLを使用して、アドビのソリューションデータ、お客様のファーストパーティデータ、その他のプラットフォームデータなど、Adobe Experience Platformからデータを取得します。 このツールは、任意のデータセットを結合し、クエリ結果を新しいデータセットとして取り込み、レポート、Data Science Workspace、またはプロファイルサービスへの取り込みに使用できるサーバーレスツールです。 Query Serviceを使用して、データ分析エコシステムを構築し、様々なインタラクションチャネルにわたる消費者の画像を作成できます。 これらのチャネルには、販売時点管理システム、Web、モバイル、CRMシステムなどが含まれます。
* [リアルタイム顧客プロファイル](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [ID サービス](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) （「開発者」オプション）:adobe Experience Platformの事前設計された人工知能(AI)と機械学習モデルを使用して、顧客の遍歴の様々なポイントに影響を与えることができます。 隠れた洞察を発見することで、顧客の遍歴を通じてより良い予測を立てたり、推奨される次のステップを提案したり、面倒なプロセスを自動化したりできます。
