---
description: ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを検証できます。
title: ディメンション間のフロー
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 80522177d5258e4b5046b3872483ce2b482ae77d
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 7%

---

# ディメンション間のフロー

ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを調べることができます。この記事では、モバイルアプリのインタラクションとイベント、およびキャンペーンによる web 訪問の促進方法の 2 つのユースケースに対して、このフローを使用する方法を説明します

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## モバイルアプリのインタラクションとイベント

このサンプルフローでは、[!UICONTROL  画面名 ] ディメンションを使用して、ユーザーがアプリ内の様々な画面（シーン）をどのように使用しているかを確認します。 返される上部の画面は **[!UICONTROL luma:content:ios:en:home]** で、これはアプリのホームページです。

![ 追加された項目を示すフロー。](assets/flowapp.png)

このアプリで画面とイベントタイプ（買い物かごに追加、購入など）間のやり取りを確認するには、**[!UICONTROL イベントタイプ]** ディメンションをドラッグ&amp;ドロップします。

* フロー内の使用可能なステップの上に、そのディメンションを置き換えるには、次の手順を実行します。

  ![ 複数の領域にドラッグされたページディメンションを示すフロー ](assets/flowapp-replace.png)

* 現在のフロービジュアライゼーションの外部で、ディメンションを追加するには：

  ![ 末尾の空白にドラッグされたページディメンションを示すフロー。](assets/flowapp-add.png)

以下のフロービジュアライゼーションは、**[!UICONTROL Event Types]** ディメンションを追加した結果を示しています。 このビジュアライゼーションは、モバイルアプリのユーザーが、商品を買い物かごに追加する前やアプリケーションを閉じる前やオファーを表示する前に、アプリ内の様々な画面をどのように移動するかについてのインサイトを提供します。

![ ページディメンションの結果をリストの上部に表示する fLow。](assets/flowapp-result.png)

## キャンペーンによる web 訪問の促進

Web サイトへの訪問を促進するキャンペーンを分析します。 **[!UICONTROL キャンペーン名]** をディメンションとするフロービジュアライゼーションを作成します

![ フロー web キャンペーン名ディメンション ](assets/flowweb.png)

最後の **[!UICONTROL キャンペーン名]** ディメンションを **[!UICONTROL 書式設定されたページ名]** ディメンションに置き換え、フロービジュアライゼーションの最後に別の **[!UICONTROL 書式設定されたページ名]** ディメンションを追加します。

![ フロー web キャンペーン名および web ページディメンション ](assets/flowweb-replace.png)

フローの上にマウスポインターを置くと、詳細が表示されます。 例えば、どのキャンペーンが買い物かごのチェックアウトにつながったかを示します。

![ フロー web キャンペーン名と web ページディメンションのホバー ](assets/flowweb-hover.png)
