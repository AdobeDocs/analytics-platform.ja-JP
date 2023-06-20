---
title: Adobe Analytics ユーザー向けユーザーガイド
description: 企業が Adobe Analytics から Customer Journey Analytics にデータを移行する際にユーザーの観点から考慮すべき事項
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1480'
ht-degree: 76%

---

# Adobe Analytics ユーザー向けユーザーガイド

お客様の組織がAdobe Customer Journey Analyticsの使用を開始している場合は、Adobe AnalyticsとCustomer Journey Analyticsの類似点と相違点に気付くかもしれません。 このページでは、この CJA の実装と新しいレポートワークフローに慣れるために、これらの相違点について説明します。また、新しい概念に関する追加のリソースを提供するほか、アナリストとしてのジャーニーをより簡単に成功させるための手順についても説明します。

Customer Journey Analyticsのいくつかの機能は、業界標準に合わせて名前が変更され、再設計されます。 更新された用語には、セグメント、仮想レポートスイート、分類、顧客属性、コンテナ名などがあります。カスタムディメンションおよび指標を柔軟に使用できるように、eVar と prop の制限は撤廃されました。

## 変更されていない点

レポート面で使い慣れた内容の多くは変更されていません。

* データ分析には、強力な [Analysis Workspace](/help/analysis-workspace/home.md) を引き続き使用できます。ワークスペースの動作は、従来の Adobe Analytics 内の動作と同じです。
* 同じバージョンの [Adobe Analyticsダッシュボード](/help/mobile-app/home.md) が使用可能で、Customer Journey AnalyticsとAdobe Analyticsの間で同様の機能を果たします。
* [Report Builder](/help/report-builder/report-buider-overview.md) には、MS Windows、macOS および Excel（web バージョン）で動作する新しいインターフェイスが用意されています（以前のバージョンの Report Builder は、VMware 上で実行しない限り、Mac 上では使用できませんでした）。ただし、このバージョンは、従来の AA データリクエストにはまだ対応していません。

## レポートの変更点

より多くのクロスチャネルデータにアクセスして分析できるようになりました。例えば、複数のチャネルのパフォーマンスを分析する Workspace プロジェクトを作成できます。たとえば、これらのデータセットが組織で取り込まれ、Customer Journey Analyticsが使用するデータビューに含まれる場合です（以下の「データアーキテクチャの変更」を参照）。

![マルチチャネルビジュアライゼーション](assets/cross-channel.png)

## データアーキテクチャの変更 {#architecture}

Customer Journey AnalyticsはAdobe Experience Platformからデータを取得します。 Experience Platform を使用すると、顧客データとコンテンツを、どのシステムまたはチャネルからでも一元管理および標準化できます。データサイエンスと機械学習を適用して、パーソナライズされたエクスペリエンスのデザインと配信を大幅に改善できます。

Experience Platform 内の顧客データは、[スキーマ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ja)とデータのバッチで構成されるデータセットとして保存されます。Experience Platform について詳しくは、[Adobe Experience Platform アーキテクチャの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=ja)を参照してください。

Customer Journey Analytics管理者が設定しています [接続](/help/connections/create-connection.md) をExperience Platform内のデータセットに追加します。 その後、この接続を使用して、[データビュー](/help/data-views/data-views.md)を作成します。データビューは概念的には仮想レポートスイートと似ており、Customer Journey Analyticsのレポートの基礎です。 レポートのすべてのデータは Experience Platform から提供されるので、レポートスイートはデータのコンテナとしては使用されなくなりました。

接続を使用すれば、Analytics 管理者は、次のビデオに含まれるAdobe Experience PlatformのデータセットをCustomer Journey Analyticsに統合できます。

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

アドビでは、Adobe Analytics ソースコネクタや Web SDK を使用したレポートスイートデータなど、Adobe Experience Platform にデータを取り込む方法を複数用意しています。複数のレポートスイートにある既存の実装を Experience Platform で組み合わせることもできます。これらのデータセットに基づく接続とデータビューは、別々のレポートスイートに以前存在したデータを組み合わせることができます。

## 仮想レポートスイートの概念の変更 {#data-views}

[!UICONTROL データビュー]は、現在の仮想レポートスイートの概念をさらに拡大するものです。接続で使用可能になる[データ](/help/data-views/create-dataview.md)を、さらに制御できるようになります。これらの変更により、タイムゾーンやセッションのタイムアウト間隔などの一般的な設定が、設定したり遡及したりできるようになりました。アトリビューションや有効期限などの個々の変数設定は、レポートレベルまたはデータビューレベルでカスタマイズすることもできます。これらの設定は、ノンデストラクティブ（非破壊的）であり遡及可能です。

右上のレポートスイートセレクターで、使用可能なデータビューから目的のデータビューを選択できるようになりました。

![データビューセレクター](assets/data-views.png)

詳しくは、[データビューに関するユースケース](/help/use-cases/data-views/data-views-usecases.md)を参照してください。

## eVar および prop の概念の変更

従来の Adobe Analytics の [!UICONTROL eVar]、[!UICONTROL prop] および[!UICONTROL イベント]の概念は、[!UICONTROL Customer Journey Analytics] には存在しません。Adobe Analytics では、eVar と prop によって、コンテンツや顧客、キャンペーンなどの説明が格納され、イベントによって、売上高やサブスクリプション、獲得したリードなどがカウントされます。Customer Journey Analytics では、両方のタイプのデータが保持され、Analysis Workspace の左パネルの「ディメンション」または「指標」から、同じ方法でアクセスできます。

