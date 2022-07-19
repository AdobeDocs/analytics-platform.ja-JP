---
title: CJA アクセス制御
description: 接続の作成、データセットの追加、データビューの作成などのアクセス制御要件について説明します。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 53%

---

# CJA アクセス制御

Customer Journey Analyticsでタスクにアクセスして実行するには、管理者として **Customer Journey Analytics製品プロファイル** 内 [Admin Console](https://adminconsole.adobe.com/enterprise/). 製品管理者には、次の権限が付与されます。

* 接続またはデータビューの作成/更新/削除
* 他のユーザーが作成したプロジェクト、フィルター、計算指標、フィルターの更新／削除を行います。
* Workspace プロジェクトをすべてのユーザーと共有

## 必要なAdobe Experience Platform権限

接続の作成、更新、削除をおこなうのに、Customer Journey Analyticsだけで製品管理者になるだけでは十分ではありません。 Experience Platform データセットへの接続を作成するには、Experience Platform 権限も必要です。特に、**Experience Platform 製品プロファイル**&#x200B;の一部であり、次の権限が与えられていることが必要です。

* スキーマの表示
* スキーマの管理
* ID 名前空間の表示
* データセットの表示

Experience Platform 権限について詳しくは、「[Adobe Experience Platform のアクセス制御](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja)」を参照してください。

## 個々の指標またはディメンションへのアクセス権の付与

従来の Adobe Analytics の場合とは異なり、Customer Journey Analytics 内の個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは[データビュー](/help/data-views/data-views.md)で変更できるので、CJA で変更される可能性があります。その場合、レポートも遡って変更されます。

## ユーザーアクセス

Customer Journey Analyticsの非製品管理者（ユーザー）は、データ表示や接続は表示できませんが、フィルター、プロジェクトおよび計算指標を作成できます。

