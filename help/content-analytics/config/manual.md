---
title: Content Analytics の手動設定
description: Content Analytics の手動設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---

# Content Analytics の手動設定

>[!WARNING]
>
>この記事は、今後の最終バージョンの非公式ドラフトバージョンであり、コンテンツ分析ドキュメントの一部です。 すべてのコンテンツは変更される可能性があり、この記事の現在のバージョンから法的義務を引き出すことはできません。
>

{{release-limited-testing}}

この記事では、Content Analytics 設定のアクティブ化または非アクティブ化や、Content Analytics 実装の編集に必要な手動アクションについて詳しく説明します。

次の手動設定アクションを使用できます。

## アクティブ化

新しい設定または既存の設定に加えた変更をアクティベートするには：

1. [ 公開フロー ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} に従う必要があります。 Content Analytics設定を含むタグプロパティのライブラリを正常に公開します。 設定したドメイン、エクスペリエンスおよびアセットについてContent Analytics データが収集されるのは、その後のみです。

1. Content Analyticsに従って、開発、ステージングまたはパブリッシ `<head>` 環境のページの構成要素に埋め込みコードを [ インストール ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) する必要があります。


## 非アクティブ化

コンテンツ分析データの収集を無効にするには：

1. Content Analyticsに従って、開発環境、ステージング環境または実稼動環境でページの `<head>` 要素にある [ 埋め込みコード ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) を削除します。
1. [ 削除 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview):Content Analytics設定に関連するタグプロパティ。



## 変更

[ ガイド付き設定ウィザード ](guided.md) を使用して、実装された設定にいくつかの小さな変更を加えることができます。 例えば、データビューを変更します。

Content Analytics設定に関連付けられたタグプロパティで ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)0}Adobe Content Analytics拡張機能 } を使用して、次のアーティファクトを変更します。[

* [ サンドボックスとデータストリーム ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >Adobe Content Analytics拡張機能で設定したサンドボックスとデータストリームが、以前の段階で [ ガイド付き設定 ](guided.md) を使用してContent Analytics用に設定されていることを確認します。 この設定により、必要なすべてのアーティファクトが使用可能になります。<br/><br/> また、サンドボックスまたはデータストリームの更新が、同じサンドボックスまたはデータストリームを使用するように設定された別のContent Analytics設定の妨げとならないことも確認します。
  >

* [ イベントのフィルタリング ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  正規表現を編集して、ページやアセットのフィルタリング方法を変更できます。


Adobe Content Analytics 拡張機能で変更を行った後、使用する [ 公開フロー ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} を確認して、変更内容をアクティベートします。



>[!MORELIKETHIS]
>
>[ ガイド付き設定 ](guided.md)
>[データ収集タグの公開 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) 概要
>


## バージョン管理

Content Analytics エクスペリエンスのバージョン管理が必要な場合は、分析するエクスペリエンスについて検討するページにグローバル `adobe.getContentExperienceVersion` 関数を追加する必要があります。

`adobe.getContentExperienceVersion` 関数は、バージョンを識別する文字列を値として返す必要があります。この値は、任意で選択できます。 バージョンが [ エクスペリエンス ID URL](/help/content-analytics/report/components.md#experience-metadata) に追加されます。

関数が存在しない場合や関数から値が返されない場合は、値 `NoVersion` がデフォルトとして使用されます。

### 例

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
