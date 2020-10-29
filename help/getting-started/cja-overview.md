---
title: Customer Journey Analytics の概要
description: どのように Customer Journey Analytics を使用すれば、Experience Platform からのデータと共に Analysis Workspace を使用できるかを説明します。
translation-type: ht
source-git-commit: f52a6788a0a5f3aea23fc783e479c3f8a23a260d
workflow-type: ht
source-wordcount: '1229'
ht-degree: 100%

---


# Customer Journey Analytics の概要

Customer Journey Analytics は、Adobe Experience Platform のデータを使用して Analysis Workspace を活用できる Analytics の機能です。数年分のデータを分類、フィルタリング、クエリ、視覚化でき、あらゆる種類のデータスキーマやデータの種類を保持できる Platform の機能と組み合わせることができます。**Experience Data Model（XDM）**&#x200B;を使用すると、データを均等に表示および整理し、組み合わせや調査に対応できます。**エクスペリエンスクエリサービス**：SQL 互換のツールとフレームワークを使用して、すべてのデータをクエリし、操作できます。

## CJA と従来の Adobe Analytics の比較

Customer Journey Analytics では、使いやすいクロスチャネル機能を提供し、以前のバージョンの Adobe Analytics の制限を取り除くことで、Analytics の範囲を広げます。主な改善点を次に示します。

* **変数とイベントは無制限**：eVar、prop、イベントの概念は存在しなくなりました。データは主にディメンションと指標に焦点を当てています。データセットは、一意のディメンションと指標の数に制限はありません。
* **ユニーク値は無制限**：Adobe Experience Platform は、従来のレポートスイートの 500,000 個のユニーク値など、ユニーク値の制約には縛られません。
* **履歴データの変更**：Adobe Experience Platform を使用して、データを削除または修正できます。
* **クロスレポートスイートデータ**：Platform で、複数のデータセットから既存の実装を組み合わせることができます。

Customer Journey Analytics の最初のリリースには、Analysis Workspace に含まれる多くの機能が含まれています。完全なリストについては、「[Customer Journey Analytics 機能のサポート](cja-aa.md)」を参照してください。

## CJA とクロスデバイス分析の比較

