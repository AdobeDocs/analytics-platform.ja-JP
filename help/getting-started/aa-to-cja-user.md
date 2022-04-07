---
title: Adobe Analyticsユーザー向け CJA ユーザーガイド
description: 会社がAdobe AnalyticsからCustomer Journey Analyticsにデータを移動する際に、ユーザーの観点から考慮すべき事項
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 570fb36de0ed81f001ed6115e73d1d4347f368ec
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 21%

---

# Adobe Analyticsユーザー向け CJA ユーザーガイド

あなたの会社はCustomer Journey Analyticsを採用し始めている。 Adobe Analyticsに詳しいユーザーは、すでに優れた優れたスタートを切っています。 Customer Journey Analyticsを扱う際には、いくつかの類似点といくつかの大きな違いに気が付くでしょう。 このページでは、まだ変更がない点と、主な違いについて説明します。 また、新しい概念に関するより多くの情報を得る方法や、カスタマージャーニーをより簡単かつ成功に導くためのさらなる手順についても説明します。

CJA のいくつかの機能は、従来のAdobe Analyticsと比較して、業界標準に合わせて名前が変更され、再構築されました。 更新された用語には、セグメント、仮想レポートスイート、分類、顧客属性、コンテナ名などがあります。 eVar や prop などの慣れ親しんだ概念は、課せられた制限と共に存在しなくなりました。

## 変更されていないもの

レポート側での使い慣れた内容の多くは変更されていません。

* 引き続き、 [Analysis Workspace](/help/analysis-workspace/home.md) を使用してデータを分析します。 Workspace は、従来のAdobe Analyticsと同じように機能します。
* 同じバージョンの [Adobe Analyticsダッシュボード](/help/mobile-app/home.md) あなたの好きなように ダッシュボード (Mobileアプリ ) は、従来のAdobe Analyticsと同じように機能します。
* [Report Builder](/help/report-builder/report-buider-overview.md) は新しいインターフェイスを備え、PC、Mac、Web 版の Excel で動作するようになりました。

報告に関して言えば **相違点** は、分析する多くのクロスチャネルデータにアクセスできることを示しています。 クロスチャネルのデータソースを含むいくつかのビジュアライゼーションの例を次に示します。

![マルチチャネルビジュアライゼーション](assets/cross-channel.png)

## 新しいアーキテクチャ {#architecture}

Customer Journey AnalyticsはAdobe Experience Platformからデータを取得します。 Experience Platformを使用すると、顧客データとコンテンツを任意のシステムまたはチャネルから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を改善できます。

プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。プラットフォームについて詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)を参照してください。

CJA 管理者が確立しました。 [接続](/help/connections/create-connection.md) を Platform のデータセットに追加します。 その後、 [データビュー](/help/data-views/data-views.md) 接続内で データビューは、仮想レポートスイートと似ています。 データビューは、Customer Journey Analyticsのレポートの基礎です。 レポートスイートの概念は存在しなくなりました。

## 接続

