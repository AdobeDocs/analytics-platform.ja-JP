---
title: Adobe Analytics から Customer Journey Analytics へのアップグレード
description: Adobe Analytics から Customer Journey Analytics へのアップグレード時に推奨される手順について説明します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bd19250e-91c0-49f6-b6dc-3abd641344aa
TQID: https://experienceleague.adobe.com/DtETa7Qh3l2X9YSjkX56zX8CmDTWVpGvvyrd9HFayt4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c4147b6e-073b-4d3c-9ab1-d60f2f4434efid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 1186
ht-degree: 15%

---

# Customer Journey Analytics にアップグレードする組織の準備

アップグレードを成功させる一環として、（[Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード ](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)で説明しているように）特定の運用上の考慮事項に焦点を当てて組織を準備します。 組織を準備するには、次のことをお勧めします。

* 主要な関係者からの同意と調整の獲得

* 目標の定義と文書化

* 現実的で思慮深いタイムラインを設定する

* 貢献者の明確な責任の定義

## 関係者の賛同と調整

組織の主要な関係者や意思決定者は、Customer Journey Analyticsへのアップグレードについて調整する必要があります。

次の節では、関係者の連携を得る方法について説明します。

### 価値に注力する

Customer Journey Analyticsが自社にもたらす価値と、ビジネス目標の達成をどのように加速させるのかに注目しましょう。

次の表では、注目すべき主な機能をいくつか示します。

