---
title: Adobe Analyticsからの進化
description: Adobe Analytics データを Customer Journey Analytics データに変換する手順
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 4dcf9ab808475cc3cc48cab4c076b6c3cfb66f8a
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 79%

---

# Adobe Analytics からの進化

## 既存のデータの準備

Customer Journey Analytics にシームレスに移行するために Adobe Analytics データを準備することは、データの整合性とレポートの一貫性を保つうえできわめて重要です。

### ID の収集

カスタマージャーニーを理解するうえで最も重要な要素は、各ステップで顧客が誰であるかを把握することです。Customer Journey Analytics の場合、すべてのチャネルとそれに対応するデータに存在する識別子を持つことで、Customer Journey Analytics 内で複数のソースを結び付ける（ステッチする）ことができます。
ID の例としては、顧客 ID、アカウント ID、メール ID などがあります。ID（場合によっては複数の ID）に関係なく、ID ごとに次の点を必ず考慮してください。

* ID は Customer Journey Analytics に取り込むすべてのデータソースに存在する、または追加できます。
* ID はデータの各行に設定されます。
* ID に PII は含まれていません。機密性が高い可能性のあるすべての要素にはハッシュを適用します。
* ID は、すべてのソース（同じ長さ、同じハッシュメソッドなど）で同じ形式を使用します。

Adobe Analytics などのデータセットでは、データの必ずしもすべての行に ID が存在するわけではなく、セカンダリ ID が存在する場合があります。このような場合は、顧客が ECID でのみ識別される場合の行と ID が収集される場合（例えば、顧客の認証時）の行とのギャップを埋めるために、[ クロスチャネル分析（ステッチとも呼ばれます） ](/help/stitching/overview.md) を使用できます。

### 変数の整合

