---
title: Adobe Analyticsユーザー向け CJA ユーザーガイド
description: 会社がAdobe AnalyticsからCustomer Journey Analyticsにデータを移動する際に、ユーザーの観点から考慮すべき事項
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 30e02f8865daea5d0f6a669f84714abec25ecd76
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 8%

---

# Adobe Analyticsユーザー向け CJA ユーザーガイド

組織がCustomer Journey Analyticsの採用を開始している場合は、従来の Analytics と CJA に似ている点と違いに気が付くかもしれません。 このページでは、組織を新しい実装およびレポートワークフローに適合させるために、これらの違いについて説明します。 また、このページでは、新しい概念に関する追加のリソースと、アナリストとしてのジャーニーをより簡単かつ成功に導くための手順についても説明します。

CJA のいくつかの機能は、業界標準に合わせて名前が変更され、再設計されています。 更新された用語には、セグメント、仮想レポートスイート、分類、顧客属性、コンテナ名などがあります。 柔軟なカスタムディメンションおよび指標を考慮して、eVar と prop の制限は存在しなくなりました。

## 変更されていないもの

レポート側での使い慣れた内容の多くは変更されていません。

* 引き続き、 [Analysis Workspace](/help/analysis-workspace/home.md) を使用してデータを分析します。 Workspace は、従来のAdobe Analyticsと同じように動作します。
* 同じバージョンの [Adobe Analyticsダッシュボード](/help/mobile-app/home.md) は使用可能で、CJA と従来の Analytics の間で同様に機能します。
* [Report Builder](/help/report-builder/report-buider-overview.md) には、PC、Mac、および Web バージョンの Excel で動作する新しいインターフェイスがあります。

## レポートの変更点

分析するために、より多くのクロスチャネルデータにアクセスできます。 例えば、複数のチャネルのパフォーマンスを分析するワークスペースプロジェクトを作成できます

![マルチチャネルビジュアライゼーション](assets/cross-channel.png)

## データアーキテクチャの変更 {#architecture}

Customer Journey AnalyticsはAdobe Experience Platformからデータを取得します。 Experience Platformを使用すると、顧客データとコンテンツを任意のシステムまたはチャネルから一元管理し、データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を改善できます。

プラットフォーム内の顧客データは、スキーマとデータのバッチで構成されるデータセットとして保存されます。プラットフォームについて詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)を参照してください。

CJA 管理者が設定します。 [接続](/help/connections/create-connection.md) を Platform のデータセットに追加します。 その後、 [データビュー](/help/data-views/data-views.md) これらの接続を使用します。 データビューは概念的には仮想レポートスイートと似ており、Customer Journey Analyticsのレポートの基礎です。 Platform はレポートのすべてのデータをソースするので、レポートスイートはデータのコンテナとして存在しなくなりました。

接続を使用すると、Analytics 管理者は、 [!DNL Adobe Experience Platform] into [!UICONTROL Customer Journey Analytics]を次のビデオに含めます。

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobeでは、Adobe Analyticsソースコネクタや Web SDK を使用したレポートスイートデータなど、複数の方法でAdobe Experience Platformにデータを取り込むことができます。 Platform で、複数のレポートスイートから既存の実装を組み合わせることができます。 これらのデータセットに基づく接続とデータビューは、別々のレポートスイートに以前存在したデータを組み合わせることができます。

## 仮想レポートスイートの概念の変更 {#data-views}

[!UICONTROL データビュー] 仮想レポートスイートの概念を現在の状態から取り上げ、 [データに対する追加の制御を有効にする](/help/data-views/create-dataview.md) 接続で使用可能になりました。 これらの変更により、タイムゾーンやセッションのタイムアウト間隔などの一般的な設定が設定可能になり、遡及的になります。 アトリビューションや有効期限などの個々の変数設定は、レポートレベルまたはデータビューレベルでカスタマイズすることもできます。 これらの設定は、非破壊的および遡及的です。

右上のレポートスイートセレクターで、利用可能なデータビューから選択できるようになりました。

![data-view-selector](assets/data-views.png)

詳しくは、 [データビューに関する使用例](/help/data-views/data-views-usecases.md) を参照してください。

## eVar および prop の概念の変更

[!UICONTROL eVar], [!UICONTROL prop]、および [!UICONTROL イベント] 従来のAdobe Analyticsでは、もはや存在しない [!UICONTROL Customer Journey Analytics]. ディメンション、指標、リストフィールドなど、使用できるスキーマ要素は無制限です。 データ収集プロセス中に以前適用されたすべてのアトリビューション設定が、クエリ時に適用されるようになりました。

## セグメントの概念の変更

