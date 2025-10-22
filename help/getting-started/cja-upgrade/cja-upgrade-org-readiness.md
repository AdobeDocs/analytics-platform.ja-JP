---
title: Adobe Analytics から Customer Journey Analytics へのアップグレード
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨される手順について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 7c0342a68f75774fd7b29979d3ce610f22d047ae
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 8%

---

# Customer Journey Analyticsにアップグレードするための準備

アップグレードを成功させるには（[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード &#x200B;](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) で説明しているように）、運用上の特定の考慮事項に焦点を当てて組織を準備する必要があります。 組織を準備するには、次の操作を実行することをお勧めします。

* 主要な関係者から賛同と調整を得る

* 目標の定義とドキュメント化

* 現実的で思慮深いタイムラインの設定

* コントリビューターに対する明確な責任の定義

## 関係者の賛同と連携

組織の主要な関係者や意思決定者は、Customer Journey Analyticsへのアップグレードで連携する必要があります。

次の節では、関係者の調整を得る方法について説明します。

### 価値に焦点を当てる

Customer Journey Analyticsがお客様にもたらす価値と、それがビジネス目標の達成をどのように促進するかについて重点的に説明します。

次の表では、重点的に取り上げたい主な機能をいくつか説明します。

| 機能 | 利点 | 例 |
|---------|----------|---------|
| **[各種データへの対応 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home)** | Customer Journey Analyticsは、Experience Platformの機能と組み合わされて、あらゆる種類のデータスキーマおよびデータタイプを保持します。 | 小売組織では、次の種類のデータを 1 つのビューに統合することで、カスタマージャーニー全体を可視化できます。 <ul><li>Web クリックストリームトランザクション</li><li>モバイルアプリのトランザクション</li><li>店舗内トランザクション</li><li>CRM とロイヤルティデータ</li></ul> |
| **[クロスチャネル分析](/help/use-cases/cross-channel/cross-channel.md)** | 様々な web、モバイル、オフラインのプロパティのデータを統合することで、様々なチャネルをまたいだ顧客の行動を 1 つの統合ビューで表示できます。 | 複数のチャネルからデータを収集している小売組織は、次のような分析を実行できます。<p>買い物客は、有料検索広告をクリックし、ジーンズをオンラインで閲覧し、プッシュ通知を受け取ると、2 日後に店舗で購入します。 この統一されたパースペクティブにより、正確なクロスチャネルアトリビューションが可能になり、デジタルタッチポイントが店舗の売上にどのように貢献するかを示します。 また、「オンラインで閲覧され、店頭で購入された」顧客をカスタマイズされたオファーでターゲティングするなど、より正確なセグメント化もサポートします。 さらに、1 つのダッシュボードで明確な全チャネルの売上高レポートを提供し、分断されたサイロ化されたインサイトを顧客の行動の全体像に置き換えます。 |
| **[レポート時の処理](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | 基になるデータの収集方法を変更しなくても、遡及的な設定を適用し、変数の永続性のバージョンを複数作成できます。 | Customer Journey Analyticsでは、データの再取り込みや再処理を行わなくても、指標、ディメンション、アトリビューションモデルをその場で作成および調整できるので、小売業者は、最近のソーシャルキャンペーンがオンラインと店舗の両方の売上にどのように影響したかを確認でき、データセットを再構築するようにエンジニアリングに依頼する必要はありません。 アトリビューションモデルをラストタッチからファーストタッチまたはカスタムルールベースのアトリビューションに即座に変更できます。 |
| **[コンテンツ分析](/help/content-analytics/content-analytics.md)** | マーケターが、コンテンツがビジネスが定義した主要業績評価指標にどのように影響するかを理解するのに役立ちます。 Content Analytics では、行動データに加えて、消費されるコンテンツと、影響を与えるコンテンツに関するデータを収集します。 | Web、アプリ、メール、さらには店舗データを統合することで、小売組織は、作成したデジタルコンテンツがカスタマージャーニーとコンバージョンにどのように貢献しているかを正確に確認できます。 <p>小売組織は、人気のあるソーシャルメディアプラットフォームの「夏のデニムスタイルガイド」がロイヤルティメンバーの高いエンゲージメントを促進し、これらのメンバーが 1 週間以内に店頭でデニムを購入する可能性が 40% 高いことを確認できます。</p> |

### エグゼクティブスポンサーを任命する

組織内でエグゼクティブスポンサーを見つけて任命します。 このエグゼクティブスポンサーは、Customer Journey Analyticsがビジネス目標の達成をどのように加速するかを理解する必要があります。

エグゼクティブスポンサーは、次の点で重要です。

* 組織内のチャンピオン Customer Journey Analytics

* 障害の削除

* リソースの承認

### 組織全体の主要なリーダーからのサポートを確保

エグゼクティブスポンサーの助けを借りて、組織全体の他の主要なリーダーからのサポートを確保します。 以下の分野のリーダーがCustomer Journey Analyticsのメリットを理解し、導入を成功に導く意欲があることを理解することが重要です。

* Analytics

* マーケティング

* 0.45111884

* 法務およびコンプライアンス

* 個々のビジネスユニット

## アップグレードとコミュニケーションのプランを作成

### アップグレード計画を作成し、関係者に配布します。

アップグレード計画には、次の情報が含まれる場合があります。

* アップグレードが行われる理由の明確な説明。 例えば、ユーザーにとってのメリットや、組織またはビジネス全体にとってのメリットを説明します。 この利点について詳しくは、[&#x200B; 価値に焦点を当てる &#x200B;](#focus-on-value) を参照してください。

* アップグレードの開始予定日、主要なマイルストーンの概要、アップグレードの完了予定日など、一般的なタイムライン。

* Customer Journey Analyticsの使用方法を学ぶための公式トレーニングを開始できるタイミングを示します。 詳しくは、[&#x200B; 組織全体でのエンドユーザーのトレーニング &#x200B;](#train-end-users-throughout-your-organization) を参照してください。

* アップグレードをリードするユーザーや、問い合わせをする方法またはタイミングに関する情報です。

### コミュニケーションプランの作成

通信計画には、次の考慮事項が含まれる場合があります。

* 関係者とユーザーにコミュニケーションを送信するタイミングの定義された頻度

* 送信される情報の種類の概要

* 通信を送信するユーザーの計画

* 関係者とユーザーが質問したり、フィードバックを提供したりできるように、定義されたフィードバックループ

## Adobe Analyticsの実装の評価と監査

次の主な領域に焦点を当てて、Adobe Analytics実装の徹底的な評価と監査を行います。

* 現在のユーザー

* ユーザーアクセス

* プロジェクト

* ビジネスプロセス

* カスタムコンポーネント

この情報の収集に役立つ以下のリソースを参照してください。

* [Analytics インベントリ](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/analytics-inventory)

  組織内のプロジェクト、セグメント、計算指標、レポートスイート、ユーザーの数に関する情報を提供します。

* [Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備 &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  コンポーネント、プロジェクト、およびユーザーの移行を準備する方法について説明します。

## チャンピオンと早期導入者の特定

組織全体でチャンピオンを特定します。 チャンピオンは次の通りです。

* Adobe Analytics パワーユーザー

* Customer Journey Analyticsに早く習熟できる

* Customer Journey Analyticsがより広く展開されるときに、他の人の助けやコーチとして利用できる

## 組織全体を通したエンドユーザーのトレーニング

* データモデルの違い、レポートパラダイム、Customer Journey Analytics内の新機能に重点を置いた実践トレーニングを提供します。

* ライブセッション（ワークショップまたは業務時間）とオンデマンドリソース（ビデオチュートリアル、動的な wiki ページ、内部ドキュメント）の両方を提供します。

* Experience Leagueに関連するトレーニング、チュートリアル、ドキュメントをユーザーに紹介します。

  作業を開始する際には、次のリソースが役立ちます。

   * [Customer Journey Analytics チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Customer Journey Analytics とは](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Customer Journey Analyticsの概要 &#x200B;](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Customer Journey Analytics の機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)

## 推奨されるアップグレード手順に従う

アップグレードプロセスを開始する準備が整ったら、『Customer Journey Analytics アップグレードガイド』の [&#x200B; 推奨されるアップグレード手順 &#x200B;](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) または動的に生成されるアップグレード手順に従います。 Customer Journey Analytics からガイドにアクセスするには、「**[!UICONTROL Workspace]**」タブを選択し、左側のパネルで「**[!UICONTROL Customer Journey Analytics にアップグレード]**」を選択します。画面の指示に従います。

