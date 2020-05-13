---
title: Customer Journey Analytics の概要
description: 顧客の遍歴分析の概要
translation-type: tm+mt
source-git-commit: 6f5c3c073069ca7f428d971515342c1a636795e3
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 7%

---


# Customer Journey Analytics の概要

カスタマージャーニー分析は、Analyticsの機能で、Adobe Experience Platformのデータを使用して分析ワークスペースの機能を利用できます。 データの分類、フィルタリング、クエリ、視覚化に役立つ年数分のデータを利用でき、Platformのあらゆる種類のデータスキーマやデータの種類を保持する機能と組み合わせて使用できます。 Experience Data Model(XDM)を使用すると ****、データを均等に表現し、整理して、組み合わせや調査に対応できます。 **エクスペリエンスクエリサービス** :SQL互換のツールおよびフレームワークを使用して、すべてのデータをクエリし、操作できます。

## CJAと従来のAdobe Analyticsの比較

カスタマージャーニー分析では、使いやすいクロスチャネル機能を提供し、以前のバージョンのAdobe Analyticsの制限を取り除くことで、Analyticsの範囲を拡張します。 主な改善点を次に示します。

* **無制限の変数とイベント**: eVar、prop、イベントの概念は存在しなくなりました。 データは主にディメンションと指標に焦点を当てています。 データセットには、一意のディメンションと指標の数に制限はありません。
* **ユニーク値は無制限**: Adobe Experience Platformは、従来のレポートスイートの500,000個のユニーク値など、一意の制限には制約されません。
* **履歴データの変更**: Adobe Experience Platformを使用して、データを削除または修正できます。
* **クロスレポートスイートデータ**: 複数のデータセットからの既存の実装は、プラットフォームで組み合わせることができます。

Customer Jeurney Analyticsの最初のリリースには、Customer Workspaceに含まれる多くの機能が含まれています。 完全なリストについては、「 [カスタマージャーニー分析機能のサポート](cja-aa.md)」を参照してください。

## CJAとデバイス間の分析の比較

