---
title: Marketo EngageデータのAdobe Experience Platformへの取り込みとCustomer Journey Analyticsでのレポート
description: Marketo EngageデータをCustomer Journey Analyticsに取り込む方法
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 57%

---

# Marketo EngageデータのAdobe Experience Platformへの取り込みとCustomer Journey Analyticsでのレポート

Adobe Experience Platform(Adobe Experience Platform) で新しく利用可能なMarketo Engageデータセットを活用して、B2B マーケターに貴重な分析およびレポートソリューションを提供できます。 次に、Adobe Customer Journey Analyticsでこれらのデータセットに関するレポートを作成します。

## 手順 1： Marketo ソースデータフィールドの XDM ターゲットへのマッピング

[人物](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#persons)および[アクティビティ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#activities)オブジェクトを、対応する XDM スキーマのターゲットフィールドにマッピングします。

## 手順 2:MarketoデータをAdobe Experience Platformに取り込む

[Marketo Engage コネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html)を使用して、Marketo から Experience Platform にデータを取り込み、プラットフォームに接続したアプリケーションを使用してこのデータを最新に維持します。

## 手順 3:Customer Journey Analyticsでこのデータセットへの接続を設定する

Experience Platformデータセットに関するレポートを作成するには、まずExperience PlatformとCustomer Journey Analyticsのデータセット間で接続を確立する必要があります。 詳細については、を参照してください。 [接続の作成または編集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ja).

## 手順 4： 1 つ以上のデータビューの作成

[データビュー](/help/data-views/data-views.md)は、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。Analysis Workspace で使用可能なすべてのディメンションおよび指標（この場合、Marketo に特有の指標およびディメンション）を指定します。また、それらのディメンションや指標がどの列からデータを取得するかも指定します。データビューは、Analysis Workspace でのレポート作成の準備の際に定義します。

## 手順 5：Analysis Workspace でのレポート

1 つのユースケースとして、2020年4月～6月のリードによる web ページ訪問数を検討してみます。

1. [Analytics Workspace](/help/analysis-workspace/home.md) を開いて、新しいプロジェクトを作成します。B2B/B2P CDP を持つお客様は、B2C 形式の分析をCustomer Journey Analyticsで実行できます。 B2B オブジェクトは、まだ使用できません。

1. 次のように、web ページビューの[フィルター](/help/components/filters/create-filters.md)を作成します。- Event Type = web.webpagedetails.pageViews :

   ![イベントとイベントタイプを示す定義ウィンドウ](../assets/marketo-filter.png)

1. フリーフォームテーブルで、作成したフィルター（Web ページビュー）を取り込み、月の日付範囲を取り込みます。これにより、毎月のリードによる web ページ訪問数がわかります。

   ![イベントを月別に表示するフリーフォームテーブル。](../assets/marketo-freeform.png)

1. または、人物キーまたは仕事用メールアドレスのディメンションを取り込みます。これにより、各リードによる web ページ訪問数がわかります。

   ![イベント、workEmail.Address および Web ページビューを示すフリーフォームテーブル。](../assets/marketo-freeform2.png)