| 機能 | 利点 | 例 |
|---------|----------|---------|
| **[あらゆる種類のデータの宿泊施設](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home)** | Customer Journey Analytics は、あらゆる種類のデータスキーマとタイプを保持する Experience Platform の機能と組み合わされています。 | 小売企業は、次のようなデータを単一の顧客像に統合することで、カスタマージャーニー全体を可視化することができます。 <ul><li>Web クリックストリームトランザクション</li><li>モバイルアプリトランザクション</li><li>実店舗での取引</li><li>CRM データとロイヤルティデータ</li></ul> |
| **[クロスチャネル分析](/help/use-cases/cross-channel/cross-channel.md)** | さまざまなweb、モバイル、オフラインのプロパティからのデータを統合することで、さまざまなチャネルをまたいで顧客行動を一元的に把握できます。 | 複数のチャネルからデータを収集する小売企業では、次のような分析を実行できます。<p>有料検索広告をクリックした買い物客は、オンラインでジーンズを閲覧し、プッシュ通知を受け取った後、2日後に店舗で購入しました。 この統合された視点により、正確なクロスチャネルアトリビューションが可能になり、デジタル接点が実店舗での販売にどのように貢献しているかを把握できます。 また、「オンラインで閲覧し、店舗で購入した」顧客に合わせたオファーを提供するなど、より正確なセグメンテーションにも対応しています。 さらに、あらゆるチャネルをまたいで単一のダッシュボードで明確な売上レポートを提供し、断片化され、分散しているインサイトを、顧客行動の全体像を把握するのに置き換えます。 |
| **[レポート時処理](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | データの収集方法を変更することなく、遡及的な設定を適用し、変数の永続性の複数のバージョンを作成できます。 | Customer Journey Analyticsでは、データを再取得または再処理することなく、指標、ディメンション、アトリビューションモデルを即座に作成および調整できるため、小売企業は、エンジニアリングにデータセットを再構築するように依頼することなく、最近のソーシャルキャンペーンがオンラインと実店舗の販売の両方にどのような影響を与えたのかを確認できます。 ファーストタッチからファーストタッチへ、またはルールベースのカスタムアトリビューションに至るまで、アトリビューションモデルを瞬時に変更できます。 |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | ビジネスが定義した主要業績評価指標（KPI）に対するコンテンツの影響をマーケターが理解するのに役立ちます。 Content Analytics では、行動データに加えて、消費されるコンテンツと、影響を与えるコンテンツに関するデータを収集します。 | web、アプリ、電子メール、店舗データなどを統合することで、制作するデジタルコンテンツの各要素が、カスタマージャーニーやコンバージョンにどのように貢献しているのかを正確に把握することができました。 <p>小売企業は、人気のあるソーシャルメディアプラットフォームに掲載された「夏のデニムスタイルガイド」が、ロイヤルティメンバーのエンゲージメントを高め、1週間以内に実店舗でデニムを購入する可能性が40%高いことがわかりました。</p> |

### エグゼクティブスポンサーを任命する

組織内のエグゼクティブスポンサーを見つけて任命します。 エグゼクティブスポンサーは、Customer Journey Analyticsがどのようにビジネス目標の達成を加速させるのかを理解する必要があります。

エグゼクティブスポンサーは次のように重要です。

* Adobe Customer Journey Analyticsの導入を支援します

* 障害の削除

* リソースの承認

### 組織全体の主要なリーダーからのサポートを確保したい

エグゼクティブスポンサーの助けを借りて、組織全体の主要なリーダーからのサポートを確保します。 次の領域のリーダーは、Customer Journey Analyticsの利点を理解し、導入を成功に導くことを望んでいることが重要です。

* Analytics

* マーケティング

* IT

* 法務とコンプライアンス

* それぞれの事業部

## アップグレードとコミュニケーション計画の策定

### アップグレード計画を作成し、関係者に配布する

アップグレードプランには、次の情報が含まれる場合があります。

* アップグレードが行われる理由を明確に説明します。 例えば、利用者と組織全体または企業全体にとっての利点を説明します。 利点について詳しくは、[価値に焦点を当てる](#focus-on-value)を参照してください。

* アップグレードの開始予定日、主要なマイルストーンの概要、アップグレードの完了予定日の見積りなど、一般的なタイムライン。

* Customer Journey Analyticsの使用方法を学ぶための公式トレーニングを受講できるタイミングを示します。 詳しくは、[組織全体でエンドユーザーをトレーニングする](#train-end-users-throughout-your-organization)を参照してください。

* 誰がアップグレードを主導しているのか、いつ、どのように質問することができるのかに関する情報。

### コミュニケーションプランの作成

コミュニケーション計画には、次のような考慮事項が含まれる場合があります。

* 関係者やユーザーにコミュニケーションを送信するタイミングを定義

* 送信される情報のタイプの概要

* コミュニケーションの送信者の計画

* 関係者やユーザーが質問したり、フィードバックを提供したりするためのフィードバックループを定義

## Adobe Analyticsの導入に関する評価と監査

Adobe Adobe Analyticsを導入する際は、次の点に重点を置いて徹底的な評価と監査を実施します。

* 現在のユーザー

* ユーザーアクセス

* プロジェクト

* ビジネスプロセス

* カスタムコンポーネント

この情報の収集に役立つ次のリソースを参照してください。

* [Analytics インベントリ](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/analytics-inventory)

  組織内のプロジェクト、セグメント、計算指標、レポートスイート、ユーザーの数に関する情報を提供します。

* [Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行の準備](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  コンポーネント、プロジェクト、ユーザーの移行に備える方法について説明します。

## 先進企業とアーリーアダプターを特定する

組織全体でチャンピオンを特定する： チャンピオンは以下の通りです。

* Adobe Analytics power users

* Customer Journey Analyticsですばやく熟達する能力

* Customer Journey Analyticsがより広範に展開されるため、他のユーザーへのサポートやコーチとして利用できます

## 組織全体でエンドユーザーをトレーニングする

* データモデル、レポートパラダイム、Customer Journey Analyticsの新機能の違いに焦点を当てた実践的なトレーニングを提供します。

* ライブセッション（ワークショップや営業時間）とオンデマンドリソース（ビデオチュートリアル、動的なWiki ページ、社内ドキュメント）の両方を提供します。

* Experience Leagueに関するトレーニング、チュートリアル、ドキュメントを提供します。

  次のリソースは、在庫管理に役立ちます。

   * [Customer Journey Analytics チュートリアル](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Customer Journey Analytics とは](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Customer Journey Analytics の概要](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Customer Journey Analytics の機能のサポート](/help/getting-started/aa-vs-cja/cja-aa.md)

## 推奨されるアップグレード手順に従います

アップグレード プロセスを開始する準備ができたら、[推奨されるアップグレード手順](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)またはCustomer Journey Analytics アップグレード ガイドの動的に生成されるアップグレード手順に従ってください。 Customer Journey Analytics からガイドにアクセスするには、「**[!UICONTROL Workspace]**」タブを選択し、左側のパネルで「**[!UICONTROL Customer Journey Analytics にアップグレード]**」を選択します。 画面の指示に従います。
