---
title: CJA アクセス制御
description: 接続の作成、データセットの追加、データビューの作成などのアクセス制御要件について説明します。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: e5ae592c6765638e26ee5252f458e82af9d24e44
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# CJA アクセス制御

Customer Journey Analytics にアクセスしてタスクを実行するには、[Admin Console](https://adminconsole.adobe.com/enterprise/) の **Customer Journey Analytics 製品プロファイル**&#x200B;で管理者として追加される必要があります。製品管理者には、次の権限が付与されます。

* 接続またはデータ表示の作成／更新／削除を行う
* プロジェクト、フィルター、計算指標、他のユーザーが作成したフィルターの更新／削除を行います。
* Workspace プロジェクトをすべてのユーザーと共有する

## Adobe Experience Platform 必須権限

Customer Journey Analytics 内で製品管理者になるだけでは、接続を作成、更新または削除することはできません。Experience Platform データセットへの接続を作成するには、Experience Platform 権限も必要です。特に、**Experience Platform 製品プロファイル**&#x200B;の一部であり、次の権限が与えられていることが必要です。

* スキーマの表示
* スキーマの管理
* ID 名前空間の表示
* データセットの表示

Experience Platform 権限について詳しくは、「[Adobe Experience Platform のアクセス制御](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja)」を参照してください。

## 個々の指標またはディメンションへのアクセス権を付与する

従来の Adobe Analytics の場合とは異なり、Customer Journey Analytics 内の個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは[データビュー](/help/data-views/data-views.md)で変更できるので、CJA で変更される可能性があります。その場合、レポートも遡って変更されます。

## ユーザーアクセス

Customer Journey Analytics の非製品管理者（ユーザー）は、データビューや接続は表示できませんが、フィルター、プロジェクトおよび計算指標を作成できます。

## Workspace プロジェクトのキュレーション

プロジェクトレベルでコンポーネント（ディメンション、指標、セグメント、日付範囲）を制限する方法について詳しくは、 [プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md).