[デバイス間の分析](https://docs.adobe.com/content/help/ja-JP/analytics/components/cda/cda-home.html) :Co-op Graphまたはプライベートグラフを利用するAdobe Experience Platform Identity Serviceと統合して、デジタルデバイスと人とのマッピング方法を特定します。 Adobe Analytics Ultimateのお客様が利用できます。

CJAは、Adobe Experience Platformのデータセットと統合され、分析ワークスペースでのチャネル間の分析を可能にします。 CJAはまだCo-opまたはプライベートIDグラフとは統合されていませんが、独自のIDを持ってデータセットを結合できます。また、これらのデータセットはデジタルデータを超え、オンラインとオフラインの両方のタッチポイントを含むことができます。 CJAの前提条件について詳しくは、以下を参照してください。

## 主な使用例

顧客の遍歴分析では、次のことができます。

* **遍歴の中で顧客を見る**: 複数のチャネルにまたがるデータを順番に表示および分析できます。 コールセンター、POSシステム、オンラインプロパティのデータは、1つのレポート表示に結合できます。
* **インサイトを全員に提供**: データアクセスを民主化し、データに基づくインサイトを活用してより多くの人がビジネス上の意思決定を行えるようにします。 顧客体験のあらゆる側面に責任を負う組織内の誰でも、より完全なデータに基づいて、真の意思決定を迅速に行うことができます。
* **分析者にデータ科学の機能を活用**: 顧客の遍歴分析を使用すると、通常の人間はデータ科学を使用して、深い洞察と分析を解き放つことができます。
* **アドホックレポートを使用してデータセットを視覚化し、操作します**。 Workspaceでは、Adobe Experience Platformのデータセットで、基本的なルールに準拠しているものを使用できます。
* **Web以外の表示データ**: ワークスペースが、「ヒット」または「イベント」の厳密な定義に制限されなくなりました。 カスタムスキーマでは、データと定義を完全に制御できます。
* **データ操作をより詳細に制御する**: アップロードしたデータの変更、新しいデータセットの作成、Workspaceへのインポートを行います。 Adobe Experience Platformは、Experience Cloudクエリサービスを通じて、ツールのクエリ、抽出、変換および読み込みを行います。

## 前提条件

Customer Jeurney Analyticsを使用して開始を行う前に、次の前提条件を満たす必要があります。

* 組織は、Adobe AnalyticsとSelect、PrimeまたはUltimateの間で、Customer Jeurney Analyticsアドオンとの間でアクティブな契約を結んでいます。 契約の種類が不明な場合や、CJAアドオンがあるかどうかが不明な場合は、組織のアカウントマネージャーにお問い合わせください。
* 組織がAdobe Experience Platform用にプロビジョニングされました。

## ユーザーアクセス権限

接続を作成したり、データセットを追加したりするには、 [管理コンソールで次の権限が必要です](https://adminconsole.adobe.com/enterprise/)。

* Experience Platformでデータセットを管理するには、「データセットを管理」の権限を持つプラットフォーム製品プロファイルのメンバーである必要があります。 詳しくは、「Adobe Experience Platformでの [アクセス制御](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)」を参照してください。
* プラットフォームデータセットへの接続を作成するには、次の権限を持つプラットフォーム製品プロファイルに所属している必要があります。
   * 表示スキーマ
   * 表示データセット
   * ID名前空間の管理
   * 表示サンドボックス
* カスタマージャーニー分析にアクセスする、または接続するには、 [管理コンソールのカスタマージャーニー分析製品プロファイルにも追加される必要があります](https://adminconsole.adobe.com/enterprise/)。

### 用語の更新

CJAのいくつかの機能は、業界標準に合わせて名前が変更されました。 更新された名前には次のようなものがあります。

* セグメントは「フィルター」と呼ばれるようになりました。
* 仮想レポートスイートは、「表示」と呼ばれるようになりました。
* 分類は、「参照データセット」と呼ばれるようになりました。
* 顧客属性は、「プロファイルデータセット」と呼ばれるようになりました。
* ヒットコンテナは、「イベント」コンテナと呼ばれるようになりました。
* 訪問コンテナは、現在は「セッション」コンテナと呼ばれます。
* 訪問者コンテナは、現在は「人」コンテナと呼ばれています。

## Adobe Experience Platformで構築されたその他の機能

カスタマージャーニー分析は、Adobeエクスペリエンスプラットフォームに依存する多くの機能の1つです。 他にもプラットフォーム上に構築されたいくつかの機能があり、データを最大限に活用できます。

Adobe Experience Platformを使用すると、あらゆるシステムから顧客データとコンテンツを一元管理し、データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を改善できます。 プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。 プラットフォームについて詳しくは、「 [Adobe Experience Platform Architecture Overview](https://www.adobe.io/apis/experienceplatform/home/overview.html)」を参照してください。

データ取り込みからSQLへの直接アクセスに至るまで、エクスペリエンスプラットフォームのいくつかのコンポーネントは、Customer Jarney Analyticsの中心となり、これと連携して動作します。

* [クエリサービス](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): 標準SQLを使用して、アドビのソリューションデータ、お客様のファーストパーティデータ、その他のプラットフォームデータなど、Adobe Experience Platformからデータを取得します。 これは、任意のデータセットを結合し、クエリ結果を新しいデータセットとして取り込み、レポート、Data Science Workspaceで使用したり、プロファイルサービスに取り込んだりするための、サーバーレスのツールです。 クエリサービスを使用してデータ分析のエコシステムを構築し、様々なインタラクションチャネルにわたる消費者の画像を作成できます。 これらのチャネルには、POS（販売時点管理システム）、Web、モバイル、CRMなどが含まれます。
* [リアルタイム顧客プロファイル](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [ID サービス](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) （「開発者」オプション）: Adobe Experience Platformの事前設計された人工知能(AI)と機械学習モデルを使用して、顧客の遍歴の様々なポイントに影響を与えることができます。 隠れたインサイトを把握することで、顧客の遍歴を通じてより良い予測を行ったり、推奨される次のステップを提案したり、面倒なプロセスを自動化したりできます。
