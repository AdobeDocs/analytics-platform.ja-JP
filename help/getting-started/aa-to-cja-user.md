---
title: Adobe Analyticsユーザー向け CJA ユーザーガイド
description: 会社がAdobe AnalyticsからCustomer Journey Analyticsにデータを移動する際に、ユーザーの観点から考慮すべき事項
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: eeb56599c81dd9cd20bf91c864aa57a783ef13fd
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 40%

---


# Adobe Analyticsユーザー向け CJA ユーザーガイド

おめでとうございます。会社は、少なくとも一部のデータをCustomer Journey Analyticsに移行しました。 Customer Journey Analyticsを使い始める際には、大きな違いといくつかの類似点に気が付くでしょう。 このページでは、まだ変更がない点と、主な違いについて説明します。

また、新しい概念に関するより多くの情報を得る方法や、カスタマージャーニーをより簡単かつ成功に導くためのさらなる手順についても説明します。

## 変更されていないもの

レポート側での使い慣れた内容の多くは変更されていません。 Analysis Workspaceの機能を活用してデータを分析し、さらにAdobe Analyticsのダッシュボードと新しいバージョンのReport Builderを分析できます。 Workspace とダッシュボードは、基本的に従来のAdobe Analyticsと同じように機能します。 Report Builderは新しいインターフェイスを備え、PC、Macコンピューター、および Excel の Web バージョンで動作するようになりました。 レポートでは、様々なクロスチャネルデータにアクセスして分析できます。 次に Workspace の例を示します。

## 新しいアーキテクチャ

アーキテクチャ上、Customer Journey AnalyticsはAdobe Experience Platformからデータを取得します。 Experience Platformを使用すると、顧客データとコンテンツを任意のシステムまたはチャネルから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を改善できます。

プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。プラットフォームについて詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)を参照してください。

CJA 管理者は、Platform のデータへの接続を確立し、それらの接続内にデータ表示を構築します。 データビューは、仮想レポートスイートと似ています。 データビューは、Customer Journey Analyticsのレポートの基礎です。

## 新しい概念と用語

CJA のいくつかの機能は、従来のAdobe Analyticsと比較して、業界標準に合わせて名前が変更され、再構築されました。 更新された用語には、セグメント、仮想レポートスイート、分類、顧客属性、コンテナ名などがあります。 eVar や prop などの慣れ親しんだ概念は、課せられた制限と共に存在しなくなりました。

### セグメントは「フィルター」になりました


### 仮想レポートスイートが「データビュー」になりました


### 分類は、「参照データセット」になりました。

### 顧客属性が「プロファイルデータセット」になりました。


### ヒットコンテナが「イベント」コンテナになりました。

### 訪問コンテナは、「セッション」コンテナになりました

### 訪問者コンテナは、「ユーザー」コンテナになりました

## Adobe Analyticsコンポーネントに関する FAQ

| 質問 | 回答 |
| --- | --- |
| [!UICONTROL フィルター]（[!UICONTROL セグメント]）を [!DNL Customer Journey Analytics] から Experience Platform 統合プロファイルまたは他の Experience Cloud アプリケーションに共有または公開することはできますか？ | 現在はできませんが、アドビではこの機能を提供できるように鋭意取り組んでいます。 |
| 以前の [!UICONTROL eVar] 設定はどうなりましたか？ | 従来の Adobe Analytics の [!UICONTROL eVar]、[!UICONTROL prop] および[!UICONTROL イベント]は、[!UICONTROL Customer Journey Analytics] にはもう存在しません。スキーマ要素（ディメンション、指標、リストフィールド）は無制限です。したがって、データ収集プロセスで適用したアトリビューション設定はすべて、クエリ時に適用されます。 |
| すべてのセッションと変数の永続性の設定は、どこにありますか。 | [!UICONTROL Customer Journey Analytics] では、報告時にこれらのすべての設定が適用され、これらの設定はデータビューに反映されます。これらの設定に対する変更が遡及的となり、複数のデータビューを使用して複数のバージョンを持つことができるようになりました。 |
| 既存のセグメント／計算指標はどうなりますか。 | [!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに AEP スキーマを使用します。つまり、既存のセグメントや計算指標には、いずれも [!UICONTROL Customer Journey Analytics] との互換性はありません。 |
| [!UICONTROL Customer Journey Analytics] での `Uniques Exceeded` 制限の処理方法を教えてください。 | [!UICONTROL Customer Journey Analytics] には一意の値に関する制限がないので、ご心配は不要です。 |
| 既存の [!DNL Data Workbench] のユーザーであれば、今すぐ [!UICONTROL Customer Journey Analytics] に移行できますか。 | ユースケースによって異なります。アドビアカウントチームにご相談ください。 お客様の現在のユースケースは、既に Customer Journey Analytics に適している可能性があります。 |
