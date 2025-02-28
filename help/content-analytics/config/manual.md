---
title: Content Analytics の手動設定
description: Content Analytics の手動設定方法
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

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

新しい設定または既存の設定に加えた変更をアクティブ化するには、関連するタグプロパティを [ 公開 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} する必要があります。 Content Analytics タグプロパティを公開した場合にのみ、設定したドメイン、エクスペリエンスおよびアセットに関する Content Analytics データが収集されます。


## 非アクティブ化

コンテンツ分析データの収集を無効にするには、コンテンツ分析設定に関連付けられているタグプロパティを [ 非公開 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} します。



## 変更

一般に、実装を変更するには、[ ガイド付き設定ウィザード ](guided.md) を使用します。

または、Content Analytics 設定に関連付けられたタグプロパティでAdobe Content Analytics 拡張機能を使用して、次のアーティファクトを変更することもできます。

* [ サンドボックスとデータストリーム ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >Adobe Content Analytics 拡張機能で設定したサンドボックスとデータストリームが、以前の段階で [ ガイド付き設定 ](guided.md) を使用してコンテンツ分析用に設定されていることを確認する必要があります。 この設定により、必要なすべてのアーティファクトが使用可能になります。<br/><br/> また、サンドボックスまたはデータストリームの更新が、同じサンドボックスまたはデータストリームを使用するように設定された別の Content Analytics 設定に干渉しないことを確認する必要もあります。
  >

* [ イベントのフィルタリング ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}。

  正規表現を編集して、ページやアセットのフィルタリング方法を変更できます。


Adobe Content Analytics 拡張機能で変更を行ったら、必ず変更内容を [ アクティベート ](#activate) します。



>[!MORELIKETHIS]
>
>[ ガイド付き設定 ](guided.md)
>[データ収集タグの公開 ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) 概要
>