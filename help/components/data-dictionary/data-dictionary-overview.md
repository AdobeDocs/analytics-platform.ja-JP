---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素の概要
feature: Components
role: User, Admin
exl-id: 8e4b8169-7c7f-4a58-a6c6-70efb0c86ce8
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 67%

---

# データ要素の概要

Analysis Workspace のデータ要素は、ユーザーと管理者の両方が Analytics 環境のコンポーネントを追跡し、よりよく理解するのに役立ちます。

Analytics 管理者は、データディクショナリ内の各コンポーネントに関する情報をキュレーションして、ユーザーが利用できるようにする必要があります。

>[!VIDEO](https://video.tv.adobe.com/v/3418028/?quality=12&learn=on)

## ユーザーにとってのメリット

データ要素は、ユーザーが使用可能な各コンポーネントをよりよく理解するのに役立ちます。

データ要素には、次の情報が含まれます。

* コンポーネントの機能と使用目的

* 表示しているコンポーネントで通常使用されるコンポーネント

* 表示しているコンポーネントに類似するコンポーネント

* コンポーネントがシステム管理者によって承認済みであるかどうか

データディクショナリへのアクセス方法とデータディクショナリに含まれる情報の詳細については、 [データディクショナリでのコンポーネント情報の表示](/help/components/data-dictionary/view-data-dictionary.md).

## 管理者にとってのメリット

データ要素は、システム管理者が Analytics 環境内のコンポーネントを追跡し、キュレートするのに役立ちます。

Analytics 管理者がデータ要素を使用する方法の一部を以下に示します。

* 統合が必要な重複コンポーネントを識別します。

* データを収集していないコンポーネントを識別して、更新または削除できるようにします。

* まだ承認されていないコンポーネントを識別します。

* コンポーネントの説明を Analysis Workspace で直接更新します。データディクショナリ内のコンポーネントの説明に対する更新は、データビューに反映されます。

  同様に、データビュー内のコンポーネントの説明に対する更新は、Analysis Workspaceにも反映されます。

  Analysis Workspaceまたはデータビューでコンポーネントの説明を追加する方法について詳しくは、 [コンポーネントの説明を追加](/help/components/add-component-descriptions.md).

## データ要素へのアクセス

Analysis Workspace 内で、次のいずれかの方法でデータ要素にアクセスできます。

* 左側のパネルの「**データ要素**」アイコンから。

  ![左側のパネルの「データ要素」アイコン](assets/data-dictionary-access-icon.png)

* コンポーネントの情報ポップオーバー内の「**データ要素**」アイコンから。

  ![情報ポップオーバー内の「データ要素」アイコン](assets/data-dictionary-access-infopopover.png)
  <!--update screenshot; this was taken from a mock-->

* [!UICONTROL **ヘルプ**]／[!UICONTROL **データ要素**]&#x200B;メニューから。

データディクショナリで使用できる様々なオプションについて詳しくは、 [データディクショナリでのコンポーネント情報の表示](/help/components/data-dictionary/view-data-dictionary.md).

## データディクショナリの更新とキュレーション

Customer Journey Analytics管理者は、組織の健全なデータディクショナリを維持する責任を負います。詳しくは、 [データ辞書の正常性の監視](/help/components/data-dictionary/monitor-data-dictionary-health.md).

このプロセスの一環として、Customer Journey Analytics管理者は、データディクショナリ内の各コンポーネントに関する情報を編集できます。詳しくは、 [データディクショナリ内のコンポーネントエントリの編集](/help/components/data-dictionary/edit-entries-data-dictionary.md).

## データ要素を移動、最小化または閉じる

データ要素を開くと（[データ要素へのアクセス](#access-the-data-dictionary)で説明しているように）、Analysis Workspace の上にウィンドウとして表示されます。

データ要素ウィンドウは、次のいずれかの方法で操作できます。

* Analysis Workspace 内の任意の領域にドラッグ

  Analysis Workspace を閉じて再度開いた場合、データ要素ウィンドウは最後に移動した場所に残ります。<!--True?-->

* 最小化

  最小化すると、データ要素は、Analysis Workspace の右下隅に青いタブとして表示されます。

  青いタブを選択すると、データ要素が開き、最後に表示していたコンポーネントが表示されます。

* 閉じる
