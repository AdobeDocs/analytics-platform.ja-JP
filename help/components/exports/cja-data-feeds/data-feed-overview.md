---
description: データフィードを使用してCustomer Journey Analyticsから生データを取得する方法を説明します。 データフィードを使用するための前提条件と次に行うべきことについて説明します。
keywords: クリックストリーム;データフィード;データフィード;データフィード
title: Analytics データフィードの概要
feature: Components
hide: true
hidefromtoc: true
source-git-commit: b0b86424399ea79deca8f1d522d52354dfaaa8c7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 40%

---

# データフィードの概要

データフィードは、Customer Journey Analyticsから生データを取得する強力な方法です。 この生データは、アドビ以外の他のプラットフォームで使用し、組織の裁量で使用できます。データは、各時間の終了時に時間単位のバッチで、または毎日の終わりに日単位のバッチで配信されます。

## 前提条件

データフィードを使用する前に、次の要件をすべて満たしていることを確認してください。

* データをAdobe Customer Journey Analyticsに取り込み、作業中の実装。<!-- For more information, see Data ingestion overview - add link -->
* アカウントがAnalytics製品の管理者であるか、アカウントがデータフィードへのアクセス権を持つ製品プロファイルに属している。<!--???-->
* Amazon S3、Google Cloud Platform、Azure RBAC、またはAzure SASで構成されたバケット。<!--Which cloud providers do we support??-->
* （レガシー：従来のFTPおよびSFTP宛先タイプにのみ必要） FTP サイトと資格情報が手元にある（組織から提供されたFTP資格情報） <!--Delete???-->

## Customer Journey AnalyticsとAdobe Analyticsのデータフィードの比較

Customer Journey Analyticsのデータフィード機能は、Adobe Analyticsとは異なります。 詳しくは、[Customer Journey AnalyticsとAdobe Analyticsのデータフィードの比較](/help/components/exports/cja-data-feeds/df-comparison.md)を参照してください。


## 次の手順

以下のリソースは、データフィードを取得する基本的なワークフローを理解するのに役立ちます。基本的なワークフローを理解したら、組織内のチームと協力して、生データをデータベースに保存または取り込むことができます。

* データフィードのベストプラクティス <!--add link-->: データフィードを作成および管理するためのベストプラクティスです。
* データフィードを作成<!--add link-->: データフィードを作成するための技術的な詳細。個々のフィールドをより詳細に説明します
* データフィードの管理<!--add link-->: データフィードのインターフェイスの操作について詳しく見る
* データフィードの内容<!--add link-->：圧縮ファイル <!-- Is this still the output users can download from the destination? I aske Jun. -->の内容を理解する
* データ列の定義<!--add link-->：使用可能なすべての列の包括的なリスト。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [データフィードインターフェイスの操作](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [データフィード ID の検索](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]
