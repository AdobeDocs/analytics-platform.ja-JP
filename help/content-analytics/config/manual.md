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
ht-degree: 5%

---

# コンテンツ分析手動設定

この記事では、Content Analytics設定のデータ収集を開始または停止したり、Content Analytics実装を編集したりするために必要な手動のアクションについて詳しく説明します。

次の手動設定アクションを使用できます。

## データ収集の開始

実装されたContent Analytics設定のデータ収集を開始するには、次の手順を実行します。

1. [ 公開フロー ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} に従います。 Content Analytics設定を含むタグプロパティのライブラリを正常に公開します。

1. [ インストール ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)Content Analyticsを使用して、開発環境、ステージング環境またはパブリッシ `<head>` 環境のページの UI 要素に埋め込まれたコード。


## データ収集の停止

実装されたContent Analytics設定のデータ収集を停止するには、次の手順を実行します。

1. Content Analyticsに従って、開発環境、ステージング環境または実稼動環境でページの `<head>` 要素にある [ 埋め込みコード ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) を削除します。
1. [ 削除 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview):Content Analytics設定に関連するタグプロパティ。



## データ収集の変更

[ ガイド付き設定ウィザード ](guided.md) を使用して、実装された設定にいくつかの小さな変更を加えることができます。 例えば、データビューを変更したり、エクスペリエンスを有効または無効にしたりします。

Content Analytics設定に関連付けられたタグプロパティで ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)0}Adobe Content Analytics拡張機能 } を使用して、次のアーティファクトを変更します。[

* [ サンドボックスとデータストリーム ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >Adobe Content Analytics拡張機能で設定したサンドボックスとデータストリームが、以前の段階で [ ガイド付き設定 ](guided.md) を使用してContent Analytics用に設定されていることを確認します。 この設定により、必要なすべてのアーティファクトが使用可能になります。<br/><br/> また、サンドボックスまたはデータストリームの更新が、同じサンドボックスまたはデータストリームを使用するように設定された別のContent Analytics設定の妨げとならないことも確認します。
  >

* [ エクスペリエンスのキャプチャと定義 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  エクスペリエンスを有効または無効にしたり、正規表現とクエリパラメーターの組み合わせを編集したりして、web サイト上でのコンテンツのレンダリング方法を決定できます。

* [ イベントのセグメント化 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  正規表現を編集して、ページやアセットのセグメント化方法を変更できます。


Adobe Content Analytics拡張機能で変更を行った後、使用している [ 公開フロー ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} を確認し、加えられた変更に基づいてデータの収集を開始します。



>[!MORELIKETHIS]
>
>[ガイド付き設定](guided.md)
>[データ収集タグの公開 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) 概要
>


## バージョン管理

Content Analytics エクスペリエンスを収集する場合は、新しいエクスペリエンス（web ページの変更内容）が適切に収集されるように、バージョン管理の実装を検討する必要があります。

バージョン管理を実装するには、分析するエクスペリエンスについて検討するページにグローバル `adobe.getContentExperienceVersion` 関数を追加します。

`adobe.getContentExperienceVersion` 関数は、バージョンを識別する文字列を値として返す必要があります。この値は、任意で選択できます。 バージョンが [ エクスペリエンス ID URL](/help/content-analytics/report/components.md#experience-metadata) に追加されます。

関数が存在しない場合や関数から値が返されない場合は、値 `NoVersion` がデフォルトとして使用されます。

### 例

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
