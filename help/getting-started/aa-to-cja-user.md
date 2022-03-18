---
title: Adobe Analyticsユーザー向け CJA ユーザーガイド
description: 会社がAdobe AnalyticsからCustomer Journey Analyticsにデータを移動する際に、ユーザーの観点から考慮すべき事項
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 24a6319b1303eaef80ddf6142deae60e7f664ae4
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 25%

---


# Adobe Analyticsユーザー向け CJA ユーザーガイド

>[!NOTE]
>
>このページは作成中です。

おめでとうございます。会社がCustomer Journey Analyticsを始めました。 Adobe Analyticsをご利用のお客様には、すでに優れた優れたスタートを切っています。 Customer Journey Analyticsを扱う際には、いくつかの大きな違いといくつかの類似点に気が付くでしょう。 このページでは、まだ変更がない点と、主な違いについて説明します。 また、新しい概念に関するより多くの情報を得る方法や、カスタマージャーニーをより簡単かつ成功に導くためのさらなる手順についても説明します。

## 変更されていないもの

レポート側での使い慣れた内容の多くは変更されていません。 引き続き、Analysis Workspaceの機能を利用してデータを分析できます。 また、同じバージョンのAdobe Analyticsダッシュボードを任意で使用できます。 Workspace とダッシュボードは、基本的に従来のAdobe Analyticsと同じように機能します。 Report Builderは新しいインターフェイスを備え、PC、Macコンピューター、および Excel の Web バージョンで動作するようになりました。 レポートでは、様々なクロスチャネルデータにアクセスして分析できます。 次に、一部のマルチチャネルビジュアライゼーションの例を示します。

![マルチチャネル](assets/cross-channel.png)

## 新しいアーキテクチャ

Customer Journey AnalyticsはAdobe Experience Platformからデータを取得します。 Experience Platformを使用すると、顧客データとコンテンツを任意のシステムまたはチャネルから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を改善できます。

プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。プラットフォームについて詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)を参照してください。

CJA 管理者が確立しました。 [接続](/help/connections/create-connection.md) を Platform のデータセットに追加します。 その後、 [データビュー](/help/data-views/data-views.md) 接続内で データビューは、仮想レポートスイートと似ています。 データビューは、Customer Journey Analyticsのレポートの基礎です。

## 新しい概念と用語

CJA のいくつかの機能は、従来のAdobe Analyticsと比較して、業界標準に合わせて名前が変更され、再構築されました。 更新された用語には、セグメント、仮想レポートスイート、分類、顧客属性、コンテナ名などがあります。 eVar や prop などの慣れ親しんだ概念は、課せられた制限と共に存在しなくなりました。

### eVar と prop

従来の Adobe Analytics の [!UICONTROL eVar]、[!UICONTROL prop] および[!UICONTROL イベント]は、[!UICONTROL Customer Journey Analytics] にはもう存在しません。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。

### セグメントは「フィルター」になりました

[!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存のセグメントの中で、 [!UICONTROL Customer Journey Analytics]. さらに、「セグメント」の名前が「フィルター」に変更されました。

当面の間、共有/公開できません [!UICONTROL フィルター] ([!UICONTROL セグメント]から ) [!DNL Customer Journey Analytics] を統合プロファイルまたは他のExperience CloudアプリケーションにExperience Platformします。 この機能は現在開発中です。

### 計算指標

[!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存の計算指標に対して [!UICONTROL Customer Journey Analytics].

### セッションと変数の持続性の設定

[!UICONTROL Customer Journey Analytics] では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。

### 仮想レポートスイートが「データビュー」になりました



### 分類は、「参照データセット」になりました。

### 顧客属性が「プロファイルデータセット」になりました。


### ヒットコンテナが「イベント」コンテナになりました。

### 訪問コンテナは、「セッション」コンテナになりました

### 訪問者コンテナは、「ユーザー」コンテナになりました

### `Uniques Exceeded` 制限

[!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。
