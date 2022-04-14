---
title: B2B データの AEP への取り込みと CJA でのレポート
description: Marketoデータを CJA に取り込む方法を説明します。
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: e18de2563427941f8c227881b46f73c490be218d
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 5%

---


# Marketo B2B データを AEP に取り込み、CJA でレポートする

Adobe Experience Platform(AEP) で新しく入手可能なMarketo B2B データセットを活用して、B2B マーケターに貴重な分析およびレポートソリューションを提供できます。 次に、これらのデータセットに関するレポートをCustomer Journey Analytics(CJA) で作成します。

## 手順 1:Marketoソースデータフィールドの XDM ターゲットへのマッピング

を [人物](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#persons) および [アクティビティ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#activities) をそれぞれの XDM スキーマターゲットフィールドに追加します。

## 手順 2:Marketoデータの AEP への取り込み

以下を使用： [Marketo Engageコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=en) を使用して、MarketoからExperience Platformに B2B データを取り込み、Platform 接続のアプリケーションを使用してこのデータを最新の状態に保ちます。

## 手順 3:CJA でこのデータセットへの接続を設定する

Experience Platformデータセットに関するレポートを作成するには、まずExperience Platformと CJA のデータセット間で接続を確立する必要があります。 詳細は、 [接続の作成](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja).

## 手順 4:1 つ以上のデータビューの作成

A [データビュー](/help/data-views/data-views.md) は、接続からのCustomer Journey Analyticsの解釈方法を決定するためのコンテナ固有のものです。 Analysis Workspaceで使用できるすべてのディメンションと指標を指定します。この例では、Marketoに固有の指標とディメンションです。 また、これらのディメンションと指標のデータを取得する列も指定します。 データビューは、Analysis Workspace でのレポート作成の準備の際に定義します。

## 手順 5:Analysis Workspaceでのレポート

検討してみると、次のようなユースケースがあります。2020 年 4 月～6 月にリード別の Web ページ訪問数はいくつですか？

1. 開く [Analytics Workspace](/help/analysis-workspace/home.md) 新しいプロジェクトを作成します。

1. の作成 [フィルター](/help/components/filters/create-filters.md) web ページビューの場合は次のようになります — イベントタイプ= web.webpagedetails.pageViews :

   ![](assets/marketo-filter.png)

1. フリーフォームテーブルに、作成したフィルター（「Web ページビュー数」）を取り込み、月の日付範囲を取り込みます。 これにより、各月のリード別の Web ページ訪問数がわかります。

   ![](assets/marketo-freeform.png)

1. または、次のディメンションを引き込みます。担当者キーまたは勤務先の電子メールアドレス。 これにより、各リード別の Web ページ訪問数が得られます。

   ![](assets/marketo-freeform2.png)