Adobe Analytics のデータを Customer Journey Analytics のデータに変換する最も簡単な方法は、[Analytics ソースコネクタ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)を使用して[グローバルレポートスイート](https://experienceleague.adobe.com/ja/docs/analytics/implementation/prepare/global-rs)を Experience Platform に取り込むことです。このコネクタは、Adobe Analytics 変数を Experience Platform の XDM スキーマとデータセットに直接マッピングします。これらは Customer Journey Analytics に簡単に接続できます。

グローバルレポートスイートすべてを完全に実装することが現実的ではない場合があります。複数のレポートスイートを Customer Journey Analytics に取り込むには、次の 2 つのオプションがあります。

* 事前にこれらのレポートスイート間で変数の整合性を取っておく。例えば、レポートスイート 1 の eVar1 が[!UICONTROL ページ]を指し、レポートスイート 2 の eVar1 が[!UICONTROL 内部キャンペーン]を指している場合を考えてみましょう。Customer Journey Analyticsに取り込むと、これらの変数が 1 つのeVar1 ディメンションに混ざってしまうので、わかりにくく不正確なレポートになる可能性があります。

* [データ準備](https://experienceleague.adobe.com/ja/docs/experience-platform/data-prep/home)機能を使用して、変数をマッピングします。すべてのレポートスイートで共通の変数設計を使用していれば便利ですが、Experience Platform に新しく導入された[データ準備](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)機能を使用する場合、共通の変数設計は不要です。この新機能により、データストリーム（またはプロパティ）レベルでマッピングされた値を使用して変数を参照できます。

[!UICONTROL ユニーク数超過]または[!UICONTROL 低トラフィック]の問題が原因でグローバルレポートスイートへの移行を避けた場合は、Customer Journey Analytics には[ディメンションの基数の制限](/help/components/dimensions/high-cardinality.md)がないことを知っておいてください。これにより、どのような一意の値でも出現可能かつカウントできます。

次に、[レポートスイートと様々なスキーマの組み合わせ](/help/use-cases/aa-data/combine-report-suites.md)に関するユースケースを示します。

### マーケティングチャネルの（再）設定

従来の Adobe Analytics マーケティングチャネル設定は、Customer Journey Analytics では同じようには行われません。次の 2 つの理由により違いがあります。

* Adobe Experience Platform に取り込まれる Adobe Analytics データの処理レベル。

* Customer Journey Analytics のレポート時間の特性

アドビでは、[マーケティングチャネルの実装に関する最新のベストプラクティス](https://experienceleague.adobe.com/ja/docs/analytics/components/marketing-channels/mchannel-best-practices)を公開しています。これらの最新の推奨事項は、高度なアトリビューション機能を使用して既にAdobe Analyticsにある機能を最大限に活用するのに役立ちます。 また、Customer Journey Analyticsへの移行を成功させるための設定も行っています。

また、Customer Journey Analytics データビューの一部として[派生フィールド](../data-views/derived-fields/derived-fields.md)を導入したことにより、[マーケティングチャネル関数テンプレート](../data-views/derived-fields/derived-fields.md#function-templates)を使用した非破壊的かつ遡及的な方法でマーケティングチャネルもサポートされます。

## Customer Journey Analytics への移行時の重大な違いの準備

Customer Journey Analytics への移行に際しては、データ準備の手順を確認し、2 つのテクノロジー間の重要な違いを認識しておく必要があります。この記事は管理者を対象として書かれています。

### レポート時の処理を使いこなす {#report-time}

Adobe Analytics のレポートは、[!UICONTROL eVar] に見られる永続性などの成果を生み出すために、大量のデータの事前処理に依存しています。これに対して、Customer Journey Analytics は、レポートの実行時にこれらの計算を実行します。

[!UICONTROL レポート時の処理]では、基になるデータの収集方法を変更しなくても、遡及的な設定を適用でき、変数の永続性のバージョンを複数作成できるようになります。

この変更により、特に、有効期限が長くなる可能性のある変数について、データのレポート方法に多少の違いが生じます。 [仮想レポートスイート](https://experienceleague.adobe.com/ja/docs/analytics/components/virtual-report-suites/vrs-report-time-processing)を使用して、レポート時の処理がレポートにどのように影響するかを評価することから始めることができます。

### 重要なセグメントと計算指標の特定 {#segments-calcmetrics}

Adobe Analytics セグメントおよび計算指標は、Customer Journey Analytics と互換性がありません。多くの場合は、使用可能な新しいスキーマとデータを使用して、Customer Journey Analytics でこれらのコンポーネントを再構築できます。

ユーザーがシステム間を移行する際に作業ができるだけスムーズに進むように、次のことを行って前もって計画しておきます。

1. これらのコンポーネントのうち最も重要なものを特定する。

2. 定義をドキュメント化する。

3. データに必要なフィールドを特定し、それらを [ セグメント ](/help/components/segments/seg-overview.md) および [ 計算指標 ](/help/components/calc-metrics/calc-metr-overview.md) としてCustomer Journey Analyticsにレプリケートする。

次に、ガイドとなるビデオをいくつか示します。

* [Adobe Analytics セグメントの Customer Journey Analytics への移動](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=ja)

* [Adobe Analytics から Customer Journey Analytics への計算指標の移行](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics)

### その他の考慮事項

* Customer Journey Analytics データビューの機能を利用すると、Customer Journey Analytics 内で指標とディメンションをはるかに柔軟に定義できます。例えば、ディメンションの値を使用して指標の定義を作成できます。[詳細情報](/help/use-cases/data-views/data-views-usecases.md)

* Adobe Analyticsでカスタムカレンダーを定義した場合、Customer Journey Analytics内にも同様の [ カスタムカレンダー機能 ](/help/components/date-ranges/overview.md) があります。 カレンダーが正しく定義されていることを確認してください。

* Customer Journey Analyticsでは、カスタムセッションタイムアウトを定義できるほか、新しいセッションを開始する指標も定義できます。 様々なセッション定義でデータビューを作成して、Adobe Analytics で可能な範囲を超えるインサイトを得ることができます。この機能は、モバイルデータセットで特に役に立つ可能性があります。

* ユーザーに対してデータ要素を提供することを検討します。 または、SDR を拡張してスキーマ要素のExperience Platform フィールド名を含めます。

### 次の手順

Customer Journey Analytics に移行した後、データの相違に気付いた場合は、元の Adobe Analytics データと、現在 Customer Journey Analytics にある Adobe Analytics データを比較できます。[詳細情報](/help/troubleshooting/compare.md)
