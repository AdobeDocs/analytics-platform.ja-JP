---
title: コンテンツ分析手動設定
description: コンテンツ分析の手動設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 96%

---

# コンテンツ分析手動設定

この記事では、コンテンツ分析設定のデータ収集を開始または停止したり、コンテンツ分析の実装を編集したりするために必要な手動アクションについて詳しく説明します。

次の手動設定アクションを使用できます。

## データ収集を開始

実装されたコンテンツ分析設定のデータ収集を開始するには：

1. [公開フロー](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview){target="_blank"}に従います。コンテンツ分析設定を含むタグプロパティのライブラリを正常に公開します。

1. コンテンツ分析に従って、開発環境、ステージング環境または公開環境のページの `<head>` 要素にある埋め込みコードを[インストール](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/environments/environments#installation)します。


## データ収集を停止

実装されたコンテンツ分析設定のデータ収集を停止するには：

1. コンテンツ分析に従って、開発環境、ステージング環境または実稼動環境のページの `<head>` 要素にある[埋め込みコード](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/environments/environments)を削除します。
1. コンテンツ分析設定に関連付けられたタグプロパティを[削除](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)します。



## データ収集を変更

[ガイド付き設定ウィザード](guided.md)を使用して、実装済み設定に一部の小さな変更を行うことができます。例えば、データビューを変更したり、エクスペリエンスを有効または無効にしたりします。

コンテンツ分析設定に関連付けられたタグプロパティで [Adobe コンテンツ分析拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview)を使用して、次のアーティファクトを変更します。

* [サンドボックスとデータストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >Adobe コンテンツ分析拡張機能で設定するサンドボックスとデータストリームが、以前のステージで[ガイド付き設定](guided.md)を使用して既にコンテンツ分析用に設定されていることを確認します。この設定により、必要なすべてのアーティファクトが使用可能になります。<br/><br/>また、サンドボックスまたはデータストリームの更新が、同じサンドボックスまたはデータストリームを使用するように設定されている別のコンテンツ分析設定の妨げとならないことも確認します。
  >

* [エクスペリエンスのキャプチャと定義](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=ja#configure-experience-capture-and-definition)

  エクスペリエンスを有効または無効にし、正規表現とクエリパラメーターの組み合わせを編集して、web サイトでコンテンツをレンダリングする方法を決定できます。

* [ イベントのセグメント化 ](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  正規表現を編集して、ページやアセットのセグメント化方法を変更できます。


Adobe コンテンツ分析拡張機能に変更を行った後、[公開フロー](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview){target="_blank"}を使用して、行った変更に基づいてデータの収集を開始します。



>[!MORELIKETHIS]
>
>[ガイド付き設定](guided.md)
>[データ収集タグ公開の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/publish/overview)
>


## バージョン管理

コンテンツ分析エクスペリエンスを収集する場合は、新しいエクスペリエンス（web ページへの変更）が適切に収集されるように、バージョン管理を実装することを検討する必要があります。

バージョン管理を実装するには、分析するエクスペリエンスと見なされるページにグローバル `adobe.getContentExperienceVersion` 関数を追加します。

`adobe.getContentExperienceVersion` 関数は、バージョンを識別するために文字列を値として返す必要があります。値は、任意の値にすることができます。バージョンが[エクスペリエンス ID URL](/help/content-analytics/report/components.md#experience-metadata) に追加されます。

関数が存在しないか、関数から値が返されない場合は、値 `NoVersion` がデフォルトとして使用されます。

### 例

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