接続を使用すると、Analytics 管理者は、 [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. [!DNL Experience Platform] データセットに関するレポートを作成するには、まず [!DNL Experience Platform] と [!UICONTROL ワークスペース] のデータセット間で接続を確立する必要があります。

以下は、このトピックの概要に関するビデオです。

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## レポートスイート {#report-suites}

組織がまだAdobe Analyticsプラットフォームにいて、CJA/AEP を追加している場合、レポートスイートのデータは、Adobe Analytics Source Connector または Web SDK 経由でExperience Platformに取り込むことができます。 通常、Analytics スキーマを使用して、レポートスイートに固有のソースデータセットを使用します。

ただし、レポートスイートは、CJA でのレポートの基盤ではなくなりました。 [データビュー](/help/data-views/data-views.md) はです。 データビューについて詳しくは、以下の節を参照してください。

複数のデータセットから既存の実装を組み合わせることができます。Experience Platform これらのデータセットに基づく接続とデータビューは、別々のレポートスイートに以前存在したデータを組み合わせることができます。

## （仮想）レポートスイートが「データビュー」になりました。 {#data-views}

[!UICONTROL データビュー] 仮想レポートスイートの概念を現在の状態から取り上げ、 [データに対する追加の制御を有効にする](/help/data-views/create-dataview.md) 接続で使用可能になりました。 これにより、タイムゾーンとセッションのタイムアウト間隔を設定できるようになります。 また、個々のディメンションにアトリビューションプロパティと有効期限プロパティを動的に適用することもできます。 これらは、すべてのデータに遡って適用されます。

**必要な操作**:

* Workspace では、以前使用していたレポートスイートセレクターを使用して、管理者が共有しているデータビューから選択できるようになりました。

   ![data-view-selector](assets/data-views.png)

* 多くの [データビューに関する使用例](/help/data-views/data-views-usecases.md).

## eVar と prop

従来の Adobe Analytics の [!UICONTROL eVar]、[!UICONTROL prop] および[!UICONTROL イベント]は、[!UICONTROL Customer Journey Analytics] にはもう存在しません。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。

**必要な操作**:

* これらのスキーマ要素を使用してデータを詳細に分析する方法について詳しく説明します。

## セグメントは「フィルター」になりました

[!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存のセグメントの中で、 [!UICONTROL Customer Journey Analytics]. さらに、「セグメント」の名前が「フィルター」に変更されました。

当面の間、共有/公開できません [!UICONTROL フィルター] ([!UICONTROL セグメント]から ) [!DNL Customer Journey Analytics] を統合プロファイルまたは他のExperience CloudアプリケーションにExperience Platformします。 この機能は現在開発中です。

**必要な操作**:

* 既存のAdobe AnalyticsセグメントをCustomer Journey Analyticsに移動する場合は、「 [このビデオ](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=ja).
* それ以外の場合は、Customer Journey Analyticsでフィルターを再作成します。

## 計算指標

[!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存の計算指標に対して [!UICONTROL Customer Journey Analytics].

**必要な操作**:

* Adobe Analyticsの計算指標をCustomer Journey Analyticsに移動する場合は、 [このビデオ](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=ja).
* それ以外の場合は、Customer Journey Analyticsで計算指標を再作成します。

## セッションと変数の持続性の設定

[!UICONTROL Customer Journey Analytics] は、レポート時にこれらのすべての設定を適用し、これらの設定は [データビュー](/help/data-views/component-settings/persistence.md). これらの設定に対する変更が遡及的になり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。

## 分類は、「参照データセット」になりました。

ルックアップデータセットは、イベントまたはプロファイルデータにある値やキーを検索するために使用されます。 例えば、イベントデータ内の数値 ID を製品名にマッピングするルックアップデータをアップロードできます。詳しくは、[この使用例](/help/use-cases/b2b.md)をご覧ください。

## 顧客属性が「プロファイルデータセット」になりました。

プロファイルデータセットには、 [!UICONTROL イベント] データ。 例えば、顧客に関する CRM データをアップロードできます。 含める個人 ID を選択できます。[!DNL Experience Platform] 内で定義される各データセットには、1 つ以上の個人 ID セット（Cookie ID、スティッチされた ID、ユーザー ID、トラッキングコードなど）があります。

## ID

CJA は、ECID 以外に ID の概念を拡張し、顧客 ID、Cookie ID、関連付け ID、ユーザー ID、トラッキングコードなど、使用する ID を含めます。 データセット全体で共通の名前空間 ID を使用する、またはを使用する [クロスチャネル分析](/help/connections/cca/overview.md) は、異なるデータセットをまたいで人々をリンクするのに役立ちます。 CJA で Workspace プロジェクトを設定するユーザーは、データセット全体で使用される ID を理解する必要があります。

次に、Customer Journey Analyticsでの ID の使用に関するビデオを示します。

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## コンテナの名前が変更されました

次のコンテナを指定します。 [作成するすべてのデータビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).

* **ヒットコンテナが「イベント」コンテナになりました。**. [!UICONTROL 個人] コンテナには、指定した期間内の訪問者に対するすべてのセッションとイベントが含まれます。
* **訪問コンテナは、「セッション」コンテナになりました**. [!UICONTROL セッション]コンテナでは、特定のセッションのページインタラクション、キャンペーンまたはコンバージョンを識別できます。
* **訪問者コンテナが [!UICONTROL 人物] コンテナ**. [!UICONTROL 個人] コンテナには、指定した期間内の訪問者に対するすべてのセッションとイベントが含まれます。

**必要な操作**:

組織のニーズに合わせて任意のコンテナの名前を変更することもできます。

## `Uniques Exceeded` 制限

[!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。