Adobeでは、業界標準に合わせて、Adobe Experience Platformのセグメントとの区別を改善するために、「セグメント」コンポーネントの名前を「フィルター」に変更しました。\

[!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに、Platform スキーマ要素を使用します。 この変更は、既存のセグメントの中で、との互換性がないことを意味します。 [!UICONTROL Customer Journey Analytics]. 既存のAdobe AnalyticsセグメントをCustomer Journey Analyticsに移動する場合は、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

まだ共有または公開できませんが [!UICONTROL フィルター] ([!UICONTROL セグメント]から ) [!DNL Customer Journey Analytics] Experience Platform統合プロファイルに対して、この機能は開発中です。

セグメントの変更の概念に加えて、セグメントコンテナも更新されます。

* **ヒットコンテナが「イベント」コンテナになりました。**. [!UICONTROL 個人] コンテナには、指定した期間内の訪問者に対するすべてのセッションとイベントが含まれます。
* **訪問コンテナは、「セッション」コンテナになりました**. [!UICONTROL セッション]コンテナでは、特定のセッションのページインタラクション、キャンペーンまたはコンバージョンを識別できます。
* **訪問者コンテナが [!UICONTROL 人物] コンテナ**. [!UICONTROL 個人] コンテナには、指定した期間内の訪問者に対するすべてのセッションとイベントが含まれます。

## 計算指標の概念の変更

計算指標は、従来の Analytics と CJA では同様に名前が付けられています。 しかし、 [!UICONTROL Customer Journey Analytics] は、eVar、prop またはイベントを使用しなくなりました。代わりに、Platform スキーマ要素を使用します。 この基本的な変更は、既存の計算指標に対して、 [!UICONTROL Customer Journey Analytics]. Adobe Analyticsの計算指標をCustomer Journey Analyticsに移行する場合は、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## 変数の属性と有効期限の設定の変更

[!UICONTROL Customer Journey Analytics] は、レポート時に、アトリビューションと有効期限を含むすべての変数設定を適用します。 これらの設定は、現在は、 [データビュー](/help/data-views/component-settings/persistence.md)また、一部の変数設定（アトリビューションなど）は、Workspace プロジェクトで変更できます。

同じデータビューで、同じ変数の複数のバージョンを持つことができます。 例えば、30 日後に期限切れになるトラッキングコードディメンションと、セッションの終わりに期限切れになるトラッキングコードディメンションを設定できます。 これらのトラッキングコードディメンションは両方とも同じソースデータを使用しますが、異なるアトリビューション設定を使用します。

また、同じ接続に基づいて複数のデータビューを持つこともできます。 例えば、あるデータビューのセッションタイムアウトが 30 分の場合と、別のデータビューのセッションタイムアウトが 15 分の場合があります。 両方のデータビューが右上のセレクターに表示されるので、シームレスに切り替えることができます。

## 分類の概念の変更

「分類」は、「ルックアップデータセット」になりました。 ルックアップデータセットは、イベントまたはプロファイルデータにある値やキーを検索するために使用されます。 例えば、イベントデータ内の数値 ID を製品名にマッピングするルックアップデータをアップロードできます。詳しくは、 [アカウントレベルのデータをルックアップデータセットとして追加](/help/use-cases/b2b.md) を参照してください。

## 顧客属性の概念の変更

「顧客属性」は、「プロファイルデータセット」になりました。 プロファイルデータセットには、 [!UICONTROL イベント] データ。 例えば、顧客に関する CRM データをアップロードできます。 含める個人 ID を選択できます。で定義された各データセット [!DNL Experience Platform] には、1 つ以上のユーザー ID セットが定義されています。

## 訪問者の識別方法の変更Adobe

CJA は、ECID 以外に ID の概念を拡張し、顧客 ID、Cookie ID、関連付け ID、ユーザー ID、トラッキングコードなど、使用する ID を含めます。 データセット全体で共通の名前空間 ID を使用する、またはを使用する [クロスチャネル分析](/help/connections/cca/overview.md) は、異なるデータセットをまたいで人々をリンクするのに役立ちます。 CJA で Workspace プロジェクトを設定するユーザーは、データセット全体で使用される ID を理解する必要があります。 Customer Journey Analyticsでの ID の使用について重点的に説明している次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## 「低トラフィック」ディメンション項目の概念の変更

従来の Analytics では、一意の値を受け取りすぎる変数が、次の場所にディメンション項目をグループ化し始めます。 `Low-Traffic`. Customer Journey Analyticsには、基数の高いフィールドに対して多くの制限があります。 レポートアーキテクチャが変更され、Analysis Workspaceは、より多くの一意のディメンション項目に関するレポートを作成できます。 詳しくは、 [ロングテール](../analysis-workspace/workspace-faq/long-tail.md) を参照してください。