[クロスデバイス分析](https://docs.adobe.com/content/help/ja-JP/analytics/components/cda/cda-home.html)：Adobe Experience Platform Identity Service と統合して、Co-op Graph またはプライベートグラフを活用し、デジタルデバイスをどのように人物にマッピングするかを特定します。Adobe Analytics Ultimate のお客様が利用できます。

その一方、CJA は、Adobe Experience Platform のデータセットと統合され、Analysis Workspace でのクロスチャネル分析を可能にします。CJA はまだ Co-op またはプライベート ID グラフとは統合されていませんが、bring-your-own-ID（個人 ID の持ち込み）によってデータセットを結合できます。また、これらのデータセットには、デジタルデータだけでなく、オンラインとオフラインの両方のタッチポイントを含めることができます。CJA の前提条件について詳しくは、以下を参照してください。

## 主な使用例

Customer Journey Analytics では、次のことが可能です。

* **ジャーニーのコンテキストと照らし合わせて顧客を把握する**：複数のチャネルにまたがるデータを、順番に表示および分析できます。コールセンター、POS システム、オンラインプロパティのデータを、1 つのレポートビューに組み合わせることができます。
* **誰でもインサイトを利用可能**：データアクセスを民主化し、多くの人がデータに基づいたインサイトを活用してよりビジネス上の意思決定おこなえるようにします。顧客体験のあらゆる側面を取り扱う組織に所属するすべてのメンバーが、より完全なデータに基づいて、実際の意思決定を迅速に下すことができます。
* **データアナリスト向けデータサイエンスの機能を活用**：Customer Journey Analytics を使用すると、専門家でなくてもデータサイエンスを活用して、深いインサイトと分析を解き放つことができます。
* **アドホックレポートを使用してデータセットの視覚化や操作をおこなう**：Workspace では、いくつかの基本的なルールに準拠した Adobe Experience Platform のデータセットを使用できます。
* **Web 以外の表示データ**：Workspace は、「ヒット」または「イベント」の厳密な定義に制限されなくなりました。カスタムスキーマでは、データと定義を完全に制御できます。
* **データ操作をより詳細に制御**：アップロードしたデータの変更、新しいデータセットの作成、Workspace への読み込みをおこないます。Adobe Experience Platform は、Experience Cloud クエリサービスを通じて、ツールのクエリ、抽出、変換および読み込みをおこないます。

## 前提条件

Customer Journey Analytics の使用を開始する前に、次の前提条件を満たす必要があります。

* 組織が、Adobe Analytics（Select、Prime または Ultimate）および Customer Journey Analytics アドオンのアクティブな契約を結んでいる。契約の種類が不明な場合や、CJA アドオンがあるかどうかが不明な場合は、組織のアカウントマネージャーにお問い合わせください。
* 組織が Adobe Experience Platform 用にプロビジョニングされている。

## 管理者アクセス権限

接続を作成したり、データセットを追加したりするには、[Admin Console](https://adminconsole.adobe.com/enterprise/) で次の権限が必要です。

* 2020 年 9 月 9 日現在、Customer Journey Analytics にアクセスする、または接続するには、[Admin Console](https://adminconsole.adobe.com/enterprise/) コンソールの **Customer Journey Analytics 製品**&#x200B;に管理者として追加されている必要があります。製品管理者には、次の権限が付与されます。
   * 接続またはデータ表示の作成／更新／削除をおこなう
   * 他のユーザーが作成したプロジェクト、フィルター、計算指標、セグメントの更新／削除をおこなう
   * Workspace プロジェクトをすべてのユーザーと共有する
* 接続の作成、更新、削除をおこなうためには、Customer Journey Analytics 単体の製品管理者であることは十分ではありません。Experience Platform データセットへの接続を作成するには、Experience Platform 権限も必要です。特に、**Experience Platform 製品プロファイル**&#x200B;の一部であり、次の権限が与えられていることが必要です。
   * スキーマの表示
   * スキーマの管理
   * ID 名前空間の表示
   * データセットの表示

Experience Platform 権限について詳しくは、「[Adobe Experience Platform のアクセス制御](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)」を参照してください。

### ユーザーアクセス

Customer Journey Analytics の非製品管理者（ユーザー）は、データビューや接続は表示できませんが、フィルター、プロジェクトおよび計算指標を作成できます。

## 用語の更新

CJA のいくつかの機能は、従来の Adobe Analytics の機能に比べ、業界標準に合わせて名前が変更されました。更新された用語の一部には、以下が含まれます。

* セグメントは「フィルター」になりました。
* 仮想レポートスイートは、「ビュー」になりました。
* 分類は、「参照データセット」になりました。
* 顧客属性は、「プロファイルデータセット」になりました。
* ヒットコンテナは、「イベント」コンテナになりました。
* 訪問コンテナは、「セッション」コンテナになりました。
* 訪問者コンテナは、「ユーザー」コンテナになりました。

## Adobe Experience Platform で構築されたその他の機能

Customer Journey Analytics は、Adobe Experience Platform に依存する多数の機能の 1 つです。Experience Platform には他にも、データを最大限に活用できる複数の機能が備わっています。

Adobe Experience Platform を使用すると、顧客データとコンテンツを任意のシステムから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされた豊富なエクスペリエンスのデザインと配信を大幅に改善できます。プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。プラットフォームについて詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.translate.html)を参照してください。

データ取り込みから SQL への直接アクセスに至るまで、Experience Platform のいくつかのコンポーネントが Customer Journey Analytics の中心となり、これらは連携して動作します。

* [クエリサービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/query/home.translate.html)：標準 SQL を使用して、Adobe Experience Platform からデータ（Adobe ソリューションデータ、お客様のファーストパーティデータ、その他の Platform データなど）を取得します。あらゆるデータセットを結合し、クエリ結果を新しいデータセットとして取り込んでレポートや Data Science Workspace で使用したり、プロファイルサービスに取り込んだりできる、サーバーレスのツールです。クエリサービスを使用してデータ分析のエコシステムを構築し、様々なインタラクションチャネルをまたいだ消費者の全体像を把握できます。これらのチャネルには、POS（販売時点管理システム）、Web、モバイル、CRM などが含まれます。
* [リアルタイム顧客プロファイル](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)：
* [ID サービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md)：
* [Data Science Workspace](https://docs.adobe.com/content/help/ja-JP/experience-platform/data-science-workspace/home.translate.html)（「開発者」オプション）：Adobe Experience Platform にあらかじめ組み込まれた人工知能（AI）および機械学習モデルを使用して、カスタマージャーニーの様々なポイントに影響を与えることができます。隠れたインサイトを把握することで、カスタマージャーニーを通じてより優れた予測をおこなったり、推奨される次のステップを提案したり、面倒なプロセスを自動化したりできます。
