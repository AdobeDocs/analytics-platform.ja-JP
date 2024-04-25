---
title: Customer Journey Analytics 接続の概要
description: Customer Journey Analytics での接続について説明します。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: dc3a109f162adfe48f621ba3ece95fedead3c6e1
workflow-type: ht
source-wordcount: '184'
ht-degree: 100%

---

# 接続の概要

接続を使用すると、Customer Journey Analytics 製品管理者は、イベント、ルックアップ、プロファイルデータセットなど、様々な [!DNL Adobe Experience Platform] データソースとの接続を確立できます。これらの接続により、接続から派生データビューへのデータの統合を有効にすることができます。接続は CJA の基盤であり、[!DNL Experience Platform] ソースデータセットから作成されます。また、接続へのアクセス権があれば、接続マネージャーを表示し、そこで接続を構成する基になるデータセットを確認したり、重要な編集や設定の選択を行ったりすることもできます。

接続管理へのアクセスを、コア管理グループに制限することをお勧めします。接続レベルでの設定は、Customer Journey Analytics に取り込まれるデータ量の割り当てに関して契約上の影響を受けます。

次に、概要に関するビデオを示します。

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 必要な権限

Customer Journey Analytics 接続を作成するには、[Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) で次の権限が必要です。

Adobe Experience Platform:
* データモデリング：ビュースキーマ、スキーマの管理
* データ管理：ビューデータセット，データセットの管理
* データ取り込み：ソースの管理
* ID 名前空間の表示

Customer Journey Analytics
* 製品管理者アクセス

>[!IMPORTANT]
>
> 複数の [!DNL Experience Platform] データセットを 1 つの接続に組み合わせることができます。
