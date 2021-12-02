---
title: Customer Journey Analytics の概要
description: どのように Customer Journey Analytics を使用すれば、Experience Platform からのデータと共に Analysis Workspace を使用できるかを説明します。
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
source-git-commit: 69ded6c9d08981810f6d9edef273cad95cb2c367
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 97%

---

# Customer Journey Analytics の概要

Customer Journey Analytics は、Adobe Experience Platform のデータを使用して Analysis Workspace を活用できる Analytics の機能です。数年分のデータを分類、フィルタリング、クエリ、視覚化でき、あらゆる種類のデータスキーマやデータの種類を保持できる Platform の機能と組み合わせることができます。**Experience Data Model（XDM）**&#x200B;を使用すると、データを均等に表示および整理し、組み合わせや調査に対応できます。**エクスペリエンスクエリサービス**：SQL 互換のツールとフレームワークを使用して、すべてのデータをクエリし、操作できます。

CJA の概要アーキテクチャを次に示します。

![アーキテクチャ](assets/cja-architecture.png)

## CJA と従来の Adobe Analytics の比較

Customer Journey Analytics では、使いやすいクロスチャネル機能を提供し、以前のバージョンの Adobe Analytics の制限を取り除くことで、Analytics の範囲を広げます。主な改善点を次に示します。

* **変数とイベントは無制限**：eVar、prop、イベントの概念は存在しなくなりました。データは主にディメンションと指標に焦点を当てています。データセットは、一意のディメンションと指標の数に制限はありません。
* **無制限の一意の値**：Adobe Experience Platform では、一意制限を受けることはありません。
* **履歴データの変更**：Adobe Experience Platform を使用して、データを削除または修正できます。
* **クロスレポートスイートデータ**：Platform で、複数のデータセットから既存の実装を組み合わせることができます。

Customer Journey Analytics の最初のリリースには、Analysis Workspace に含まれる多くの機能が含まれています。完全なリストについては、「[Customer Journey Analytics 機能のサポート](cja-aa.md)」を参照してください。

## CJA とクロスデバイス分析の比較

[クロスデバイス分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ja)：Adobe Experience Platform Identity Service と統合して、Co-op Graph またはプライベートグラフを活用し、デジタルデバイスをどのように人物にマッピングするかを特定します。Adobe Analytics Ultimate のお客様が利用できます。

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

* Customer Journey Analytics にアクセスしたり接続したりするには、[Admin Console](https://adminconsole.adobe.com/enterprise/) で **Customer Journey Analytics 製品**&#x200B;に管理者として追加される必要があります。 製品管理者には、次の権限が付与されます。
   * 接続またはデータ表示の作成／更新／削除をおこなう
   * 他のユーザーが作成したプロジェクト、フィルター、計算指標、フィルターの更新／削除を行います。
   * Workspace プロジェクトをすべてのユーザーと共有する
* 接続の作成、更新、削除を行うのに、Customer Journey Analytics内だけでは製品管理者になることは十分ではありません。 Experience Platform データセットへの接続を作成するには、Experience Platform 権限も必要です。特に、**Experience Platform 製品プロファイル**&#x200B;の一部であり、次の権限が与えられていることが必要です。
   * スキーマの表示
   * スキーマの管理
   * データセットの表示
   * データセットの管理
   * ソースの管理

Experience Platform 権限について詳しくは、「[Adobe Experience Platform のアクセス制御](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)」を参照してください。

>[!NOTE]
>
>従来の Adobe Analytics の場合とは異なり、Customer Journey Analytics 内の個々の指標やディメンションに権限を設定することはできません。 指標とディメンションはデータビューで変更できるため、CJA で変更される可能性があり、レポートも遡って変更されます。

### ユーザーアクセス

Customer Journey Analytics の非製品管理者（ユーザー）は、データビューや接続は表示できませんが、フィルター、プロジェクトおよび計算指標を作成できます。

## 用語の更新

CJA のいくつかの機能は、従来の Adobe Analytics の機能に比べ、業界標準に合わせて名前が変更されました。更新された用語の一部には、以下が含まれます。

* セグメントは「フィルター」になりました。
* 仮想レポートスイートは、「データビュー」と呼ばれるようになりました。
* 分類は、「参照データセット」になりました。
* 顧客属性は、「プロファイルデータセット」になりました。
* ヒットコンテナは、「イベント」コンテナになりました。
* 訪問コンテナは、「セッション」コンテナになりました。
* 訪問者コンテナは、「ユーザー」コンテナになりました。

## Adobe Experience Platform で構築されたその他の機能

Customer Journey Analytics は、Adobe Experience Platform に依存する多数の機能の 1 つです。Experience Platform には他にも、データを最大限に活用できる複数の機能が備わっています。

Adobe Experience Platform を使用すると、顧客データとコンテンツを任意のシステムから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされた豊富なエクスペリエンスのデザインと配信を大幅に改善できます。プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。プラットフォームについて詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.html)を参照してください。

データ取り込みから SQL への直接アクセスに至るまで、Experience Platform のいくつかのコンポーネントが Customer Journey Analytics の中心となり、これらは連携して動作します。

* [クエリサービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/query/home.html)：標準 SQL を使用して、Adobe Experience Platform からデータ（Adobe ソリューションデータ、お客様のファーストパーティデータ、その他の Platform データなど）を取得します。あらゆるデータセットを結合し、クエリ結果を新しいデータセットとして取り込んでレポートや Data Science Workspace で使用したり、プロファイルサービスに取り込んだりできる、サーバーレスのツールです。クエリサービスを使用してデータ分析のエコシステムを構築し、様々なインタラクションチャネルをまたいだ消費者の全体像を把握できます。これらのチャネルには、POS（販売時点管理システム）、Web、モバイル、CRM などが含まれます。
* [リアルタイム顧客プロファイル](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)：
* [ID サービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/home.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md)：
* [Data Science Workspace](https://docs.adobe.com/content/help/ja-JP/experience-platform/data-science-workspace/home.html)（「開発者」オプション）：Adobe Experience Platform にあらかじめ組み込まれた人工知能（AI）および機械学習モデルを使用して、カスタマージャーニーの様々なポイントに影響を与えることができます。隠れたインサイトを把握することで、カスタマージャーニーを通じてより優れた予測をおこなったり、推奨される次のステップを提案したり、面倒なプロセスを自動化したりできます。
