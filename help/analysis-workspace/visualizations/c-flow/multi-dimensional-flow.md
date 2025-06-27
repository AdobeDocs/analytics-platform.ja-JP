---
description: ディメンション間フローを使用して、様々なディメンションをまたいだユーザーパスを調べる方法を理解します。
title: ディメンション間のフロー
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 89%

---

# ディメンション間のフロー

ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを調べることができます。この記事では、モバイルアプリのインタラクションとイベント、およびキャンペーンによる web 訪問の促進方法の 2 つのユースケースに対して、このフローを使用する方法を説明します

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## モバイルアプリのインタラクションとイベント

このフロー例では、[!UICONTROL 画面名]ディメンションを使用して、ユーザーがアプリ内の様々な画面（シーン）をどのように使用するかを確認します。返される上部の画面は **[!UICONTROL luma: content: ios: en: home]** で、これはアプリのホームページです。

![追加された項目を示すフロー。](assets/flowapp.png)

このアプリの画面とイベントタイプ（買い物かごへの追加、購入など）間のインタラクションを調べるには、**[!UICONTROL イベントタイプ]**&#x200B;ディメンションをドラッグ＆ドロップします。

* フロー内の使用可能なステップに加えて、そのディメンションを置き換えるには：

  ![複数の領域にドラッグされたページディメンションを示すフロー。](assets/flowapp-replace.png)

* 現在のフロービジュアライゼーションの外部で、ディメンションを追加するには：

  ![末尾の空白にドラッグされたページディメンションを示すフロー。](assets/flowapp-add.png)

以下のフロービジュアライゼーションは、**[!UICONTROL イベントタイプ]**&#x200B;ディメンションを追加した結果を示しています。このビジュアライゼーションでは、モバイルアプリのユーザーが、商品を買い物かごに追加する前にどのように画面を移動し、アプリケーションを閉じ、オファーを提示されているかといったインサイトが得られます。

![ページディメンションの結果がリストの上部に表示されているフロー。](assets/flowapp-result.png)

## キャンペーンがどのように web 訪問を促しているか

Web サイトへの訪問を推進するキャンペーンを分析します。**[!UICONTROL キャンペーン名]**&#x200B;をディメンションとするフロービジュアライゼーションを作成します

![フロー web キャンペーン名ディメンション](assets/flowweb.png)

最後の&#x200B;**[!UICONTROL キャンペーン名ディメンション]**&#x200B;を&#x200B;**[!UICONTROL 書式設定されたページ名]**&#x200B;ディメンションに置き換え、フロービジュアライゼーションの最後に別の&#x200B;**[!UICONTROL 書式設定されたページ名]**&#x200B;ディメンションを追加します。

![フロー web キャンペーン名および web ページディメンション](assets/flowweb-replace.png)

いずれかのフローにポインタを合わせると、詳細が表示されます。例えば、どのキャンペーンが買い物かごのチェックアウトにつながったかが表示されます。

![フロー web キャンペーン名と web ページディメンションのホバー](assets/flowweb-hover.png)
