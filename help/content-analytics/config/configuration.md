---
title: コンテンツ分析の設定
description: コンテンツ分析の設定方法の概要
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 19%

---

# コンテンツ分析の設定

コンテンツ分析の設定は、次の手順で構成されます。

![ コンテンツ分析の設定 ](../assets/aca-configuration.svg){zoomable="yes"}

1. Content Analytics [ ガイド付き設定 ](guided.md) ウィザードを使用して、Content Analyticsの設定の前提条件を設定するために必要なすべての手順を確認します。 設定はいつでも保存し、後で戻ることができます。
1. 設定値に慣れたら、設定を実装できます。 この実装は、ウィザードで設定した内容に基づいて、必要なすべてのアーティファクトを作成します。
1. タグプロパティを [ 手動で公開 ](manual.md) した場合にのみ、Content Analytics設定が効果的にデプロイされ、データ収集が開始されます。

1. [ ガイド付き設定 ](guided.md) ウィザードを使用して行える実装済み設定の変更は、一部のみです。 例えば、「[ データビュー ](/help/data-views/data-views.md) を変更します。
1. 関連するタグプロパティの [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)0&rbrace;Adobe Content Analytics拡張機能 &rbrace; を使用して、実装された設定に他の変更を加えることができます。
1. タグプロパティ [ 手動での再公開 ](manual.md) を行った場合にのみ、設定変更が効果的にデプロイされ、変更内容に基づいてデータ収集が開始されます。


## 前提条件

Content Analyticsを設定する前に、次の前提条件が満たされていることを確認してください。

* コンテンツ分析で使用する機能サービスのユーザーエージェントと IP アドレスを許可リストに登録しています。設定するユーザーエージェント文字列は <code>AdobeFeaturization/1.0 です。</code>。
* 通常の行動データ収集に [JavaScriptを使用した web SDK](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/install/library){target="_blank"} を実装している場合は、デフォルト名 <code>alloy を使用していることを確認します</code> JavaScript ライブラリ用。
* Customer Journey Analyticsの製品管理者の役割に加えて、接続の管理とデータビューの管理を行う権限があります。
* Content Analyticsのエクスペリエンスを収集する場合は、web ページの変更に基づいて [Content Analyticsのバージョン管理 ](manual.md#versioning) を設定および更新してください。
* [ データ収集権限 ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"} が必要です。
   * [Experience Platformの権限 ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform データ収集の権限 ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* 次の重要な設定オプションを慎重に検討しました。

   * サイトはエクスペリエンスレポートに適しています。 適切なエクスペリエンスレポートは、次の条件を満たした場合にのみ可能です。
      * ページ URL を使用して、サイト上のページを再現できる必要があります。
      * 特定のユーザーが表示するテキストコンテンツは、ページ URL を使用して再生でき、Cookie やその他のパーソナライゼーションメカニズムには依存しません。
   * コンテンツエンゲージメントの分析とインサイトを取り込むページを明確に理解しています。
   * コンテンツエンゲージメントの分析とインサイトを取り込むアセット（タイプ）を明確に理解しています。


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
>* [ガイド付き設定](guided.md)
>* [手動設定](manual.md)
>* [アクセス制御](/help/technotes/access-control.md)
>
