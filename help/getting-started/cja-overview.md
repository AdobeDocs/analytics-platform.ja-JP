---
title: Customer Journey Analytics の概要
description: どのように Customer Journey Analytics を使用すれば、Experience Platform からのデータと共に Analysis Workspace を使用できるかを説明します。
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: dac10a1e4848514661bf06fe71d233da6f9aa878
workflow-type: tm+mt
source-wordcount: '980'
ht-degree: 97%

---

# Customer Journey Analytics の概要

Customer Journey Analytics は、Adobe Experience Platform のデータを使用して Analysis Workspace を活用できる Analytics の機能です。数年分のデータを分類、フィルタリング、クエリ、視覚化でき、あらゆる種類のデータスキーマやデータの種類を保持できる Platform の機能と組み合わせることができます。**Experience Data Model（XDM）**&#x200B;を使用すると、データを均等に表示および整理し、組み合わせや調査に対応できます。**エクスペリエンスクエリサービス**：SQL 互換のツールとフレームワークを使用して、すべてのデータをクエリし、操作できます。

CJA アーキテクチャの概要を次に示します。

![アークテクチャ](assets/cja-architecture.png)

次に、Customer Journey Analytics の概要ビデオを示します。

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## CJA と従来の Adobe Analytics の比較

Customer Journey Analytics では、使いやすいクロスチャネル機能を提供し、以前のバージョンの Adobe Analytics の制限を取り除くことで、Adobe Analytics の範囲を広げています。主な改善点を次に示します。

* **変数とイベントは無制限**：eVar、prop、イベントの概念は存在しなくなりました。データは主にディメンションと指標に焦点を当てています。データセットは、一意のディメンションと指標の数に制限はありません。
* **無制限の一意の値**：Adobe Experience Platform では、一意制限を受けることはありません。
* **履歴データの変更**：Adobe Experience Platform を使用して、データを削除または修正できます。
* **クロスレポートスイートデータ**：Platform で、複数のデータセットから既存の実装を組み合わせることができます。

>[!TIP]
>
>これまで Adobe Analytics を使用していて、Customer Journey Analytics で Adobe Analytics データを使用する必要がある場合は、[データ取り込み](../data-ingestion/data-ingestion.md)の節に含まれている[従来の Adobe Analytics からのデータの取り込みと使用](../data-ingestion/analytics.md)のクイックスタートガイドを参照してください。


Customer Journey Analytics の最初のリリースには、Analysis Workspace に含まれる多くの機能が含まれています。完全なリストについては、[Customer Journey Analytics 機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)を参照してください。

## 主なユースケース

Customer Journey Analytics では、次のことが可能です。

* **ジャーニーのコンテキストと照らし合わせて顧客を把握する**：複数のチャネルにまたがるデータを、順番に表示および分析できます。コールセンター、POS システム、オンラインプロパティのデータを、1 つのレポートビューに組み合わせることができます。
* **誰でもインサイトを利用可能**：データアクセスを民主化し、多くの人がデータに基づいたインサイトを活用してよりビジネス上の意思決定を行えるようにします。顧客体験のあらゆる側面を取り扱う組織に所属するすべてのメンバーが、より完全なデータに基づいて、実際の意思決定を迅速に下すことができます。
* **データアナリスト向けデータサイエンスの機能を活用**：Customer Journey Analytics を使用すると、専門家でなくてもデータサイエンスを活用して、深いインサイトと分析を解き放つことができます。
* **オンデマンドレポートを使用してデータセットの視覚化や操作を行う**：ワークスペースでは、いくつかの基本的なルールに準拠した Adobe Experience Platform のデータセットを使用できます。
* **Web 以外の表示データ**：ワークスペースは、「ヒット」または「イベント」の厳密な定義に制限されなくなりました。カスタムスキーマでは、データと定義を完全に制御できます。
* **データ操作をより詳細に制御**：アップロードしたデータの変更、データセットの作成、ワークスペースへの読み込みを行います。Adobe Experience Platform は、Experience Cloud クエリサービスを通じて、ツールのクエリ、抽出、変換および読み込みを行います。

## 前提条件

Customer Journey Analytics の使用を開始する前に、次の前提条件を満たす必要があります。

* 組織が、Adobe Analytics（Select、Prime または Ultimate）および Customer Journey Analytics アドオンのアクティブな契約を結んでいる。契約の種類が不明な場合や、CJA アドオンがあるかどうかが不明な場合は、Adobeのアカウントチームにお問い合わせください。
* 組織が Adobe Experience Platform 用にプロビジョニングされている。
* Adobe Analytics を必要とせずに、Customer Journey Analytics をスタンドアロン製品として購入することもできます。

## アクセス制御

[アクセス制御](/help/admin/cja-access-control.md)に関するトピックを参照してください。

## 用語の更新

CJA のいくつかの機能は、従来の Adobe Analytics の機能に比べ、業界標準に合わせて名前が変更されました。次に、更新された用語の一部を示します。

* セグメントは「フィルター」になりました。
* 仮想レポートスイートは、「データビュー」と呼ばれるようになりました。
* 分類は、「ルックアップデータセット」になりました。
* 顧客属性は、「プロファイルデータセット」になりました。
* ヒットコンテナは、「イベント」コンテナになりました。
* 訪問コンテナは、「セッション」コンテナになりました。
* 訪問者コンテナは、「人物」コンテナになりました。

## Adobe Experience Platform で構築されたその他の機能

Customer Journey Analytics は、Adobe Experience Platform に依存する多数の機能の 1 つです。Experience Platform には他にも、データを最大限に活用できる複数の機能が備わっています。

Adobe Experience Platform を使用すると、顧客データとコンテンツを任意のシステムから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされた豊富なエクスペリエンスのデザインと配信を大幅に改善できます。プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。Experience Platform について詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=ja)を参照してください。

データ取り込みから SQL への直接アクセスに至るまで、Experience Platform のいくつかのコンポーネントが Customer Journey Analytics の中心となり、補完します。

* [クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)：標準 SQL を使用して、Adobe Experience Platform からデータ（アドビのソリューションデータ、お客様のファーストパーティデータ、その他の Platform データなど）を取得します。あらゆるデータセットを結合し、クエリ結果を新しいデータセットとして取り込んでレポートや Data Science Workspace で使用したり、プロファイルサービスに取り込んだりできる、サーバーレスのツールです。クエリサービスを使用してデータ分析のエコシステムを構築し、様々なインタラクションチャネルをまたいだ消費者の全体像を把握できます。これらのチャネルには、POS（販売時点管理システム）、web、モバイル、CRM などが含まれます。
* [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)：
* [ID サービス](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja)：
* [Data Science Workspace](https://experienceleague.adobe.com/docs/experience-platform/data-science-workspace/home.html?lang=ja)（「開発者」オプション）：Adobe Experience Platform にあらかじめ組み込まれた人工知能（AI）および機械学習モデルを使用して、カスタマージャーニーの様々なポイントに影響を与えることができます。隠れたインサイトを把握することで、カスタマージャーニーを通じてより優れた予測を行ったり、推奨される次のステップを提案したり、面倒なプロセスを自動化したりできます。

## ビデオ

* Customer Journey Analytics でのデータの操作：

   >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Customer Journey Analytics のアーキテクチャと統合：

   >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

