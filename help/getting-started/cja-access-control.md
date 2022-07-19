---
title: CJA アクセス制御
description: 接続の作成、データセットの追加、データビューの作成などのアクセス制御要件について説明します。
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# CJA アクセス制御

接続を作成したり、データセットを追加したりするには、[Admin Console](https://adminconsole.adobe.com/enterprise/) で次の権限が必要です。

* Customer Journey Analytics にアクセスしたり接続したりするには、[Admin Console](https://adminconsole.adobe.com/enterprise/) で **Customer Journey Analytics 製品**&#x200B;に対する管理者として追加される必要があります。製品管理者には、次の権限が付与されます。
   * 接続またはデータ表示の作成／更新／削除を行う
   * 他のユーザーが作成したプロジェクト、フィルター、計算指標、フィルターの更新／削除を行います。
   * ワークスペースプロジェクトをすべてのユーザーと共有する
* Customer Journey Analytics 内で製品管理者になるだけでは、接続を作成、更新、削除することはできません。Experience Platform データセットへの接続を作成するには、Experience Platform 権限も必要です。特に、**Experience Platform 製品プロファイル**&#x200B;の一部であり、次の権限が与えられていることが必要です。
   * スキーマの表示
   * スキーマの管理
   * ID 名前空間の表示
   * データセットの表示

Experience Platform 権限について詳しくは、「[Adobe Experience Platform のアクセス制御](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja)」を参照してください。

>[!NOTE]
>
>従来の Adobe Analytics の場合とは異なり、Customer Journey Analytics 内の個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは[データビュー](/help/data-views/data-views.md)で変更できるので、CJA で変更される可能性があります。その場合、レポートも遡って変更されます。

## ユーザーアクセス

Customer Journey Analytics の非製品管理者（ユーザー）は、データビューや接続は表示できませんが、フィルター、プロジェクトおよび計算指標を作成できます。