---
title: Customer Journey Analytics 接続の概要
description: Customer Journey Analytics での接続について説明します。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: a2262e446a15ee58be2f3f674c77223368fc8f76
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# 接続の概要

接続を使用すると、Customer Journey Analytics 製品管理者は、イベント、ルックアップ、プロファイルデータセットなど、様々な [!DNL Adobe Experience Platform] データソースとの接続を確立できます。これらの接続により、接続から派生データビューへのデータの統合を有効にすることができます。接続は CJA の基盤であり、[!DNL Experience Platform] ソースデータセットから作成されます。また、接続へのアクセス権があれば、接続マネージャーを表示し、そこで接続を構成する基になるデータセットを確認したり、重要な編集や設定の選択を行ったりすることもできます。

接続管理へのアクセスを、コア管理グループに制限することをお勧めします。接続レベルでの設定は、Customer Journey Analytics に取り込まれるデータ量の割り当てに関して契約上の影響を受けます。

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target=&#34;_blank&#34;} for a demo video.

>[!ENDSHADEBOX]

-->

## 必要な権限

Customer Journey Analytics 接続を作成するには、次の権限が必要です。権限について詳しくは、[Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) および [Adobe Experience Platform 権限](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/home)のドキュメントを参照してください。

### Adobe Admin Console 内：

* Customer Journey Analytics：製品管理者
* Adobe Experience Platform：*AEP-Default-All-Users* という名前の製品プロファイルに追加されました

### Adobe Experience Platform 権限内：

* データモデリング：ビュースキーマ、スキーマの管理
* データ管理：ビューデータセット，データセットの管理
* データ取り込み：ソースの管理
* Identity Management：ID 名前空間の表示
* サンドボックス：関連する Customer Journey Analytics 接続で使用されるサンドボックス

>[!IMPORTANT]
>
>複数の [!DNL Experience Platform] データセットを 1 つの接続に組み合わせることができます。
