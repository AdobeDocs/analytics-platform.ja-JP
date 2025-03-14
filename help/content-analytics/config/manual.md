---
title: Content Analytics の手動設定
description: Content Analytics の手動設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
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

1. [ 公開フロー ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} に従う必要があります。 Content Analytics 設定を含むタグプロパティのライブラリを正常に公開した場合にのみ、設定したドメイン、エクスペリエンスおよびアセットに関する Content Analytics データが収集されます。

1. 埋め込みコードは、コンテンツ分析に応じて ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) 開発、ステージングまたは公開環境上のページの `<head>` 要素に [ インストール」する必要があります。


## 非アクティブ化

コンテンツ分析データの収集を無効にするには：

1. コンテンツ分析の対象となる、開発環境、ステージング環境または実稼動環境のページの `<head>` 要素にある [ 埋め込みコード ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) を削除します。
1. [ 削除 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)Content Analytics 設定に関連付けられたタグプロパティ。



## 変更

一般に、実装を変更するには、[ ガイド付き設定ウィザード ](guided.md) を使用します。

または、Content Analytics 設定に関連付けられたタグプロパティで ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)0}Adobe Content Analytics 拡張機能 } を使用して、次のアーティファクトを変更することもできます。[

* [ サンドボックスとデータストリーム ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >Adobe Content Analytics 拡張機能で設定したサンドボックスとデータストリームが、以前の段階で [ ガイド付き設定 ](guided.md) を使用してコンテンツ分析用に設定されていることを確認する必要があります。 この設定により、必要なすべてのアーティファクトが使用可能になります。<br/><br/> また、サンドボックスまたはデータストリームの更新が、同じサンドボックスまたはデータストリームを使用するように設定された別の Content Analytics 設定に干渉しないことを確認する必要もあります。
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

Content Analytics エクスペリエンスのバージョン管理が必要な場合は、分析するエクスペリエンスについて考慮するページにグローバル `adobe.getContentExperienceVersion` 関数を追加する必要があります。

`adobe.getContentExperienceVersion` 関数は、値として文字列を返す必要があります。この文字列は、バージョンを識別するために選択した任意の値になります。 バージョンがエクスペリエンス ID の URL に追加されます。

関数が存在しない場合や関数から値が返されない場合は、値 `NoVersion` がデフォルトとして使用されます。

### 例

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
