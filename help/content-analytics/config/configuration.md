---
title: コンテンツ分析の設定
description: コンテンツ分析の設定方法の概要
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 14%

---

# コンテンツ分析の設定

{{draft-aca}}

{{release-limited-testing}}

コンテンツ分析の設定は、次の手順で構成されます。

![ コンテンツ分析の設定 ](../assets/aca-configuration.svg){zoomable="yes"}

1. Content Analytics [ ガイド付き設定 ](guided.md) ウィザードを使用して、Content Analyticsの設定の前提条件を設定するために必要なすべての手順を確認します。 設定はいつでも保存し、後で戻ることができます。
1. 設定値に慣れたら、設定を実装できます。 この実装は、ウィザードで設定した内容に基づいて、必要なすべてのアーティファクトを作成します。
1. タグプロパティを [ 手動で公開 ](manual.md) した場合にのみ、Content Analytics設定が効果的にデプロイされアクティブ化されます。

1. [ ガイド付き設定 ](guided.md) ウィザードを使用して行える実装済み設定の変更は、一部のみです。 例えば、「[ データビュー ](/help/data-views/data-views.md) を変更します。
1. 関連するタグプロパティの ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)0}Adobe Content Analytics拡張機能 } を使用して、実装された設定に他の変更を加えることができます。[
1. タグプロパティを [ 手動で再公開 ](manual.md) した場合にのみ、設定の変更が効果的にデプロイされアクティブ化されます。


## 前提条件

Content Analyticsを設定する前に、次の前提条件が満たされていることを確認してください。

* Content Analytics で使用する機能サービスのユーザーエージェントと IP アドレスを許可リストに登録している。 設定するユーザーエージェント文字列は <code>AdobeFeaturization/1.0 です。</code>。
* Customer Journey Analyticsの製品管理者の役割に加えて、接続の管理とデータビューの管理を行う権限があります。
* 必要なExperience Platform権限がある。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL データ収集] | データストリームを表示 | データストリームへの読み取り専用アクセス |
  | [!UICONTROL データ収集] | データストリームの管理 | データストリームの読み取り、作成、編集、削除へのアクセス。 |
  | [!UICONTROL  データモデリング ] | [!UICONTROL スキーマの表示] | スキーマおよび関連リソースへの読み取り専用アクセス |
  | [!UICONTROL  データモデリング ] | [!UICONTROL スキーマの管理] | 各スキーマと関連リソースへの読み取り、作成、編集および削除アクセス |
  | [!UICONTROL データ管理] | [!UICONTROL データセットの表示] | データセットおよびスキーマへの読み取り専用アクセス |
  | [!UICONTROL データ管理] | [!UICONTROL データセットの管理] | データセットへの読み取り、作成、編集、削除アクセススキーマへの読み取り専用アクセス |
  | [!UICONTROL データ取り込み] | [!UICONTROL ソースの管理] | ソースへの読み取り、作成、編集、無効化アクセス |
  | [!UICONTROL Identity Management] | [!UICONTROL ID 名前空間の表示] | ID 名前空間への読み取り専用アクセス |

* 次の重要な設定オプションを慎重に検討しました。

   * サイトはエクスペリエンスレポートに適しています。 適切なエクスペリエンスレポートは、次の条件を満たした場合にのみ可能です。
      * 公開 URL でのみサイトコンテンツにアクセスできます。 サイトへのアクセスには、URL を通じて利用できないパーソナライズされたトークン、Cookie、その他のメカニズムは必要ありません。
      * ページ URL を使用すると、サイト上のページを再現できます。また、エクスペリエンスを推進するオプションの URL パラメーターを理解できます。
   * コンテンツエンゲージメントの分析とインサイトを取り込むページを明確に理解している。
   * コンテンツエンゲージメントの分析とインサイトを取り込むアセット（タイプ）を明確に理解している。


## アクセス制御

>[!IMPORTANT]
>
>個々のユーザーまたはユーザーグループに対してContent Analytics アクセスを有効または無効にするために設定できるContent Analytics アクセス権はありません。
>

ユーザーまたはユーザーグループにContent Analyticsへのアクセスを提供するには、1 つ以上の [Content Analytics用に設定されたデータビュー ](guided.md#data-view) へのアクセスをユーザーまたはユーザーグループに提供する必要があります。

このアクセスは、次のことを意味します。

1. Content Analytics対応データビューは、特定のCustomer Journey Analytics製品プロファイルのデータビュー権限の一部として含まれています。
1. その特定のCustomer Journey Analytics製品プロファイルは、ユーザーまたはユーザーグループに割り当てられた製品プロファイルの 1 つです。

>[!MORELIKETHIS]
>
>* [ ガイド付き設定 ](guided.md)
>* [ 手動設定 ](manual.md)
>* [アクセス制御](/help/technotes/access-control.md)
>