Customer Journey Analyticsでは、ディメンション、指標、リストフィールドなど、無制限のスキーマ要素を使用できます。 これらは、Experience Platform 内のディメンション、指標、リストフィールドなど、無制限のスキーマ要素にマッピングされます。Adobe Analytics ではルールの処理後にすべての訪問およびアトリビューションの設定が適用されますが、Customer Journey Analytics ではクエリ時に適用されます。

この柔軟性により、1 つのスキーマフィールドをディメンションと指標の両方で使用し、異なるトラッキングニーズに対応することも可能になりました。

## セグメントの概念の変更

アドビでは、業界標準に合わせて、また、Adobe Experience Platform のセグメントとの区別を明確にするために、「セグメント」コンポーネントの名前を「フィルター」に変更しました。

[!UICONTROL Customer Journey Analytics] では、eVar、prop、イベントを使用せず、代わりに、マッピング先の Experience Platform のスキーマフィールド名を使用します。つまり、Adobe Analytics の既存のセグメントはすべて、[!UICONTROL Customer Journey Analytics] では互換性がなく、使用できません。既存の Adobe Analytics セグメントを Customer Journey Analytics に移行するには、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

[!DNL Customer Journey Analytics] から Experience Platform 統合プロファイルへの[!UICONTROL フィルター]（[!UICONTROL セグメント]）の共有や公開はまだできません（この機能は現在開発中です）。

セグメントの概念の変更に加えて、セグメントコンテナも次のように更新されます。

* **ヒットコンテナは、[!UICONTROL イベント]コンテナになりました。**&#x200B;この [!UICONTROL イベント] コンテナを使用すると、個々のイベントに基づいて人物情報を分類できます。
* **訪問コンテナは、[!UICONTROL セッション]コンテナになりました**。[!UICONTROL セッション]コンテナでは、特定のセッションのページインタラクション、キャンペーンまたはコンバージョンを識別できます。
* **訪問者コンテナは、[!UICONTROL ユーザー]コンテナになりました。**&#x200B;この [!UICONTROL 人物] コンテナには、指定した期間内に発生した個人のすべてのセッションとイベントが含まれます。

## 計算指標の概念の変更

計算指標は、Adobe AnalyticsとCustomer Journey Analyticsで同じ名前を付けています。 ただし、[!UICONTROL  Customer Journey Analytics] では、eVar、prop またはイベントを使用しなくなりました。代わりに Experience Platform スキーマ要素を使用します。つまり、既存の計算指標はすべて、[!UICONTROL Customer Journey Analytics] では互換性がなく、使用できません。Adobe Analytics の計算指標を Customer Journey Analytics に移行するには、次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## 変数アトリビューションと有効期限の設定の変更

[!UICONTROL Customer Journey Analytics] では、アトリビューションや有効期限を含むすべての変数設定を、レポート時に適用します。これらの設定は、現在、[データビュー](/help/data-views/component-settings/persistence.md)にあり、一部の変数設定（アトリビューションなど）はワークスペースプロジェクトで変更できます。

同じデータビューで、同じ変数の複数のバージョンを持つことができます。例えば、30 日後に期限切れになるトラッキングコードディメンションと、セッションの終わりに期限切れになるトラッキングコードディメンションを設定できます。これらのトラッキングコードディメンションは、両方とも同じソースデータを使用しますが、アトリビューション設定が異なります。

また、同じ接続に基づいて複数のデータビューを持つこともできます。例えば、セッションタイムアウトが 30 分のデータビューと、セッションタイムアウトが 15 分のデータビューです。両方のデータビューが右上のセレクターに表示されるので、シームレスに切り替えることができます。

## 分類の概念の変更

「分類」は「ルックアップデータセット」になりました。ルックアップデータセットは、イベントまたはプロファイルデータにある値やキーを検索するために使用されます。例えば、イベントデータ内の数値 ID を製品名にマッピングするルックアップデータをアップロードできます。ユースケースの例については、[アカウントレベルのデータをルックアップデータセットとして追加](/help/use-cases/b2b/b2b.md)を参照してください。

## 顧客属性の概念の変更

「顧客属性」は「プロファイルデータセット」になりました。プロファイルデータセットには、 [!UICONTROL イベント] データ。 例えば、顧客に関する CRM データをアップロードできます。含めるユーザー ID を選択できます。[!DNL Experience Platform] で定義された各データセットには、1 つ以上のユーザー ID セットが定義されています。

## 訪問者の識別方法の変更

Customer Journey Analyticsは、ECID 以外に ID の概念を拡張し、顧客 ID、Cookie ID、ステッチ済み ID、ユーザー ID、トラッキングコードなど、使用する ID を含めます。 複数のデータセットをまたいで共通の名前空間 ID を使用するか、[クロスチャネル分析](/help/cca/overview.md)を使用すると、異なるデータセットをまたいで人々をリンクできます。Customer Journey Analyticsで Workspace プロジェクトを設定するユーザーは、データセット全体で使用される ID を理解する必要があります。 Customer Journey Analyticsでの ID の使用について重点的に説明している次のビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## 低トラフィックディメンション項目の概念の変更

従来の Adobe Analytics では、変数が一意の値を受け取りすぎたとき、[!UICONTROL 低トラフィック]のディメンション項目のバケット化が始まります。Customer Journey Analyticsには、基数の高いフィールドに対する制限は少なくなります。 レポートアーキテクチャが変更されたことで、Analysis Workspace では、より多くの一意のディメンション項目に関するレポートを作成できるようになっています。詳しくは、 [ロングテール](../analysis-workspace/workspace-faq/long-tail.md) を参照してください。
