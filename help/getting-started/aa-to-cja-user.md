---
title: Adobe Analyticsユーザー向け CJA ユーザーガイド
description: 会社がAdobe AnalyticsからCustomer Journey Analyticsにデータを移動する際に、ユーザーの観点から考慮すべき事項
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: fcd178add387cc79dabecace3fa1f84bd64c904f
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 18%

---


# Adobe Analyticsユーザー向け CJA ユーザーガイド

>[!NOTE]
>
>このページは作成中です。

貴社が雇用Customer Journey Analyticsを開始します。 Adobe Analyticsに詳しいユーザーは、すでに優れた優れたスタートを切っています。 Customer Journey Analyticsを扱う際には、いくつかの大きな違いといくつかの類似点に気が付くでしょう。 このページでは、まだ変更がない点と、主な違いについて説明します。 また、新しい概念に関するより多くの情報を得る方法や、カスタマージャーニーをより簡単かつ成功に導くためのさらなる手順についても説明します。

## 変更されていないもの

レポート側での使い慣れた内容の多くは変更されていません。

* 引き続き、 [Analysis Workspace](/help/analysis-workspace/home.md) を使用してデータを分析します。 Workspace は、従来のAdobe Analyticsと同じように機能します。
* 同じバージョンの [Adobe Analyticsダッシュボード](/help/mobile-app/home.md) あなたの好きなように ダッシュボード (Mobileアプリ ) は、従来のAdobe Analyticsと同じように機能します。
* [Report Builder](/help/report-builder/report-buider-overview.md) は新しいインターフェイスを備え、PC、Mac、Web 版の Excel で動作するようになりました。

レポートに関しては、分析するために、より多くのクロスチャネルデータにアクセスできる点が異なります。 クロスチャネルのデータソースを含むいくつかのビジュアライゼーションの例を次に示します。

![マルチチャネルビジュアライゼーション](assets/cross-channel.png)

## 新しいアーキテクチャ

Customer Journey AnalyticsはAdobe Experience Platformからデータを取得します。 Experience Platformを使用すると、顧客データとコンテンツを任意のシステムまたはチャネルから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を改善できます。

プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。プラットフォームについて詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)を参照してください。

CJA 管理者が確立しました。 [接続](/help/connections/create-connection.md) を Platform のデータセットに追加します。 その後、 [データビュー](/help/data-views/data-views.md) 接続内で データビューは、仮想レポートスイートと似ています。 データビューは、Customer Journey Analyticsのレポートの基礎です。 レポートスイートの概念は存在しなくなりました。

## 新しい概念と用語

CJA のいくつかの機能は、従来のAdobe Analyticsと比較して、業界標準に合わせて名前が変更され、再構築されました。 更新された用語には、セグメント、仮想レポートスイート、分類、顧客属性、コンテナ名などがあります。 eVar や prop などの慣れ親しんだ概念は、課せられた制限と共に存在しなくなりました。

## （仮想）レポートスイートが「データビュー」になりました。

[!UICONTROL データビュー] 仮想レポートスイートの概念を現在の状態から取り上げ、 [データに対する追加の制御を有効にする](/help/data-views/create-dataview.md) 接続で使用可能になりました。 これにより、タイムゾーンとセッションのタイムアウト間隔を設定できるようになります。 また、個々のディメンションにアトリビューションプロパティと有効期限プロパティを動的に適用することもできます。 これらは、すべてのデータに遡って適用されます。

**必要な操作**:

* Workspace では、以前使用していたレポートスイートセレクターを使用して、管理者が共有しているデータビューから選択できるようになりました。

   ![data-view-selector](assets/data-views.png)

* 多くの [データビューに関する使用例](/help/data-views/data-views-usecases.md).

## eVar および prop は追加されなくなりました

従来の Adobe Analytics の [!UICONTROL eVar]、[!UICONTROL prop] および[!UICONTROL イベント]は、[!UICONTROL Customer Journey Analytics] にはもう存在しません。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。CJA 管理者がデータビューを作成しました。

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


## クロスレポートスイートデータ

複数のデータセットから既存の実装を組み合わせることができます。Experience Platform これらのデータセットに基づく接続とデータビューは、別々のレポートスイートに以前存在したデータを組み合わせることができます。

**必要な操作**:

## セッションと変数の持続性の設定

[!UICONTROL Customer Journey Analytics] は、レポート時にこれらのすべての設定を適用し、これらの設定は [データビュー](/help/data-views/component-settings/persistence.md). これらの設定に対する変更が遡及的になり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。

**必要な操作**:

## 分類は、「参照データセット」になりました。



## 顧客属性が「プロファイルデータセット」になりました。


## コンテナの名前が変更されました

次のコンテナを指定します。 [作成するすべてのデータビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).
* **ヒットコンテナが「イベント」コンテナになりました。**. [!UICONTROL 個人] コンテナには、指定した期間内の訪問者に対するすべてのセッションとイベントが含まれます。
* **訪問コンテナは、「セッション」コンテナになりました**. [!UICONTROL セッション]コンテナでは、特定のセッションのページインタラクション、キャンペーンまたはコンバージョンを識別できます。
* **訪問者コンテナが [!UICONTROL 人物] コンテナ**. [!UICONTROL 個人] コンテナには、指定した期間内の訪問者に対するすべてのセッションとイベントが含まれます。

**必要な操作**:

組織のニーズに合わせて任意のコンテナの名前を変更することもできます。


## `Uniques Exceeded` 制限

[!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。
