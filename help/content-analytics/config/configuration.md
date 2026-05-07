---
title: Content Analytics の設定
description: Webとモバイルチャネル用にContent Analyticsを設定する方法について説明します。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: b8b0237a092b37d28bec56bba05c30a853097d4f
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 76%

---


# Content Analytics の設定

この記事では、コンテンツ分析の設定方法の概要について説明します。

コンテンツ分析を設定する前に、[前提条件](#prerequisites)が満たされていること、必要な[アクセス制御](#access-control)があること、[制限事項](#limitations)を認識していることを確認する必要があります。


高レベルの手順

![Content Analytics の設定](../assets/aca-configuration.svg){zoomable="yes"}

1. Content Analytics[&#x200B; ガイド付き設定](guided.md)ウィザードを使用すると、Content Analytics の設定の前提条件を設定するために必要なすべての手順を説明します。 いつでも設定を保存し、後で戻ることができます。
1. 設定値に慣れたら、設定を実装できます。 この実装では、ウィザードで設定した内容に基づいて、必要なすべてのアーティファクトが作成されます。
1. [手動で公開](manual.md)した場合にのみ、「Tags」プロパティがContent Analytics設定に効果的にデプロイされ、データ収集が開始されます。

1. [ガイド付き設定](guided.md)を使用して、実装済み設定に一部の小さな変更のみを行うことができます。 例えば、[データビュー](/help/data-views/data-views.md)を変更します。
1. [web](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview)または[mobile](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)の関連するTags プロパティのAdobe Content Analytics拡張機能を使用して、実装された設定に他の変更を加えることができます。
1. 設定の変更は効果的にデプロイされ、データ収集はタグプロパティを手動で再公開した場合にのみ開始されます。


## 前提条件

Content Analytics を設定する前に、次の前提条件が満たされていることを確認してください。

### Web

* Content Analytics で使用する機能サービスのユーザーエージェントと IP アドレスを許可リストに登録しています。 設定するユーザーエージェント文字列は次のとおりです。<code>AdobeFeaturization/1.0</code>。
* 定期的な行動データ収集のために [JavaScript を使用して Web SDK](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/install/library){target="_blank"} を実装している場合は、JavaScript ライブラリのデフォルト名 <code>alloy</code> を使用していることを確認します。
* Customer Journey Analytics 製品管理者の役割を持ち、接続の管理とデータビューの管理を行う権限が付与されています。
* Content Analytics エクスペリエンスを収集する場合は、web ページの変更に基づいてContent Analyticsのバージョン管理を設定および更新してください。
* [データ収集には必要な権限](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}権限。
   * [Experience Platform データ収集](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}権限。
* 次の重要な設定オプションを慎重に検討しました。

   * サイトはエクスペリエンスレポートに適しています。 適切なエクスペリエンスレポートは、次の条件を満たす場合にのみ可能です。
      * ページ URL を使用して、サイト上のページを再現できる必要があります。
      * 特定のユーザーが表示するテキストコンテンツは、ページ URL を使用して再現でき、Cookie やその他のパーソナライゼーションメカニズムに依存しません。
   * コンテンツエンゲージメントの分析とインサイトのために、キャプチャしたいページを明確に把握することができます。
   * コンテンツエンゲージメントの分析とインサイトを取り込むアセット（タイプ）を明確に理解しています。

### モバイル

* モバイルアプリに対して、[Experience Platform Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/)および[Experience Platform Identity for Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)拡張機能が有効になっていることを確認します。
* Customer Journey Analytics 製品管理者の役割を持ち、接続の管理とデータビューの管理を行う権限が付与されています。
* [データ収集には必要な権限](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}権限。
   * [Experience Platform データ収集](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}権限。



## アクセス制御

>[!IMPORTANT]
>
>個々のユーザーまたはユーザーグループに対して Content Analytics アクセスを有効または無効にするために設定できる Content Analytics 権限がありません。
>

ユーザーまたはユーザーグループに Content Analytics へのアクセス権を付与するには、[Content Analytics 用に設定されている 1 つ以上のデータビュー](guided.md#data-view)へのアクセス権をユーザーまたはユーザーグループに付与する必要があります。

このアクセス権は、次のことを意味します。

1. Content Analytics が有効化されたデータビューは、特定の Customer Journey Analytics 製品プロファイルのデータビュー権限の一部として含まれています。
1. この特定の Customer Journey Analytics 製品プロファイルは、ユーザーまたはユーザーグループに割り当てられた製品プロファイルの 1 つです。

## 制限事項

コンテンツ分析イベントデータに使用されるスキーマはシステム所有です。 システム所有のスキーマは変更できません。つまり、次のようになります。

* ジオロケーション、ボット検出、デバイス検索などの機能のサポートにフィールドグループを含めることはできません。
* [フィールドベースのステッチ](/help/stitching/fbs.md)をサポートする特定の識別子を追加することはできません。

>[!MORELIKETHIS]
>
>* [ガイド付き設定](guided.md)
>* [手動設定](manual.md)
>* [アクセス制御](/help/technotes/access-control.md)
>
