---
title: Content Analytics 手動設定
description: Content Analytics の手動設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a593221a9eb81d747777aedb323fd44a32c470be
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 64%

---

# Content Analytics 手動設定

この記事では、Content Analytics 設定のデータ収集を開始または停止したり、Content Analytics の実装を編集したりするために必要な手動アクションについて詳しく説明します。

次の手動設定アクションを使用できます。

## データ収集を開始

実装された Content Analytics 設定のデータ収集を開始するには：

1. [公開フロー](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview){target="_blank"}に従います。 Content Analytics設定を含むタグプロパティのライブラリを正常に公開します。

1. 設定したチャネルに基づいて、次の操作を行います。

   * **web**&#x200B;の場合：[Content Analyticsに従って、開発環境、ステージング環境または公開環境のページの`<head>`要素に埋め込まれたコードを](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/environments/environments#installation) インストールします。
   * **mobile**&#x200B;の場合：モバイルアプリケーションをContent Analytics用に設定およびインストルメントする方法については、[Experience Platform Mobile SDK ドキュメント ](https://developer.adobe.com/client-sdks/home/)の[Adobe Content Analytics拡張機能ガイド ](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)に記載されているソリューション固有のソリューションを参照してください。

## データ収集を停止

設定したチャネルに基づいて、実装されたContent Analytics設定のデータ収集を停止するには、次の手順を実行します。

* **web**&#x200B;の場合：

   1. コンテンツ分析に従って、開発環境、ステージング環境または本番環境のページの `<head>` 要素にある[埋め込みコード](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/environments/environments)を削除します。
   1. Content Analytics設定に関連付けられているweb Tags プロパティを削除します。

* **mobile**&#x200B;の場合：

   1. アプリから[Content Analytics拡張機能](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)を削除します。
   1. Content Analytics設定に関連付けられているモバイルタグのプロパティを削除します。

[公開フロー](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview){target="_blank"}に従って、変更を適用します。


## データ収集を変更

[ガイド付き設定ウィザード](guided.md)を使用して、実装済み設定に一部の小さな変更を行うことができます。 例えば、データビューを変更したり、エクスペリエンスを有効または無効にしたりします。


### Web

Content Analytics設定に関連付けられているTags プロパティで[Adobe Content Analytics web拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview)を使用して、次のアーティファクトを変更します。

* [サンドボックスとデータストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >Adobe Content Analytics 拡張機能で設定するサンドボックスとデータストリームが、以前のステージで[ガイド付き設定](guided.md)を使用して既に Content Analytics 用に設定されていることを確認します。 この設定により、必要なすべてのアーティファクトが使用可能になります。<br/><br/>また、サンドボックスまたはデータストリームの更新が、同じサンドボックスまたはデータストリームを使用するように設定されている別の Content Analytics 設定の妨げとならないことも確認します。
  >

* [エクスペリエンスのキャプチャと定義](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=ja#configure-experience-capture-and-definition)

  エクスペリエンスを有効または無効にし、正規表現とクエリパラメーターの組み合わせを編集して、web サイトでコンテンツをレンダリングする方法を決定できます。

* [イベントセグメンテーション](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  正規表現を編集して、ページとアセットをどのようにセグメント化するかを変更できます。


Adobe Content Analytics web拡張機能を変更した後、[公開フロー](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview){target="_blank"}を使用してデータの収集を開始します。


### モバイル

Content Analytics設定に関連付けられているTags プロパティで[Adobe Content Analytics モバイル拡張機能](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)を使用して、さらに変更を加えます。

Adobe Content Analytics web拡張機能を変更した後、[公開フロー](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview){target="_blank"}を使用してデータの収集を開始します。


## バージョン管理

>[!NOTE]
>
>このセクションは、web チャネルのContent Analyticsにのみ適用されます。


Content Analytics エクスペリエンスを収集する場合は、新しいエクスペリエンス（web ページへの変更）が適切に収集されるように、バージョン管理を実装することを検討する必要があります。

バージョン管理を実装するには、分析するエクスペリエンスと見なされるページにグローバル `adobe.getContentExperienceVersion` 関数を追加します。

`adobe.getContentExperienceVersion` 関数は、バージョンを識別するために文字列を値として返す必要があります。値は、任意の値にすることができます。 バージョンが[エクスペリエンス ID URL](/help/content-analytics/report/components.md#experience-metadata) に追加されます。

関数が存在しないか、関数から値が返されない場合は、値 `NoVersion` がデフォルトとして使用されます。

### 例

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

>[!MORELIKETHIS]
>
>[ ガイド付き設定](guided.md)
>[データ収集タグ公開の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)
>
