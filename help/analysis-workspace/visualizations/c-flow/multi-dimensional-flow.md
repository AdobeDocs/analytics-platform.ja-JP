---
description: ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを検証できます。
title: ディメンション間のフロー
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 92%

---


# ディメンション間のフロー

>[!NOTE]
>
>Customer Journey Analytics内のAnalysis Workspaceに関するドキュメントを表示している。 この機能セットは、従来のAdobeAnalyticsの [Analysis Workspaceとは少し異なります](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html)。 [詳細情報...](/help/getting-started/cja-aa.md)

ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを検証できます。

各フロー列の先頭のディメンションラベルにより、フローのビジュアライゼーションで複数のディメンションをより直感的に使用できます。

![](assets/flow.png)

アプリの使用例と Web の使用例の 2 つについて見ていきます。

## 使用例 1：アプリケーション

返される上位の項目が [!UICONTROL ItemAdded] で、[!UICONTROL アクション名]ディメンションがフローに追加されました。

![](assets/multi-dimensional-flow.png)

画面／ページ間のインタラクションおよびこのアプリのアクションを調査するには、調査対象に応じて複数の場所にページディメンションをドラッグできます。

* ドロップゾーンのどちらかの端（表示される黒い縁の長方形のゾーンの内側）にドラッグして、その端の上位の結果を&#x200B;**置き換えます**。

   ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* その端の白いスペース（黒い括弧で示される）にドラッグして、ビジュアライゼーションに&#x200B;**追加**&#x200B;します。

   ![](assets/multi-dimensional-flow4.png)

右の列の ItemScaled 項目をページディメンションで置き換える場合の結果を次に示します。上位の結果は、ページディメンションの上位の結果に変更されています。

![](assets/multi-dimensional-flow5.png)

これで、顧客がアクションおよびページをどのように移動しているかを確認できます。別のノードをクリックすることで、さらにフローを調査できます。

![](assets/multi-dimensional-flow6.png)

これは、別のアクション名ディメンションをビジュアライゼーションの端に追加する場合に発生することです。

![](assets/multi-dimensional-flow7.png)

これにより、深いインサイトが可能になり、分析するアプリに対する変更の可能性を考慮できます。

## 使用例 2：Web

この使用例は、最も多くのエントリを Web サイトに導くキャンペーンをどのようにして分析できるかを示します。

キャンペーン名ディメンションを新しいフローにドラッグします。

![](assets/multi-dimensional-flow8.png)

ここで、それらのキャンペーンがトラフィックを推進しているのはどのページかを確認したいので、ページディメンションをフロー結果の右側にドラッグして、ビジュアライゼーションに追加します。

![](assets/multi-dimensional-flow9.png)
