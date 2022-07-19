---
title: Adobe Analytics から Customer Journey Analytics への進化
description: Adobe Analytics データを Customer Journey Analytics データに変換する手順
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 93690a3351f2dca0b3a68e7eea7fb64c581d2d53
workflow-type: ht
source-wordcount: '1333'
ht-degree: 100%

---

# Adobe Analytics から Customer Journey Analytics への進化

Customer Journey Analytics への移行に際しては、データ準備の手順を確認し、2 つのテクノロジー間の重要な違いを認識しておく必要があります。この記事は管理者を対象として書かれています。

## データの準備

Customer Journey Analytics にシームレスに移行するために Adobe Analytics データを準備することは、データの整合性とレポートの一貫性を保つうえできわめて重要です。

### 1. ID の収集 {#identities}

カスタマージャーニーを理解するうえで最も重要な要素は、各ステップで顧客が誰であるかを把握することです。Customer Journey Analytics の場合、すべてのチャネルとそれに対応するデータに存在する識別子を持つことで、CJA 内で複数のソースを結び付ける（ステッチする）ことができます。
ID の例としては、顧客 ID、アカウント ID、メール ID などがあります。ID（場合によっては複数の ID）に関係なく、ID ごとに次の点を必ず考慮してください。

* ID が存在するか、CJA に取り込むすべてのデータソースに ID を追加できます。
* ID はデータの各行に設定されます。
* ID に PII は含まれていません。機密性が高い可能性のあるすべての要素にはハッシュを適用します。
* ID は、すべてのソース（同じ長さ、同じハッシュメソッドなど）で同じ形式を使用します。

Adobe Analytics などのデータセットでは、データの必ずしもすべての行に ID が存在するわけではなく、セカンダリ ID が存在する場合があります。このような場合は、顧客が ECID でのみ識別される場合の行と ID が収集される場合（例えば、顧客の認証時）の行とのギャップを埋めるために、Cross-Channel Analytics（以前の「フィールドベースのステッチング」）を使用できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ja)

### 2. 変数の整合 {#variables}

