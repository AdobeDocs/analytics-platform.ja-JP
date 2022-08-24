---
title: CJA アクセス制御
description: CJA の 3 つのレベルのアクセスに対するアクセス制御要件について説明します。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# CJA アクセス制御

Customer Journey Analytics(CJA) は、3 つのアクセスレベルまたは 3 つの役割で管理されます。製品管理者の役割、製品プロファイル管理者の役割、ユーザーレベルのアクセス。 このトピックでは、これらの役割について詳しく説明します。

## 製品管理者の役割

製品管理者には、CJA 内で必要なタスクを完了する権限があります。 製品管理者として、 **Customer Journey Analytics製品プロファイル** 内 [Admin Console](https://adminconsole.adobe.com/enterprise/) Customer Journey Analytics/「管理者」タブ/「管理者を追加」を選択します。 製品管理者には、次の権限が付与されます。

* 接続またはデータ表示の作成／更新／削除を行う
* プロジェクト、フィルター、計算指標、他のユーザーが作成したフィルターの更新／削除を行います。
* Workspace プロジェクトをすべてのユーザーと共有する

Customer Journey Analytics 内で製品管理者になるだけでは、接続を作成、更新または削除することはできません。Experience Platform データセットへの接続を作成するには、Experience Platform 権限も必要です。特に、**Experience Platform 製品プロファイル**&#x200B;の一部であり、次の権限が与えられていることが必要です。

* データモデリング：ビュースキーマ、スキーマの管理
* データ管理：ビューデータセット，データセットの管理
* データ取り込み：ソースの管理
* ID 名前空間の表示

Experience Platform の権限について詳しくは、[Adobe Experience Platform のアクセス制御](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja)を参照してください。

## 製品プロファイル管理者の役割

この役割は製品管理者に似ていますが、範囲がより限られています。 製品プロファイルは、一連の権限です。 例えば、製品プロファイル管理者は、製品プロファイルのメンバーに対して、すべてのまたは特定のデータビューへのアクセス権を付与できます。 レポートツールの場合、これらの管理者は次の権限を追加できます。

![admin console 権限](assets/permissions.png)

## ユーザーレベルのアクセス

製品の非管理者（ユーザー）は、Customer Journey Analyticsでは、データビューや接続を作成、編集または表示できません。 ユーザーは、指標内で特別な権限を持つフィルター、プロジェクト、オーディエンスおよび計算Admin Consoleを作成できます。

## Workspace プロジェクトのキュレーション

Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、セグメント、日付範囲）の制限方法、キュレーションとデータビューとの関連付け方法について詳しくは、 [プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md).

## 個々の指標またはディメンションへのアクセス権を付与する

従来の Adobe Analytics の場合とは異なり、Customer Journey Analytics 内の個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは[データビュー](/help/data-views/data-views.md)で変更できるので、CJA で変更される可能性があります。その場合、レポートも遡って変更されます。

