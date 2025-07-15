---
title: Marketo Engage データに関するレポート
description: Customer Journey AnalyticsでMarketo Engage データをレポートする方法を説明します
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 82aefce30834d6400d338896dc1968e37596393e
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 14%

---

# Marketo Engage データに関するレポート

Experience Platformで利用可能なMarketo Engage データセットを活用して、B2B マーケターに価値のある分析およびレポートソリューションを提供できます。 次に、Customer Journey Analyticsでこれらのデータセットについてレポートします。

次の点に注意してください。

* Marketo Engage レポートは、Marketoで直接マーケティングプログラムを測定および最適化するのに最適で、迅速で、規範的で、マーケターに適しています。
* カスタマージャーニー分析は、Marketo データを含む（ただし、これに限定されない）、複数のチャネル、製品、ビジネスユニットにまたがるカスタマージャーニーに対して、より広範でカスタマイズ可能な分析ソリューションを提供します。

詳しくは、[ レポートの比較 ](#reporting-comparison) を参照してください。

>[!NOTE]
>
>Marketo Engage データからより多くの価値を得るには [0&rbrace;Customer Journey Analytics B2B edition&rbrace; を検討する必要があります。 ](/help/getting-started/cja-b2b-edition.md)Marketo Engage データセットを、アカウントデータセットおよびルックアップデータセットと組み合わせることができます。 さらに、Customer Journey Analytics B2B editionにおけるアカウントと商談のレベルについてもレポートします。
>


Customer Journey AnalyticsでMarketo Engageの日付をレポートするには：

+++ &#x200B;1. Marketo ソースデータフィールドの XDM ターゲットへのマッピング

[人物](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo)および[アクティビティ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo)オブジェクトを、対応する XDM スキーマのターゲットフィールドにマッピングします。

+++

+++ &#x200B;2. Marketo データのAdobe Experience Platformへの取り込み

[Marketo Engage コネクタ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo)を使用して、Marketo から Experience Platform にデータを取り込み、プラットフォームに接続したアプリケーションを使用してこのデータを最新に維持します。

+++

+++ &#x200B;3. Customer Journey Analyticsでこのデータセットへの接続を設定する

Experience Platform データセットに関するレポートを作成するには、まずExperience PlatformとCustomer Journey Analyticsのデータセット間で接続を確立する必要があります。 [ 接続の作成または編集 ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection) を参照してください。

+++


+++ &#x200B;4. 1 つ以上のデータビューを作成する

[データビュー](/help/data-views/data-views.md)は、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。Analysis Workspace で使用可能なすべてのディメンションおよび指標（この場合、Marketo に特有の指標およびディメンション）を指定します。また、それらのディメンションや指標がどの列からデータを取得するかも指定します。データビューは、Analysis Workspace でのレポート作成の準備の際に定義します。

+++

+++ 5.Analysis Workspaceにおける報告

1 つのユースケースとして、2020 年 4 月～6 月のリードによる web ページ訪問数を検討してみます。

1. [Analytics Workspace](/help/analysis-workspace/home.md) を開いて、新しいプロジェクトを作成します。B2B/B2P CDP のお客様は、Customer Journey Analyticsで B2C スタイルの分析を実施できます。 B2B オブジェクトは、まだ使用できません。

1. 次のように、web ページビュー用に [segment](/help/components/segments/seg-create.md) を作成します。- Event Type = web.webpagedetails.pageViews :

   ![ イベントとイベントタイプを表示する定義ウィンドウ ](../assets/marketo-filter.png)

1. 作成したセグメントをフリーフォームテーブル - Web ページビューに取り込み、月の日付範囲を取り込みます。 このアクションにより、毎月のリードによる web ページ訪問数がわかります。

   ![ イベントを月別に表示したフリーフォームテーブル。](../assets/marketo-freeform.png)

1. または、人物キーまたは仕事用メールアドレスのディメンションを取り込みます。このアクションにより、各リードによる web ページ訪問数がわかります。

   ![ イベントおよび workEmail.Address ビューと Web ページビューを表示するフリーフォームテーブル ](../assets/marketo-freeform2.png)

Customer Journey AnalyticsのMarketo Engage データは、Marketo Engageのレポートに表示される内容と異なる場合があります。

+++


## レポートの比較

Customer Journey AnalyticsとMarketo Engageのレポートの次の比較では、分析の機能、柔軟性、情報源、ユースケースのいくつかの重要な違いについて詳しく説明します。

### Customer Journey Analytics

Customer Journey Analyticsは、Adobe Experience Platform上に構築された高度なクロスチャネル分析ツールです。 Customer Journey Analyticsは、デジタルデータソースとオフラインデータソースをまたいで、強力で柔軟かつカスタマイズ可能なレポートを必要とする大規模法人チーム向けに設計されています。

#### 主な機能

* **データソース**：複数のデータセット（web、CRM、メール、コールセンター、オフライン、Marketoなど）を組み合わせて、360 度のカスタマージャーニーレポートを作成できます。
* **セルフサービス分析**：インタラクティブ性が高く、カスタマイズ可能なダッシュボードとビジュアライゼーションを使用したワークスペースをドラッグ&amp;ドロップします。
* **高度なアトリビューション**：マーケティングプログラムだけでなく、接続されたすべてのデータにわたって、複雑なマルチタッチのカスタムアトリビューションモデルをサポートします。
* **オーディエンスとパス分析**：バイヤージャーニーをまたいだディープセグメント化、コホート、パス分析。
* **実用的なインサイト**：データ駆動型のオーケストレーションを有効にします（例えば、マーケティングやパーソナライゼーションエンジンにインサイトを送り返します）。
* **企業規模**：エンタープライズガバナンス、複数のブランド、大量のデータを必要とする組織に適しています。

#### Customer Journey Analyticsの典型的なユースケース

* 複数のチャネルとタッチポイントにわたる高度なカスタマージャーニーマッピング。
* オンラインデータとオフラインデータの複雑なセグメント化およびブレンド。
* エグゼクティブレベルおよび運用レポート用のカスタム KPI ダッシュボード。
* 全体的なアトリビューションモデリング（デジタルまたはメールのみの場合を除く）。


### Marketo Engage

Marketo Engageは、マーケティングの自動処理 KPI、プログラムとキャンペーンの測定、マーケティングの影響分析に重点を置いたアプリ内レポートを提供します。 これらのレポートはすべて、Marketo内のアクティビティに直接関連しています。

#### 主な機能

* **ネイティブマーケティング分析**：メール、ランディングページ、キャンペーン、リード、商談、パイプライン、収益属性（ファーストタッチ、ラストタッチ、マルチタッチ）の標準レポート。
* **高度な BI 分析（アドオン）**：プログラム、アカウント、リードデータを分析するためのカスタムレポートビルダーをドラッグ&amp;ドロップでポイント&amp;クリックします（最近の高度な BI 分析の概要を参照）。
* **事前に作成されたダッシュボード**：キャンペーンのパフォーマンス、チャネルの有効性、パイプライン/売上高の貢献度のために。
* **プログラムとチャネル分析**:Marketoが管理するジャーニーに固有のアトリビューションと ROI。
* **マーケティング中心**：メール統計、フォーム、スマートキャンペーン、収益への影響など、マーケティングファネルに対する透明性を必要とするユーザーに焦点を当てています。


#### Marketo Engageの典型的なユースケース

* メール、プログラム、キャンペーンのパフォーマンスのトラッキングと最適化。
* リードおよびパイプラインをマーケティング戦術に関連付けます。
* エンゲージメントのトレンドを監視し、リードを獲得します。
* データエンジニアリングリソースなしで、販売/マーケティングチームとインサイトを共有します。
* すぐに使えるマーケターにとってわかりやすいレポートにアクセスします。


Marketo EngageとCustomer Journey Analyticsのレポート機能の簡単な比較表については、以下を参照してください。

| 機能 | Marketo Engage | Customer Journey Analytics |
|---|---|---|
| **プライマリのフォーカス** | マーケティングプログラムとキャンペーン中心のレポート。 | 総合的なオムニチャネルジャーニーと行動分析およびレポート。 |
| **データソース** | Marketo Engage内および経由で生成されたデータ。 | Marketo、web サイト、モバイルアプリ、オフラインチャネルなど、Experience Platformを使用した任意のデータを組み合わせます。 |
| **アトリビューション** | Marketo データに対するシングルタッチおよびマルチタッチのアトリビューション。 | ソリューション内で使用可能な任意のデータに対するカスタムのクロスチャネル属性。 |
| **カスタムレポートと柔軟性** | プログラムおよびアカウントの高度な BI （アドオン）について詳しく説明します。 | 使用可能なすべてのデータを使用して、カスタムワークスペース、ダッシュボードまたはレポートを作成する方法について、非常に柔軟です。 |
| **オーディエンス分析** | プログラムリスト、エンゲージメントおよびスマートリストのフィルタリングとセグメント化。 | リッチペルソナとジャーニーのビジュアライゼーション、オーディエンスパス、セグメントの重複分析。 |
| **対象ユーザー** | マーケター、マーケティングオペレーター、需要創出ワーカー、収益管理者。 | アナリスト、データサイエンティスト、マーケティングストラテジスト、カスタマーエクスペリエンスの専門家。 |
