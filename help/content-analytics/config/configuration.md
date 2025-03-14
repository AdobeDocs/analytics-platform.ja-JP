---
title: コンテンツ分析の設定
description: コンテンツ分析の設定方法の概要
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 13%

---

# コンテンツ分析の設定

>[!WARNING]
>
>この記事は、今後の最終バージョンの非公式ドラフトバージョンであり、コンテンツ分析ドキュメントの一部です。 すべてのコンテンツは変更される可能性があり、この記事の現在のバージョンから法的義務を引き出すことはできません。
>

{{release-limited-testing}}

コンテンツ分析の設定は、次の手順で構成されます。

![ コンテンツ分析の設定 ](../assets/aca-configuration.svg)

1. コンテンツ分析 [ ガイド付き設定 ](guided.md) ウィザードを使用して、コンテンツ分析の設定の前提条件をセットアップするために必要なすべての手順を説明します。 設定を保存して後で戻ることができます。
1. 設定値に慣れたら、設定を実装できます。 この実装は、ウィザードで設定した内容に基づいて、必要なすべてのアーティファクトを作成します。 次のアーティファクトが作成、更新、選択されます。
   * カスタムジャーニー分析
      * [ データビュー ](/help/data-views/data-views.md) が選択されます。
      * [ 接続 ](/help/connections/overview.md) が選択され、選択したデータビューから自動的に派生します。
   * Experience Platform
      * サンドボックスが選択され、接続から自動的に派生します。 必要なワークフローとサービスがサンドボックスで有効になります。
      * コンテンツ分析スキーマは、サンドボックスで選択されます。 使用できない場合、必要なスキーマが作成されます。
      * サンドボックスで選択された Content Analytics データセット。 使用できない場合、必要なデータセットが作成されます。
   * データ収集
      * データストリームが作成され、データストリーム内にExperience Platform サービスが設定されて、Content Analytics エクスペリエンスイベントデータセットにデータがストリーミングされます。
      * タグプロパティは、設定ウィザードで正しいサンドボックス、データストリーム、その他の設定オプションに設定されたAdobe Content Analytics 拡張機能を使用して作成されます。
1. タグプロパティ [ 手動で公開 ](manual.md) した場合にのみ、コンテンツ分析が効果的にデプロイおよびアクティブ化されます。

1. [ ガイド付き設定 ](guided.md) ウィザードを使用して、実装済み設定に対して一部の制限付き変更のみを行うことができます。 例えば、「[ データビュー ](/help/data-views/data-views.md) を変更します。
1. 関連するタグプロパティの [Adobe Content Analytics 拡張機能 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) を使用して、実装された設定に他の変更を加えることができます。
1. タグプロパティを [ 手動で再公開 ](manual.md) した場合にのみ、手順 4 と 5 での設定変更が効果的にデプロイされアクティブ化されます。


コンテンツ分析を設定する前に、次の前提条件が満たされていることを確認してください。


>[!PREREQUISITES]
>
>* Content Analytics で使用する機能サービスのユーザーエージェントと IP アドレスを許可リストに登録している。 ユーザーエージェント文字列は `AdobeFeaturization/1.0` です。
>* Customer Journey Analytics Product Administrator の役割を持ち、接続の管理とデータ収集の管理を行う権限が付与されている。 Experience Platformに必要な権限は次のとおりです。
>  
>   | カテゴリ | 権限 | 説明 |
>   |---|---|---|
>   | [!UICONTROL データ収集] | データストリームを表示 | データストリームへの読み取り専用アクセス |
>   | [!UICONTROL データ収集] | データストリームの管理 | データストリームの読み取り、作成、編集、削除へのアクセス。 |
>   | [!UICONTROL  データモデリング ] | [!UICONTROL スキーマの表示] | スキーマおよび関連リソースへの読み取り専用アクセス |
>   | [!UICONTROL  データモデリング ] | [!UICONTROL スキーマの管理] | 各スキーマと関連リソースへの読み取り、作成、編集および削除アクセス |
>   | [!UICONTROL データ管理] | [!UICONTROL データセットの表示] | データセットおよびスキーマへの読み取り専用アクセス |
>   | [!UICONTROL データ管理] | [!UICONTROL データセットの管理] | データセットへの読み取り、作成、編集、削除アクセススキーマへの読み取り専用アクセス |
>   | [!UICONTROL データ取り込み] | [!UICONTROL ソースの管理] | ソースへの読み取り、作成、編集、無効化アクセス |
>   | [!UICONTROL Identity Management] | [!UICONTROL ID 名前空間の表示] | ID 名前空間への読み取り専用アクセス |
>
>* 次の重要な設定オプションを慎重に検討しました。
>
>   * サイトはエクスペリエンスレポートに適していますか？ 適切なエクスペリエンス報告は、次の条件を満たす場合にのみ可能です。
>   * サイトコンテンツは、URL によってのみ制御されます。
>   * ページ URL を使用すると、サイト上のページを再現できます。また、エクスペリエンスを推進するオプションの URL パラメーターを理解できます。
>* コンテンツエンゲージメントの分析とインサイトを取り込むページを明確に理解している。
>* コンテンツエンゲージメントの分析とインサイトを取り込むアセット（タイプ）を明確に理解している。
>


>[!MORELIKETHIS]
>
>* [ ガイド付き設定 ](guided.md)
>* [ 手動設定 ](manual.md)
>* [アクセス制御](/help/technotes/access-control.md)
>