Adobe Analytics のデータを Customer Journey Analytics のデータに変換する最も簡単な方法は、[Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を使用して[グローバルレポートスイート](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=ja)を Experience Platform に取り込むことです。このコネクタは、Adobe Analytics 変数を Experience Platform の XDM スキーマとデータセットに直接マッピングします。これらは Customer Journey Analytics に簡単に接続できます。

グローバルレポートスイートすべてを完全に実装することが現実的ではない場合があります。複数のレポートスイートを Customer Journey Analytics に取り込むには、次の 2 つのオプションがあります。

* 事前にこれらのレポートスイート間で変数の整合性を取っておく。例えば、レポートスイート 1 の eVar1 が[!UICONTROL ページ]を指し、レポートスイート 2 の eVar1 が[!UICONTROL 内部キャンペーン]を指している場合を考えてみましょう。このまま CJA に取り込むと、これらの変数が 1 つの eVar1 ディメンションに混ざってしまうので、わかりにくく不正確なレポートになる可能性があります。

* [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)機能を使用して、変数をマッピングする。すべてのレポートスイートで共通の変数設計を使用していれば便利ですが、Experience Platform に新しく導入された[データ準備](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja#mapping)機能を使用する場合、共通の変数設計は不要です。この新機能により、データストリーム（またはプロパティ）レベルでマッピングされた値を使用して変数を参照できます。

[!UICONTROL 超過したユニーク数]または[!UICONTROL 低トラフィック]の問題が原因でグローバルレポートスイートへの移行を避けた場合は、CJA には[ディメンションの基数の制限](/help/components/dimensions/high-cardinality.md)がないことを知っておいてください。これにより、任意の一意の値が出現可能でカウントもできます。

次に、[レポートスイートと様々なスキーマの組み合わせ](/help/use-cases/combine-report-suites.md)に関するユースケースを示します。

### 3.マーケティングチャネルの（再）設定 {#marketing-channels}

従来の Adobe Analytics マーケティングチャネル設定は、CJA では同じようには行われません。これは次の 2 つの理由があります。

* Adobe Experience Platform に取り込まれる Adobe Analytics データの処理レベル。

* Customer Journey Analytics のレポート時間の特性

アドビでは、[マーケティングチャネルの実装に関する最新のベストプラクティス](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=ja)を公開しています。これらの最新の推奨事項は、既に Adobe Analytics にある機能を Attribution IQ で最大限に活用するのに役立ちます。また、Customer Journey Analytics への移行を成功させるためのセットアップも行われます。

### 4. Analytics ソースコネクタと Experience Platform SDK のどちらを使用するかの決定 {#connector-vs-sdk}

[Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) データ収集が進化するにつれて、Adobe Experience Platform Edge Network を使用して [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=ja) か [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=ja) のいずれかに移行する可能性があります。SDK の一般的な実装ではデータが Adobe Analytics に送信されますが、Adobe Experience Platform にデータを直接送信する機会も新たに現れています。その後、Adobe Analytics に送信するデータも維持しながら、Customer Journey Analytics に取り込むことができます。

この方法により、データ収集の可能性が大幅に広がります。フィールド数の制限や、Analytics のようにデータ要素を prop、eVar、イベントにマッピングする必要がなくなりました。CJA [データビュー](/help/data-views/data-views.md)を使用すると、様々なタイプの無制限のスキーマ要素を使用し、それらを複数の方法で表すことができます。Adobe Experience Platform に直接送信すると、Adobe Analytics を介したデータ処理の時間が不要になるので、データの可用性が向上します。

**Experience Platform SDK を使用する場合の利点：**

* 必要なフィールドを何でも定義できる柔軟性がスキーマにあります
* Adobe Analytics の用語（prop、eVar、イベントなど）に依存しません
* 文字制限に関する問題がありません（prop の場合は 100 文字）
* Adobe Experience Platform でのデータの可用性が向上します

**Experience Platform SDK を使用する場合の欠点**

次の Adobe Analytics の機能またはコンポーネントはサポートされていません。

* マーケティングチャネル
* ボットフィルタリング
* 地域、ドメイン、デバイスのルックアップ
* Analytics for Target（A4T）

## 重要な違いに対する準備

### レポート時の処理を使いこなす {#report-time}

Adobe Analytics のレポートは、[!UICONTROL eVar] に見られる永続性などの成果を生み出すために、大量のデータの事前処理に依存しています。これに対して、Customer Journey Analytics は、レポートの実行時にこれらの計算を実行します。

[!UICONTROL レポート時の処理]では、基になるデータの収集方法を変更しなくても、遡及的な設定を適用でき、変数の永続性のバージョンを複数作成できるようになります。

この変更により、特に、有効期限が長くなる可能性のある変数について、データのレポート方法に多少の違いが生じます。[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ja)を使用して、レポート時の処理がレポートにどのように影響するかを評価することから始めることができます。

### 重要なセグメントと計算指標の特定 {#segments-calcmetrics}

Adobe Analytics セグメント（CJA では[!UICONTROL フィルター]と呼ばれます）および計算指標は、Customer Journey Analytics と互換性がありません。多くの場合は、使用可能な新しいスキーマとデータを使用して、CJA でこれらのコンポーネントを再構築できます。

ユーザーがシステム間を移行する際に作業ができるだけスムーズに進むように、次のことを行って前もって計画しておきます。

1. これらのコンポーネントのうち最も重要なものを特定する。

1. 定義をドキュメント化する。

1. データに必要なフィールドを特定し、それらを[フィルター](/help/components/filters/filters-overview.md)および[計算指標](/help/components/calc-metrics/calc-metr-overview.md)として CJA にレプリケートする。

次に、ガイドとなるビデオをいくつか示します。

* [Adobe Analytics セグメントの Customer Journey Analytics への移動](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=ja)

* [Adobe Analytics から Customer Journey Analytics への計算指標の移行](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=ja)

### その他の考慮事項

* CJA データビューの機能を利用すると、Customer Journey Analytics 内で指標とディメンションをはるかに柔軟に定義できます。例えば、ディメンションの値を使用して指標の定義を作成できます。[詳細情報](/help/data-views/data-views-usecases.md)

* Adobe Analytics でカスタムカレンダーを定義した場合、CJA 内でも同様の[カスタムカレンダー機能](/help/components/date-ranges/custom-date-ranges.md)を使用できます。カレンダーが正しく定義されていることを確認してください。

* Customer Journey Analytics では、カスタム訪問／セッションタイムアウトを定義でき、新しいセッションを開始する指標も定義できます。様々なセッション定義でデータビューを作成して、Adobe Analytics で可能な範囲を超えるインサイトを得ることができます。この機能は、モバイルデータセットで特に役に立つ可能性があります。

* ユーザーに対してデータディクショナリを提供するか、SDR を拡張してスキーマ要素の Experience Platform フィールド名を含めることを検討してください。

## 次の手順

CJA に移行した後、データの不一致に気付いた場合は、元の Adobe Analytics データと、現在 Customer Journey Analytics にある Adobe Analytics データを比較できます。[詳細情報](/help/troubleshooting/compare.md)
